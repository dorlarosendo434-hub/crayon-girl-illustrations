# 专属 IP 初始化与更换

## 目标

把用户提供的照片、头像、卡通或其他画风形象，建立为本 Skill 的活动 IP。最终形象要同时满足两件事：看得出是用户的形象，看得出属于内置蜡笔女孩的视觉世界。

## 引导话术

首次使用且未找到活动 IP 时，直接说明：

> 在开始配图前，我会先帮你把这套 Skill 换成自己的 IP。请上传 1-3 张参考图，正面、能看清脸、发型和标志性穿搭的全身图最好。真人照、头像、卡通或其他画风都可以；如果画风不一致，我会自动转绘成这套温暖的两头身蜡笔风。

不要一次追问多个设定。用户的图像已经足够清楚时，直接提取特征并继续。只有相互冲突的多张图无法判断以哪张为准时，才请用户指定主参考。

## 风格判断

先检查用户形象是否已经满足以下条件：

- 严格两头身，头部约占总高一半。
- 紧凑躯干、短圆肢体，是成年 IP 气质，不婴儿化。
- 温暖的彩色蜡笔纸面质感，有可见手绘颗粒。
- 轮廓柔和清楚，颜色克制，整体清透、有大量浅色留白。
- 不是真人照片、3D 玩偶、日漫厚涂、纯矢量或儿童绘本风。

任意一项明显不符，就使用内置 ImageGen 自动转绘，不要把风格选择题丢回给用户。如果原图已经同风格且形象清晰，可直接设为活动 IP；只有画幅不利于稳定复用时才做轻量规范化。

## 身份与风格必须分开

从用户图中提取并保留：

- 脸型、眼睛特征、发型、发色和肤色。
- 性别表达、年龄气质和整体神态。
- 标志性服装的款式、主色和图案。
- 眼镜、帽子、耳饰、首饰、包类等真正存在的识别特征。
- 其他足以让用户一眼认出的 3-7 个锚点。

从内置 `assets/ip-reference/05-canonical-beret-plump-limbs.png` 只迁移：

- 严格两头身比例、大头大脸、紧凑躯干和短圆胖乎四肢。
- 温暖彩色蜡笔手绘、纸面颗粒、柔和深蓝或深色轮廓。
- 清透、克制、可靠、轻盈但不幼稚的整体气质。

不得从内置女孩迁移她的脸、黑长发、棕色贝雷帽、珍珠耳钉、奶油上衣、格纹短裙、斜挎包或鞋。只有它们本来就是用户形象的特征时才可保留。

## 自动转绘

生成一张干净、独立、方便后续引用的标准形象：浅奶油或白色纸面背景，单个角色，正面或轻微侧身全身站姿，双手和双脚完整可见，无文字、无场景物件、无多角度拼图。

转绘提示词必须明确写出：

```text
Treat the user's supplied image as the only identity source. Preserve the subject's recognizable face, hairstyle, hair color, skin tone, gender presentation, signature outfit colors and real accessories. Transfer only the visual language from the built-in crayon reference: strict two-head-tall proportions, enlarged head and face, compact torso, short rounded plump limbs, warm colored-crayon texture, visible paper grain, soft dark-blue outlines, restrained colors and a capable adult personality. Do not inherit the built-in girl's face, black long hair, brown beret, pearl earrings, cream blouse, plaid skirt, crossbody pouch or shoes unless the user's source already contains that exact feature. One clean full-body character on a pale cream paper background, front or slight three-quarter standing pose, both hands and both feet visible, no text, no props, no scene and no multi-view sheet.
```

如果用户图和内置风格图都能以本地路径作为参考传入，同时传入两者并在提示词中声明它们的不同职责。如果工具不能同时传入，优先传入用户图保住身份，并用上述文字锁定内置风格。

## 验收与保存

1. 对照用户原图检查脸、发型、发色、服装主色和配饰，必须一眼可识别。
2. 对照内置 05 参考图检查两头身、肢体、蜡笔颗粒和成年气质。
3. 如果变成内置女孩、丢失用户的关键特征或画风仍不一致，立即修正或重生成，不得设为活动 IP。
4. 验收通过后保存为 `assets/ip-reference/user/active-ip.png`。必要时先创建 `assets/ip-reference/user/`。
5. 创建或更新 `references/user-ip-profile.md`，只记录可见的视觉事实，使用以下结构：

上述两个用户文件已在 `.gitignore` 中排除。不得把用户照片、转绘结果或身份档案加入这套 Skill 的公开仓库，除非用户明确要求发布。

```markdown
# 当前用户 IP

- 活动参考：`assets/ip-reference/user/active-ip.png`
- 脸部与气质：
- 发型与发色：
- 服装与固定色：
- 标志性配饰：
- 其他识别锚点：
- 生成时不得混入的内置女孩特征：
```

初始化完成后，给用户看标准形象，简短说明已保存为默认 IP，然后继续原本的配图任务。
