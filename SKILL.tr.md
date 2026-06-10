---
name: frontend-design-power-skill
description: >
  Master frontend design skill. 109 ui-skills.com skill'inden süzülen,
  8 tam SKILL.md analiziyle zenginleştirilmiş kapsamlı frontend tasarım
  disiplini. Anti-generic design, 3-dial sistemi, tipografi, OKLCH renk,
  Double-Bezel mimarisi, spring motion, WCAG erişilebilirlik, render
  pipeline performans, ve 30+ benzersiz kural.
---

# Frontend Design Power Skill

Bu skill, ui-skills.com'daki 109 skill'in tamamının taranması ve en kritik
8 skill'in (baseline-ui, impeccable, make-interfaces-feel-better,
fixing-accessibility, fixing-motion-performance, taste-skill, soft-skill,
emil-design-eng, brutalist-skill) GitHub reposundan birebir okunmasıyla
oluşturulmuştur.

---

## 0. META: Asla AI Default'larına Düşme

AI'ın varsayılan estetiği bellidir: Inter font, purple-to-blue gradient,
rounded-lg card'lar, 1rem padding, centered hero, üç eşit feature card,
her section'da tiny uppercase eyebrow, 01/02/03 numaralı marker'lar.

**Her tasarım kararının bir nedeni olmalı.** "Default bu" diye bir şey yok.

### 0.1 Varyans Zorunluluğu (Variance Mandate)

> **Aynı tasarımı iki kez üretme.** Farklı projelerde, farklı kullanıcılarda,
> farklı isteklerde — her seferinde FARKLI bir styl, FARKLI bir layout,
> FARKLI bir renk paleti seç. Section 17'deki 30 temadan her proje için
> BAŞKA birini seç. Arka arkaya aynı temayı kullanma.

Bu kuralı ihlal eden davranışlar:
- B2B görünce otomatik Clean SaaS'a atlamak
- "Modern" görünce hep Swiss Modern seçmek
- Landing page görünce hep centered hero + 3 card yapmak

**Doğrusu:** Her projede 17.10 tablosundan EN AZ 2-3 aday stil seç,
bunlardan projeye EN UYGUN ama bir öncekinden FARKLI olanı kullan.

### 0.2 Sayfa Mimarisi Varyasyonu (Anti-Şablon Kuralı)

> **Aynı sayfa iskeletini iki kez kullanma.** AI'ın varsayılan landing page
> şablonu bellidir: Nav → Centered Hero → 3'lü Card Grid → "Why Us" →
> CTA → Footer. Bu iskeleti her gördüğünde REDDET ve farklı bir mimari seç.

