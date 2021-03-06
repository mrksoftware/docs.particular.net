---
title: Azure Storage Queues Sanitization
component: ASQ
versions: '[8,)'
tags:
- Azure
related:
- transports/azure-storage-queues/configuration
- samples/azure/storage-queues
reviewed: 2017-10-06
---


In Versions 8.0 and above, the Azure Storage Queues transport no longer sanitizes queues by default.


## Azure Storage Queues naming rules

 1. A queue name must start with a letter or number, and can only contain letters, numbers, and the dash (`-`) character.
 1. The first and last letters in the queue name must be alphanumeric.
 1. The dash (`-`) character cannot be the first or last character.
 1. Consecutive dash characters are not permitted in the queue name.
 1. All letters in a queue name must be lowercase.
 1. A queue name must be between 3 and 63 characters long.


## Custom sanitization

To sanitize queue names, a sanitization function containing the required logic can be registered.

snippet: AzureStorageQueueSanitization

When an endpoint is started, the sanitizer function will be invoked for each queue the transport creates.


## Backwards compatibility

To obtain sanitizing logic backwards compatible with the transport versions below 8.0, refer to the Azure Storage Queues sample.
