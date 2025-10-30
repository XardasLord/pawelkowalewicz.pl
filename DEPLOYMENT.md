# 🚀 Deployment na GitHub Pages

## Przygotowanie do deployment

Strona jest już gotowa do wdrożenia! Wszystkie pliki są zoptymalizowane:

✅ `.nojekyll` - Wyłącza przetwarzanie Jekyll na GitHub Pages
✅ `sitemap.xml` - Zaktualizowana mapa strony
✅ `robots.txt` - Instrukcje dla robotów Google
✅ `CNAME` - Niestandardowa domena (jeśli masz)
✅ Wszystkie obrazki w `assets/`
✅ SEO w pełni zoptymalizowane

## Krok po kroku - GitHub Pages

### 1. Utwórz repozytorium na GitHub

```bash
# W terminalu, w folderze projektu:
git init
git add .
git commit -m "Initial commit - Portfolio website"
```

### 2. Dodaj remote repository

Stwórz nowe repo na GitHub, np. `pawelkowalewicz.github.io` lub `portfolio`

```bash
git remote add origin https://github.com/XardasLord/pawelkowalewicz.github.io.git
git branch -M main
git push -u origin main
```

### 3. Włącz GitHub Pages

1. Idź do Settings → Pages
2. Source: Deploy from a branch
3. Branch: `main` (lub `master`)
4. Folder: `/ (root)`
5. Kliknij **Save**

### 4. Niestandardowa domena (opcjonalnie)

Jeśli masz domenę `pawelkowalewicz.pl`:

1. W Settings → Pages → Custom domain wpisz: `pawelkowalewicz.pl`
2. W DNS domeny dodaj rekord:
   - Typ: `A`
   - Host: `@`
   - Wartość: 
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
3. Dodaj też rekord CNAME:
   - Typ: `CNAME`
   - Host: `www`
   - Wartość: `xardaslord.github.io`

### 5. Sprawdź działanie

Strona będzie dostępna pod:
- `https://xardaslord.github.io/` (domyślnie)
- `https://pawelkowalewicz.pl/` (jeśli skonfigurujesz domenę)

## Aktualizacje strony

Gdy chcesz zaktualizować stronę:

```bash
# 1. Edytuj pliki
# 2. Commituj zmiany
git add .
git commit -m "Opis zmian"
git push

# GitHub Pages automatycznie zaktualizuje stronę (2-5 minut)
```

## Checklist przed deployment

- [ ] Sprawdź czy wszystkie linki działają
- [ ] Przetestuj na różnych urządzeniach
- [ ] Uruchom w trybie prywatnym przeglądarki
- [ ] Sprawdź konsolę (F12) - brak błędów
- [ ] Wszystkie obrazki się ładują
- [ ] Responsywność działa
- [ ] Menu mobilne działa

## Testy SEO po deployment

Po wdrożeniu sprawdź:

1. **Google Search Console**
   - Dodaj stronę
   - Prześlij sitemap.xml

2. **PageSpeed Insights**
   - https://pagespeed.web.dev/
   - Sprawdź wydajność (powinno być 90+)

3. **Schema Markup Validator**
   - https://validator.schema.org/
   - Wklej URL, sprawdź structured data

4. **Mobile-Friendly Test**
   - https://search.google.com/test/mobile-friendly

## Monitoring

### Google Analytics (opcjonalnie)

Dodaj przed `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Google Search Console

1. Idź do: https://search.google.com/search-console
2. Dodaj property: `pawelkowalewicz.pl`
3. Weryfikuj przez plik HTML lub meta tag
4. Prześlij sitemap: `https://pawelkowalewicz.pl/sitemap.xml`

## Troubleshooting

**Problem: 404 Not Found**
- Sprawdź czy `index.html` jest w głównym folderze
- Sprawdź czy branch w ustawieniach GitHub Pages jest poprawny

**Problem: Brak CSS/obrazków**
- Sprawdź ścieżki w HTML (czy są relatywne, bez początkowego `/`)
- Obecny: `assets/logo.svg` ✅
- Błędny: `/assets/logo.svg` ❌

**Problem: Strona się nie aktualizuje**
- Wyczyść cache przeglądarki (Ctrl+Shift+R)
- Zaczekaj 2-5 minut na przebudowę GitHub Pages
- Sprawdź Actions w GitHub (czy build się powiódł)

**Problem: Domena nie działa**
- Sprawdź DNS (może zająć do 48h)
- Sprawdź czy CNAME w repo jest poprawny
- W GitHub Pages zaznaczy "Enforce HTTPS"

## 🎉 Gotowe!

Twoja strona jest teraz live i dostępna dla całego świata!

## Następne kroki (opcjonalnie)

1. **Dodaj blog** - Jekyll/Hugo integration
2. **Newsletter** - Mailchimp integration
3. **Contact form** - Formspree/Netlify Forms
4. **Dark/Light toggle** - Switcher motywów
5. **Animacje** - Dodatkowe micro-interactions

## Potrzebujesz pomocy?

Sprawdź:
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Custom Domain Setup](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

Powodzenia! 🚀

