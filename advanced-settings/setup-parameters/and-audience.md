---
description: Secure Public Stream Publishing
---

# \&audience

The `&audience` parameter in VDO.Ninja enables secure public stream publishing, ideal for website [embedding (using Iframes)](../../guides/iframe-api-documentation.md) while preventing unauthorized publishing.

### Key Features

* Publishers get a unique publishing token, separate from the stream ID
* Viewers use a different audience token to access the stream
* Publishing requires both stream ID and publishing token
* Maintains compatibility with existing code structure

### Example Usage:

```
# Publisher Link:
https://vdo.ninja/?audience=12345abcPublishingToken&push=JkYwyxy

# Viewer Link:
https://vdo.ninja/?audience=HrDrNy3jiA50QzlU&view=JkYwyxy
```

### Technical Details

* Works with single streams only (not compatible with rooms)
* Password functionality remains mostly intact
* Public audience link appears in header unless `&cleanoutput` is used
* New publishers will establish new P2P connections while maintaining existing ones

### Security Notes

* Keep publishing tokens private and unique
* P2P connections may expose public IP addresses
* Exercise caution with untrusted sources due to potential zero-day exploits
* System automatically identifies roles based on `&view` and `&push` parameters
