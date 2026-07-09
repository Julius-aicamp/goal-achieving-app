# goal-achieving-app
Klar — hier der komplette Custom-Code als reiner Text zum Copy-Paste (ohne ZIP, ohne Vorschau-Widget). Die ~40 Standard-shadcn/ui-Dateien (button.tsx, card.tsx, input.tsx, etc.) lass ich weg, die kommen 1:1 aus `npx shadcn add ...` (Befehl weiter oben) — copy-paste macht bei reinem Boilerplate keinen Sinn. Alles Projekt-Spezifische ist hier:

## Config

**package.json**
```json
{
  "name": "tanstack_start_ts",
  "private": true,
  "sideEffects": false,
  "type": "module",
  "scripts": {
    "dev": "vite dev",
    "build": "vite build",
    "build:dev": "vite build --mode development",
    "preview": "vite preview",
    "lint": "eslint .",
    "format": "prettier --write ."
  },
  "dependencies": {
    "@hookform/resolvers": "^5.2.2",
    "@lovable.dev/cloud-auth-js": "^1.1.2",
    "@radix-ui/react-accordion": "^1.2.12",
    "@radix-ui/react-alert-dialog": "^1.1.15",
    "@radix-ui/react-aspect-ratio": "^1.1.8",
    "@radix-ui/react-avatar": "^1.1.11",
    "@radix-ui/react-checkbox": "^1.3.3",
    "@radix-ui/react-collapsible": "^1.1.12",
    "@radix-ui/react-context-menu": "^2.2.16",
    "@radix-ui/react-dialog": "^1.1.15",
    "@radix-ui/react-dropdown-menu": "^2.1.16",
    "@radix-ui/react-hover-card": "^1.1.15",
    "@radix-ui/react-label": "^2.1.8",
    "@radix-ui/react-menubar": "^1.1.16",
    "@radix-ui/react-navigation-menu": "^1.2.14",
    "@radix-ui/react-popover": "^1.1.15",
    "@radix-ui/react-progress": "^1.1.8",
    "@radix-ui/react-radio-group": "^1.3.8",
    "@radix-ui/react-scroll-area": "^1.2.10",
    "@radix-ui/react-select": "^2.2.6",
    "@radix-ui/react-separator": "^1.1.8",
    "@radix-ui/react-slider": "^1.3.6",
    "@radix-ui/react-slot": "^1.2.4",
    "@radix-ui/react-switch": "^1.2.6",
    "@radix-ui/react-tabs": "^1.1.13",
    "@radix-ui/react-toggle": "^1.1.10",
    "@radix-ui/react-toggle-group": "^1.1.11",
    "@radix-ui/react-tooltip": "^1.2.8",
    "@supabase/supabase-js": "^2.110.0",
    "@tailwindcss/vite": "^4.2.1",
    "@tanstack/react-query": "^5.101.1",
    "@tanstack/react-router": "^1.170.16",
    "@tanstack/react-start": "^1.168.26",
    "@tanstack/router-plugin": "^1.168.18",
    "class-variance-authority": "^0.7.1",
    "clsx": "^2.1.1",
    "cmdk": "^1.1.1",
    "date-fns": "^4.1.0",
    "embla-carousel-react": "^8.6.0",
    "input-otp": "^1.4.2",
    "lucide-react": "^0.575.0",
    "react": "^19.2.0",
    "react-day-picker": "^9.14.0",
    "react-dom": "^19.2.0",
    "react-hook-form": "^7.71.2",
    "react-resizable-panels": "^4.6.5",
    "recharts": "^2.15.4",
    "sonner": "^2.0.7",
    "tailwind-merge": "^3.5.0",
    "tailwindcss": "^4.2.1",
    "tw-animate-css": "^1.3.4",
    "vaul": "^1.1.2",
    "vite-tsconfig-paths": "^6.0.2",
    "zod": "^3.24.2"
  },
  "devDependencies": {
    "@eslint/js": "^9.32.0",
    "@lovable.dev/vite-tanstack-config": "^2.7.1",
    "@types/node": "^22.16.5",
    "@types/react": "^19.2.0",
    "@types/react-dom": "^19.2.0",
    "@vitejs/plugin-react": "^5.2.0",
    "eslint": "^9.32.0",
    "eslint-config-prettier": "^10.1.1",
    "eslint-plugin-prettier": "^5.2.6",
    "eslint-plugin-react-hooks": "^5.2.0",
    "eslint-plugin-react-refresh": "^0.4.20",
    "globals": "^15.15.0",
    "nitro": "3.0.260603-beta",
    "prettier": "^3.7.3",
    "typescript": "^5.8.3",
    "typescript-eslint": "^8.56.1",
    "vite": "^8.0.16"
  }
}
```

**tsconfig.json**
```json
{
  "include": ["src/**/*.ts", "src/**/*.tsx", "vite.config.ts", "eslint.config.js"],
  "compilerOptions": {
    "target": "ES2022",
    "jsx": "react-jsx",
    "module": "ESNext",
    "lib": ["ES2022", "DOM", "DOM.Iterable"],
    "types": ["vite/client"],
    "moduleResolution": "Bundler",
    "allowImportingTsExtensions": true,
    "verbatimModuleSyntax": false,
    "noEmit": true,
    "skipLibCheck": true,
    "strict": true,
    "noUnusedLocals": false,
    "noUnusedParameters": false,
    "noFallthroughCasesInSwitch": true,
    "noUncheckedSideEffectImports": true,
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}
```

**vite.config.ts**
```typescript
import { defineConfig } from "@lovable.dev/vite-tanstack-config";

export default defineConfig({
  tanstackStart: {
    server: { entry: "server" },
  },
});
```

**components.json**
```json
{
  "$schema": "https://ui.shadcn.com/schema.json",
  "style": "new-york",
  "rsc": false,
  "tsx": true,
  "tailwind": {
    "css": "src/styles.css",
    "baseColor": "slate",
    "cssVariables": true,
    "prefix": ""
  },
  "iconLibrary": "lucide",
  "rtl": false,
  "aliases": {
    "components": "@/components",
    "utils": "@/lib/utils",
    "ui": "@/components/ui",
    "lib": "@/lib",
    "hooks": "@/hooks"
  },
  "registries": {}
}
```

## src/ — Entry points

**src/router.tsx**
```typescript
import { QueryClient } from "@tanstack/react-query";
import { createRouter } from "@tanstack/react-router";
import { routeTree } from "./routeTree.gen";

export const getRouter = () => {
  const queryClient = new QueryClient();

  const router = createRouter({
    routeTree,
    context: { queryClient },
    scrollRestoration: true,
    defaultPreloadStaleTime: 0,
  });

  return router;
};
```

**src/start.ts**
```typescript
import { createStart, createMiddleware } from "@tanstack/react-start";

import { renderErrorPage } from "./lib/error-page";
import { attachSupabaseAuth } from "@/integrations/supabase/auth-attacher";

const errorMiddleware = createMiddleware().server(async ({ next }) => {
  try {
    return await next();
  } catch (error) {
    if (error != null && typeof error === "object" && "statusCode" in error) {
      throw error;
    }
    console.error(error);
    return new Response(renderErrorPage(), {
      status: 500,
      headers: { "content-type": "text/html; charset=utf-8" },
    });
  }
});

export const startInstance = createStart(() => ({
  functionMiddleware: [attachSupabaseAuth],
  requestMiddleware: [errorMiddleware],
}));
```

**src/server.ts**
```typescript
import "./lib/error-capture";

import { consumeLastCapturedError } from "./lib/error-capture";
import { renderErrorPage } from "./lib/error-page";

type ServerEntry = {
  fetch: (request: Request, env: unknown, ctx: unknown) => Promise<Response> | Response;
};

let serverEntryPromise: Promise<ServerEntry> | undefined;

async function getServerEntry(): Promise<ServerEntry> {
  if (!serverEntryPromise) {
    serverEntryPromise = import("@tanstack/react-start/server-entry").then(
      (m) => (m.default ?? m) as ServerEntry,
    );
  }
  return serverEntryPromise;
}

async function normalizeCatastrophicSsrResponse(response: Response): Promise<Response> {
  if (response.status < 500) return response;
  const contentType = response.headers.get("content-type") ?? "";
  if (!contentType.includes("application/json")) return response;

  const body = await response.clone().text();
  if (!isH3SwallowedErrorBody(body)) return response;

  console.error(consumeLastCapturedError() ?? new Error(`h3 swallowed SSR error: ${body}`));
  return new Response(renderErrorPage(), {
    status: 500,
    headers: { "content-type": "text/html; charset=utf-8" },
  });
}

function isH3SwallowedErrorBody(body: string): boolean {
  try {
    const payload = JSON.parse(body) as { unhandled?: unknown; message?: unknown };
    return payload.unhandled === true && payload.message === "HTTPError";
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
        headers: { "content-type": "text/html; charset=utf-8" },
      });
    }
  },
};
```

## src/lib/

**src/lib/utils.ts**
```typescript
import { clsx, type ClassValue } from "clsx";
import { twMerge } from "tailwind-merge";

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs));
}
```

**src/lib/streak.ts**
```typescript
export function toISO(d: Date): string {
  return d.toISOString().slice(0, 10);
}

export function daysBetween(a: string, b: string): number {
  const da = new Date(a + "T00:00:00Z").getTime();
  const db = new Date(b + "T00:00:00Z").getTime();
  return Math.round((db - da) / 86400000);
}

export function calcStreak(completed: Set<string>, freezes: Set<string>): { current: number; longest: number } {
  if (completed.size === 0 && freezes.size === 0) return { current: 0, longest: 0 };
  const all = Array.from(new Set([...completed, ...freezes])).sort();

  const earliest = all[0];
  const todayISO = toISO(new Date());
  const totalDays = daysBetween(earliest, todayISO) + 1;

  let longest = 0;
  let run = 0;
  let missedYesterday = false;
  for (let i = 0; i < totalDays; i++) {
    const d = new Date(earliest + "T00:00:00Z");
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
        missedYesterday = true;
      }
    }
  }

  let current = 0;
  let graceUsed = false;
  for (let i = 0; ; i++) {
    const d = new Date(todayISO + "T00:00:00Z");
    d.setUTCDate(d.getUTCDate() - i);
    const iso = toISO(d);
    const active = completed.has(iso) || freezes.has(iso);
    if (active) {
      current += 1;
      graceUsed = false;
    } else {
      if (i === 0) {
        continue;
      }
      if (!graceUsed) {
        graceUsed = true;
      } else {
        break;
      }
    }
    if (i > 3650) break;
  }

  return { current, longest };
}
```

