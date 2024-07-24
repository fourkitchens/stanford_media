# 1. Editors can more clearly see what a change to media will affect
Date: 2024-07-23

## Status

Proposed

## Context

Based on ticket [SHS-5630](https://fourkitchens.clickup.com/t/36718269/SHS-5630), it was requested that when editing a media entity, if that entity is used someplace, to add a link inside the warning message that already existed. The link would open in a new tab (because sometimes editing media happens inside a modal) and would go to the `/media/xxx/usage` page to more easily allow editors to view the usage of the media with ID `xxx`.

## Decision

We modified the `stanford_media.module` to add the link to the text "piece of content" or "pieces of content" depending on the count of media items. The link is created with `FormattableMarkup`.

Since the styling of the link inside of the warning message was white on orange and not accessible, we also added the `stanford_media.admin.css` to that form and styled links inside of warning messages to be black and bold. It retains an underline as well.

## Consequences

When editing a media entity that is being used someplace, it now shows a link (which opens in a new tab) in the warning message to better allow an editor to see usage.
