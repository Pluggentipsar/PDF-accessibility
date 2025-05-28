# Instruktioner för att ladda upp till GitHub

## Steg för att skapa ett nytt repository utan känslig information:

### 1. Skapa nytt repository på GitHub
- Gå till GitHub.com
- Klicka på "New repository"
- Namnge ditt repository (t.ex. "tillganglighet-ai")
- Välj "Public" eller "Private"
- **SKAPA INTE** med README, .gitignore eller license (vi har redan dessa)

### 2. Förbered dina filer lokalt
Du behöver bara ladda upp dessa viktiga filer/mappar:

**Viktiga filer att inkludera:**
- `package.json` och `package-lock.json`
- `client/` mappen (hela frontend)
- `server/` mappen (hela backend)
- `shared/` mappen (delade typer)
- `components.json`
- `drizzle.config.ts`
- `postcss.config.js`
- `tailwind.config.ts`
- `tsconfig.json`
- `vite.config.ts`
- `.gitignore` (den uppdaterade versionen)
- `.env.example` (den nya filen)

**UNDVIK dessa filer:**
- `.env` (innehåller dina riktiga nycklar)
- `node_modules/` (installeras automatiskt)
- `.git/` mappen (den gamla git-historiken)

### 3. Ladda upp till GitHub
Du kan antingen:

**Alternativ A: Använd GitHub Web Interface**
- Drag and drop filerna direkt på GitHub
- Eller använd "uploading an existing file" länken

**Alternativ B: Kommandoraden (rekommenderat)**
```bash
# I din projektmapp (utan .git)
git init
git add .
git commit -m "Initial commit - TillgängligAI accessibility tool"
git branch -M main
git remote add origin https://github.com/DITT-ANVÄNDARNAMN/DITT-REPOSITORY-NAMN.git
git push -u origin main
```

### 4. Säkerställ att miljövariabler fungerar
När någon klonar ditt repository behöver de:
1. Kopiera `.env.example` till `.env`
2. Fylla i sina egna Azure OpenAI nycklar
3. Konfigurera sin egen databas

Dina känsliga nycklar kommer aldrig att exponeras!