**src/lib/error-capture.ts**
```typescript
let lastCapturedError: { error: unknown; at: number } | undefined;
const TTL_MS = 5_000;

function record(error: unknown) {
  lastCapturedError = { error, at: Date.now() };
}

if (typeof globalThis.addEventListener === "function") {
  globalThis.addEventListener("error", (event) => record((event as ErrorEvent).error ?? event));
  globalThis.addEventListener("unhandledrejection", (event) =>
    record((event as PromiseRejectionEvent).reason),
  );
}

export function consumeLastCapturedError(): unknown {
  if (!lastCapturedError) return undefined;
  if (Date.now() - lastCapturedError.at > TTL_MS) {
    lastCapturedError = undefined;
    return undefined;
  }
  const { error } = lastCapturedError;
  lastCapturedError = undefined;
  return error;
}
```

**src/lib/error-page.ts**
```typescript
export function renderErrorPage(): string {
  return `<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>This page didn't load</title>
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <style>
      body { font: 15px/1.5 system-ui, -apple-system, sans-serif; background: #fafafa; color: #111; display: grid; place-items: center; min-height: 100vh; margin: 0; padding: 1.5rem; }
      .card { max-width: 28rem; width: 100%; text-align: center; padding: 2rem; }
      h1 { font-size: 1.25rem; margin: 0 0 0.5rem; }
      p { color: #4b5563; margin: 0 0 1.5rem; }
      .actions { display: flex; gap: 0.5rem; justify-content: center; flex-wrap: wrap; }
      a, button { padding: 0.5rem 1rem; border-radius: 0.375rem; font: inherit; cursor: pointer; text-decoration: none; border: 1px solid transparent; }
      .primary { background: #111; color: #fff; }
      .secondary { background: #fff; color: #111; border-color: #d1d5db; }
    </style>
  </head>
  <body>
    <div class="card">
      <h1>This page didn't load</h1>
      <p>Something went wrong on our end. You can try refreshing or head back home.</p>
      <div class="actions">
        <button class="primary" onclick="location.reload()">Try again</button>
        <a class="secondary" href="/">Go home</a>
      </div>
    </div>
  </body>
</html>`;
}
```

**src/lib/lovable-error-reporting.ts**
```typescript
type LovableErrorOptions = {
  mechanism?: "manual" | "onerror" | "unhandledrejection" | "react_error_boundary";
  handled?: boolean;
  severity?: "error" | "warning" | "info";
};

type LovableEvents = {
  captureException?: (
    error: unknown,
    context?: Record<string, unknown>,
    options?: LovableErrorOptions,
  ) => void;
};

declare global {
  interface Window {
    __lovableEvents?: LovableEvents;
  }
}

export function reportLovableError(error: unknown, context: Record<string, unknown> = {}) {
  if (typeof window === "undefined") return;
  window.__lovableEvents?.captureException?.(
    error,
    {
      source: "react_error_boundary",
      route: window.location.pathname,
      ...context,
    },
    {
      mechanism: "react_error_boundary",
      handled: false,
      severity: "error",
    },
  );
}
```

**src/lib/goals.functions.ts** (SMART-Kalibrierung + Task-Breakdown, Server-Functions)
```typescript
import { createServerFn } from "@tanstack/react-start";
import { requireSupabaseAuth } from "@/integrations/supabase/auth-middleware";
import type { TablesInsert } from "@/integrations/supabase/types";
import { z } from "zod";

const GATEWAY_URL = "https://ai.gateway.lovable.dev/v1/chat/completions";
const MODEL = "google/gemini-2.5-flash";

async function callAI(messages: Array<{ role: string; content: string }>, schema: unknown) {
  const key = process.env.LOVABLE_API_KEY;
  if (!key) throw new Error("LOVABLE_API_KEY missing");
  const res = await fetch(GATEWAY_URL, {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      "Lovable-API-Key": key,
    },
    body: JSON.stringify({
      model: MODEL,
      messages,
      tools: [{ type: "function", function: { name: "respond", description: "Return structured response", parameters: schema } }],
      tool_choice: { type: "function", function: { name: "respond" } },
    }),
  });
  if (!res.ok) {
    const text = await res.text();
    if (res.status === 429) throw new Error("AI rate limit — try again in a moment.");
    if (res.status === 402) throw new Error("AI credits exhausted. Add credits in workspace settings.");
    throw new Error(`AI error ${res.status}: ${text.slice(0, 200)}`);
  }
  const data = await res.json();
  const call = data.choices?.[0]?.message?.tool_calls?.[0];
  if (!call) throw new Error("AI returned no structured output");
  return JSON.parse(call.function.arguments);
}

const CalibrateInput = z.object({
  title: z.string().min(3),
  baseline: z.string().min(1),
  targetDate: z.string().min(1),
  obstacles: z.string().optional().default(""),
  whyMotivation: z.string().optional().default(""),
  whatIfNot: z.string().optional().default(""),
});

export const calibrateGoal = createServerFn({ method: "POST" })
  .middleware([requireSupabaseAuth])
  .inputValidator((d: unknown) => CalibrateInput.parse(d))
  .handler(async ({ data, context }) => {
    const schema = {
      type: "object",
      properties: {
        calibrated_target: { type: "string", description: "Specific, measurable target (e.g. 'Run a 4:00 marathon')" },
        calibrated_metric: { type: "string", description: "How progress is measured" },
        calibrated_deadline: { type: "string", description: "ISO date YYYY-MM-DD, adjusted if needed" },
        difficulty_tier: { type: "string", enum: ["easy", "moderate", "hard", "very_hard", "unrealistic"] },
        smart_score: { type: "number", description: "0-100 SMART alignment" },
        explanation: { type: "string", description: "Plain English 2-3 sentences on the adjustment vs original" },
        was_recalibrated: { type: "boolean" },
      },
      required: ["calibrated_target", "calibrated_metric", "calibrated_deadline", "difficulty_tier", "smart_score", "explanation", "was_recalibrated"],
      additionalProperties: false,
    };
    const sys = `You are a goal-setting coach. Rate the user's goal against SMART criteria. Aim for "hard but achievable" — roughly 90th percentile difficulty for the stated baseline. If unrealistic for the timeframe, RECALIBRATE by adjusting the target OR extending the deadline (or both together — they are linked). Return the recalibrated goal with a plain-English explanation of what changed and why. If the original is already well-calibrated, return it essentially unchanged with was_recalibrated=false.`;
    const user = `Goal: ${data.title}\nCurrent baseline: ${data.baseline}\nStated target date: ${data.targetDate}\nUsual obstacles: ${data.obstacles || "(none stated)"}`;
    const result = await callAI([
      { role: "system", content: sys },
      { role: "user", content: user },
    ], schema);

    const { data: goal, error } = await context.supabase
      .from("goals")
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
        calibration_status: "calibrated",
        why_motivation: data.whyMotivation,
        what_if_not: data.whatIfNot,
        obstacles: data.obstacles,
      })
      .select()
      .single();
    if (error) throw new Error(error.message);
    return { goal, calibration: result };
  });

const BreakdownInput = z.object({ goalId: z.string().uuid() });

