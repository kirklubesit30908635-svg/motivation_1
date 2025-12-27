git checkout -B fix/vercel-layout
git apply --3way <<'EOF'
diff --git a/vercel.json b/vercel.json
new file mode 100644
index 0000000..8d6a4c1
--- /dev/null
+++ b/vercel.json
@@ -0,0 +1,8 @@
+{
+  "framework": "nextjs",
+  "installCommand": "npm install",
+  "buildCommand": "npm run build",
+  "devCommand": "npm run dev"
+}
diff --git a/next-env.d.ts b/next-env.d.ts
new file mode 100644
index 0000000..d2dff1a
--- /dev/null
+++ b/next-env.d.ts
@@ -0,0 +1,5 @@
+/// <reference types="next" />
+/// <reference types="next/image-types/global" />
+// NOTE: This file should not be edited
+// See https://nextjs.org/docs/basic-features/typescript for more information.
diff --git a/tsconfig.json b/tsconfig.json
new file mode 100644
index 0000000..8a51b6f
--- /dev/null
+++ b/tsconfig.json
@@ -0,0 +1,27 @@
+{
+  "compilerOptions": {
+    "target": "ES2022",
+    "lib": ["dom", "dom.iterable", "esnext"],
+    "allowJs": false,
+    "skipLibCheck": true,
+    "strict": true,
+    "noEmit": true,
+    "esModuleInterop": true,
+    "module": "esnext",
+    "moduleResolution": "bundler",
+    "resolveJsonModule": true,
+    "isolatedModules": true,
+    "jsx": "preserve",
+    "incremental": true,
+    "types": ["node"]
+  },
+  "include": ["next-env.d.ts", "**/*.ts", "**/*.tsx"],
+  "exclude": ["node_modules"]
+}
diff --git a/.gitignore b/.gitignore
new file mode 100644
index 0000000..c9e7756
--- /dev/null
+++ b/.gitignore
@@ -0,0 +1,27 @@
+node_modules
+.next
+out
+dist
+.DS_Store
+*.log
+npm-debug.log*
+yarn-debug.log*
+yarn-error.log*
+pnpm-debug.log*
+.env
+.env.local
+.env.development.local
+.env.test.local
+.env.production.local
+.vercel
diff --git a/app/layout.tsx b/app/layout.tsx
new file mode 100644
index 0000000..bbf0d0d
--- /dev/null
+++ b/app/layout.tsx
@@ -0,0 +1,15 @@
+export default function RootLayout({
+  children,
+}: {
+  children: React.ReactNode;
+}) {
+  return (
+    <html lang="en">
+      <body style={{ margin: 0, fontFamily: "system-ui, Arial, sans-serif" }}>
+        {children}
+      </body>
+    </html>
+  );
+}
diff --git a/app/page.tsx b/app/page.tsx
new file mode 100644
index 0000000..c0e79a9
--- /dev/null
+++ b/app/page.tsx
@@ -0,0 +1,28 @@
+export default function Home() {
+  return (
+    <main style={{ padding: 24 }}>
+      <h1 style={{ fontSize: 28, margin: "0 0 10px" }}>motivation_1</h1>
+      <p style={{ margin: "0 0 18px", maxWidth: 720 }}>
+        Deployed on Vercel with a clean Next.js + TypeScript layout. This page exists
+        to prove the pipeline is stable. Replace this with your real UI after the
+        deploy goes green.
+      </p>
+      <div
+        style={{
+          padding: 16,
+          border: "1px solid rgba(255,255,255,0.15)",
+          borderRadius: 12,
+          maxWidth: 720,
+        }}
+      >
+        <strong>Next step:</strong> keep this repo UI-only, and build your motivation
+        interface on top of this baseline.
+      </div>
+    </main>
+  );
+}
diff --git a/package.json b/package.json
index 0000000..2d3e7a1
--- /dev/null
+++ b/package.json
@@ -0,0 +1,23 @@
+{
+  "name": "motivation_1",
+  "private": true,
+  "scripts": {
+    "dev": "next dev",
+    "build": "next build",
+    "start": "next start",
+    "lint": "next lint"
+  },
+  "dependencies": {
+    "next": "14.1.0",
+    "react": "18.2.0",
+    "react-dom": "18.2.0"
+  },
+  "devDependencies": {
+    "typescript": "^5.3.3",
+    "@types/node": "^20.11.0",
+    "@types/react": "^18.2.0",
+    "@types/react-dom": "^18.2.0"
+  },
+  "engines": { "node": "20.x" }
+}
EOF
