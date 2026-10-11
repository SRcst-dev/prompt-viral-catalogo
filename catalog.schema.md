# Catálogo remoto — schema v1

Arquivo JSON único, hospedado em URL estática. Raiz:

| Campo | Tipo | Notas |
|---|---|---|
| `schemaVersion` | int | 1 |
| `version` | int | sobe a cada publicação; o app só troca se for maior |
| `updatedAt` | string | ISO 8601 |
| `categories[]` | `{id, name, icon, order}` | `icon` = nome de símbolo (ver app) |
| `items[]` | ver abaixo | |

Item:

| Campo | Tipo | Notas |
|---|---|---|
| `id`, `title`, `description` | string | |
| `category` | string | `id` de categoria |
| `type` | `video` \| `image` | |
| `thumbnailUrl`, `previewUrl` | string? | sem thumbnail, usa `gradient` |
| `gradient` | [hex, hex] | |
| `aiTools[]` | `{name, url, pricing: free\|freemium\|paid, note?}` | |
| `requiredMaterials[]` | string | vazio = nenhuma imagem |
| `prompt`, `promptPt?` | string | `{chave}` = variável |
| `variables[]` | `{key, label, default, options?[]}` | |
| `tutorial[]` | `{title, description, link?}` | |
| `settings` | `{aspectRatio?, duration?}` | |
| `tips[]` | string | |
| `difficulty` | `easy` \| `medium` \| `hard` | |
| `tags[]` | string | |
| `isTrending`, `isPublished` | bool | |
| `popularity` | int | |
| `createdAt` | `YYYY-MM-DD` | |
| `publishAt?` | `YYYY-MM-DD` | futuro = oculto |
