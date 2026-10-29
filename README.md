# ARC Music — Obsidian Glass

Tema original para **Spicetify** com preto obsidiana, cobre metálico, vidro fumê e violeta pontual.

**Versão:** 0.1 (experimental, ainda não testada no Spotify local).

## Visual
- Painéis laterais e player com transparência e desfoque.
- Cobre nos elementos de destaque; violeta em reprodução, foco e progresso.
- Dois esquemas: `Base` e `Velvet` (mais violeta).
- Movimento reduzido respeitado; nenhuma extensão JS ou fonte externa.

## Instalar no Windows

Requer Spotify desktop e Spicetify funcionando corretamente. Caso ainda exista o erro `Cannot detect Spotify location`, primeiro é necessário resolver o caminho do Spotify.

Abra o PowerShell normal (não como administrador):

```powershell
$destination = Join-Path $env:APPDATA "spicetify\Themes\ObsidianGlass"
New-Item -ItemType Directory -Force -Path $destination | Out-Null
$base = "https://raw.githubusercontent.com/oliviacachoeira92-ux/arc-music-spicetify/feat/obsidian-glass-v0.1/ObsidianGlass"
Invoke-WebRequest "$base/color.ini" -OutFile (Join-Path $destination "color.ini")
Invoke-WebRequest "$base/user.css" -OutFile (Join-Path $destination "user.css")
spicetify config current_theme ObsidianGlass color_scheme Base
spicetify backup apply
```

Após integrar o tema à branch `main`, substituir `feat/obsidian-glass-v0.1` por `main` na variável `$base`.

### Alternar esquema
```powershell
spicetify config color_scheme Velvet
spicetify apply
```

### Restaurar o tema padrão
```powershell
spicetify config current_theme ""
spicetify apply
```

## Arquivos
- `ObsidianGlass/color.ini`: cores dos esquemas.
- `ObsidianGlass/user.css`: glassmorphism e acabamento visual.

**Observação:** classes CSS do Spotify podem mudar após atualizações. Alguns efeitos dependerão do comportamento de transparência do aplicativo. O primeiro teste deverá validar essas diferenças.

Não afiliado ao Spotify ou Spicetify.
