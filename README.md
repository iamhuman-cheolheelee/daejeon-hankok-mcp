# Daejeon Hankok MCP server (대전한콕)

[![mcptry](https://mcptry.com/badge/com.ferrorium.daejeon/hankok)](https://mcptry.com/servers/com.ferrorium.daejeon/hankok)

<img src="icon.png" width="96" alt="Daejeon Hankok icon">

A free, read-only remote MCP server for local life in Daejeon, Korea. It covers about 8,600 restaurants, cafes, hair salons and nail shops with opening hours, prices, parking and Naver booking links, plus hair designers, festivals and budget-friendly "good price" shops. Shop lists for the rest of Korea, by province, district and neighborhood, cover about 580,000 more places.

No sign-in, no API key and nothing to install.

- Endpoint: `https://daejeon.ferrorium.com/mcp` (Streamable HTTP)
- Website: https://daejeon.ferrorium.com
- Connection guide: https://daejeon.ferrorium.com/ai
- Registry name: `com.ferrorium.daejeon/hankok` in the official MCP Registry

## Connect

Claude Code

```sh
claude mcp add --transport http hankok https://daejeon.ferrorium.com/mcp
```

Claude Desktop, claude.ai and ChatGPT: add a custom connector with the URL above.

Cursor, VS Code, Windsurf and other clients that read an `mcpServers` config:

```json
{
  "mcpServers": {
    "hankok": { "url": "https://daejeon.ferrorium.com/mcp" }
  }
}
```

Clients that only speak stdio can bridge with `npx mcp-remote https://daejeon.ferrorium.com/mcp`.

## Tools

All tools are read-only and marked with `readOnlyHint`.

| Tool | What it does |
|---|---|
| list_areas | Neighborhoods, categories and situation tags with shop counts. Use it to pick values for the other tools. |
| list_places | Shops of one category in one neighborhood, nearest first, with address, booking, hours, price range and parking. |
| get_place | Full detail of a shop: address, coordinates, hours, phone, parking, Naver booking URL, menu or service prices. |
| search_places | Find shops by name, menu, service or address. Daejeon first, then shops across Korea by name and area. |
| list_region_places | Shops of one category in any region of Korea outside Daejeon. Takes a name like 성수동 or 해운대구, or a region code. |
| places_near | Shops around a coordinate, nearest first, up to 10 km. |
| events_and_deals | Daejeon festivals, shows and exhibitions, or government listed good price shops. |
| search_stylists | Hair designers by name, specialty (perm, bleach, layered cut), salon or neighborhood. |
| get_stylist | Designer detail: salon, address, specialties, photo count, Naver booking URL, salon prices. |
| stylists_near | Hair designers around a coordinate, up to 10 km. |
| search | ChatGPT style search across shops and designers. Open a result with fetch. |
| fetch | Full text of a search result id such as `p/food/1001646519` or `d/3812316`. |

Tool descriptions are written in Korean because most questions about Daejeon are asked in Korean. Every argument has a description and an example.

## Example questions

- 둔산동에서 지금 열려 있는 마라탕집 알려 줘
- Find a hair designer good at hippie perm near Daejeon Station and give me the booking link
- 이번 주말 대전 축제 뭐 있어?
- 만원 이하 점심 되는 착한가격업소 유성구
- 성수동 카페 중에 네이버 예약 되는 곳

## Data

Shop data comes from public Naver Place pages, the Ministry of the Interior and Safety good price shop list, KOPIS and Daejeon tourism event listings. Each answer links back to the source page. Shop owners can ask for removal at https://daejeon.ferrorium.com/about.

## 한국어

대전한콕은 대전 맛집, 카페, 헤어, 네일 약 8,600곳과 헤어 디자이너, 행사, 착한가격업소를 AI 에게 알려 주는 무료 MCP 서버입니다. 로그인과 키가 필요 없고 읽기만 합니다. 위 주소를 커넥터로 추가하면 바로 씁니다.

## License

The documentation in this repository is MIT licensed. The server itself is operated at daejeon.ferrorium.com.