export const generateBreakdown = createServerFn({ method: "POST" })
  .middleware([requireSupabaseAuth])
  .inputValidator((d: unknown) => BreakdownInput.parse(d))
  .handler(async ({ data, context }) => {
    const { data: goal, error: gErr } = await context.supabase
      .from("goals").select("*").eq("id", data.goalId).single();
    if (gErr || !goal) throw new Error("Goal not found");

    await context.supabase.from("tasks").delete().eq("goal_id", goal.id);
    await context.supabase.from("daily_actions").delete().eq("goal_id", goal.id);

    const deadlineStr = goal.calibrated_deadline || goal.target_date || "";
    const weeksLeft = Math.max(1, Math.min(16, Math.ceil(
      (new Date(deadlineStr || Date.now() + 8 * 7 * 86400000).getTime() - Date.now()) / (7 * 86400000)
    )));

    const schema = {
      type: "object",
      properties: {
        weeks: {
          type: "array",
          items: {
            type: "object",
            properties: {
              week_number: { type: "number" },
              theme: { type: "string" },
              tasks: {
                type: "array",
                items: {
                  type: "object",
                  properties: {
                    title: { type: "string" },
                    description: { type: "string" },
                    estimated_hours: { type: "number", description: "1-2" },
                    if_then_plans: {
                      type: "array",
                      items: {
                        type: "object",
                        properties: { trigger: { type: "string" }, response: { type: "string" } },
                        required: ["trigger", "response"],
                        additionalProperties: false,
                      },
                    },
                  },
                  required: ["title", "description", "estimated_hours", "if_then_plans"],
                  additionalProperties: false,
                },
              },
            },
            required: ["week_number", "theme", "tasks"],
            additionalProperties: false,
          },
        },
        daily_actions: {
          type: "array",
          description: "2-4 recurring daily habits that support the goal",
          items: {
            type: "object",
            properties: {
              title: { type: "string" },
              description: { type: "string" },
            },
            required: ["title", "description"],
            additionalProperties: false,
          },
        },
      },
      required: ["weeks", "daily_actions"],
      additionalProperties: false,
    };

    const sys = `You break down calibrated goals into weekly "sprints" of concrete tasks (each 1-2 hours max). For each task include 1-2 if-then plans tied to the user's stated obstacles. Also produce 2-4 recurring daily actions (habits) that support the goal — these become the habit tracker. Keep tasks specific and actionable, not generic.`;
    const user = `Calibrated goal: ${goal.calibrated_target}\nMetric: ${goal.calibrated_metric}\nDeadline: ${goal.calibrated_deadline}\nDifficulty: ${goal.difficulty_tier}\nBaseline: ${goal.baseline}\nObstacles user mentioned: ${goal.obstacles || "(none)"}\nWeeks available: ${weeksLeft}\n\nProduce ${Math.min(weeksLeft, 8)} weeks of sprints (3-5 tasks each) and daily actions.`;

    const result = await callAI([
      { role: "system", content: sys },
      { role: "user", content: user },
    ], schema);

    const taskRows: TablesInsert<"tasks">[] = [];
    for (const w of result.weeks) {
      w.tasks.forEach((t: { title: string; description: string; estimated_hours: number; if_then_plans: unknown }, i: number) => {
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
      const { error: tErr } = await context.supabase.from("tasks").insert(taskRows);
      if (tErr) throw new Error(tErr.message);
    }

    const actionRows = result.daily_actions.map((a: { title: string; description: string }) => ({
      user_id: context.userId,
      goal_id: goal.id,
      title: a.title,
      description: a.description,
    }));
    if (actionRows.length) {
      const { error: aErr } = await context.supabase.from("daily_actions").insert(actionRows);
      if (aErr) throw new Error(aErr.message);
    }

    return { ok: true, taskCount: taskRows.length, actionCount: actionRows.length };
  });
```

## src/integrations/supabase/

**src/integrations/supabase/client.ts**
```typescript
import { createClient } from '@supabase/supabase-js';
import type { Database } from './types';

function isNewSupabaseApiKey(value: string): boolean {
  return value.startsWith('sb_publishable_') || value.startsWith('sb_secret_');
}

function createSupabaseFetch(supabaseKey: string): typeof fetch {
  return (input, init) => {
    const headers = new Headers(
      typeof Request !== 'undefined' && input instanceof Request ? input.headers : undefined,
    );

    if (init?.headers) {
      new Headers(init.headers).forEach((value, key) => headers.set(key, value));
    }

    if (isNewSupabaseApiKey(supabaseKey) && headers.get('Authorization') === `Bearer ${supabaseKey}`) {
      headers.delete('Authorization');
    }

    headers.set('apikey', supabaseKey);
    return fetch(input, { ...init, headers });
  };
}

function createSupabaseClient() {
  const SUPABASE_URL = import.meta.env.VITE_SUPABASE_URL || process.env.SUPABASE_URL;
  const SUPABASE_PUBLISHABLE_KEY = import.meta.env.VITE_SUPABASE_PUBLISHABLE_KEY || process.env.SUPABASE_PUBLISHABLE_KEY;

  if (!SUPABASE_URL || !SUPABASE_PUBLISHABLE_KEY) {
    const missing = [
      ...(!SUPABASE_URL ? ['SUPABASE_URL'] : []),
      ...(!SUPABASE_PUBLISHABLE_KEY ? ['SUPABASE_PUBLISHABLE_KEY'] : []),
    ];
    const message = `Missing Supabase environment variable(s): ${missing.join(', ')}. Connect Supabase in Lovable Cloud.`;
    console.error(`[Supabase] ${message}`);
    throw new Error(message);
  }

  return createClient<Database>(SUPABASE_URL, SUPABASE_PUBLISHABLE_KEY, {
    global: {
      fetch: createSupabaseFetch(SUPABASE_PUBLISHABLE_KEY),
    },
    auth: {
      storage: typeof window !== 'undefined' ? localStorage : undefined,
      persistSession: true,
      autoRefreshToken: true,
    }
  });
}

let _supabase: ReturnType<typeof createSupabaseClient> | undefined;

export const supabase = new Proxy({} as ReturnType<typeof createSupabaseClient>, {
  get(_, prop, receiver) {
    if (!_supabase) _supabase = createSupabaseClient();
    return Reflect.get(_supabase, prop, receiver);
  },
});
```

**src/integrations/supabase/client.server.ts**
```typescript
import { createClient } from '@supabase/supabase-js';
import type { Database } from './types';

function isNewSupabaseApiKey(value: string): boolean {
  return value.startsWith('sb_publishable_') || value.startsWith('sb_secret_');
}

function createSupabaseFetch(supabaseKey: string): typeof fetch {
  return (input, init) => {
    const headers = new Headers(
      typeof Request !== 'undefined' && input instanceof Request ? input.headers : undefined,
    );

    if (init?.headers) {
      new Headers(init.headers).forEach((value, key) => headers.set(key, value));
    }

    if (isNewSupabaseApiKey(supabaseKey) && headers.get('Authorization') === `Bearer ${supabaseKey}`) {
      headers.delete('Authorization');
    }

    headers.set('apikey', supabaseKey);
    return fetch(input, { ...init, headers });
  };
}

function createSupabaseAdminClient() {
  const SUPABASE_URL = process.env.SUPABASE_URL;
  const SUPABASE_SERVICE_ROLE_KEY = process.env.SUPABASE_SERVICE_ROLE_KEY;

  if (!SUPABASE_URL || !SUPABASE_SERVICE_ROLE_KEY) {
    const missing = [
      ...(!SUPABASE_URL ? ['SUPABASE_URL'] : []),
      ...(!SUPABASE_SERVICE_ROLE_KEY ? ['SUPABASE_SERVICE_ROLE_KEY'] : []),
    ];
    const message = `Missing Supabase environment variable(s): ${missing.join(', ')}. Connect Supabase in Lovable Cloud.`;
    console.error(`[Supabase] ${message}`);
    throw new Error(message);
  }

  return createClient<Database>(SUPABASE_URL, SUPABASE_SERVICE_ROLE_KEY, {
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

let _supabaseAdmin: ReturnType<typeof createSupabaseAdminClient> | undefined;

export const supabaseAdmin = new Proxy({} as ReturnType<typeof createSupabaseAdminClient>, {
  get(_, prop, receiver) {
    if (!_supabaseAdmin) _supabaseAdmin = createSupabaseAdminClient();
    return Reflect.get(_supabaseAdmin, prop, receiver);
  },
});
```

**src/integrations/supabase/auth-attacher.ts**
```typescript
import { createMiddleware } from '@tanstack/react-start'
import { supabase } from './client'

export const attachSupabaseAuth = createMiddleware({ type: 'function' }).client(
  async ({ next }) => {
    const { data } = await supabase.auth.getSession()
    const token = data.session?.access_token
    return next({
      headers: token ? { Authorization: `Bearer ${token}` } : {},
    })
  },
)
```

**src/integrations/supabase/auth-middleware.ts**
```typescript
import { createMiddleware } from '@tanstack/react-start'
import { getRequest } from '@tanstack/react-start/server'
import { createClient } from '@supabase/supabase-js'
import type { Database } from './types'

function isNewSupabaseApiKey(value: string): boolean {
  return value.startsWith('sb_publishable_') || value.startsWith('sb_secret_');
}

function createSupabaseFetch(supabaseKey: string): typeof fetch {
  return (input, init) => {
    const headers = new Headers(
      typeof Request !== 'undefined' && input instanceof Request ? input.headers : undefined,
    );

    if (init?.headers) {
      new Headers(init.headers).forEach((value, key) => headers.set(key, value));
    }

    if (isNewSupabaseApiKey(supabaseKey) && headers.get('Authorization') === `Bearer ${supabaseKey}`) {
      headers.delete('Authorization');
    }

    headers.set('apikey', supabaseKey);
    return fetch(input, { ...init, headers });
  };
}

export const requireSupabaseAuth = createMiddleware({ type: 'function' }).server(
  async ({ next }) => {
    const SUPABASE_URL = process.env.SUPABASE_URL;
    const SUPABASE_PUBLISHABLE_KEY = process.env.SUPABASE_PUBLISHABLE_KEY;

    if (!SUPABASE_URL || !SUPABASE_PUBLISHABLE_KEY) {
      const missing = [
        ...(!SUPABASE_URL ? ['SUPABASE_URL'] : []),
        ...(!SUPABASE_PUBLISHABLE_KEY ? ['SUPABASE_PUBLISHABLE_KEY'] : []),
      ];
      const message = `Missing Supabase environment variable(s): ${missing.join(', ')}. Connect Supabase in Lovable Cloud.`;
      console.error(`[Supabase] ${message}`);
      throw new Error(message);
    }

    const request = getRequest();

    if (!request?.headers) {
      throw new Error('Unauthorized: No request headers available');
    }

    const authHeader = request.headers.get('authorization');

    if (!authHeader) {
      throw new Error('Unauthorized: No authorization header provided');
    }

    if (!authHeader.startsWith('Bearer ')) {
      throw new Error('Unauthorized: Only Bearer tokens are supported');
    }

    const token = authHeader.replace('Bearer ', '');
    if (!token) {
      throw new Error('Unauthorized: No token provided');
    }

    if (token.split('.').length !== 3) {
      throw new Error('Unauthorized: Invalid token');
    }

    const supabase = createClient<Database>(
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
      throw new Error('Unauthorized: Invalid token');
    }

    if (!data.claims.sub) {
      throw new Error('Unauthorized: No user ID found in token');
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
```

**src/integrations/supabase/types.ts**
```typescript
export type Json =
  | string
  | number
  | boolean
  | null
  | { [key: string]: Json | undefined }
  | Json[]

export type Database = {
  __InternalSupabase: {
    PostgrestVersion: "14.5"
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
            foreignKeyName: "action_completions_daily_action_id_fkey"
            columns: ["daily_action_id"]
            isOneToOne: false
            referencedRelation: "daily_actions"
            referencedColumns: ["id"]
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
            foreignKeyName: "daily_actions_goal_id_fkey"
            columns: ["goal_id"]
            isOneToOne: false
            referencedRelation: "goals"
            referencedColumns: ["id"]
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
            foreignKeyName: "streak_freezes_goal_id_fkey"
            columns: ["goal_id"]
            isOneToOne: false
            referencedRelation: "goals"
            referencedColumns: ["id"]
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
            foreignKeyName: "tasks_goal_id_fkey"
            columns: ["goal_id"]
            isOneToOne: false
            referencedRelation: "goals"
            referencedColumns: ["id"]
          },
        ]
      }
    }
    Views: { [_ in never]: never }
    Functions: { [_ in never]: never }
    Enums: { [_ in never]: never }
    CompositeTypes: { [_ in never]: never }
  }
}

type DatabaseWithoutInternals = Omit<Database, "__InternalSupabase">
type DefaultSchema = DatabaseWithoutInternals[Extract<keyof Database, "public">]

export type Tables
  DefaultSchemaTableNameOrOptions extends
    | keyof (DefaultSchema["Tables"] & DefaultSchema["Views"])
    | { schema: keyof DatabaseWithoutInternals },
  TableName extends DefaultSchemaTableNameOrOptions extends {
    schema: keyof DatabaseWithoutInternals
  }
    ? keyof (DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions["schema"]]["Tables"] &
        DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions["schema"]]["Views"])
    : never = never,
> = DefaultSchemaTableNameOrOptions extends {
  schema: keyof DatabaseWithoutInternals
}
  ? (DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions["schema"]]["Tables"] &
      DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions["schema"]]["Views"])[TableName] extends {
      Row: infer R
    }
    ? R
    : never
  : DefaultSchemaTableNameOrOptions extends keyof (DefaultSchema["Tables"] &
        DefaultSchema["Views"])
    ? (DefaultSchema["Tables"] &
        DefaultSchema["Views"])[DefaultSchemaTableNameOrOptions] extends {
        Row: infer R
      }
      ? R
      : never
    : never

export type TablesInsert
  DefaultSchemaTableNameOrOptions extends
    | keyof DefaultSchema["Tables"]
    | { schema: keyof DatabaseWithoutInternals },
  TableName extends DefaultSchemaTableNameOrOptions extends {
    schema: keyof DatabaseWithoutInternals
  }
    ? keyof DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions["schema"]]["Tables"]
    : never = never,
