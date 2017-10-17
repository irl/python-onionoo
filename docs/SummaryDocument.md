# SummaryDocument

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**version** | **str** | Onionoo protocol version string. | 
**next_major_version_scheduled** | **str** | UTC date (YYYY-MM-DD) when the next major protocol version is scheduled to be deployed. Omitted if no major protocol changes are planned. | [optional] 
**build_revision** | **str** | Git revision of the Onionoo instance&#39;s software used to write this response, which will be omitted if unknown. | [optional] 
**relays_published** | **str** | UTC timestamp (YYYY-MM-DD hh:mm:ss) when the last known relay network status consensus started being valid. Indicates how recent the relay objects in this document are. | 
**relays_skipped** | **float** | Number of skipped relays as requested by a positive \&quot;offset\&quot; parameter value. Omitted if zero. | [optional] 
**relays_truncated** | **float** | Number of truncated relays as requested by a positive \&quot;limit\&quot; parameter value. Omitted if zero. | [optional] 
**relays** | [**list[RelaySummaryObject]**](RelaySummaryObject.md) |  | 
**bridges_published** | **str** | UTC timestamp (YYYY-MM-DD hh:mm:ss) when the last known bridge network status consensus started being valid. Indicates how recent the relay objects in this document are. | 
**bridges_skipped** | **float** | Number of skipped bridges as requested by a positive \&quot;offset\&quot; parameter value. Omitted if zero. | [optional] 
**bridges_truncated** | **float** | Number of truncated bridges as requested by a positive \&quot;limit\&quot; parameter value. Omitted if zero. | [optional] 
**bridges** | [**list[BridgeSummaryObject]**](BridgeSummaryObject.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


