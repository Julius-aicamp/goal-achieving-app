<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Momentum Mastered — Code Export</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/styles/github-dark.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/highlight.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/languages/typescript.min.js"></script>
<style>
  :root {
    --bg: #0d1117;
    --panel: #161b22;
    --border: #30363d;
    --text: #c9d1d9;
    --text-muted: #8b949e;
    --accent: #ff8a3d;
  }
  * { box-sizing: border-box; }
  body {
    margin: 0;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    background: var(--bg);
    color: var(--text);
    display: flex;
    min-height: 100vh;
  }
  nav {
    width: 300px;
    flex-shrink: 0;
    background: var(--panel);
    border-right: 1px solid var(--border);
    padding: 1rem 0;
    height: 100vh;
    position: sticky;
    top: 0;
    overflow-y: auto;
  }
  nav h1 {
    font-size: 15px;
    padding: 0 1rem 0.75rem;
    margin: 0 0 0.5rem;
    border-bottom: 1px solid var(--border);
    color: #fff;
  }
  nav h1 span { color: var(--accent); }
  .nav-group-label {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    color: var(--text-muted);
    padding: 12px 1rem 4px;
  }
  .nav-link {
    display: block;
    padding: 4px 1rem;
    font-size: 12.5px;
    color: var(--text);
    text-decoration: none;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    font-family: ui-monospace, SFMono-Regular, Menlo, monospace;
  }
  .nav-link:hover { background: #21262d; color: var(--accent); }
  main { flex: 1; padding: 1.5rem 2rem 4rem; max-width: 980px; }
  .top-note {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 1rem 1.25rem;
    margin-bottom: 1.5rem;
    font-size: 14px;
    line-height: 1.6;
  }
  .top-note code { background: #21262d; padding: 1px 5px; border-radius: 4px; font-size: 12.5px; }
  .file-section { margin-bottom: 2rem; }
  .file-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: #21262d;
    border: 1px solid var(--border);
    border-bottom: none;
    border-radius: 8px 8px 0 0;
    padding: 8px 14px;
  }
  .file-path {
    font-family: ui-monospace, SFMono-Regular, Menlo, monospace;
    font-size: 13px;
    color: #fff;
  }
  .copy-btn {
    background: transparent;
    border: 1px solid var(--border);
    color: var(--text);
    font-size: 12px;
    padding: 4px 10px;
    border-radius: 5px;
    cursor: pointer;
  }
  .copy-btn:hover { border-color: var(--accent); color: var(--accent); }
  pre {
    margin: 0;
    border: 1px solid var(--border);
    border-radius: 0 0 8px 8px;
    max-height: 480px;
    overflow: auto;
  }
  pre code { font-size: 12.5px; line-height: 1.55; }
  ::-webkit-scrollbar { width: 10px; height: 10px; }
  ::-webkit-scrollbar-thumb { background: #30363d; border-radius: 5px; }
</style>
</head>
<body>
<nav>
  <h1>Momentum <span>Mastered</span></h1>
  <div class="nav-group-label">Config (root)</div><a href="#f--env-example" class="nav-link">.env.example</a><a href="#f--gitignore" class="nav-link">.gitignore</a><a href="#f--prettierignore" class="nav-link">.prettierignore</a><a href="#f--prettierrc" class="nav-link">.prettierrc</a><a href="#f-AGENTS-md" class="nav-link">AGENTS.md</a><a href="#f-README-md" class="nav-link">README.md</a><a href="#f-bunfig-toml" class="nav-link">bunfig.toml</a><a href="#f-components-json" class="nav-link">components.json</a><a href="#f-eslint-config-js" class="nav-link">eslint.config.js</a><a href="#f-package-json" class="nav-link">package.json</a><a href="#f-tsconfig-json" class="nav-link">tsconfig.json</a><a href="#f-vite-config-ts" class="nav-link">vite.config.ts</a><div class="nav-group-label">src/lib</div><a href="#f-src_lib_error-capture-ts" class="nav-link">src/lib/error-capture.ts</a><a href="#f-src_lib_error-page-ts" class="nav-link">src/lib/error-page.ts</a><a href="#f-src_lib_goals-functions-ts" class="nav-link">src/lib/goals.functions.ts</a><a href="#f-src_lib_lovable-error-reporting-ts" class="nav-link">src/lib/lovable-error-reporting.ts</a><a href="#f-src_lib_streak-ts" class="nav-link">src/lib/streak.ts</a><a href="#f-src_lib_utils-ts" class="nav-link">src/lib/utils.ts</a><div class="nav-group-label">src/integrations</div><a href="#f-src_integrations_lovable_index-ts" class="nav-link">src/integrations/lovable/index.ts</a><a href="#f-src_integrations_supabase_auth-attacher-ts" class="nav-link">src/integrations/supabase/auth-attacher.ts</a><a href="#f-src_integrations_supabase_auth-middleware-ts" class="nav-link">src/integrations/supabase/auth-middleware.ts</a><a href="#f-src_integrations_supabase_client-server-ts" class="nav-link">src/integrations/supabase/client.server.ts</a><a href="#f-src_integrations_supabase_client-ts" class="nav-link">src/integrations/supabase/client.ts</a><a href="#f-src_integrations_supabase_types-ts" class="nav-link">src/integrations/supabase/types.ts</a><div class="nav-group-label">src/hooks</div><a href="#f-src_hooks_use-mobile-tsx" class="nav-link">src/hooks/use-mobile.tsx</a><div class="nav-group-label">src/components</div><a href="#f-src_components_app-shell-tsx" class="nav-link">src/components/app-shell.tsx</a><a href="#f-src_components_ui_accordion-tsx" class="nav-link">src/components/ui/accordion.tsx</a><a href="#f-src_components_ui_alert-dialog-tsx" class="nav-link">src/components/ui/alert-dialog.tsx</a><a href="#f-src_components_ui_alert-tsx" class="nav-link">src/components/ui/alert.tsx</a><a href="#f-src_components_ui_aspect-ratio-tsx" class="nav-link">src/components/ui/aspect-ratio.tsx</a><a href="#f-src_components_ui_avatar-tsx" class="nav-link">src/components/ui/avatar.tsx</a><a href="#f-src_components_ui_badge-tsx" class="nav-link">src/components/ui/badge.tsx</a><a href="#f-src_components_ui_breadcrumb-tsx" class="nav-link">src/components/ui/breadcrumb.tsx</a><a href="#f-src_components_ui_button-tsx" class="nav-link">src/components/ui/button.tsx</a><a href="#f-src_components_ui_calendar-tsx" class="nav-link">src/components/ui/calendar.tsx</a><a href="#f-src_components_ui_card-tsx" class="nav-link">src/components/ui/card.tsx</a><a href="#f-src_components_ui_carousel-tsx" class="nav-link">src/components/ui/carousel.tsx</a><a href="#f-src_components_ui_chart-tsx" class="nav-link">src/components/ui/chart.tsx</a><a href="#f-src_components_ui_checkbox-tsx" class="nav-link">src/components/ui/checkbox.tsx</a><a href="#f-src_components_ui_collapsible-tsx" class="nav-link">src/components/ui/collapsible.tsx</a><a href="#f-src_components_ui_command-tsx" class="nav-link">src/components/ui/command.tsx</a><a href="#f-src_components_ui_context-menu-tsx" class="nav-link">src/components/ui/context-menu.tsx</a><a href="#f-src_components_ui_dialog-tsx" class="nav-link">src/components/ui/dialog.tsx</a><a href="#f-src_components_ui_drawer-tsx" class="nav-link">src/components/ui/drawer.tsx</a><a href="#f-src_components_ui_dropdown-menu-tsx" class="nav-link">src/components/ui/dropdown-menu.tsx</a><a href="#f-src_components_ui_form-tsx" class="nav-link">src/components/ui/form.tsx</a><a href="#f-src_components_ui_hover-card-tsx" class="nav-link">src/components/ui/hover-card.tsx</a><a href="#f-src_components_ui_input-otp-tsx" class="nav-link">src/components/ui/input-otp.tsx</a><a href="#f-src_components_ui_input-tsx" class="nav-link">src/components/ui/input.tsx</a><a href="#f-src_components_ui_label-tsx" class="nav-link">src/components/ui/label.tsx</a><a href="#f-src_components_ui_menubar-tsx" class="nav-link">src/components/ui/menubar.tsx</a><a href="#f-src_components_ui_navigation-menu-tsx" class="nav-link">src/components/ui/navigation-menu.tsx</a><a href="#f-src_components_ui_pagination-tsx" class="nav-link">src/components/ui/pagination.tsx</a><a href="#f-src_components_ui_popover-tsx" class="nav-link">src/components/ui/popover.tsx</a><a href="#f-src_components_ui_progress-tsx" class="nav-link">src/components/ui/progress.tsx</a><a href="#f-src_components_ui_radio-group-tsx" class="nav-link">src/components/ui/radio-group.tsx</a><a href="#f-src_components_ui_resizable-tsx" class="nav-link">src/components/ui/resizable.tsx</a><a href="#f-src_components_ui_scroll-area-tsx" class="nav-link">src/components/ui/scroll-area.tsx</a><a href="#f-src_components_ui_select-tsx" class="nav-link">src/components/ui/select.tsx</a><a href="#f-src_components_ui_separator-tsx" class="nav-link">src/components/ui/separator.tsx</a><a href="#f-src_components_ui_sheet-tsx" class="nav-link">src/components/ui/sheet.tsx</a><a href="#f-src_components_ui_sidebar-tsx" class="nav-link">src/components/ui/sidebar.tsx</a><a href="#f-src_components_ui_skeleton-tsx" class="nav-link">src/components/ui/skeleton.tsx</a><a href="#f-src_components_ui_slider-tsx" class="nav-link">src/components/ui/slider.tsx</a><a href="#f-src_components_ui_sonner-tsx" class="nav-link">src/components/ui/sonner.tsx</a><a href="#f-src_components_ui_switch-tsx" class="nav-link">src/components/ui/switch.tsx</a><a href="#f-src_components_ui_table-tsx" class="nav-link">src/components/ui/table.tsx</a><a href="#f-src_components_ui_tabs-tsx" class="nav-link">src/components/ui/tabs.tsx</a><a href="#f-src_components_ui_textarea-tsx" class="nav-link">src/components/ui/textarea.tsx</a><a href="#f-src_components_ui_toggle-group-tsx" class="nav-link">src/components/ui/toggle-group.tsx</a><a href="#f-src_components_ui_toggle-tsx" class="nav-link">src/components/ui/toggle.tsx</a><a href="#f-src_components_ui_tooltip-tsx" class="nav-link">src/components/ui/tooltip.tsx</a><div class="nav-group-label">src/routes</div><a href="#f-src_routes_README-md" class="nav-link">src/routes/README.md</a><a href="#f-src_routes___root-tsx" class="nav-link">src/routes/__root.tsx</a><a href="#f-src_routes__authenticated_dashboard-tsx" class="nav-link">src/routes/_authenticated/dashboard.tsx</a><a href="#f-src_routes__authenticated_goals-Sid-tsx" class="nav-link">src/routes/_authenticated/goals.$id.tsx</a><a href="#f-src_routes__authenticated_goals-new-tsx" class="nav-link">src/routes/_authenticated/goals.new.tsx</a><a href="#f-src_routes__authenticated_route-tsx" class="nav-link">src/routes/_authenticated/route.tsx</a><a href="#f-src_routes_auth-tsx" class="nav-link">src/routes/auth.tsx</a><a href="#f-src_routes_index-tsx" class="nav-link">src/routes/index.tsx</a><div class="nav-group-label">src</div><a href="#f-src_router-tsx" class="nav-link">src/router.tsx</a><a href="#f-src_server-ts" class="nav-link">src/server.ts</a><a href="#f-src_start-ts" class="nav-link">src/start.ts</a><a href="#f-src_styles-css" class="nav-link">src/styles.css</a><div class="nav-group-label">supabase</div><a href="#f-supabase_config-toml" class="nav-link">supabase/config.toml</a><a href="#f-supabase_migrations_20260708110954_3ddd6732-7a30-40d6-9836-5f73d73835c4-sql" class="nav-link">supabase/migrations/20260708110954_3ddd6732-7a30-40d6-9836-5f73d73835c4.sql</a><a href="#f-supabase_migrations_20260708111029_30bcabec-6f38-4948-97a4-ddc34dd7d238-sql" class="nav-link">supabase/migrations/20260708111029_30bcabec-6f38-4948-97a4-ddc34dd7d238.sql</a>
</nav>
<main>
  <div class="top-note">
    Kompletter Custom-Code des Projekts (<code>steady-build-achieve.lovable.app</code>), als eine HTML-Datei zum Durchklicken und Copy-Pasten.
    Standard-shadcn/ui-Komponenten sind inklusive. Nicht enthalten: <code>package-lock.json</code> (regenerierbar via <code>npm install</code>),
    <code>routeTree.gen.ts</code> (auto-generiert von TanStack Router) und <code>.env</code> (Secrets — nutz <code>.env.example</code> als Vorlage).
  </div>
  
<section class="file-section" id="f--env-example">
  <div class="file-header">
    <span class="file-path">.env.example</span>
    <button class="copy-btn" onclick="copyCode('f--env-example', this)">Copy</button>
  </div>
  <pre><code class="language-plaintext" id="code-f--env-example"># Supabase (client-side, Vite build-time)
VITE_SUPABASE_URL=
VITE_SUPABASE_PUBLISHABLE_KEY=

# Supabase (server-side / SSR)
SUPABASE_URL=
SUPABASE_PUBLISHABLE_KEY=
SUPABASE_SERVICE_ROLE_KEY=

# Lovable AI Gateway (used by src/lib/goals.functions.ts)
LOVABLE_API_KEY=
</code></pre>
</section>

<section class="file-section" id="f--gitignore">
  <div class="file-header">
    <span class="file-path">.gitignore</span>
    <button class="copy-btn" onclick="copyCode('f--gitignore', this)">Copy</button>
  </div>
  <pre><code class="language-plaintext" id="code-f--gitignore"># Logs
logs
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pnpm-debug.log*
lerna-debug.log*

node_modules
dist
dist-ssr
.output
.vinxi
.tanstack/**
.nitro
*.local

# Wrangler / Cloudflare
.wrangler/
.dev.vars

# Editor directories and files
.vscode/*
!.vscode/extensions.json
.idea
.DS_Store
*.suo
*.ntvs*
*.njsproj
*.sln
*.sw?

# env
.env
</code></pre>
</section>

<section class="file-section" id="f--prettierignore">
  <div class="file-header">
    <span class="file-path">.prettierignore</span>
    <button class="copy-btn" onclick="copyCode('f--prettierignore', this)">Copy</button>
  </div>
  <pre><code class="language-plaintext" id="code-f--prettierignore">node_modules
dist
.output
.vinxi
pnpm-lock.yaml
package-lock.json
bun.lock
routeTree.gen.ts
</code></pre>
</section>

<section class="file-section" id="f--prettierrc">
  <div class="file-header">
    <span class="file-path">.prettierrc</span>
    <button class="copy-btn" onclick="copyCode('f--prettierrc', this)">Copy</button>
  </div>
  <pre><code class="language-plaintext" id="code-f--prettierrc">{
  &quot;printWidth&quot;: 100,
  &quot;semi&quot;: true,
  &quot;singleQuote&quot;: false,
  &quot;trailingComma&quot;: &quot;all&quot;
}
</code></pre>
</section>

<section class="file-section" id="f-AGENTS-md">
  <div class="file-header">
    <span class="file-path">AGENTS.md</span>
    <button class="copy-btn" onclick="copyCode('f-AGENTS-md', this)">Copy</button>
  </div>
  <pre><code class="language-markdown" id="code-f-AGENTS-md">&lt;!-- LOVABLE:BEGIN --&gt;
&gt; [!IMPORTANT]
&gt; This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
&gt; published git history — force pushing, or rebasing/amending/squashing commits
&gt; that are already pushed — as it rewrites history on Lovable&#x27;s side and the
&gt; user will likely lose their project history.
&gt;
&gt; Commits you push to the connected branch sync back to Lovable and show up in
&gt; the editor, so keep the branch in a working state.
&lt;!-- LOVABLE:END --&gt;
</code></pre>
</section>

<section class="file-section" id="f-README-md">
  <div class="file-header">
    <span class="file-path">README.md</span>
    <button class="copy-btn" onclick="copyCode('f-README-md', this)">Copy</button>
  </div>
  <pre><code class="language-markdown" id="code-f-README-md"># Momentum Mastered

SMART-Goal-Kalibrierung, automatisches Task-Breakdown und Habit-Tracker mit Streak-System.
Gebaut mit TanStack Start (React), Supabase, Tailwind + shadcn/ui.

Live-Vorschau (Lovable): https://steady-build-achieve.lovable.app

## Setup

```bash
npm install
cp .env.example .env   # Werte aus Lovable Cloud / Supabase eintragen
npm run dev
```

`.env` ist in `.gitignore` — die echten Keys wurden **nicht** mit exportiert.
Trag sie lokal ein bzw. als Secrets in deinem Hosting (Vercel/Cloudflare/etc.) ein.

## Nach `git clone` einmalig

`src/routeTree.gen.ts` ist auto-generiert (TanStack Router) und wurde bewusst
nicht mit exportiert. Beim ersten `npm run dev` oder `npm run build` wird sie
automatisch neu erzeugt.

## GitHub veröffentlichen

```bash
cd momentum-mastered
git init
git add .
git commit -m &quot;Initial commit&quot;
git branch -M main
git remote add origin https://github.com/&lt;dein-user&gt;/&lt;repo-name&gt;.git
git push -u origin main
```

## Struktur

- `src/routes/` — TanStack Start File-Based Routing (Landing, Auth, Dashboard, Goal-Detail, New-Goal)
- `src/lib/goals.functions.ts` — Server-Functions: SMART-Kalibrierung + Task-Breakdown via Lovable AI Gateway
- `src/lib/streak.ts` — Streak-Berechnung (Zwei-Tage-Regel + Freezes)
- `src/integrations/supabase/` — Supabase-Client (Browser + Server + Auth-Middleware)
- `supabase/migrations/` — Tabellen: `goals`, `tasks`, `daily_actions`, `action_completions`, `streak_freezes`, `profiles`
</code></pre>
</section>

<section class="file-section" id="f-bunfig-toml">
  <div class="file-header">
    <span class="file-path">bunfig.toml</span>
    <button class="copy-btn" onclick="copyCode('f-bunfig-toml', this)">Copy</button>
  </div>
  <pre><code class="language-toml" id="code-f-bunfig-toml">[install]
# 24h supply-chain guard: skip package versions published less than a day ago.
minimumReleaseAge = 86400
# Each entry bypasses the 24h guard for one package — confirm with the user
# before adding any.
minimumReleaseAgeExcludes = [&quot;@lovable.dev/vite-tanstack-config&quot;, &quot;@lovable.dev/mcp-js&quot;, &quot;@lovable.dev/vite-plugin-dev-server-bridge&quot;, &quot;@lovable.dev/vite-plugin-hmr-gate&quot;]
</code></pre>
</section>

<section class="file-section" id="f-components-json">
  <div class="file-header">
    <span class="file-path">components.json</span>
    <button class="copy-btn" onclick="copyCode('f-components-json', this)">Copy</button>
  </div>
  <pre><code class="language-json" id="code-f-components-json">{
  &quot;$schema&quot;: &quot;https://ui.shadcn.com/schema.json&quot;,
  &quot;style&quot;: &quot;new-york&quot;,
  &quot;rsc&quot;: false,
  &quot;tsx&quot;: true,
  &quot;tailwind&quot;: {
    &quot;css&quot;: &quot;src/styles.css&quot;,
    &quot;baseColor&quot;: &quot;slate&quot;,
    &quot;cssVariables&quot;: true,
    &quot;prefix&quot;: &quot;&quot;
  },
  &quot;iconLibrary&quot;: &quot;lucide&quot;,
  &quot;rtl&quot;: false,
  &quot;aliases&quot;: {
    &quot;components&quot;: &quot;@/components&quot;,
    &quot;utils&quot;: &quot;@/lib/utils&quot;,
    &quot;ui&quot;: &quot;@/components/ui&quot;,
    &quot;lib&quot;: &quot;@/lib&quot;,
    &quot;hooks&quot;: &quot;@/hooks&quot;
  },
  &quot;registries&quot;: {}
}
</code></pre>
</section>

<section class="file-section" id="f-eslint-config-js">
  <div class="file-header">
    <span class="file-path">eslint.config.js</span>
    <button class="copy-btn" onclick="copyCode('f-eslint-config-js', this)">Copy</button>
  </div>
  <pre><code class="language-javascript" id="code-f-eslint-config-js">import js from &quot;@eslint/js&quot;;
import eslintPluginPrettier from &quot;eslint-plugin-prettier/recommended&quot;;
import globals from &quot;globals&quot;;
import reactHooks from &quot;eslint-plugin-react-hooks&quot;;
import reactRefresh from &quot;eslint-plugin-react-refresh&quot;;
import tseslint from &quot;typescript-eslint&quot;;

export default tseslint.config(
  { ignores: [&quot;dist&quot;, &quot;.output&quot;, &quot;.vinxi&quot;] },
  {
    extends: [js.configs.recommended, ...tseslint.configs.recommended],
    files: [&quot;**/*.{ts,tsx}&quot;],
    languageOptions: {
      ecmaVersion: 2020,
      globals: globals.browser,
    },
    plugins: {
      &quot;react-hooks&quot;: reactHooks,
      &quot;react-refresh&quot;: reactRefresh,
    },
    rules: {
      ...reactHooks.configs.recommended.rules,
      &quot;no-restricted-imports&quot;: [
        &quot;error&quot;,
        {
          paths: [
            {
              name: &quot;server-only&quot;,
              message:
                &quot;TanStack Start does not use the Next.js `server-only` package. Rename the module to `*.server.ts` or mark it with `@tanstack/react-start/server-only`.&quot;,
            },
          ],
        },
      ],
      &quot;react-refresh/only-export-components&quot;: [&quot;warn&quot;, { allowConstantExport: true }],
      &quot;@typescript-eslint/no-unused-vars&quot;: &quot;off&quot;,
    },
  },
  eslintPluginPrettier,
);
</code></pre>
</section>

<section class="file-section" id="f-package-json">
  <div class="file-header">
    <span class="file-path">package.json</span>
    <button class="copy-btn" onclick="copyCode('f-package-json', this)">Copy</button>
  </div>
  <pre><code class="language-json" id="code-f-package-json">{
  &quot;name&quot;: &quot;tanstack_start_ts&quot;,
  &quot;private&quot;: true,
  &quot;sideEffects&quot;: false,
  &quot;type&quot;: &quot;module&quot;,
  &quot;scripts&quot;: {
    &quot;dev&quot;: &quot;vite dev&quot;,
    &quot;build&quot;: &quot;vite build&quot;,
    &quot;build:dev&quot;: &quot;vite build --mode development&quot;,
    &quot;preview&quot;: &quot;vite preview&quot;,
    &quot;lint&quot;: &quot;eslint .&quot;,
    &quot;format&quot;: &quot;prettier --write .&quot;
  },
  &quot;dependencies&quot;: {
    &quot;@hookform/resolvers&quot;: &quot;^5.2.2&quot;,
    &quot;@lovable.dev/cloud-auth-js&quot;: &quot;^1.1.2&quot;,
    &quot;@radix-ui/react-accordion&quot;: &quot;^1.2.12&quot;,
    &quot;@radix-ui/react-alert-dialog&quot;: &quot;^1.1.15&quot;,
    &quot;@radix-ui/react-aspect-ratio&quot;: &quot;^1.1.8&quot;,
    &quot;@radix-ui/react-avatar&quot;: &quot;^1.1.11&quot;,
    &quot;@radix-ui/react-checkbox&quot;: &quot;^1.3.3&quot;,
    &quot;@radix-ui/react-collapsible&quot;: &quot;^1.1.12&quot;,
    &quot;@radix-ui/react-context-menu&quot;: &quot;^2.2.16&quot;,
    &quot;@radix-ui/react-dialog&quot;: &quot;^1.1.15&quot;,
    &quot;@radix-ui/react-dropdown-menu&quot;: &quot;^2.1.16&quot;,
    &quot;@radix-ui/react-hover-card&quot;: &quot;^1.1.15&quot;,
    &quot;@radix-ui/react-label&quot;: &quot;^2.1.8&quot;,
    &quot;@radix-ui/react-menubar&quot;: &quot;^1.1.16&quot;,
    &quot;@radix-ui/react-navigation-menu&quot;: &quot;^1.2.14&quot;,
    &quot;@radix-ui/react-popover&quot;: &quot;^1.1.15&quot;,
    &quot;@radix-ui/react-progress&quot;: &quot;^1.1.8&quot;,
    &quot;@radix-ui/react-radio-group&quot;: &quot;^1.3.8&quot;,
    &quot;@radix-ui/react-scroll-area&quot;: &quot;^1.2.10&quot;,
    &quot;@radix-ui/react-select&quot;: &quot;^2.2.6&quot;,
    &quot;@radix-ui/react-separator&quot;: &quot;^1.1.8&quot;,
    &quot;@radix-ui/react-slider&quot;: &quot;^1.3.6&quot;,
    &quot;@radix-ui/react-slot&quot;: &quot;^1.2.4&quot;,
    &quot;@radix-ui/react-switch&quot;: &quot;^1.2.6&quot;,
    &quot;@radix-ui/react-tabs&quot;: &quot;^1.1.13&quot;,
    &quot;@radix-ui/react-toggle&quot;: &quot;^1.1.10&quot;,
    &quot;@radix-ui/react-toggle-group&quot;: &quot;^1.1.11&quot;,
    &quot;@radix-ui/react-tooltip&quot;: &quot;^1.2.8&quot;,
    &quot;@supabase/supabase-js&quot;: &quot;^2.110.0&quot;,
    &quot;@tailwindcss/vite&quot;: &quot;^4.2.1&quot;,
    &quot;@tanstack/react-query&quot;: &quot;^5.101.1&quot;,
    &quot;@tanstack/react-router&quot;: &quot;^1.170.16&quot;,
    &quot;@tanstack/react-start&quot;: &quot;^1.168.26&quot;,
    &quot;@tanstack/router-plugin&quot;: &quot;^1.168.18&quot;,
    &quot;class-variance-authority&quot;: &quot;^0.7.1&quot;,
    &quot;clsx&quot;: &quot;^2.1.1&quot;,
    &quot;cmdk&quot;: &quot;^1.1.1&quot;,
    &quot;date-fns&quot;: &quot;^4.1.0&quot;,
    &quot;embla-carousel-react&quot;: &quot;^8.6.0&quot;,
    &quot;input-otp&quot;: &quot;^1.4.2&quot;,
    &quot;lucide-react&quot;: &quot;^0.575.0&quot;,
    &quot;next-themes&quot;: &quot;^0.4.6&quot;,
    &quot;react&quot;: &quot;^19.2.0&quot;,
    &quot;react-day-picker&quot;: &quot;^10.0.1&quot;,
    &quot;react-dom&quot;: &quot;^19.2.0&quot;,
    &quot;react-hook-form&quot;: &quot;^7.71.2&quot;,
    &quot;react-resizable-panels&quot;: &quot;^4.6.5&quot;,
    &quot;recharts&quot;: &quot;^2.15.4&quot;,
    &quot;sonner&quot;: &quot;^2.0.7&quot;,
    &quot;tailwind-merge&quot;: &quot;^3.5.0&quot;,
    &quot;tailwindcss&quot;: &quot;^4.2.1&quot;,
    &quot;tw-animate-css&quot;: &quot;^1.3.4&quot;,
    &quot;vaul&quot;: &quot;^1.1.2&quot;,
    &quot;vite-tsconfig-paths&quot;: &quot;^6.0.2&quot;,
    &quot;zod&quot;: &quot;^3.24.2&quot;
  },
  &quot;devDependencies&quot;: {
    &quot;@eslint/js&quot;: &quot;^9.32.0&quot;,
    &quot;@lovable.dev/vite-tanstack-config&quot;: &quot;^2.7.1&quot;,
    &quot;@types/node&quot;: &quot;^22.16.5&quot;,
    &quot;@types/react&quot;: &quot;^19.2.0&quot;,
    &quot;@types/react-dom&quot;: &quot;^19.2.0&quot;,
    &quot;@vitejs/plugin-react&quot;: &quot;^5.2.0&quot;,
    &quot;eslint&quot;: &quot;^9.32.0&quot;,
    &quot;eslint-config-prettier&quot;: &quot;^10.1.1&quot;,
    &quot;eslint-plugin-prettier&quot;: &quot;^5.2.6&quot;,
    &quot;eslint-plugin-react-hooks&quot;: &quot;^5.2.0&quot;,
    &quot;eslint-plugin-react-refresh&quot;: &quot;^0.4.20&quot;,
    &quot;globals&quot;: &quot;^15.15.0&quot;,
    &quot;nitro&quot;: &quot;3.0.260603-beta&quot;,
    &quot;prettier&quot;: &quot;^3.7.3&quot;,
    &quot;typescript&quot;: &quot;^5.8.3&quot;,
    &quot;typescript-eslint&quot;: &quot;^8.56.1&quot;,
    &quot;vite&quot;: &quot;^8.0.16&quot;
  }
}
</code></pre>
</section>

<section class="file-section" id="f-tsconfig-json">
  <div class="file-header">
    <span class="file-path">tsconfig.json</span>
    <button class="copy-btn" onclick="copyCode('f-tsconfig-json', this)">Copy</button>
  </div>
  <pre><code class="language-json" id="code-f-tsconfig-json">{
  &quot;include&quot;: [&quot;src/**/*.ts&quot;, &quot;src/**/*.tsx&quot;, &quot;vite.config.ts&quot;, &quot;eslint.config.js&quot;],
  &quot;compilerOptions&quot;: {
    &quot;target&quot;: &quot;ES2022&quot;,
    &quot;jsx&quot;: &quot;react-jsx&quot;,
    &quot;module&quot;: &quot;ESNext&quot;,
    &quot;lib&quot;: [&quot;ES2022&quot;, &quot;DOM&quot;, &quot;DOM.Iterable&quot;],
    &quot;types&quot;: [&quot;vite/client&quot;],

    /* Bundler mode */
    &quot;moduleResolution&quot;: &quot;Bundler&quot;,
    &quot;allowImportingTsExtensions&quot;: true,
    &quot;verbatimModuleSyntax&quot;: false,
    &quot;noEmit&quot;: true,

    /* Linting */
    &quot;skipLibCheck&quot;: true,
    &quot;strict&quot;: true,
    &quot;noUnusedLocals&quot;: false,
    &quot;noUnusedParameters&quot;: false,
    &quot;noFallthroughCasesInSwitch&quot;: true,
    &quot;noUncheckedSideEffectImports&quot;: true,
    &quot;paths&quot;: {
      &quot;@/*&quot;: [&quot;./src/*&quot;]
    }
  }
}
</code></pre>
</section>

<section class="file-section" id="f-vite-config-ts">
  <div class="file-header">
    <span class="file-path">vite.config.ts</span>
    <button class="copy-btn" onclick="copyCode('f-vite-config-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-vite-config-ts">// @lovable.dev/vite-tanstack-config already includes the following — do NOT add them manually
// or the app will break with duplicate plugins:
//   - tanstackStart, viteReact, tailwindcss, tsConfigPaths, nitro (build-only using cloudflare as a default target),
//     componentTagger (dev-only), VITE_* env injection, @ path alias, React/TanStack dedupe,
//     error logger plugins, and sandbox detection (port/host/strictPort).
// You can pass additional config via defineConfig({ vite: { ... }, etc... }) if needed.
import { defineConfig } from &quot;@lovable.dev/vite-tanstack-config&quot;;

export default defineConfig({
  tanstackStart: {
    // Redirect TanStack Start&#x27;s bundled server entry to src/server.ts (our SSR error wrapper).
    // nitro/vite builds from this
    server: { entry: &quot;server&quot; },
  },
});
</code></pre>
</section>

<section class="file-section" id="f-src_hooks_use-mobile-tsx">
  <div class="file-header">
    <span class="file-path">src/hooks/use-mobile.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_hooks_use-mobile-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_hooks_use-mobile-tsx">import * as React from &quot;react&quot;

const MOBILE_BREAKPOINT = 768

export function useIsMobile() {
  const [isMobile, setIsMobile] = React.useState&lt;boolean | undefined&gt;(undefined)

  React.useEffect(() =&gt; {
    const mql = window.matchMedia(`(max-width: ${MOBILE_BREAKPOINT - 1}px)`)
    const onChange = () =&gt; {
      setIsMobile(window.innerWidth &lt; MOBILE_BREAKPOINT)
    }
    mql.addEventListener(&quot;change&quot;, onChange)
    setIsMobile(window.innerWidth &lt; MOBILE_BREAKPOINT)
    return () =&gt; mql.removeEventListener(&quot;change&quot;, onChange)
  }, [])

  return !!isMobile
}
</code></pre>
</section>

<section class="file-section" id="f-src_integrations_lovable_index-ts">
  <div class="file-header">
    <span class="file-path">src/integrations/lovable/index.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_integrations_lovable_index-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_integrations_lovable_index-ts">// This file is auto-generated by Lovable. Do not modify it.

import { createLovableAuth } from &quot;@lovable.dev/cloud-auth-js&quot;;
import { supabase } from &quot;../supabase/client&quot;;
const lovableAuth = createLovableAuth();

type SignInOptions = {
  redirect_uri?: string;
  extraParams?: Record&lt;string, string&gt;;
};

export const lovable = {
  auth: {
    signInWithOAuth: async (provider: &quot;google&quot; | &quot;apple&quot; | &quot;microsoft&quot; | &quot;lovable&quot;, opts?: SignInOptions) =&gt; {
      const result = await lovableAuth.signInWithOAuth(provider, {
        redirect_uri: opts?.redirect_uri,
        extraParams: {
          ...opts?.extraParams,
        },
      });

      if (result.redirected) {
        return result;
      }

      if (result.error) {
        return result;
      }

      try {
        await supabase.auth.setSession(result.tokens);
      } catch (e) {
        return { error: e instanceof Error ? e : new Error(String(e)) };
      }
      return result;
    },
  },
};
</code></pre>
</section>

<section class="file-section" id="f-src_integrations_supabase_auth-attacher-ts">
  <div class="file-header">
    <span class="file-path">src/integrations/supabase/auth-attacher.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_integrations_supabase_auth-attacher-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_integrations_supabase_auth-attacher-ts">// This file is automatically generated. Do not edit it directly.
import { createMiddleware } from &#x27;@tanstack/react-start&#x27;
import { supabase } from &#x27;./client&#x27;

// Must be registered as a global `functionMiddleware` in `src/start.ts`; otherwise
// the browser never attaches the bearer token to serverFn RPCs.
export const attachSupabaseAuth = createMiddleware({ type: &#x27;function&#x27; }).client(
  async ({ next }) =&gt; {
    const { data } = await supabase.auth.getSession()
    const token = data.session?.access_token
    return next({
      headers: token ? { Authorization: `Bearer ${token}` } : {},
    })
  },
)
</code></pre>
</section>

<section class="file-section" id="f-src_integrations_supabase_auth-middleware-ts">
  <div class="file-header">
    <span class="file-path">src/integrations/supabase/auth-middleware.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_integrations_supabase_auth-middleware-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_integrations_supabase_auth-middleware-ts">// This file is automatically generated. Do not edit it directly.
import { createMiddleware } from &#x27;@tanstack/react-start&#x27;
import { getRequest } from &#x27;@tanstack/react-start/server&#x27;
import { createClient } from &#x27;@supabase/supabase-js&#x27;
import type { Database } from &#x27;./types&#x27;



function isNewSupabaseApiKey(value: string): boolean {
  return value.startsWith(&#x27;sb_publishable_&#x27;) || value.startsWith(&#x27;sb_secret_&#x27;);
}

function createSupabaseFetch(supabaseKey: string): typeof fetch {
  return (input, init) =&gt; {
    const headers = new Headers(
      typeof Request !== &#x27;undefined&#x27; &amp;&amp; input instanceof Request ? input.headers : undefined,
    );

    if (init?.headers) {
      new Headers(init.headers).forEach((value, key) =&gt; headers.set(key, value));
    }

    // New Supabase API keys are opaque strings, not bearer JWTs.
    if (isNewSupabaseApiKey(supabaseKey) &amp;&amp; headers.get(&#x27;Authorization&#x27;) === `Bearer ${supabaseKey}`) {
      headers.delete(&#x27;Authorization&#x27;);
    }

    headers.set(&#x27;apikey&#x27;, supabaseKey);
    return fetch(input, { ...init, headers });
  };
}

export const requireSupabaseAuth = createMiddleware({ type: &#x27;function&#x27; }).server(
  async ({ next }) =&gt; {
    
    const SUPABASE_URL = process.env.SUPABASE_URL;
    const SUPABASE_PUBLISHABLE_KEY = process.env.SUPABASE_PUBLISHABLE_KEY;

    if (!SUPABASE_URL || !SUPABASE_PUBLISHABLE_KEY) {
      const missing = [
        ...(!SUPABASE_URL ? [&#x27;SUPABASE_URL&#x27;] : []),
        ...(!SUPABASE_PUBLISHABLE_KEY ? [&#x27;SUPABASE_PUBLISHABLE_KEY&#x27;] : []),
      ];
      const message = `Missing Supabase environment variable(s): ${missing.join(&#x27;, &#x27;)}. Connect Supabase in Lovable Cloud.`;
      console.error(`[Supabase] ${message}`);
      throw new Error(message);
    }
    
    const request = getRequest();

    if (!request?.headers) {
      throw new Error(&#x27;Unauthorized: No request headers available&#x27;);
    }

    const authHeader = request.headers.get(&#x27;authorization&#x27;);

    if (!authHeader) {
      throw new Error(&#x27;Unauthorized: No authorization header provided&#x27;);
    }

    if (!authHeader.startsWith(&#x27;Bearer &#x27;)) {
      throw new Error(&#x27;Unauthorized: Only Bearer tokens are supported&#x27;);
    }

    const token = authHeader.replace(&#x27;Bearer &#x27;, &#x27;&#x27;);
    if (!token) {
      throw new Error(&#x27;Unauthorized: No token provided&#x27;);
    }

    if (token.split(&#x27;.&#x27;).length !== 3) {
      throw new Error(&#x27;Unauthorized: Invalid token&#x27;);
    }

    const supabase = createClient&lt;Database&gt;(
      SUPABASE_URL!,
      SUPABASE_PUBLISHABLE_KEY!,
      {
        global: {
          fetch: createSupabaseFetch(SUPABASE_PUBLISHABLE_KEY!),
          headers: {
            Authorization: `Bearer ${token}`,
          },
        },
        auth: {
          storage: undefined,
          persistSession: false,
          autoRefreshToken: false,
        },
      }
    );

    const { data, error } = await supabase.auth.getClaims(token);
    if (error || !data?.claims) {
      throw new Error(&#x27;Unauthorized: Invalid token&#x27;);
    }

    if (!data.claims.sub) {
      throw new Error(&#x27;Unauthorized: No user ID found in token&#x27;);
    }

    return next({
      context: {
        supabase,
        userId: data.claims.sub,
        claims: data.claims,
      },
    });
  },
);
</code></pre>
</section>

<section class="file-section" id="f-src_integrations_supabase_client-server-ts">
  <div class="file-header">
    <span class="file-path">src/integrations/supabase/client.server.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_integrations_supabase_client-server-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_integrations_supabase_client-server-ts">// This file is automatically generated. Do not edit it directly.
// Server-side Supabase client with service role key - bypasses RLS.
// Use this for admin operations in server functions and server routes only.
// For user-authenticated queries (with RLS), use the auth middleware instead.
import { createClient } from &#x27;@supabase/supabase-js&#x27;;
import type { Database } from &#x27;./types&#x27;;

function isNewSupabaseApiKey(value: string): boolean {
  return value.startsWith(&#x27;sb_publishable_&#x27;) || value.startsWith(&#x27;sb_secret_&#x27;);
}

function createSupabaseFetch(supabaseKey: string): typeof fetch {
  return (input, init) =&gt; {
    const headers = new Headers(
      typeof Request !== &#x27;undefined&#x27; &amp;&amp; input instanceof Request ? input.headers : undefined,
    );

    if (init?.headers) {
      new Headers(init.headers).forEach((value, key) =&gt; headers.set(key, value));
    }

    // New Supabase API keys are opaque strings, not bearer JWTs.
    if (isNewSupabaseApiKey(supabaseKey) &amp;&amp; headers.get(&#x27;Authorization&#x27;) === `Bearer ${supabaseKey}`) {
      headers.delete(&#x27;Authorization&#x27;);
    }

    headers.set(&#x27;apikey&#x27;, supabaseKey);
    return fetch(input, { ...init, headers });
  };
}

function createSupabaseAdminClient() {
  const SUPABASE_URL = process.env.SUPABASE_URL;
  const SUPABASE_SERVICE_ROLE_KEY = process.env.SUPABASE_SERVICE_ROLE_KEY;

  if (!SUPABASE_URL || !SUPABASE_SERVICE_ROLE_KEY) {
    const missing = [
      ...(!SUPABASE_URL ? [&#x27;SUPABASE_URL&#x27;] : []),
      ...(!SUPABASE_SERVICE_ROLE_KEY ? [&#x27;SUPABASE_SERVICE_ROLE_KEY&#x27;] : []),
    ];
    const message = `Missing Supabase environment variable(s): ${missing.join(&#x27;, &#x27;)}. Connect Supabase in Lovable Cloud.`;
    console.error(`[Supabase] ${message}`);
    throw new Error(message);
  }

  return createClient&lt;Database&gt;(SUPABASE_URL, SUPABASE_SERVICE_ROLE_KEY, {
    global: {
      fetch: createSupabaseFetch(SUPABASE_SERVICE_ROLE_KEY),
    },
    auth: {
      storage: undefined,
      persistSession: false,
      autoRefreshToken: false,
    }
  });
}

let _supabaseAdmin: ReturnType&lt;typeof createSupabaseAdminClient&gt; | undefined;

// Server-side Supabase client with service role - bypasses RLS
// SECURITY: Only use this for trusted server-side operations, never expose to client code
// Load inside server handlers: const { supabaseAdmin } = await import(&quot;@/integrations/supabase/client.server&quot;);
// Top-level import is safe only in other .server.ts modules - route files and *.functions.ts ship to the client bundle.
export const supabaseAdmin = new Proxy({} as ReturnType&lt;typeof createSupabaseAdminClient&gt;, {
  get(_, prop, receiver) {
    if (!_supabaseAdmin) _supabaseAdmin = createSupabaseAdminClient();
    return Reflect.get(_supabaseAdmin, prop, receiver);
  },
});
</code></pre>
</section>

<section class="file-section" id="f-src_integrations_supabase_client-ts">
  <div class="file-header">
    <span class="file-path">src/integrations/supabase/client.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_integrations_supabase_client-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_integrations_supabase_client-ts">// This file is automatically generated. Do not edit it directly.
import { createClient } from &#x27;@supabase/supabase-js&#x27;;
import type { Database } from &#x27;./types&#x27;;

function isNewSupabaseApiKey(value: string): boolean {
  return value.startsWith(&#x27;sb_publishable_&#x27;) || value.startsWith(&#x27;sb_secret_&#x27;);
}

function createSupabaseFetch(supabaseKey: string): typeof fetch {
  return (input, init) =&gt; {
    const headers = new Headers(
      typeof Request !== &#x27;undefined&#x27; &amp;&amp; input instanceof Request ? input.headers : undefined,
    );

    if (init?.headers) {
      new Headers(init.headers).forEach((value, key) =&gt; headers.set(key, value));
    }

    // New Supabase API keys are opaque strings, not bearer JWTs.
    if (isNewSupabaseApiKey(supabaseKey) &amp;&amp; headers.get(&#x27;Authorization&#x27;) === `Bearer ${supabaseKey}`) {
      headers.delete(&#x27;Authorization&#x27;);
    }

    headers.set(&#x27;apikey&#x27;, supabaseKey);
    return fetch(input, { ...init, headers });
  };
}


function createSupabaseClient() {
  // Use import.meta.env for client-side (Vite build-time replacement)
  // Fall back to process.env for SSR (server-side rendering)
  const SUPABASE_URL = import.meta.env.VITE_SUPABASE_URL || process.env.SUPABASE_URL;
  const SUPABASE_PUBLISHABLE_KEY = import.meta.env.VITE_SUPABASE_PUBLISHABLE_KEY || process.env.SUPABASE_PUBLISHABLE_KEY;

  if (!SUPABASE_URL || !SUPABASE_PUBLISHABLE_KEY) {
    const missing = [
      ...(!SUPABASE_URL ? [&#x27;SUPABASE_URL&#x27;] : []),
      ...(!SUPABASE_PUBLISHABLE_KEY ? [&#x27;SUPABASE_PUBLISHABLE_KEY&#x27;] : []),
    ];
    const message = `Missing Supabase environment variable(s): ${missing.join(&#x27;, &#x27;)}. Connect Supabase in Lovable Cloud.`;
    console.error(`[Supabase] ${message}`);
    throw new Error(message);
  }

  return createClient&lt;Database&gt;(SUPABASE_URL, SUPABASE_PUBLISHABLE_KEY, {
    global: {
      fetch: createSupabaseFetch(SUPABASE_PUBLISHABLE_KEY),
    },
    auth: {
      storage: typeof window !== &#x27;undefined&#x27; ? localStorage : undefined,
      persistSession: true,
      autoRefreshToken: true,
    }
  });
}

let _supabase: ReturnType&lt;typeof createSupabaseClient&gt; | undefined;

// Import the supabase client like this:
// import { supabase } from &quot;@/integrations/supabase/client&quot;;
export const supabase = new Proxy({} as ReturnType&lt;typeof createSupabaseClient&gt;, {
  get(_, prop, receiver) {
    if (!_supabase) _supabase = createSupabaseClient();
    return Reflect.get(_supabase, prop, receiver);
  },
});
</code></pre>
</section>

<section class="file-section" id="f-src_integrations_supabase_types-ts">
  <div class="file-header">
    <span class="file-path">src/integrations/supabase/types.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_integrations_supabase_types-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_integrations_supabase_types-ts">export type Json =
  | string
  | number
  | boolean
  | null
  | { [key: string]: Json | undefined }
  | Json[]

export type Database = {
  // Allows to automatically instantiate createClient with right options
  // instead of createClient&lt;Database, { PostgrestVersion: &#x27;XX&#x27; }&gt;(URL, KEY)
  __InternalSupabase: {
    PostgrestVersion: &quot;14.5&quot;
  }
  public: {
    Tables: {
      action_completions: {
        Row: {
          completed_date: string
          created_at: string
          daily_action_id: string
          id: string
          user_id: string
        }
        Insert: {
          completed_date: string
          created_at?: string
          daily_action_id: string
          id?: string
          user_id: string
        }
        Update: {
          completed_date?: string
          created_at?: string
          daily_action_id?: string
          id?: string
          user_id?: string
        }
        Relationships: [
          {
            foreignKeyName: &quot;action_completions_daily_action_id_fkey&quot;
            columns: [&quot;daily_action_id&quot;]
            isOneToOne: false
            referencedRelation: &quot;daily_actions&quot;
            referencedColumns: [&quot;id&quot;]
          },
        ]
      }
      daily_actions: {
        Row: {
          active: boolean
          created_at: string
          description: string | null
          goal_id: string
          id: string
          title: string
          user_id: string
        }
        Insert: {
          active?: boolean
          created_at?: string
          description?: string | null
          goal_id: string
          id?: string
          title: string
          user_id: string
        }
        Update: {
          active?: boolean
          created_at?: string
          description?: string | null
          goal_id?: string
          id?: string
          title?: string
          user_id?: string
        }
        Relationships: [
          {
            foreignKeyName: &quot;daily_actions_goal_id_fkey&quot;
            columns: [&quot;goal_id&quot;]
            isOneToOne: false
            referencedRelation: &quot;goals&quot;
            referencedColumns: [&quot;id&quot;]
          },
        ]
      }
      goals: {
        Row: {
          baseline: string | null
          calibrated_deadline: string | null
          calibrated_metric: string | null
          calibrated_target: string | null
          calibration_explanation: string | null
          calibration_status: string
          created_at: string
          description: string | null
          difficulty_tier: string | null
          id: string
          obstacles: string | null
          status: string
          target_date: string | null
          title: string
          updated_at: string
          user_id: string
          what_if_not: string | null
          why_motivation: string | null
        }
        Insert: {
          baseline?: string | null
          calibrated_deadline?: string | null
          calibrated_metric?: string | null
          calibrated_target?: string | null
          calibration_explanation?: string | null
          calibration_status?: string
          created_at?: string
          description?: string | null
          difficulty_tier?: string | null
          id?: string
          obstacles?: string | null
          status?: string
          target_date?: string | null
          title: string
          updated_at?: string
          user_id: string
          what_if_not?: string | null
          why_motivation?: string | null
        }
        Update: {
          baseline?: string | null
          calibrated_deadline?: string | null
          calibrated_metric?: string | null
          calibrated_target?: string | null
          calibration_explanation?: string | null
          calibration_status?: string
          created_at?: string
          description?: string | null
          difficulty_tier?: string | null
          id?: string
          obstacles?: string | null
          status?: string
          target_date?: string | null
          title?: string
          updated_at?: string
          user_id?: string
          what_if_not?: string | null
          why_motivation?: string | null
        }
        Relationships: []
      }
      profiles: {
        Row: {
          created_at: string
          display_name: string | null
          freeze_credits: number
          id: string
          last_freeze_reset: string
          updated_at: string
        }
        Insert: {
          created_at?: string
          display_name?: string | null
          freeze_credits?: number
          id: string
          last_freeze_reset?: string
          updated_at?: string
        }
        Update: {
          created_at?: string
          display_name?: string | null
          freeze_credits?: number
          id?: string
          last_freeze_reset?: string
          updated_at?: string
        }
        Relationships: []
      }
      streak_freezes: {
        Row: {
          applied_at: string
          freeze_date: string
          goal_id: string | null
          id: string
          user_id: string
        }
        Insert: {
          applied_at?: string
          freeze_date: string
          goal_id?: string | null
          id?: string
          user_id: string
        }
        Update: {
          applied_at?: string
          freeze_date?: string
          goal_id?: string | null
          id?: string
          user_id?: string
        }
        Relationships: [
          {
            foreignKeyName: &quot;streak_freezes_goal_id_fkey&quot;
            columns: [&quot;goal_id&quot;]
            isOneToOne: false
            referencedRelation: &quot;goals&quot;
            referencedColumns: [&quot;id&quot;]
          },
        ]
      }
      tasks: {
        Row: {
          completed: boolean
          completed_at: string | null
          created_at: string
          description: string | null
          estimated_hours: number | null
          goal_id: string
          id: string
          if_then_plans: Json | null
          sprint_order: number
          title: string
          user_id: string
          week_number: number
        }
        Insert: {
          completed?: boolean
          completed_at?: string | null
          created_at?: string
          description?: string | null
          estimated_hours?: number | null
          goal_id: string
          id?: string
          if_then_plans?: Json | null
          sprint_order?: number
          title: string
          user_id: string
          week_number?: number
        }
        Update: {
          completed?: boolean
          completed_at?: string | null
          created_at?: string
          description?: string | null
          estimated_hours?: number | null
          goal_id?: string
          id?: string
          if_then_plans?: Json | null
          sprint_order?: number
          title?: string
          user_id?: string
          week_number?: number
        }
        Relationships: [
          {
            foreignKeyName: &quot;tasks_goal_id_fkey&quot;
            columns: [&quot;goal_id&quot;]
            isOneToOne: false
            referencedRelation: &quot;goals&quot;
            referencedColumns: [&quot;id&quot;]
          },
        ]
      }
    }
    Views: {
      [_ in never]: never
    }
    Functions: {
      [_ in never]: never
    }
    Enums: {
      [_ in never]: never
    }
    CompositeTypes: {
      [_ in never]: never
    }
  }
}

type DatabaseWithoutInternals = Omit&lt;Database, &quot;__InternalSupabase&quot;&gt;

type DefaultSchema = DatabaseWithoutInternals[Extract&lt;keyof Database, &quot;public&quot;&gt;]

export type Tables&lt;
  DefaultSchemaTableNameOrOptions extends
    | keyof (DefaultSchema[&quot;Tables&quot;] &amp; DefaultSchema[&quot;Views&quot;])
    | { schema: keyof DatabaseWithoutInternals },
  TableName extends DefaultSchemaTableNameOrOptions extends {
    schema: keyof DatabaseWithoutInternals
  }
    ? keyof (DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions[&quot;schema&quot;]][&quot;Tables&quot;] &amp;
        DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions[&quot;schema&quot;]][&quot;Views&quot;])
    : never = never,
&gt; = DefaultSchemaTableNameOrOptions extends {
  schema: keyof DatabaseWithoutInternals
}
  ? (DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions[&quot;schema&quot;]][&quot;Tables&quot;] &amp;
      DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions[&quot;schema&quot;]][&quot;Views&quot;])[TableName] extends {
      Row: infer R
    }
    ? R
    : never
  : DefaultSchemaTableNameOrOptions extends keyof (DefaultSchema[&quot;Tables&quot;] &amp;
        DefaultSchema[&quot;Views&quot;])
    ? (DefaultSchema[&quot;Tables&quot;] &amp;
        DefaultSchema[&quot;Views&quot;])[DefaultSchemaTableNameOrOptions] extends {
        Row: infer R
      }
      ? R
      : never
    : never

export type TablesInsert&lt;
  DefaultSchemaTableNameOrOptions extends
    | keyof DefaultSchema[&quot;Tables&quot;]
    | { schema: keyof DatabaseWithoutInternals },
  TableName extends DefaultSchemaTableNameOrOptions extends {
    schema: keyof DatabaseWithoutInternals
  }
    ? keyof DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions[&quot;schema&quot;]][&quot;Tables&quot;]
    : never = never,
&gt; = DefaultSchemaTableNameOrOptions extends {
  schema: keyof DatabaseWithoutInternals
}
  ? DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions[&quot;schema&quot;]][&quot;Tables&quot;][TableName] extends {
      Insert: infer I
    }
    ? I
    : never
  : DefaultSchemaTableNameOrOptions extends keyof DefaultSchema[&quot;Tables&quot;]
    ? DefaultSchema[&quot;Tables&quot;][DefaultSchemaTableNameOrOptions] extends {
        Insert: infer I
      }
      ? I
      : never
    : never

export type TablesUpdate&lt;
  DefaultSchemaTableNameOrOptions extends
    | keyof DefaultSchema[&quot;Tables&quot;]
    | { schema: keyof DatabaseWithoutInternals },
  TableName extends DefaultSchemaTableNameOrOptions extends {
    schema: keyof DatabaseWithoutInternals
  }
    ? keyof DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions[&quot;schema&quot;]][&quot;Tables&quot;]
    : never = never,
&gt; = DefaultSchemaTableNameOrOptions extends {
  schema: keyof DatabaseWithoutInternals
}
  ? DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions[&quot;schema&quot;]][&quot;Tables&quot;][TableName] extends {
      Update: infer U
    }
    ? U
    : never
  : DefaultSchemaTableNameOrOptions extends keyof DefaultSchema[&quot;Tables&quot;]
    ? DefaultSchema[&quot;Tables&quot;][DefaultSchemaTableNameOrOptions] extends {
        Update: infer U
      }
      ? U
      : never
    : never

export type Enums&lt;
  DefaultSchemaEnumNameOrOptions extends
    | keyof DefaultSchema[&quot;Enums&quot;]
    | { schema: keyof DatabaseWithoutInternals },
  EnumName extends DefaultSchemaEnumNameOrOptions extends {
    schema: keyof DatabaseWithoutInternals
  }
    ? keyof DatabaseWithoutInternals[DefaultSchemaEnumNameOrOptions[&quot;schema&quot;]][&quot;Enums&quot;]
    : never = never,
&gt; = DefaultSchemaEnumNameOrOptions extends {
  schema: keyof DatabaseWithoutInternals
}
  ? DatabaseWithoutInternals[DefaultSchemaEnumNameOrOptions[&quot;schema&quot;]][&quot;Enums&quot;][EnumName]
  : DefaultSchemaEnumNameOrOptions extends keyof DefaultSchema[&quot;Enums&quot;]
    ? DefaultSchema[&quot;Enums&quot;][DefaultSchemaEnumNameOrOptions]
    : never

export type CompositeTypes&lt;
  PublicCompositeTypeNameOrOptions extends
    | keyof DefaultSchema[&quot;CompositeTypes&quot;]
    | { schema: keyof DatabaseWithoutInternals },
  CompositeTypeName extends PublicCompositeTypeNameOrOptions extends {
    schema: keyof DatabaseWithoutInternals
  }
    ? keyof DatabaseWithoutInternals[PublicCompositeTypeNameOrOptions[&quot;schema&quot;]][&quot;CompositeTypes&quot;]
    : never = never,
&gt; = PublicCompositeTypeNameOrOptions extends {
  schema: keyof DatabaseWithoutInternals
}
  ? DatabaseWithoutInternals[PublicCompositeTypeNameOrOptions[&quot;schema&quot;]][&quot;CompositeTypes&quot;][CompositeTypeName]
  : PublicCompositeTypeNameOrOptions extends keyof DefaultSchema[&quot;CompositeTypes&quot;]
    ? DefaultSchema[&quot;CompositeTypes&quot;][PublicCompositeTypeNameOrOptions]
    : never

export const Constants = {
  public: {
    Enums: {},
  },
} as const
</code></pre>
</section>

<section class="file-section" id="f-src_lib_error-capture-ts">
  <div class="file-header">
    <span class="file-path">src/lib/error-capture.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_lib_error-capture-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_lib_error-capture-ts">// Captures the original Error out-of-band so server.ts can recover the stack
// when h3 has already swallowed the throw into a generic 500 Response.

let lastCapturedError: { error: unknown; at: number } | undefined;
const TTL_MS = 5_000;

function record(error: unknown) {
  lastCapturedError = { error, at: Date.now() };
}

if (typeof globalThis.addEventListener === &quot;function&quot;) {
  globalThis.addEventListener(&quot;error&quot;, (event) =&gt; record((event as ErrorEvent).error ?? event));
  globalThis.addEventListener(&quot;unhandledrejection&quot;, (event) =&gt;
    record((event as PromiseRejectionEvent).reason),
  );
}

export function consumeLastCapturedError(): unknown {
  if (!lastCapturedError) return undefined;
  if (Date.now() - lastCapturedError.at &gt; TTL_MS) {
    lastCapturedError = undefined;
    return undefined;
  }
  const { error } = lastCapturedError;
  lastCapturedError = undefined;
  return error;
}
</code></pre>
</section>

<section class="file-section" id="f-src_lib_error-page-ts">
  <div class="file-header">
    <span class="file-path">src/lib/error-page.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_lib_error-page-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_lib_error-page-ts">export function renderErrorPage(): string {
  return `&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;utf-8&quot; /&gt;
    &lt;title&gt;This page didn&#x27;t load&lt;/title&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1&quot; /&gt;
    &lt;style&gt;
      body { font: 15px/1.5 system-ui, -apple-system, sans-serif; background: #fafafa; color: #111; display: grid; place-items: center; min-height: 100vh; margin: 0; padding: 1.5rem; }
      .card { max-width: 28rem; width: 100%; text-align: center; padding: 2rem; }
      h1 { font-size: 1.25rem; margin: 0 0 0.5rem; }
      p { color: #4b5563; margin: 0 0 1.5rem; }
      .actions { display: flex; gap: 0.5rem; justify-content: center; flex-wrap: wrap; }
      a, button { padding: 0.5rem 1rem; border-radius: 0.375rem; font: inherit; cursor: pointer; text-decoration: none; border: 1px solid transparent; }
      .primary { background: #111; color: #fff; }
      .secondary { background: #fff; color: #111; border-color: #d1d5db; }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div class=&quot;card&quot;&gt;
      &lt;h1&gt;This page didn&#x27;t load&lt;/h1&gt;
      &lt;p&gt;Something went wrong on our end. You can try refreshing or head back home.&lt;/p&gt;
      &lt;div class=&quot;actions&quot;&gt;
        &lt;button class=&quot;primary&quot; onclick=&quot;location.reload()&quot;&gt;Try again&lt;/button&gt;
        &lt;a class=&quot;secondary&quot; href=&quot;/&quot;&gt;Go home&lt;/a&gt;
      &lt;/div&gt;
    &lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;`;
}
</code></pre>
</section>

<section class="file-section" id="f-src_lib_goals-functions-ts">
  <div class="file-header">
    <span class="file-path">src/lib/goals.functions.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_lib_goals-functions-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_lib_goals-functions-ts">import { createServerFn } from &quot;@tanstack/react-start&quot;;
import { requireSupabaseAuth } from &quot;@/integrations/supabase/auth-middleware&quot;;
import type { TablesInsert } from &quot;@/integrations/supabase/types&quot;;
import { z } from &quot;zod&quot;;

// ---------- AI helpers ----------
const GATEWAY_URL = &quot;https://ai.gateway.lovable.dev/v1/chat/completions&quot;;
const MODEL = &quot;google/gemini-2.5-flash&quot;;

async function callAI(messages: Array&lt;{ role: string; content: string }&gt;, schema: unknown) {
  const key = process.env.LOVABLE_API_KEY;
  if (!key) throw new Error(&quot;LOVABLE_API_KEY missing&quot;);
  const res = await fetch(GATEWAY_URL, {
    method: &quot;POST&quot;,
    headers: {
      &quot;Content-Type&quot;: &quot;application/json&quot;,
      &quot;Lovable-API-Key&quot;: key,
    },
    body: JSON.stringify({
      model: MODEL,
      messages,
      tools: [{ type: &quot;function&quot;, function: { name: &quot;respond&quot;, description: &quot;Return structured response&quot;, parameters: schema } }],
      tool_choice: { type: &quot;function&quot;, function: { name: &quot;respond&quot; } },
    }),
  });
  if (!res.ok) {
    const text = await res.text();
    if (res.status === 429) throw new Error(&quot;AI rate limit — try again in a moment.&quot;);
    if (res.status === 402) throw new Error(&quot;AI credits exhausted. Add credits in workspace settings.&quot;);
    throw new Error(`AI error ${res.status}: ${text.slice(0, 200)}`);
  }
  const data = await res.json();
  const call = data.choices?.[0]?.message?.tool_calls?.[0];
  if (!call) throw new Error(&quot;AI returned no structured output&quot;);
  return JSON.parse(call.function.arguments);
}

// ---------- Calibrate ----------
const CalibrateInput = z.object({
  title: z.string().min(3),
  baseline: z.string().min(1),
  targetDate: z.string().min(1),
  obstacles: z.string().optional().default(&quot;&quot;),
  whyMotivation: z.string().optional().default(&quot;&quot;),
  whatIfNot: z.string().optional().default(&quot;&quot;),
});

export const calibrateGoal = createServerFn({ method: &quot;POST&quot; })
  .middleware([requireSupabaseAuth])
  .inputValidator((d: unknown) =&gt; CalibrateInput.parse(d))
  .handler(async ({ data, context }) =&gt; {
    const schema = {
      type: &quot;object&quot;,
      properties: {
        calibrated_target: { type: &quot;string&quot;, description: &quot;Specific, measurable target (e.g. &#x27;Run a 4:00 marathon&#x27;)&quot; },
        calibrated_metric: { type: &quot;string&quot;, description: &quot;How progress is measured&quot; },
        calibrated_deadline: { type: &quot;string&quot;, description: &quot;ISO date YYYY-MM-DD, adjusted if needed&quot; },
        difficulty_tier: { type: &quot;string&quot;, enum: [&quot;easy&quot;, &quot;moderate&quot;, &quot;hard&quot;, &quot;very_hard&quot;, &quot;unrealistic&quot;] },
        smart_score: { type: &quot;number&quot;, description: &quot;0-100 SMART alignment&quot; },
        explanation: { type: &quot;string&quot;, description: &quot;Plain English 2-3 sentences on the adjustment vs original&quot; },
        was_recalibrated: { type: &quot;boolean&quot; },
      },
      required: [&quot;calibrated_target&quot;, &quot;calibrated_metric&quot;, &quot;calibrated_deadline&quot;, &quot;difficulty_tier&quot;, &quot;smart_score&quot;, &quot;explanation&quot;, &quot;was_recalibrated&quot;],
      additionalProperties: false,
    };
    const sys = `You are a goal-setting coach. Rate the user&#x27;s goal against SMART criteria. Aim for &quot;hard but achievable&quot; — roughly 90th percentile difficulty for the stated baseline. If unrealistic for the timeframe, RECALIBRATE by adjusting the target OR extending the deadline (or both together — they are linked). Return the recalibrated goal with a plain-English explanation of what changed and why. If the original is already well-calibrated, return it essentially unchanged with was_recalibrated=false.`;
    const user = `Goal: ${data.title}\nCurrent baseline: ${data.baseline}\nStated target date: ${data.targetDate}\nUsual obstacles: ${data.obstacles || &quot;(none stated)&quot;}`;
    const result = await callAI([
      { role: &quot;system&quot;, content: sys },
      { role: &quot;user&quot;, content: user },
    ], schema);

    // Save
    const { data: goal, error } = await context.supabase
      .from(&quot;goals&quot;)
      .insert({
        user_id: context.userId,
        title: data.title,
        baseline: data.baseline,
        target_date: data.targetDate,
        calibrated_target: result.calibrated_target,
        calibrated_metric: result.calibrated_metric,
        calibrated_deadline: result.calibrated_deadline,
        difficulty_tier: result.difficulty_tier,
        calibration_explanation: result.explanation,
        calibration_status: &quot;calibrated&quot;,
        why_motivation: data.whyMotivation,
        what_if_not: data.whatIfNot,
        obstacles: data.obstacles,
      })
      .select()
      .single();
    if (error) throw new Error(error.message);
    return { goal, calibration: result };
  });

// ---------- Task breakdown ----------
const BreakdownInput = z.object({ goalId: z.string().uuid() });

export const generateBreakdown = createServerFn({ method: &quot;POST&quot; })
  .middleware([requireSupabaseAuth])
  .inputValidator((d: unknown) =&gt; BreakdownInput.parse(d))
  .handler(async ({ data, context }) =&gt; {
    const { data: goal, error: gErr } = await context.supabase
      .from(&quot;goals&quot;).select(&quot;*&quot;).eq(&quot;id&quot;, data.goalId).single();
    if (gErr || !goal) throw new Error(&quot;Goal not found&quot;);

    // wipe existing generated ones (in case of regen)
    await context.supabase.from(&quot;tasks&quot;).delete().eq(&quot;goal_id&quot;, goal.id);
    await context.supabase.from(&quot;daily_actions&quot;).delete().eq(&quot;goal_id&quot;, goal.id);

    const deadlineStr = goal.calibrated_deadline || goal.target_date || &quot;&quot;;
    const weeksLeft = Math.max(1, Math.min(16, Math.ceil(
      (new Date(deadlineStr || Date.now() + 8 * 7 * 86400000).getTime() - Date.now()) / (7 * 86400000)
    )));

    const schema = {
      type: &quot;object&quot;,
      properties: {
        weeks: {
          type: &quot;array&quot;,
          items: {
            type: &quot;object&quot;,
            properties: {
              week_number: { type: &quot;number&quot; },
              theme: { type: &quot;string&quot; },
              tasks: {
                type: &quot;array&quot;,
                items: {
                  type: &quot;object&quot;,
                  properties: {
                    title: { type: &quot;string&quot; },
                    description: { type: &quot;string&quot; },
                    estimated_hours: { type: &quot;number&quot;, description: &quot;1-2&quot; },
                    if_then_plans: {
                      type: &quot;array&quot;,
                      items: {
                        type: &quot;object&quot;,
                        properties: { trigger: { type: &quot;string&quot; }, response: { type: &quot;string&quot; } },
                        required: [&quot;trigger&quot;, &quot;response&quot;],
                        additionalProperties: false,
                      },
                    },
                  },
                  required: [&quot;title&quot;, &quot;description&quot;, &quot;estimated_hours&quot;, &quot;if_then_plans&quot;],
                  additionalProperties: false,
                },
              },
            },
            required: [&quot;week_number&quot;, &quot;theme&quot;, &quot;tasks&quot;],
            additionalProperties: false,
          },
        },
        daily_actions: {
          type: &quot;array&quot;,
          description: &quot;2-4 recurring daily habits that support the goal&quot;,
          items: {
            type: &quot;object&quot;,
            properties: {
              title: { type: &quot;string&quot; },
              description: { type: &quot;string&quot; },
            },
            required: [&quot;title&quot;, &quot;description&quot;],
            additionalProperties: false,
          },
        },
      },
      required: [&quot;weeks&quot;, &quot;daily_actions&quot;],
      additionalProperties: false,
    };

    const sys = `You break down calibrated goals into weekly &quot;sprints&quot; of concrete tasks (each 1-2 hours max). For each task include 1-2 if-then plans tied to the user&#x27;s stated obstacles. Also produce 2-4 recurring daily actions (habits) that support the goal — these become the habit tracker. Keep tasks specific and actionable, not generic.`;
    const user = `Calibrated goal: ${goal.calibrated_target}\nMetric: ${goal.calibrated_metric}\nDeadline: ${goal.calibrated_deadline}\nDifficulty: ${goal.difficulty_tier}\nBaseline: ${goal.baseline}\nObstacles user mentioned: ${goal.obstacles || &quot;(none)&quot;}\nWeeks available: ${weeksLeft}\n\nProduce ${Math.min(weeksLeft, 8)} weeks of sprints (3-5 tasks each) and daily actions.`;

    const result = await callAI([
      { role: &quot;system&quot;, content: sys },
      { role: &quot;user&quot;, content: user },
    ], schema);

    // Insert tasks
    const taskRows: TablesInsert&lt;&quot;tasks&quot;&gt;[] = [];
    for (const w of result.weeks) {
      w.tasks.forEach((t: { title: string; description: string; estimated_hours: number; if_then_plans: unknown }, i: number) =&gt; {
        taskRows.push({
          user_id: context.userId,
          goal_id: goal.id,
          title: t.title,
          description: t.description,
          week_number: w.week_number,
          sprint_order: i,
          estimated_hours: t.estimated_hours,
          if_then_plans: t.if_then_plans as never,
        });
      });
    }
    if (taskRows.length) {
      const { error: tErr } = await context.supabase.from(&quot;tasks&quot;).insert(taskRows);
      if (tErr) throw new Error(tErr.message);
    }

    const actionRows = result.daily_actions.map((a: { title: string; description: string }) =&gt; ({
      user_id: context.userId,
      goal_id: goal.id,
      title: a.title,
      description: a.description,
    }));
    if (actionRows.length) {
      const { error: aErr } = await context.supabase.from(&quot;daily_actions&quot;).insert(actionRows);
      if (aErr) throw new Error(aErr.message);
    }

    return { ok: true, taskCount: taskRows.length, actionCount: actionRows.length };
  });
</code></pre>
</section>

<section class="file-section" id="f-src_lib_lovable-error-reporting-ts">
  <div class="file-header">
    <span class="file-path">src/lib/lovable-error-reporting.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_lib_lovable-error-reporting-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_lib_lovable-error-reporting-ts">type LovableErrorOptions = {
  mechanism?: &quot;manual&quot; | &quot;onerror&quot; | &quot;unhandledrejection&quot; | &quot;react_error_boundary&quot;;
  handled?: boolean;
  severity?: &quot;error&quot; | &quot;warning&quot; | &quot;info&quot;;
};

type LovableEvents = {
  captureException?: (
    error: unknown,
    context?: Record&lt;string, unknown&gt;,
    options?: LovableErrorOptions,
  ) =&gt; void;
};

declare global {
  interface Window {
    __lovableEvents?: LovableEvents;
  }
}

export function reportLovableError(error: unknown, context: Record&lt;string, unknown&gt; = {}) {
  if (typeof window === &quot;undefined&quot;) return;
  window.__lovableEvents?.captureException?.(
    error,
    {
      source: &quot;react_error_boundary&quot;,
      route: window.location.pathname,
      ...context,
    },
    {
      mechanism: &quot;react_error_boundary&quot;,
      handled: false,
      severity: &quot;error&quot;,
    },
  );
}
</code></pre>
</section>

<section class="file-section" id="f-src_lib_streak-ts">
  <div class="file-header">
    <span class="file-path">src/lib/streak.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_lib_streak-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_lib_streak-ts">// Pure streak calculator with two-day rule + freezes.
// Given a set of completed dates (ISO YYYY-MM-DD) and freeze dates,
// returns current + longest streaks.
// Two-day rule: missing ONE day does not break; missing TWO consecutive does.

export function toISO(d: Date): string {
  return d.toISOString().slice(0, 10);
}

export function daysBetween(a: string, b: string): number {
  const da = new Date(a + &quot;T00:00:00Z&quot;).getTime();
  const db = new Date(b + &quot;T00:00:00Z&quot;).getTime();
  return Math.round((db - da) / 86400000);
}

export function calcStreak(completed: Set&lt;string&gt;, freezes: Set&lt;string&gt;): { current: number; longest: number } {
  if (completed.size === 0 &amp;&amp; freezes.size === 0) return { current: 0, longest: 0 };
  const all = Array.from(new Set([...completed, ...freezes])).sort();

  // longest run considering that a single-day gap is tolerated (two-day rule)
  // walk day-by-day from earliest to today.
  const earliest = all[0];
  const todayISO = toISO(new Date());
  const totalDays = daysBetween(earliest, todayISO) + 1;

  let longest = 0;
  let run = 0;
  let missedYesterday = false;
  for (let i = 0; i &lt; totalDays; i++) {
    const d = new Date(earliest + &quot;T00:00:00Z&quot;);
    d.setUTCDate(d.getUTCDate() + i);
    const iso = toISO(d);
    const active = completed.has(iso) || freezes.has(iso);
    if (active) {
      run += 1;
      missedYesterday = false;
      longest = Math.max(longest, run);
    } else {
      if (missedYesterday) {
        run = 0;
      } else {
        // one grace day — streak persists but doesn&#x27;t grow
        missedYesterday = true;
      }
    }
  }

  // current streak = same walk but reported at &quot;today&quot;
  // recompute current by walking backwards from today
  let current = 0;
  let graceUsed = false;
  for (let i = 0; ; i++) {
    const d = new Date(todayISO + &quot;T00:00:00Z&quot;);
    d.setUTCDate(d.getUTCDate() - i);
    const iso = toISO(d);
    const active = completed.has(iso) || freezes.has(iso);
    if (active) {
      current += 1;
      graceUsed = false;
    } else {
      if (i === 0) {
        // today not done yet — don&#x27;t break, don&#x27;t count
        continue;
      }
      if (!graceUsed) {
        graceUsed = true;
      } else {
        break;
      }
    }
    if (i &gt; 3650) break; // safety
  }

  return { current, longest };
}
</code></pre>
</section>

<section class="file-section" id="f-src_lib_utils-ts">
  <div class="file-header">
    <span class="file-path">src/lib/utils.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_lib_utils-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_lib_utils-ts">import { clsx, type ClassValue } from &quot;clsx&quot;;
import { twMerge } from &quot;tailwind-merge&quot;;

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs));
}
</code></pre>
</section>

<section class="file-section" id="f-src_router-tsx">
  <div class="file-header">
    <span class="file-path">src/router.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_router-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_router-tsx">import { QueryClient } from &quot;@tanstack/react-query&quot;;
import { createRouter } from &quot;@tanstack/react-router&quot;;
import { routeTree } from &quot;./routeTree.gen&quot;;

export const getRouter = () =&gt; {
  const queryClient = new QueryClient();

  const router = createRouter({
    routeTree,
    context: { queryClient },
    scrollRestoration: true,
    defaultPreloadStaleTime: 0,
  });

  return router;
};
</code></pre>
</section>

<section class="file-section" id="f-src_server-ts">
  <div class="file-header">
    <span class="file-path">src/server.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_server-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_server-ts">import &quot;./lib/error-capture&quot;;

import { consumeLastCapturedError } from &quot;./lib/error-capture&quot;;
import { renderErrorPage } from &quot;./lib/error-page&quot;;

type ServerEntry = {
  fetch: (request: Request, env: unknown, ctx: unknown) =&gt; Promise&lt;Response&gt; | Response;
};

let serverEntryPromise: Promise&lt;ServerEntry&gt; | undefined;

async function getServerEntry(): Promise&lt;ServerEntry&gt; {
  if (!serverEntryPromise) {
    serverEntryPromise = import(&quot;@tanstack/react-start/server-entry&quot;).then(
      (m) =&gt; (m.default ?? m) as ServerEntry,
    );
  }
  return serverEntryPromise;
}

// h3 swallows in-handler throws into a normal 500 Response with body
// {&quot;unhandled&quot;:true,&quot;message&quot;:&quot;HTTPError&quot;} — try/catch alone never fires for those.
async function normalizeCatastrophicSsrResponse(response: Response): Promise&lt;Response&gt; {
  if (response.status &lt; 500) return response;
  const contentType = response.headers.get(&quot;content-type&quot;) ?? &quot;&quot;;
  if (!contentType.includes(&quot;application/json&quot;)) return response;

  const body = await response.clone().text();
  if (!isH3SwallowedErrorBody(body)) return response;

  console.error(consumeLastCapturedError() ?? new Error(`h3 swallowed SSR error: ${body}`));
  return new Response(renderErrorPage(), {
    status: 500,
    headers: { &quot;content-type&quot;: &quot;text/html; charset=utf-8&quot; },
  });
}

function isH3SwallowedErrorBody(body: string): boolean {
  try {
    const payload = JSON.parse(body) as { unhandled?: unknown; message?: unknown };
    return payload.unhandled === true &amp;&amp; payload.message === &quot;HTTPError&quot;;
  } catch {
    return false;
  }
}

export default {
  async fetch(request: Request, env: unknown, ctx: unknown) {
    try {
      const handler = await getServerEntry();
      const response = await handler.fetch(request, env, ctx);
      return await normalizeCatastrophicSsrResponse(response);
    } catch (error) {
      console.error(error);
      return new Response(renderErrorPage(), {
        status: 500,
        headers: { &quot;content-type&quot;: &quot;text/html; charset=utf-8&quot; },
      });
    }
  },
};
</code></pre>
</section>

<section class="file-section" id="f-src_start-ts">
  <div class="file-header">
    <span class="file-path">src/start.ts</span>
    <button class="copy-btn" onclick="copyCode('f-src_start-ts', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_start-ts">import { createStart, createMiddleware } from &quot;@tanstack/react-start&quot;;

import { renderErrorPage } from &quot;./lib/error-page&quot;;
import { attachSupabaseAuth } from &quot;@/integrations/supabase/auth-attacher&quot;;

const errorMiddleware = createMiddleware().server(async ({ next }) =&gt; {
  try {
    return await next();
  } catch (error) {
    if (error != null &amp;&amp; typeof error === &quot;object&quot; &amp;&amp; &quot;statusCode&quot; in error) {
      throw error;
    }
    console.error(error);
    return new Response(renderErrorPage(), {
      status: 500,
      headers: { &quot;content-type&quot;: &quot;text/html; charset=utf-8&quot; },
    });
  }
});

export const startInstance = createStart(() =&gt; ({
  functionMiddleware: [attachSupabaseAuth],
  requestMiddleware: [errorMiddleware],
}));
</code></pre>
</section>

<section class="file-section" id="f-src_styles-css">
  <div class="file-header">
    <span class="file-path">src/styles.css</span>
    <button class="copy-btn" onclick="copyCode('f-src_styles-css', this)">Copy</button>
  </div>
  <pre><code class="language-css" id="code-f-src_styles-css">@import &quot;tailwindcss&quot; source(none);
@source &quot;../src&quot;;
@import &quot;tw-animate-css&quot;;

@custom-variant dark (&amp;:is(.dark *));

@theme inline {
  --font-display: &quot;Fraunces&quot;, Georgia, serif;
  --font-sans: &quot;Manrope&quot;, ui-sans-serif, system-ui, sans-serif;

  --radius-sm: calc(var(--radius) - 4px);
  --radius-md: calc(var(--radius) - 2px);
  --radius-lg: var(--radius);
  --radius-xl: calc(var(--radius) + 4px);
  --radius-2xl: calc(var(--radius) + 8px);
  --radius-3xl: calc(var(--radius) + 12px);

  --color-background: var(--background);
  --color-foreground: var(--foreground);
  --color-card: var(--card);
  --color-card-foreground: var(--card-foreground);
  --color-popover: var(--popover);
  --color-popover-foreground: var(--popover-foreground);
  --color-primary: var(--primary);
  --color-primary-foreground: var(--primary-foreground);
  --color-secondary: var(--secondary);
  --color-secondary-foreground: var(--secondary-foreground);
  --color-muted: var(--muted);
  --color-muted-foreground: var(--muted-foreground);
  --color-accent: var(--accent);
  --color-accent-foreground: var(--accent-foreground);
  --color-destructive: var(--destructive);
  --color-destructive-foreground: var(--destructive-foreground);
  --color-success: var(--success);
  --color-success-foreground: var(--success-foreground);
  --color-flame: var(--flame);
  --color-flame-glow: var(--flame-glow);
  --color-border: var(--border);
  --color-input: var(--input);
  --color-ring: var(--ring);
  --color-chart-1: var(--chart-1);
  --color-chart-2: var(--chart-2);
  --color-chart-3: var(--chart-3);
  --color-chart-4: var(--chart-4);
  --color-chart-5: var(--chart-5);

  --shadow-soft: 0 4px 20px -8px oklch(0.4 0.1 40 / 0.15);
  --shadow-glow: 0 0 40px -8px var(--flame-glow);
  --color-sidebar-ring: var(--sidebar-ring);
  --color-sidebar-border: var(--sidebar-border);
  --color-sidebar-accent-foreground: var(--sidebar-accent-foreground);
  --color-sidebar-accent: var(--sidebar-accent);
  --color-sidebar-primary-foreground: var(--sidebar-primary-foreground);
  --color-sidebar-primary: var(--sidebar-primary);
  --color-sidebar-foreground: var(--sidebar-foreground);
  --color-sidebar: var(--sidebar);
  --animate-accordion-down: accordion-down 0.2s ease-out;
  --animate-accordion-up: accordion-up 0.2s ease-out;

  @keyframes accordion-down {
    from {
      height: 0;
    }
    to {
      height: var(--radix-accordion-content-height);
    }
  }

  @keyframes accordion-up {
    from {
      height: var(--radix-accordion-content-height);
    }
    to {
      height: 0;
    }
  }
}

:root {
  --radius: 0.875rem;
  --background: oklch(0.985 0.008 85);
  --foreground: oklch(0.22 0.02 265);
  --card: oklch(1 0 0);
  --card-foreground: oklch(0.22 0.02 265);
  --popover: oklch(1 0 0);
  --popover-foreground: oklch(0.22 0.02 265);

  --primary: oklch(0.68 0.19 42);
  --primary-foreground: oklch(0.99 0.005 85);

  --secondary: oklch(0.94 0.02 85);
  --secondary-foreground: oklch(0.28 0.03 265);

  --muted: oklch(0.955 0.01 85);
  --muted-foreground: oklch(0.5 0.02 265);

  --accent: oklch(0.92 0.05 260);
  --accent-foreground: oklch(0.28 0.06 265);

  --destructive: oklch(0.6 0.22 27);
  --destructive-foreground: oklch(0.99 0 0);

  --success: oklch(0.72 0.16 148);
  --success-foreground: oklch(0.15 0.02 148);

  --flame: oklch(0.7 0.2 45);
  --flame-glow: oklch(0.75 0.22 60 / 0.5);

  --border: oklch(0.9 0.015 85);
  --input: oklch(0.9 0.015 85);
  --ring: oklch(0.68 0.19 42);

  --chart-1: oklch(0.68 0.19 42);
  --chart-2: oklch(0.65 0.15 260);
  --chart-3: oklch(0.72 0.16 148);
  --chart-4: oklch(0.75 0.16 85);
  --chart-5: oklch(0.6 0.2 320);
  --sidebar: hsl(0 0% 98%);
  --sidebar-foreground: hsl(240 5.3% 26.1%);
  --sidebar-primary: hsl(240 5.9% 10%);
  --sidebar-primary-foreground: hsl(0 0% 98%);
  --sidebar-accent: hsl(240 4.8% 95.9%);
  --sidebar-accent-foreground: hsl(240 5.9% 10%);
  --sidebar-border: hsl(220 13% 91%);
  --sidebar-ring: hsl(217.2 91.2% 59.8%);
}

.dark {
  --background: oklch(0.16 0.02 265);
  --foreground: oklch(0.96 0.01 85);
  --card: oklch(0.21 0.025 265);
  --card-foreground: oklch(0.96 0.01 85);
  --popover: oklch(0.21 0.025 265);
  --popover-foreground: oklch(0.96 0.01 85);
  --primary: oklch(0.72 0.19 45);
  --primary-foreground: oklch(0.15 0.02 265);
  --secondary: oklch(0.28 0.03 265);
  --secondary-foreground: oklch(0.96 0.01 85);
  --muted: oklch(0.26 0.02 265);
  --muted-foreground: oklch(0.7 0.02 260);
  --accent: oklch(0.32 0.06 260);
  --accent-foreground: oklch(0.96 0.01 85);
  --destructive: oklch(0.65 0.2 27);
  --destructive-foreground: oklch(0.99 0 0);
  --success: oklch(0.7 0.16 148);
  --success-foreground: oklch(0.99 0 0);
  --flame: oklch(0.75 0.2 50);
  --flame-glow: oklch(0.8 0.22 60 / 0.4);
  --border: oklch(1 0 0 / 10%);
  --input: oklch(1 0 0 / 12%);
  --ring: oklch(0.72 0.19 45);
  --chart-1: oklch(0.72 0.19 45);
  --chart-2: oklch(0.7 0.15 260);
  --chart-3: oklch(0.72 0.16 148);
  --chart-4: oklch(0.78 0.16 85);
  --chart-5: oklch(0.65 0.2 320);
  --sidebar: hsl(240 5.9% 10%);
  --sidebar-foreground: hsl(240 4.8% 95.9%);
  --sidebar-primary: hsl(224.3 76.3% 48%);
  --sidebar-primary-foreground: hsl(0 0% 100%);
  --sidebar-accent: hsl(240 3.7% 15.9%);
  --sidebar-accent-foreground: hsl(240 4.8% 95.9%);
  --sidebar-border: hsl(240 3.7% 15.9%);
  --sidebar-ring: hsl(217.2 91.2% 59.8%);
}

@layer base {
  * {
    border-color: var(--color-border);
  }
  html, body {
    font-family: var(--font-sans);
    font-feature-settings: &quot;cv02&quot;, &quot;cv03&quot;, &quot;cv04&quot;, &quot;cv11&quot;;
  }
  body {
    background-color: var(--color-background);
    color: var(--color-foreground);
    -webkit-font-smoothing: antialiased;
  }
  h1, h2, h3, h4, .font-display {
    font-family: var(--font-display);
    font-optical-sizing: auto;
    font-variation-settings: &quot;SOFT&quot; 50, &quot;WONK&quot; 0;
    letter-spacing: -0.02em;
  }
}

@utility flame-text {
  background: linear-gradient(135deg, oklch(0.72 0.2 55), oklch(0.65 0.22 30));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

@keyframes flame-flicker {
  0%, 100% { transform: scale(1) rotate(-1deg); filter: drop-shadow(0 0 8px var(--flame-glow)); }
  50% { transform: scale(1.05) rotate(1deg); filter: drop-shadow(0 0 16px var(--flame-glow)); }
}
.animate-flame { animation: flame-flicker 2.4s ease-in-out infinite; }

@keyframes pop-in {
  0% { transform: scale(0.6); opacity: 0; }
  60% { transform: scale(1.12); opacity: 1; }
  100% { transform: scale(1); opacity: 1; }
}
.animate-pop { animation: pop-in 0.35s cubic-bezier(0.34, 1.56, 0.64, 1); }

@keyframes confetti-fall {
  0% { transform: translateY(-20px) rotate(0deg); opacity: 1; }
  100% { transform: translateY(120px) rotate(720deg); opacity: 0; }
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_app-shell-tsx">
  <div class="file-header">
    <span class="file-path">src/components/app-shell.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_app-shell-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_app-shell-tsx">import { Link, useNavigate } from &quot;@tanstack/react-router&quot;;
import { Flame, Plus, LogOut } from &quot;lucide-react&quot;;
import { Button } from &quot;@/components/ui/button&quot;;
import { supabase } from &quot;@/integrations/supabase/client&quot;;
import type { ReactNode } from &quot;react&quot;;

export function AppShell({ children, streakTotal }: { children: ReactNode; streakTotal?: number }) {
  const navigate = useNavigate();
  return (
    &lt;div className=&quot;min-h-screen bg-background&quot;&gt;
      &lt;header className=&quot;sticky top-0 z-20 border-b border-border/60 bg-background/80 backdrop-blur&quot;&gt;
        &lt;div className=&quot;mx-auto flex max-w-6xl items-center justify-between px-4 py-3 sm:px-6&quot;&gt;
          &lt;Link to=&quot;/dashboard&quot; className=&quot;flex items-center gap-2&quot;&gt;
            &lt;Flame className=&quot;h-5 w-5 text-primary animate-flame&quot; /&gt;
            &lt;span className=&quot;font-display text-lg font-semibold&quot;&gt;Momentum&lt;/span&gt;
          &lt;/Link&gt;
          &lt;div className=&quot;flex items-center gap-2 sm:gap-3&quot;&gt;
            {typeof streakTotal === &quot;number&quot; &amp;&amp; (
              &lt;div className=&quot;flex items-center gap-1.5 rounded-full bg-primary/10 px-3 py-1.5 text-sm font-semibold text-primary&quot;&gt;
                &lt;Flame className=&quot;h-4 w-4&quot; /&gt;
                {streakTotal}
              &lt;/div&gt;
            )}
            &lt;Button asChild size=&quot;sm&quot; className=&quot;gap-1&quot;&gt;
              &lt;Link to=&quot;/goals/new&quot;&gt;&lt;Plus className=&quot;h-4 w-4&quot; /&gt;New goal&lt;/Link&gt;
            &lt;/Button&gt;
            &lt;Button
              size=&quot;icon&quot;
              variant=&quot;ghost&quot;
              aria-label=&quot;Sign out&quot;
              onClick={async () =&gt; {
                await supabase.auth.signOut();
                navigate({ to: &quot;/auth&quot; });
              }}
            &gt;
              &lt;LogOut className=&quot;h-4 w-4&quot; /&gt;
            &lt;/Button&gt;
          &lt;/div&gt;
        &lt;/div&gt;
      &lt;/header&gt;
      &lt;main className=&quot;mx-auto max-w-6xl px-4 py-8 sm:px-6&quot;&gt;{children}&lt;/main&gt;
    &lt;/div&gt;
  );
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_accordion-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/accordion.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_accordion-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_accordion-tsx">import * as React from &quot;react&quot;
import * as AccordionPrimitive from &quot;@radix-ui/react-accordion&quot;
import { ChevronDown } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;

const Accordion = AccordionPrimitive.Root

const AccordionItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof AccordionPrimitive.Item&gt;,
  React.ComponentPropsWithoutRef&lt;typeof AccordionPrimitive.Item&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;AccordionPrimitive.Item
    ref={ref}
    className={cn(&quot;border-b&quot;, className)}
    {...props}
  /&gt;
))
AccordionItem.displayName = &quot;AccordionItem&quot;

const AccordionTrigger = React.forwardRef&lt;
  React.ElementRef&lt;typeof AccordionPrimitive.Trigger&gt;,
  React.ComponentPropsWithoutRef&lt;typeof AccordionPrimitive.Trigger&gt;
&gt;(({ className, children, ...props }, ref) =&gt; (
  &lt;AccordionPrimitive.Header className=&quot;flex&quot;&gt;
    &lt;AccordionPrimitive.Trigger
      ref={ref}
      className={cn(
        &quot;flex flex-1 items-center justify-between py-4 text-sm font-medium transition-all hover:underline text-left [&amp;[data-state=open]&gt;svg]:rotate-180&quot;,
        className
      )}
      {...props}
    &gt;
      {children}
      &lt;ChevronDown className=&quot;h-4 w-4 shrink-0 text-muted-foreground transition-transform duration-200&quot; /&gt;
    &lt;/AccordionPrimitive.Trigger&gt;
  &lt;/AccordionPrimitive.Header&gt;
))
AccordionTrigger.displayName = AccordionPrimitive.Trigger.displayName

const AccordionContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof AccordionPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof AccordionPrimitive.Content&gt;
&gt;(({ className, children, ...props }, ref) =&gt; (
  &lt;AccordionPrimitive.Content
    ref={ref}
    className=&quot;overflow-hidden text-sm data-[state=closed]:animate-accordion-up data-[state=open]:animate-accordion-down&quot;
    {...props}
  &gt;
    &lt;div className={cn(&quot;pb-4 pt-0&quot;, className)}&gt;{children}&lt;/div&gt;
  &lt;/AccordionPrimitive.Content&gt;
))
AccordionContent.displayName = AccordionPrimitive.Content.displayName

export { Accordion, AccordionItem, AccordionTrigger, AccordionContent }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_alert-dialog-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/alert-dialog.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_alert-dialog-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_alert-dialog-tsx">&quot;use client&quot;

import * as React from &quot;react&quot;
import * as AlertDialogPrimitive from &quot;@radix-ui/react-alert-dialog&quot;

import { cn } from &quot;@/lib/utils&quot;
import { buttonVariants } from &quot;@/components/ui/button&quot;

const AlertDialog = AlertDialogPrimitive.Root

const AlertDialogTrigger = AlertDialogPrimitive.Trigger

const AlertDialogPortal = AlertDialogPrimitive.Portal

const AlertDialogOverlay = React.forwardRef&lt;
  React.ElementRef&lt;typeof AlertDialogPrimitive.Overlay&gt;,
  React.ComponentPropsWithoutRef&lt;typeof AlertDialogPrimitive.Overlay&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;AlertDialogPrimitive.Overlay
    className={cn(
      &quot;fixed inset-0 z-50 bg-black/80 data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0&quot;,
      className
    )}
    {...props}
    ref={ref}
  /&gt;
))
AlertDialogOverlay.displayName = AlertDialogPrimitive.Overlay.displayName

const AlertDialogContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof AlertDialogPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof AlertDialogPrimitive.Content&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;AlertDialogPortal&gt;
    &lt;AlertDialogOverlay /&gt;
    &lt;AlertDialogPrimitive.Content
      ref={ref}
      className={cn(
        &quot;fixed left-[50%] top-[50%] z-50 grid w-full max-w-lg translate-x-[-50%] translate-y-[-50%] gap-4 border bg-background p-6 shadow-lg duration-200 data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[state=closed]:slide-out-to-left-1/2 data-[state=closed]:slide-out-to-top-[48%] data-[state=open]:slide-in-from-left-1/2 data-[state=open]:slide-in-from-top-[48%] sm:rounded-lg&quot;,
        className
      )}
      {...props}
    /&gt;
  &lt;/AlertDialogPortal&gt;
))
AlertDialogContent.displayName = AlertDialogPrimitive.Content.displayName

const AlertDialogHeader = ({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLDivElement&gt;) =&gt; (
  &lt;div
    className={cn(
      &quot;flex flex-col space-y-2 text-center sm:text-left&quot;,
      className
    )}
    {...props}
  /&gt;
)
AlertDialogHeader.displayName = &quot;AlertDialogHeader&quot;

const AlertDialogFooter = ({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLDivElement&gt;) =&gt; (
  &lt;div
    className={cn(
      &quot;flex flex-col-reverse sm:flex-row sm:justify-end sm:space-x-2&quot;,
      className
    )}
    {...props}
  /&gt;
)
AlertDialogFooter.displayName = &quot;AlertDialogFooter&quot;

const AlertDialogTitle = React.forwardRef&lt;
  React.ElementRef&lt;typeof AlertDialogPrimitive.Title&gt;,
  React.ComponentPropsWithoutRef&lt;typeof AlertDialogPrimitive.Title&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;AlertDialogPrimitive.Title
    ref={ref}
    className={cn(&quot;text-lg font-semibold&quot;, className)}
    {...props}
  /&gt;
))
AlertDialogTitle.displayName = AlertDialogPrimitive.Title.displayName

const AlertDialogDescription = React.forwardRef&lt;
  React.ElementRef&lt;typeof AlertDialogPrimitive.Description&gt;,
  React.ComponentPropsWithoutRef&lt;typeof AlertDialogPrimitive.Description&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;AlertDialogPrimitive.Description
    ref={ref}
    className={cn(&quot;text-sm text-muted-foreground&quot;, className)}
    {...props}
  /&gt;
))
AlertDialogDescription.displayName =
  AlertDialogPrimitive.Description.displayName

const AlertDialogAction = React.forwardRef&lt;
  React.ElementRef&lt;typeof AlertDialogPrimitive.Action&gt;,
  React.ComponentPropsWithoutRef&lt;typeof AlertDialogPrimitive.Action&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;AlertDialogPrimitive.Action
    ref={ref}
    className={cn(buttonVariants(), className)}
    {...props}
  /&gt;
))
AlertDialogAction.displayName = AlertDialogPrimitive.Action.displayName

const AlertDialogCancel = React.forwardRef&lt;
  React.ElementRef&lt;typeof AlertDialogPrimitive.Cancel&gt;,
  React.ComponentPropsWithoutRef&lt;typeof AlertDialogPrimitive.Cancel&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;AlertDialogPrimitive.Cancel
    ref={ref}
    className={cn(
      buttonVariants({ variant: &quot;outline&quot; }),
      &quot;mt-2 sm:mt-0&quot;,
      className
    )}
    {...props}
  /&gt;
))
AlertDialogCancel.displayName = AlertDialogPrimitive.Cancel.displayName

export {
  AlertDialog,
  AlertDialogPortal,
  AlertDialogOverlay,
  AlertDialogTrigger,
  AlertDialogContent,
  AlertDialogHeader,
  AlertDialogFooter,
  AlertDialogTitle,
  AlertDialogDescription,
  AlertDialogAction,
  AlertDialogCancel,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_alert-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/alert.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_alert-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_alert-tsx">import * as React from &quot;react&quot;
import { cva, type VariantProps } from &quot;class-variance-authority&quot;

import { cn } from &quot;@/lib/utils&quot;

const alertVariants = cva(
  &quot;relative w-full rounded-lg border px-4 py-3 text-sm [&amp;&gt;svg+div]:translate-y-[-3px] [&amp;&gt;svg]:absolute [&amp;&gt;svg]:left-4 [&amp;&gt;svg]:top-4 [&amp;&gt;svg]:text-foreground [&amp;&gt;svg~*]:pl-7&quot;,
  {
    variants: {
      variant: {
        default: &quot;bg-background text-foreground&quot;,
        destructive:
          &quot;border-destructive/50 text-destructive dark:border-destructive [&amp;&gt;svg]:text-destructive&quot;,
      },
    },
    defaultVariants: {
      variant: &quot;default&quot;,
    },
  }
)

const Alert = React.forwardRef&lt;
  HTMLDivElement,
  React.HTMLAttributes&lt;HTMLDivElement&gt; &amp; VariantProps&lt;typeof alertVariants&gt;
&gt;(({ className, variant, ...props }, ref) =&gt; (
  &lt;div
    ref={ref}
    role=&quot;alert&quot;
    className={cn(alertVariants({ variant }), className)}
    {...props}
  /&gt;
))
Alert.displayName = &quot;Alert&quot;

const AlertTitle = React.forwardRef&lt;
  HTMLParagraphElement,
  React.HTMLAttributes&lt;HTMLHeadingElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;h5
    ref={ref}
    className={cn(&quot;mb-1 font-medium leading-none tracking-tight&quot;, className)}
    {...props}
  /&gt;
))
AlertTitle.displayName = &quot;AlertTitle&quot;

const AlertDescription = React.forwardRef&lt;
  HTMLParagraphElement,
  React.HTMLAttributes&lt;HTMLParagraphElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div
    ref={ref}
    className={cn(&quot;text-sm [&amp;_p]:leading-relaxed&quot;, className)}
    {...props}
  /&gt;
))
AlertDescription.displayName = &quot;AlertDescription&quot;

export { Alert, AlertTitle, AlertDescription }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_aspect-ratio-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/aspect-ratio.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_aspect-ratio-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_aspect-ratio-tsx">import * as AspectRatioPrimitive from &quot;@radix-ui/react-aspect-ratio&quot;

const AspectRatio = AspectRatioPrimitive.Root

export { AspectRatio }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_avatar-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/avatar.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_avatar-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_avatar-tsx">&quot;use client&quot;

import * as React from &quot;react&quot;
import * as AvatarPrimitive from &quot;@radix-ui/react-avatar&quot;

import { cn } from &quot;@/lib/utils&quot;

const Avatar = React.forwardRef&lt;
  React.ElementRef&lt;typeof AvatarPrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof AvatarPrimitive.Root&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;AvatarPrimitive.Root
    ref={ref}
    className={cn(
      &quot;relative flex h-10 w-10 shrink-0 overflow-hidden rounded-full&quot;,
      className
    )}
    {...props}
  /&gt;
))
Avatar.displayName = AvatarPrimitive.Root.displayName

const AvatarImage = React.forwardRef&lt;
  React.ElementRef&lt;typeof AvatarPrimitive.Image&gt;,
  React.ComponentPropsWithoutRef&lt;typeof AvatarPrimitive.Image&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;AvatarPrimitive.Image
    ref={ref}
    className={cn(&quot;aspect-square h-full w-full&quot;, className)}
    {...props}
  /&gt;
))
AvatarImage.displayName = AvatarPrimitive.Image.displayName

const AvatarFallback = React.forwardRef&lt;
  React.ElementRef&lt;typeof AvatarPrimitive.Fallback&gt;,
  React.ComponentPropsWithoutRef&lt;typeof AvatarPrimitive.Fallback&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;AvatarPrimitive.Fallback
    ref={ref}
    className={cn(
      &quot;flex h-full w-full items-center justify-center rounded-full bg-muted&quot;,
      className
    )}
    {...props}
  /&gt;
))
AvatarFallback.displayName = AvatarPrimitive.Fallback.displayName

export { Avatar, AvatarImage, AvatarFallback }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_badge-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/badge.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_badge-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_badge-tsx">import * as React from &quot;react&quot;
import { cva, type VariantProps } from &quot;class-variance-authority&quot;

import { cn } from &quot;@/lib/utils&quot;

const badgeVariants = cva(
  &quot;inline-flex items-center rounded-md border px-2.5 py-0.5 text-xs font-semibold transition-colors focus:outline-none focus:ring-2 focus:ring-ring focus:ring-offset-2&quot;,
  {
    variants: {
      variant: {
        default:
          &quot;border-transparent bg-primary text-primary-foreground shadow hover:bg-primary/80&quot;,
        secondary:
          &quot;border-transparent bg-secondary text-secondary-foreground hover:bg-secondary/80&quot;,
        destructive:
          &quot;border-transparent bg-destructive text-destructive-foreground shadow hover:bg-destructive/80&quot;,
        outline: &quot;text-foreground&quot;,
      },
    },
    defaultVariants: {
      variant: &quot;default&quot;,
    },
  }
)

export interface BadgeProps
  extends React.HTMLAttributes&lt;HTMLDivElement&gt;,
    VariantProps&lt;typeof badgeVariants&gt; {}

function Badge({ className, variant, ...props }: BadgeProps) {
  return (
    &lt;div className={cn(badgeVariants({ variant }), className)} {...props} /&gt;
  )
}

export { Badge, badgeVariants }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_breadcrumb-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/breadcrumb.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_breadcrumb-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_breadcrumb-tsx">import * as React from &quot;react&quot;
import { Slot } from &quot;@radix-ui/react-slot&quot;
import { ChevronRight, MoreHorizontal } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;

const Breadcrumb = React.forwardRef&lt;
  HTMLElement,
  React.ComponentPropsWithoutRef&lt;&quot;nav&quot;&gt; &amp; {
    separator?: React.ReactNode
  }
&gt;(({ ...props }, ref) =&gt; &lt;nav ref={ref} aria-label=&quot;breadcrumb&quot; {...props} /&gt;)
Breadcrumb.displayName = &quot;Breadcrumb&quot;

const BreadcrumbList = React.forwardRef&lt;
  HTMLOListElement,
  React.ComponentPropsWithoutRef&lt;&quot;ol&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;ol
    ref={ref}
    className={cn(
      &quot;flex flex-wrap items-center gap-1.5 break-words text-sm text-muted-foreground sm:gap-2.5&quot;,
      className
    )}
    {...props}
  /&gt;
))
BreadcrumbList.displayName = &quot;BreadcrumbList&quot;

const BreadcrumbItem = React.forwardRef&lt;
  HTMLLIElement,
  React.ComponentPropsWithoutRef&lt;&quot;li&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;li
    ref={ref}
    className={cn(&quot;inline-flex items-center gap-1.5&quot;, className)}
    {...props}
  /&gt;
))
BreadcrumbItem.displayName = &quot;BreadcrumbItem&quot;

const BreadcrumbLink = React.forwardRef&lt;
  HTMLAnchorElement,
  React.ComponentPropsWithoutRef&lt;&quot;a&quot;&gt; &amp; {
    asChild?: boolean
  }
&gt;(({ asChild, className, ...props }, ref) =&gt; {
  const Comp = asChild ? Slot : &quot;a&quot;

  return (
    &lt;Comp
      ref={ref}
      className={cn(&quot;transition-colors hover:text-foreground&quot;, className)}
      {...props}
    /&gt;
  )
})
BreadcrumbLink.displayName = &quot;BreadcrumbLink&quot;

const BreadcrumbPage = React.forwardRef&lt;
  HTMLSpanElement,
  React.ComponentPropsWithoutRef&lt;&quot;span&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;span
    ref={ref}
    role=&quot;link&quot;
    aria-disabled=&quot;true&quot;
    aria-current=&quot;page&quot;
    className={cn(&quot;font-normal text-foreground&quot;, className)}
    {...props}
  /&gt;
))
BreadcrumbPage.displayName = &quot;BreadcrumbPage&quot;

const BreadcrumbSeparator = ({
  children,
  className,
  ...props
}: React.ComponentProps&lt;&quot;li&quot;&gt;) =&gt; (
  &lt;li
    role=&quot;presentation&quot;
    aria-hidden=&quot;true&quot;
    className={cn(&quot;[&amp;&gt;svg]:w-3.5 [&amp;&gt;svg]:h-3.5&quot;, className)}
    {...props}
  &gt;
    {children ?? &lt;ChevronRight /&gt;}
  &lt;/li&gt;
)
BreadcrumbSeparator.displayName = &quot;BreadcrumbSeparator&quot;

const BreadcrumbEllipsis = ({
  className,
  ...props
}: React.ComponentProps&lt;&quot;span&quot;&gt;) =&gt; (
  &lt;span
    role=&quot;presentation&quot;
    aria-hidden=&quot;true&quot;
    className={cn(&quot;flex h-9 w-9 items-center justify-center&quot;, className)}
    {...props}
  &gt;
    &lt;MoreHorizontal className=&quot;h-4 w-4&quot; /&gt;
    &lt;span className=&quot;sr-only&quot;&gt;More&lt;/span&gt;
  &lt;/span&gt;
)
BreadcrumbEllipsis.displayName = &quot;BreadcrumbElipssis&quot;

export {
  Breadcrumb,
  BreadcrumbList,
  BreadcrumbItem,
  BreadcrumbLink,
  BreadcrumbPage,
  BreadcrumbSeparator,
  BreadcrumbEllipsis,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_button-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/button.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_button-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_button-tsx">import * as React from &quot;react&quot;
import { Slot } from &quot;@radix-ui/react-slot&quot;
import { cva, type VariantProps } from &quot;class-variance-authority&quot;

import { cn } from &quot;@/lib/utils&quot;

const buttonVariants = cva(
  &quot;inline-flex items-center justify-center gap-2 whitespace-nowrap rounded-md text-sm font-medium transition-colors focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring disabled:pointer-events-none disabled:opacity-50 [&amp;_svg]:pointer-events-none [&amp;_svg]:size-4 [&amp;_svg]:shrink-0&quot;,
  {
    variants: {
      variant: {
        default:
          &quot;bg-primary text-primary-foreground shadow hover:bg-primary/90&quot;,
        destructive:
          &quot;bg-destructive text-destructive-foreground shadow-sm hover:bg-destructive/90&quot;,
        outline:
          &quot;border border-input bg-background shadow-sm hover:bg-accent hover:text-accent-foreground&quot;,
        secondary:
          &quot;bg-secondary text-secondary-foreground shadow-sm hover:bg-secondary/80&quot;,
        ghost: &quot;hover:bg-accent hover:text-accent-foreground&quot;,
        link: &quot;text-primary underline-offset-4 hover:underline&quot;,
      },
      size: {
        default: &quot;h-9 px-4 py-2&quot;,
        sm: &quot;h-8 rounded-md px-3 text-xs&quot;,
        lg: &quot;h-10 rounded-md px-8&quot;,
        icon: &quot;h-9 w-9&quot;,
      },
    },
    defaultVariants: {
      variant: &quot;default&quot;,
      size: &quot;default&quot;,
    },
  }
)

export interface ButtonProps
  extends React.ButtonHTMLAttributes&lt;HTMLButtonElement&gt;,
    VariantProps&lt;typeof buttonVariants&gt; {
  asChild?: boolean
}

const Button = React.forwardRef&lt;HTMLButtonElement, ButtonProps&gt;(
  ({ className, variant, size, asChild = false, ...props }, ref) =&gt; {
    const Comp = asChild ? Slot : &quot;button&quot;
    return (
      &lt;Comp
        className={cn(buttonVariants({ variant, size, className }))}
        ref={ref}
        {...props}
      /&gt;
    )
  }
)
Button.displayName = &quot;Button&quot;

export { Button, buttonVariants }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_calendar-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/calendar.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_calendar-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_calendar-tsx">import * as React from &quot;react&quot;
import {
  ChevronDownIcon,
  ChevronLeftIcon,
  ChevronRightIcon,
} from &quot;lucide-react&quot;
import { DayButton, DayPicker, getDefaultClassNames } from &quot;react-day-picker&quot;

import { cn } from &quot;@/lib/utils&quot;
import { Button, buttonVariants } from &quot;@/components/ui/button&quot;

function Calendar({
  className,
  classNames,
  showOutsideDays = true,
  captionLayout = &quot;label&quot;,
  buttonVariant = &quot;ghost&quot;,
  formatters,
  components,
  ...props
}: React.ComponentProps&lt;typeof DayPicker&gt; &amp; {
  buttonVariant?: React.ComponentProps&lt;typeof Button&gt;[&quot;variant&quot;]
}) {
  const defaultClassNames = getDefaultClassNames()

  return (
    &lt;DayPicker
      showOutsideDays={showOutsideDays}
      className={cn(
        &quot;bg-background group/calendar p-3 [--cell-size:2rem] [[data-slot=card-content]_&amp;]:bg-transparent [[data-slot=popover-content]_&amp;]:bg-transparent&quot;,
        String.raw`rtl:**:[.rdp-button\_next&gt;svg]:rotate-180`,
        String.raw`rtl:**:[.rdp-button\_previous&gt;svg]:rotate-180`,
        className
      )}
      captionLayout={captionLayout}
      formatters={{
        formatMonthDropdown: (date) =&gt;
          date.toLocaleString(&quot;default&quot;, { month: &quot;short&quot; }),
        ...formatters,
      }}
      classNames={{
        root: cn(&quot;w-fit&quot;, defaultClassNames.root),
        months: cn(
          &quot;relative flex flex-col gap-4 md:flex-row&quot;,
          defaultClassNames.months
        ),
        month: cn(&quot;flex w-full flex-col gap-4&quot;, defaultClassNames.month),
        nav: cn(
          &quot;absolute inset-x-0 top-0 flex w-full items-center justify-between gap-1&quot;,
          defaultClassNames.nav
        ),
        button_previous: cn(
          buttonVariants({ variant: buttonVariant }),
          &quot;h-[--cell-size] w-[--cell-size] select-none p-0 aria-disabled:opacity-50&quot;,
          defaultClassNames.button_previous
        ),
        button_next: cn(
          buttonVariants({ variant: buttonVariant }),
          &quot;h-[--cell-size] w-[--cell-size] select-none p-0 aria-disabled:opacity-50&quot;,
          defaultClassNames.button_next
        ),
        month_caption: cn(
          &quot;flex h-[--cell-size] w-full items-center justify-center px-[--cell-size]&quot;,
          defaultClassNames.month_caption
        ),
        dropdowns: cn(
          &quot;flex h-[--cell-size] w-full items-center justify-center gap-1.5 text-sm font-medium&quot;,
          defaultClassNames.dropdowns
        ),
        dropdown_root: cn(
          &quot;has-focus:border-ring border-input shadow-xs has-focus:ring-ring/50 has-focus:ring-[3px] relative rounded-md border&quot;,
          defaultClassNames.dropdown_root
        ),
        dropdown: cn(
          &quot;bg-popover absolute inset-0 opacity-0&quot;,
          defaultClassNames.dropdown
        ),
        caption_label: cn(
          &quot;select-none font-medium&quot;,
          captionLayout === &quot;label&quot;
            ? &quot;text-sm&quot;
            : &quot;[&amp;&gt;svg]:text-muted-foreground flex h-8 items-center gap-1 rounded-md pl-2 pr-1 text-sm [&amp;&gt;svg]:size-3.5&quot;,
          defaultClassNames.caption_label
        ),
        month_grid: cn(&quot;w-full border-collapse&quot;, defaultClassNames.month_grid),
        weekdays: cn(&quot;flex&quot;, defaultClassNames.weekdays),
        weekday: cn(
          &quot;text-muted-foreground flex-1 select-none rounded-md text-[0.8rem] font-normal&quot;,
          defaultClassNames.weekday
        ),
        week: cn(&quot;mt-2 flex w-full&quot;, defaultClassNames.week),
        week_number_header: cn(
          &quot;w-[--cell-size] select-none&quot;,
          defaultClassNames.week_number_header
        ),
        week_number: cn(
          &quot;text-muted-foreground select-none text-[0.8rem]&quot;,
          defaultClassNames.week_number
        ),
        day: cn(
          &quot;group/day relative aspect-square h-full w-full select-none p-0 text-center [&amp;:first-child[data-selected=true]_button]:rounded-l-md [&amp;:last-child[data-selected=true]_button]:rounded-r-md&quot;,
          defaultClassNames.day
        ),
        range_start: cn(
          &quot;bg-accent rounded-l-md&quot;,
          defaultClassNames.range_start
        ),
        range_middle: cn(&quot;rounded-none&quot;, defaultClassNames.range_middle),
        range_end: cn(&quot;bg-accent rounded-r-md&quot;, defaultClassNames.range_end),
        today: cn(
          &quot;bg-accent text-accent-foreground rounded-md data-[selected=true]:rounded-none&quot;,
          defaultClassNames.today
        ),
        outside: cn(
          &quot;text-muted-foreground aria-selected:text-muted-foreground&quot;,
          defaultClassNames.outside
        ),
        disabled: cn(
          &quot;text-muted-foreground opacity-50&quot;,
          defaultClassNames.disabled
        ),
        hidden: cn(&quot;invisible&quot;, defaultClassNames.hidden),
        ...classNames,
      }}
      components={{
        Root: ({ className, rootRef, ...props }) =&gt; {
          return (
            &lt;div
              data-slot=&quot;calendar&quot;
              ref={rootRef}
              className={cn(className)}
              {...props}
            /&gt;
          )
        },
        Chevron: ({ className, orientation, ...props }) =&gt; {
          if (orientation === &quot;left&quot;) {
            return (
              &lt;ChevronLeftIcon className={cn(&quot;size-4&quot;, className)} {...props} /&gt;
            )
          }

          if (orientation === &quot;right&quot;) {
            return (
              &lt;ChevronRightIcon
                className={cn(&quot;size-4&quot;, className)}
                {...props}
              /&gt;
            )
          }

          return (
            &lt;ChevronDownIcon className={cn(&quot;size-4&quot;, className)} {...props} /&gt;
          )
        },
        DayButton: CalendarDayButton,
        WeekNumber: ({ children, ...props }) =&gt; {
          return (
            &lt;td {...props}&gt;
              &lt;div className=&quot;flex size-[--cell-size] items-center justify-center text-center&quot;&gt;
                {children}
              &lt;/div&gt;
            &lt;/td&gt;
          )
        },
        ...components,
      }}
      {...props}
    /&gt;
  )
}

function CalendarDayButton({
  className,
  day,
  modifiers,
  ...props
}: React.ComponentProps&lt;typeof DayButton&gt;) {
  const defaultClassNames = getDefaultClassNames()

  const ref = React.useRef&lt;HTMLButtonElement&gt;(null)
  React.useEffect(() =&gt; {
    if (modifiers.focused) ref.current?.focus()
  }, [modifiers.focused])

  return (
    &lt;Button
      ref={ref}
      variant=&quot;ghost&quot;
      size=&quot;icon&quot;
      data-day={day.date.toLocaleDateString()}
      data-selected-single={
        modifiers.selected &amp;&amp;
        !modifiers.range_start &amp;&amp;
        !modifiers.range_end &amp;&amp;
        !modifiers.range_middle
      }
      data-range-start={modifiers.range_start}
      data-range-end={modifiers.range_end}
      data-range-middle={modifiers.range_middle}
      className={cn(
        &quot;data-[selected-single=true]:bg-primary data-[selected-single=true]:text-primary-foreground data-[range-middle=true]:bg-accent data-[range-middle=true]:text-accent-foreground data-[range-start=true]:bg-primary data-[range-start=true]:text-primary-foreground data-[range-end=true]:bg-primary data-[range-end=true]:text-primary-foreground group-data-[focused=true]/day:border-ring group-data-[focused=true]/day:ring-ring/50 flex aspect-square h-auto w-full min-w-[--cell-size] flex-col gap-1 font-normal leading-none data-[range-end=true]:rounded-md data-[range-middle=true]:rounded-none data-[range-start=true]:rounded-md group-data-[focused=true]/day:relative group-data-[focused=true]/day:z-10 group-data-[focused=true]/day:ring-[3px] [&amp;&gt;span]:text-xs [&amp;&gt;span]:opacity-70&quot;,
        defaultClassNames.day,
        className
      )}
      {...props}
    /&gt;
  )
}

export { Calendar, CalendarDayButton }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_card-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/card.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_card-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_card-tsx">import * as React from &quot;react&quot;

import { cn } from &quot;@/lib/utils&quot;

const Card = React.forwardRef&lt;
  HTMLDivElement,
  React.HTMLAttributes&lt;HTMLDivElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div
    ref={ref}
    className={cn(
      &quot;rounded-xl border bg-card text-card-foreground shadow&quot;,
      className
    )}
    {...props}
  /&gt;
))
Card.displayName = &quot;Card&quot;

const CardHeader = React.forwardRef&lt;
  HTMLDivElement,
  React.HTMLAttributes&lt;HTMLDivElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div
    ref={ref}
    className={cn(&quot;flex flex-col space-y-1.5 p-6&quot;, className)}
    {...props}
  /&gt;
))
CardHeader.displayName = &quot;CardHeader&quot;

const CardTitle = React.forwardRef&lt;
  HTMLDivElement,
  React.HTMLAttributes&lt;HTMLDivElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div
    ref={ref}
    className={cn(&quot;font-semibold leading-none tracking-tight&quot;, className)}
    {...props}
  /&gt;
))
CardTitle.displayName = &quot;CardTitle&quot;

const CardDescription = React.forwardRef&lt;
  HTMLDivElement,
  React.HTMLAttributes&lt;HTMLDivElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div
    ref={ref}
    className={cn(&quot;text-sm text-muted-foreground&quot;, className)}
    {...props}
  /&gt;
))
CardDescription.displayName = &quot;CardDescription&quot;

const CardContent = React.forwardRef&lt;
  HTMLDivElement,
  React.HTMLAttributes&lt;HTMLDivElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div ref={ref} className={cn(&quot;p-6 pt-0&quot;, className)} {...props} /&gt;
))
CardContent.displayName = &quot;CardContent&quot;

const CardFooter = React.forwardRef&lt;
  HTMLDivElement,
  React.HTMLAttributes&lt;HTMLDivElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div
    ref={ref}
    className={cn(&quot;flex items-center p-6 pt-0&quot;, className)}
    {...props}
  /&gt;
))
CardFooter.displayName = &quot;CardFooter&quot;

export { Card, CardHeader, CardFooter, CardTitle, CardDescription, CardContent }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_carousel-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/carousel.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_carousel-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_carousel-tsx">&quot;use client&quot;

import * as React from &quot;react&quot;
import useEmblaCarousel, {
  type UseEmblaCarouselType,
} from &quot;embla-carousel-react&quot;
import { ArrowLeft, ArrowRight } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;
import { Button } from &quot;@/components/ui/button&quot;

type CarouselApi = UseEmblaCarouselType[1]
type UseCarouselParameters = Parameters&lt;typeof useEmblaCarousel&gt;
type CarouselOptions = UseCarouselParameters[0]
type CarouselPlugin = UseCarouselParameters[1]

type CarouselProps = {
  opts?: CarouselOptions
  plugins?: CarouselPlugin
  orientation?: &quot;horizontal&quot; | &quot;vertical&quot;
  setApi?: (api: CarouselApi) =&gt; void
}

type CarouselContextProps = {
  carouselRef: ReturnType&lt;typeof useEmblaCarousel&gt;[0]
  api: ReturnType&lt;typeof useEmblaCarousel&gt;[1]
  scrollPrev: () =&gt; void
  scrollNext: () =&gt; void
  canScrollPrev: boolean
  canScrollNext: boolean
} &amp; CarouselProps

const CarouselContext = React.createContext&lt;CarouselContextProps | null&gt;(null)

function useCarousel() {
  const context = React.useContext(CarouselContext)

  if (!context) {
    throw new Error(&quot;useCarousel must be used within a &lt;Carousel /&gt;&quot;)
  }

  return context
}

const Carousel = React.forwardRef&lt;
  HTMLDivElement,
  React.HTMLAttributes&lt;HTMLDivElement&gt; &amp; CarouselProps
&gt;(
  (
    {
      orientation = &quot;horizontal&quot;,
      opts,
      setApi,
      plugins,
      className,
      children,
      ...props
    },
    ref
  ) =&gt; {
    const [carouselRef, api] = useEmblaCarousel(
      {
        ...opts,
        axis: orientation === &quot;horizontal&quot; ? &quot;x&quot; : &quot;y&quot;,
      },
      plugins
    )
    const [canScrollPrev, setCanScrollPrev] = React.useState(false)
    const [canScrollNext, setCanScrollNext] = React.useState(false)

    const onSelect = React.useCallback((api: CarouselApi) =&gt; {
      if (!api) {
        return
      }

      setCanScrollPrev(api.canScrollPrev())
      setCanScrollNext(api.canScrollNext())
    }, [])

    const scrollPrev = React.useCallback(() =&gt; {
      api?.scrollPrev()
    }, [api])

    const scrollNext = React.useCallback(() =&gt; {
      api?.scrollNext()
    }, [api])

    const handleKeyDown = React.useCallback(
      (event: React.KeyboardEvent&lt;HTMLDivElement&gt;) =&gt; {
        if (event.key === &quot;ArrowLeft&quot;) {
          event.preventDefault()
          scrollPrev()
        } else if (event.key === &quot;ArrowRight&quot;) {
          event.preventDefault()
          scrollNext()
        }
      },
      [scrollPrev, scrollNext]
    )

    React.useEffect(() =&gt; {
      if (!api || !setApi) {
        return
      }

      setApi(api)
    }, [api, setApi])

    React.useEffect(() =&gt; {
      if (!api) {
        return
      }

      onSelect(api)
      api.on(&quot;reInit&quot;, onSelect)
      api.on(&quot;select&quot;, onSelect)

      return () =&gt; {
        api?.off(&quot;select&quot;, onSelect)
      }
    }, [api, onSelect])

    return (
      &lt;CarouselContext.Provider
        value={{
          carouselRef,
          api: api,
          opts,
          orientation:
            orientation || (opts?.axis === &quot;y&quot; ? &quot;vertical&quot; : &quot;horizontal&quot;),
          scrollPrev,
          scrollNext,
          canScrollPrev,
          canScrollNext,
        }}
      &gt;
        &lt;div
          ref={ref}
          onKeyDownCapture={handleKeyDown}
          className={cn(&quot;relative&quot;, className)}
          role=&quot;region&quot;
          aria-roledescription=&quot;carousel&quot;
          {...props}
        &gt;
          {children}
        &lt;/div&gt;
      &lt;/CarouselContext.Provider&gt;
    )
  }
)
Carousel.displayName = &quot;Carousel&quot;

const CarouselContent = React.forwardRef&lt;
  HTMLDivElement,
  React.HTMLAttributes&lt;HTMLDivElement&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  const { carouselRef, orientation } = useCarousel()

  return (
    &lt;div ref={carouselRef} className=&quot;overflow-hidden&quot;&gt;
      &lt;div
        ref={ref}
        className={cn(
          &quot;flex&quot;,
          orientation === &quot;horizontal&quot; ? &quot;-ml-4&quot; : &quot;-mt-4 flex-col&quot;,
          className
        )}
        {...props}
      /&gt;
    &lt;/div&gt;
  )
})
CarouselContent.displayName = &quot;CarouselContent&quot;

const CarouselItem = React.forwardRef&lt;
  HTMLDivElement,
  React.HTMLAttributes&lt;HTMLDivElement&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  const { orientation } = useCarousel()

  return (
    &lt;div
      ref={ref}
      role=&quot;group&quot;
      aria-roledescription=&quot;slide&quot;
      className={cn(
        &quot;min-w-0 shrink-0 grow-0 basis-full&quot;,
        orientation === &quot;horizontal&quot; ? &quot;pl-4&quot; : &quot;pt-4&quot;,
        className
      )}
      {...props}
    /&gt;
  )
})
CarouselItem.displayName = &quot;CarouselItem&quot;

const CarouselPrevious = React.forwardRef&lt;
  HTMLButtonElement,
  React.ComponentProps&lt;typeof Button&gt;
&gt;(({ className, variant = &quot;outline&quot;, size = &quot;icon&quot;, ...props }, ref) =&gt; {
  const { orientation, scrollPrev, canScrollPrev } = useCarousel()

  return (
    &lt;Button
      ref={ref}
      variant={variant}
      size={size}
      className={cn(
        &quot;absolute  h-8 w-8 rounded-full&quot;,
        orientation === &quot;horizontal&quot;
          ? &quot;-left-12 top-1/2 -translate-y-1/2&quot;
          : &quot;-top-12 left-1/2 -translate-x-1/2 rotate-90&quot;,
        className
      )}
      disabled={!canScrollPrev}
      onClick={scrollPrev}
      {...props}
    &gt;
      &lt;ArrowLeft className=&quot;h-4 w-4&quot; /&gt;
      &lt;span className=&quot;sr-only&quot;&gt;Previous slide&lt;/span&gt;
    &lt;/Button&gt;
  )
})
CarouselPrevious.displayName = &quot;CarouselPrevious&quot;

const CarouselNext = React.forwardRef&lt;
  HTMLButtonElement,
  React.ComponentProps&lt;typeof Button&gt;
&gt;(({ className, variant = &quot;outline&quot;, size = &quot;icon&quot;, ...props }, ref) =&gt; {
  const { orientation, scrollNext, canScrollNext } = useCarousel()

  return (
    &lt;Button
      ref={ref}
      variant={variant}
      size={size}
      className={cn(
        &quot;absolute h-8 w-8 rounded-full&quot;,
        orientation === &quot;horizontal&quot;
          ? &quot;-right-12 top-1/2 -translate-y-1/2&quot;
          : &quot;-bottom-12 left-1/2 -translate-x-1/2 rotate-90&quot;,
        className
      )}
      disabled={!canScrollNext}
      onClick={scrollNext}
      {...props}
    &gt;
      &lt;ArrowRight className=&quot;h-4 w-4&quot; /&gt;
      &lt;span className=&quot;sr-only&quot;&gt;Next slide&lt;/span&gt;
    &lt;/Button&gt;
  )
})
CarouselNext.displayName = &quot;CarouselNext&quot;

export {
  type CarouselApi,
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselPrevious,
  CarouselNext,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_chart-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/chart.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_chart-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_chart-tsx">import * as React from &quot;react&quot;
import * as RechartsPrimitive from &quot;recharts&quot;

import { cn } from &quot;@/lib/utils&quot;

// Format: { THEME_NAME: CSS_SELECTOR }
const THEMES = { light: &quot;&quot;, dark: &quot;.dark&quot; } as const

export type ChartConfig = {
  [k in string]: {
    label?: React.ReactNode
    icon?: React.ComponentType
  } &amp; (
    | { color?: string; theme?: never }
    | { color?: never; theme: Record&lt;keyof typeof THEMES, string&gt; }
  )
}

type ChartContextProps = {
  config: ChartConfig
}

const ChartContext = React.createContext&lt;ChartContextProps | null&gt;(null)

function useChart() {
  const context = React.useContext(ChartContext)

  if (!context) {
    throw new Error(&quot;useChart must be used within a &lt;ChartContainer /&gt;&quot;)
  }

  return context
}

const ChartContainer = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;div&quot;&gt; &amp; {
    config: ChartConfig
    children: React.ComponentProps&lt;
      typeof RechartsPrimitive.ResponsiveContainer
    &gt;[&quot;children&quot;]
  }
&gt;(({ id, className, children, config, ...props }, ref) =&gt; {
  const uniqueId = React.useId()
  const chartId = `chart-${id || uniqueId.replace(/:/g, &quot;&quot;)}`

  return (
    &lt;ChartContext.Provider value={{ config }}&gt;
      &lt;div
        data-chart={chartId}
        ref={ref}
        className={cn(
          &quot;flex aspect-video justify-center text-xs [&amp;_.recharts-cartesian-axis-tick_text]:fill-muted-foreground [&amp;_.recharts-cartesian-grid_line[stroke=&#x27;#ccc&#x27;]]:stroke-border/50 [&amp;_.recharts-curve.recharts-tooltip-cursor]:stroke-border [&amp;_.recharts-dot[stroke=&#x27;#fff&#x27;]]:stroke-transparent [&amp;_.recharts-layer]:outline-none [&amp;_.recharts-polar-grid_[stroke=&#x27;#ccc&#x27;]]:stroke-border [&amp;_.recharts-radial-bar-background-sector]:fill-muted [&amp;_.recharts-rectangle.recharts-tooltip-cursor]:fill-muted [&amp;_.recharts-reference-line_[stroke=&#x27;#ccc&#x27;]]:stroke-border [&amp;_.recharts-sector[stroke=&#x27;#fff&#x27;]]:stroke-transparent [&amp;_.recharts-sector]:outline-none [&amp;_.recharts-surface]:outline-none&quot;,
          className
        )}
        {...props}
      &gt;
        &lt;ChartStyle id={chartId} config={config} /&gt;
        &lt;RechartsPrimitive.ResponsiveContainer&gt;
          {children}
        &lt;/RechartsPrimitive.ResponsiveContainer&gt;
      &lt;/div&gt;
    &lt;/ChartContext.Provider&gt;
  )
})
ChartContainer.displayName = &quot;Chart&quot;

const ChartStyle = ({ id, config }: { id: string; config: ChartConfig }) =&gt; {
  const colorConfig = Object.entries(config).filter(
    ([, config]) =&gt; config.theme || config.color
  )

  if (!colorConfig.length) {
    return null
  }

  return (
    &lt;style
      dangerouslySetInnerHTML={{
        __html: Object.entries(THEMES)
          .map(
            ([theme, prefix]) =&gt; `
${prefix} [data-chart=${id}] {
${colorConfig
  .map(([key, itemConfig]) =&gt; {
    const color =
      itemConfig.theme?.[theme as keyof typeof itemConfig.theme] ||
      itemConfig.color
    return color ? `  --color-${key}: ${color};` : null
  })
  .join(&quot;\n&quot;)}
}
`
          )
          .join(&quot;\n&quot;),
      }}
    /&gt;
  )
}

const ChartTooltip = RechartsPrimitive.Tooltip

const ChartTooltipContent = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;typeof RechartsPrimitive.Tooltip&gt; &amp;
    React.ComponentProps&lt;&quot;div&quot;&gt; &amp; {
      hideLabel?: boolean
      hideIndicator?: boolean
      indicator?: &quot;line&quot; | &quot;dot&quot; | &quot;dashed&quot;
      nameKey?: string
      labelKey?: string
    }
&gt;(
  (
    {
      active,
      payload,
      className,
      indicator = &quot;dot&quot;,
      hideLabel = false,
      hideIndicator = false,
      label,
      labelFormatter,
      labelClassName,
      formatter,
      color,
      nameKey,
      labelKey,
    },
    ref
  ) =&gt; {
    const { config } = useChart()

    const tooltipLabel = React.useMemo(() =&gt; {
      if (hideLabel || !payload?.length) {
        return null
      }

      const [item] = payload
      const key = `${labelKey || item?.dataKey || item?.name || &quot;value&quot;}`
      const itemConfig = getPayloadConfigFromPayload(config, item, key)
      const value =
        !labelKey &amp;&amp; typeof label === &quot;string&quot;
          ? config[label as keyof typeof config]?.label || label
          : itemConfig?.label

      if (labelFormatter) {
        return (
          &lt;div className={cn(&quot;font-medium&quot;, labelClassName)}&gt;
            {labelFormatter(value, payload)}
          &lt;/div&gt;
        )
      }

      if (!value) {
        return null
      }

      return &lt;div className={cn(&quot;font-medium&quot;, labelClassName)}&gt;{value}&lt;/div&gt;
    }, [
      label,
      labelFormatter,
      payload,
      hideLabel,
      labelClassName,
      config,
      labelKey,
    ])

    if (!active || !payload?.length) {
      return null
    }

    const nestLabel = payload.length === 1 &amp;&amp; indicator !== &quot;dot&quot;

    return (
      &lt;div
        ref={ref}
        className={cn(
          &quot;grid min-w-[8rem] items-start gap-1.5 rounded-lg border border-border/50 bg-background px-2.5 py-1.5 text-xs shadow-xl&quot;,
          className
        )}
      &gt;
        {!nestLabel ? tooltipLabel : null}
        &lt;div className=&quot;grid gap-1.5&quot;&gt;
          {payload
            .filter((item) =&gt; item.type !== &quot;none&quot;)
            .map((item, index) =&gt; {
              const key = `${nameKey || item.name || item.dataKey || &quot;value&quot;}`
              const itemConfig = getPayloadConfigFromPayload(config, item, key)
              const indicatorColor = color || item.payload.fill || item.color

              return (
                &lt;div
                  key={item.dataKey}
                  className={cn(
                    &quot;flex w-full flex-wrap items-stretch gap-2 [&amp;&gt;svg]:h-2.5 [&amp;&gt;svg]:w-2.5 [&amp;&gt;svg]:text-muted-foreground&quot;,
                    indicator === &quot;dot&quot; &amp;&amp; &quot;items-center&quot;
                  )}
                &gt;
                  {formatter &amp;&amp; item?.value !== undefined &amp;&amp; item.name ? (
                    formatter(item.value, item.name, item, index, item.payload)
                  ) : (
                    &lt;&gt;
                      {itemConfig?.icon ? (
                        &lt;itemConfig.icon /&gt;
                      ) : (
                        !hideIndicator &amp;&amp; (
                          &lt;div
                            className={cn(
                              &quot;shrink-0 rounded-[2px] border-[--color-border] bg-[--color-bg]&quot;,
                              {
                                &quot;h-2.5 w-2.5&quot;: indicator === &quot;dot&quot;,
                                &quot;w-1&quot;: indicator === &quot;line&quot;,
                                &quot;w-0 border-[1.5px] border-dashed bg-transparent&quot;:
                                  indicator === &quot;dashed&quot;,
                                &quot;my-0.5&quot;: nestLabel &amp;&amp; indicator === &quot;dashed&quot;,
                              }
                            )}
                            style={
                              {
                                &quot;--color-bg&quot;: indicatorColor,
                                &quot;--color-border&quot;: indicatorColor,
                              } as React.CSSProperties
                            }
                          /&gt;
                        )
                      )}
                      &lt;div
                        className={cn(
                          &quot;flex flex-1 justify-between leading-none&quot;,
                          nestLabel ? &quot;items-end&quot; : &quot;items-center&quot;
                        )}
                      &gt;
                        &lt;div className=&quot;grid gap-1.5&quot;&gt;
                          {nestLabel ? tooltipLabel : null}
                          &lt;span className=&quot;text-muted-foreground&quot;&gt;
                            {itemConfig?.label || item.name}
                          &lt;/span&gt;
                        &lt;/div&gt;
                        {item.value &amp;&amp; (
                          &lt;span className=&quot;font-mono font-medium tabular-nums text-foreground&quot;&gt;
                            {item.value.toLocaleString()}
                          &lt;/span&gt;
                        )}
                      &lt;/div&gt;
                    &lt;/&gt;
                  )}
                &lt;/div&gt;
              )
            })}
        &lt;/div&gt;
      &lt;/div&gt;
    )
  }
)
ChartTooltipContent.displayName = &quot;ChartTooltip&quot;

const ChartLegend = RechartsPrimitive.Legend

const ChartLegendContent = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;div&quot;&gt; &amp;
    Pick&lt;RechartsPrimitive.LegendProps, &quot;payload&quot; | &quot;verticalAlign&quot;&gt; &amp; {
      hideIcon?: boolean
      nameKey?: string
    }
&gt;(
  (
    { className, hideIcon = false, payload, verticalAlign = &quot;bottom&quot;, nameKey },
    ref
  ) =&gt; {
    const { config } = useChart()

    if (!payload?.length) {
      return null
    }

    return (
      &lt;div
        ref={ref}
        className={cn(
          &quot;flex items-center justify-center gap-4&quot;,
          verticalAlign === &quot;top&quot; ? &quot;pb-3&quot; : &quot;pt-3&quot;,
          className
        )}
      &gt;
        {payload
          .filter((item) =&gt; item.type !== &quot;none&quot;)
          .map((item) =&gt; {
            const key = `${nameKey || item.dataKey || &quot;value&quot;}`
            const itemConfig = getPayloadConfigFromPayload(config, item, key)

            return (
              &lt;div
                key={item.value}
                className={cn(
                  &quot;flex items-center gap-1.5 [&amp;&gt;svg]:h-3 [&amp;&gt;svg]:w-3 [&amp;&gt;svg]:text-muted-foreground&quot;
                )}
              &gt;
                {itemConfig?.icon &amp;&amp; !hideIcon ? (
                  &lt;itemConfig.icon /&gt;
                ) : (
                  &lt;div
                    className=&quot;h-2 w-2 shrink-0 rounded-[2px]&quot;
                    style={{
                      backgroundColor: item.color,
                    }}
                  /&gt;
                )}
                {itemConfig?.label}
              &lt;/div&gt;
            )
          })}
      &lt;/div&gt;
    )
  }
)
ChartLegendContent.displayName = &quot;ChartLegend&quot;

// Helper to extract item config from a payload.
function getPayloadConfigFromPayload(
  config: ChartConfig,
  payload: unknown,
  key: string
) {
  if (typeof payload !== &quot;object&quot; || payload === null) {
    return undefined
  }

  const payloadPayload =
    &quot;payload&quot; in payload &amp;&amp;
    typeof payload.payload === &quot;object&quot; &amp;&amp;
    payload.payload !== null
      ? payload.payload
      : undefined

  let configLabelKey: string = key

  if (
    key in payload &amp;&amp;
    typeof payload[key as keyof typeof payload] === &quot;string&quot;
  ) {
    configLabelKey = payload[key as keyof typeof payload] as string
  } else if (
    payloadPayload &amp;&amp;
    key in payloadPayload &amp;&amp;
    typeof payloadPayload[key as keyof typeof payloadPayload] === &quot;string&quot;
  ) {
    configLabelKey = payloadPayload[
      key as keyof typeof payloadPayload
    ] as string
  }

  return configLabelKey in config
    ? config[configLabelKey]
    : config[key as keyof typeof config]
}

export {
  ChartContainer,
  ChartTooltip,
  ChartTooltipContent,
  ChartLegend,
  ChartLegendContent,
  ChartStyle,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_checkbox-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/checkbox.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_checkbox-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_checkbox-tsx">import * as React from &quot;react&quot;
import * as CheckboxPrimitive from &quot;@radix-ui/react-checkbox&quot;
import { Check } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;

const Checkbox = React.forwardRef&lt;
  React.ElementRef&lt;typeof CheckboxPrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof CheckboxPrimitive.Root&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;CheckboxPrimitive.Root
    ref={ref}
    className={cn(
      &quot;grid place-content-center peer h-4 w-4 shrink-0 rounded-sm border border-primary shadow focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring disabled:cursor-not-allowed disabled:opacity-50 data-[state=checked]:bg-primary data-[state=checked]:text-primary-foreground&quot;,
      className
    )}
    {...props}
  &gt;
    &lt;CheckboxPrimitive.Indicator
      className={cn(&quot;grid place-content-center text-current&quot;)}
    &gt;
      &lt;Check className=&quot;h-4 w-4&quot; /&gt;
    &lt;/CheckboxPrimitive.Indicator&gt;
  &lt;/CheckboxPrimitive.Root&gt;
))
Checkbox.displayName = CheckboxPrimitive.Root.displayName

export { Checkbox }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_collapsible-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/collapsible.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_collapsible-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_collapsible-tsx">&quot;use client&quot;

import * as CollapsiblePrimitive from &quot;@radix-ui/react-collapsible&quot;

const Collapsible = CollapsiblePrimitive.Root

const CollapsibleTrigger = CollapsiblePrimitive.CollapsibleTrigger

const CollapsibleContent = CollapsiblePrimitive.CollapsibleContent

export { Collapsible, CollapsibleTrigger, CollapsibleContent }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_command-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/command.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_command-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_command-tsx">&quot;use client&quot;

import * as React from &quot;react&quot;
import { type DialogProps } from &quot;@radix-ui/react-dialog&quot;
import { Command as CommandPrimitive } from &quot;cmdk&quot;
import { Search } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;
import { Dialog, DialogContent } from &quot;@/components/ui/dialog&quot;

const Command = React.forwardRef&lt;
  React.ElementRef&lt;typeof CommandPrimitive&gt;,
  React.ComponentPropsWithoutRef&lt;typeof CommandPrimitive&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;CommandPrimitive
    ref={ref}
    className={cn(
      &quot;flex h-full w-full flex-col overflow-hidden rounded-md bg-popover text-popover-foreground&quot;,
      className
    )}
    {...props}
  /&gt;
))
Command.displayName = CommandPrimitive.displayName

const CommandDialog = ({ children, ...props }: DialogProps) =&gt; {
  return (
    &lt;Dialog {...props}&gt;
      &lt;DialogContent className=&quot;overflow-hidden p-0&quot;&gt;
        &lt;Command className=&quot;[&amp;_[cmdk-group-heading]]:px-2 [&amp;_[cmdk-group-heading]]:font-medium [&amp;_[cmdk-group-heading]]:text-muted-foreground [&amp;_[cmdk-group]:not([hidden])_~[cmdk-group]]:pt-0 [&amp;_[cmdk-group]]:px-2 [&amp;_[cmdk-input-wrapper]_svg]:h-5 [&amp;_[cmdk-input-wrapper]_svg]:w-5 [&amp;_[cmdk-input]]:h-12 [&amp;_[cmdk-item]]:px-2 [&amp;_[cmdk-item]]:py-3 [&amp;_[cmdk-item]_svg]:h-5 [&amp;_[cmdk-item]_svg]:w-5&quot;&gt;
          {children}
        &lt;/Command&gt;
      &lt;/DialogContent&gt;
    &lt;/Dialog&gt;
  )
}

const CommandInput = React.forwardRef&lt;
  React.ElementRef&lt;typeof CommandPrimitive.Input&gt;,
  React.ComponentPropsWithoutRef&lt;typeof CommandPrimitive.Input&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div className=&quot;flex items-center border-b px-3&quot; cmdk-input-wrapper=&quot;&quot;&gt;
    &lt;Search className=&quot;mr-2 h-4 w-4 shrink-0 opacity-50&quot; /&gt;
    &lt;CommandPrimitive.Input
      ref={ref}
      className={cn(
        &quot;flex h-10 w-full rounded-md bg-transparent py-3 text-sm outline-none placeholder:text-muted-foreground disabled:cursor-not-allowed disabled:opacity-50&quot;,
        className
      )}
      {...props}
    /&gt;
  &lt;/div&gt;
))

CommandInput.displayName = CommandPrimitive.Input.displayName

const CommandList = React.forwardRef&lt;
  React.ElementRef&lt;typeof CommandPrimitive.List&gt;,
  React.ComponentPropsWithoutRef&lt;typeof CommandPrimitive.List&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;CommandPrimitive.List
    ref={ref}
    className={cn(&quot;max-h-[300px] overflow-y-auto overflow-x-hidden&quot;, className)}
    {...props}
  /&gt;
))

CommandList.displayName = CommandPrimitive.List.displayName

const CommandEmpty = React.forwardRef&lt;
  React.ElementRef&lt;typeof CommandPrimitive.Empty&gt;,
  React.ComponentPropsWithoutRef&lt;typeof CommandPrimitive.Empty&gt;
&gt;((props, ref) =&gt; (
  &lt;CommandPrimitive.Empty
    ref={ref}
    className=&quot;py-6 text-center text-sm&quot;
    {...props}
  /&gt;
))

CommandEmpty.displayName = CommandPrimitive.Empty.displayName

const CommandGroup = React.forwardRef&lt;
  React.ElementRef&lt;typeof CommandPrimitive.Group&gt;,
  React.ComponentPropsWithoutRef&lt;typeof CommandPrimitive.Group&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;CommandPrimitive.Group
    ref={ref}
    className={cn(
      &quot;overflow-hidden p-1 text-foreground [&amp;_[cmdk-group-heading]]:px-2 [&amp;_[cmdk-group-heading]]:py-1.5 [&amp;_[cmdk-group-heading]]:text-xs [&amp;_[cmdk-group-heading]]:font-medium [&amp;_[cmdk-group-heading]]:text-muted-foreground&quot;,
      className
    )}
    {...props}
  /&gt;
))

CommandGroup.displayName = CommandPrimitive.Group.displayName

const CommandSeparator = React.forwardRef&lt;
  React.ElementRef&lt;typeof CommandPrimitive.Separator&gt;,
  React.ComponentPropsWithoutRef&lt;typeof CommandPrimitive.Separator&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;CommandPrimitive.Separator
    ref={ref}
    className={cn(&quot;-mx-1 h-px bg-border&quot;, className)}
    {...props}
  /&gt;
))
CommandSeparator.displayName = CommandPrimitive.Separator.displayName

const CommandItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof CommandPrimitive.Item&gt;,
  React.ComponentPropsWithoutRef&lt;typeof CommandPrimitive.Item&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;CommandPrimitive.Item
    ref={ref}
    className={cn(
      &quot;relative flex cursor-default gap-2 select-none items-center rounded-sm px-2 py-1.5 text-sm outline-none data-[disabled=true]:pointer-events-none data-[selected=true]:bg-accent data-[selected=true]:text-accent-foreground data-[disabled=true]:opacity-50 [&amp;_svg]:pointer-events-none [&amp;_svg]:size-4 [&amp;_svg]:shrink-0&quot;,
      className
    )}
    {...props}
  /&gt;
))

CommandItem.displayName = CommandPrimitive.Item.displayName

const CommandShortcut = ({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLSpanElement&gt;) =&gt; {
  return (
    &lt;span
      className={cn(
        &quot;ml-auto text-xs tracking-widest text-muted-foreground&quot;,
        className
      )}
      {...props}
    /&gt;
  )
}
CommandShortcut.displayName = &quot;CommandShortcut&quot;

export {
  Command,
  CommandDialog,
  CommandInput,
  CommandList,
  CommandEmpty,
  CommandGroup,
  CommandItem,
  CommandShortcut,
  CommandSeparator,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_context-menu-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/context-menu.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_context-menu-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_context-menu-tsx">import * as React from &quot;react&quot;
import * as ContextMenuPrimitive from &quot;@radix-ui/react-context-menu&quot;
import { Check, ChevronRight, Circle } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;

const ContextMenu = ContextMenuPrimitive.Root

const ContextMenuTrigger = ContextMenuPrimitive.Trigger

const ContextMenuGroup = ContextMenuPrimitive.Group

const ContextMenuPortal = ContextMenuPrimitive.Portal

const ContextMenuSub = ContextMenuPrimitive.Sub

const ContextMenuRadioGroup = ContextMenuPrimitive.RadioGroup

const ContextMenuSubTrigger = React.forwardRef&lt;
  React.ElementRef&lt;typeof ContextMenuPrimitive.SubTrigger&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ContextMenuPrimitive.SubTrigger&gt; &amp; {
    inset?: boolean
  }
&gt;(({ className, inset, children, ...props }, ref) =&gt; (
  &lt;ContextMenuPrimitive.SubTrigger
    ref={ref}
    className={cn(
      &quot;flex cursor-default select-none items-center rounded-sm px-2 py-1.5 text-sm outline-none focus:bg-accent focus:text-accent-foreground data-[state=open]:bg-accent data-[state=open]:text-accent-foreground&quot;,
      inset &amp;&amp; &quot;pl-8&quot;,
      className
    )}
    {...props}
  &gt;
    {children}
    &lt;ChevronRight className=&quot;ml-auto h-4 w-4&quot; /&gt;
  &lt;/ContextMenuPrimitive.SubTrigger&gt;
))
ContextMenuSubTrigger.displayName = ContextMenuPrimitive.SubTrigger.displayName

const ContextMenuSubContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof ContextMenuPrimitive.SubContent&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ContextMenuPrimitive.SubContent&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;ContextMenuPrimitive.SubContent
    ref={ref}
    className={cn(
      &quot;z-50 min-w-[8rem] overflow-hidden rounded-md border bg-popover p-1 text-popover-foreground shadow-lg data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 origin-[--radix-context-menu-content-transform-origin]&quot;,
      className
    )}
    {...props}
  /&gt;
))
ContextMenuSubContent.displayName = ContextMenuPrimitive.SubContent.displayName

const ContextMenuContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof ContextMenuPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ContextMenuPrimitive.Content&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;ContextMenuPrimitive.Portal&gt;
    &lt;ContextMenuPrimitive.Content
      ref={ref}
      className={cn(
        &quot;z-50 max-h-[--radix-context-menu-content-available-height] min-w-[8rem] overflow-y-auto overflow-x-hidden rounded-md border bg-popover p-1 text-popover-foreground shadow-md data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 origin-[--radix-context-menu-content-transform-origin]&quot;,
        className
      )}
      {...props}
    /&gt;
  &lt;/ContextMenuPrimitive.Portal&gt;
))
ContextMenuContent.displayName = ContextMenuPrimitive.Content.displayName

const ContextMenuItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof ContextMenuPrimitive.Item&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ContextMenuPrimitive.Item&gt; &amp; {
    inset?: boolean
  }
&gt;(({ className, inset, ...props }, ref) =&gt; (
  &lt;ContextMenuPrimitive.Item
    ref={ref}
    className={cn(
      &quot;relative flex cursor-default select-none items-center rounded-sm px-2 py-1.5 text-sm outline-none focus:bg-accent focus:text-accent-foreground data-[disabled]:pointer-events-none data-[disabled]:opacity-50&quot;,
      inset &amp;&amp; &quot;pl-8&quot;,
      className
    )}
    {...props}
  /&gt;
))
ContextMenuItem.displayName = ContextMenuPrimitive.Item.displayName

const ContextMenuCheckboxItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof ContextMenuPrimitive.CheckboxItem&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ContextMenuPrimitive.CheckboxItem&gt;
&gt;(({ className, children, checked, ...props }, ref) =&gt; (
  &lt;ContextMenuPrimitive.CheckboxItem
    ref={ref}
    className={cn(
      &quot;relative flex cursor-default select-none items-center rounded-sm py-1.5 pl-8 pr-2 text-sm outline-none focus:bg-accent focus:text-accent-foreground data-[disabled]:pointer-events-none data-[disabled]:opacity-50&quot;,
      className
    )}
    checked={checked}
    {...props}
  &gt;
    &lt;span className=&quot;absolute left-2 flex h-3.5 w-3.5 items-center justify-center&quot;&gt;
      &lt;ContextMenuPrimitive.ItemIndicator&gt;
        &lt;Check className=&quot;h-4 w-4&quot; /&gt;
      &lt;/ContextMenuPrimitive.ItemIndicator&gt;
    &lt;/span&gt;
    {children}
  &lt;/ContextMenuPrimitive.CheckboxItem&gt;
))
ContextMenuCheckboxItem.displayName =
  ContextMenuPrimitive.CheckboxItem.displayName

const ContextMenuRadioItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof ContextMenuPrimitive.RadioItem&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ContextMenuPrimitive.RadioItem&gt;
&gt;(({ className, children, ...props }, ref) =&gt; (
  &lt;ContextMenuPrimitive.RadioItem
    ref={ref}
    className={cn(
      &quot;relative flex cursor-default select-none items-center rounded-sm py-1.5 pl-8 pr-2 text-sm outline-none focus:bg-accent focus:text-accent-foreground data-[disabled]:pointer-events-none data-[disabled]:opacity-50&quot;,
      className
    )}
    {...props}
  &gt;
    &lt;span className=&quot;absolute left-2 flex h-3.5 w-3.5 items-center justify-center&quot;&gt;
      &lt;ContextMenuPrimitive.ItemIndicator&gt;
        &lt;Circle className=&quot;h-4 w-4 fill-current&quot; /&gt;
      &lt;/ContextMenuPrimitive.ItemIndicator&gt;
    &lt;/span&gt;
    {children}
  &lt;/ContextMenuPrimitive.RadioItem&gt;
))
ContextMenuRadioItem.displayName = ContextMenuPrimitive.RadioItem.displayName

const ContextMenuLabel = React.forwardRef&lt;
  React.ElementRef&lt;typeof ContextMenuPrimitive.Label&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ContextMenuPrimitive.Label&gt; &amp; {
    inset?: boolean
  }
&gt;(({ className, inset, ...props }, ref) =&gt; (
  &lt;ContextMenuPrimitive.Label
    ref={ref}
    className={cn(
      &quot;px-2 py-1.5 text-sm font-semibold text-foreground&quot;,
      inset &amp;&amp; &quot;pl-8&quot;,
      className
    )}
    {...props}
  /&gt;
))
ContextMenuLabel.displayName = ContextMenuPrimitive.Label.displayName

const ContextMenuSeparator = React.forwardRef&lt;
  React.ElementRef&lt;typeof ContextMenuPrimitive.Separator&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ContextMenuPrimitive.Separator&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;ContextMenuPrimitive.Separator
    ref={ref}
    className={cn(&quot;-mx-1 my-1 h-px bg-border&quot;, className)}
    {...props}
  /&gt;
))
ContextMenuSeparator.displayName = ContextMenuPrimitive.Separator.displayName

const ContextMenuShortcut = ({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLSpanElement&gt;) =&gt; {
  return (
    &lt;span
      className={cn(
        &quot;ml-auto text-xs tracking-widest text-muted-foreground&quot;,
        className
      )}
      {...props}
    /&gt;
  )
}
ContextMenuShortcut.displayName = &quot;ContextMenuShortcut&quot;

export {
  ContextMenu,
  ContextMenuTrigger,
  ContextMenuContent,
  ContextMenuItem,
  ContextMenuCheckboxItem,
  ContextMenuRadioItem,
  ContextMenuLabel,
  ContextMenuSeparator,
  ContextMenuShortcut,
  ContextMenuGroup,
  ContextMenuPortal,
  ContextMenuSub,
  ContextMenuSubContent,
  ContextMenuSubTrigger,
  ContextMenuRadioGroup,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_dialog-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/dialog.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_dialog-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_dialog-tsx">&quot;use client&quot;

import * as React from &quot;react&quot;
import * as DialogPrimitive from &quot;@radix-ui/react-dialog&quot;
import { X } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;

const Dialog = DialogPrimitive.Root

const DialogTrigger = DialogPrimitive.Trigger

const DialogPortal = DialogPrimitive.Portal

const DialogClose = DialogPrimitive.Close

const DialogOverlay = React.forwardRef&lt;
  React.ElementRef&lt;typeof DialogPrimitive.Overlay&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DialogPrimitive.Overlay&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;DialogPrimitive.Overlay
    ref={ref}
    className={cn(
      &quot;fixed inset-0 z-50 bg-black/80  data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0&quot;,
      className
    )}
    {...props}
  /&gt;
))
DialogOverlay.displayName = DialogPrimitive.Overlay.displayName

const DialogContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof DialogPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DialogPrimitive.Content&gt;
&gt;(({ className, children, ...props }, ref) =&gt; (
  &lt;DialogPortal&gt;
    &lt;DialogOverlay /&gt;
    &lt;DialogPrimitive.Content
      ref={ref}
      className={cn(
        &quot;fixed left-[50%] top-[50%] z-50 grid w-full max-w-lg translate-x-[-50%] translate-y-[-50%] gap-4 border bg-background p-6 shadow-lg duration-200 data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[state=closed]:slide-out-to-left-1/2 data-[state=closed]:slide-out-to-top-[48%] data-[state=open]:slide-in-from-left-1/2 data-[state=open]:slide-in-from-top-[48%] sm:rounded-lg&quot;,
        className
      )}
      {...props}
    &gt;
      {children}
      &lt;DialogPrimitive.Close className=&quot;absolute right-4 top-4 rounded-sm opacity-70 ring-offset-background transition-opacity hover:opacity-100 focus:outline-none focus:ring-2 focus:ring-ring focus:ring-offset-2 disabled:pointer-events-none data-[state=open]:bg-accent data-[state=open]:text-muted-foreground&quot;&gt;
        &lt;X className=&quot;h-4 w-4&quot; /&gt;
        &lt;span className=&quot;sr-only&quot;&gt;Close&lt;/span&gt;
      &lt;/DialogPrimitive.Close&gt;
    &lt;/DialogPrimitive.Content&gt;
  &lt;/DialogPortal&gt;
))
DialogContent.displayName = DialogPrimitive.Content.displayName

const DialogHeader = ({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLDivElement&gt;) =&gt; (
  &lt;div
    className={cn(
      &quot;flex flex-col space-y-1.5 text-center sm:text-left&quot;,
      className
    )}
    {...props}
  /&gt;
)
DialogHeader.displayName = &quot;DialogHeader&quot;

const DialogFooter = ({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLDivElement&gt;) =&gt; (
  &lt;div
    className={cn(
      &quot;flex flex-col-reverse sm:flex-row sm:justify-end sm:space-x-2&quot;,
      className
    )}
    {...props}
  /&gt;
)
DialogFooter.displayName = &quot;DialogFooter&quot;

const DialogTitle = React.forwardRef&lt;
  React.ElementRef&lt;typeof DialogPrimitive.Title&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DialogPrimitive.Title&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;DialogPrimitive.Title
    ref={ref}
    className={cn(
      &quot;text-lg font-semibold leading-none tracking-tight&quot;,
      className
    )}
    {...props}
  /&gt;
))
DialogTitle.displayName = DialogPrimitive.Title.displayName

const DialogDescription = React.forwardRef&lt;
  React.ElementRef&lt;typeof DialogPrimitive.Description&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DialogPrimitive.Description&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;DialogPrimitive.Description
    ref={ref}
    className={cn(&quot;text-sm text-muted-foreground&quot;, className)}
    {...props}
  /&gt;
))
DialogDescription.displayName = DialogPrimitive.Description.displayName

export {
  Dialog,
  DialogPortal,
  DialogOverlay,
  DialogTrigger,
  DialogClose,
  DialogContent,
  DialogHeader,
  DialogFooter,
  DialogTitle,
  DialogDescription,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_drawer-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/drawer.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_drawer-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_drawer-tsx">import * as React from &quot;react&quot;
import { Drawer as DrawerPrimitive } from &quot;vaul&quot;

import { cn } from &quot;@/lib/utils&quot;

const Drawer = ({
  shouldScaleBackground = true,
  ...props
}: React.ComponentProps&lt;typeof DrawerPrimitive.Root&gt;) =&gt; (
  &lt;DrawerPrimitive.Root
    shouldScaleBackground={shouldScaleBackground}
    {...props}
  /&gt;
)
Drawer.displayName = &quot;Drawer&quot;

const DrawerTrigger = DrawerPrimitive.Trigger

const DrawerPortal = DrawerPrimitive.Portal

const DrawerClose = DrawerPrimitive.Close

const DrawerOverlay = React.forwardRef&lt;
  React.ElementRef&lt;typeof DrawerPrimitive.Overlay&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DrawerPrimitive.Overlay&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;DrawerPrimitive.Overlay
    ref={ref}
    className={cn(&quot;fixed inset-0 z-50 bg-black/80&quot;, className)}
    {...props}
  /&gt;
))
DrawerOverlay.displayName = DrawerPrimitive.Overlay.displayName

const DrawerContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof DrawerPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DrawerPrimitive.Content&gt;
&gt;(({ className, children, ...props }, ref) =&gt; (
  &lt;DrawerPortal&gt;
    &lt;DrawerOverlay /&gt;
    &lt;DrawerPrimitive.Content
      ref={ref}
      className={cn(
        &quot;fixed inset-x-0 bottom-0 z-50 mt-24 flex h-auto flex-col rounded-t-[10px] border bg-background&quot;,
        className
      )}
      {...props}
    &gt;
      &lt;div className=&quot;mx-auto mt-4 h-2 w-[100px] rounded-full bg-muted&quot; /&gt;
      {children}
    &lt;/DrawerPrimitive.Content&gt;
  &lt;/DrawerPortal&gt;
))
DrawerContent.displayName = &quot;DrawerContent&quot;

const DrawerHeader = ({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLDivElement&gt;) =&gt; (
  &lt;div
    className={cn(&quot;grid gap-1.5 p-4 text-center sm:text-left&quot;, className)}
    {...props}
  /&gt;
)
DrawerHeader.displayName = &quot;DrawerHeader&quot;

const DrawerFooter = ({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLDivElement&gt;) =&gt; (
  &lt;div
    className={cn(&quot;mt-auto flex flex-col gap-2 p-4&quot;, className)}
    {...props}
  /&gt;
)
DrawerFooter.displayName = &quot;DrawerFooter&quot;

const DrawerTitle = React.forwardRef&lt;
  React.ElementRef&lt;typeof DrawerPrimitive.Title&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DrawerPrimitive.Title&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;DrawerPrimitive.Title
    ref={ref}
    className={cn(
      &quot;text-lg font-semibold leading-none tracking-tight&quot;,
      className
    )}
    {...props}
  /&gt;
))
DrawerTitle.displayName = DrawerPrimitive.Title.displayName

const DrawerDescription = React.forwardRef&lt;
  React.ElementRef&lt;typeof DrawerPrimitive.Description&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DrawerPrimitive.Description&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;DrawerPrimitive.Description
    ref={ref}
    className={cn(&quot;text-sm text-muted-foreground&quot;, className)}
    {...props}
  /&gt;
))
DrawerDescription.displayName = DrawerPrimitive.Description.displayName

export {
  Drawer,
  DrawerPortal,
  DrawerOverlay,
  DrawerTrigger,
  DrawerClose,
  DrawerContent,
  DrawerHeader,
  DrawerFooter,
  DrawerTitle,
  DrawerDescription,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_dropdown-menu-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/dropdown-menu.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_dropdown-menu-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_dropdown-menu-tsx">&quot;use client&quot;

import * as React from &quot;react&quot;
import * as DropdownMenuPrimitive from &quot;@radix-ui/react-dropdown-menu&quot;
import { Check, ChevronRight, Circle } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;

const DropdownMenu = DropdownMenuPrimitive.Root

const DropdownMenuTrigger = DropdownMenuPrimitive.Trigger

const DropdownMenuGroup = DropdownMenuPrimitive.Group

const DropdownMenuPortal = DropdownMenuPrimitive.Portal

const DropdownMenuSub = DropdownMenuPrimitive.Sub

const DropdownMenuRadioGroup = DropdownMenuPrimitive.RadioGroup

const DropdownMenuSubTrigger = React.forwardRef&lt;
  React.ElementRef&lt;typeof DropdownMenuPrimitive.SubTrigger&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DropdownMenuPrimitive.SubTrigger&gt; &amp; {
    inset?: boolean
  }
&gt;(({ className, inset, children, ...props }, ref) =&gt; (
  &lt;DropdownMenuPrimitive.SubTrigger
    ref={ref}
    className={cn(
      &quot;flex cursor-default select-none items-center gap-2 rounded-sm px-2 py-1.5 text-sm outline-none focus:bg-accent data-[state=open]:bg-accent [&amp;_svg]:pointer-events-none [&amp;_svg]:size-4 [&amp;_svg]:shrink-0&quot;,
      inset &amp;&amp; &quot;pl-8&quot;,
      className
    )}
    {...props}
  &gt;
    {children}
    &lt;ChevronRight className=&quot;ml-auto&quot; /&gt;
  &lt;/DropdownMenuPrimitive.SubTrigger&gt;
))
DropdownMenuSubTrigger.displayName =
  DropdownMenuPrimitive.SubTrigger.displayName

const DropdownMenuSubContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof DropdownMenuPrimitive.SubContent&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DropdownMenuPrimitive.SubContent&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;DropdownMenuPrimitive.SubContent
    ref={ref}
    className={cn(
      &quot;z-50 min-w-[8rem] overflow-hidden rounded-md border bg-popover p-1 text-popover-foreground shadow-lg data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 origin-[--radix-dropdown-menu-content-transform-origin]&quot;,
      className
    )}
    {...props}
  /&gt;
))
DropdownMenuSubContent.displayName =
  DropdownMenuPrimitive.SubContent.displayName

const DropdownMenuContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof DropdownMenuPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DropdownMenuPrimitive.Content&gt;
&gt;(({ className, sideOffset = 4, ...props }, ref) =&gt; (
  &lt;DropdownMenuPrimitive.Portal&gt;
    &lt;DropdownMenuPrimitive.Content
      ref={ref}
      sideOffset={sideOffset}
      className={cn(
        &quot;z-50 max-h-[var(--radix-dropdown-menu-content-available-height)] min-w-[8rem] overflow-y-auto overflow-x-hidden rounded-md border bg-popover p-1 text-popover-foreground shadow-md&quot;,
        &quot;data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 origin-[--radix-dropdown-menu-content-transform-origin]&quot;,
        className
      )}
      {...props}
    /&gt;
  &lt;/DropdownMenuPrimitive.Portal&gt;
))
DropdownMenuContent.displayName = DropdownMenuPrimitive.Content.displayName

const DropdownMenuItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof DropdownMenuPrimitive.Item&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DropdownMenuPrimitive.Item&gt; &amp; {
    inset?: boolean
  }
&gt;(({ className, inset, ...props }, ref) =&gt; (
  &lt;DropdownMenuPrimitive.Item
    ref={ref}
    className={cn(
      &quot;relative flex cursor-default select-none items-center gap-2 rounded-sm px-2 py-1.5 text-sm outline-none transition-colors focus:bg-accent focus:text-accent-foreground data-[disabled]:pointer-events-none data-[disabled]:opacity-50 [&amp;&gt;svg]:size-4 [&amp;&gt;svg]:shrink-0&quot;,
      inset &amp;&amp; &quot;pl-8&quot;,
      className
    )}
    {...props}
  /&gt;
))
DropdownMenuItem.displayName = DropdownMenuPrimitive.Item.displayName

const DropdownMenuCheckboxItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof DropdownMenuPrimitive.CheckboxItem&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DropdownMenuPrimitive.CheckboxItem&gt;
&gt;(({ className, children, checked, ...props }, ref) =&gt; (
  &lt;DropdownMenuPrimitive.CheckboxItem
    ref={ref}
    className={cn(
      &quot;relative flex cursor-default select-none items-center rounded-sm py-1.5 pl-8 pr-2 text-sm outline-none transition-colors focus:bg-accent focus:text-accent-foreground data-[disabled]:pointer-events-none data-[disabled]:opacity-50&quot;,
      className
    )}
    checked={checked}
    {...props}
  &gt;
    &lt;span className=&quot;absolute left-2 flex h-3.5 w-3.5 items-center justify-center&quot;&gt;
      &lt;DropdownMenuPrimitive.ItemIndicator&gt;
        &lt;Check className=&quot;h-4 w-4&quot; /&gt;
      &lt;/DropdownMenuPrimitive.ItemIndicator&gt;
    &lt;/span&gt;
    {children}
  &lt;/DropdownMenuPrimitive.CheckboxItem&gt;
))
DropdownMenuCheckboxItem.displayName =
  DropdownMenuPrimitive.CheckboxItem.displayName

const DropdownMenuRadioItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof DropdownMenuPrimitive.RadioItem&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DropdownMenuPrimitive.RadioItem&gt;
&gt;(({ className, children, ...props }, ref) =&gt; (
  &lt;DropdownMenuPrimitive.RadioItem
    ref={ref}
    className={cn(
      &quot;relative flex cursor-default select-none items-center rounded-sm py-1.5 pl-8 pr-2 text-sm outline-none transition-colors focus:bg-accent focus:text-accent-foreground data-[disabled]:pointer-events-none data-[disabled]:opacity-50&quot;,
      className
    )}
    {...props}
  &gt;
    &lt;span className=&quot;absolute left-2 flex h-3.5 w-3.5 items-center justify-center&quot;&gt;
      &lt;DropdownMenuPrimitive.ItemIndicator&gt;
        &lt;Circle className=&quot;h-2 w-2 fill-current&quot; /&gt;
      &lt;/DropdownMenuPrimitive.ItemIndicator&gt;
    &lt;/span&gt;
    {children}
  &lt;/DropdownMenuPrimitive.RadioItem&gt;
))
DropdownMenuRadioItem.displayName = DropdownMenuPrimitive.RadioItem.displayName

const DropdownMenuLabel = React.forwardRef&lt;
  React.ElementRef&lt;typeof DropdownMenuPrimitive.Label&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DropdownMenuPrimitive.Label&gt; &amp; {
    inset?: boolean
  }
&gt;(({ className, inset, ...props }, ref) =&gt; (
  &lt;DropdownMenuPrimitive.Label
    ref={ref}
    className={cn(
      &quot;px-2 py-1.5 text-sm font-semibold&quot;,
      inset &amp;&amp; &quot;pl-8&quot;,
      className
    )}
    {...props}
  /&gt;
))
DropdownMenuLabel.displayName = DropdownMenuPrimitive.Label.displayName

const DropdownMenuSeparator = React.forwardRef&lt;
  React.ElementRef&lt;typeof DropdownMenuPrimitive.Separator&gt;,
  React.ComponentPropsWithoutRef&lt;typeof DropdownMenuPrimitive.Separator&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;DropdownMenuPrimitive.Separator
    ref={ref}
    className={cn(&quot;-mx-1 my-1 h-px bg-muted&quot;, className)}
    {...props}
  /&gt;
))
DropdownMenuSeparator.displayName = DropdownMenuPrimitive.Separator.displayName

const DropdownMenuShortcut = ({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLSpanElement&gt;) =&gt; {
  return (
    &lt;span
      className={cn(&quot;ml-auto text-xs tracking-widest opacity-60&quot;, className)}
      {...props}
    /&gt;
  )
}
DropdownMenuShortcut.displayName = &quot;DropdownMenuShortcut&quot;

export {
  DropdownMenu,
  DropdownMenuTrigger,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuCheckboxItem,
  DropdownMenuRadioItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuShortcut,
  DropdownMenuGroup,
  DropdownMenuPortal,
  DropdownMenuSub,
  DropdownMenuSubContent,
  DropdownMenuSubTrigger,
  DropdownMenuRadioGroup,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_form-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/form.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_form-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_form-tsx">import * as React from &quot;react&quot;
import * as LabelPrimitive from &quot;@radix-ui/react-label&quot;
import { Slot } from &quot;@radix-ui/react-slot&quot;
import {
  Controller,
  FormProvider,
  useFormContext,
  type ControllerProps,
  type FieldPath,
  type FieldValues,
} from &quot;react-hook-form&quot;

import { cn } from &quot;@/lib/utils&quot;
import { Label } from &quot;@/components/ui/label&quot;

const Form = FormProvider

type FormFieldContextValue&lt;
  TFieldValues extends FieldValues = FieldValues,
  TName extends FieldPath&lt;TFieldValues&gt; = FieldPath&lt;TFieldValues&gt;
&gt; = {
  name: TName
}

const FormFieldContext = React.createContext&lt;FormFieldContextValue | null&gt;(null)

const FormField = &lt;
  TFieldValues extends FieldValues = FieldValues,
  TName extends FieldPath&lt;TFieldValues&gt; = FieldPath&lt;TFieldValues&gt;
&gt;({
  ...props
}: ControllerProps&lt;TFieldValues, TName&gt;) =&gt; {
  return (
    &lt;FormFieldContext.Provider value={{ name: props.name }}&gt;
      &lt;Controller {...props} /&gt;
    &lt;/FormFieldContext.Provider&gt;
  )
}

const useFormField = () =&gt; {
  const fieldContext = React.useContext(FormFieldContext)
  const itemContext = React.useContext(FormItemContext)
  const { getFieldState, formState } = useFormContext()

  if (!fieldContext) {
    throw new Error(&quot;useFormField should be used within &lt;FormField&gt;&quot;)
  }

  if (!itemContext) {
    throw new Error(&quot;useFormField should be used within &lt;FormItem&gt;&quot;)
  }

  const fieldState = getFieldState(fieldContext.name, formState)

  const { id } = itemContext

  return {
    id,
    name: fieldContext.name,
    formItemId: `${id}-form-item`,
    formDescriptionId: `${id}-form-item-description`,
    formMessageId: `${id}-form-item-message`,
    ...fieldState,
  }
}

type FormItemContextValue = {
  id: string
}

const FormItemContext = React.createContext&lt;FormItemContextValue | null&gt;(null)

const FormItem = React.forwardRef&lt;
  HTMLDivElement,
  React.HTMLAttributes&lt;HTMLDivElement&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  const id = React.useId()

  return (
    &lt;FormItemContext.Provider value={{ id }}&gt;
      &lt;div ref={ref} className={cn(&quot;space-y-2&quot;, className)} {...props} /&gt;
    &lt;/FormItemContext.Provider&gt;
  )
})
FormItem.displayName = &quot;FormItem&quot;

const FormLabel = React.forwardRef&lt;
  React.ElementRef&lt;typeof LabelPrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof LabelPrimitive.Root&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  const { error, formItemId } = useFormField()

  return (
    &lt;Label
      ref={ref}
      className={cn(error &amp;&amp; &quot;text-destructive&quot;, className)}
      htmlFor={formItemId}
      {...props}
    /&gt;
  )
})
FormLabel.displayName = &quot;FormLabel&quot;

const FormControl = React.forwardRef&lt;
  React.ElementRef&lt;typeof Slot&gt;,
  React.ComponentPropsWithoutRef&lt;typeof Slot&gt;
&gt;(({ ...props }, ref) =&gt; {
  const { error, formItemId, formDescriptionId, formMessageId } = useFormField()

  return (
    &lt;Slot
      ref={ref}
      id={formItemId}
      aria-describedby={
        !error
          ? `${formDescriptionId}`
          : `${formDescriptionId} ${formMessageId}`
      }
      aria-invalid={!!error}
      {...props}
    /&gt;
  )
})
FormControl.displayName = &quot;FormControl&quot;

const FormDescription = React.forwardRef&lt;
  HTMLParagraphElement,
  React.HTMLAttributes&lt;HTMLParagraphElement&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  const { formDescriptionId } = useFormField()

  return (
    &lt;p
      ref={ref}
      id={formDescriptionId}
      className={cn(&quot;text-[0.8rem] text-muted-foreground&quot;, className)}
      {...props}
    /&gt;
  )
})
FormDescription.displayName = &quot;FormDescription&quot;

const FormMessage = React.forwardRef&lt;
  HTMLParagraphElement,
  React.HTMLAttributes&lt;HTMLParagraphElement&gt;
&gt;(({ className, children, ...props }, ref) =&gt; {
  const { error, formMessageId } = useFormField()
  const body = error ? String(error?.message ?? &quot;&quot;) : children

  if (!body) {
    return null
  }

  return (
    &lt;p
      ref={ref}
      id={formMessageId}
      className={cn(&quot;text-[0.8rem] font-medium text-destructive&quot;, className)}
      {...props}
    &gt;
      {body}
    &lt;/p&gt;
  )
})
FormMessage.displayName = &quot;FormMessage&quot;

export {
  useFormField,
  Form,
  FormItem,
  FormLabel,
  FormControl,
  FormDescription,
  FormMessage,
  FormField,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_hover-card-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/hover-card.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_hover-card-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_hover-card-tsx">import * as React from &quot;react&quot;
import * as HoverCardPrimitive from &quot;@radix-ui/react-hover-card&quot;

import { cn } from &quot;@/lib/utils&quot;

const HoverCard = HoverCardPrimitive.Root

const HoverCardTrigger = HoverCardPrimitive.Trigger

const HoverCardContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof HoverCardPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof HoverCardPrimitive.Content&gt;
&gt;(({ className, align = &quot;center&quot;, sideOffset = 4, ...props }, ref) =&gt; (
  &lt;HoverCardPrimitive.Content
    ref={ref}
    align={align}
    sideOffset={sideOffset}
    className={cn(
      &quot;z-50 w-64 rounded-md border bg-popover p-4 text-popover-foreground shadow-md outline-none data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 origin-[--radix-hover-card-content-transform-origin]&quot;,
      className
    )}
    {...props}
  /&gt;
))
HoverCardContent.displayName = HoverCardPrimitive.Content.displayName

export { HoverCard, HoverCardTrigger, HoverCardContent }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_input-otp-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/input-otp.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_input-otp-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_input-otp-tsx">&quot;use client&quot;

import * as React from &quot;react&quot;
import { OTPInput, OTPInputContext } from &quot;input-otp&quot;
import { Minus } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;

const InputOTP = React.forwardRef&lt;
  React.ElementRef&lt;typeof OTPInput&gt;,
  React.ComponentPropsWithoutRef&lt;typeof OTPInput&gt;
&gt;(({ className, containerClassName, ...props }, ref) =&gt; (
  &lt;OTPInput
    ref={ref}
    containerClassName={cn(
      &quot;flex items-center gap-2 has-[:disabled]:opacity-50&quot;,
      containerClassName
    )}
    className={cn(&quot;disabled:cursor-not-allowed&quot;, className)}
    {...props}
  /&gt;
))
InputOTP.displayName = &quot;InputOTP&quot;

const InputOTPGroup = React.forwardRef&lt;
  React.ElementRef&lt;&quot;div&quot;&gt;,
  React.ComponentPropsWithoutRef&lt;&quot;div&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div ref={ref} className={cn(&quot;flex items-center&quot;, className)} {...props} /&gt;
))
InputOTPGroup.displayName = &quot;InputOTPGroup&quot;

const InputOTPSlot = React.forwardRef&lt;
  React.ElementRef&lt;&quot;div&quot;&gt;,
  React.ComponentPropsWithoutRef&lt;&quot;div&quot;&gt; &amp; { index: number }
&gt;(({ index, className, ...props }, ref) =&gt; {
  const inputOTPContext = React.useContext(OTPInputContext)
  const { char, hasFakeCaret, isActive } = inputOTPContext.slots[index]

  return (
    &lt;div
      ref={ref}
      className={cn(
        &quot;relative flex h-9 w-9 items-center justify-center border-y border-r border-input text-sm shadow-sm transition-all first:rounded-l-md first:border-l last:rounded-r-md&quot;,
        isActive &amp;&amp; &quot;z-10 ring-1 ring-ring&quot;,
        className
      )}
      {...props}
    &gt;
      {char}
      {hasFakeCaret &amp;&amp; (
        &lt;div className=&quot;pointer-events-none absolute inset-0 flex items-center justify-center&quot;&gt;
          &lt;div className=&quot;h-4 w-px animate-caret-blink bg-foreground duration-1000&quot; /&gt;
        &lt;/div&gt;
      )}
    &lt;/div&gt;
  )
})
InputOTPSlot.displayName = &quot;InputOTPSlot&quot;

const InputOTPSeparator = React.forwardRef&lt;
  React.ElementRef&lt;&quot;div&quot;&gt;,
  React.ComponentPropsWithoutRef&lt;&quot;div&quot;&gt;
&gt;(({ ...props }, ref) =&gt; (
  &lt;div ref={ref} role=&quot;separator&quot; {...props}&gt;
    &lt;Minus /&gt;
  &lt;/div&gt;
))
InputOTPSeparator.displayName = &quot;InputOTPSeparator&quot;

export { InputOTP, InputOTPGroup, InputOTPSlot, InputOTPSeparator }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_input-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/input.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_input-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_input-tsx">import * as React from &quot;react&quot;

import { cn } from &quot;@/lib/utils&quot;

const Input = React.forwardRef&lt;HTMLInputElement, React.ComponentProps&lt;&quot;input&quot;&gt;&gt;(
  ({ className, type, ...props }, ref) =&gt; {
    return (
      &lt;input
        type={type}
        className={cn(
          &quot;flex h-9 w-full rounded-md border border-input bg-transparent px-3 py-1 text-base shadow-sm transition-colors file:border-0 file:bg-transparent file:text-sm file:font-medium file:text-foreground placeholder:text-muted-foreground focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring disabled:cursor-not-allowed disabled:opacity-50 md:text-sm&quot;,
          className
        )}
        ref={ref}
        {...props}
      /&gt;
    )
  }
)
Input.displayName = &quot;Input&quot;

export { Input }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_label-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/label.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_label-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_label-tsx">import * as React from &quot;react&quot;
import * as LabelPrimitive from &quot;@radix-ui/react-label&quot;
import { cva, type VariantProps } from &quot;class-variance-authority&quot;

import { cn } from &quot;@/lib/utils&quot;

const labelVariants = cva(
  &quot;text-sm font-medium leading-none peer-disabled:cursor-not-allowed peer-disabled:opacity-70&quot;
)

const Label = React.forwardRef&lt;
  React.ElementRef&lt;typeof LabelPrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof LabelPrimitive.Root&gt; &amp;
    VariantProps&lt;typeof labelVariants&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;LabelPrimitive.Root
    ref={ref}
    className={cn(labelVariants(), className)}
    {...props}
  /&gt;
))
Label.displayName = LabelPrimitive.Root.displayName

export { Label }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_menubar-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/menubar.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_menubar-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_menubar-tsx">&quot;use client&quot;

import * as React from &quot;react&quot;
import * as MenubarPrimitive from &quot;@radix-ui/react-menubar&quot;
import { Check, ChevronRight, Circle } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;

function MenubarMenu({
  ...props
}: React.ComponentProps&lt;typeof MenubarPrimitive.Menu&gt;) {
  return &lt;MenubarPrimitive.Menu {...props} /&gt;
}

function MenubarGroup({
  ...props
}: React.ComponentProps&lt;typeof MenubarPrimitive.Group&gt;) {
  return &lt;MenubarPrimitive.Group {...props} /&gt;
}

function MenubarPortal({
  ...props
}: React.ComponentProps&lt;typeof MenubarPrimitive.Portal&gt;) {
  return &lt;MenubarPrimitive.Portal {...props} /&gt;
}

function MenubarRadioGroup({
  ...props
}: React.ComponentProps&lt;typeof MenubarPrimitive.RadioGroup&gt;) {
  return &lt;MenubarPrimitive.RadioGroup {...props} /&gt;
}

function MenubarSub({
  ...props
}: React.ComponentProps&lt;typeof MenubarPrimitive.Sub&gt;) {
  return &lt;MenubarPrimitive.Sub data-slot=&quot;menubar-sub&quot; {...props} /&gt;
}

const Menubar = React.forwardRef&lt;
  React.ElementRef&lt;typeof MenubarPrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof MenubarPrimitive.Root&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;MenubarPrimitive.Root
    ref={ref}
    className={cn(
      &quot;flex h-9 items-center space-x-1 rounded-md border bg-background p-1 shadow-sm&quot;,
      className
    )}
    {...props}
  /&gt;
))
Menubar.displayName = MenubarPrimitive.Root.displayName

const MenubarTrigger = React.forwardRef&lt;
  React.ElementRef&lt;typeof MenubarPrimitive.Trigger&gt;,
  React.ComponentPropsWithoutRef&lt;typeof MenubarPrimitive.Trigger&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;MenubarPrimitive.Trigger
    ref={ref}
    className={cn(
      &quot;flex cursor-default select-none items-center rounded-sm px-3 py-1 text-sm font-medium outline-none focus:bg-accent focus:text-accent-foreground data-[state=open]:bg-accent data-[state=open]:text-accent-foreground&quot;,
      className
    )}
    {...props}
  /&gt;
))
MenubarTrigger.displayName = MenubarPrimitive.Trigger.displayName

const MenubarSubTrigger = React.forwardRef&lt;
  React.ElementRef&lt;typeof MenubarPrimitive.SubTrigger&gt;,
  React.ComponentPropsWithoutRef&lt;typeof MenubarPrimitive.SubTrigger&gt; &amp; {
    inset?: boolean
  }
&gt;(({ className, inset, children, ...props }, ref) =&gt; (
  &lt;MenubarPrimitive.SubTrigger
    ref={ref}
    className={cn(
      &quot;flex cursor-default select-none items-center rounded-sm px-2 py-1.5 text-sm outline-none focus:bg-accent focus:text-accent-foreground data-[state=open]:bg-accent data-[state=open]:text-accent-foreground&quot;,
      inset &amp;&amp; &quot;pl-8&quot;,
      className
    )}
    {...props}
  &gt;
    {children}
    &lt;ChevronRight className=&quot;ml-auto h-4 w-4&quot; /&gt;
  &lt;/MenubarPrimitive.SubTrigger&gt;
))
MenubarSubTrigger.displayName = MenubarPrimitive.SubTrigger.displayName

const MenubarSubContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof MenubarPrimitive.SubContent&gt;,
  React.ComponentPropsWithoutRef&lt;typeof MenubarPrimitive.SubContent&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;MenubarPrimitive.SubContent
    ref={ref}
    className={cn(
      &quot;z-50 min-w-[8rem] overflow-hidden rounded-md border bg-popover p-1 text-popover-foreground shadow-lg data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 origin-[--radix-menubar-content-transform-origin]&quot;,
      className
    )}
    {...props}
  /&gt;
))
MenubarSubContent.displayName = MenubarPrimitive.SubContent.displayName

const MenubarContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof MenubarPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof MenubarPrimitive.Content&gt;
&gt;(
  (
    { className, align = &quot;start&quot;, alignOffset = -4, sideOffset = 8, ...props },
    ref
  ) =&gt; (
    &lt;MenubarPrimitive.Portal&gt;
      &lt;MenubarPrimitive.Content
        ref={ref}
        align={align}
        alignOffset={alignOffset}
        sideOffset={sideOffset}
        className={cn(
          &quot;z-50 min-w-[12rem] overflow-hidden rounded-md border bg-popover p-1 text-popover-foreground shadow-md data-[state=open]:animate-in data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 origin-[--radix-menubar-content-transform-origin]&quot;,
          className
        )}
        {...props}
      /&gt;
    &lt;/MenubarPrimitive.Portal&gt;
  )
)
MenubarContent.displayName = MenubarPrimitive.Content.displayName

const MenubarItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof MenubarPrimitive.Item&gt;,
  React.ComponentPropsWithoutRef&lt;typeof MenubarPrimitive.Item&gt; &amp; {
    inset?: boolean
  }
&gt;(({ className, inset, ...props }, ref) =&gt; (
  &lt;MenubarPrimitive.Item
    ref={ref}
    className={cn(
      &quot;relative flex cursor-default select-none items-center rounded-sm px-2 py-1.5 text-sm outline-none focus:bg-accent focus:text-accent-foreground data-[disabled]:pointer-events-none data-[disabled]:opacity-50&quot;,
      inset &amp;&amp; &quot;pl-8&quot;,
      className
    )}
    {...props}
  /&gt;
))
MenubarItem.displayName = MenubarPrimitive.Item.displayName

const MenubarCheckboxItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof MenubarPrimitive.CheckboxItem&gt;,
  React.ComponentPropsWithoutRef&lt;typeof MenubarPrimitive.CheckboxItem&gt;
&gt;(({ className, children, checked, ...props }, ref) =&gt; (
  &lt;MenubarPrimitive.CheckboxItem
    ref={ref}
    className={cn(
      &quot;relative flex cursor-default select-none items-center rounded-sm py-1.5 pl-8 pr-2 text-sm outline-none focus:bg-accent focus:text-accent-foreground data-[disabled]:pointer-events-none data-[disabled]:opacity-50&quot;,
      className
    )}
    checked={checked}
    {...props}
  &gt;
    &lt;span className=&quot;absolute left-2 flex h-3.5 w-3.5 items-center justify-center&quot;&gt;
      &lt;MenubarPrimitive.ItemIndicator&gt;
        &lt;Check className=&quot;h-4 w-4&quot; /&gt;
      &lt;/MenubarPrimitive.ItemIndicator&gt;
    &lt;/span&gt;
    {children}
  &lt;/MenubarPrimitive.CheckboxItem&gt;
))
MenubarCheckboxItem.displayName = MenubarPrimitive.CheckboxItem.displayName

const MenubarRadioItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof MenubarPrimitive.RadioItem&gt;,
  React.ComponentPropsWithoutRef&lt;typeof MenubarPrimitive.RadioItem&gt;
&gt;(({ className, children, ...props }, ref) =&gt; (
  &lt;MenubarPrimitive.RadioItem
    ref={ref}
    className={cn(
      &quot;relative flex cursor-default select-none items-center rounded-sm py-1.5 pl-8 pr-2 text-sm outline-none focus:bg-accent focus:text-accent-foreground data-[disabled]:pointer-events-none data-[disabled]:opacity-50&quot;,
      className
    )}
    {...props}
  &gt;
    &lt;span className=&quot;absolute left-2 flex h-3.5 w-3.5 items-center justify-center&quot;&gt;
      &lt;MenubarPrimitive.ItemIndicator&gt;
        &lt;Circle className=&quot;h-4 w-4 fill-current&quot; /&gt;
      &lt;/MenubarPrimitive.ItemIndicator&gt;
    &lt;/span&gt;
    {children}
  &lt;/MenubarPrimitive.RadioItem&gt;
))
MenubarRadioItem.displayName = MenubarPrimitive.RadioItem.displayName

const MenubarLabel = React.forwardRef&lt;
  React.ElementRef&lt;typeof MenubarPrimitive.Label&gt;,
  React.ComponentPropsWithoutRef&lt;typeof MenubarPrimitive.Label&gt; &amp; {
    inset?: boolean
  }
&gt;(({ className, inset, ...props }, ref) =&gt; (
  &lt;MenubarPrimitive.Label
    ref={ref}
    className={cn(
      &quot;px-2 py-1.5 text-sm font-semibold&quot;,
      inset &amp;&amp; &quot;pl-8&quot;,
      className
    )}
    {...props}
  /&gt;
))
MenubarLabel.displayName = MenubarPrimitive.Label.displayName

const MenubarSeparator = React.forwardRef&lt;
  React.ElementRef&lt;typeof MenubarPrimitive.Separator&gt;,
  React.ComponentPropsWithoutRef&lt;typeof MenubarPrimitive.Separator&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;MenubarPrimitive.Separator
    ref={ref}
    className={cn(&quot;-mx-1 my-1 h-px bg-muted&quot;, className)}
    {...props}
  /&gt;
))
MenubarSeparator.displayName = MenubarPrimitive.Separator.displayName

const MenubarShortcut = ({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLSpanElement&gt;) =&gt; {
  return (
    &lt;span
      className={cn(
        &quot;ml-auto text-xs tracking-widest text-muted-foreground&quot;,
        className
      )}
      {...props}
    /&gt;
  )
}
MenubarShortcut.displayname = &quot;MenubarShortcut&quot;

export {
  Menubar,
  MenubarMenu,
  MenubarTrigger,
  MenubarContent,
  MenubarItem,
  MenubarSeparator,
  MenubarLabel,
  MenubarCheckboxItem,
  MenubarRadioGroup,
  MenubarRadioItem,
  MenubarPortal,
  MenubarSubContent,
  MenubarSubTrigger,
  MenubarGroup,
  MenubarSub,
  MenubarShortcut,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_navigation-menu-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/navigation-menu.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_navigation-menu-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_navigation-menu-tsx">import * as React from &quot;react&quot;
import * as NavigationMenuPrimitive from &quot;@radix-ui/react-navigation-menu&quot;
import { cva } from &quot;class-variance-authority&quot;
import { ChevronDown } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;

const NavigationMenu = React.forwardRef&lt;
  React.ElementRef&lt;typeof NavigationMenuPrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof NavigationMenuPrimitive.Root&gt;
&gt;(({ className, children, ...props }, ref) =&gt; (
  &lt;NavigationMenuPrimitive.Root
    ref={ref}
    className={cn(
      &quot;relative z-10 flex max-w-max flex-1 items-center justify-center&quot;,
      className
    )}
    {...props}
  &gt;
    {children}
    &lt;NavigationMenuViewport /&gt;
  &lt;/NavigationMenuPrimitive.Root&gt;
))
NavigationMenu.displayName = NavigationMenuPrimitive.Root.displayName

const NavigationMenuList = React.forwardRef&lt;
  React.ElementRef&lt;typeof NavigationMenuPrimitive.List&gt;,
  React.ComponentPropsWithoutRef&lt;typeof NavigationMenuPrimitive.List&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;NavigationMenuPrimitive.List
    ref={ref}
    className={cn(
      &quot;group flex flex-1 list-none items-center justify-center space-x-1&quot;,
      className
    )}
    {...props}
  /&gt;
))
NavigationMenuList.displayName = NavigationMenuPrimitive.List.displayName

const NavigationMenuItem = NavigationMenuPrimitive.Item

const navigationMenuTriggerStyle = cva(
  &quot;group inline-flex h-9 w-max items-center justify-center rounded-md bg-background px-4 py-2 text-sm font-medium transition-colors hover:bg-accent hover:text-accent-foreground focus:bg-accent focus:text-accent-foreground focus:outline-none disabled:pointer-events-none disabled:opacity-50 data-[state=open]:text-accent-foreground data-[state=open]:bg-accent/50 data-[state=open]:hover:bg-accent data-[state=open]:focus:bg-accent&quot;
)

const NavigationMenuTrigger = React.forwardRef&lt;
  React.ElementRef&lt;typeof NavigationMenuPrimitive.Trigger&gt;,
  React.ComponentPropsWithoutRef&lt;typeof NavigationMenuPrimitive.Trigger&gt;
&gt;(({ className, children, ...props }, ref) =&gt; (
  &lt;NavigationMenuPrimitive.Trigger
    ref={ref}
    className={cn(navigationMenuTriggerStyle(), &quot;group&quot;, className)}
    {...props}
  &gt;
    {children}{&quot; &quot;}
    &lt;ChevronDown
      className=&quot;relative top-[1px] ml-1 h-3 w-3 transition duration-300 group-data-[state=open]:rotate-180&quot;
      aria-hidden=&quot;true&quot;
    /&gt;
  &lt;/NavigationMenuPrimitive.Trigger&gt;
))
NavigationMenuTrigger.displayName = NavigationMenuPrimitive.Trigger.displayName

const NavigationMenuContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof NavigationMenuPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof NavigationMenuPrimitive.Content&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;NavigationMenuPrimitive.Content
    ref={ref}
    className={cn(
      &quot;left-0 top-0 w-full data-[motion^=from-]:animate-in data-[motion^=to-]:animate-out data-[motion^=from-]:fade-in data-[motion^=to-]:fade-out data-[motion=from-end]:slide-in-from-right-52 data-[motion=from-start]:slide-in-from-left-52 data-[motion=to-end]:slide-out-to-right-52 data-[motion=to-start]:slide-out-to-left-52 md:absolute md:w-auto &quot;,
      className
    )}
    {...props}
  /&gt;
))
NavigationMenuContent.displayName = NavigationMenuPrimitive.Content.displayName

const NavigationMenuLink = NavigationMenuPrimitive.Link

const NavigationMenuViewport = React.forwardRef&lt;
  React.ElementRef&lt;typeof NavigationMenuPrimitive.Viewport&gt;,
  React.ComponentPropsWithoutRef&lt;typeof NavigationMenuPrimitive.Viewport&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div className={cn(&quot;absolute left-0 top-full flex justify-center&quot;)}&gt;
    &lt;NavigationMenuPrimitive.Viewport
      className={cn(
        &quot;origin-top-center relative mt-1.5 h-[var(--radix-navigation-menu-viewport-height)] w-full overflow-hidden rounded-md border bg-popover text-popover-foreground shadow data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-90 md:w-[var(--radix-navigation-menu-viewport-width)]&quot;,
        className
      )}
      ref={ref}
      {...props}
    /&gt;
  &lt;/div&gt;
))
NavigationMenuViewport.displayName =
  NavigationMenuPrimitive.Viewport.displayName

const NavigationMenuIndicator = React.forwardRef&lt;
  React.ElementRef&lt;typeof NavigationMenuPrimitive.Indicator&gt;,
  React.ComponentPropsWithoutRef&lt;typeof NavigationMenuPrimitive.Indicator&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;NavigationMenuPrimitive.Indicator
    ref={ref}
    className={cn(
      &quot;top-full z-[1] flex h-1.5 items-end justify-center overflow-hidden data-[state=visible]:animate-in data-[state=hidden]:animate-out data-[state=hidden]:fade-out data-[state=visible]:fade-in&quot;,
      className
    )}
    {...props}
  &gt;
    &lt;div className=&quot;relative top-[60%] h-2 w-2 rotate-45 rounded-tl-sm bg-border shadow-md&quot; /&gt;
  &lt;/NavigationMenuPrimitive.Indicator&gt;
))
NavigationMenuIndicator.displayName =
  NavigationMenuPrimitive.Indicator.displayName

export {
  navigationMenuTriggerStyle,
  NavigationMenu,
  NavigationMenuList,
  NavigationMenuItem,
  NavigationMenuContent,
  NavigationMenuTrigger,
  NavigationMenuLink,
  NavigationMenuIndicator,
  NavigationMenuViewport,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_pagination-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/pagination.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_pagination-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_pagination-tsx">import * as React from &quot;react&quot;
import { ChevronLeft, ChevronRight, MoreHorizontal } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;
import { ButtonProps, buttonVariants } from &quot;@/components/ui/button&quot;

const Pagination = ({ className, ...props }: React.ComponentProps&lt;&quot;nav&quot;&gt;) =&gt; (
  &lt;nav
    role=&quot;navigation&quot;
    aria-label=&quot;pagination&quot;
    className={cn(&quot;mx-auto flex w-full justify-center&quot;, className)}
    {...props}
  /&gt;
)
Pagination.displayName = &quot;Pagination&quot;

const PaginationContent = React.forwardRef&lt;
  HTMLUListElement,
  React.ComponentProps&lt;&quot;ul&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;ul
    ref={ref}
    className={cn(&quot;flex flex-row items-center gap-1&quot;, className)}
    {...props}
  /&gt;
))
PaginationContent.displayName = &quot;PaginationContent&quot;

const PaginationItem = React.forwardRef&lt;
  HTMLLIElement,
  React.ComponentProps&lt;&quot;li&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;li ref={ref} className={cn(&quot;&quot;, className)} {...props} /&gt;
))
PaginationItem.displayName = &quot;PaginationItem&quot;

type PaginationLinkProps = {
  isActive?: boolean
} &amp; Pick&lt;ButtonProps, &quot;size&quot;&gt; &amp;
  React.ComponentProps&lt;&quot;a&quot;&gt;

const PaginationLink = ({
  className,
  isActive,
  size = &quot;icon&quot;,
  ...props
}: PaginationLinkProps) =&gt; (
  &lt;a
    aria-current={isActive ? &quot;page&quot; : undefined}
    className={cn(
      buttonVariants({
        variant: isActive ? &quot;outline&quot; : &quot;ghost&quot;,
        size,
      }),
      className
    )}
    {...props}
  /&gt;
)
PaginationLink.displayName = &quot;PaginationLink&quot;

const PaginationPrevious = ({
  className,
  ...props
}: React.ComponentProps&lt;typeof PaginationLink&gt;) =&gt; (
  &lt;PaginationLink
    aria-label=&quot;Go to previous page&quot;
    size=&quot;default&quot;
    className={cn(&quot;gap-1 pl-2.5&quot;, className)}
    {...props}
  &gt;
    &lt;ChevronLeft className=&quot;h-4 w-4&quot; /&gt;
    &lt;span&gt;Previous&lt;/span&gt;
  &lt;/PaginationLink&gt;
)
PaginationPrevious.displayName = &quot;PaginationPrevious&quot;

const PaginationNext = ({
  className,
  ...props
}: React.ComponentProps&lt;typeof PaginationLink&gt;) =&gt; (
  &lt;PaginationLink
    aria-label=&quot;Go to next page&quot;
    size=&quot;default&quot;
    className={cn(&quot;gap-1 pr-2.5&quot;, className)}
    {...props}
  &gt;
    &lt;span&gt;Next&lt;/span&gt;
    &lt;ChevronRight className=&quot;h-4 w-4&quot; /&gt;
  &lt;/PaginationLink&gt;
)
PaginationNext.displayName = &quot;PaginationNext&quot;

const PaginationEllipsis = ({
  className,
  ...props
}: React.ComponentProps&lt;&quot;span&quot;&gt;) =&gt; (
  &lt;span
    aria-hidden
    className={cn(&quot;flex h-9 w-9 items-center justify-center&quot;, className)}
    {...props}
  &gt;
    &lt;MoreHorizontal className=&quot;h-4 w-4&quot; /&gt;
    &lt;span className=&quot;sr-only&quot;&gt;More pages&lt;/span&gt;
  &lt;/span&gt;
)
PaginationEllipsis.displayName = &quot;PaginationEllipsis&quot;

export {
  Pagination,
  PaginationContent,
  PaginationLink,
  PaginationItem,
  PaginationPrevious,
  PaginationNext,
  PaginationEllipsis,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_popover-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/popover.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_popover-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_popover-tsx">import * as React from &quot;react&quot;
import * as PopoverPrimitive from &quot;@radix-ui/react-popover&quot;

import { cn } from &quot;@/lib/utils&quot;

const Popover = PopoverPrimitive.Root

const PopoverTrigger = PopoverPrimitive.Trigger

const PopoverAnchor = PopoverPrimitive.Anchor

const PopoverContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof PopoverPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof PopoverPrimitive.Content&gt;
&gt;(({ className, align = &quot;center&quot;, sideOffset = 4, ...props }, ref) =&gt; (
  &lt;PopoverPrimitive.Portal&gt;
    &lt;PopoverPrimitive.Content
      ref={ref}
      align={align}
      sideOffset={sideOffset}
      className={cn(
        &quot;z-50 w-72 rounded-md border bg-popover p-4 text-popover-foreground shadow-md outline-none data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 origin-[--radix-popover-content-transform-origin]&quot;,
        className
      )}
      {...props}
    /&gt;
  &lt;/PopoverPrimitive.Portal&gt;
))
PopoverContent.displayName = PopoverPrimitive.Content.displayName

export { Popover, PopoverTrigger, PopoverContent, PopoverAnchor }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_progress-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/progress.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_progress-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_progress-tsx">&quot;use client&quot;

import * as React from &quot;react&quot;
import * as ProgressPrimitive from &quot;@radix-ui/react-progress&quot;

import { cn } from &quot;@/lib/utils&quot;

const Progress = React.forwardRef&lt;
  React.ElementRef&lt;typeof ProgressPrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ProgressPrimitive.Root&gt;
&gt;(({ className, value, ...props }, ref) =&gt; (
  &lt;ProgressPrimitive.Root
    ref={ref}
    className={cn(
      &quot;relative h-2 w-full overflow-hidden rounded-full bg-primary/20&quot;,
      className
    )}
    {...props}
  &gt;
    &lt;ProgressPrimitive.Indicator
      className=&quot;h-full w-full flex-1 bg-primary transition-all&quot;
      style={{ transform: `translateX(-${100 - (value || 0)}%)` }}
    /&gt;
  &lt;/ProgressPrimitive.Root&gt;
))
Progress.displayName = ProgressPrimitive.Root.displayName

export { Progress }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_radio-group-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/radio-group.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_radio-group-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_radio-group-tsx">import * as React from &quot;react&quot;
import * as RadioGroupPrimitive from &quot;@radix-ui/react-radio-group&quot;
import { Circle } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;

const RadioGroup = React.forwardRef&lt;
  React.ElementRef&lt;typeof RadioGroupPrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof RadioGroupPrimitive.Root&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  return (
    &lt;RadioGroupPrimitive.Root
      className={cn(&quot;grid gap-2&quot;, className)}
      {...props}
      ref={ref}
    /&gt;
  )
})
RadioGroup.displayName = RadioGroupPrimitive.Root.displayName

const RadioGroupItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof RadioGroupPrimitive.Item&gt;,
  React.ComponentPropsWithoutRef&lt;typeof RadioGroupPrimitive.Item&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  return (
    &lt;RadioGroupPrimitive.Item
      ref={ref}
      className={cn(
        &quot;aspect-square h-4 w-4 rounded-full border border-primary text-primary shadow focus:outline-none focus-visible:ring-1 focus-visible:ring-ring disabled:cursor-not-allowed disabled:opacity-50&quot;,
        className
      )}
      {...props}
    &gt;
      &lt;RadioGroupPrimitive.Indicator className=&quot;flex items-center justify-center&quot;&gt;
        &lt;Circle className=&quot;h-3.5 w-3.5 fill-primary&quot; /&gt;
      &lt;/RadioGroupPrimitive.Indicator&gt;
    &lt;/RadioGroupPrimitive.Item&gt;
  )
})
RadioGroupItem.displayName = RadioGroupPrimitive.Item.displayName

export { RadioGroup, RadioGroupItem }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_resizable-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/resizable.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_resizable-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_resizable-tsx">&quot;use client&quot;

import { GripVertical } from &quot;lucide-react&quot;
import * as ResizablePrimitive from &quot;react-resizable-panels&quot;

import { cn } from &quot;@/lib/utils&quot;

const ResizablePanelGroup = ({
  className,
  ...props
}: React.ComponentProps&lt;typeof ResizablePrimitive.PanelGroup&gt;) =&gt; (
  &lt;ResizablePrimitive.PanelGroup
    className={cn(
      &quot;flex h-full w-full data-[panel-group-direction=vertical]:flex-col&quot;,
      className
    )}
    {...props}
  /&gt;
)

const ResizablePanel = ResizablePrimitive.Panel

const ResizableHandle = ({
  withHandle,
  className,
  ...props
}: React.ComponentProps&lt;typeof ResizablePrimitive.PanelResizeHandle&gt; &amp; {
  withHandle?: boolean
}) =&gt; (
  &lt;ResizablePrimitive.PanelResizeHandle
    className={cn(
      &quot;relative flex w-px items-center justify-center bg-border after:absolute after:inset-y-0 after:left-1/2 after:w-1 after:-translate-x-1/2 focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring focus-visible:ring-offset-1 data-[panel-group-direction=vertical]:h-px data-[panel-group-direction=vertical]:w-full data-[panel-group-direction=vertical]:after:left-0 data-[panel-group-direction=vertical]:after:h-1 data-[panel-group-direction=vertical]:after:w-full data-[panel-group-direction=vertical]:after:-translate-y-1/2 data-[panel-group-direction=vertical]:after:translate-x-0 [&amp;[data-panel-group-direction=vertical]&gt;div]:rotate-90&quot;,
      className
    )}
    {...props}
  &gt;
    {withHandle &amp;&amp; (
      &lt;div className=&quot;z-10 flex h-4 w-3 items-center justify-center rounded-sm border bg-border&quot;&gt;
        &lt;GripVertical className=&quot;h-2.5 w-2.5&quot; /&gt;
      &lt;/div&gt;
    )}
  &lt;/ResizablePrimitive.PanelResizeHandle&gt;
)

export { ResizablePanelGroup, ResizablePanel, ResizableHandle }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_scroll-area-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/scroll-area.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_scroll-area-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_scroll-area-tsx">import * as React from &quot;react&quot;
import * as ScrollAreaPrimitive from &quot;@radix-ui/react-scroll-area&quot;

import { cn } from &quot;@/lib/utils&quot;

const ScrollArea = React.forwardRef&lt;
  React.ElementRef&lt;typeof ScrollAreaPrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ScrollAreaPrimitive.Root&gt;
&gt;(({ className, children, ...props }, ref) =&gt; (
  &lt;ScrollAreaPrimitive.Root
    ref={ref}
    className={cn(&quot;relative overflow-hidden&quot;, className)}
    {...props}
  &gt;
    &lt;ScrollAreaPrimitive.Viewport className=&quot;h-full w-full rounded-[inherit]&quot;&gt;
      {children}
    &lt;/ScrollAreaPrimitive.Viewport&gt;
    &lt;ScrollBar /&gt;
    &lt;ScrollAreaPrimitive.Corner /&gt;
  &lt;/ScrollAreaPrimitive.Root&gt;
))
ScrollArea.displayName = ScrollAreaPrimitive.Root.displayName

const ScrollBar = React.forwardRef&lt;
  React.ElementRef&lt;typeof ScrollAreaPrimitive.ScrollAreaScrollbar&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ScrollAreaPrimitive.ScrollAreaScrollbar&gt;
&gt;(({ className, orientation = &quot;vertical&quot;, ...props }, ref) =&gt; (
  &lt;ScrollAreaPrimitive.ScrollAreaScrollbar
    ref={ref}
    orientation={orientation}
    className={cn(
      &quot;flex touch-none select-none transition-colors&quot;,
      orientation === &quot;vertical&quot; &amp;&amp;
        &quot;h-full w-2.5 border-l border-l-transparent p-[1px]&quot;,
      orientation === &quot;horizontal&quot; &amp;&amp;
        &quot;h-2.5 flex-col border-t border-t-transparent p-[1px]&quot;,
      className
    )}
    {...props}
  &gt;
    &lt;ScrollAreaPrimitive.ScrollAreaThumb className=&quot;relative flex-1 rounded-full bg-border&quot; /&gt;
  &lt;/ScrollAreaPrimitive.ScrollAreaScrollbar&gt;
))
ScrollBar.displayName = ScrollAreaPrimitive.ScrollAreaScrollbar.displayName

export { ScrollArea, ScrollBar }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_select-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/select.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_select-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_select-tsx">&quot;use client&quot;

import * as React from &quot;react&quot;
import * as SelectPrimitive from &quot;@radix-ui/react-select&quot;
import { Check, ChevronDown, ChevronUp } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;

const Select = SelectPrimitive.Root

const SelectGroup = SelectPrimitive.Group

const SelectValue = SelectPrimitive.Value

const SelectTrigger = React.forwardRef&lt;
  React.ElementRef&lt;typeof SelectPrimitive.Trigger&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SelectPrimitive.Trigger&gt;
&gt;(({ className, children, ...props }, ref) =&gt; (
  &lt;SelectPrimitive.Trigger
    ref={ref}
    className={cn(
      &quot;flex h-9 w-full items-center justify-between whitespace-nowrap rounded-md border border-input bg-transparent px-3 py-2 text-sm shadow-sm ring-offset-background data-[placeholder]:text-muted-foreground focus:outline-none focus:ring-1 focus:ring-ring disabled:cursor-not-allowed disabled:opacity-50 [&amp;&gt;span]:line-clamp-1&quot;,
      className
    )}
    {...props}
  &gt;
    {children}
    &lt;SelectPrimitive.Icon asChild&gt;
      &lt;ChevronDown className=&quot;h-4 w-4 opacity-50&quot; /&gt;
    &lt;/SelectPrimitive.Icon&gt;
  &lt;/SelectPrimitive.Trigger&gt;
))
SelectTrigger.displayName = SelectPrimitive.Trigger.displayName

const SelectScrollUpButton = React.forwardRef&lt;
  React.ElementRef&lt;typeof SelectPrimitive.ScrollUpButton&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SelectPrimitive.ScrollUpButton&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;SelectPrimitive.ScrollUpButton
    ref={ref}
    className={cn(
      &quot;flex cursor-default items-center justify-center py-1&quot;,
      className
    )}
    {...props}
  &gt;
    &lt;ChevronUp className=&quot;h-4 w-4&quot; /&gt;
  &lt;/SelectPrimitive.ScrollUpButton&gt;
))
SelectScrollUpButton.displayName = SelectPrimitive.ScrollUpButton.displayName

const SelectScrollDownButton = React.forwardRef&lt;
  React.ElementRef&lt;typeof SelectPrimitive.ScrollDownButton&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SelectPrimitive.ScrollDownButton&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;SelectPrimitive.ScrollDownButton
    ref={ref}
    className={cn(
      &quot;flex cursor-default items-center justify-center py-1&quot;,
      className
    )}
    {...props}
  &gt;
    &lt;ChevronDown className=&quot;h-4 w-4&quot; /&gt;
  &lt;/SelectPrimitive.ScrollDownButton&gt;
))
SelectScrollDownButton.displayName =
  SelectPrimitive.ScrollDownButton.displayName

const SelectContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof SelectPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SelectPrimitive.Content&gt;
&gt;(({ className, children, position = &quot;popper&quot;, ...props }, ref) =&gt; (
  &lt;SelectPrimitive.Portal&gt;
    &lt;SelectPrimitive.Content
      ref={ref}
      className={cn(
        &quot;relative z-50 max-h-[--radix-select-content-available-height] min-w-[8rem] overflow-y-auto overflow-x-hidden rounded-md border bg-popover text-popover-foreground shadow-md data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 origin-[--radix-select-content-transform-origin]&quot;,
        position === &quot;popper&quot; &amp;&amp;
          &quot;data-[side=bottom]:translate-y-1 data-[side=left]:-translate-x-1 data-[side=right]:translate-x-1 data-[side=top]:-translate-y-1&quot;,
        className
      )}
      position={position}
      {...props}
    &gt;
      &lt;SelectScrollUpButton /&gt;
      &lt;SelectPrimitive.Viewport
        className={cn(
          &quot;p-1&quot;,
          position === &quot;popper&quot; &amp;&amp;
            &quot;h-[var(--radix-select-trigger-height)] w-full min-w-[var(--radix-select-trigger-width)]&quot;
        )}
      &gt;
        {children}
      &lt;/SelectPrimitive.Viewport&gt;
      &lt;SelectScrollDownButton /&gt;
    &lt;/SelectPrimitive.Content&gt;
  &lt;/SelectPrimitive.Portal&gt;
))
SelectContent.displayName = SelectPrimitive.Content.displayName

const SelectLabel = React.forwardRef&lt;
  React.ElementRef&lt;typeof SelectPrimitive.Label&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SelectPrimitive.Label&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;SelectPrimitive.Label
    ref={ref}
    className={cn(&quot;px-2 py-1.5 text-sm font-semibold&quot;, className)}
    {...props}
  /&gt;
))
SelectLabel.displayName = SelectPrimitive.Label.displayName

const SelectItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof SelectPrimitive.Item&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SelectPrimitive.Item&gt;
&gt;(({ className, children, ...props }, ref) =&gt; (
  &lt;SelectPrimitive.Item
    ref={ref}
    className={cn(
      &quot;relative flex w-full cursor-default select-none items-center rounded-sm py-1.5 pl-2 pr-8 text-sm outline-none focus:bg-accent focus:text-accent-foreground data-[disabled]:pointer-events-none data-[disabled]:opacity-50&quot;,
      className
    )}
    {...props}
  &gt;
    &lt;span className=&quot;absolute right-2 flex h-3.5 w-3.5 items-center justify-center&quot;&gt;
      &lt;SelectPrimitive.ItemIndicator&gt;
        &lt;Check className=&quot;h-4 w-4&quot; /&gt;
      &lt;/SelectPrimitive.ItemIndicator&gt;
    &lt;/span&gt;
    &lt;SelectPrimitive.ItemText&gt;{children}&lt;/SelectPrimitive.ItemText&gt;
  &lt;/SelectPrimitive.Item&gt;
))
SelectItem.displayName = SelectPrimitive.Item.displayName

const SelectSeparator = React.forwardRef&lt;
  React.ElementRef&lt;typeof SelectPrimitive.Separator&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SelectPrimitive.Separator&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;SelectPrimitive.Separator
    ref={ref}
    className={cn(&quot;-mx-1 my-1 h-px bg-muted&quot;, className)}
    {...props}
  /&gt;
))
SelectSeparator.displayName = SelectPrimitive.Separator.displayName

export {
  Select,
  SelectGroup,
  SelectValue,
  SelectTrigger,
  SelectContent,
  SelectLabel,
  SelectItem,
  SelectSeparator,
  SelectScrollUpButton,
  SelectScrollDownButton,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_separator-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/separator.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_separator-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_separator-tsx">import * as React from &quot;react&quot;
import * as SeparatorPrimitive from &quot;@radix-ui/react-separator&quot;

import { cn } from &quot;@/lib/utils&quot;

const Separator = React.forwardRef&lt;
  React.ElementRef&lt;typeof SeparatorPrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SeparatorPrimitive.Root&gt;
&gt;(
  (
    { className, orientation = &quot;horizontal&quot;, decorative = true, ...props },
    ref
  ) =&gt; (
    &lt;SeparatorPrimitive.Root
      ref={ref}
      decorative={decorative}
      orientation={orientation}
      className={cn(
        &quot;shrink-0 bg-border&quot;,
        orientation === &quot;horizontal&quot; ? &quot;h-[1px] w-full&quot; : &quot;h-full w-[1px]&quot;,
        className
      )}
      {...props}
    /&gt;
  )
)
Separator.displayName = SeparatorPrimitive.Root.displayName

export { Separator }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_sheet-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/sheet.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_sheet-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_sheet-tsx">&quot;use client&quot;

import * as React from &quot;react&quot;
import * as SheetPrimitive from &quot;@radix-ui/react-dialog&quot;
import { cva, type VariantProps } from &quot;class-variance-authority&quot;
import { X } from &quot;lucide-react&quot;

import { cn } from &quot;@/lib/utils&quot;

const Sheet = SheetPrimitive.Root

const SheetTrigger = SheetPrimitive.Trigger

const SheetClose = SheetPrimitive.Close

const SheetPortal = SheetPrimitive.Portal

const SheetOverlay = React.forwardRef&lt;
  React.ElementRef&lt;typeof SheetPrimitive.Overlay&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SheetPrimitive.Overlay&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;SheetPrimitive.Overlay
    className={cn(
      &quot;fixed inset-0 z-50 bg-black/80  data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0&quot;,
      className
    )}
    {...props}
    ref={ref}
  /&gt;
))
SheetOverlay.displayName = SheetPrimitive.Overlay.displayName

const sheetVariants = cva(
  &quot;fixed z-50 gap-4 bg-background p-6 shadow-lg transition ease-in-out data-[state=closed]:duration-300 data-[state=open]:duration-500 data-[state=open]:animate-in data-[state=closed]:animate-out&quot;,
  {
    variants: {
      side: {
        top: &quot;inset-x-0 top-0 border-b data-[state=closed]:slide-out-to-top data-[state=open]:slide-in-from-top&quot;,
        bottom:
          &quot;inset-x-0 bottom-0 border-t data-[state=closed]:slide-out-to-bottom data-[state=open]:slide-in-from-bottom&quot;,
        left: &quot;inset-y-0 left-0 h-full w-3/4 border-r data-[state=closed]:slide-out-to-left data-[state=open]:slide-in-from-left sm:max-w-sm&quot;,
        right:
          &quot;inset-y-0 right-0 h-full w-3/4 border-l data-[state=closed]:slide-out-to-right data-[state=open]:slide-in-from-right sm:max-w-sm&quot;,
      },
    },
    defaultVariants: {
      side: &quot;right&quot;,
    },
  }
)

interface SheetContentProps
  extends React.ComponentPropsWithoutRef&lt;typeof SheetPrimitive.Content&gt;,
    VariantProps&lt;typeof sheetVariants&gt; {}

const SheetContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof SheetPrimitive.Content&gt;,
  SheetContentProps
&gt;(({ side = &quot;right&quot;, className, children, ...props }, ref) =&gt; (
  &lt;SheetPortal&gt;
    &lt;SheetOverlay /&gt;
    &lt;SheetPrimitive.Content
      ref={ref}
      className={cn(sheetVariants({ side }), className)}
      {...props}
    &gt;
      &lt;SheetPrimitive.Close className=&quot;absolute right-4 top-4 rounded-sm opacity-70 ring-offset-background transition-opacity hover:opacity-100 focus:outline-none focus:ring-2 focus:ring-ring focus:ring-offset-2 disabled:pointer-events-none data-[state=open]:bg-secondary&quot;&gt;
        &lt;X className=&quot;h-4 w-4&quot; /&gt;
        &lt;span className=&quot;sr-only&quot;&gt;Close&lt;/span&gt;
      &lt;/SheetPrimitive.Close&gt;
      {children}
    &lt;/SheetPrimitive.Content&gt;
  &lt;/SheetPortal&gt;
))
SheetContent.displayName = SheetPrimitive.Content.displayName

const SheetHeader = ({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLDivElement&gt;) =&gt; (
  &lt;div
    className={cn(
      &quot;flex flex-col space-y-2 text-center sm:text-left&quot;,
      className
    )}
    {...props}
  /&gt;
)
SheetHeader.displayName = &quot;SheetHeader&quot;

const SheetFooter = ({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLDivElement&gt;) =&gt; (
  &lt;div
    className={cn(
      &quot;flex flex-col-reverse sm:flex-row sm:justify-end sm:space-x-2&quot;,
      className
    )}
    {...props}
  /&gt;
)
SheetFooter.displayName = &quot;SheetFooter&quot;

const SheetTitle = React.forwardRef&lt;
  React.ElementRef&lt;typeof SheetPrimitive.Title&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SheetPrimitive.Title&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;SheetPrimitive.Title
    ref={ref}
    className={cn(&quot;text-lg font-semibold text-foreground&quot;, className)}
    {...props}
  /&gt;
))
SheetTitle.displayName = SheetPrimitive.Title.displayName

const SheetDescription = React.forwardRef&lt;
  React.ElementRef&lt;typeof SheetPrimitive.Description&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SheetPrimitive.Description&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;SheetPrimitive.Description
    ref={ref}
    className={cn(&quot;text-sm text-muted-foreground&quot;, className)}
    {...props}
  /&gt;
))
SheetDescription.displayName = SheetPrimitive.Description.displayName

export {
  Sheet,
  SheetPortal,
  SheetOverlay,
  SheetTrigger,
  SheetClose,
  SheetContent,
  SheetHeader,
  SheetFooter,
  SheetTitle,
  SheetDescription,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_sidebar-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/sidebar.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_sidebar-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_sidebar-tsx">import * as React from &quot;react&quot;
import { Slot } from &quot;@radix-ui/react-slot&quot;
import { cva, type VariantProps } from &quot;class-variance-authority&quot;
import { PanelLeft } from &quot;lucide-react&quot;

import { useIsMobile } from &quot;@/hooks/use-mobile&quot;
import { cn } from &quot;@/lib/utils&quot;
import { Button } from &quot;@/components/ui/button&quot;
import { Input } from &quot;@/components/ui/input&quot;
import { Separator } from &quot;@/components/ui/separator&quot;
import {
  Sheet,
  SheetContent,
  SheetDescription,
  SheetHeader,
  SheetTitle,
} from &quot;@/components/ui/sheet&quot;
import { Skeleton } from &quot;@/components/ui/skeleton&quot;
import {
  Tooltip,
  TooltipContent,
  TooltipProvider,
  TooltipTrigger,
} from &quot;@/components/ui/tooltip&quot;

const SIDEBAR_COOKIE_NAME = &quot;sidebar_state&quot;
const SIDEBAR_COOKIE_MAX_AGE = 60 * 60 * 24 * 7
const SIDEBAR_WIDTH = &quot;16rem&quot;
const SIDEBAR_WIDTH_MOBILE = &quot;18rem&quot;
const SIDEBAR_WIDTH_ICON = &quot;3rem&quot;
const SIDEBAR_KEYBOARD_SHORTCUT = &quot;b&quot;

type SidebarContextProps = {
  state: &quot;expanded&quot; | &quot;collapsed&quot;
  open: boolean
  setOpen: (open: boolean) =&gt; void
  openMobile: boolean
  setOpenMobile: (open: boolean) =&gt; void
  isMobile: boolean
  toggleSidebar: () =&gt; void
}

const SidebarContext = React.createContext&lt;SidebarContextProps | null&gt;(null)

function useSidebar() {
  const context = React.useContext(SidebarContext)
  if (!context) {
    throw new Error(&quot;useSidebar must be used within a SidebarProvider.&quot;)
  }

  return context
}

const SidebarProvider = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;div&quot;&gt; &amp; {
    defaultOpen?: boolean
    open?: boolean
    onOpenChange?: (open: boolean) =&gt; void
  }
&gt;(
  (
    {
      defaultOpen = true,
      open: openProp,
      onOpenChange: setOpenProp,
      className,
      style,
      children,
      ...props
    },
    ref
  ) =&gt; {
    const isMobile = useIsMobile()
    const [openMobile, setOpenMobile] = React.useState(false)

    // This is the internal state of the sidebar.
    // We use openProp and setOpenProp for control from outside the component.
    const [_open, _setOpen] = React.useState(defaultOpen)
    const open = openProp ?? _open
    const setOpen = React.useCallback(
      (value: boolean | ((value: boolean) =&gt; boolean)) =&gt; {
        const openState = typeof value === &quot;function&quot; ? value(open) : value
        if (setOpenProp) {
          setOpenProp(openState)
        } else {
          _setOpen(openState)
        }

        // This sets the cookie to keep the sidebar state.
        document.cookie = `${SIDEBAR_COOKIE_NAME}=${openState}; path=/; max-age=${SIDEBAR_COOKIE_MAX_AGE}`
      },
      [setOpenProp, open]
    )

    // Helper to toggle the sidebar.
    const toggleSidebar = React.useCallback(() =&gt; {
      return isMobile
        ? setOpenMobile((open) =&gt; !open)
        : setOpen((open) =&gt; !open)
    }, [isMobile, setOpen, setOpenMobile])

    // Adds a keyboard shortcut to toggle the sidebar.
    React.useEffect(() =&gt; {
      const handleKeyDown = (event: KeyboardEvent) =&gt; {
        if (
          event.key === SIDEBAR_KEYBOARD_SHORTCUT &amp;&amp;
          (event.metaKey || event.ctrlKey)
        ) {
          event.preventDefault()
          toggleSidebar()
        }
      }

      window.addEventListener(&quot;keydown&quot;, handleKeyDown)
      return () =&gt; window.removeEventListener(&quot;keydown&quot;, handleKeyDown)
    }, [toggleSidebar])

    // We add a state so that we can do data-state=&quot;expanded&quot; or &quot;collapsed&quot;.
    // This makes it easier to style the sidebar with Tailwind classes.
    const state = open ? &quot;expanded&quot; : &quot;collapsed&quot;

    const contextValue = React.useMemo&lt;SidebarContextProps&gt;(
      () =&gt; ({
        state,
        open,
        setOpen,
        isMobile,
        openMobile,
        setOpenMobile,
        toggleSidebar,
      }),
      [state, open, setOpen, isMobile, openMobile, setOpenMobile, toggleSidebar]
    )

    return (
      &lt;SidebarContext.Provider value={contextValue}&gt;
        &lt;TooltipProvider delayDuration={0}&gt;
          &lt;div
            style={
              {
                &quot;--sidebar-width&quot;: SIDEBAR_WIDTH,
                &quot;--sidebar-width-icon&quot;: SIDEBAR_WIDTH_ICON,
                ...style,
              } as React.CSSProperties
            }
            className={cn(
              &quot;group/sidebar-wrapper flex min-h-svh w-full has-[[data-variant=inset]]:bg-sidebar&quot;,
              className
            )}
            ref={ref}
            {...props}
          &gt;
            {children}
          &lt;/div&gt;
        &lt;/TooltipProvider&gt;
      &lt;/SidebarContext.Provider&gt;
    )
  }
)
SidebarProvider.displayName = &quot;SidebarProvider&quot;

const Sidebar = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;div&quot;&gt; &amp; {
    side?: &quot;left&quot; | &quot;right&quot;
    variant?: &quot;sidebar&quot; | &quot;floating&quot; | &quot;inset&quot;
    collapsible?: &quot;offcanvas&quot; | &quot;icon&quot; | &quot;none&quot;
  }
&gt;(
  (
    {
      side = &quot;left&quot;,
      variant = &quot;sidebar&quot;,
      collapsible = &quot;offcanvas&quot;,
      className,
      children,
      ...props
    },
    ref
  ) =&gt; {
    const { isMobile, state, openMobile, setOpenMobile } = useSidebar()

    if (collapsible === &quot;none&quot;) {
      return (
        &lt;div
          className={cn(
            &quot;flex h-full w-[--sidebar-width] flex-col bg-sidebar text-sidebar-foreground&quot;,
            className
          )}
          ref={ref}
          {...props}
        &gt;
          {children}
        &lt;/div&gt;
      )
    }

    if (isMobile) {
      return (
        &lt;Sheet open={openMobile} onOpenChange={setOpenMobile} {...props}&gt;
          &lt;SheetContent
            data-sidebar=&quot;sidebar&quot;
            data-mobile=&quot;true&quot;
            className=&quot;w-[--sidebar-width] bg-sidebar p-0 text-sidebar-foreground [&amp;&gt;button]:hidden&quot;
            style={
              {
                &quot;--sidebar-width&quot;: SIDEBAR_WIDTH_MOBILE,
              } as React.CSSProperties
            }
            side={side}
          &gt;
            &lt;SheetHeader className=&quot;sr-only&quot;&gt;
              &lt;SheetTitle&gt;Sidebar&lt;/SheetTitle&gt;
              &lt;SheetDescription&gt;Displays the mobile sidebar.&lt;/SheetDescription&gt;
            &lt;/SheetHeader&gt;
            &lt;div className=&quot;flex h-full w-full flex-col&quot;&gt;{children}&lt;/div&gt;
          &lt;/SheetContent&gt;
        &lt;/Sheet&gt;
      )
    }

    return (
      &lt;div
        ref={ref}
        className=&quot;group peer hidden text-sidebar-foreground md:block&quot;
        data-state={state}
        data-collapsible={state === &quot;collapsed&quot; ? collapsible : &quot;&quot;}
        data-variant={variant}
        data-side={side}
      &gt;
        {/* This is what handles the sidebar gap on desktop */}
        &lt;div
          className={cn(
            &quot;relative w-[--sidebar-width] bg-transparent transition-[width] duration-200 ease-linear&quot;,
            &quot;group-data-[collapsible=offcanvas]:w-0&quot;,
            &quot;group-data-[side=right]:rotate-180&quot;,
            variant === &quot;floating&quot; || variant === &quot;inset&quot;
              ? &quot;group-data-[collapsible=icon]:w-[calc(var(--sidebar-width-icon)_+_theme(spacing.4))]&quot;
              : &quot;group-data-[collapsible=icon]:w-[--sidebar-width-icon]&quot;
          )}
        /&gt;
        &lt;div
          className={cn(
            &quot;fixed inset-y-0 z-10 hidden h-svh w-[--sidebar-width] transition-[left,right,width] duration-200 ease-linear md:flex&quot;,
            side === &quot;left&quot;
              ? &quot;left-0 group-data-[collapsible=offcanvas]:left-[calc(var(--sidebar-width)*-1)]&quot;
              : &quot;right-0 group-data-[collapsible=offcanvas]:right-[calc(var(--sidebar-width)*-1)]&quot;,
            // Adjust the padding for floating and inset variants.
            variant === &quot;floating&quot; || variant === &quot;inset&quot;
              ? &quot;p-2 group-data-[collapsible=icon]:w-[calc(var(--sidebar-width-icon)_+_theme(spacing.4)_+2px)]&quot;
              : &quot;group-data-[collapsible=icon]:w-[--sidebar-width-icon] group-data-[side=left]:border-r group-data-[side=right]:border-l&quot;,
            className
          )}
          {...props}
        &gt;
          &lt;div
            data-sidebar=&quot;sidebar&quot;
            className=&quot;flex h-full w-full flex-col bg-sidebar group-data-[variant=floating]:rounded-lg group-data-[variant=floating]:border group-data-[variant=floating]:border-sidebar-border group-data-[variant=floating]:shadow&quot;
          &gt;
            {children}
          &lt;/div&gt;
        &lt;/div&gt;
      &lt;/div&gt;
    )
  }
)
Sidebar.displayName = &quot;Sidebar&quot;

const SidebarTrigger = React.forwardRef&lt;
  React.ElementRef&lt;typeof Button&gt;,
  React.ComponentProps&lt;typeof Button&gt;
&gt;(({ className, onClick, ...props }, ref) =&gt; {
  const { toggleSidebar } = useSidebar()

  return (
    &lt;Button
      ref={ref}
      data-sidebar=&quot;trigger&quot;
      variant=&quot;ghost&quot;
      size=&quot;icon&quot;
      className={cn(&quot;h-7 w-7&quot;, className)}
      onClick={(event) =&gt; {
        onClick?.(event)
        toggleSidebar()
      }}
      {...props}
    &gt;
      &lt;PanelLeft /&gt;
      &lt;span className=&quot;sr-only&quot;&gt;Toggle Sidebar&lt;/span&gt;
    &lt;/Button&gt;
  )
})
SidebarTrigger.displayName = &quot;SidebarTrigger&quot;

const SidebarRail = React.forwardRef&lt;
  HTMLButtonElement,
  React.ComponentProps&lt;&quot;button&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  const { toggleSidebar } = useSidebar()

  return (
    &lt;button
      ref={ref}
      data-sidebar=&quot;rail&quot;
      aria-label=&quot;Toggle Sidebar&quot;
      tabIndex={-1}
      onClick={toggleSidebar}
      title=&quot;Toggle Sidebar&quot;
      className={cn(
        &quot;absolute inset-y-0 z-20 hidden w-4 -translate-x-1/2 transition-all ease-linear after:absolute after:inset-y-0 after:left-1/2 after:w-[2px] hover:after:bg-sidebar-border group-data-[side=left]:-right-4 group-data-[side=right]:left-0 sm:flex&quot;,
        &quot;[[data-side=left]_&amp;]:cursor-w-resize [[data-side=right]_&amp;]:cursor-e-resize&quot;,
        &quot;[[data-side=left][data-state=collapsed]_&amp;]:cursor-e-resize [[data-side=right][data-state=collapsed]_&amp;]:cursor-w-resize&quot;,
        &quot;group-data-[collapsible=offcanvas]:translate-x-0 group-data-[collapsible=offcanvas]:after:left-full group-data-[collapsible=offcanvas]:hover:bg-sidebar&quot;,
        &quot;[[data-side=left][data-collapsible=offcanvas]_&amp;]:-right-2&quot;,
        &quot;[[data-side=right][data-collapsible=offcanvas]_&amp;]:-left-2&quot;,
        className
      )}
      {...props}
    /&gt;
  )
})
SidebarRail.displayName = &quot;SidebarRail&quot;

const SidebarInset = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;main&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  return (
    &lt;main
      ref={ref}
      className={cn(
        &quot;relative flex w-full flex-1 flex-col bg-background&quot;,
        &quot;md:peer-data-[variant=inset]:m-2 md:peer-data-[state=collapsed]:peer-data-[variant=inset]:ml-2 md:peer-data-[variant=inset]:ml-0 md:peer-data-[variant=inset]:rounded-xl md:peer-data-[variant=inset]:shadow&quot;,
        className
      )}
      {...props}
    /&gt;
  )
})
SidebarInset.displayName = &quot;SidebarInset&quot;

const SidebarInput = React.forwardRef&lt;
  React.ElementRef&lt;typeof Input&gt;,
  React.ComponentProps&lt;typeof Input&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  return (
    &lt;Input
      ref={ref}
      data-sidebar=&quot;input&quot;
      className={cn(
        &quot;h-8 w-full bg-background shadow-none focus-visible:ring-2 focus-visible:ring-sidebar-ring&quot;,
        className
      )}
      {...props}
    /&gt;
  )
})
SidebarInput.displayName = &quot;SidebarInput&quot;

const SidebarHeader = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;div&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  return (
    &lt;div
      ref={ref}
      data-sidebar=&quot;header&quot;
      className={cn(&quot;flex flex-col gap-2 p-2&quot;, className)}
      {...props}
    /&gt;
  )
})
SidebarHeader.displayName = &quot;SidebarHeader&quot;

const SidebarFooter = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;div&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  return (
    &lt;div
      ref={ref}
      data-sidebar=&quot;footer&quot;
      className={cn(&quot;flex flex-col gap-2 p-2&quot;, className)}
      {...props}
    /&gt;
  )
})
SidebarFooter.displayName = &quot;SidebarFooter&quot;

const SidebarSeparator = React.forwardRef&lt;
  React.ElementRef&lt;typeof Separator&gt;,
  React.ComponentProps&lt;typeof Separator&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  return (
    &lt;Separator
      ref={ref}
      data-sidebar=&quot;separator&quot;
      className={cn(&quot;mx-2 w-auto bg-sidebar-border&quot;, className)}
      {...props}
    /&gt;
  )
})
SidebarSeparator.displayName = &quot;SidebarSeparator&quot;

const SidebarContent = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;div&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  return (
    &lt;div
      ref={ref}
      data-sidebar=&quot;content&quot;
      className={cn(
        &quot;flex min-h-0 flex-1 flex-col gap-2 overflow-auto group-data-[collapsible=icon]:overflow-hidden&quot;,
        className
      )}
      {...props}
    /&gt;
  )
})
SidebarContent.displayName = &quot;SidebarContent&quot;

const SidebarGroup = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;div&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  return (
    &lt;div
      ref={ref}
      data-sidebar=&quot;group&quot;
      className={cn(&quot;relative flex w-full min-w-0 flex-col p-2&quot;, className)}
      {...props}
    /&gt;
  )
})
SidebarGroup.displayName = &quot;SidebarGroup&quot;

const SidebarGroupLabel = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;div&quot;&gt; &amp; { asChild?: boolean }
&gt;(({ className, asChild = false, ...props }, ref) =&gt; {
  const Comp = asChild ? Slot : &quot;div&quot;

  return (
    &lt;Comp
      ref={ref}
      data-sidebar=&quot;group-label&quot;
      className={cn(
        &quot;flex h-8 shrink-0 items-center rounded-md px-2 text-xs font-medium text-sidebar-foreground/70 outline-none ring-sidebar-ring transition-[margin,opacity] duration-200 ease-linear focus-visible:ring-2 [&amp;&gt;svg]:size-4 [&amp;&gt;svg]:shrink-0&quot;,
        &quot;group-data-[collapsible=icon]:-mt-8 group-data-[collapsible=icon]:opacity-0&quot;,
        className
      )}
      {...props}
    /&gt;
  )
})
SidebarGroupLabel.displayName = &quot;SidebarGroupLabel&quot;

const SidebarGroupAction = React.forwardRef&lt;
  HTMLButtonElement,
  React.ComponentProps&lt;&quot;button&quot;&gt; &amp; { asChild?: boolean }
&gt;(({ className, asChild = false, ...props }, ref) =&gt; {
  const Comp = asChild ? Slot : &quot;button&quot;

  return (
    &lt;Comp
      ref={ref}
      data-sidebar=&quot;group-action&quot;
      className={cn(
        &quot;absolute right-3 top-3.5 flex aspect-square w-5 items-center justify-center rounded-md p-0 text-sidebar-foreground outline-none ring-sidebar-ring transition-transform hover:bg-sidebar-accent hover:text-sidebar-accent-foreground focus-visible:ring-2 [&amp;&gt;svg]:size-4 [&amp;&gt;svg]:shrink-0&quot;,
        // Increases the hit area of the button on mobile.
        &quot;after:absolute after:-inset-2 after:md:hidden&quot;,
        &quot;group-data-[collapsible=icon]:hidden&quot;,
        className
      )}
      {...props}
    /&gt;
  )
})
SidebarGroupAction.displayName = &quot;SidebarGroupAction&quot;

const SidebarGroupContent = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;div&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div
    ref={ref}
    data-sidebar=&quot;group-content&quot;
    className={cn(&quot;w-full text-sm&quot;, className)}
    {...props}
  /&gt;
))
SidebarGroupContent.displayName = &quot;SidebarGroupContent&quot;

const SidebarMenu = React.forwardRef&lt;
  HTMLUListElement,
  React.ComponentProps&lt;&quot;ul&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;ul
    ref={ref}
    data-sidebar=&quot;menu&quot;
    className={cn(&quot;flex w-full min-w-0 flex-col gap-1&quot;, className)}
    {...props}
  /&gt;
))
SidebarMenu.displayName = &quot;SidebarMenu&quot;

const SidebarMenuItem = React.forwardRef&lt;
  HTMLLIElement,
  React.ComponentProps&lt;&quot;li&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;li
    ref={ref}
    data-sidebar=&quot;menu-item&quot;
    className={cn(&quot;group/menu-item relative&quot;, className)}
    {...props}
  /&gt;
))
SidebarMenuItem.displayName = &quot;SidebarMenuItem&quot;

const sidebarMenuButtonVariants = cva(
  &quot;peer/menu-button flex w-full items-center gap-2 overflow-hidden rounded-md p-2 text-left text-sm outline-none ring-sidebar-ring transition-[width,height,padding] hover:bg-sidebar-accent hover:text-sidebar-accent-foreground focus-visible:ring-2 active:bg-sidebar-accent active:text-sidebar-accent-foreground disabled:pointer-events-none disabled:opacity-50 group-has-[[data-sidebar=menu-action]]/menu-item:pr-8 aria-disabled:pointer-events-none aria-disabled:opacity-50 data-[active=true]:bg-sidebar-accent data-[active=true]:font-medium data-[active=true]:text-sidebar-accent-foreground data-[state=open]:hover:bg-sidebar-accent data-[state=open]:hover:text-sidebar-accent-foreground group-data-[collapsible=icon]:!size-8 group-data-[collapsible=icon]:!p-2 [&amp;&gt;span:last-child]:truncate [&amp;&gt;svg]:size-4 [&amp;&gt;svg]:shrink-0&quot;,
  {
    variants: {
      variant: {
        default: &quot;hover:bg-sidebar-accent hover:text-sidebar-accent-foreground&quot;,
        outline:
          &quot;bg-background shadow-[0_0_0_1px_hsl(var(--sidebar-border))] hover:bg-sidebar-accent hover:text-sidebar-accent-foreground hover:shadow-[0_0_0_1px_hsl(var(--sidebar-accent))]&quot;,
      },
      size: {
        default: &quot;h-8 text-sm&quot;,
        sm: &quot;h-7 text-xs&quot;,
        lg: &quot;h-12 text-sm group-data-[collapsible=icon]:!p-0&quot;,
      },
    },
    defaultVariants: {
      variant: &quot;default&quot;,
      size: &quot;default&quot;,
    },
  }
)

const SidebarMenuButton = React.forwardRef&lt;
  HTMLButtonElement,
  React.ComponentProps&lt;&quot;button&quot;&gt; &amp; {
    asChild?: boolean
    isActive?: boolean
    tooltip?: string | React.ComponentProps&lt;typeof TooltipContent&gt;
  } &amp; VariantProps&lt;typeof sidebarMenuButtonVariants&gt;
&gt;(
  (
    {
      asChild = false,
      isActive = false,
      variant = &quot;default&quot;,
      size = &quot;default&quot;,
      tooltip,
      className,
      ...props
    },
    ref
  ) =&gt; {
    const Comp = asChild ? Slot : &quot;button&quot;
    const { isMobile, state } = useSidebar()

    const button = (
      &lt;Comp
        ref={ref}
        data-sidebar=&quot;menu-button&quot;
        data-size={size}
        data-active={isActive}
        className={cn(sidebarMenuButtonVariants({ variant, size }), className)}
        {...props}
      /&gt;
    )

    if (!tooltip) {
      return button
    }

    if (typeof tooltip === &quot;string&quot;) {
      tooltip = {
        children: tooltip,
      }
    }

    return (
      &lt;Tooltip&gt;
        &lt;TooltipTrigger asChild&gt;{button}&lt;/TooltipTrigger&gt;
        &lt;TooltipContent
          side=&quot;right&quot;
          align=&quot;center&quot;
          hidden={state !== &quot;collapsed&quot; || isMobile}
          {...tooltip}
        /&gt;
      &lt;/Tooltip&gt;
    )
  }
)
SidebarMenuButton.displayName = &quot;SidebarMenuButton&quot;

const SidebarMenuAction = React.forwardRef&lt;
  HTMLButtonElement,
  React.ComponentProps&lt;&quot;button&quot;&gt; &amp; {
    asChild?: boolean
    showOnHover?: boolean
  }
&gt;(({ className, asChild = false, showOnHover = false, ...props }, ref) =&gt; {
  const Comp = asChild ? Slot : &quot;button&quot;

  return (
    &lt;Comp
      ref={ref}
      data-sidebar=&quot;menu-action&quot;
      className={cn(
        &quot;absolute right-1 top-1.5 flex aspect-square w-5 items-center justify-center rounded-md p-0 text-sidebar-foreground outline-none ring-sidebar-ring transition-transform hover:bg-sidebar-accent hover:text-sidebar-accent-foreground focus-visible:ring-2 peer-hover/menu-button:text-sidebar-accent-foreground [&amp;&gt;svg]:size-4 [&amp;&gt;svg]:shrink-0&quot;,
        // Increases the hit area of the button on mobile.
        &quot;after:absolute after:-inset-2 after:md:hidden&quot;,
        &quot;peer-data-[size=sm]/menu-button:top-1&quot;,
        &quot;peer-data-[size=default]/menu-button:top-1.5&quot;,
        &quot;peer-data-[size=lg]/menu-button:top-2.5&quot;,
        &quot;group-data-[collapsible=icon]:hidden&quot;,
        showOnHover &amp;&amp;
          &quot;group-focus-within/menu-item:opacity-100 group-hover/menu-item:opacity-100 data-[state=open]:opacity-100 peer-data-[active=true]/menu-button:text-sidebar-accent-foreground md:opacity-0&quot;,
        className
      )}
      {...props}
    /&gt;
  )
})
SidebarMenuAction.displayName = &quot;SidebarMenuAction&quot;

const SidebarMenuBadge = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;div&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div
    ref={ref}
    data-sidebar=&quot;menu-badge&quot;
    className={cn(
      &quot;pointer-events-none absolute right-1 flex h-5 min-w-5 select-none items-center justify-center rounded-md px-1 text-xs font-medium tabular-nums text-sidebar-foreground&quot;,
      &quot;peer-hover/menu-button:text-sidebar-accent-foreground peer-data-[active=true]/menu-button:text-sidebar-accent-foreground&quot;,
      &quot;peer-data-[size=sm]/menu-button:top-1&quot;,
      &quot;peer-data-[size=default]/menu-button:top-1.5&quot;,
      &quot;peer-data-[size=lg]/menu-button:top-2.5&quot;,
      &quot;group-data-[collapsible=icon]:hidden&quot;,
      className
    )}
    {...props}
  /&gt;
))
SidebarMenuBadge.displayName = &quot;SidebarMenuBadge&quot;

const SidebarMenuSkeleton = React.forwardRef&lt;
  HTMLDivElement,
  React.ComponentProps&lt;&quot;div&quot;&gt; &amp; {
    showIcon?: boolean
  }
&gt;(({ className, showIcon = false, ...props }, ref) =&gt; {
  // Random width between 50 to 90%.
  const width = React.useMemo(() =&gt; {
    return `${Math.floor(Math.random() * 40) + 50}%`
  }, [])

  return (
    &lt;div
      ref={ref}
      data-sidebar=&quot;menu-skeleton&quot;
      className={cn(&quot;flex h-8 items-center gap-2 rounded-md px-2&quot;, className)}
      {...props}
    &gt;
      {showIcon &amp;&amp; (
        &lt;Skeleton
          className=&quot;size-4 rounded-md&quot;
          data-sidebar=&quot;menu-skeleton-icon&quot;
        /&gt;
      )}
      &lt;Skeleton
        className=&quot;h-4 max-w-[--skeleton-width] flex-1&quot;
        data-sidebar=&quot;menu-skeleton-text&quot;
        style={
          {
            &quot;--skeleton-width&quot;: width,
          } as React.CSSProperties
        }
      /&gt;
    &lt;/div&gt;
  )
})
SidebarMenuSkeleton.displayName = &quot;SidebarMenuSkeleton&quot;

const SidebarMenuSub = React.forwardRef&lt;
  HTMLUListElement,
  React.ComponentProps&lt;&quot;ul&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;ul
    ref={ref}
    data-sidebar=&quot;menu-sub&quot;
    className={cn(
      &quot;mx-3.5 flex min-w-0 translate-x-px flex-col gap-1 border-l border-sidebar-border px-2.5 py-0.5&quot;,
      &quot;group-data-[collapsible=icon]:hidden&quot;,
      className
    )}
    {...props}
  /&gt;
))
SidebarMenuSub.displayName = &quot;SidebarMenuSub&quot;

const SidebarMenuSubItem = React.forwardRef&lt;
  HTMLLIElement,
  React.ComponentProps&lt;&quot;li&quot;&gt;
&gt;(({ ...props }, ref) =&gt; &lt;li ref={ref} {...props} /&gt;)
SidebarMenuSubItem.displayName = &quot;SidebarMenuSubItem&quot;

const SidebarMenuSubButton = React.forwardRef&lt;
  HTMLAnchorElement,
  React.ComponentProps&lt;&quot;a&quot;&gt; &amp; {
    asChild?: boolean
    size?: &quot;sm&quot; | &quot;md&quot;
    isActive?: boolean
  }
&gt;(({ asChild = false, size = &quot;md&quot;, isActive, className, ...props }, ref) =&gt; {
  const Comp = asChild ? Slot : &quot;a&quot;

  return (
    &lt;Comp
      ref={ref}
      data-sidebar=&quot;menu-sub-button&quot;
      data-size={size}
      data-active={isActive}
      className={cn(
        &quot;flex h-7 min-w-0 -translate-x-px items-center gap-2 overflow-hidden rounded-md px-2 text-sidebar-foreground outline-none ring-sidebar-ring hover:bg-sidebar-accent hover:text-sidebar-accent-foreground focus-visible:ring-2 active:bg-sidebar-accent active:text-sidebar-accent-foreground disabled:pointer-events-none disabled:opacity-50 aria-disabled:pointer-events-none aria-disabled:opacity-50 [&amp;&gt;span:last-child]:truncate [&amp;&gt;svg]:size-4 [&amp;&gt;svg]:shrink-0 [&amp;&gt;svg]:text-sidebar-accent-foreground&quot;,
        &quot;data-[active=true]:bg-sidebar-accent data-[active=true]:text-sidebar-accent-foreground&quot;,
        size === &quot;sm&quot; &amp;&amp; &quot;text-xs&quot;,
        size === &quot;md&quot; &amp;&amp; &quot;text-sm&quot;,
        &quot;group-data-[collapsible=icon]:hidden&quot;,
        className
      )}
      {...props}
    /&gt;
  )
})
SidebarMenuSubButton.displayName = &quot;SidebarMenuSubButton&quot;

export {
  Sidebar,
  SidebarContent,
  SidebarFooter,
  SidebarGroup,
  SidebarGroupAction,
  SidebarGroupContent,
  SidebarGroupLabel,
  SidebarHeader,
  SidebarInput,
  SidebarInset,
  SidebarMenu,
  SidebarMenuAction,
  SidebarMenuBadge,
  SidebarMenuButton,
  SidebarMenuItem,
  SidebarMenuSkeleton,
  SidebarMenuSub,
  SidebarMenuSubButton,
  SidebarMenuSubItem,
  SidebarProvider,
  SidebarRail,
  SidebarSeparator,
  SidebarTrigger,
  useSidebar,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_skeleton-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/skeleton.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_skeleton-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_skeleton-tsx">import { cn } from &quot;@/lib/utils&quot;

function Skeleton({
  className,
  ...props
}: React.HTMLAttributes&lt;HTMLDivElement&gt;) {
  return (
    &lt;div
      className={cn(&quot;animate-pulse rounded-md bg-primary/10&quot;, className)}
      {...props}
    /&gt;
  )
}

export { Skeleton }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_slider-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/slider.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_slider-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_slider-tsx">import * as React from &quot;react&quot;
import * as SliderPrimitive from &quot;@radix-ui/react-slider&quot;

import { cn } from &quot;@/lib/utils&quot;

const Slider = React.forwardRef&lt;
  React.ElementRef&lt;typeof SliderPrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SliderPrimitive.Root&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;SliderPrimitive.Root
    ref={ref}
    className={cn(
      &quot;relative flex w-full touch-none select-none items-center&quot;,
      className
    )}
    {...props}
  &gt;
    &lt;SliderPrimitive.Track className=&quot;relative h-1.5 w-full grow overflow-hidden rounded-full bg-primary/20&quot;&gt;
      &lt;SliderPrimitive.Range className=&quot;absolute h-full bg-primary&quot; /&gt;
    &lt;/SliderPrimitive.Track&gt;
    &lt;SliderPrimitive.Thumb className=&quot;block h-4 w-4 rounded-full border border-primary/50 bg-background shadow transition-colors focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring disabled:pointer-events-none disabled:opacity-50&quot; /&gt;
  &lt;/SliderPrimitive.Root&gt;
))
Slider.displayName = SliderPrimitive.Root.displayName

export { Slider }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_sonner-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/sonner.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_sonner-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_sonner-tsx">&quot;use client&quot;

import { useTheme } from &quot;next-themes&quot;
import { Toaster as Sonner } from &quot;sonner&quot;

type ToasterProps = React.ComponentProps&lt;typeof Sonner&gt;

const Toaster = ({ ...props }: ToasterProps) =&gt; {
  const { theme = &quot;system&quot; } = useTheme()

  return (
    &lt;Sonner
      theme={theme as ToasterProps[&quot;theme&quot;]}
      className=&quot;toaster group&quot;
      toastOptions={{
        classNames: {
          toast:
            &quot;group toast group-[.toaster]:bg-background group-[.toaster]:text-foreground group-[.toaster]:border-border group-[.toaster]:shadow-lg&quot;,
          description: &quot;group-[.toast]:text-muted-foreground&quot;,
          actionButton:
            &quot;group-[.toast]:bg-primary group-[.toast]:text-primary-foreground&quot;,
          cancelButton:
            &quot;group-[.toast]:bg-muted group-[.toast]:text-muted-foreground&quot;,
        },
      }}
      {...props}
    /&gt;
  )
}

export { Toaster }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_switch-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/switch.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_switch-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_switch-tsx">import * as React from &quot;react&quot;
import * as SwitchPrimitives from &quot;@radix-ui/react-switch&quot;

import { cn } from &quot;@/lib/utils&quot;

const Switch = React.forwardRef&lt;
  React.ElementRef&lt;typeof SwitchPrimitives.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof SwitchPrimitives.Root&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;SwitchPrimitives.Root
    className={cn(
      &quot;peer inline-flex h-5 w-9 shrink-0 cursor-pointer items-center rounded-full border-2 border-transparent shadow-sm transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 focus-visible:ring-offset-background disabled:cursor-not-allowed disabled:opacity-50 data-[state=checked]:bg-primary data-[state=unchecked]:bg-input&quot;,
      className
    )}
    {...props}
    ref={ref}
  &gt;
    &lt;SwitchPrimitives.Thumb
      className={cn(
        &quot;pointer-events-none block h-4 w-4 rounded-full bg-background shadow-lg ring-0 transition-transform data-[state=checked]:translate-x-4 data-[state=unchecked]:translate-x-0&quot;
      )}
    /&gt;
  &lt;/SwitchPrimitives.Root&gt;
))
Switch.displayName = SwitchPrimitives.Root.displayName

export { Switch }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_table-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/table.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_table-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_table-tsx">import * as React from &quot;react&quot;

import { cn } from &quot;@/lib/utils&quot;

const Table = React.forwardRef&lt;
  HTMLTableElement,
  React.HTMLAttributes&lt;HTMLTableElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;div className=&quot;relative w-full overflow-auto&quot;&gt;
    &lt;table
      ref={ref}
      className={cn(&quot;w-full caption-bottom text-sm&quot;, className)}
      {...props}
    /&gt;
  &lt;/div&gt;
))
Table.displayName = &quot;Table&quot;

const TableHeader = React.forwardRef&lt;
  HTMLTableSectionElement,
  React.HTMLAttributes&lt;HTMLTableSectionElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;thead ref={ref} className={cn(&quot;[&amp;_tr]:border-b&quot;, className)} {...props} /&gt;
))
TableHeader.displayName = &quot;TableHeader&quot;

const TableBody = React.forwardRef&lt;
  HTMLTableSectionElement,
  React.HTMLAttributes&lt;HTMLTableSectionElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;tbody
    ref={ref}
    className={cn(&quot;[&amp;_tr:last-child]:border-0&quot;, className)}
    {...props}
  /&gt;
))
TableBody.displayName = &quot;TableBody&quot;

const TableFooter = React.forwardRef&lt;
  HTMLTableSectionElement,
  React.HTMLAttributes&lt;HTMLTableSectionElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;tfoot
    ref={ref}
    className={cn(
      &quot;border-t bg-muted/50 font-medium [&amp;&gt;tr]:last:border-b-0&quot;,
      className
    )}
    {...props}
  /&gt;
))
TableFooter.displayName = &quot;TableFooter&quot;

const TableRow = React.forwardRef&lt;
  HTMLTableRowElement,
  React.HTMLAttributes&lt;HTMLTableRowElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;tr
    ref={ref}
    className={cn(
      &quot;border-b transition-colors hover:bg-muted/50 data-[state=selected]:bg-muted&quot;,
      className
    )}
    {...props}
  /&gt;
))
TableRow.displayName = &quot;TableRow&quot;

const TableHead = React.forwardRef&lt;
  HTMLTableCellElement,
  React.ThHTMLAttributes&lt;HTMLTableCellElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;th
    ref={ref}
    className={cn(
      &quot;h-10 px-2 text-left align-middle font-medium text-muted-foreground [&amp;:has([role=checkbox])]:pr-0 [&amp;&gt;[role=checkbox]]:translate-y-[2px]&quot;,
      className
    )}
    {...props}
  /&gt;
))
TableHead.displayName = &quot;TableHead&quot;

const TableCell = React.forwardRef&lt;
  HTMLTableCellElement,
  React.TdHTMLAttributes&lt;HTMLTableCellElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;td
    ref={ref}
    className={cn(
      &quot;p-2 align-middle [&amp;:has([role=checkbox])]:pr-0 [&amp;&gt;[role=checkbox]]:translate-y-[2px]&quot;,
      className
    )}
    {...props}
  /&gt;
))
TableCell.displayName = &quot;TableCell&quot;

const TableCaption = React.forwardRef&lt;
  HTMLTableCaptionElement,
  React.HTMLAttributes&lt;HTMLTableCaptionElement&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;caption
    ref={ref}
    className={cn(&quot;mt-4 text-sm text-muted-foreground&quot;, className)}
    {...props}
  /&gt;
))
TableCaption.displayName = &quot;TableCaption&quot;

export {
  Table,
  TableHeader,
  TableBody,
  TableFooter,
  TableHead,
  TableRow,
  TableCell,
  TableCaption,
}
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_tabs-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/tabs.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_tabs-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_tabs-tsx">import * as React from &quot;react&quot;
import * as TabsPrimitive from &quot;@radix-ui/react-tabs&quot;

import { cn } from &quot;@/lib/utils&quot;

const Tabs = TabsPrimitive.Root

const TabsList = React.forwardRef&lt;
  React.ElementRef&lt;typeof TabsPrimitive.List&gt;,
  React.ComponentPropsWithoutRef&lt;typeof TabsPrimitive.List&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;TabsPrimitive.List
    ref={ref}
    className={cn(
      &quot;inline-flex h-9 items-center justify-center rounded-lg bg-muted p-1 text-muted-foreground&quot;,
      className
    )}
    {...props}
  /&gt;
))
TabsList.displayName = TabsPrimitive.List.displayName

const TabsTrigger = React.forwardRef&lt;
  React.ElementRef&lt;typeof TabsPrimitive.Trigger&gt;,
  React.ComponentPropsWithoutRef&lt;typeof TabsPrimitive.Trigger&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;TabsPrimitive.Trigger
    ref={ref}
    className={cn(
      &quot;inline-flex items-center justify-center whitespace-nowrap rounded-md px-3 py-1 text-sm font-medium ring-offset-background transition-all focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 data-[state=active]:bg-background data-[state=active]:text-foreground data-[state=active]:shadow&quot;,
      className
    )}
    {...props}
  /&gt;
))
TabsTrigger.displayName = TabsPrimitive.Trigger.displayName

const TabsContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof TabsPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof TabsPrimitive.Content&gt;
&gt;(({ className, ...props }, ref) =&gt; (
  &lt;TabsPrimitive.Content
    ref={ref}
    className={cn(
      &quot;mt-2 ring-offset-background focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2&quot;,
      className
    )}
    {...props}
  /&gt;
))
TabsContent.displayName = TabsPrimitive.Content.displayName

export { Tabs, TabsList, TabsTrigger, TabsContent }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_textarea-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/textarea.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_textarea-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_textarea-tsx">import * as React from &quot;react&quot;

import { cn } from &quot;@/lib/utils&quot;

const Textarea = React.forwardRef&lt;
  HTMLTextAreaElement,
  React.ComponentProps&lt;&quot;textarea&quot;&gt;
&gt;(({ className, ...props }, ref) =&gt; {
  return (
    &lt;textarea
      className={cn(
        &quot;flex min-h-[60px] w-full rounded-md border border-input bg-transparent px-3 py-2 text-base shadow-sm placeholder:text-muted-foreground focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring disabled:cursor-not-allowed disabled:opacity-50 md:text-sm&quot;,
        className
      )}
      ref={ref}
      {...props}
    /&gt;
  )
})
Textarea.displayName = &quot;Textarea&quot;

export { Textarea }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_toggle-group-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/toggle-group.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_toggle-group-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_toggle-group-tsx">import * as React from &quot;react&quot;
import * as ToggleGroupPrimitive from &quot;@radix-ui/react-toggle-group&quot;
import { type VariantProps } from &quot;class-variance-authority&quot;

import { cn } from &quot;@/lib/utils&quot;
import { toggleVariants } from &quot;@/components/ui/toggle&quot;

const ToggleGroupContext = React.createContext&lt;
  VariantProps&lt;typeof toggleVariants&gt;
&gt;({
  size: &quot;default&quot;,
  variant: &quot;default&quot;,
})

const ToggleGroup = React.forwardRef&lt;
  React.ElementRef&lt;typeof ToggleGroupPrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ToggleGroupPrimitive.Root&gt; &amp;
    VariantProps&lt;typeof toggleVariants&gt;
&gt;(({ className, variant, size, children, ...props }, ref) =&gt; (
  &lt;ToggleGroupPrimitive.Root
    ref={ref}
    className={cn(&quot;flex items-center justify-center gap-1&quot;, className)}
    {...props}
  &gt;
    &lt;ToggleGroupContext.Provider value={{ variant, size }}&gt;
      {children}
    &lt;/ToggleGroupContext.Provider&gt;
  &lt;/ToggleGroupPrimitive.Root&gt;
))

ToggleGroup.displayName = ToggleGroupPrimitive.Root.displayName

const ToggleGroupItem = React.forwardRef&lt;
  React.ElementRef&lt;typeof ToggleGroupPrimitive.Item&gt;,
  React.ComponentPropsWithoutRef&lt;typeof ToggleGroupPrimitive.Item&gt; &amp;
    VariantProps&lt;typeof toggleVariants&gt;
&gt;(({ className, children, variant, size, ...props }, ref) =&gt; {
  const context = React.useContext(ToggleGroupContext)

  return (
    &lt;ToggleGroupPrimitive.Item
      ref={ref}
      className={cn(
        toggleVariants({
          variant: context.variant || variant,
          size: context.size || size,
        }),
        className
      )}
      {...props}
    &gt;
      {children}
    &lt;/ToggleGroupPrimitive.Item&gt;
  )
})

ToggleGroupItem.displayName = ToggleGroupPrimitive.Item.displayName

export { ToggleGroup, ToggleGroupItem }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_toggle-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/toggle.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_toggle-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_toggle-tsx">import * as React from &quot;react&quot;
import * as TogglePrimitive from &quot;@radix-ui/react-toggle&quot;
import { cva, type VariantProps } from &quot;class-variance-authority&quot;

import { cn } from &quot;@/lib/utils&quot;

const toggleVariants = cva(
  &quot;inline-flex items-center justify-center gap-2 rounded-md text-sm font-medium transition-colors hover:bg-muted hover:text-muted-foreground focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring disabled:pointer-events-none disabled:opacity-50 data-[state=on]:bg-accent data-[state=on]:text-accent-foreground [&amp;_svg]:pointer-events-none [&amp;_svg]:size-4 [&amp;_svg]:shrink-0&quot;,
  {
    variants: {
      variant: {
        default: &quot;bg-transparent&quot;,
        outline:
          &quot;border border-input bg-transparent shadow-sm hover:bg-accent hover:text-accent-foreground&quot;,
      },
      size: {
        default: &quot;h-9 px-2 min-w-9&quot;,
        sm: &quot;h-8 px-1.5 min-w-8&quot;,
        lg: &quot;h-10 px-2.5 min-w-10&quot;,
      },
    },
    defaultVariants: {
      variant: &quot;default&quot;,
      size: &quot;default&quot;,
    },
  }
)

const Toggle = React.forwardRef&lt;
  React.ElementRef&lt;typeof TogglePrimitive.Root&gt;,
  React.ComponentPropsWithoutRef&lt;typeof TogglePrimitive.Root&gt; &amp;
    VariantProps&lt;typeof toggleVariants&gt;
&gt;(({ className, variant, size, ...props }, ref) =&gt; (
  &lt;TogglePrimitive.Root
    ref={ref}
    className={cn(toggleVariants({ variant, size, className }))}
    {...props}
  /&gt;
))

Toggle.displayName = TogglePrimitive.Root.displayName

export { Toggle, toggleVariants }
</code></pre>
</section>

<section class="file-section" id="f-src_components_ui_tooltip-tsx">
  <div class="file-header">
    <span class="file-path">src/components/ui/tooltip.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_components_ui_tooltip-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_components_ui_tooltip-tsx">&quot;use client&quot;

import * as React from &quot;react&quot;
import * as TooltipPrimitive from &quot;@radix-ui/react-tooltip&quot;

import { cn } from &quot;@/lib/utils&quot;

const TooltipProvider = TooltipPrimitive.Provider

const Tooltip = TooltipPrimitive.Root

const TooltipTrigger = TooltipPrimitive.Trigger

const TooltipContent = React.forwardRef&lt;
  React.ElementRef&lt;typeof TooltipPrimitive.Content&gt;,
  React.ComponentPropsWithoutRef&lt;typeof TooltipPrimitive.Content&gt;
&gt;(({ className, sideOffset = 4, ...props }, ref) =&gt; (
  &lt;TooltipPrimitive.Portal&gt;
    &lt;TooltipPrimitive.Content
      ref={ref}
      sideOffset={sideOffset}
      className={cn(
        &quot;z-50 overflow-hidden rounded-md bg-primary px-3 py-1.5 text-xs text-primary-foreground animate-in fade-in-0 zoom-in-95 data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=closed]:zoom-out-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 origin-[--radix-tooltip-content-transform-origin]&quot;,
        className
      )}
      {...props}
    /&gt;
  &lt;/TooltipPrimitive.Portal&gt;
))
TooltipContent.displayName = TooltipPrimitive.Content.displayName

export { Tooltip, TooltipTrigger, TooltipContent, TooltipProvider }
</code></pre>
</section>

<section class="file-section" id="f-src_routes_README-md">
  <div class="file-header">
    <span class="file-path">src/routes/README.md</span>
    <button class="copy-btn" onclick="copyCode('f-src_routes_README-md', this)">Copy</button>
  </div>
  <pre><code class="language-markdown" id="code-f-src_routes_README-md"># Routes

TanStack Start uses **file-based routing**. Every `.tsx` file in this directory
defines a route. Do **not** create `src/pages/`, `src/routes/_app/index.tsx`, or
`app/layout.tsx` — those are Next.js / Remix conventions. The only root layout
is `src/routes/__root.tsx`.

## Conventions

| File | URL |
| --- | --- |
| `index.tsx` | `/` |
| `about.tsx` | `/about` |
| `users/index.tsx` | `/users` |
| `users/$id.tsx` | `/users/:id` (dynamic — bare `$`, no curly braces) |
| `posts/{-$category}.tsx` | `/posts/:category?` (optional segment) |
| `files/$.tsx` | `/files/*` (splat — read via `_splat` param, never `*`) |
| `_layout.tsx` | layout route (renders children via `&lt;Outlet /&gt;`) |
| `__root.tsx` | app shell — wraps every page; preserve `&lt;Outlet /&gt;` |

`routeTree.gen.ts` is auto-generated. Don&#x27;t edit it by hand.
</code></pre>
</section>

<section class="file-section" id="f-src_routes___root-tsx">
  <div class="file-header">
    <span class="file-path">src/routes/__root.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_routes___root-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_routes___root-tsx">import { QueryClient, QueryClientProvider } from &quot;@tanstack/react-query&quot;;
import {
  Outlet,
  Link,
  createRootRouteWithContext,
  useRouter,
  HeadContent,
  Scripts,
} from &quot;@tanstack/react-router&quot;;
import { useEffect, type ReactNode } from &quot;react&quot;;
import { Toaster } from &quot;sonner&quot;;

import appCss from &quot;../styles.css?url&quot;;
import { reportLovableError } from &quot;../lib/lovable-error-reporting&quot;;

function NotFoundComponent() {
  return (
    &lt;div className=&quot;flex min-h-screen items-center justify-center bg-background px-4&quot;&gt;
      &lt;div className=&quot;max-w-md text-center&quot;&gt;
        &lt;h1 className=&quot;text-7xl font-bold text-foreground&quot;&gt;404&lt;/h1&gt;
        &lt;h2 className=&quot;mt-4 text-xl font-semibold text-foreground&quot;&gt;Page not found&lt;/h2&gt;
        &lt;p className=&quot;mt-2 text-sm text-muted-foreground&quot;&gt;
          The page you&#x27;re looking for doesn&#x27;t exist or has been moved.
        &lt;/p&gt;
        &lt;div className=&quot;mt-6&quot;&gt;
          &lt;Link
            to=&quot;/&quot;
            className=&quot;inline-flex items-center justify-center rounded-md bg-primary px-4 py-2 text-sm font-medium text-primary-foreground transition-colors hover:bg-primary/90&quot;
          &gt;
            Go home
          &lt;/Link&gt;
        &lt;/div&gt;
      &lt;/div&gt;
    &lt;/div&gt;
  );
}

function ErrorComponent({ error, reset }: { error: Error; reset: () =&gt; void }) {
  console.error(error);
  const router = useRouter();
  useEffect(() =&gt; {
    reportLovableError(error, { boundary: &quot;tanstack_root_error_component&quot; });
  }, [error]);

  return (
    &lt;div className=&quot;flex min-h-screen items-center justify-center bg-background px-4&quot;&gt;
      &lt;div className=&quot;max-w-md text-center&quot;&gt;
        &lt;h1 className=&quot;text-xl font-semibold tracking-tight text-foreground&quot;&gt;
          This page didn&#x27;t load
        &lt;/h1&gt;
        &lt;p className=&quot;mt-2 text-sm text-muted-foreground&quot;&gt;
          Something went wrong on our end. You can try refreshing or head back home.
        &lt;/p&gt;
        &lt;div className=&quot;mt-6 flex flex-wrap justify-center gap-2&quot;&gt;
          &lt;button
            onClick={() =&gt; {
              router.invalidate();
              reset();
            }}
            className=&quot;inline-flex items-center justify-center rounded-md bg-primary px-4 py-2 text-sm font-medium text-primary-foreground transition-colors hover:bg-primary/90&quot;
          &gt;
            Try again
          &lt;/button&gt;
          &lt;a
            href=&quot;/&quot;
            className=&quot;inline-flex items-center justify-center rounded-md border border-input bg-background px-4 py-2 text-sm font-medium text-foreground transition-colors hover:bg-accent&quot;
          &gt;
            Go home
          &lt;/a&gt;
        &lt;/div&gt;
      &lt;/div&gt;
    &lt;/div&gt;
  );
}

export const Route = createRootRouteWithContext&lt;{ queryClient: QueryClient }&gt;()({
  head: () =&gt; ({
    meta: [
      { charSet: &quot;utf-8&quot; },
      { name: &quot;viewport&quot;, content: &quot;width=device-width, initial-scale=1&quot; },
      { title: &quot;Momentum — goals that actually happen&quot; },
      { name: &quot;description&quot;, content: &quot;Calibrate ambitious goals, break them into daily steps, and keep the streak alive.&quot; },
      { property: &quot;og:title&quot;, content: &quot;Momentum — goals that actually happen&quot; },
      { property: &quot;og:description&quot;, content: &quot;Calibrate ambitious goals, break them into daily steps, and keep the streak alive.&quot; },
      { property: &quot;og:type&quot;, content: &quot;website&quot; },
      { name: &quot;twitter:card&quot;, content: &quot;summary_large_image&quot; },
      { name: &quot;twitter:title&quot;, content: &quot;Momentum — goals that actually happen&quot; },
      { name: &quot;twitter:description&quot;, content: &quot;Calibrate ambitious goals, break them into daily steps, and keep the streak alive.&quot; },
      { property: &quot;og:image&quot;, content: &quot;https://pub-bb2e103a32db4e198524a2e9ed8f35b4.r2.dev/1355d92c-9a35-42d7-986d-5694fad35ef6/id-preview-2099627c--481dd7cf-21b7-4bee-a5ff-610bc98965ab.lovable.app-1783509413924.png&quot; },
      { name: &quot;twitter:image&quot;, content: &quot;https://pub-bb2e103a32db4e198524a2e9ed8f35b4.r2.dev/1355d92c-9a35-42d7-986d-5694fad35ef6/id-preview-2099627c--481dd7cf-21b7-4bee-a5ff-610bc98965ab.lovable.app-1783509413924.png&quot; },
    ],
    links: [
      { rel: &quot;stylesheet&quot;, href: appCss },
      { rel: &quot;icon&quot;, href: &quot;/favicon.ico&quot;, type: &quot;image/x-icon&quot; },
      { rel: &quot;preconnect&quot;, href: &quot;https://fonts.googleapis.com&quot; },
      { rel: &quot;preconnect&quot;, href: &quot;https://fonts.gstatic.com&quot;, crossOrigin: &quot;anonymous&quot; },
      { rel: &quot;stylesheet&quot;, href: &quot;https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,600;9..144,700&amp;family=Manrope:wght@400;500;600;700;800&amp;display=swap&quot; },
    ],
  }),
  shellComponent: RootShell,
  component: RootComponent,
  notFoundComponent: NotFoundComponent,
  errorComponent: ErrorComponent,
});

function RootShell({ children }: { children: ReactNode }) {
  return (
    &lt;html lang=&quot;en&quot;&gt;
      &lt;head&gt;
        &lt;HeadContent /&gt;
      &lt;/head&gt;
      &lt;body&gt;
        {children}
        &lt;Scripts /&gt;
      &lt;/body&gt;
    &lt;/html&gt;
  );
}

function RootComponent() {
  const { queryClient } = Route.useRouteContext();
  const router = useRouter();

  useEffect(() =&gt; {
    let mounted = true;
    // dynamic import to keep browser-only supabase out of SSR module graph
    import(&quot;@/integrations/supabase/client&quot;).then(({ supabase }) =&gt; {
      if (!mounted) return;
      const { data: sub } = supabase.auth.onAuthStateChange((event) =&gt; {
        if (event !== &quot;SIGNED_IN&quot; &amp;&amp; event !== &quot;SIGNED_OUT&quot; &amp;&amp; event !== &quot;USER_UPDATED&quot;) return;
        router.invalidate();
        if (event !== &quot;SIGNED_OUT&quot;) queryClient.invalidateQueries();
      });
      // store cleanup on the closure
      (window as unknown as { __momentumAuthSub?: { unsubscribe: () =&gt; void } }).__momentumAuthSub = sub.subscription;
    });
    return () =&gt; {
      mounted = false;
      const w = window as unknown as { __momentumAuthSub?: { unsubscribe: () =&gt; void } };
      w.__momentumAuthSub?.unsubscribe();
    };
  }, [queryClient, router]);

  return (
    &lt;QueryClientProvider client={queryClient}&gt;
      &lt;Outlet /&gt;
      &lt;Toaster position=&quot;top-center&quot; richColors /&gt;
    &lt;/QueryClientProvider&gt;
  );
}
</code></pre>
</section>

<section class="file-section" id="f-src_routes__authenticated_dashboard-tsx">
  <div class="file-header">
    <span class="file-path">src/routes/_authenticated/dashboard.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_routes__authenticated_dashboard-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_routes__authenticated_dashboard-tsx">import { createFileRoute, Link, useNavigate } from &quot;@tanstack/react-router&quot;;
import { useQuery } from &quot;@tanstack/react-query&quot;;
import { supabase } from &quot;@/integrations/supabase/client&quot;;
import { AppShell } from &quot;@/components/app-shell&quot;;
import { Button } from &quot;@/components/ui/button&quot;;
import { Card } from &quot;@/components/ui/card&quot;;
import { Progress } from &quot;@/components/ui/progress&quot;;
import { Flame, Plus, Target, Calendar, TrendingUp } from &quot;lucide-react&quot;;
import { calcStreak, toISO } from &quot;@/lib/streak&quot;;
import { useEffect, useState } from &quot;react&quot;;

export const Route = createFileRoute(&quot;/_authenticated/dashboard&quot;)({
  component: Dashboard,
});

function Dashboard() {
  const navigate = useNavigate();
  const [userId, setUserId] = useState&lt;string | null&gt;(null);
  useEffect(() =&gt; {
    supabase.auth.getUser().then(({ data }) =&gt; setUserId(data.user?.id ?? null));
  }, []);

  const { data, isLoading } = useQuery({
    queryKey: [&quot;dashboard&quot;, userId],
    enabled: !!userId,
    queryFn: async () =&gt; {
      const [g, t, a, c, f] = await Promise.all([
        supabase.from(&quot;goals&quot;).select(&quot;*&quot;).eq(&quot;status&quot;, &quot;active&quot;).order(&quot;created_at&quot;, { ascending: false }),
        supabase.from(&quot;tasks&quot;).select(&quot;id,goal_id,completed,week_number&quot;),
        supabase.from(&quot;daily_actions&quot;).select(&quot;id,goal_id,active&quot;),
        supabase.from(&quot;action_completions&quot;).select(&quot;completed_date,daily_action_id&quot;),
        supabase.from(&quot;streak_freezes&quot;).select(&quot;freeze_date,goal_id&quot;),
      ]);
      return {
        goals: g.data ?? [],
        tasks: t.data ?? [],
        actions: a.data ?? [],
        completions: c.data ?? [],
        freezes: f.data ?? [],
      };
    },
  });

  if (isLoading || !data) {
    return &lt;AppShell&gt;&lt;p className=&quot;text-muted-foreground&quot;&gt;Loading…&lt;/p&gt;&lt;/AppShell&gt;;
  }

  // Overall streak: any completion across account
  const allCompleted = new Set(data.completions.map((c) =&gt; c.completed_date));
  const allFreezes = new Set(data.freezes.map((f) =&gt; f.freeze_date));
  const overall = calcStreak(allCompleted, allFreezes);

  if (data.goals.length === 0) {
    return (
      &lt;AppShell streakTotal={overall.current}&gt;
        &lt;EmptyState onStart={() =&gt; navigate({ to: &quot;/goals/new&quot; })} /&gt;
      &lt;/AppShell&gt;
    );
  }

  const today = toISO(new Date());

  return (
    &lt;AppShell streakTotal={overall.current}&gt;
      &lt;div className=&quot;mb-8 flex items-start justify-between gap-4&quot;&gt;
        &lt;div&gt;
          &lt;h1 className=&quot;font-display text-3xl font-semibold sm:text-4xl&quot;&gt;Your goals&lt;/h1&gt;
          &lt;p className=&quot;mt-1 text-muted-foreground&quot;&gt;
            {overall.current &gt; 0
              ? `You&#x27;re on a ${overall.current}-day streak. Keep going.`
              : &quot;Check in today to start your streak.&quot;}
          &lt;/p&gt;
        &lt;/div&gt;
      &lt;/div&gt;

      &lt;div className=&quot;grid gap-4 sm:grid-cols-2&quot;&gt;
        {data.goals.map((goal) =&gt; {
          const goalActions = data.actions.filter((a) =&gt; a.goal_id === goal.id);
          const actionIds = new Set(goalActions.map((a) =&gt; a.id));
          const goalCompletions = new Set(
            data.completions.filter((c) =&gt; actionIds.has(c.daily_action_id)).map((c) =&gt; c.completed_date)
          );
          const goalFreezes = new Set(data.freezes.filter((f) =&gt; f.goal_id === goal.id).map((f) =&gt; f.freeze_date));
          const streak = calcStreak(goalCompletions, goalFreezes);

          const goalTasks = data.tasks.filter((t) =&gt; t.goal_id === goal.id);
          const currentWeek = Math.max(1, ...goalTasks.map((t) =&gt; t.week_number));
          const sprintTasks = goalTasks.filter((t) =&gt; t.week_number === currentWeek);
          const sprintDone = sprintTasks.filter((t) =&gt; t.completed).length;
          const sprintPct = sprintTasks.length ? Math.round((sprintDone / sprintTasks.length) * 100) : 0;

          const doneToday = goalActions.some((a) =&gt; goalCompletions.has(today));
          const daysToDeadline = goal.calibrated_deadline
            ? Math.max(0, Math.ceil((new Date(goal.calibrated_deadline).getTime() - Date.now()) / 86400000))
            : null;

          const status = doneToday
            ? { label: &quot;On track today&quot;, tone: &quot;success&quot; as const }
            : streak.current &gt; 0
            ? { label: &quot;Check in today&quot;, tone: &quot;primary&quot; as const }
            : { label: &quot;Get started&quot;, tone: &quot;muted&quot; as const };

          return (
            &lt;Link key={goal.id} to=&quot;/goals/$id&quot; params={{ id: goal.id }} className=&quot;group&quot;&gt;
              &lt;Card className=&quot;h-full p-5 transition-all hover:shadow-soft hover:-translate-y-0.5&quot;&gt;
                &lt;div className=&quot;flex items-start justify-between gap-3&quot;&gt;
                  &lt;div className=&quot;min-w-0 flex-1&quot;&gt;
                    &lt;h3 className=&quot;font-display text-xl font-semibold leading-tight&quot;&gt;
                      {goal.calibrated_target || goal.title}
                    &lt;/h3&gt;
                    {goal.difficulty_tier &amp;&amp; (
                      &lt;span className=&quot;mt-2 inline-block rounded-full bg-accent px-2 py-0.5 text-xs font-medium text-accent-foreground&quot;&gt;
                        {goal.difficulty_tier.replace(&quot;_&quot;, &quot; &quot;)}
                      &lt;/span&gt;
                    )}
                  &lt;/div&gt;
                  &lt;div className=&quot;flex flex-col items-center rounded-xl bg-primary/10 px-3 py-2 text-primary&quot;&gt;
                    &lt;Flame className={`h-5 w-5 ${streak.current &gt; 0 ? &quot;animate-flame&quot; : &quot;opacity-50&quot;}`} /&gt;
                    &lt;span className=&quot;text-sm font-bold&quot;&gt;{streak.current}&lt;/span&gt;
                  &lt;/div&gt;
                &lt;/div&gt;

                &lt;div className=&quot;mt-4 space-y-2 text-sm&quot;&gt;
                  &lt;div className=&quot;flex items-center justify-between text-muted-foreground&quot;&gt;
                    &lt;span className=&quot;flex items-center gap-1.5&quot;&gt;&lt;Target className=&quot;h-3.5 w-3.5&quot; /&gt; Week {currentWeek} sprint&lt;/span&gt;
                    &lt;span className=&quot;font-medium text-foreground&quot;&gt;{sprintDone}/{sprintTasks.length}&lt;/span&gt;
                  &lt;/div&gt;
                  &lt;Progress value={sprintPct} className=&quot;h-2&quot; /&gt;
                  &lt;div className=&quot;flex items-center justify-between pt-1 text-xs&quot;&gt;
                    {daysToDeadline !== null &amp;&amp; (
                      &lt;span className=&quot;flex items-center gap-1 text-muted-foreground&quot;&gt;
                        &lt;Calendar className=&quot;h-3 w-3&quot; /&gt; {daysToDeadline}d to deadline
                      &lt;/span&gt;
                    )}
                    &lt;span className={
                      status.tone === &quot;success&quot; ? &quot;font-medium text-success&quot; :
                      status.tone === &quot;primary&quot; ? &quot;font-medium text-primary&quot; :
                      &quot;text-muted-foreground&quot;
                    }&gt;{status.label}&lt;/span&gt;
                  &lt;/div&gt;
                &lt;/div&gt;
              &lt;/Card&gt;
            &lt;/Link&gt;
          );
        })}

        &lt;Link to=&quot;/goals/new&quot; className=&quot;group&quot;&gt;
          &lt;Card className=&quot;flex h-full min-h-[180px] items-center justify-center border-dashed p-6 transition-colors hover:bg-accent/40&quot;&gt;
            &lt;div className=&quot;text-center&quot;&gt;
              &lt;div className=&quot;mx-auto flex h-10 w-10 items-center justify-center rounded-full bg-primary/10 text-primary&quot;&gt;
                &lt;Plus className=&quot;h-5 w-5&quot; /&gt;
              &lt;/div&gt;
              &lt;p className=&quot;mt-2 font-medium&quot;&gt;Add a new goal&lt;/p&gt;
              &lt;p className=&quot;text-xs text-muted-foreground&quot;&gt;Calibrate it against reality&lt;/p&gt;
            &lt;/div&gt;
          &lt;/Card&gt;
        &lt;/Link&gt;
      &lt;/div&gt;

      &lt;div className=&quot;mt-10 grid gap-4 sm:grid-cols-3&quot;&gt;
        &lt;StatCard label=&quot;Longest streak&quot; value={overall.longest} icon={&lt;Flame className=&quot;h-4 w-4&quot; /&gt;} /&gt;
        &lt;StatCard label=&quot;Active goals&quot; value={data.goals.length} icon={&lt;Target className=&quot;h-4 w-4&quot; /&gt;} /&gt;
        &lt;StatCard label=&quot;Check-ins (30d)&quot; value={countLast(data.completions.map((c) =&gt; c.completed_date), 30)} icon={&lt;TrendingUp className=&quot;h-4 w-4&quot; /&gt;} /&gt;
      &lt;/div&gt;
    &lt;/AppShell&gt;
  );
}

function StatCard({ label, value, icon }: { label: string; value: number; icon: React.ReactNode }) {
  return (
    &lt;Card className=&quot;p-5&quot;&gt;
      &lt;div className=&quot;flex items-center gap-2 text-sm text-muted-foreground&quot;&gt;{icon}{label}&lt;/div&gt;
      &lt;p className=&quot;mt-2 font-display text-3xl font-semibold&quot;&gt;{value}&lt;/p&gt;
    &lt;/Card&gt;
  );
}

function countLast(dates: string[], n: number) {
  const cutoff = Date.now() - n * 86400000;
  return new Set(dates.filter((d) =&gt; new Date(d).getTime() &gt;= cutoff)).size;
}

function EmptyState({ onStart }: { onStart: () =&gt; void }) {
  return (
    &lt;div className=&quot;mx-auto max-w-lg pt-8 text-center&quot;&gt;
      &lt;div className=&quot;mx-auto flex h-16 w-16 items-center justify-center rounded-2xl bg-primary/10&quot;&gt;
        &lt;Flame className=&quot;h-8 w-8 text-primary animate-flame&quot; /&gt;
      &lt;/div&gt;
      &lt;h1 className=&quot;mt-6 font-display text-3xl font-semibold&quot;&gt;Set your first goal&lt;/h1&gt;
      &lt;p className=&quot;mt-2 text-muted-foreground&quot;&gt;
        We&#x27;ll calibrate it against your baseline, break it into weekly sprints, and turn it into a streak worth protecting.
      &lt;/p&gt;
      &lt;Button size=&quot;lg&quot; className=&quot;mt-6&quot; onClick={onStart}&gt;Start now&lt;/Button&gt;
    &lt;/div&gt;
  );
}
</code></pre>
</section>

<section class="file-section" id="f-src_routes__authenticated_goals-Sid-tsx">
  <div class="file-header">
    <span class="file-path">src/routes/_authenticated/goals.$id.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_routes__authenticated_goals-Sid-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_routes__authenticated_goals-Sid-tsx">import { createFileRoute, Link } from &quot;@tanstack/react-router&quot;;
import { useQuery, useQueryClient } from &quot;@tanstack/react-query&quot;;
import { supabase } from &quot;@/integrations/supabase/client&quot;;
import { AppShell } from &quot;@/components/app-shell&quot;;
import { Card } from &quot;@/components/ui/card&quot;;
import { Button } from &quot;@/components/ui/button&quot;;
import { Checkbox } from &quot;@/components/ui/checkbox&quot;;
import { Tabs, TabsList, TabsTrigger, TabsContent } from &quot;@/components/ui/tabs&quot;;
import { Flame, ArrowLeft, Snowflake, Sparkles, Calendar as CalIcon, Target } from &quot;lucide-react&quot;;
import { calcStreak, toISO } from &quot;@/lib/streak&quot;;
import { useEffect, useMemo, useState } from &quot;react&quot;;
import { toast } from &quot;sonner&quot;;

export const Route = createFileRoute(&quot;/_authenticated/goals/$id&quot;)({
  component: GoalDetail,
});

function GoalDetail() {
  const { id } = Route.useParams();
  const qc = useQueryClient();
  const [userId, setUserId] = useState&lt;string | null&gt;(null);
  useEffect(() =&gt; { supabase.auth.getUser().then(({ data }) =&gt; setUserId(data.user?.id ?? null)); }, []);

  const { data, isLoading } = useQuery({
    queryKey: [&quot;goal&quot;, id],
    queryFn: async () =&gt; {
      const [g, t, a, c, f, p] = await Promise.all([
        supabase.from(&quot;goals&quot;).select(&quot;*&quot;).eq(&quot;id&quot;, id).single(),
        supabase.from(&quot;tasks&quot;).select(&quot;*&quot;).eq(&quot;goal_id&quot;, id).order(&quot;week_number&quot;).order(&quot;sprint_order&quot;),
        supabase.from(&quot;daily_actions&quot;).select(&quot;*&quot;).eq(&quot;goal_id&quot;, id).eq(&quot;active&quot;, true),
        supabase.from(&quot;action_completions&quot;).select(&quot;*&quot;),
        supabase.from(&quot;streak_freezes&quot;).select(&quot;*&quot;).eq(&quot;goal_id&quot;, id),
        supabase.from(&quot;profiles&quot;).select(&quot;freeze_credits&quot;).maybeSingle(),
      ]);
      return {
        goal: g.data,
        tasks: t.data ?? [],
        actions: a.data ?? [],
        completions: c.data ?? [],
        freezes: f.data ?? [],
        freezeCredits: p.data?.freeze_credits ?? 0,
      };
    },
  });

  const invalidate = () =&gt; qc.invalidateQueries({ queryKey: [&quot;goal&quot;, id] });

  if (isLoading || !data?.goal) return &lt;AppShell&gt;&lt;p className=&quot;text-muted-foreground&quot;&gt;Loading…&lt;/p&gt;&lt;/AppShell&gt;;

  const { goal, tasks, actions, completions, freezes, freezeCredits } = data;
  const actionIds = new Set(actions.map((a) =&gt; a.id));
  const goalCompletions = completions.filter((c) =&gt; actionIds.has(c.daily_action_id));
  const completedDates = new Set(goalCompletions.map((c) =&gt; c.completed_date));
  const freezeDates = new Set(freezes.map((f) =&gt; f.freeze_date));
  const streak = calcStreak(completedDates, freezeDates);

  const toggleTask = async (taskId: string, completed: boolean) =&gt; {
    await supabase.from(&quot;tasks&quot;).update({ completed, completed_at: completed ? new Date().toISOString() : null }).eq(&quot;id&quot;, taskId);
    invalidate();
  };

  const toggleAction = async (actionId: string, date: string, currentlyDone: boolean) =&gt; {
    if (currentlyDone) {
      await supabase.from(&quot;action_completions&quot;).delete().eq(&quot;daily_action_id&quot;, actionId).eq(&quot;completed_date&quot;, date);
    } else {
      const { error } = await supabase.from(&quot;action_completions&quot;).insert({ daily_action_id: actionId, user_id: userId!, completed_date: date });
      if (error) { toast.error(error.message); return; }
      if (date === toISO(new Date())) {
        confetti();
        toast.success(&quot;Check-in locked in!&quot;, { icon: &quot;🔥&quot; });
      }
    }
    invalidate();
  };

  const applyFreeze = async (date: string) =&gt; {
    if (freezeCredits &lt;= 0) { toast.error(&quot;No freezes left this month.&quot;); return; }
    const { error } = await supabase.from(&quot;streak_freezes&quot;).insert({ user_id: userId!, goal_id: goal.id, freeze_date: date });
    if (error) { toast.error(error.message); return; }
    await supabase.from(&quot;profiles&quot;).update({ freeze_credits: freezeCredits - 1 }).eq(&quot;id&quot;, userId!);
    toast.success(&quot;Streak protected&quot;, { icon: &quot;❄️&quot; });
    invalidate();
  };

  return (
    &lt;AppShell streakTotal={streak.current}&gt;
      &lt;Link to=&quot;/dashboard&quot; className=&quot;mb-4 inline-flex items-center gap-1 text-sm text-muted-foreground hover:text-foreground&quot;&gt;
        &lt;ArrowLeft className=&quot;h-4 w-4&quot; /&gt; Dashboard
      &lt;/Link&gt;

      &lt;div className=&quot;mb-6 flex flex-wrap items-start justify-between gap-4&quot;&gt;
        &lt;div className=&quot;min-w-0 flex-1&quot;&gt;
          &lt;h1 className=&quot;font-display text-3xl font-semibold sm:text-4xl&quot;&gt;{goal.calibrated_target || goal.title}&lt;/h1&gt;
          &lt;div className=&quot;mt-2 flex flex-wrap items-center gap-3 text-sm text-muted-foreground&quot;&gt;
            {goal.calibrated_deadline &amp;&amp; &lt;span className=&quot;inline-flex items-center gap-1&quot;&gt;&lt;CalIcon className=&quot;h-3.5 w-3.5&quot; /&gt; {goal.calibrated_deadline}&lt;/span&gt;}
            {goal.difficulty_tier &amp;&amp; &lt;span className=&quot;rounded-full bg-accent px-2 py-0.5 text-xs capitalize text-accent-foreground&quot;&gt;{goal.difficulty_tier.replace(&quot;_&quot;, &quot; &quot;)}&lt;/span&gt;}
            {goal.calibrated_metric &amp;&amp; &lt;span className=&quot;inline-flex items-center gap-1&quot;&gt;&lt;Target className=&quot;h-3.5 w-3.5&quot; /&gt; {goal.calibrated_metric}&lt;/span&gt;}
          &lt;/div&gt;
        &lt;/div&gt;
        &lt;StreakBadge current={streak.current} longest={streak.longest} freezeCredits={freezeCredits} /&gt;
      &lt;/div&gt;

      {goal.why_motivation &amp;&amp; (
        &lt;Card className=&quot;mb-6 border-primary/20 bg-primary/5 p-4&quot;&gt;
          &lt;p className=&quot;text-xs font-medium uppercase tracking-wide text-primary flex items-center gap-1&quot;&gt;&lt;Sparkles className=&quot;h-3 w-3&quot; /&gt; Why this matters&lt;/p&gt;
          &lt;p className=&quot;mt-1 text-sm&quot;&gt;{goal.why_motivation}&lt;/p&gt;
        &lt;/Card&gt;
      )}

      &lt;Tabs defaultValue=&quot;habits&quot;&gt;
        &lt;TabsList className=&quot;grid w-full max-w-sm grid-cols-2&quot;&gt;
          &lt;TabsTrigger value=&quot;habits&quot;&gt;Habits&lt;/TabsTrigger&gt;
          &lt;TabsTrigger value=&quot;roadmap&quot;&gt;Roadmap&lt;/TabsTrigger&gt;
        &lt;/TabsList&gt;

        &lt;TabsContent value=&quot;habits&quot; className=&quot;mt-6&quot;&gt;
          &lt;HabitsGrid actions={actions} completions={goalCompletions} freezes={freezes} onToggle={toggleAction} onFreeze={applyFreeze} freezeCredits={freezeCredits} userId={userId} /&gt;
        &lt;/TabsContent&gt;

        &lt;TabsContent value=&quot;roadmap&quot; className=&quot;mt-6&quot;&gt;
          &lt;Roadmap tasks={tasks} onToggle={toggleTask} /&gt;
        &lt;/TabsContent&gt;
      &lt;/Tabs&gt;
    &lt;/AppShell&gt;
  );
}

function StreakBadge({ current, longest, freezeCredits }: { current: number; longest: number; freezeCredits: number }) {
  return (
    &lt;div className=&quot;flex items-center gap-3 rounded-2xl border border-primary/20 bg-gradient-to-br from-primary/10 to-primary/5 px-4 py-3&quot;&gt;
      &lt;Flame className={`h-8 w-8 text-primary ${current &gt; 0 ? &quot;animate-flame&quot; : &quot;opacity-40&quot;}`} /&gt;
      &lt;div className=&quot;text-sm&quot;&gt;
        &lt;p className=&quot;font-display text-2xl font-bold leading-none&quot;&gt;{current}&lt;/p&gt;
        &lt;p className=&quot;text-xs text-muted-foreground&quot;&gt;day streak · best {longest}&lt;/p&gt;
        &lt;p className=&quot;mt-0.5 flex items-center gap-1 text-xs text-secondary-foreground/70&quot;&gt;&lt;Snowflake className=&quot;h-3 w-3&quot; /&gt; {freezeCredits} freezes left&lt;/p&gt;
      &lt;/div&gt;
    &lt;/div&gt;
  );
}

type DailyAction = { id: string; title: string; description: string | null };
type Completion = { daily_action_id: string; completed_date: string };
type Freeze = { freeze_date: string };

function HabitsGrid({ actions, completions, freezes, onToggle, onFreeze, freezeCredits, userId }: {
  actions: DailyAction[];
  completions: Completion[];
  freezes: Freeze[];
  onToggle: (id: string, date: string, done: boolean) =&gt; void;
  onFreeze: (date: string) =&gt; void;
  freezeCredits: number;
  userId: string | null;
}) {
  const days = useMemo(() =&gt; {
    const arr: string[] = [];
    const today = new Date();
    for (let i = 29; i &gt;= 0; i--) {
      const d = new Date(today);
      d.setDate(d.getDate() - i);
      arr.push(toISO(d));
    }
    return arr;
  }, []);

  const freezeSet = new Set(freezes.map((f) =&gt; f.freeze_date));

  if (actions.length === 0) {
    return &lt;Card className=&quot;p-8 text-center text-muted-foreground&quot;&gt;No daily habits yet. Rebuild your roadmap to generate them.&lt;/Card&gt;;
  }

  const compMap = new Map&lt;string, Set&lt;string&gt;&gt;();
  completions.forEach((c) =&gt; {
    if (!compMap.has(c.daily_action_id)) compMap.set(c.daily_action_id, new Set());
    compMap.get(c.daily_action_id)!.add(c.completed_date);
  });

  const today = toISO(new Date());

  return (
    &lt;div className=&quot;space-y-6&quot;&gt;
      {/* Today check-in */}
      &lt;Card className=&quot;p-5&quot;&gt;
        &lt;div className=&quot;flex items-center justify-between&quot;&gt;
          &lt;h3 className=&quot;font-display text-lg font-semibold&quot;&gt;Today · {today}&lt;/h3&gt;
          &lt;Button size=&quot;sm&quot; variant=&quot;outline&quot; className=&quot;gap-1&quot; disabled={freezeCredits &lt;= 0 || freezeSet.has(today)} onClick={() =&gt; onFreeze(today)}&gt;
            &lt;Snowflake className=&quot;h-3.5 w-3.5&quot; /&gt; Freeze today
          &lt;/Button&gt;
        &lt;/div&gt;
        &lt;div className=&quot;mt-4 space-y-2&quot;&gt;
          {actions.map((a) =&gt; {
            const done = compMap.get(a.id)?.has(today) ?? false;
            return (
              &lt;label key={a.id} className={`flex cursor-pointer items-start gap-3 rounded-xl border p-3 transition-all ${done ? &quot;border-success/40 bg-success/5&quot; : &quot;border-border hover:bg-accent/30&quot;}`}&gt;
                &lt;Checkbox checked={done} onCheckedChange={() =&gt; userId &amp;&amp; onToggle(a.id, today, done)} className=&quot;mt-0.5&quot; /&gt;
                &lt;div className=&quot;flex-1&quot;&gt;
                  &lt;p className={`font-medium ${done ? &quot;line-through opacity-60&quot; : &quot;&quot;}`}&gt;{a.title}&lt;/p&gt;
                  {a.description &amp;&amp; &lt;p className=&quot;text-sm text-muted-foreground&quot;&gt;{a.description}&lt;/p&gt;}
                &lt;/div&gt;
                {done &amp;&amp; &lt;span className=&quot;animate-pop text-2xl&quot;&gt;🔥&lt;/span&gt;}
              &lt;/label&gt;
            );
          })}
        &lt;/div&gt;
      &lt;/Card&gt;

      {/* 30-day grid */}
      &lt;Card className=&quot;p-5&quot;&gt;
        &lt;h3 className=&quot;font-display text-lg font-semibold&quot;&gt;Last 30 days&lt;/h3&gt;
        &lt;div className=&quot;mt-4 space-y-3 overflow-x-auto&quot;&gt;
          {actions.map((a) =&gt; {
            const set = compMap.get(a.id) ?? new Set&lt;string&gt;();
            return (
              &lt;div key={a.id}&gt;
                &lt;p className=&quot;mb-1 text-sm font-medium&quot;&gt;{a.title}&lt;/p&gt;
                &lt;div className=&quot;flex gap-1&quot;&gt;
                  {days.map((d) =&gt; {
                    const done = set.has(d);
                    const froze = freezeSet.has(d);
                    return (
                      &lt;button
                        key={d}
                        type=&quot;button&quot;
                        aria-label={d}
                        onClick={() =&gt; userId &amp;&amp; onToggle(a.id, d, done)}
                        className={`h-6 w-6 rounded-md text-[10px] transition-transform hover:scale-110 ${
                          done ? &quot;bg-primary text-primary-foreground&quot; :
                          froze ? &quot;bg-secondary text-secondary-foreground&quot; :
                          &quot;bg-muted&quot;
                        }`}
                        title={d}
                      &gt;
                        {done ? &quot;✓&quot; : froze ? &quot;❄&quot; : &quot;&quot;}
                      &lt;/button&gt;
                    );
                  })}
                &lt;/div&gt;
              &lt;/div&gt;
            );
          })}
        &lt;/div&gt;
        &lt;div className=&quot;mt-4 flex items-center gap-4 text-xs text-muted-foreground&quot;&gt;
          &lt;span className=&quot;flex items-center gap-1&quot;&gt;&lt;span className=&quot;inline-block h-3 w-3 rounded-sm bg-primary&quot; /&gt; done&lt;/span&gt;
          &lt;span className=&quot;flex items-center gap-1&quot;&gt;&lt;span className=&quot;inline-block h-3 w-3 rounded-sm bg-secondary&quot; /&gt; freeze&lt;/span&gt;
          &lt;span className=&quot;flex items-center gap-1&quot;&gt;&lt;span className=&quot;inline-block h-3 w-3 rounded-sm bg-muted&quot; /&gt; empty&lt;/span&gt;
        &lt;/div&gt;
      &lt;/Card&gt;
    &lt;/div&gt;
  );
}

type Task = { id: string; title: string; description: string | null; week_number: number; completed: boolean; estimated_hours: number | null; if_then_plans: unknown };

function Roadmap({ tasks, onToggle }: { tasks: Task[]; onToggle: (id: string, c: boolean) =&gt; void }) {
  if (tasks.length === 0) return &lt;Card className=&quot;p-8 text-center text-muted-foreground&quot;&gt;No tasks yet.&lt;/Card&gt;;
  const byWeek = new Map&lt;number, Task[]&gt;();
  tasks.forEach((t) =&gt; {
    if (!byWeek.has(t.week_number)) byWeek.set(t.week_number, []);
    byWeek.get(t.week_number)!.push(t);
  });
  const weeks = Array.from(byWeek.keys()).sort((a, b) =&gt; a - b);

  return (
    &lt;div className=&quot;space-y-6&quot;&gt;
      {weeks.map((w) =&gt; {
        const ws = byWeek.get(w)!;
        const done = ws.filter((t) =&gt; t.completed).length;
        return (
          &lt;Card key={w} className=&quot;p-5&quot;&gt;
            &lt;div className=&quot;mb-4 flex items-center justify-between&quot;&gt;
              &lt;h3 className=&quot;font-display text-xl font-semibold&quot;&gt;Week {w}&lt;/h3&gt;
              &lt;span className=&quot;text-sm text-muted-foreground&quot;&gt;{done}/{ws.length} done&lt;/span&gt;
            &lt;/div&gt;
            &lt;div className=&quot;space-y-2&quot;&gt;
              {ws.map((t) =&gt; {
                const plans = Array.isArray(t.if_then_plans) ? t.if_then_plans as Array&lt;{ trigger: string; response: string }&gt; : [];
                return (
                  &lt;div key={t.id} className={`rounded-xl border p-3 transition-all ${t.completed ? &quot;border-success/30 bg-success/5&quot; : &quot;border-border&quot;}`}&gt;
                    &lt;label className=&quot;flex cursor-pointer items-start gap-3&quot;&gt;
                      &lt;Checkbox checked={t.completed} onCheckedChange={(v) =&gt; onToggle(t.id, !!v)} className=&quot;mt-1&quot; /&gt;
                      &lt;div className=&quot;flex-1&quot;&gt;
                        &lt;div className=&quot;flex items-start justify-between gap-2&quot;&gt;
                          &lt;p className={`font-medium ${t.completed ? &quot;line-through opacity-60&quot; : &quot;&quot;}`}&gt;{t.title}&lt;/p&gt;
                          {t.estimated_hours &amp;&amp; &lt;span className=&quot;shrink-0 rounded-full bg-muted px-2 py-0.5 text-xs text-muted-foreground&quot;&gt;{t.estimated_hours}h&lt;/span&gt;}
                        &lt;/div&gt;
                        {t.description &amp;&amp; &lt;p className=&quot;mt-1 text-sm text-muted-foreground&quot;&gt;{t.description}&lt;/p&gt;}
                        {plans.length &gt; 0 &amp;&amp; (
                          &lt;div className=&quot;mt-2 space-y-1&quot;&gt;
                            {plans.map((p, i) =&gt; (
                              &lt;p key={i} className=&quot;text-xs text-secondary-foreground/80&quot;&gt;&lt;span className=&quot;font-semibold&quot;&gt;If&lt;/span&gt; {p.trigger} &lt;span className=&quot;font-semibold&quot;&gt;then&lt;/span&gt; {p.response}&lt;/p&gt;
                            ))}
                          &lt;/div&gt;
                        )}
                      &lt;/div&gt;
                    &lt;/label&gt;
                  &lt;/div&gt;
                );
              })}
            &lt;/div&gt;
          &lt;/Card&gt;
        );
      })}
    &lt;/div&gt;
  );
}

function confetti() {
  const colors = [&quot;#ff8a3d&quot;, &quot;#ffb44a&quot;, &quot;#4ade80&quot;, &quot;#60a5fa&quot;, &quot;#c084fc&quot;];
  const container = document.createElement(&quot;div&quot;);
  container.style.cssText = &quot;position:fixed;inset:0;pointer-events:none;z-index:9999&quot;;
  for (let i = 0; i &lt; 30; i++) {
    const p = document.createElement(&quot;div&quot;);
    p.style.cssText = `position:absolute;top:40%;left:${45 + Math.random() * 10}%;width:8px;height:8px;background:${colors[i % colors.length]};border-radius:2px;animation:confetti-fall ${0.8 + Math.random() * 0.8}s ease-out forwards;transform:translateX(${(Math.random() - 0.5) * 200}px)`;
    container.appendChild(p);
  }
  document.body.appendChild(container);
  setTimeout(() =&gt; container.remove(), 2000);
}
</code></pre>
</section>

<section class="file-section" id="f-src_routes__authenticated_goals-new-tsx">
  <div class="file-header">
    <span class="file-path">src/routes/_authenticated/goals.new.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_routes__authenticated_goals-new-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_routes__authenticated_goals-new-tsx">import { createFileRoute, useNavigate } from &quot;@tanstack/react-router&quot;;
import { useState } from &quot;react&quot;;
import { useServerFn } from &quot;@tanstack/react-start&quot;;
import { calibrateGoal, generateBreakdown } from &quot;@/lib/goals.functions&quot;;
import { AppShell } from &quot;@/components/app-shell&quot;;
import { Button } from &quot;@/components/ui/button&quot;;
import { Input } from &quot;@/components/ui/input&quot;;
import { Label } from &quot;@/components/ui/label&quot;;
import { Textarea } from &quot;@/components/ui/textarea&quot;;
import { Card } from &quot;@/components/ui/card&quot;;
import { Sparkles, ArrowRight, Loader2 } from &quot;lucide-react&quot;;
import { toast } from &quot;sonner&quot;;

type CalibrationResult = {
  goal: { id: string; title: string; calibrated_target: string; calibrated_metric: string; calibrated_deadline: string; difficulty_tier: string; calibration_explanation: string };
  calibration: { was_recalibrated: boolean; smart_score: number };
};

export const Route = createFileRoute(&quot;/_authenticated/goals/new&quot;)({
  component: NewGoal,
});

function NewGoal() {
  const navigate = useNavigate();
  const calibrate = useServerFn(calibrateGoal);
  const breakdown = useServerFn(generateBreakdown);

  const [step, setStep] = useState&lt;&quot;form&quot; | &quot;review&quot; | &quot;breakdown&quot;&gt;(&quot;form&quot;);
  const [loading, setLoading] = useState(false);
  const [result, setResult] = useState&lt;CalibrationResult | null&gt;(null);

  const [form, setForm] = useState({
    title: &quot;&quot;,
    baseline: &quot;&quot;,
    targetDate: &quot;&quot;,
    obstacles: &quot;&quot;,
    whyMotivation: &quot;&quot;,
    whatIfNot: &quot;&quot;,
  });

  const handleCalibrate = async (e: React.FormEvent) =&gt; {
    e.preventDefault();
    setLoading(true);
    try {
      const res = await calibrate({ data: form }) as CalibrationResult;
      setResult(res);
      setStep(&quot;review&quot;);
    } catch (err) {
      toast.error(err instanceof Error ? err.message : &quot;Calibration failed&quot;);
    } finally {
      setLoading(false);
    }
  };

  const handleAccept = async () =&gt; {
    if (!result) return;
    setLoading(true);
    setStep(&quot;breakdown&quot;);
    try {
      await breakdown({ data: { goalId: result.goal.id } });
      toast.success(&quot;Roadmap built&quot;);
      navigate({ to: &quot;/goals/$id&quot;, params: { id: result.goal.id } });
    } catch (err) {
      toast.error(err instanceof Error ? err.message : &quot;Breakdown failed&quot;);
      setStep(&quot;review&quot;);
    } finally {
      setLoading(false);
    }
  };

  return (
    &lt;AppShell&gt;
      &lt;div className=&quot;mx-auto max-w-2xl&quot;&gt;
        {step === &quot;form&quot; &amp;&amp; (
          &lt;&gt;
            &lt;h1 className=&quot;font-display text-3xl font-semibold sm:text-4xl&quot;&gt;What do you want to achieve?&lt;/h1&gt;
            &lt;p className=&quot;mt-2 text-muted-foreground&quot;&gt;
              Tell us the goal, where you&#x27;re starting from, and when you want it done. We&#x27;ll pressure-test it.
            &lt;/p&gt;
            &lt;form onSubmit={handleCalibrate} className=&quot;mt-8 space-y-5&quot;&gt;
              &lt;div&gt;
                &lt;Label htmlFor=&quot;title&quot;&gt;Goal&lt;/Label&gt;
                &lt;Input id=&quot;title&quot; required placeholder=&quot;Run a 3-hour marathon&quot; className=&quot;mt-1.5&quot;
                  value={form.title} onChange={(e) =&gt; setForm({ ...form, title: e.target.value })} /&gt;
              &lt;/div&gt;
              &lt;div&gt;
                &lt;Label htmlFor=&quot;baseline&quot;&gt;Where you&#x27;re starting&lt;/Label&gt;
                &lt;Textarea id=&quot;baseline&quot; required rows={2} className=&quot;mt-1.5&quot;
                  placeholder=&quot;I currently run 5k in 35 minutes, twice a week.&quot;
                  value={form.baseline} onChange={(e) =&gt; setForm({ ...form, baseline: e.target.value })} /&gt;
              &lt;/div&gt;
              &lt;div&gt;
                &lt;Label htmlFor=&quot;targetDate&quot;&gt;Target date&lt;/Label&gt;
                &lt;Input id=&quot;targetDate&quot; type=&quot;date&quot; required className=&quot;mt-1.5&quot;
                  value={form.targetDate} onChange={(e) =&gt; setForm({ ...form, targetDate: e.target.value })} /&gt;
              &lt;/div&gt;
              &lt;div&gt;
                &lt;Label htmlFor=&quot;obstacles&quot;&gt;What usually gets in the way?&lt;/Label&gt;
                &lt;Textarea id=&quot;obstacles&quot; rows={2} className=&quot;mt-1.5&quot;
                  placeholder=&quot;Travel weeks, late-night work, bad weather.&quot;
                  value={form.obstacles} onChange={(e) =&gt; setForm({ ...form, obstacles: e.target.value })} /&gt;
                &lt;p className=&quot;mt-1 text-xs text-muted-foreground&quot;&gt;Used to build if-then plans for your tasks.&lt;/p&gt;
              &lt;/div&gt;
              &lt;div&gt;
                &lt;Label htmlFor=&quot;whyMotivation&quot;&gt;Why does this matter to you?&lt;/Label&gt;
                &lt;Textarea id=&quot;whyMotivation&quot; rows={2} className=&quot;mt-1.5&quot;
                  placeholder=&quot;I want to prove to myself I can commit to something hard.&quot;
                  value={form.whyMotivation} onChange={(e) =&gt; setForm({ ...form, whyMotivation: e.target.value })} /&gt;
              &lt;/div&gt;
              &lt;div&gt;
                &lt;Label htmlFor=&quot;whatIfNot&quot;&gt;What happens if you don&#x27;t do it?&lt;/Label&gt;
                &lt;Textarea id=&quot;whatIfNot&quot; rows={2} className=&quot;mt-1.5&quot;
                  placeholder=&quot;Another year of half-starting things.&quot;
                  value={form.whatIfNot} onChange={(e) =&gt; setForm({ ...form, whatIfNot: e.target.value })} /&gt;
              &lt;/div&gt;
              &lt;Button type=&quot;submit&quot; size=&quot;lg&quot; disabled={loading} className=&quot;w-full gap-2&quot;&gt;
                {loading ? &lt;&gt;&lt;Loader2 className=&quot;h-4 w-4 animate-spin&quot; /&gt; Calibrating…&lt;/&gt; : &lt;&gt;&lt;Sparkles className=&quot;h-4 w-4&quot; /&gt; Calibrate my goal&lt;/&gt;}
              &lt;/Button&gt;
            &lt;/form&gt;
          &lt;/&gt;
        )}

        {step === &quot;review&quot; &amp;&amp; result &amp;&amp; (
          &lt;&gt;
            &lt;h1 className=&quot;font-display text-3xl font-semibold sm:text-4xl&quot;&gt;Here&#x27;s your calibrated goal&lt;/h1&gt;
            &lt;p className=&quot;mt-2 text-muted-foreground&quot;&gt;
              {result.calibration.was_recalibrated
                ? &quot;We adjusted it to hard-but-achievable given your baseline.&quot;
                : &quot;Your goal is already well-calibrated.&quot;}
            &lt;/p&gt;

            &lt;Card className=&quot;mt-6 overflow-hidden p-0&quot;&gt;
              &lt;div className=&quot;border-b border-border bg-muted/50 p-5&quot;&gt;
                &lt;p className=&quot;text-xs font-medium uppercase tracking-wide text-muted-foreground&quot;&gt;You asked for&lt;/p&gt;
                &lt;p className=&quot;mt-1 text-base line-through decoration-muted-foreground/50&quot;&gt;{form.title}&lt;/p&gt;
                &lt;p className=&quot;mt-1 text-sm text-muted-foreground&quot;&gt;by {form.targetDate}&lt;/p&gt;
              &lt;/div&gt;
              &lt;div className=&quot;p-5&quot;&gt;
                &lt;p className=&quot;text-xs font-medium uppercase tracking-wide text-primary&quot;&gt;Calibrated target&lt;/p&gt;
                &lt;p className=&quot;mt-1 font-display text-2xl font-semibold leading-tight&quot;&gt;{result.goal.calibrated_target}&lt;/p&gt;
                &lt;div className=&quot;mt-3 grid gap-3 text-sm sm:grid-cols-2&quot;&gt;
                  &lt;div&gt;
                    &lt;p className=&quot;text-muted-foreground&quot;&gt;Metric&lt;/p&gt;
                    &lt;p className=&quot;font-medium&quot;&gt;{result.goal.calibrated_metric}&lt;/p&gt;
                  &lt;/div&gt;
                  &lt;div&gt;
                    &lt;p className=&quot;text-muted-foreground&quot;&gt;Deadline&lt;/p&gt;
                    &lt;p className=&quot;font-medium&quot;&gt;{result.goal.calibrated_deadline}&lt;/p&gt;
                  &lt;/div&gt;
                  &lt;div&gt;
                    &lt;p className=&quot;text-muted-foreground&quot;&gt;Difficulty&lt;/p&gt;
                    &lt;p className=&quot;font-medium capitalize&quot;&gt;{result.goal.difficulty_tier.replace(&quot;_&quot;, &quot; &quot;)}&lt;/p&gt;
                  &lt;/div&gt;
                  &lt;div&gt;
                    &lt;p className=&quot;text-muted-foreground&quot;&gt;SMART score&lt;/p&gt;
                    &lt;p className=&quot;font-medium&quot;&gt;{result.calibration.smart_score}/100&lt;/p&gt;
                  &lt;/div&gt;
                &lt;/div&gt;
                &lt;div className=&quot;mt-4 rounded-lg bg-accent/50 p-3 text-sm&quot;&gt;
                  &lt;p className=&quot;font-medium text-accent-foreground&quot;&gt;Why this change&lt;/p&gt;
                  &lt;p className=&quot;mt-1 text-accent-foreground/80&quot;&gt;{result.goal.calibration_explanation}&lt;/p&gt;
                &lt;/div&gt;
              &lt;/div&gt;
            &lt;/Card&gt;

            &lt;div className=&quot;mt-6 flex flex-wrap gap-3&quot;&gt;
              &lt;Button size=&quot;lg&quot; onClick={handleAccept} disabled={loading} className=&quot;gap-2&quot;&gt;
                {loading ? &lt;&gt;&lt;Loader2 className=&quot;h-4 w-4 animate-spin&quot; /&gt; Building your roadmap…&lt;/&gt; : &lt;&gt;Accept &amp; build roadmap &lt;ArrowRight className=&quot;h-4 w-4&quot; /&gt;&lt;/&gt;}
              &lt;/Button&gt;
              &lt;Button size=&quot;lg&quot; variant=&quot;outline&quot; onClick={() =&gt; setStep(&quot;form&quot;)} disabled={loading}&gt;
                Edit inputs
              &lt;/Button&gt;
            &lt;/div&gt;
          &lt;/&gt;
        )}

        {step === &quot;breakdown&quot; &amp;&amp; (
          &lt;div className=&quot;py-20 text-center&quot;&gt;
            &lt;Loader2 className=&quot;mx-auto h-8 w-8 animate-spin text-primary&quot; /&gt;
            &lt;p className=&quot;mt-4 font-display text-xl&quot;&gt;Building your weekly sprints…&lt;/p&gt;
            &lt;p className=&quot;mt-1 text-sm text-muted-foreground&quot;&gt;Generating tasks and daily habits&lt;/p&gt;
          &lt;/div&gt;
        )}
      &lt;/div&gt;
    &lt;/AppShell&gt;
  );
}
</code></pre>
</section>

<section class="file-section" id="f-src_routes__authenticated_route-tsx">
  <div class="file-header">
    <span class="file-path">src/routes/_authenticated/route.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_routes__authenticated_route-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_routes__authenticated_route-tsx">import { createFileRoute, Outlet, redirect } from &quot;@tanstack/react-router&quot;;
import { supabase } from &quot;@/integrations/supabase/client&quot;;

export const Route = createFileRoute(&quot;/_authenticated&quot;)({
  ssr: false,
  beforeLoad: async () =&gt; {
    const { data, error } = await supabase.auth.getUser();
    if (error || !data.user) throw redirect({ to: &quot;/auth&quot; });
    return { user: data.user };
  },
  component: () =&gt; &lt;Outlet /&gt;,
});
</code></pre>
</section>

<section class="file-section" id="f-src_routes_auth-tsx">
  <div class="file-header">
    <span class="file-path">src/routes/auth.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_routes_auth-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_routes_auth-tsx">import { createFileRoute, useNavigate, Link } from &quot;@tanstack/react-router&quot;;
import { useState, useEffect } from &quot;react&quot;;
import { supabase } from &quot;@/integrations/supabase/client&quot;;
import { lovable } from &quot;@/integrations/lovable&quot;;
import { Button } from &quot;@/components/ui/button&quot;;
import { Input } from &quot;@/components/ui/input&quot;;
import { Label } from &quot;@/components/ui/label&quot;;
import { Flame } from &quot;lucide-react&quot;;
import { toast } from &quot;sonner&quot;;

export const Route = createFileRoute(&quot;/auth&quot;)({
  component: AuthPage,
});

function AuthPage() {
  const navigate = useNavigate();
  const [mode, setMode] = useState&lt;&quot;signin&quot; | &quot;signup&quot;&gt;(&quot;signin&quot;);
  const [email, setEmail] = useState(&quot;&quot;);
  const [password, setPassword] = useState(&quot;&quot;);
  const [loading, setLoading] = useState(false);

  useEffect(() =&gt; {
    supabase.auth.getUser().then(({ data }) =&gt; {
      if (data.user) navigate({ to: &quot;/dashboard&quot; });
    });
  }, [navigate]);

  const handleSubmit = async (e: React.FormEvent) =&gt; {
    e.preventDefault();
    setLoading(true);
    try {
      if (mode === &quot;signup&quot;) {
        const { error } = await supabase.auth.signUp({
          email,
          password,
          options: { emailRedirectTo: window.location.origin },
        });
        if (error) throw error;
        toast.success(&quot;Account created! Check your email if confirmation is required.&quot;);
      } else {
        const { error } = await supabase.auth.signInWithPassword({ email, password });
        if (error) throw error;
      }
      navigate({ to: &quot;/dashboard&quot; });
    } catch (err) {
      toast.error(err instanceof Error ? err.message : &quot;Auth failed&quot;);
    } finally {
      setLoading(false);
    }
  };

  const handleGoogle = async () =&gt; {
    const result = await lovable.auth.signInWithOAuth(&quot;google&quot;, {
      redirect_uri: window.location.origin,
    });
    if (result.error) {
      toast.error(result.error.message || &quot;Google sign-in failed&quot;);
      return;
    }
    if (result.redirected) return;
    navigate({ to: &quot;/dashboard&quot; });
  };

  return (
    &lt;div className=&quot;flex min-h-screen items-center justify-center bg-background px-4 py-12&quot;&gt;
      &lt;div className=&quot;w-full max-w-md&quot;&gt;
        &lt;Link to=&quot;/&quot; className=&quot;mb-8 flex items-center justify-center gap-2&quot;&gt;
          &lt;Flame className=&quot;h-6 w-6 text-primary animate-flame&quot; /&gt;
          &lt;span className=&quot;font-display text-xl font-semibold&quot;&gt;Momentum&lt;/span&gt;
        &lt;/Link&gt;
        &lt;div className=&quot;rounded-2xl border border-border bg-card p-8 shadow-soft&quot;&gt;
          &lt;h1 className=&quot;font-display text-2xl font-semibold&quot;&gt;
            {mode === &quot;signin&quot; ? &quot;Welcome back&quot; : &quot;Create your account&quot;}
          &lt;/h1&gt;
          &lt;p className=&quot;mt-1 text-sm text-muted-foreground&quot;&gt;
            {mode === &quot;signin&quot; ? &quot;Pick up where you left off.&quot; : &quot;Start your first calibrated goal.&quot;}
          &lt;/p&gt;

          &lt;Button
            type=&quot;button&quot;
            variant=&quot;outline&quot;
            className=&quot;mt-6 w-full&quot;
            onClick={handleGoogle}
          &gt;
            &lt;svg className=&quot;mr-2 h-4 w-4&quot; viewBox=&quot;0 0 24 24&quot;&gt;
              &lt;path fill=&quot;#4285F4&quot; d=&quot;M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z&quot;/&gt;
              &lt;path fill=&quot;#34A853&quot; d=&quot;M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z&quot;/&gt;
              &lt;path fill=&quot;#FBBC05&quot; d=&quot;M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l3.66-2.84z&quot;/&gt;
              &lt;path fill=&quot;#EA4335&quot; d=&quot;M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z&quot;/&gt;
            &lt;/svg&gt;
            Continue with Google
          &lt;/Button&gt;

          &lt;div className=&quot;my-6 flex items-center gap-3&quot;&gt;
            &lt;div className=&quot;h-px flex-1 bg-border&quot; /&gt;
            &lt;span className=&quot;text-xs text-muted-foreground&quot;&gt;or&lt;/span&gt;
            &lt;div className=&quot;h-px flex-1 bg-border&quot; /&gt;
          &lt;/div&gt;

          &lt;form onSubmit={handleSubmit} className=&quot;space-y-4&quot;&gt;
            &lt;div&gt;
              &lt;Label htmlFor=&quot;email&quot;&gt;Email&lt;/Label&gt;
              &lt;Input id=&quot;email&quot; type=&quot;email&quot; required value={email} onChange={(e) =&gt; setEmail(e.target.value)} className=&quot;mt-1.5&quot; /&gt;
            &lt;/div&gt;
            &lt;div&gt;
              &lt;Label htmlFor=&quot;password&quot;&gt;Password&lt;/Label&gt;
              &lt;Input id=&quot;password&quot; type=&quot;password&quot; required minLength={6} value={password} onChange={(e) =&gt; setPassword(e.target.value)} className=&quot;mt-1.5&quot; /&gt;
            &lt;/div&gt;
            &lt;Button type=&quot;submit&quot; className=&quot;w-full&quot; disabled={loading}&gt;
              {loading ? &quot;...&quot; : mode === &quot;signin&quot; ? &quot;Sign in&quot; : &quot;Create account&quot;}
            &lt;/Button&gt;
          &lt;/form&gt;

          &lt;button
            type=&quot;button&quot;
            className=&quot;mt-4 w-full text-center text-sm text-muted-foreground hover:text-foreground&quot;
            onClick={() =&gt; setMode(mode === &quot;signin&quot; ? &quot;signup&quot; : &quot;signin&quot;)}
          &gt;
            {mode === &quot;signin&quot; ? &quot;New here? Create an account&quot; : &quot;Already have an account? Sign in&quot;}
          &lt;/button&gt;
        &lt;/div&gt;
      &lt;/div&gt;
    &lt;/div&gt;
  );
}
</code></pre>
</section>

<section class="file-section" id="f-src_routes_index-tsx">
  <div class="file-header">
    <span class="file-path">src/routes/index.tsx</span>
    <button class="copy-btn" onclick="copyCode('f-src_routes_index-tsx', this)">Copy</button>
  </div>
  <pre><code class="language-typescript" id="code-f-src_routes_index-tsx">import { createFileRoute, Link } from &quot;@tanstack/react-router&quot;;
import { Flame, Target, CalendarCheck, Sparkles } from &quot;lucide-react&quot;;
import { Button } from &quot;@/components/ui/button&quot;;

export const Route = createFileRoute(&quot;/&quot;)({
  component: Landing,
});

function Landing() {
  return (
    &lt;div className=&quot;min-h-screen bg-background text-foreground&quot;&gt;
      &lt;header className=&quot;mx-auto flex max-w-6xl items-center justify-between px-6 py-6&quot;&gt;
        &lt;div className=&quot;flex items-center gap-2&quot;&gt;
          &lt;Flame className=&quot;h-6 w-6 text-primary animate-flame&quot; /&gt;
          &lt;span className=&quot;font-display text-xl font-semibold&quot;&gt;Momentum&lt;/span&gt;
        &lt;/div&gt;
        &lt;nav className=&quot;flex items-center gap-3&quot;&gt;
          &lt;Link to=&quot;/auth&quot; className=&quot;text-sm text-muted-foreground hover:text-foreground&quot;&gt;
            Sign in
          &lt;/Link&gt;
          &lt;Button asChild size=&quot;sm&quot;&gt;
            &lt;Link to=&quot;/auth&quot;&gt;Get started&lt;/Link&gt;
          &lt;/Button&gt;
        &lt;/nav&gt;
      &lt;/header&gt;

      &lt;main className=&quot;mx-auto max-w-6xl px-6&quot;&gt;
        &lt;section className=&quot;py-20 md:py-28&quot;&gt;
          &lt;div className=&quot;mx-auto max-w-3xl text-center&quot;&gt;
            &lt;span className=&quot;inline-flex items-center gap-1.5 rounded-full border border-border bg-card px-3 py-1 text-xs font-medium text-muted-foreground&quot;&gt;
              &lt;Sparkles className=&quot;h-3.5 w-3.5 text-primary&quot; /&gt; SMART calibration · AI task breakdown · streaks
            &lt;/span&gt;
            &lt;h1 className=&quot;mt-6 font-display text-5xl font-semibold leading-[1.05] tracking-tight md:text-7xl&quot;&gt;
              Goals that actually{&quot; &quot;}
              &lt;span className=&quot;flame-text&quot;&gt;happen.&lt;/span&gt;
            &lt;/h1&gt;
            &lt;p className=&quot;mt-6 text-lg text-muted-foreground md:text-xl&quot;&gt;
              You&#x27;ve tried habit trackers before. Momentum calibrates your goal against reality,
              breaks it into 1-2 hour steps, and keeps you moving with a streak worth protecting.
            &lt;/p&gt;
            &lt;div className=&quot;mt-8 flex flex-wrap items-center justify-center gap-3&quot;&gt;
              &lt;Button asChild size=&quot;lg&quot; className=&quot;h-12 px-6 text-base&quot;&gt;
                &lt;Link to=&quot;/auth&quot;&gt;Start your first goal&lt;/Link&gt;
              &lt;/Button&gt;
            &lt;/div&gt;
          &lt;/div&gt;
        &lt;/section&gt;

        &lt;section className=&quot;grid gap-4 pb-24 md:grid-cols-3&quot;&gt;
          {[
            { icon: Target, title: &quot;Calibrate&quot;, body: &quot;Tell us the goal, baseline, and deadline. AI recalibrates to hard-but-achievable.&quot; },
            { icon: CalendarCheck, title: &quot;Break it down&quot;, body: &quot;Weekly sprints of 1-2 hour tasks, plus if-then plans for your usual obstacles.&quot; },
            { icon: Flame, title: &quot;Keep the streak&quot;, body: &quot;Duolingo-style tracker with a two-day rule and monthly freezes when life happens.&quot; },
          ].map(({ icon: Icon, title, body }) =&gt; (
            &lt;div key={title} className=&quot;rounded-2xl border border-border bg-card p-6 shadow-soft&quot;&gt;
              &lt;Icon className=&quot;h-8 w-8 text-primary&quot; /&gt;
              &lt;h3 className=&quot;mt-4 font-display text-xl font-semibold&quot;&gt;{title}&lt;/h3&gt;
              &lt;p className=&quot;mt-2 text-sm text-muted-foreground&quot;&gt;{body}&lt;/p&gt;
            &lt;/div&gt;
          ))}
        &lt;/section&gt;
      &lt;/main&gt;
    &lt;/div&gt;
  );
}
</code></pre>
</section>

<section class="file-section" id="f-supabase_config-toml">
  <div class="file-header">
    <span class="file-path">supabase/config.toml</span>
    <button class="copy-btn" onclick="copyCode('f-supabase_config-toml', this)">Copy</button>
  </div>
  <pre><code class="language-toml" id="code-f-supabase_config-toml">project_id = &quot;fpaopxacraudpbeyuesa&quot;
</code></pre>
</section>

<section class="file-section" id="f-supabase_migrations_20260708110954_3ddd6732-7a30-40d6-9836-5f73d73835c4-sql">
  <div class="file-header">
    <span class="file-path">supabase/migrations/20260708110954_3ddd6732-7a30-40d6-9836-5f73d73835c4.sql</span>
    <button class="copy-btn" onclick="copyCode('f-supabase_migrations_20260708110954_3ddd6732-7a30-40d6-9836-5f73d73835c4-sql', this)">Copy</button>
  </div>
  <pre><code class="language-sql" id="code-f-supabase_migrations_20260708110954_3ddd6732-7a30-40d6-9836-5f73d73835c4-sql">
-- profiles
CREATE TABLE public.profiles (
  id UUID PRIMARY KEY REFERENCES auth.users(id) ON DELETE CASCADE,
  display_name TEXT,
  freeze_credits INT NOT NULL DEFAULT 3,
  last_freeze_reset DATE NOT NULL DEFAULT CURRENT_DATE,
  created_at TIMESTAMPTZ NOT NULL DEFAULT now(),
  updated_at TIMESTAMPTZ NOT NULL DEFAULT now()
);
GRANT SELECT, INSERT, UPDATE, DELETE ON public.profiles TO authenticated;
GRANT ALL ON public.profiles TO service_role;
ALTER TABLE public.profiles ENABLE ROW LEVEL SECURITY;
CREATE POLICY &quot;profiles self&quot; ON public.profiles FOR ALL USING (auth.uid() = id) WITH CHECK (auth.uid() = id);

-- goals
CREATE TABLE public.goals (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID NOT NULL REFERENCES auth.users(id) ON DELETE CASCADE,
  title TEXT NOT NULL,
  description TEXT,
  baseline TEXT,
  target_date DATE,
  calibrated_target TEXT,
  calibrated_metric TEXT,
  calibrated_deadline DATE,
  calibration_explanation TEXT,
  difficulty_tier TEXT,
  calibration_status TEXT NOT NULL DEFAULT &#x27;raw&#x27;,
  why_motivation TEXT,
  what_if_not TEXT,
  obstacles TEXT,
  status TEXT NOT NULL DEFAULT &#x27;active&#x27;,
  created_at TIMESTAMPTZ NOT NULL DEFAULT now(),
  updated_at TIMESTAMPTZ NOT NULL DEFAULT now()
);
GRANT SELECT, INSERT, UPDATE, DELETE ON public.goals TO authenticated;
GRANT ALL ON public.goals TO service_role;
ALTER TABLE public.goals ENABLE ROW LEVEL SECURITY;
CREATE POLICY &quot;goals owner&quot; ON public.goals FOR ALL USING (auth.uid() = user_id) WITH CHECK (auth.uid() = user_id);

-- tasks
CREATE TABLE public.tasks (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  goal_id UUID NOT NULL REFERENCES public.goals(id) ON DELETE CASCADE,
  user_id UUID NOT NULL REFERENCES auth.users(id) ON DELETE CASCADE,
  title TEXT NOT NULL,
  description TEXT,
  week_number INT NOT NULL DEFAULT 1,
  sprint_order INT NOT NULL DEFAULT 0,
  estimated_hours NUMERIC(3,1),
  if_then_plans JSONB DEFAULT &#x27;[]&#x27;::jsonb,
  completed BOOLEAN NOT NULL DEFAULT false,
  completed_at TIMESTAMPTZ,
  created_at TIMESTAMPTZ NOT NULL DEFAULT now()
);
GRANT SELECT, INSERT, UPDATE, DELETE ON public.tasks TO authenticated;
GRANT ALL ON public.tasks TO service_role;
ALTER TABLE public.tasks ENABLE ROW LEVEL SECURITY;
CREATE POLICY &quot;tasks owner&quot; ON public.tasks FOR ALL USING (auth.uid() = user_id) WITH CHECK (auth.uid() = user_id);
CREATE INDEX tasks_goal_idx ON public.tasks(goal_id, week_number, sprint_order);

-- daily actions
CREATE TABLE public.daily_actions (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  goal_id UUID NOT NULL REFERENCES public.goals(id) ON DELETE CASCADE,
  user_id UUID NOT NULL REFERENCES auth.users(id) ON DELETE CASCADE,
  title TEXT NOT NULL,
  description TEXT,
  active BOOLEAN NOT NULL DEFAULT true,
  created_at TIMESTAMPTZ NOT NULL DEFAULT now()
);
GRANT SELECT, INSERT, UPDATE, DELETE ON public.daily_actions TO authenticated;
GRANT ALL ON public.daily_actions TO service_role;
ALTER TABLE public.daily_actions ENABLE ROW LEVEL SECURITY;
CREATE POLICY &quot;da owner&quot; ON public.daily_actions FOR ALL USING (auth.uid() = user_id) WITH CHECK (auth.uid() = user_id);

-- action completions
CREATE TABLE public.action_completions (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  daily_action_id UUID NOT NULL REFERENCES public.daily_actions(id) ON DELETE CASCADE,
  user_id UUID NOT NULL REFERENCES auth.users(id) ON DELETE CASCADE,
  completed_date DATE NOT NULL,
  created_at TIMESTAMPTZ NOT NULL DEFAULT now(),
  UNIQUE(daily_action_id, completed_date)
);
GRANT SELECT, INSERT, UPDATE, DELETE ON public.action_completions TO authenticated;
GRANT ALL ON public.action_completions TO service_role;
ALTER TABLE public.action_completions ENABLE ROW LEVEL SECURITY;
CREATE POLICY &quot;ac owner&quot; ON public.action_completions FOR ALL USING (auth.uid() = user_id) WITH CHECK (auth.uid() = user_id);
CREATE INDEX ac_user_date_idx ON public.action_completions(user_id, completed_date);

-- streak freezes
CREATE TABLE public.streak_freezes (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID NOT NULL REFERENCES auth.users(id) ON DELETE CASCADE,
  goal_id UUID REFERENCES public.goals(id) ON DELETE CASCADE,
  freeze_date DATE NOT NULL,
  applied_at TIMESTAMPTZ NOT NULL DEFAULT now(),
  UNIQUE(user_id, goal_id, freeze_date)
);
GRANT SELECT, INSERT, UPDATE, DELETE ON public.streak_freezes TO authenticated;
GRANT ALL ON public.streak_freezes TO service_role;
ALTER TABLE public.streak_freezes ENABLE ROW LEVEL SECURITY;
CREATE POLICY &quot;sf owner&quot; ON public.streak_freezes FOR ALL USING (auth.uid() = user_id) WITH CHECK (auth.uid() = user_id);

-- profile auto-create trigger
CREATE OR REPLACE FUNCTION public.handle_new_user()
RETURNS TRIGGER
LANGUAGE plpgsql
SECURITY DEFINER SET search_path = public
AS $$
BEGIN
  INSERT INTO public.profiles (id, display_name)
  VALUES (NEW.id, COALESCE(NEW.raw_user_meta_data-&gt;&gt;&#x27;name&#x27;, NEW.raw_user_meta_data-&gt;&gt;&#x27;full_name&#x27;, split_part(NEW.email, &#x27;@&#x27;, 1)))
  ON CONFLICT (id) DO NOTHING;
  RETURN NEW;
END;
$$;

CREATE TRIGGER on_auth_user_created
  AFTER INSERT ON auth.users
  FOR EACH ROW EXECUTE FUNCTION public.handle_new_user();
</code></pre>
</section>

<section class="file-section" id="f-supabase_migrations_20260708111029_30bcabec-6f38-4948-97a4-ddc34dd7d238-sql">
  <div class="file-header">
    <span class="file-path">supabase/migrations/20260708111029_30bcabec-6f38-4948-97a4-ddc34dd7d238.sql</span>
    <button class="copy-btn" onclick="copyCode('f-supabase_migrations_20260708111029_30bcabec-6f38-4948-97a4-ddc34dd7d238-sql', this)">Copy</button>
  </div>
  <pre><code class="language-sql" id="code-f-supabase_migrations_20260708111029_30bcabec-6f38-4948-97a4-ddc34dd7d238-sql">REVOKE EXECUTE ON FUNCTION public.handle_new_user() FROM PUBLIC, anon, authenticated;</code></pre>
</section>

</main>
<script>
  hljs.highlightAll();
  function copyCode(id, btn) {
    const el = document.getElementById('code-' + id);
    navigator.clipboard.writeText(el.textContent).then(() => {
      const old = btn.textContent;
      btn.textContent = 'Copied!';
      setTimeout(() => btn.textContent = old, 1200);
    });
  }
</script>
</body>
</html>
