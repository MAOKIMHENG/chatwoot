# MAQSU Chatwoot Customizations

This file tells an AI assistant which Chatwoot application changes must be preserved when updating this fork from the latest Chatwoot version.

Last reviewed: 2026-07-14

## Desired behavior

Replace the original clickable Chatwoot branding and logo with this plain, non-clickable notice:

> MAQSU AI can make mistakes. Please verify important info.

The notice is shared by the chat widget and survey. It remains hidden when the existing `disableBranding` prop is enabled.

## Changed files

### `app/javascript/shared/components/Branding.vue`

- Removed the branding logo, link, redirect URL, and unused branding logic.
- Displays the translated `AI_DISCLAIMER` text.
- Preserves the existing `disableBranding` behavior.

When updating Chatwoot, adapt this behavior to the latest upstream component instead of blindly replacing the new file with an old copy.

### `app/javascript/widget/i18n/locale/en.json`

Added:

```json
"AI_DISCLAIMER": "MAQSU AI can make mistakes. Please verify important info."
```

### `app/javascript/survey/i18n/locale/en.json`

Added the same translation because the survey also uses `Branding.vue`:

```json
"AI_DISCLAIMER": "MAQSU AI can make mistakes. Please verify important info."
```

## Update checklist for an AI assistant

1. Inspect the latest upstream versions of the three files listed above.
2. Preserve the latest upstream structure and reapply the desired behavior.
3. Do not restore the old logo, branding link, or redirect URL.
4. Ensure both English locale files contain `AI_DISCLAIMER`.
5. Verify the widget and survey display the notice and that it is not clickable.
6. Do not modify unrelated Chatwoot files.
