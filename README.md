# Bilibili MCP

This public listing provides connection metadata and client examples for the hosted SocialDataX Bilibili MCP service. The implementation is privately hosted; this directory contains public connection materials only.

## Service

- Hosted MCP endpoint: `https://mcp.socialdatax.com/bilibili/mcp`
- Hosted transport: `streamable-http`
- Authentication: `Authorization: Bearer <SOCIALDATAX_API_KEY>`
- Product: `SocialDataX` / `社媒数据助手`
- Website and API Key access: <https://socialdatax.com/ai?from=github>
- Registry name: `com.52choujiang/bilibili-insights`
- Future registry name: `com.socialdatax/bilibili-insights`
- Current public capability version: `0.1.2`

## Scope

Use this service for public Bilibili video, article, dynamic, creator, comment, reaction, download-manifest, and speech-to-text research. It does not provide account login, posting, editing, liking, commenting, following, or other account actions.

## Tools

The public server card is the source of truth for descriptions and schemas. The current tools are:

| Tool | Purpose |
| --- | --- |
| `socialdatax_get_points_balance` | Query the current API Key account balance. |
| `bilibili_search_videos` | Search public videos; use when a search term is available, and continue with `page_token`. |
| `bilibili_search_articles` | Search public articles; use when a search term is available, and continue with `page_token`. |
| `bilibili_get_content_detail_by_id` | Read video, article, or dynamic details from a content ID. |
| `bilibili_get_content_detail_by_url` | Read details from a Bilibili link or share text. |
| `bilibili_get_video_download_links` | Read a video download manifest from a video URL. |
| `bilibili_get_content_comments_by_id` | Read first-level comments from a content ID. |
| `bilibili_get_content_comments_by_url` | Read first-level comments from a content link. |
| `bilibili_get_content_comment_replies_by_comment_id` | Read replies using the content target and first-level comment ID. |
| `bilibili_get_content_likes_and_reposts_by_post_id` | Read article or dynamic likes and reposts by post ID. |
| `bilibili_get_content_likes_and_reposts_by_url` | Read article or dynamic likes and reposts by URL. |
| `bilibili_get_user_info_by_user_id` | Read a creator profile by user ID. |
| `bilibili_get_user_info_by_profile_url` | Read a creator profile from a profile URL. |
| `bilibili_get_user_posted_videos_by_user_id` | Read a creator's public videos by user ID. |
| `bilibili_get_user_posted_videos_by_profile_url` | Read a creator's public videos by profile URL. |
| `bilibili_get_user_posted_articles_by_user_id` | Read a creator's public articles by user ID. |
| `bilibili_get_user_posted_articles_by_profile_url` | Read a creator's public articles by profile URL. |
| `bilibili_get_user_posted_dynamics_by_user_id` | Read a creator's public dynamics by user ID. |
| `bilibili_get_user_posted_dynamics_by_profile_url` | Read a creator's public dynamics by profile URL. |
| `bilibili_submit_video_speech_text_by_video_url` | Submit transcript work from a video URL. |
| `bilibili_submit_video_speech_text_by_bvid` | Submit transcript work from a BV ID. |
| `bilibili_get_video_speech_text_job` | Check a submitted transcript job by `job_id`. |

Search tools support opaque `page_token` pagination. When a Bilibili link or ID is already available, use the matching detail, comment, creator, or transcript tool instead of searching again.

## Quick Start

Use the hosted endpoint directly when the client supports authenticated `streamable-http`:

```json
{
  "mcpServers": {
    "socialdatax-bilibili": {
      "type": "streamable_http",
      "url": "https://mcp.socialdatax.com/bilibili/mcp",
      "headers": {"Authorization": "Bearer <SOCIALDATAX_API_KEY>"}
    }
  }
}
```

For command/stdio-only clients, use `npx -y mcp-remote https://mcp.socialdatax.com/bilibili/mcp --header "Authorization: Bearer <SOCIALDATAX_API_KEY>"`. See the files in [examples](examples/) for client-specific configuration.

Request or manage API access at <https://socialdatax.com/ai?from=github>. Never commit a real API Key.

## Directory Metadata

- [server-card.json](server-card.json) is the directory metadata for this hosted service.
- [mcp.json](mcp.json) is the command/stdio fallback configuration.
- [SUBMISSION_CHECKLIST.md](SUBMISSION_CHECKLIST.md) records the publication checks.
