[Documentation](https://learn.microsoft.com/en-us/training/paths/develop-solutions-that-use-blob-storage/)

Blob storage is Azures solution for cloud object storage. It can store anything from audio/image/video to log files. Cloud storage accounts can be standard (general purpose v2) or premium. With the premium accounts having the advantage of using solid state drives. Premium accounts can store information as block blobs, page blobs or file shares/append blobs.

Block blobs have the following options when it comes to access:

- Hot tier: best for frequently accessed data. Has the highest monetary cost but lowest latency.
- Cool tier: best for infrequently accessed data (> 30 days, Cold tier available for storage > 90 days). Has lower monetary cost but higher latency.
- Archive tier: best for data that is accessed not often (> 180 days) and latency of upto several hours can be tolerated. Most cost effective option.

[Security on Blob Storage](https://learn.microsoft.com/en-us/training/modules/explore-azure-blob-storage/4-blob-storage-security)

## AZURE BLOB STORAGE LIFECYCLE

Blog storage offers lifecycle management that can be configured at the account level. It allows you to set policies that enable data transition between various tiers based on their frequency of use.