**Zorunlu varyasyon alanları (her projede en az 3'ünü değiştir):**

#### Hero Varyasyonları (her projede farklı seç)
| Tip | Açıklama |
|-----|----------|
| A. **Centered text** | Klasik ortalanmış başlık + CTA |
| B. **Split** | Sol text + sağ görsel/ürün |
| C. **Full-bleed image** | Tam ekran görsel, text overlay |
| D. **Type-only** | Sadece tipografi, görsel yok |
| E. **Immediate product** | Hero yok, direkt ürün grid'iyle başla |
| F. **Video/animasyon bg** | Hareketli arka plan |
| G. **Masonry/Bento hero** | Kart grid'i hero olarak |

#### Navigasyon Varyasyonları
| Tip | Açıklama |
|-----|----------|
| 1. **Top fixed** | Üstte sabit bar |
| 2. **Floating pill** | Ortada floating capsule nav |
| 3. **Sidebar** | Sol/sağ dikey navigasyon |
| 4. **Bottom** | Mobil tarzı alt navigasyon |
| 5. **Hamburger-only** | Sadece menü ikonu, temiz sayfa |
| 6. **None** | Navigasyon yok, single page |

#### Section Sıralaması (her projede shuffle et)
İçerik aynı kalsa bile section'ların SIRASINI değiştir:
- Features üstte, hero altta olabilir
- CTA ortada, testimonial en üstte olabilir
- Footer'a yakın bir yerde yeni bir mini-hero olabilir

#### İçerik Yoğunluğu (her projede farklı)
| Yoğunluk | Karakteristik |
|----------|--------------|
| **Airy** | Az section (3-4), bol whitespace, her section tam ekran |
| **Dense** | Çok section (7+), kompakt, hızlı scroll |
| **Hybrid** | 1 Airy hero + dense içerik |

**Her projede şu kararları açıkça belirt:**
```
[ ] Hero tipi: A / B / C / D / E / F / G (bu ürün tipi için en bariz olanı SEÇME)
[ ] Nav tipi: 1 / 2 / 3 / 4 / 5 / 6 (bu ürün tipi için en bariz olanı SEÇME)
[ ] Section sırası: [sıralamayı yaz]
[ ] Yoğunluk: Airy / Dense / Hybrid
[ ] Stil: 17.10 tablosundan bu ürün tipine uyan 2-3 aday çıkar, EN BARİZ olanı DEĞİL yanındakini seç
```
> **"En bariz" ne demek?** SaaS → Clean SaaS, oyun → Deep Tech, portfolyo → Editorial Minimal. Bunları gördüğün an ATLA, yanındakini seç. SaaS için Clean SaaS yerine Graphite veya Soft Structuralism. Oyun için Deep Tech yerine Cyberpunk veya Vaporwave.

---

## 1. BRIEF INFERENCE — Önce Odayı Oku (taste-skill)

Kod yazmadan önce **tasarım yönünü çıkar:**

### 1.1 Sinyalleri Oku
1. Sayfa türü (landing / portfolio / redesign / editorial)
2. Kullanıcının kullandığı vibe kelimeleri
3. Referans URL'ler, screenshot'lar, rakip markalar
4. Hedef kitle (B2B procurement vs design-conscious consumer vs recruiter)
5. Mevcut brand asset'leri (logo, renk, font, fotoğraf)
6. Sessiz kısıtlar (accessibility-first, public-sector, regulated)

### 1.2 "Design Read" Çıktısı
Kod yazmadan önce tek cümle:
> "Reading this as: [sayfa türü] for [kitle], with a [dil] language, leaning toward [stack]."

Örnek: *"Reading this as: B2B SaaS landing for technical buyers, with a Linear-style minimalist language, leaning toward Tailwind + Geist + restrained motion."*

### 1.3 Muğlaksa Sor
Tam olarak **bir** soru sor. Asla çoklu soru dump'ı yapma.

---

## 2. 3-DIAL SİSTEMİ — Tasarımın DNA'sı (taste-skill)

Her tasarım kararı bu üç kadran tarafından belirlenir:

| Kadran | 1 | 10 | Varsayılan |
|-----------|---|----|-----------|
| **DESIGN_VARIANCE** | Mükemmel simetri | Sanatsal kaos | 8 |
| **MOTION_INTENSITY** | Statik | Sinematik / fizik | 6 |
| **VISUAL_DENSITY** | Sanat galerisi / havadar | Kokpit / veri dolu | 4 |

### 2.1 Kadran Çıkarımı

| Sinyal | VARIANCE | MOTION | DENSITY |
|--------|----------|--------|---------|
| "minimalist / clean / calm / editorial / Linear-style" | 5-6 | 3-4 | 2-3 |
| "premium consumer / Apple-y / luxury / brand" | 7-8 | 5-7 | 3-4 |
| "playful / wild / Dribbble / Awwwards / experimental" | 9-10 | 8-10 | 3-4 |
| "landing page / portfolio (default)" | 7-9 | 6-8 | 3-5 |
| "trust-first / public-sector / accessibility-critical" | 3-4 | 2-3 | 4-5 |
| "redesign - preserve" | mevcutla aynı | +1 | mevcutla aynı |
| "redesign - overhaul" | +2 | +2 | mevcutla aynı |

---

## 3. TİPOGRAFİ

### 3.1 Hiyerarşi (En az 3 seviye)
```
Display  — hero, landing (2-3 yerde)
Heading  — bölüm başlıkları
Body     — metin içeriği
Label    — buton, input, badge
```

### 3.2 Altın Kurallar
- **En fazla 2 font ailesi.** Pair on contrast axis (serif + sans, geometric + humanist). İki geometric sans = hata.
- **Line-height:** heading 1.1-1.3, body 1.5-1.6
- **Letter-spacing:** heading -0.02em, body 0. Display floor ≥ **-0.04em** (altı cramped).
- **Measure:** body max 65-75 karakter
- `text-wrap: balance` headings, `text-wrap: pretty` body
- `font-variant-numeric: tabular-nums` veri/sayaç için
- **Asla** `letter-spacing` değiştirme (tracking), açıkça istenmediği sürece (baseline-ui)

### 3.3 Yasaklı Fontlar (soft-skill)
Inter, Roboto, Arial, Open Sans, Helvetica → premium projelerde kullanma.
Onun yerine: Geist, Clash Display, PP Editorial New, Plus Jakarta Sans.

---

## 4. RENK SİSTEMLERİ (OKLCH)

### 4.1 Palet Mimarisi
```
Brand       — 1 ana renk
Neutral     — 8-10 ton (50..950)
Accent      — 1 vurgu (opsiyonel)
Semantic    — success, warning, error, info
```

### 4.2 2026'nın AI Default'u: Cream/Sand Body BG (impeccable)
OKLCH L 0.84-0.97, C < 0.06, hue 40-100 → cream, sand, bone, flour, linen,
parchment, wheat, biscuit, ivory. **Token adları bile AI kokar** (`--paper`,
`--cream`, `--sand`).

> Brief "warm, traditional" dese bile warm-tinted body bg yapma. Onun yerine:
> (a) doygun brand rengi body, (b) chroma 0 off-white, veya (c) koyu nötr.

### 4.3 Tinted Neutrals
Nötrlere chroma'yı **brand'in hue'suna doğru** 0.005-0.015 ekle.
"Brand sıcak" diye her nötrü warm yapma — cross-project monokültür.

### 4.4 Color Strategy: 4 Kademe (impeccable)

| Seviye | Açıklama | Ne Zaman |
|--------|----------|----------|
| **Restrained** | Renkli nötrler + tek accent ≤%10 | Ürün default'u |
| **Committed** | Tek doygun renk %30-60 yüzey | Kimlik sayfaları |
| **Full palette** | 3-4 isimli rol | Kampanya, data viz |
| **Drenched** | Yüzey RENGİN kendisi | Hero, kampanya |

### 4.5 Dark vs Light: Fiziksel Sahne Sorusu (impeccable)
Cevap vermeden önce bir cümle yaz:
> "Bu arayüzü kim, nerede, hangi ışıkta, hangi ruh halinde kullanıyor?"

Cümle cevabı zorlamıyorsa yeterince somut değil.

### 4.6 Kontrast
- Body text ≥ 4.5:1, large text ≥ 3:1
- **Placeholder text de 4.5:1** (muted-gray yetmez — en yaygın failure)
- Gri text + renkli BG = soluk. BG'nin kendi hue'sunun koyu tonunu kullan
- Anlamı sadece renkle iletme

---

## 5. BOŞLUK VE GRID

### 5.1 Spatial Scale (4px base)
```
4px   — ikon-padding, inline gap
8px   — iç padding, yakın elementler
16px  — standart padding, card içi
24px  — bölüm içi boşluk
32px+ — bölümler arası
```
Tutarlı ol. 13px, 7px yok.

### 5.2 Macro-Whitespace (soft-skill)
Section padding: `py-24` ile `py-40`. Tasarım nefes alsın.

### 5.3 Davranış
- Flexbox 1D, Grid 2D. `flex-wrap` varken Grid'e default'lama
- Responsive grids: `repeat(auto-fit, minmax(280px, 1fr))`
- Cards are lazy. Nested cards = always wrong
- `size-*` kare elementler için (baseline-ui)

### 5.4 Card Grid Tutarlılığı

Asimetrik grid yaparken şu hataları yapma:

| Hata | Sonuç | Doğrusu |
|------|-------|---------|
| 1 kart 2fr + 4 kart 1fr yan yana | Genişlikler çok farklı, görsel dengesiz | Tüm kartlar aynı genişlikte, VEYA asimetri kasıtlı ve anlamlı |
| `grid-column: 1 / 3` + diğerleri 1fr | Featured kart 2x geniş, diğerleri sıkışık | Featured kart İÇERİĞİ farklı olmalı (resim + text), sırf "asimetrik olsun" diye yapma |
| 3-column grid'de 5 kart | Son satırda 2 kart ortalanır, 1 boşluk kalır | Kart sayısı grid'in katı olsun veya `auto-fill` kullan |
| Mobilde 1-column, desktop'ta 3-column | İçerik sıralaması bozulur (1-2-3 vs 1-4-2-5-3-6) | Aynı içerik akışını koru, `grid-auto-flow: dense` KULLANMA |

**Card grid checklist:**
```
[ ] Tüm kartlar aynı genişlikte mi? Değilse ASİMETRİ kasıtlı ve anlamlı mı?
[ ] Kart sayısı grid sütun sayısına bölünebiliyor mu?
[ ] Mobilde kart sıralaması bozuluyor mu?
[ ] Her kartın İÇ padding'i eşit mi?
[ ] Kartlar arası gap tutarlı mı?
```

#### 5.5 Kart Sayısına Göre Grid Stratejisi

`auto-fit` her zaman doğru sonuç vermez. Kart sayısına göre KASITLI grid seç:

| Kart sayısı | Masaüstü grid | Tablet | Mobil |
|------------|--------------|--------|-------|
| 2 | `repeat(2, 1fr)` | `repeat(2, 1fr)` | `1fr` |
| 3 | `repeat(3, 1fr)` | `repeat(3, 1fr)` | `1fr` |
| 4 | **`repeat(2, 1fr)`** ← 2x2 | `repeat(2, 1fr)` | `1fr` |
| 5 | `repeat(3, 1fr)` (3+2) veya 3+2 asimetrik | `repeat(2, 1fr)` → 2+2+1 | `1fr` |
| 6 | `repeat(3, 1fr)` (2 sıra) | `repeat(2, 1fr)` (3 sıra) | `1fr` |
| 7+ | `repeat(auto-fit, minmax(300px, 1fr))` | `repeat(2, 1fr)` | `1fr` |

> **Altın kural:** 4 kart = 2x2. Asla 3+1 bırakma. 5 kart = 3+2 tamam ama 2+2+1 değil.
> `auto-fit` sadece kart sayısı 7+ ise veya tam olarak kaç kart olacağını bilmiyorsan kullan.

---

## 6. DOUBLE-BEZEL MİMARİSİ (soft-skill)

Premium kart, imaj veya container'lar asla düz yerleştirilmez:

```
Outer Shell (bg-black/5, ring-1, p-1.5, rounded-[2rem])
  └── Inner Core (kendi bg'si, shadow-[inset_0_1px_1px_white/15],
       rounded-[calc(2rem-0.375rem)])
```

### Button-in-Button (soft-skill)
Trailing ikon asla text'in yanında çıplak durmaz. Kendi circular wrapper'ı içinde:
```html
<span class="w-8 h-8 rounded-full bg-black/5 flex items-center justify-center">↗</span>
```

### 6.1 Button Kalite Kontrolü

Button'larda şu hataları ASLA yapma:

| Hata | Sonuç | Doğrusu |
|------|-------|---------|
| `line-height: 1` + icon wrapper farklı boyutta | Text baseline kayar, ikon ile text ortalanmaz | `line-height: 1.2` veya icon wrapper ile aynı `height` kullan |
| `scale(0.97)` + `inline-flex` icon | İkon küçülür, text yerinde kalır gibi görünür | Tüm button'u scale et, icon wrapper'a `flex-shrink: 0` ver |
| `padding` asimetrik (sol 1rem, sağ icon wrapper kadar değil) | Text ile ikon arası dengesiz | Sol ve sağ padding eşit, gap icon wrapper'dan bağımsız |
| `min-height: 44px` ama `line-height: 1` | Text dikeyde ortalanmaz, üste yapışık durur | `display: inline-flex; align-items: center` + yeterli padding |
| Icon wrapper'a `flex-shrink: 0` yok | Dar ekranda icon ezilir | Her zaman `flex-shrink: 0` ekle |

**Button checklist (her button için):**
```
[ ] Text + icon aynı dikey eksende mi? (align-items: center)
[ ] scale(0.97) active state'te text kaymıyor mu?
[ ] Sol/sağ padding eşit mi?
[ ] min-height ≥ 44px mi?
[ ] Icon wrapper flex-shrink: 0 mı?
[ ] white-space: nowrap var mı?
```

---

## 7. HAREKET VE MİKRO-ETKİLEŞİM

### 7.1 Animasyon Karar Çerçevesi (emil-design-eng)

**Önce sor: Bu animasyonu kullanıcı ne sıklıkla görecek?**

| Sıklık | Karar |
|--------|-------|
| 100+/gün (klavye kısayolları, command palette) | **Asla anime etme** |
| Onlarca/gün (hover, liste gezinme) | Kaldır veya ciddi azalt |
| Ara sıra (modal, drawer, toast) | Standart animasyon |
| Nadir/ilk kez (onboarding, kutlama) | Delight eklenebilir |

**Klavye ile tetiklenen hiçbir şeyi anime etme.**

### 7.2 Easing Kuralları (emil-design-eng)

| Durum | Easing |
|-------|--------|
| Enter/exit | **ease-out** (hızlı başlar, responsive hissettirir) |
| Ekranda hareket/morph | ease-in-out |
| Hover/renk değişimi | ease |
| Sabit hareket (marquee, progress) | linear |

**Asla ease-in kullanma.** Yavaş başlar, arayüz sluggish hissettirir.

Custom easing'ler (built-in CSS easeler çok zayıf):
```css
--ease-out: cubic-bezier(0.23, 1, 0.32, 1);
--ease-in-out: cubic-bezier(0.77, 0, 0.175, 1);
--ease-drawer: cubic-bezier(0.32, 0.72, 0, 1); /* iOS-like */
```

### 7.3 Süre Hiyerarşisi (emil-design-eng)

| Element | Süre |
|---------|------|
| Button press | 100-160ms |
| Tooltip, küçük popover | 125-200ms |
| Dropdown, select | 150-250ms |
| Modal, drawer | 200-500ms |
| **Kural:** UI animasyonları 300ms altında kalmalı |

### 7.4 Spring > Duration (emil-design-eng)
- Drag + momentum → spring
- "Canlı" hissetmesi gereken elementler → spring
- Kesilebilir gesture'lar → spring
- Mouse-tracking → `useSpring` (asla `useState` ile continuous value track etme)

### 7.5 Enter/Exit Formülü (make-interfaces-feel-better)
- **Enter:** opacity + ufak translateY + opsiyonel blur
- **Exit:** daha kısa, daha sessiz (150ms)
- **İkon swap:** opacity + scale + blur cross-fade
- **Press:** `scale(0.96)`, rahatsız edici olursa kapatma yolu bırak

### 7.6 CSS Transition > Keyframe (make-interfaces-feel-better)
İnteraktif state'lerde transition kullan — kullanıcı fikrini değiştirirse
retarget olabilir. Keyframe'leri one-shot girişler için sakla.

---

## 8. PERFORMANS

### 8.1 Render Pipeline (fixing-motion-performance)

| Katman | Özellikler | Maliyet |
|--------|-----------|--------|
| Composite | transform, opacity | En ucuz |
| Paint | color, border, gradient, mask, filter | Orta |
| Layout | size, position, flow, grid, flex | En pahalı |

### 8.2 Asla Yapma
- Aynı frame'de layout read + write
- Büyük yüzeylerde sürekli layout animasyonu
- Scroll event'inden animasyon sürme — **Scroll/View Timeline** veya **IntersectionObserver** kullan
- `useState` ile continuous value (mouse, scroll) track etme — Motion's `useMotionValue` kullan
- `will-change` sadece ilk-frame takılmasında, geçici ve cerrahi

### 8.3 FLIP Tekniği
Layout değişimi şartsa: ölç → değiştir → tersini hesapla → transform ile anime et.
`getBoundingClientRect()`'i animasyon döngüsünde çağırma.

### 8.4 Blur
- ≤ 8px, kısa, tek seferlik
- Asla sürekli, asla büyük yüzeylerde
- Sadece fixed/sticky elementlerde

### 8.5 GPU-Safe (soft-skill)
Sadece `transform` ve `opacity` anime et. Asla `top`, `left`, `width`, `height`.
`will-change: transform` sadece aktif animasyon sırasında.

---

## 9. ERİŞİLEBİLİRLİK (WCAG 2.2 AA)

### 9.1 Öncelik Sırası (fixing-accessibility)
1. **Accessible names** (kritik) — her kontrolün adı olmalı, icon-only = aria-label
2. **Keyboard** (kritik) — Tab ulaşabilmeli, Escape kapatmalı, tabindex > 0 yasak
3. **Focus & dialogs** (kritik) — trap, restore, initial focus
4. **Semantics** (yüksek) — native > role hack; heading atlama
5. **Forms & errors** (yüksek) — aria-describedby, aria-invalid
6. **Announcements** (orta) — aria-live, aria-busy
7. **Contrast** (orta) — hover = keyboard equivalent de olmalı
8. **Motion** (düşük) — prefers-reduced-motion
9. **Tool boundaries** (kritik) — native çözüyorsa aria ekleme, UI library migrate etme

### 9.2 Checklist (Her Component İçin)
- [ ] Klavye: Tab, Enter, Escape, Arrow'lar
- [ ] Focus: visible outline (asla `outline: none` tek başına)
- [ ] ARIA: doğru roller
- [ ] Kontrast: AA minimum
- [ ] Screen reader: alt text, aria-label
- [ ] Form: her input'un label'ı, error state'ler duyuruluyor
- [ ] Renk: anlam sadece renkle değil

---

## 10. EDGE CASES — Her State Tasarlanmış Olmalı

```
✅ İdeal (dolu)
🔄 Loading (skeleton, spinner değil)
📭 Empty (anlamlı + aksiyon)
❌ Error (ne oldu + ne yapmalı)
🚫 Disabled (neden + nasıl aktif)
📱 Responsive (320px'de patlama yok)
🌍 i18n ready (%30 büyüme payı)
```

**Spesifik kurallar:**
- `h-dvh` — `h-screen` değil (mobil address bar için)
- `safe-area-inset` fixed elementler için
- Asla input/textarea'da paste engelleme
- Empty state'te bir net aksiyon
- AlertDialog destrüktif işlemler için
- Asla `useEffect`'i render logic olarak kullanma

---

## 11. YASAKLI AI PATTERN'LERİ

Bu pattern'lerden birini yazmak üzereysen DUR:

| Pattern | Kaynak |
|---------|--------|
| Cream/sand body bg (OKLCH L 0.84-0.97, C<0.06, hue 40-100) | impeccable |
| `border-left/right > 1px` renkli stripe | impeccable |
| `background-clip: text` gradient | impeccable |
| Glassmorphism default | impeccable |
| Hero-metric (büyük sayı + label + stats) | impeccable |
| Özdeş card grid'leri | impeccable |
| Her section'da tiny uppercase eyebrow | impeccable |
| 01/02/03 numaralı section marker | impeccable |
| Text overflow (clamp + dar grid) | impeccable |
| Hover'da `<img>` animasyonu (group-hover:scale) | impeccable |
| Gradient (özellikle purple/multicolor) | baseline-ui |
| Glow efektleri primary affordance | baseline-ui |
| `transition: all` | make-interfaces-feel-better |
| `will-change: all` | make-interfaces-feel-better |
| Inter, Roboto, Arial font'ları (premium projelerde) | soft-skill |
| `ease-in` UI animasyonları | emil-design-eng |
| Klavye action'larına animasyon | emil-design-eng |
| `useState` ile continuous value track | taste-skill |
| `z-[999]` rastgele z-index | baseline-ui + soft-skill |

---

## 12. RESPONSIVE DESIGN — Mobil Öncelikli Düşün

Mobil %60+ trafik demek. Responsive sonradan eklenmez, **tasarımın kendisidir.**

### 12.1 Breakpoint Stratejisi

```css
/* Mobile-first: base stiller mobil için */
/* Tablet: 640px+ */
@media (min-width: 640px) { ... }
/* Desktop: 1024px+ */
@media (min-width: 1024px) { ... }
/* Wide: 1280px+ (opsiyonel) */
@media (min-width: 1280px) { ... }
```

### 12.2 Her Bileşende Kontrol Edilmesi Gerekenler

| Nokta | Mobil | Tablet | Masaüstü |
|-------|-------|--------|----------|
| **Grid** | 1 column | 2 column (veya kart sayısına göre) | 5.5 tablosundaki |
| **Font** | -%10 küçült (clamp varsa otomatik) | Normal | Normal |
| **Padding** | `px-4` → `px-6` → `px-8` | Orta | Geniş |
| **Nav** | Hamburger/bottom | Sabit/seçili | Seçili |
| **Hero** | Tam genişlik, küçük text | Orta | Tam tasarım |
| **Touch** | 44px+ target, 8px+ gap | 44px+ | 44px+ |
| **Görsel** | Küçük, lazy | Orta | Tam kalite |

### 12.3 Mobilde ASLA Yapma

| Hata | Sonuç | Doğrusu |
|------|-------|---------|
| `h-screen` | iOS Safari address bar yüzünden taşar | `min-h-dvh` veya `min-h-[100dvh]` |
| Yatay scroll | İçerik taşmış, kullanıcı sağa kaydırıyor | `overflow-x-hidden` + gerçek sebebi bul |
| `hover` ile kritik etkileşim | Mobilde hover yok, işlev kaybolur | `click/tap` primary, hover sadece enhancement |
| Sabit `width: 1200px` | Mobilde yatay scroll | `max-width` + `width: 100%` |
| `zoom` engelleme | Erişilebilirlik ihlali | `user-scalable=yes` (default) |
| Asimetrik grid'i mobilde zorlamak | 2-column asimetri mobilde 1-column'a düşünce anlamsız | Mobilde `grid-template-columns: 1fr` |
| `font-size: clamp(4rem, 10vw, 9rem)` başlık | Mobilde hala çok büyük | Mobil için ayrı clamp: `clamp(2.5rem, 12vw, 4rem)` |

### 12.4 Test Komutları

Her sayfayı şu çözünürlüklerde ZİHİNDE test et:
```
[ ] 375px  (iPhone SE)  — her şey görünüyor mu? yatay scroll var mı?
[ ] 768px  (iPad mini)  — grid doğru sütun sayısında mı?
[ ] 1024px (iPad Pro)   — masaüstüne geçiş düzgün mü?
[ ] 1440px (MacBook)    — çok geniş ekranda içerik ip gibi dizilmiyor mu?
```

---

## 13. TEKNOLOJİ SEÇİMİ

| Amaç | Tercih |
|------|--------|
| Stil | Tailwind v4 (varsayılan) |
| Animasyon | Motion (`motion/react`), GSAP (karmaşık) |
| Renk | OKLCH, fallback HSL |
| İkon | Phosphor, Lucide, Remix Line (ultra-light) |
| Font | next/font veya self-host + font-display:swap |
| Form | react-hook-form + zod |
| Erişilebilirlik | Radix UI, Base UI, React Aria |
| State | Local useState/useReducer; global: Zustand/Jotai |

---

## 14. TASARIM SİSTEMİ HARİTASI (taste-skill)

Brief bir tasarım sistemini işaret ediyorsa **resmi paketi** kullan, CSS'ini
elle yazma:

| Brief | Sistem |
|-------|--------|
| Microsoft / enterprise SaaS | @fluentui/react-components |
| Google-ish / Material | @material/web + M3 tokens |
| IBM-style B2B | @carbon/react |
| GitHub-style devtool | @primer/css |
| Public-sector UK | govuk-frontend |
| US public-sector | uswds |
| Modern React foundation | @radix-ui/themes |
| Kendi component'lerinle SaaS | shadcn/ui |
| Indie / small team | Tailwind v4 |

**Bir sistem, bir proje.** Asla Fluent + Carbon karıştırma.

---

## 15. ÇIKTI DİSİPLİNİ

- Asla `// ... more items`, `{/* TODO */}`, truncated kod
- Her zaman production-ready, tüm import'lar, tüm stiller
- Tüm state'ler: loading, empty, error, disabled
- Responsive: 320px, 768px, 1024px, 1440px test edilmiş
- Tüm referans path'leri absolute

---

## 16. ÖZET CHECKLIST

Kod yazmadan önce:
1. [ ] Design Read yapıldı mı?
2. [ ] 3 kadran (VARIANCE/MOTION/DENSITY) belirlendi mi?
3. [ ] Renk stratejisi seçildi mi (Restrained/Committed/Full/Drenched)?
4. [ ] Kullanıcı bunu günde kaç kez görecek? (Animasyon kararı)

Kod yazdıktan sonra:
5. [ ] Yasaklı pattern'lerden var mı?
6. [ ] Spacing 4px scale'ine uyuyor mu?
7. [ ] Kontrast AA geçiyor mu?
8. [ ] Klavye ile kullanılabiliyor mu?
9. [ ] `transition: all` veya `will-change: all` var mı?
10. [ ] Layout animasyonu (width/height/top/left) var mı?
11. [ ] `h-screen` yerine `h-dvh` kullanıldı mı?
12. [ ] 320px'de patlıyor mu?

---

## 17. CONTRAST & OKUNABİLİRLİK — LLM Çıktısını İyileştirme

> **Temel sorun:** AI modelleri "güzel görünen" için optimize eder, "herkes için
> çalışan" için değil. WebAIM 2024: **web sayfalarının %95.9'unda WCAG hatası var.**
> AI bu veriden öğreniyor — aynı hataları kopyalıyor.

### 16.1 AI'ın En Sık Yaptığı Kontrast Hataları

| Hata | Örnek | Gerçek Oran | Gereken |
|------|-------|-------------|---------|
| **Açık gri text / beyaz BG** | `#999` on `#fff` | ~2.8:1 | 4.5:1 |
| **Orta gri text** | `#666` on `#fff` | ~5.2:1 ✅ | — (bu geçer) |
| **Soluk gri text** | `#999` on `#f5f5f5` | ~2.1:1 | 4.5:1 |
| **Mavi link / koyu BG** | `#007bff` on `#1a1a1a` | ~2.1:1 | 4.5:1 |
| **Accent renk body text** | Orange on light | ~2.8:1 | 4.5:1 |
| **Dark mode gri text** | Brown/beige on dark | ~2-3:1 | 4.5:1 |

**En sık failure:** AI, light gray text'i "clean" ve "modern" sanıyor.
Gerçekte 2:1 contrast = WCAG AA'nın yarısı bile değil.

### 16.2 AI Neden Kontrastı Iskalıyor?

1. **Eğitim verisi erişilebilir değil.** Milyonlarca web sayfası aynı hatalarla dolu.
   AI "böyle olmalı" sanıyor.
2. **Kontrast hesaplamaz.** AI renk seçerken matematik yapmaz — olasılıksal
   örüntü eşleştirme yapar.
3. **Renk körlüğü simülasyonu yapmaz.** Erkeklerin %8'i, kadınların %0.5'i renk
   körü. 100K kullanıcıda ~4000 kişi arayüzü farklı görüyor.
4. **Dark mode'u sonradan düşünür.** Light mode için seçilen renk dark mode'da
   çalışmayabilir.

### 16.3 Kesin Kurallar (Prompt-Seviyesinde)

Bu kuralları her frontend görevinde uygula:

```
1. Body text: en az 16px, line-height ≥ 1.5, contrast ≥ 4.5:1
2. Large text (≥18px bold veya ≥24px): contrast ≥ 3:1
3. Placeholder bile 4.5:1 (muted-gray default yetmez)
4. Text asla 12px altı (body için)
5. Gri text + beyaz BG kombinasyonunu ASLA kullanma.
   "Clean" görünen açık gri = erişilemez.
6. Rengi TEK başına anlam taşıyıcı olarak kullanma.
   Error/success her zaman ikon + text ile desteklenmeli.
7. Dark mode'da text'i asla kahverengi/bej yapma.
   Bu AI'ın en yaygın dark mode hatasıdır.
8. Focus ring'i asla kaldırma. `outline: none` tek başına = yasak.
```

### 16.4 Prompt Mühendisliği: AI'dan Erişilebilir Çıktı Almak

AI'dan UI isterken şu spesifikasyonları her zaman ekle:

> "Generate a [component] with: 16px minimum text size, 4.5:1 contrast
> ratios on all text, proper semantic HTML, 44px minimum touch targets,
> visible focus indicators, and no color-only state indicators."

### 16.5 Kendi Kendini Denetleme (Self-Audit) Komutları

Çıktı ürettikten sonra AI'ın kendi kendine yapması gereken kontroller:

```
1. [ ] Tüm text'ler 16px veya üstü mü?
2. [ ] Line-height body'de ≥ 1.5 mi?
3. [ ] En az 2 text/BG pair'i 4.5:1 altında mı? Varsa DÜZELT.
4. [ ] Focus ring visible mı? (outline: none tek başına mı?)
5. [ ] Sadece renkle iletilen anlam var mı? Varsa ikon/text ekle.
6. [ ] Touch target'lar en az 44x44px mi?
7. [ ] Dark mode'da text kahverengi/bej değil, değil mi?
8. [ ] `transition: all` veya `will-change: all` var mı?
```

### 16.6 Renk Rolleri ve Kullanım Matrisi

Her renk bir role sahip olmalı. Rol dışı kullanım = hata:

| Rol | Nerede KULLANILIR | Nerede KULLANILMAZ |
|-----|-------------------|-------------------|
| **Ink** (text) | Body, heading, label | — (tek kullanımı text) |
| **Background** | Sayfa/ kart arka planı | — |
| **Accent** | CTA buton, link, vurgu | **ASLA body text olarak** |
| **Muted** | Secondary text, caption | **ASLA body text olarak** (contrast yetmez) |
| **Border** | Ayırıcı çizgiler | Text olarak (çok düşük contrast) |

### 16.7 Hızlı Contrast Test Formülü (Eğer Tool Yoksa)

OKLCH kullanıyorsan kaba hesap:
- **L değeri farkı ≥ 40** → genelde 4.5:1 geçer
- **L farkı < 30** → neredeyse kesin FAIL
- Light mode'da en koyu text: L = 20-35
- Dark mode'da en açık text: L = 85-95
- Muted text için: L farkı ≥ 50 hedefle (AAA için)

> **Unutma:** AI'ın "güzel" dediği gri text'lerin %80'i WCAG fail.
> `#999999` body text gördüğün an düzelt.

---

## 18. STİL VE TEMA KATALOĞU (30 Tema)

Kullanıcı "güzel bir tasarım yap" dediğinde ajana yön verecek stil kütüphanesi.
Her stil; vibe, renk paleti, tipografi, layout ve "ne zaman kullanılır" ile
tanımlanır. Ajan brief'ten çıkarım yapamazsa bu listeden en yakın 2-3 stili
kullanıcıya sor.

### 18.1 Koyu / Teknoloji

**1. Dark Terminal** — Ham, CRT hacker estetiği. `#0A0A0A` bg, `#4AF626` yeşil phosphor, monospace font. Dev tool, CLI docs, güvenlik ürünleri.

**2. Deep Tech / OLED** — Premium siyah, neon vurgulu. `#040308` bg, `#C44DFF` accent. Grotesk display. AI/ML, oyun stüdyosu, devtool landing.

**3. Cyberpunk / Neon Noir** — Yağmurlu sokak, sentetik. `#0D0221` bg, magenta+cyan. Square sans. Oyun, müzik, Web3.

**4. Graphite / Monochrome Dark** — Ciddi, kurumsal. 12 ton gri + tek accent. Humanist sans. Profesyonel tool, B2B SaaS.

### 17.2 Açık / Temiz

**5. Editorial Minimal** — Dergi sayfası, tipografi önde. `#FDFBF7` krem, serif heading. Blog, portfolio, içerik.

**6. Swiss Modern** — Grafik tasarım, grid, objektif. `#FFFFFF` + kırmızı/mavi accent. Neo-grotesk. Mimarlık, tasarım stüdyosu.

**7. Soft Structuralism** — Gümüş-gri, havadar. `#F5F5F7` + yumuşak mavi. SF Pro. Tüketici, sağlık, Apple-esque.

**8. Clean SaaS** — Profesyonel, güvenilir. `#FFFFFF` + `#2563EB`. Geometric sans. SaaS landing, B2B.

### 17.3 Sıcak / Organik

**9. Editorial Luxury** — Butik otel lobisi. `#FDF8F0` krem, `#2D1B0E` espresso, `#C4A265` altın. Lüks emlak, moda.

**10. Earth / Natural** — Organik, toprak. `#F4F1EA` + yeşil/terracotta. Serif + rounded sans. Sürdürülebilirlik, outdoor.

**11. Mediterranean / Warm** — Akdeniz, taş, zeytin. `#FEF9F0` + koyu yeşil + toprak. Restoran, seyahat.

### 17.4 Cesur / Deneysel

**12. Brutalist** — Ham beton, tavizsiz. `#F4F4F0` newsprint, `#E61919` red. Ağır grotesk, border-radius:0. Portfolyo, deneysel.

**13. Bento Grid** — Apple etkinliği, modüler. Asimetrik CSS Grid. SF Pro. Ürün tanıtım, feature showcase.

**14. Memphis / Playful** — 80'ler geometri, eğlenceli. Çoklu yüksek kontrast renk. Yuvarlak display font. Çocuk, etkinlik.

**15. Z-Axis Cascade** — 3B hissi, katmanlı. Kartlar üst üste, rotation'lı. Portfolyo, ajans.

### 17.5 Cam / Işık

**16. Ethereal Glass** — Vantablack + glass. `#050505` + `backdrop-blur-2xl`. AI/tech SaaS.

**17. Aurora / Mesh Gradient** — Kuzey ışıkları, rüya. Mor/mavi/yeşil gradient'ler. Kreatif tool, müzik.

**18. Frosted Glass / Light** — Aydınlık buzlu cam. `#F0F0F5` + blur. iOS app landing, modern dashboard.

### 17.6 Retro / Nostaljik

**19. Vaporwave / Synthwave** — 80'ler Miami. Pembe/mor/cyan. Outrun font. Müzik, oyun, festival.

**20. Y2K / Web 1.0** — 2000'ler interneti. Web-safe palette, pixel font, marquee. Nostalji, ironik.

**21. Grunge / Punk** — Konser posteri, fotokopi. Kağıt tonu + toner siyahı + sprey kırmızı. Müzik, sokak giyim.

### 17.7 Kurumsal / Güven

**22. Trust-First / Public Sector** — Erişilebilir, resmi. Gov blue `#1D70B8`. System font. Kamu, sağlık, banka.

**23. Corporate / Enterprise** — Büyük şirket. `#003366` + sınırlı kırmızı accent. Enterprise SaaS, yatırımcı.

**24. Financial / Fintech** — Güven + data. `#0F1923` + `#00D4AA`. Mono numbers. Banka, kripto.

### 17.8 Yaratıcı / Sanatsal

**25. Editorial Split** — İkiye bölünmüş sayfa. w-1/2 text + w-1/2 görsel. Portfolyo, fotoğraf.

**26. Magazine / Editorial** — Vogue/NYT dijital. Didot/Bodoni serif. Yayın, uzun-form.

**27. Kinetic Typography** — Hareketli tipografi. Scroll-driven, variable font. Marka hikayesi.

### 17.9 Mobil / App

**28. Mobile-First / App Shell** — Native app hissi. iOS HIG / Material. Mobil landing.

**29. Dashboard / Data-Dense** — Veri kokpiti. Koyu bg, anlamsal renkler. Analytics, monitoring.

**30. Onboarding / Welcome Flow** — Sıcak karşılama. Progress bar, illüstrasyon. App onboarding.

---

### 18.10 Stil Seçim Algoritması

| Sinyal | Stil # |
|--------|--------|
| "dark / karanlık / gece" | 1, 2, 3, 4, 16 |
| "modern / temiz / sade" | 5, 6, 7, 8 |
| "sıcak / samimi / organik" | 9, 10, 11 |
| "cesur / farklı / deneysel" | 12, 13, 14, 15 |
| "premium / lüks / pahalı" | 9, 17, 18 |
| "retro / eski / nostaljik" | 19, 20, 21 |
| "kurumsal / ciddi / güvenilir" | 22, 23, 24 |
| "yaratıcı / sanatsal / portfolyo" | 25, 26, 27 |
| "mobil / app" | 28, 29, 30 |
| "AI / tech / yazılım" | 2, 8, 16 |
| "oyun / eğlence" | 3, 14, 19 |

**Kullanıcı hiçbir şey belirtmezse:** Ürün tipine göre varsayılan seç.
SaaS → 8, Portfolyo → 5, Oyun → 2, Landing → 2 veya 8, Dashboard → 29.

---

Bu skill şu 8 SKILL.md'nin tam içerik analizine dayanır:

| Skill | Yazar | Ana Katkı |
|-------|-------|-----------|
| taste-skill | Leonxlnx | 3-dial sistemi, brief inference, tasarım sistemi haritası |
| soft-skill | Leonxlnx | Double-Bezel, variance engine, yasaklı fontlar/ikonlar |
| brutalist-skill | Leonxlnx | Swiss Industrial + Tactical Telemetry estetiği |
| impeccable | pbakaus | Renk stratejisi, absolute bans, anti-AI pattern'ler |
| baseline-ui | Ibelick | Tailwind enforcement, animasyon/performans constraint'leri |
| emil-design-eng | emilkowalski | Animasyon karar çerçevesi, spring fizik, frequency-based |
| make-interfaces-feel-better | jakubkrehel | Mikro-polish: konsantrik radius, optik hizalama, hit area |
| fixing-accessibility | Ibelick | WCAG öncelik sıralı kurallar |
| fixing-motion-performance | Ibelick | Render pipeline, FLIP, blur constraint'leri |

Diğer 100 skill framework-specific (Vue, React, Next.js, Three.js, Svelte),
çok dar kapsamlı (Slidev, tsdown, Pinia), veya yukarıdakilerin
varyasyonları olduğu için ayrıca analiz edilmemiştir.
