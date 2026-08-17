# claude-plugin

Bu — [Claude Code](https://claude.com/claude-code) uchun shaxsiy skill (ko'nikma) to'plamim. Har bir papka alohida skill: Claude'ga qandaydir vaziyatda qanday ishlashini o'rgatadigan qisqa qoida.

Bu **test/tajriba loyiha** — o'zim uchun yozib borayotgan kichik qoidalar to'plami, xolos. Agar buni o'zingizga qanday moslashtirish yoki yaxshiroq qilish kerakligini bilsangiz, bemalol fork qilib, o'zingizga moslab tuzatib oling.

Bu repo (va undagi kod/skilllar) ko'p qismi **Claude AI chatbot'ining o'zi tomonidan** yozilgan — men vazifani tasvirlab berganman, qolganini Claude yozgan. Shu sababli kod/qoidalar unchalik mukammal bo'lmasligi, ba'zi joylarda soddaroq yoki takomillashtirish kerak bo'lishi mumkin.

## Skilllar

- **`no-unsolicited-work/`** — Claude so'ralmagan ishni o'z-o'zidan taklif qilib/davom ettirib yubormasligi uchun. Faqat aniq so'ralgan narsani bajaradi, natijani aytadi va to'xtaydi.
- **`model-tiering/`** — Katta vazifani bir nechta subagent'larga bo'lib bajarilganda (masalan: reja → amalga oshirish → tekshirish), har bir bosqichga qaysi model darajasini (kuchli/arzon) tayinlash kerakligini belgilaydi — narxni tejash uchun.
- **`uzbek-language/`** — Foydalanuvchi o'zbekcha yozsa yoki shunday so'ragan bo'lsa, Claude javoblarni standart tarzda o'zbek tilida yozadi (kod va texnik atamalar bundan mustasno).

## O'rnatish

Bu skilllar `.claude-plugin/marketplace.json` shaklida rasmiylashtirilmagan (hozircha), shuning uchun `claude plugin marketplace add` ishlamaydi. Buning o'rniga kerakli skill papkasini `~/.claude/skills/` ichiga nusxalang — Claude Code uni keyingi sessiyada `<nomi>@skills-dir` sifatida avtomatik yuklaydi:

```bash
git clone git@github.com:Saidqodirxon/claude-plugin.git
mkdir -p ~/.claude/skills
cp -r claude-plugin/uzbek-language ~/.claude/skills/
cp -r claude-plugin/no-unsolicited-work ~/.claude/skills/
cp -r claude-plugin/model-tiering ~/.claude/skills/
```

## Bog'lanish

- Telegram: [@saidqodirxonuz](https://t.me/saidqodirxonuz)
- Moliyaviy qo'llab-quvvatlash (donate): [saadahbooks.uz/donate](https://saadahbooks.uz/donate)
