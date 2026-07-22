# 🎨 ชุดเครื่องมือแต่ง GitHub Profile ให้สวย

> วิธีใช้: แทนที่ `YOUR_USERNAME` ด้วยชื่อ GitHub ของคุณทุกที่ แล้วก๊อปโค้ดที่ชอบไปวางใน README.md
> เปลี่ยนธีมได้ที่คำว่า `theme=` เช่น `radical`, `dracula`, `tokyonight`, `merko`, `gruvbox`, `catppuccin_mocha`

---

## 1️⃣ ตัวสร้างแบบลากวาง (ไม่ต้องเขียนโค้ด)

| เครื่องมือ | ลิงก์ | ใช้ทำอะไร |
|---|---|---|
| GitHub Profile README Generator | https://rahuldkjain.github.io/gh-profile-readme-generator/ | กรอกข้อมูลแล้วได้ markdown ทันที ตัวยอดนิยม |
| readme.so | https://readme.so | เอดิเตอร์ลากวาง ทำได้ทั้งโปรไฟล์และโปรเจกต์ |
| Profile Readme Generator | https://profile-readme-generator.com | UI สวย มีพรีวิวสด |

---

## 2️⃣ หัวแบนเนอร์ (Header / Banner)

**Capsule Render** — หัวคลื่นสวยๆ 👉 https://github.com/kyechan99/capsule-render
```markdown
![header](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=200&section=header&text=YOUR%20NAME&fontSize=70&fontColor=ffffff)
```
> เปลี่ยน `type=` ได้: `waving`, `wave`, `egg`, `shark`, `slice`, `rect`, `cylinder`, `soft`

**Typing SVG** — ตัวอักษรพิมพ์วิ่ง 👉 https://github.com/DenverCoder1/readme-typing-svg
```markdown
![Typing](https://readme-typing-svg.demolab.com?font=Fira+Code&size=28&duration=3000&color=6C63FF&center=true&width=500&lines=Hello+World!;Full-Stack+Developer)
```

---

## 3️⃣ การ์ดสถิติ (Stats Cards)

**GitHub Readme Stats** — ตัวที่คนใช้เยอะสุด 👉 https://github.com/anuraghazra/github-readme-stats
```markdown
![Stats](https://github-readme-stats.vercel.app/api?username=YOUR_USERNAME&show_icons=true&theme=tokyonight&count_private=true)
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_USERNAME&layout=compact&theme=tokyonight)
```

**Streak Stats** — วัน commit ต่อเนื่อง 👉 https://github.com/DenverCoder1/github-readme-streak-stats
```markdown
![Streak](https://streak-stats.demolab.com?user=YOUR_USERNAME&theme=tokyonight)
```

**Profile Summary Cards** — การ์ดสรุปหลายใบ 👉 https://github.com/vn7n24fzkq/github-profile-summary-cards
```markdown
![Summary](https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=YOUR_USERNAME&theme=tokyonight)
```

**Metrics** — infographic ละเอียดสุด (ต้องตั้ง GitHub Action) 👉 https://github.com/lowlighter/metrics

**Trophy** — ถ้วยรางวัล 👉 https://github.com/ryo-ma/github-profile-trophy
```markdown
![Trophy](https://github-profile-trophy.vercel.app/?username=YOUR_USERNAME&theme=tokyonight&no-frame=true&column=7)
```

---

## 4️⃣ ไอคอนและ Badge

**Skill Icons** — ไอคอน tech stack 👉 https://skillicons.dev
```markdown
![Skills](https://skillicons.dev/icons?i=js,ts,react,nodejs,python,git,docker,figma)
```

**Shields.io** — badge สีๆ 👉 https://shields.io
```markdown
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/YOUR_PROFILE)
```

**Simple Icons** — คลังไอคอน SVG ฟรีกว่า 3,000 อัน 👉 https://simpleicons.org

**ตัวนับผู้เข้าชม**
```markdown
![views](https://komarev.com/ghpvc/?username=YOUR_USERNAME&color=6c63ff)
```

---

## 5️⃣ 🐍 งูกิน Contribution Graph (อันฮิต)

ตัวนี้ต้องตั้ง GitHub Action เพราะรูปต้อง generate ใหม่ทุกวัน 👉 https://github.com/Platane/snk

**ขั้นตอน:**
1. สร้างไฟล์ `.github/workflows/snake.yml` ใน repo โปรไฟล์
2. วางโค้ดด้านล่าง
3. รอ Action รันเสร็จ แล้วเอา URL รูปไปวางใน README

```yaml
name: Generate Snake
on:
  schedule:
    - cron: "0 */24 * * *"
  workflow_dispatch:
jobs:
  generate:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/snake.svg
            dist/snake-dark.svg?palette=github-dark
      - uses: crazy-max/ghaction-github-pages@v4
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

จากนั้นวางใน README:
```markdown
![snake](https://raw.githubusercontent.com/YOUR_USERNAME/YOUR_USERNAME/output/snake.svg)
```

---

## 6️⃣ 📚 รายการรวมของสวย (ดูตัวอย่าง / หาไอเดีย)

| รายการ | ลิงก์ |
|---|---|
| Awesome GitHub Profile README | https://github.com/abhisheknaiidu/awesome-github-profile-readme |
| Awesome Readme Tools | https://github.com/dhyeythumar/awesome-readme-tools |

---

_เคล็ดลับ: ใช้ธีมสีเดียวกันทั้งหน้า (เช่น tokyonight ทุกอัน) จะทำให้โปรไฟล์ดูเป็นเอกภาพและมืออาชีพขึ้นมาก_
