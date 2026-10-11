# Bilibili MCP Directory Submission Checklist

## Metadata

- Registry name: `com.52choujiang/bilibili-insights`
- Future registry name: `com.socialdatax/bilibili-insights`
- Version: `0.1.3`
- Endpoint: `https://mcp.socialdatax.com/bilibili/mcp`
- Auth: `Authorization: Bearer <SOCIALDATAX_API_KEY>`
- Website and API Key access: <https://socialdatax.com/ai?from=github>
- Transport: hosted `streamable-http`; command/stdio fallback uses `mcp-remote`
- License: MIT for public documentation and configuration examples only
- Product: `SocialDataX` / `社媒数据助手`
- current 24 public tools are listed in `server-card.json`.

## Safety and publication checks

- No real API Key, private backend code, production configuration, internal sample, or account data is present.
- `server-card.json` and `registry/bilibili/server.json` describe local capability metadata; verify the hosted card independently before submission.
- The hosted card must expose these transcript tools before publication: `bilibili_submit_video_speech_text_by_video_url`, `bilibili_submit_video_speech_text_by_bvid`, `bilibili_get_video_speech_text_job`.
- The hosted card must expose `bilibili_search_videos`, `bilibili_get_content_detail_by_url`, `bilibili_get_content_comments_by_url`, and `bilibili_get_user_info_by_profile_url`.
- Search and list calls pass the opaque `page_token` returned by the service for continuation.
- `examples/codex_config.toml` uses `bearer_token_env_var = "SOCIALDATAX_API_KEY"`.
- `examples/cursor_mcp.json` uses the remote URL and `${env:SOCIALDATAX_API_KEY}`.
- `mcp.json` and `examples/claude_desktop_config.json` are explicit `mcp-remote` fallbacks.
- Validate JSON and the official Registry file before submission; do not treat a hosted server card as a Registry publication.

## Required files

`README.md`, `LICENSE`, `server-card.json`, `mcp.json`, `glama.json`, all files under `examples/`, and `assets/logo.png`.

本地 `0.1.3` 候选新增 `bilibili_search_users`（用户搜索，支持 `page_token`）与 `bilibili_search_suggestions`（搜索联想，不分页）。尚未部署或发布 Registry，发布后需复验。
