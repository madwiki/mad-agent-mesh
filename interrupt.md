# interrupt

Use `interrupt` when the currently active runner turn for one specific `mams_channel` must stop immediately.

This works for:

- a direct wrapper call such as `sync`, `review-this-plan`, or `execute-this-plan`
- a request currently running inside `invoke`

`interrupt` targets exactly one `mams_channel`, chosen by `--mams-channel <name>`.

Input is optional. You may pass a short JSON object to record why the interruption was requested:

```json
{
  "reason": "The current direction is wrong."
}
```

If no input is needed, you may call it with empty stdin.
