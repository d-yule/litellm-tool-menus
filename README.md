# litellm-tool-menus

Trimmed OpenAPI spec files ("menus") for exposing a limited set of an app's API actions as tools through LiteLLM's MCP gateway.

**No secrets belong here.** API keys go into LiteLLM, never into this repo.

## businessmap/

Cut down from Businessmap's published API v2 description, which has 764 actions.

| File | Actions |
|---|---|
| `businessmap_read.json` | 18 look-ups: current user, users, boards, board structure, columns, lanes, workflows, custom fields, cards, comments, parent/child cards, subtasks |
| `businessmap_write.json` | The 18 look-ups, plus: create card, update card, add comment, set custom field, link parent/child card, add subtask |

Neither file contains any delete action, or anything that changes boards, columns, users or settings.

Use: in LiteLLM, **MCP Servers → Custom Server → OpenAPI Spec**, point it at the raw file link, and send the Businessmap API key as header `apikey`.
