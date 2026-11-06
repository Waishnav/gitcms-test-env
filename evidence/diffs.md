# Draft diffs (task #40, branch gitcms-draft-40), each between consecutive saves

## Scenario 1b
```diff
@@ -6,7 +6,7 @@ import { Tabs, TabItem, Steps, Card, CardGrid, LinkCard, Aside, Badge, FileTree
 
 <Steps>
 
-1. First step with **emphasis**.
+1. First step with **emphasis**. done
    ```bash
    npm install
    ```
```

## Scenario 1c
```diff
@@ -8,7 +8,7 @@ import { Tabs, TabItem, Steps, Card, CardGrid, LinkCard, Aside, Badge, FileTree
 
 1. First step with **emphasis**. done
    ```bash
-   npm install
+   npm install -g
    ```
 2. Second step.
    ```bash
```

## Scenario 1d
```diff
@@ -16,6 +16,7 @@ import { Tabs, TabItem, Steps, Card, CardGrid, LinkCard, Aside, Badge, FileTree
    ```
 3. Third step.
 4. Fourth step.
+5. Fifth step.
 
 </Steps>
 
```

## Scenario 1e
```diff
@@ -14,9 +14,10 @@ import { Tabs, TabItem, Steps, Card, CardGrid, LinkCard, Aside, Badge, FileTree
    ```bash
    npm run build
    ```
-3. Third step.
-4. Fourth step.
-5. Fifth step.
+3. Third
+4. &#x20;step.
+5. Fourth step.
+6. Fifth step.
 
 </Steps>
 
```

## Scenario 4
```diff
@@ -4,12 +4,12 @@ title: QA asides and tabs
 
 import { Tabs, TabItem, Steps, Card, CardGrid, LinkCard, Aside, Badge, FileTree } from '@astrojs/starlight/components'
 
-<Aside type="note" title="A note v2">
+<Aside type="note" title="A note v23">
   **Rich** body and a [link](https://example.com).
 </Aside>
 
 <Tabs syncKey="language">
-  <TabItem label="JavaScript" icon="star">JavaScript text.</TabItem>
+  <TabItem label="JavaScriptX" icon="star">JavaScript text.</TabItem>
   <TabItem label="TypeScript">TypeScript text. ok</TabItem>
 </Tabs>
 
```

## Scenario 1a (task #41, branch gitcms-draft-41)
Save refused in the editor; no commit was created (branch head unchanged).

## Scenario 1f
Save refused; no commit was created.