> = DefaultSchemaTableNameOrOptions extends {
  schema: keyof DatabaseWithoutInternals
}
  ? DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions["schema"]]["Tables"][TableName] extends {
      Insert: infer I
    }
    ? I
    : never
  : DefaultSchemaTableNameOrOptions extends keyof DefaultSchema["Tables"]
    ? DefaultSchema["Tables"][DefaultSchemaTableNameOrOptions] extends {
        Insert: infer I
      }
      ? I
      : never
    : never

export type TablesUpdate
  DefaultSchemaTableNameOrOptions extends
    | keyof DefaultSchema["Tables"]
    | { schema: keyof DatabaseWithoutInternals },
  TableName extends DefaultSchemaTableNameOrOptions extends {
    schema: keyof DatabaseWithoutInternals
  }
    ? keyof DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions["schema"]]["Tables"]
    : never = never,
> = DefaultSchemaTableNameOrOptions extends {
  schema: keyof DatabaseWithoutInternals
}
  ? DatabaseWithoutInternals[DefaultSchemaTableNameOrOptions["schema"]]["Tables"][TableName] extends {
      Update: infer U
    }
    ? U
    : never
  : DefaultSchemaTableNameOrOptions extends keyof DefaultSchema["Tables"]
    ? DefaultSchema["Tables"][DefaultSchemaTableNameOrOptions] extends {
        Update: infer U
      }
      ? U
      : never
    : never

export type Enums
  DefaultSchemaEnumNameOrOptions extends
    | keyof DefaultSchema["Enums"]
    | { schema: keyof DatabaseWithoutInternals },
  EnumName extends DefaultSchemaEnumNameOrOptions extends {
    schema: keyof DatabaseWithoutInternals
  }
    ? keyof DatabaseWithoutInternals[DefaultSchemaEnumNameOrOptions["schema"]]["Enums"]
    : never = never,
> = DefaultSchemaEnumNameOrOptions extends {
  schema: keyof DatabaseWithoutInternals
}
  ? DatabaseWithoutInternals[DefaultSchemaEnumNameOrOptions["schema"]]["Enums"][EnumName]
  : DefaultSchemaEnumNameOrOptions extends keyof DefaultSchema["Enums"]
    ? DefaultSchema["Enums"][DefaultSchemaEnumNameOrOptions]
    : never

export type CompositeTypes
  PublicCompositeTypeNameOrOptions extends
    | keyof DefaultSchema["CompositeTypes"]
    | { schema: keyof DatabaseWithoutInternals },
  CompositeTypeName extends PublicCompositeTypeNameOrOptions extends {
    schema: keyof DatabaseWithoutInternals
  }
    ? keyof DatabaseWithoutInternals[PublicCompositeTypeNameOrOptions["schema"]]["CompositeTypes"]
    : never = never,
> = PublicCompositeTypeNameOrOptions extends {
  schema: keyof DatabaseWithoutInternals
}
  ? DatabaseWithoutInternals[PublicCompositeTypeNameOrOptions["schema"]]["CompositeTypes"][CompositeTypeName]
  : PublicCompositeTypeNameOrOptions extends keyof DefaultSchema["CompositeTypes"]
    ? DefaultSchema["CompositeTypes"][PublicCompositeTypeNameOrOptions]
    : never

export const Constants = {
  public: {
    Enums: {},
  },
} as const
```

**src/integrations/lovable/index.ts**
```typescript
import { createLovableAuth } from "@lovable.dev/cloud-auth-js";
import { supabase } from "../supabase/client";
const lovableAuth = createLovableAuth();

type SignInOptions = {
  redirect_uri?: string;
  extraParams?: Record<string, string>;
};

