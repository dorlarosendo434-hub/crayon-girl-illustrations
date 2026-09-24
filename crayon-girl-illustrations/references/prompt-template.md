# 生图提示词模板

每张图单独生成。根据正文内容替换变量，不要把多张图拼在一起。

```text
Generate one standalone Chinese content illustration in the selected aspect ratio.

Canvas mode:
{默认横图：strict 16:9 horizontal canvas for article body illustration / 竖图：strict 3:4 portrait canvas for Xiaohongshu or Xiaolushu}

Content role:
{正文/轮播内页：quiet title-safe area, sparse annotations / 封面：large readable Chinese title + one short content summary + girl directly interacting with title or main object}

Visual DNA:
Warm crayon-style hand-drawn illustration. Use the selected palette's required pale background with subtle crayon grain. The pale background and calm empty space cover at least 70% of the canvas. Clean, airy, restrained color, sparse short handwritten Chinese annotations. Not commercial vector art, PPT infographic, children's book, 3D, realistic photo, or dense explainer.

Active recurring IP character required:
Match assets/ip-reference/user/active-ip.png as the highest-priority identity reference. Preserve every identity anchor recorded in references/user-ip-profile.md: {paste the active face, expression, hairstyle, hair color, skin tone, signature outfit colors, footwear, real accessories and other recognition anchors here}. Do not add the built-in girl's black long hair, brown beret, pearl earrings, cream blouse, plaid skirt, crossbody pouch or shoes unless the active profile explicitly contains that feature.

Transfer only the visual language from assets/ip-reference/05-canonical-beret-plump-limbs.png: strict two-head-tall proportions, with total height approximately two head-heights; enlarged head and face occupy about half the total height; compact body from chin to shoe soles occupies about one head-height. Use short, rounded, visibly plump limbs: gently thick upper arms and forearms, rounded elbows, small chubby hands, short rounded thighs and calves, soft knees and compact chunky ankles. Adapt the active IP's real outfit and accessories to this compact body without replacing, recoloring or inventing identity features. Keep a thoughtful, capable adult personality, not infant-like. The active IP must perform the core conceptual action, not decorate the scene.

Theme:
{正文配图主题}

Structure type:
{Workflow / 系统局部 / 前后对比 / 角色状态 / 概念隐喻 / 方法分层 / 地图路线 / 小漫画分镜}

Core idea:
{核心意思}

Composition:
{女孩在哪里、正在做什么、主要物件、信息如何流动}

Portrait-only layout rule:
For a 3:4 body or carousel page, reserve the top 15% as calm empty space for a future platform title; place one main object or state in the middle and the girl performing the key action in the lower half. Create one clear top-to-bottom reading path. Do not compress a wide left-to-right workflow, two-column comparison, or long horizontal route into the portrait canvas.

Cover-only layout rule:
For a cover, do not leave an empty title-safe area. Put the exact large Chinese main title "{封面主标题，8-16字，最多两行}" in the upper half as the first visual layer. Put the exact short summary "{封面内容总结，12-24字}" below or beside it as the third visual layer. Make the girl directly hold, pull, stamp, circle, deliver, or emerge from the title or main object. The girl and the core object form the second visual layer. Keep the cover to one judgement, not a dense explainer.

Suggested elements:
{元素1} / {元素2} / {元素3} / {元素4}

Chinese handwritten labels:
{标注词1} / {标注词2} / {标注词3} / {标注词4} / {可选标注词5}

Palette:
{经典绿 / 薰衣草 / 安全蓝 / 人民红 / 文艺琥珀 / 午夜档案；从 references/palette-system.md 复制该方案的浅底、主色、辅助色、浅块和深墨}

Color use:
Use the selected palette's pale background across the full canvas. Apply its main and supporting colors to scene objects, paths, paper notes and annotations. Limit dark colors to outlines, short text and small accents; no dark full-width header or large dark block. Keep the active IP's recorded hair color, outfit colors and signature accessories unchanged across palettes.

Constraints:
One image explains one core structure. Keep the main subject around 40%-60% of the canvas, at least 30% calm empty space, and at least 70% pale background or quiet light area. No dark full-canvas background, large dark rectangle, strong gradient or heavy shadow. For a 3:4 body or carousel page, use only 3-6 short labels and preserve the top 15% as empty space with no title or critical visual. For a cover, prioritize the exact main title and summary over extra labels; do not add a generic top-left type label. Maintain the exact active identity in every pose: no changed face, eye features, hairstyle, hair color, outfit palette, footwear or signature accessories; no invented built-in-girl features; no 2.5-head, 3-head, long torso, long legs, thin stick limbs or realistic adult anatomy. No formal diagram, course slide, commercial poster, copied reference composition, or watermark.
```

## 新手解释型配图补充模板

当任务是解释“是什么、如何工作、包含什么、能否复用或修改”时，在基础模板中追加：

```text
Beginner explainer requirement:
Do not represent the answer as several isolated icons. Build one coherent physical story around a single main object.

Show these layers when relevant:
1. Definition: what the concept is, represented by one clear main object.
2. Contents: reveal 3-5 essential internal parts.
3. Operation: show one readable input -> processing -> output path.
4. Capabilities: show reuse, modification, checking, or customization through physical actions.

Use concrete noun-and-verb labels rather than vague benefit words. A beginner should be able to explain what it is and how it works after viewing the image. For this mode, 8-11 short labels are allowed if they follow one clear reading path. Keep it a warm crayon scene, not a PPT grid or formal flowchart.
```

## 一致性修正提示

```text
Edit or regenerate this illustration to match the active user IP in assets/ip-reference/user/active-ip.png and every identity anchor in references/user-ip-profile.md. Preserve the scene and core meaning, but correct all identity drift: restore the active face, eye features, hairstyle, hair color, skin tone, signature outfit colors, footwear and real accessories; remove any feature borrowed from the built-in girl that is not present in the active profile. Restore strict two-head-tall proportions, an enlarged head and face, compact torso, and short rounded plump arms, legs, hands and ankles. Preserve the warm colored-crayon texture, visible paper grain and capable adult personality. Do not replace the user's identity with the built-in reference.
```


