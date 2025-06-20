---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "fabric_eventstream_source_connection Data Source - terraform-provider-fabric"
subcategory: ""
description: |-
  The Eventstream Source Connection data-source allows you to retrieve details about a Fabric Eventstream Source Connection https://learn.microsoft.com/fabric/real-time-intelligence/event-streams/overview.
  -> This data-source supports Service Principal authentication.
  ~> This data-source is in preview. To access it, you must explicitly enable the preview mode in the provider level configuration.
---

# fabric_eventstream_source_connection (Data Source)

The Eventstream Source Connection data-source allows you to retrieve details about a Fabric [Eventstream Source Connection](https://learn.microsoft.com/fabric/real-time-intelligence/event-streams/overview).

-> This data-source supports Service Principal authentication.

~> This data-source is in **preview**. To access it, you must explicitly enable the `preview` mode in the provider level configuration.

## Example Usage

```terraform
# Get data-source details
data "fabric_eventstream_source_connection" "example" {
  workspace_id   = "00000000-0000-0000-0000-000000000000"
  eventstream_id = "11111111-1111-1111-1111-111111111111"
  source_id      = "22222222-2222-2222-2222-222222222222"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `eventstream_id` (String) The eventstream ID.
- `source_id` (String) The source ID.
- `workspace_id` (String) The workspace ID.

### Optional

- `timeouts` (Attributes) (see [below for nested schema](#nestedatt--timeouts))

### Read-Only

- `access_keys` (Attributes) The access keys for the event hub. (see [below for nested schema](#nestedatt--access_keys))
- `event_hub_name` (String) The name of the event hub.
- `fully_qualified_namespace` (String) The fully qualified namespace of the event hub.

<a id="nestedatt--timeouts"></a>

### Nested Schema for `timeouts`

Optional:

- `read` (String) A string that can be [parsed as a duration](https://pkg.go.dev/time#ParseDuration) consisting of numbers and unit suffixes, such as "30s" or "2h45m". Valid time units are "s" (seconds), "m" (minutes), "h" (hours).

<a id="nestedatt--access_keys"></a>

### Nested Schema for `access_keys`

Read-Only:

- `primary_connection_string` (String, Sensitive) The primary connection string for the event hub.
- `primary_key` (String, Sensitive) The primary key for the event hub.
- `secondary_connection_string` (String, Sensitive) The secondary connection string for the event hub.
- `secondary_key` (String, Sensitive) The secondary key for the event hub.