export const lovable = {
  auth: {
    signInWithOAuth: async (provider: "google" | "apple" | "microsoft" | "lovable", opts?: SignInOptions) => {
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
```

## src/hooks/

**src/hooks/use-mobile.tsx**
```typescript
import * as React from "react";

const MOBILE_BREAKPOINT = 768;

export function useIsMobile() {
  const [isMobile, setIsMobile] = React.useState<boolean | undefined>(undefined);

  React.useEffect(() => {
    const mql = window.matchMedia(`(max-width: ${MOBILE_BREAKPOINT - 1}px)`);
    const onChange = () => {
      setIsMobile(window.innerWidth < MOBILE_BREAKPOINT);
    };
    mql.addEventListener("change", onChange);
    setIsMobile(window.innerWidth < MOBILE_BREAKPOINT);
    return () => mql.removeEventListener("change", onChange);
  }, []);

  return !!isMobile;
}
```

## src/components/

**src/components/app-shell.tsx**
```tsx
import { Link, useNavigate } from "@tanstack/react-router";
import { Flame, Plus, LogOut } from "lucide-react";
import { Button } from "@/components/ui/button";
import { supabase } from "@/integrations/supabase/client";
import type { ReactNode } from "react";

export function AppShell({ children, streakTotal }: { children: ReactNode; streakTotal?: number }) {
  const navigate = useNavigate();
  return (
    <div className="min-h-screen bg-background">
      <header className="sticky top-0 z-20 border-b border-border/60 bg-background/80 backdrop-blur">
        <div className="mx-auto flex max-w-6xl items-center justify-between px-4 py-3 sm:px-6">
          <Link to="/dashboard" className="flex items-center gap-2">
            <Flame className="h-5 w-5 text-primary animate-flame" />
            <span className="font-display text-lg font-semibold">Momentum</span>
          </Link>
          <div className="flex items-center gap-2 sm:gap-3">
            {typeof streakTotal === "number" && (
              <div className="flex items-center gap-1.5 rounded-full bg-primary/10 px-3 py-1.5 text-sm font-semibold text-primary">
                <Flame className="h-4 w-4" />
                {streakTotal}
              </div>
            )}
            <Button asChild size="sm" className="gap-1">
              <Link to="/goals/new"><Plus className="h-4 w-4" />New goal</Link>
            </Button>
            <Button
              size="icon"
              variant="ghost"
              aria-label="Sign out"
              onClick={async () => {
                await supabase.auth.signOut();
                navigate({ to: "/auth" });
              }}
            >
              <LogOut className="h-4 w-4" />
            </Button>
          </div>
        </div>
      </header>
      <main className="mx-auto max-w-6xl px-4 py-8 sm:px-6">{children}</main>
    </div>
  );
}
```

## src/routes/

**src/routes/__root.tsx**
```tsx
import { QueryClient, QueryClientProvider } from "@tanstack/react-query";
import {
  Outlet,
  Link,
  createRootRouteWithContext,
  useRouter,
  HeadContent,
  Scripts,
} from "@tanstack/react-router";
import { useEffect, type ReactNode } from "react";
import { Toaster } from "sonner";

import appCss from "../styles.css?url";
import { reportLovableError } from "../lib/lovable-error-reporting";

function NotFoundComponent() {
  return (
    <div className="flex min-h-screen items-center justify-center bg-background px-4">
      <div className="max-w-md text-center">
        <h1 className="text-7xl font-bold text-foreground">404</h1>
        <h2 className="mt-4 text-xl font-semibold text-foreground">Page not found</h2>
        <p className="mt-2 text-sm text-muted-foreground">
          The page you're looking for doesn't exist or has been moved.
        </p>
        <div className="mt-6">
          <Link
            to="/"
            className="inline-flex items-center justify-center rounded-md bg-primary px-4 py-2 text-sm font-medium text-primary-foreground transition-colors hover:bg-primary/90"
          >
            Go home
          </Link>
        </div>
      </div>
    </div>
  );
}

function ErrorComponent({ error, reset }: { error: Error; reset: () => void }) {
  console.error(error);
  const router = useRouter();
  useEffect(() => {
    reportLovableError(error, { boundary: "tanstack_root_error_component" });
  }, [error]);

  return (
    <div className="flex min-h-screen items-center justify-center bg-background px-4">
      <div className="max-w-md text-center">
        <h1 className="text-xl font-semibold tracking-tight text-foreground">
          This page didn't load
        </h1>
        <p className="mt-2 text-sm text-muted-foreground">
          Something went wrong on our end. You can try refreshing or head back home.
        </p>
        <div className="mt-6 flex flex-wrap justify-center gap-2">
          <button
            onClick={() => {
              router.invalidate();
              reset();
            }}
            className="inline-flex items-center justify-center rounded-md bg-primary px-4 py-2 text-sm font-medium text-primary-foreground transition-colors hover:bg-primary/90"
          >
            Try again
          </button>
          
            href="/"
            className="inline-flex items-center justify-center rounded-md border border-input bg-background px-4 py-2 text-sm font-medium text-foreground transition-colors hover:bg-accent"
          >
            Go home
          </a>
        </div>
      </div>
    </div>
  );
}

export const Route = createRootRouteWithContext<{ queryClient: QueryClient }>()({
  head: () => ({
    meta: [
      { charSet: "utf-8" },
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      { title: "Momentum — goals that actually happen" },
      { name: "description", content: "Calibrate ambitious goals, break them into daily steps, and keep the streak alive." },
      { property: "og:title", content: "Momentum — goals that actually happen" },
      { property: "og:description", content: "Calibrate ambitious goals, break them into daily steps, and keep the streak alive." },
      { property: "og:type", content: "website" },
      { name: "twitter:card", content: "summary_large_image" },
      { name: "twitter:title", content: "Momentum — goals that actually happen" },
      { name: "twitter:description", content: "Calibrate ambitious goals, break them into daily steps, and keep the streak alive." },
    ],
    links: [
      { rel: "stylesheet", href: appCss },
      { rel: "icon", href: "/favicon.ico", type: "image/x-icon" },
      { rel: "preconnect", href: "https://fonts.googleapis.com" },
      { rel: "preconnect", href: "https://fonts.gstatic.com", crossOrigin: "anonymous" },
      { rel: "stylesheet", href: "https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,600;9..144,700&family=Manrope:wght@400;500;600;700;800&display=swap" },
    ],
  }),
  shellComponent: RootShell,
  component: RootComponent,
  notFoundComponent: NotFoundComponent,
  errorComponent: ErrorComponent,
});

function RootShell({ children }: { children: ReactNode }) {
  return (
    <html lang="en">
      <head>
        <HeadContent />
      </head>
      <body>
        {children}
        <Scripts />
      </body>
    </html>
  );
}

function RootComponent() {
  const { queryClient } = Route.useRouteContext();
  const router = useRouter();

  useEffect(() => {
    let mounted = true;
    import("@/integrations/supabase/client").then(({ supabase }) => {
      if (!mounted) return;
      const { data: sub } = supabase.auth.onAuthStateChange((event) => {
        if (event !== "SIGNED_IN" && event !== "SIGNED_OUT" && event !== "USER_UPDATED") return;
        router.invalidate();
        if (event !== "SIGNED_OUT") queryClient.invalidateQueries();
      });
      (window as unknown as { __momentumAuthSub?: { unsubscribe: () => void } }).__momentumAuthSub = sub.subscription;
    });
    return () => {
      mounted = false;
      const w = window as unknown as { __momentumAuthSub?: { unsubscribe: () => void } };
      w.__momentumAuthSub?.unsubscribe();
    };
  }, [queryClient, router]);

  return (
    <QueryClientProvider client={queryClient}>
      <Outlet />
      <Toaster position="top-center" richColors />
    </QueryClientProvider>
  );
}
```

**src/routes/index.tsx**
```tsx
import { createFileRoute, Link } from "@tanstack/react-router";
import { Flame, Target, CalendarCheck, Sparkles } from "lucide-react";
import { Button } from "@/components/ui/button";

export const Route = createFileRoute("/")({
  component: Landing,
});

function Landing() {
  return (
    <div className="min-h-screen bg-background text-foreground">
      <header className="mx-auto flex max-w-6xl items-center justify-between px-6 py-6">
        <div className="flex items-center gap-2">
          <Flame className="h-6 w-6 text-primary animate-flame" />
          <span className="font-display text-xl font-semibold">Momentum</span>
        </div>
        <nav className="flex items-center gap-3">
          <Link to="/auth" className="text-sm text-muted-foreground hover:text-foreground">
            Sign in
          </Link>
          <Button asChild size="sm">
            <Link to="/auth">Get started</Link>
          </Button>
        </nav>
      </header>

      <main className="mx-auto max-w-6xl px-6">
        <section className="py-20 md:py-28">
          <div className="mx-auto max-w-3xl text-center">
            <span className="inline-flex items-center gap-1.5 rounded-full border border-border bg-card px-3 py-1 text-xs font-medium text-muted-foreground">
              <Sparkles className="h-3.5 w-3.5 text-primary" /> SMART calibration · AI task breakdown · streaks
            </span>
            <h1 className="mt-6 font-display text-5xl font-semibold leading-[1.05] tracking-tight md:text-7xl">
              Goals that actually{" "}
              <span className="flame-text">happen.</span>
            </h1>
            <p className="mt-6 text-lg text-muted-foreground md:text-xl">
              You've tried habit trackers before. Momentum calibrates your goal against reality,
              breaks it into 1-2 hour steps, and keeps you moving with a streak worth protecting.
            </p>
            <div className="mt-8 flex flex-wrap items-center justify-center gap-3">
              <Button asChild size="lg" className="h-12 px-6 text-base">
                <Link to="/auth">Start your first goal</Link>
              </Button>
            </div>
          </div>
        </section>

        <section className="grid gap-4 pb-24 md:grid-cols-3">
          {[
            { icon: Target, title: "Calibrate", body: "Tell us the goal, baseline, and deadline. AI recalibrates to hard-but-achievable." },
            { icon: CalendarCheck, title: "Break it down", body: "Weekly sprints of 1-2 hour tasks, plus if-then plans for your usual obstacles." },
            { icon: Flame, title: "Keep the streak", body: "Duolingo-style tracker with a two-day rule and monthly freezes when life happens." },
          ].map(({ icon: Icon, title, body }) => (
            <div key={title} className="rounded-2xl border border-border bg-card p-6 shadow-soft">
              <Icon className="h-8 w-8 text-primary" />
              <h3 className="mt-4 font-display text-xl font-semibold">{title}</h3>
              <p className="mt-2 text-sm text-muted-foreground">{body}</p>
            </div>
          ))}
        </section>
      </main>
    </div>
  );
}
```

**src/routes/auth.tsx**
```tsx
import { createFileRoute, useNavigate, Link } from "@tanstack/react-router";
import { useState, useEffect } from "react";
import { supabase } from "@/integrations/supabase/client";
import { lovable } from "@/integrations/lovable";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Label } from "@/components/ui/label";
import { Flame } from "lucide-react";
import { toast } from "sonner";

export const Route = createFileRoute("/auth")({
  component: AuthPage,
});

function AuthPage() {
  const navigate = useNavigate();
  const [mode, setMode] = useState<"signin" | "signup">("signin");
  const [email, setEmail] = useState("");
  const [password, setPassword] = useState("");
  const [loading, setLoading] = useState(false);

  useEffect(() => {
    supabase.auth.getUser().then(({ data }) => {
      if (data.user) navigate({ to: "/dashboard" });
    });
  }, [navigate]);

  const handleSubmit = async (e: React.FormEvent) => {
    e.preventDefault();
    setLoading(true);
    try {
      if (mode === "signup") {
        const { error } = await supabase.auth.signUp({
          email,
          password,
          options: { emailRedirectTo: window.location.origin },
        });
        if (error) throw error;
        toast.success("Account created! Check your email if confirmation is required.");
      } else {
        const { error } = await supabase.auth.signInWithPassword({ email, password });
        if (error) throw error;
      }
      navigate({ to: "/dashboard" });
    } catch (err) {
      toast.error(err instanceof Error ? err.message : "Auth failed");
    } finally {
      setLoading(false);
    }
  };

  const handleGoogle = async () => {
    const result = await lovable.auth.signInWithOAuth("google", {
      redirect_uri: window.location.origin,
    });
    if (result.error) {
      toast.error(result.error.message || "Google sign-in failed");
      return;
    }
    if (result.redirected) return;
    navigate({ to: "/dashboard" });
  };

  return (
    <div className="flex min-h-screen items-center justify-center bg-background px-4 py-12">
      <div className="w-full max-w-md">
        <Link to="/" className="mb-8 flex items-center justify-center gap-2">
          <Flame className="h-6 w-6 text-primary animate-flame" />
          <span className="font-display text-xl font-semibold">Momentum</span>
        </Link>
        <div className="rounded-2xl border border-border bg-card p-8 shadow-soft">
          <h1 className="font-display text-2xl font-semibold">
            {mode === "signin" ? "Welcome back" : "Create your account"}
          </h1>
          <p className="mt-1 text-sm text-muted-foreground">
            {mode === "signin" ? "Pick up where you left off." : "Start your first calibrated goal."}
          </p>

          <Button
            type="button"
            variant="outline"
            className="mt-6 w-full"
            onClick={handleGoogle}
          >
            <svg className="mr-2 h-4 w-4" viewBox="0 0 24 24">
              <path fill="#4285F4" d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z"/>
              <path fill="#34A853" d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z"/>
              <path fill="#FBBC05" d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l3.66-2.84z"/>
              <path fill="#EA4335" d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z"/>
            </svg>
            Continue with Google
          </Button>

          <div className="my-6 flex items-center gap-3">
            <div className="h-px flex-1 bg-border" />
            <span className="text-xs text-muted-foreground">or</span>
            <div className="h-px flex-1 bg-border" />
          </div>

          <form onSubmit={handleSubmit} className="space-y-4">
            <div>
              <Label htmlFor="email">Email</Label>
              <Input id="email" type="email" required value={email} onChange={(e) => setEmail(e.target.value)} className="mt-1.5" />
            </div>
            <div>
              <Label htmlFor="password">Password</Label>
              <Input id="password" type="password" required minLength={6} value={password} onChange={(e) => setPassword(e.target.value)} className="mt-1.5" />
            </div>
            <Button type="submit" className="w-full" disabled={loading}>
              {loading ? "..." : mode === "signin" ? "Sign in" : "Create account"}
            </Button>
          </form>

          <button
            type="button"
            className="mt-4 w-full text-center text-sm text-muted-foreground hover:text-foreground"
            onClick={() => setMode(mode === "signin" ? "signup" : "signin")}
          >
            {mode === "signin" ? "New here? Create an account" : "Already have an account? Sign in"}
          </button>
        </div>
      </div>
    </div>
  );
}
```

**src/routes/_authenticated/route.tsx**
```tsx
import { createFileRoute, Outlet, redirect } from "@tanstack/react-router";
import { supabase } from "@/integrations/supabase/client";

export const Route = createFileRoute("/_authenticated")({
  ssr: false,
  beforeLoad: async () => {
    const { data, error } = await supabase.auth.getUser();
    if (error || !data.user) throw redirect({ to: "/auth" });
    return { user: data.user };
  },
  component: () => <Outlet />,
});
```

**src/routes/_authenticated/dashboard.tsx**
```tsx
import { createFileRoute, Link, useNavigate } from "@tanstack/react-router";
import { useQuery } from "@tanstack/react-query";
import { supabase } from "@/integrations/supabase/client";
import { AppShell } from "@/components/app-shell";
import { Button } from "@/components/ui/button";
import { Card } from "@/components/ui/card";
import { Progress } from "@/components/ui/progress";
import { Flame, Plus, Target, Calendar, TrendingUp } from "lucide-react";
import { calcStreak, toISO } from "@/lib/streak";
import { useEffect, useState } from "react";

export const Route = createFileRoute("/_authenticated/dashboard")({
  component: Dashboard,
});

function Dashboard() {
  const navigate = useNavigate();
  const [userId, setUserId] = useState<string | null>(null);
  useEffect(() => {
    supabase.auth.getUser().then(({ data }) => setUserId(data.user?.id ?? null));
  }, []);

  const { data, isLoading } = useQuery({
    queryKey: ["dashboard", userId],
    enabled: !!userId,
    queryFn: async () => {
      const [g, t, a, c, f] = await Promise.all([
        supabase.from("goals").select("*").eq("status", "active").order("created_at", { ascending: false }),
        supabase.from("tasks").select("id,goal_id,completed,week_number"),
        supabase.from("daily_actions").select("id,goal_id,active"),
        supabase.from("action_completions").select("completed_date,daily_action_id"),
        supabase.from("streak_freezes").select("freeze_date,goal_id"),
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
    return <AppShell><p className="text-muted-foreground">Loading…</p></AppShell>;
  }

  const allCompleted = new Set(data.completions.map((c) => c.completed_date));
  const allFreezes = new Set(data.freezes.map((f) => f.freeze_date));
  const overall = calcStreak(allCompleted, allFreezes);

  if (data.goals.length === 0) {
    return (
      <AppShell streakTotal={overall.current}>
        <EmptyState onStart={() => navigate({ to: "/goals/new" })} />
      </AppShell>
    );
  }

  const today = toISO(new Date());

  return (
    <AppShell streakTotal={overall.current}>
      <div className="mb-8 flex items-start justify-between gap-4">
        <div>
          <h1 className="font-display text-3xl font-semibold sm:text-4xl">Your goals</h1>
          <p className="mt-1 text-muted-foreground">
            {overall.current > 0
              ? `You're on a ${overall.current}-day streak. Keep going.`
              : "Check in today to start your streak."}
          </p>
        </div>
      </div>

      <div className="grid gap-4 sm:grid-cols-2">
        {data.goals.map((goal) => {
          const goalActions = data.actions.filter((a) => a.goal_id === goal.id);
          const actionIds = new Set(goalActions.map((a) => a.id));
          const goalCompletions = new Set(
            data.completions.filter((c) => actionIds.has(c.daily_action_id)).map((c) => c.completed_date)
          );
          const goalFreezes = new Set(data.freezes.filter((f) => f.goal_id === goal.id).map((f) => f.freeze_date));
          const streak = calcStreak(goalCompletions, goalFreezes);

          const goalTasks = data.tasks.filter((t) => t.goal_id === goal.id);
          const currentWeek = Math.max(1, ...goalTasks.map((t) => t.week_number));
          const sprintTasks = goalTasks.filter((t) => t.week_number === currentWeek);
          const sprintDone = sprintTasks.filter((t) => t.completed).length;
          const sprintPct = sprintTasks.length ? Math.round((sprintDone / sprintTasks.length) * 100) : 0;

          const doneToday = goalActions.some((a) => goalCompletions.has(today));
          const daysToDeadline = goal.calibrated_deadline
            ? Math.max(0, Math.ceil((new Date(goal.calibrated_deadline).getTime() - Date.now()) / 86400000))
            : null;

          const status = doneToday
            ? { label: "On track today", tone: "success" as const }
            : streak.current > 0
            ? { label: "Check in today", tone: "primary" as const }
            : { label: "Get started", tone: "muted" as const };

          return (
            <Link key={goal.id} to="/goals/$id" params={{ id: goal.id }} className="group">
              <Card className="h-full p-5 transition-all hover:shadow-soft hover:-translate-y-0.5">
                <div className="flex items-start justify-between gap-3">
                  <div className="min-w-0 flex-1">
                    <h3 className="font-display text-xl font-semibold leading-tight">
                      {goal.calibrated_target || goal.title}
                    </h3>
                    {goal.difficulty_tier && (
                      <span className="mt-2 inline-block rounded-full bg-accent px-2 py-0.5 text-xs font-medium text-accent-foreground">
                        {goal.difficulty_tier.replace("_", " ")}
                      </span>
                    )}
                  </div>
                  <div className="flex flex-col items-center rounded-xl bg-primary/10 px-3 py-2 text-primary">
                    <Flame className={`h-5 w-5 ${streak.current > 0 ? "animate-flame" : "opacity-50"}`} />
                    <span className="text-sm font-bold">{streak.current}</span>
                  </div>
                </div>

                <div className="mt-4 space-y-2 text-sm">
                  <div className="flex items-center justify-between text-muted-foreground">
                    <span className="flex items-center gap-1.5"><Target className="h-3.5 w-3.5" /> Week {currentWeek} sprint</span>
                    <span className="font-medium text-foreground">{sprintDone}/{sprintTasks.length}</span>
                  </div>
                  <Progress value={sprintPct} className="h-2" />
                  <div className="flex items-center justify-between pt-1 text-xs">
                    {daysToDeadline !== null && (
                      <span className="flex items-center gap-1 text-muted-foreground">
                        <Calendar className="h-3 w-3" /> {daysToDeadline}d to deadline
                      </span>
                    )}
                    <span className={
                      status.tone === "success" ? "font-medium text-success" :
                      status.tone === "primary" ? "font-medium text-primary" :
                      "text-muted-foreground"
                    }>{status.label}</span>
                  </div>
                </div>
              </Card>
            </Link>
          );
        })}

        <Link to="/goals/new" className="group">
          <Card className="flex h-full min-h-[180px] items-center justify-center border-dashed p-6 transition-colors hover:bg-accent/40">
            <div className="text-center">
              <div className="mx-auto flex h-10 w-10 items-center justify-center rounded-full bg-primary/10 text-primary">
                <Plus className="h-5 w-5" />
              </div>
              <p className="mt-2 font-medium">Add a new goal</p>
              <p className="text-xs text-muted-foreground">Calibrate it against reality</p>
            </div>
          </Card>
        </Link>
      </div>

      <div className="mt-10 grid gap-4 sm:grid-cols-3">
        <StatCard label="Longest streak" value={overall.longest} icon={<Flame className="h-4 w-4" />} />
        <StatCard label="Active goals" value={data.goals.length} icon={<Target className="h-4 w-4" />} />
        <StatCard label="Check-ins (30d)" value={countLast(data.completions.map((c) => c.completed_date), 30)} icon={<TrendingUp className="h-4 w-4" />} />
      </div>
    </AppShell>
  );
}

function StatCard({ label, value, icon }: { label: string; value: number; icon: React.ReactNode }) {
  return (
    <Card className="p-5">
      <div className="flex items-center gap-2 text-sm text-muted-foreground">{icon}{label}</div>
      <p className="mt-2 font-display text-3xl font-semibold">{value}</p>
    </Card>
  );
}

function countLast(dates: string[], n: number) {
  const cutoff = Date.now() - n * 86400000;
  return new Set(dates.filter((d) => new Date(d).getTime() >= cutoff)).size;
}

function EmptyState({ onStart }: { onStart: () => void }) {
  return (
    <div className="mx-auto max-w-lg pt-8 text-center">
      <div className="mx-auto flex h-16 w-16 items-center justify-center rounded-2xl bg-primary/10">
        <Flame className="h-8 w-8 text-primary animate-flame" />
      </div>
      <h1 className="mt-6 font-display text-3xl font-semibold">Set your first goal</h1>
      <p className="mt-2 text-muted-foreground">
        We'll calibrate it against your baseline, break it into weekly sprints, and turn it into a streak worth protecting.
      </p>
      <Button size="lg" className="mt-6" onClick={onStart}>Start now</Button>
    </div>
  );
}
```

**src/routes/_authenticated/goals.new.tsx**
```tsx
import { createFileRoute, useNavigate } from "@tanstack/react-router";
import { useState } from "react";
import { useServerFn } from "@tanstack/react-start";
import { calibrateGoal, generateBreakdown } from "@/lib/goals.functions";
import { AppShell } from "@/components/app-shell";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Label } from "@/components/ui/label";
import { Textarea } from "@/components/ui/textarea";
import { Card } from "@/components/ui/card";
import { Sparkles, ArrowRight, Loader2 } from "lucide-react";
import { toast } from "sonner";

type CalibrationResult = {
  goal: { id: string; title: string; calibrated_target: string; calibrated_metric: string; calibrated_deadline: string; difficulty_tier: string; calibration_explanation: string };
  calibration: { was_recalibrated: boolean; smart_score: number };
};

export const Route = createFileRoute("/_authenticated/goals/new")({
  component: NewGoal,
});

function NewGoal() {
  const navigate = useNavigate();
  const calibrate = useServerFn(calibrateGoal);
  const breakdown = useServerFn(generateBreakdown);

  const [step, setStep] = useState<"form" | "review" | "breakdown">("form");
  const [loading, setLoading] = useState(false);
  const [result, setResult] = useState<CalibrationResult | null>(null);

  const [form, setForm] = useState({
    title: "",
    baseline: "",
    targetDate: "",
    obstacles: "",
    whyMotivation: "",
    whatIfNot: "",
  });

  const handleCalibrate = async (e: React.FormEvent) => {
    e.preventDefault();
    setLoading(true);
    try {
      const res = await calibrate({ data: form }) as CalibrationResult;
      setResult(res);
      setStep("review");
    } catch (err) {
      toast.error(err instanceof Error ? err.message : "Calibration failed");
    } finally {
      setLoading(false);
    }
  };

  const handleAccept = async () => {
    if (!result) return;
    setLoading(true);
    setStep("breakdown");
    try {
      await breakdown({ data: { goalId: result.goal.id } });
      toast.success("Roadmap built");
      navigate({ to: "/goals/$id", params: { id: result.goal.id } });
    } catch (err) {
      toast.error(err instanceof Error ? err.message : "Breakdown failed");
      setStep("review");
    } finally {
      setLoading(false);
    }
  };

  return (
    <AppShell>
      <div className="mx-auto max-w-2xl">
        {step === "form" && (
          <>
            <h1 className="font-display text-3xl font-semibold sm:text-4xl">What do you want to achieve?</h1>
            <p className="mt-2 text-muted-foreground">
              Tell us the goal, where you're starting from, and when you want it done. We'll pressure-test it.
            </p>
            <form onSubmit={handleCalibrate} className="mt-8 space-y-5">
              <div>
                <Label htmlFor="title">Goal</Label>
                <Input id="title" required placeholder="Run a 3-hour marathon" className="mt-1.5"
                  value={form.title} onChange={(e) => setForm({ ...form, title: e.target.value })} />
              </div>
              <div>
                <Label htmlFor="baseline">Where you're starting</Label>
                <Textarea id="baseline" required rows={2} className="mt-1.5"
                  placeholder="I currently run 5k in 35 minutes, twice a week."
                  value={form.baseline} onChange={(e) => setForm({ ...form, baseline: e.target.value })} />
              </div>
              <div>
                <Label htmlFor="targetDate">Target date</Label>
                <Input id="targetDate" type="date" required className="mt-1.5"
                  value={form.targetDate} onChange={(e) => setForm({ ...form, targetDate: e.target.value })} />
              </div>
              <div>
                <Label htmlFor="obstacles">What usually gets in the way?</Label>
                <Textarea id="obstacles" rows={2} className="mt-1.5"
                  placeholder="Travel weeks, late-night work, bad weather."
                  value={form.obstacles} onChange={(e) => setForm({ ...form, obstacles: e.target.value })} />
                <p className="mt-1 text-xs text-muted-foreground">Used to build if-then plans for your tasks.</p>
              </div>
              <div>
                <Label htmlFor="whyMotivation">Why does this matter to you?</Label>
                <Textarea id="whyMotivation" rows={2} className="mt-1.5"
                  placeholder="I want to prove to myself I can commit to something hard."
                  value={form.whyMotivation} onChange={(e) => setForm({ ...form, whyMotivation: e.target.value })} />
              </div>
              <div>
                <Label htmlFor="whatIfNot">What happens if you don't do it?</Label>
                <Textarea id="whatIfNot" rows={2} className="mt-1.5"
                  placeholder="Another year of half-starting things."
                  value={form.whatIfNot} onChange={(e) => setForm({ ...form, whatIfNot: e.target.value })} />
              </div>
              <Button type="submit" size="lg" disabled={loading} className="w-full gap-2">
                {loading ? <><Loader2 className="h-4 w-4 animate-spin" /> Calibrating…</> : <><Sparkles className="h-4 w-4" /> Calibrate my goal</>}
              </Button>
            </form>
          </>
        )}

        {step === "review" && result && (
          <>
            <h1 className="font-display text-3xl font-semibold sm:text-4xl">Here's your calibrated goal</h1>
            <p className="mt-2 text-muted-foreground">
              {result.calibration.was_recalibrated
                ? "We adjusted it to hard-but-achievable given your baseline."
                : "Your goal is already well-calibrated."}
            </p>

            <Card className="mt-6 overflow-hidden p-0">
              <div className="border-b border-border bg-muted/50 p-5">
                <p className="text-xs font-medium uppercase tracking-wide text-muted-foreground">You asked for</p>
                <p className="mt-1 text-base line-through decoration-muted-foreground/50">{form.title}</p>
                <p className="mt-1 text-sm text-muted-foreground">by {form.targetDate}</p>
              </div>
              <div className="p-5">
                <p className="text-xs font-medium uppercase tracking-wide text-primary">Calibrated target</p>
                <p className="mt-1 font-display text-2xl font-semibold leading-tight">{result.goal.calibrated_target}</p>
                <div className="mt-3 grid gap-3 text-sm sm:grid-cols-2">
                  <div>
                    <p className="text-muted-foreground">Metric</p>
                    <p className="font-medium">{result.goal.calibrated_metric}</p>
                  </div>
                  <div>
                    <p className="text-muted-foreground">Deadline</p>
                    <p className="font-medium">{result.goal.calibrated_deadline}</p>
                  </div>
                  <div>
                    <p className="text-muted-foreground">Difficulty</p>
                    <p className="font-medium capitalize">{result.goal.difficulty_tier.replace("_", " ")}</p>
                  </div>
                  <div>
                    <p className="text-muted-foreground">SMART score</p>
                    <p className="font-medium">{result.calibration.smart_score}/100</p>
                  </div>
                </div>
                <div className="mt-4 rounded-lg bg-accent/50 p-3 text-sm">
                  <p className="font-medium text-accent-foreground">Why this change</p>
                  <p className="mt-1 text-accent-foreground/80">{result.goal.calibration_explanation}</p>
                </div>
              </div>
            </Card>

            <div className="mt-6 flex flex-wrap gap-3">
              <Button size="lg" onClick={handleAccept} disabled={loading} className="gap-2">
                {loading ? <><Loader2 className="h-4 w-4 animate-spin" /> Building your roadmap…</> : <>Accept & build roadmap <ArrowRight className="h-4 w-4" /></>}
              </Button>
              <Button size="lg" variant="outline" onClick={() => setStep("form")} disabled={loading}>
                Edit inputs
              </Button>
            </div>
          </>
        )}

        {step === "breakdown" && (
          <div className="py-20 text-center">
            <Loader2 className="mx-auto h-8 w-8 animate-spin text-primary" />
            <p className="mt-4 font-display text-xl">Building your weekly sprints…</p>
            <p className="mt-1 text-sm text-muted-foreground">Generating tasks and daily habits</p>
          </div>
        )}
      </div>
    </AppShell>
  );
}
```

**src/routes/_authenticated/goals.$id.tsx**
```tsx
import { createFileRoute, Link } from "@tanstack/react-router";
import { useQuery, useQueryClient } from "@tanstack/react-query";
import { supabase } from "@/integrations/supabase/client";
import { AppShell } from "@/components/app-shell";
import { Card } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Checkbox } from "@/components/ui/checkbox";
import { Tabs, TabsList, TabsTrigger, TabsContent } from "@/components/ui/tabs";
import { Flame, ArrowLeft, Snowflake, Sparkles, Calendar as CalIcon, Target } from "lucide-react";
import { calcStreak, toISO } from "@/lib/streak";
import { useEffect, useMemo, useState } from "react";
import { toast } from "sonner";

export const Route = createFileRoute("/_authenticated/goals/$id")({
  component: GoalDetail,
});

function GoalDetail() {
  const { id } = Route.useParams();
  const qc = useQueryClient();
  const [userId, setUserId] = useState<string | null>(null);
  useEffect(() => { supabase.auth.getUser().then(({ data }) => setUserId(data.user?.id ?? null)); }, []);

  const { data, isLoading } = useQuery({
    queryKey: ["goal", id],
    queryFn: async () => {
      const [g, t, a, c, f, p] = await Promise.all([
        supabase.from("goals").select("*").eq("id", id).single(),
        supabase.from("tasks").select("*").eq("goal_id", id).order("week_number").order("sprint_order"),
        supabase.from("daily_actions").select("*").eq("goal_id", id).eq("active", true),
        supabase.from("action_completions").select("*"),
        supabase.from("streak_freezes").select("*").eq("goal_id", id),
        supabase.from("profiles").select("freeze_credits").maybeSingle(),
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

  const invalidate = () => qc.invalidateQueries({ queryKey: ["goal", id] });

  if (isLoading || !data?.goal) return <AppShell><p className="text-muted-foreground">Loading…</p></AppShell>;

  const { goal, tasks, actions, completions, freezes, freezeCredits } = data;
  const actionIds = new Set(actions.map((a) => a.id));
  const goalCompletions = completions.filter((c) => actionIds.has(c.daily_action_id));
  const completedDates = new Set(goalCompletions.map((c) => c.completed_date));
  const freezeDates = new Set(freezes.map((f) => f.freeze_date));
  const streak = calcStreak(completedDates, freezeDates);

  const toggleTask = async (taskId: string, completed: boolean) => {
    await supabase.from("tasks").update({ completed, completed_at: completed ? new Date().toISOString() : null }).eq("id", taskId);
    invalidate();
  };

  const toggleAction = async (actionId: string, date: string, currentlyDone: boolean) => {
    if (currentlyDone) {
      await supabase.from("action_completions").delete().eq("daily_action_id", actionId).eq("completed_date", date);
    } else {
      const { error } = await supabase.from("action_completions").insert({ daily_action_id: actionId, user_id: userId!, completed_date: date });
      if (error) { toast.error(error.message); return; }
      if (date === toISO(new Date())) {
        confetti();
        toast.success("Check-in locked in!", { icon: "🔥" });
      }
    }
    invalidate();
  };

  const applyFreeze = async (date: string) => {
    if (freezeCredits <= 0) { toast.error("No freezes left this month."); return; }
    const { error } = await supabase.from("streak_freezes").insert({ user_id: userId!, goal_id: goal.id, freeze_date: date });
    if (error) { toast.error(error.message); return; }
    await supabase.from("profiles").update({ freeze_credits: freezeCredits - 1 }).eq("id", userId!);
    toast.success("Streak protected", { icon: "❄️" });
    invalidate();
  };

  return (
    <AppShell streakTotal={streak.current}>
      <Link to="/dashboard" className="mb-4 inline-flex items-center gap-1 text-sm text-muted-foreground hover:text-foreground">
        <ArrowLeft className="h-4 w-4" /> Dashboard
      </Link>

      <div className="mb-6 flex flex-wrap items-start justify-between gap-4">
        <div className="min-w-0 flex-1">
          <h1 className="font-display text-3xl font-semibold sm:text-4xl">{goal.calibrated_target || goal.title}</h1>
          <div className="mt-2 flex flex-wrap items-center gap-3 text-sm text-muted-foreground">
            {goal.calibrated_deadline && <span className="inline-flex items-center gap-1"><CalIcon className="h-3.5 w-3.5" /> {goal.calibrated_deadline}</span>}
            {goal.difficulty_tier && <span className="rounded-full bg-accent px-2 py-0.5 text-xs capitalize text-accent-foreground">{goal.difficulty_tier.replace("_", " ")}</span>}
            {goal.calibrated_metric && <span className="inline-flex items-center gap-1"><Target className="h-3.5 w-3.5" /> {goal.calibrated_metric}</span>}
          </div>
        </div>
        <StreakBadge current={streak.current} longest={streak.longest} freezeCredits={freezeCredits} />
      </div>

      {goal.why_motivation && (
        <Card className="mb-6 border-primary/20 bg-primary/5 p-4">
          <p className="text-xs font-medium uppercase tracking-wide text-primary flex items-center gap-1"><Sparkles className="h-3 w-3" /> Why this matters</p>
          <p className="mt-1 text-sm">{goal.why_motivation}</p>
        </Card>
      )}

      <Tabs defaultValue="habits">
        <TabsList className="grid w-full max-w-sm grid-cols-2">
          <TabsTrigger value="habits">Habits</TabsTrigger>
          <TabsTrigger value="roadmap">Roadmap</TabsTrigger>
        </TabsList>

        <TabsContent value="habits" className="mt-6">
          <HabitsGrid actions={actions} completions={goalCompletions} freezes={freezes} onToggle={toggleAction} onFreeze={applyFreeze} freezeCredits={freezeCredits} userId={userId} />
        </TabsContent>

        <TabsContent value="roadmap" className="mt-6">
          <Roadmap tasks={tasks} onToggle={toggleTask} />
        </TabsContent>
      </Tabs>
    </AppShell>
  );
}

function StreakBadge({ current, longest, freezeCredits }: { current: number; longest: number; freezeCredits: number }) {
  return (
    <div className="flex items-center gap-3 rounded-2xl border border-primary/20 bg-gradient-to-br from-primary/10 to-primary/5 px-4 py-3">
      <Flame className={`h-8 w-8 text-primary ${current > 0 ? "animate-flame" : "opacity-40"}`} />
      <div className="text-sm">
        <p className="font-display text-2xl font-bold leading-none">{current}</p>
        <p className="text-xs text-muted-foreground">day streak · best {longest}</p>
        <p className="mt-0.5 flex items-center gap-1 text-xs text-secondary-foreground/70"><Snowflake className="h-3 w-3" /> {freezeCredits} freezes left</p>
      </div>
    </div>
  );
}

type DailyAction = { id: string; title: string; description: string | null };
type Completion = { daily_action_id: string; completed_date: string };
type Freeze = { freeze_date: string };

function HabitsGrid({ actions, completions, freezes, onToggle, onFreeze, freezeCredits, userId }: {
  actions: DailyAction[];
  completions: Completion[];
  freezes: Freeze[];
  onToggle: (id: string, date: string, done: boolean) => void;
  onFreeze: (date: string) => void;
  freezeCredits: number;
  userId: string | null;
}) {
  const days = useMemo(() => {
    const arr: string[] = [];
    const today = new Date();
    for (let i = 29; i >= 0; i--) {
      const d = new Date(today);
      d.setDate(d.getDate() - i);
      arr.push(toISO(d));
    }
    return arr;
  }, []);

  const freezeSet = new Set(freezes.map((f) => f.freeze_date));

  if (actions.length === 0) {
    return <Card className="p-8 text-center text-muted-foreground">No daily habits yet. Rebuild your roadmap to generate them.</Card>;
  }

  const compMap = new Map<string, Set<string>>();
  completions.forEach((c) => {
    if (!compMap.has(c.daily_action_id)) compMap.set(c.daily_action_id, new Set());
    compMap.get(c.daily_action_id)!.add(c.completed_date);
  });

  const today = toISO(new Date());

  return (
    <div className="space-y-6">
      <Card className="p-5">
        <div className="flex items-center justify-between">
          <h3 className="font-display text-lg font-semibold">Today · {today}</h3>
          <Button size="sm" variant="outline" className="gap-1" disabled={freezeCredits <= 0 || freezeSet.has(today)} onClick={() => onFreeze(today)}>
            <Snowflake className="h-3.5 w-3.5" /> Freeze today
          </Button>
        </div>
        <div className="mt-4 space-y-2">
          {actions.map((a) => {
            const done = compMap.get(a.id)?.has(today) ?? false;
            return (
              <label key={a.id} className={`flex cursor-pointer items-start gap-3 rounded-xl border p-3 transition-all ${done ? "border-success/40 bg-success/5" : "border-border hover:bg-accent/30"}`}>
                <Checkbox checked={done} onCheckedChange={() => userId && onToggle(a.id, today, done)} className="mt-0.5" />
                <div className="flex-1">
                  <p className={`font-medium ${done ? "line-through opacity-60" : ""}`}>{a.title}</p>
                  {a.description && <p className="text-sm text-muted-foreground">{a.description}</p>}
                </div>
                {done && <span className="animate-pop text-2xl">🔥</span>}
              </label>
            );
          })}
        </div>
      </Card>

      <Card className="p-5">
        <h3 className="font-display text-lg font-semibold">Last 30 days</h3>
        <div className="mt-4 space-y-3 overflow-x-auto">
          {actions.map((a) => {
            const set = compMap.get(a.id) ?? new Set<string>();
            return (
              <div key={a.id}>
                <p className="mb-1 text-sm font-medium">{a.title}</p>
                <div className="flex gap-1">
                  {days.map((d) => {
                    const done = set.has(d);
                    const froze = freezeSet.has(d);
                    return (
                      <button
                        key={d}
                        type="button"
                        aria-label={d}
                        onClick={() => userId && onToggle(a.id, d, done)}
                        className={`h-6 w-6 rounded-md text-[10px] transition-transform hover:scale-110 ${
                          done ? "bg-primary text-primary-foreground" :
                          froze ? "bg-secondary text-secondary-foreground" :
                          "bg-muted"
                        }`}
                        title={d}
                      >
                        {done ? "✓" : froze ? "❄" : ""}
                      </button>
                    );
                  })}
                </div>
              </div>
            );
          })}
        </div>
        <div className="mt-4 flex items-center gap-4 text-xs text-muted-foreground">
          <span className="flex items-center gap-1"><span className="inline-block h-3 w-3 rounded-sm bg-primary" /> done</span>
          <span className="flex items-center gap-1"><span className="inline-block h-3 w-3 rounded-sm bg-secondary" /> freeze</span>
          <span className="flex items-center gap-1"><span className="inline-block h-3 w-3 rounded-sm bg-muted" /> empty</span>
        </div>
      </Card>
    </div>
  );
}

type Task = { id: string; title: string; description: string | null; week_number: number; completed: boolean; estimated_hours: number | null; if_then_plans: unknown };

function Roadmap({ tasks, onToggle }: { tasks: Task[]; onToggle: (id: string, c: boolean) => void }) {
  if (tasks.length === 0) return <Card className="p-8 text-center text-muted-foreground">No tasks yet.</Card>;
  const byWeek = new Map<number, Task[]>();
  tasks.forEach((t) => {
    if (!byWeek.has(t.week_number)) byWeek.set(t.week_number, []);
    byWeek.get(t.week_number)!.push(t);
  });
  const weeks = Array.from(byWeek.keys()).sort((a, b) => a - b);

  return (
    <div className="space-y-6">
      {weeks.map((w) => {
        const ws = byWeek.get(w)!;
        const done = ws.filter((t) => t.completed).length;
        return (
          <Card key={w} className="p-5">
            <div className="mb-4 flex items-center justify-between">
              <h3 className="font-display text-xl font-semibold">Week {w}</h3>
              <span className="text-sm text-muted-foreground">{done}/{ws.length} done</span>
            </div>
            <div className="space-y-2">
              {ws.map((t) => {
                const plans = Array.isArray(t.if_then_plans) ? t.if_then_plans as Array<{ trigger: string; response: string }> : [];
                return (
                  <div key={t.id} className={`rounded-xl border p-3 transition-all ${t.completed ? "border-success/30 bg-success/5" : "border-border"}`}>
                    <label className="flex cursor-pointer items-start gap-3">
                      <Checkbox checked={t.completed} onCheckedChange={(v) => onToggle(t.id, !!v)} className="mt-1" />
                      <div className="flex-1">
                        <div className="flex items-start justify-between gap-2">
                          <p className={`font-medium ${t.completed ? "line-through opacity-60" : ""}`}>{t.title}</p>
                          {t.estimated_hours && <span className="shrink-0 rounded-full bg-muted px-2 py-0.5 text-xs text-muted-foreground">{t.estimated_hours}h</span>}
                        </div>
                        {t.description && <p className="mt-1 text-sm text-muted-foreground">{t.description}</p>}
                        {plans.length > 0 && (
                          <div className="mt-2 space-y-1">
                            {plans.map((p, i) => (
                              <p key={i} className="text-xs text-secondary-foreground/80"><span className="font-semibold">If</span> {p.trigger} <span className="font-semibold">then</span> {p.response}</p>
                            ))}
                          </div>
                        )}
                      </div>
                    </label>
                  </div>
                );
              })}
            </div>
          </Card>
        );
      })}
    </div>
  );
}

function confetti() {
  const colors = ["#ff8a3d", "#ffb44a", "#4ade80", "#60a5fa", "#c084fc"];
  const container = document.createElement("div");
  container.style.cssText = "position:fixed;inset:0;pointer-events:none;z-index:9999";
  for (let i = 0; i < 30; i++) {
    const p = document.createElement("div");
    p.style.cssText = `position:absolute;top:40%;left:${45 + Math.random() * 10}%;width:8px;height:8px;background:${colors[i % colors.length]};border-radius:2px;animation:confetti-fall ${0.8 + Math.random() * 0.8}s ease-out forwards;transform:translateX(${(Math.random() - 0.5) * 200}px)`;
    container.appendChild(p);
  }
  document.body.appendChild(container);
  setTimeout(() => container.remove(), 2000);
}
```

## src/styles.css

```css
@import "tailwindcss" source(none);
@source "../src";
@import "tw-animate-css";

@custom-variant dark (&:is(.dark *));

@theme inline {
  --font-display: "Fraunces", Georgia, serif;
  --font-sans: "Manrope", ui-sans-serif, system-ui, sans-serif;

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
}

@layer base {
  * {
    border-color: var(--color-border);
  }
  html, body {
    font-family: var(--font-sans);
    font-feature-settings: "cv02", "cv03", "cv04", "cv11";
  }
  body {
    background-color: var(--color-background);
    color: var(--color-foreground);
    -webkit-font-smoothing: antialiased;
  }
  h1, h2, h3, h4, .font-display {
    font-family: var(--font-display);
    font-optical-sizing: auto;
    font-variation-settings: "SOFT" 50, "WONK" 0;
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
```

## supabase/migrations/

**20260708110954_3ddd6732-7a30-40d6-9836-5f73d73835c4.sql**
```sql
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
CREATE POLICY "profiles self" ON public.profiles FOR ALL USING (auth.uid() = id) WITH CHECK (auth.uid() = id);

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
  calibration_status TEXT NOT NULL DEFAULT 'raw',
  why_motivation TEXT,
  what_if_not TEXT,
  obstacles TEXT,
  status TEXT NOT NULL DEFAULT 'active',
  created_at TIMESTAMPTZ NOT NULL DEFAULT now(),
  updated_at TIMESTAMPTZ NOT NULL DEFAULT now()
);
GRANT SELECT, INSERT, UPDATE, DELETE ON public.goals TO authenticated;
GRANT ALL ON public.goals TO service_role;
ALTER TABLE public.goals ENABLE ROW LEVEL SECURITY;
CREATE POLICY "goals owner" ON public.goals FOR ALL USING (auth.uid() = user_id) WITH CHECK (auth.uid() = user_id);

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
  if_then_plans JSONB DEFAULT '[]'::jsonb,
  completed BOOLEAN NOT NULL DEFAULT false,
  completed_at TIMESTAMPTZ,
  created_at TIMESTAMPTZ NOT NULL DEFAULT now()
);
GRANT SELECT, INSERT, UPDATE, DELETE ON public.tasks TO authenticated;
GRANT ALL ON public.tasks TO service_role;
ALTER TABLE public.tasks ENABLE ROW LEVEL SECURITY;
CREATE POLICY "tasks owner" ON public.tasks FOR ALL USING (auth.uid() = user_id) WITH CHECK (auth.uid() = user_id);
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
CREATE POLICY "da owner" ON public.daily_actions FOR ALL USING (auth.uid() = user_id) WITH CHECK (auth.uid() = user_id);

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
CREATE POLICY "ac owner" ON public.action_completions FOR ALL USING (auth.uid() = user_id) WITH CHECK (auth.uid() = user_id);
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
CREATE POLICY "sf owner" ON public.streak_freezes FOR ALL USING (auth.uid() = user_id) WITH CHECK (auth.uid() = user_id);

-- profile auto-create trigger
CREATE OR REPLACE FUNCTION public.handle_new_user()
RETURNS TRIGGER
LANGUAGE plpgsql
SECURITY DEFINER SET search_path = public
AS $$
BEGIN
  INSERT INTO public.profiles (id, display_name)
  VALUES (NEW.id, COALESCE(NEW.raw_user_meta_data->>'name', NEW.raw_user_meta_data->>'full_name', split_part(NEW.email, '@', 1)))
  ON CONFLICT (id) DO NOTHING;
  RETURN NEW;
END;
$$;

CREATE TRIGGER on_auth_user_created
  AFTER INSERT ON auth.users
  FOR EACH ROW EXECUTE FUNCTION public.handle_new_user();
```

**20260708111029_30bcabec-6f38-4948-97a4-ddc34dd7d238.sql**
```sql
REVOKE EXECUTE ON FUNCTION public.handle_new_user() FROM PUBLIC, anon, authenticated;
```

Das ZIP von vorhin (`momentum-mastered.zip`) enthält all das bereits als fertige Dateien inkl. der 40 shadcn-Komponenten — falls copy-paste doch zu mühsam wird für 89 Dateien.
