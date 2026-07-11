# Spec: Golden Audit Trail JSON Schema

The following schema defines the mandatory structure for all agentic logs in the O&G framework. This ensures compatibility with WORM storage and regulatory forensics.

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "OG_Agent_Audit_Log",
  "type": "object",
  "properties": {
    "metadata": {
      "type": "object",
      "properties": {
        "session_id": { "type": "string" },
        "agent_id": { "type": "string" },
        "asset_class": { "enum": ["Informational", "Operational", "Critical"] },
        "timestamp": { "type": "string", "format": "date-time" }
      },
      "required": ["session_id", "agent_id", "asset_class", "timestamp"]
    },
    "trace": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "step": { "type": "integer" },
          "thought": { "type": "string" },
          "action": { "type": "string" },
          "tool_input": { "type": "object" },
          "tool_output": { "type": "string" },
          "confidence": { "type": "number", "minimum": 0, "maximum": 1 },
          "hitl_approval": {
            "type": "object",
            "properties": {
              "tier": { "enum": ["1", "2", "3"] },
              "approver_id": { "type": "string" },
              "approval_timestamp": { "type": "string", "format": "date-time" },
              "pvs_signature_id": { "type": "string" }
            }
          }
        },
        "required": ["step", "thought", "action", "tool_output"]
      }
    },
    "compliance_tag": {
      "type": "string",
      "description": "Mapping to API RP 75 or ISO 27001 section"
    }
  },
  "required": ["metadata", "trace"]
}
```
