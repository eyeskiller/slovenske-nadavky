# Slovenské nadávky

Zoznam slovenských vulgárnych slov, nadávok a sprostých výrazov vhodný na filtrovanie obsahu, trénovanie modelov alebo iné NLP účely.

## Obsah

- **`sproste_slova.csv`** — 1 350+ slovenských nadávok, každá na samostatnom riadku

## Čo obsahuje

- Základné obscénne slová (jebať, mrdať, šukať, pichať, srať, prdieť, šťať, čúrať, ...)
- Všetky časované a skloňované tvary
- Predponové slovesné odvodeniny (na-, vy-, za-, pre-, od-, roz-, po-, ...)
- Prídavné mená a podstatné mená odvodené od vulgárnych koreňov
- Bežné nadávky a urážky (kokot, kurva, hajzeľ, zmrd, magor, kretén, debil, ...)
- Augmentatívy a deminutívy (kokotisko, prdelka, kundička, ...)
- Slová dôležité pre filter nenávistného obsahu (rasové, homofóbne slová, ...)

## Použitie

```python
with open("sproste_slova.csv", encoding="utf-8") as f:
    nadavky = set(line.strip().lower() for line in f if line.strip())

def obsahuje_nadavku(text):
    slova = text.lower().split()
    return any(slovo in nadavky for slovo in slova)
```

## Licencia

Apache License 2.0 — pozri [LICENSE](LICENSE).
