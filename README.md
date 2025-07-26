# 🦜 Ornithophile

A lightweight RESTful API serving detailed information on **11,290 bird species** — including taxonomy, conservation status, sounds, and image links. Perfect for bird watchers, nature apps, educational platforms, and biodiversity research projects.

---

## 🚀 Live API

👉 Visit the live API: [https://ornithophile.vercel.app](https://ornithophile.vercel.app)

You can use the endpoints directly in your applications or for exploration in Postman, Curl, etc.

---

## 📦 Features

- 🐦 List all bird species
- 🔍 Search birds by name or other attributes
- 🧬 Filter by taxonomic category (e.g., family, genus)
- 🔤 Fetch birds by starting alphabet
- 🖼️ Automatically upgrade bird image resolutions (up to 1000px)

---
## 📚 API Endpoints

### Get All Birds

```
GET /api/birds
```

### Search Birds

```
GET /api/birds?common_name=dodo
GET /api/birds?family=Raphinae
```

Supports query strings based on bird properties.

---

### Get Bird by ID

```
GET /api/birds/:id
```

---

### Filter by Taxonomic Category

```
GET /api/birds/category/:level/:value
```

* `:level` must be one of: `domain`, `kingdom`, `phylum`, `class`, `order`, `family`, `genus`, `species`

Example:

```
GET /api/birds/category/family/Corvidae
```

---

### Filter by Alphabet

```
GET /api/birds/alpha/:letter
```

Returns birds whose names start with the specified letter. Example:

```
GET /api/birds/alpha/a
```

---

## 🖼️ Image Resolution Upgrade

If a bird's image URL contains a size of `250px` or less, it's automatically upgraded to `1000px`.
Example:

```text
Before: .../250px-Bird.jpg  
After:  .../1000px-Bird.jpg
```

Works on:

* `male_image`
* `female_image`
* `other_images[]`

---

## 📄 Example Bird Object

```json
{
    "id": "1e79e936-4a1c-4bc6-84da-8fe147b7c1ad",
    "common_name": "Abbott's babbler",
    "scientific_name": "Malacocincla abbotti",
    "male_image": "//upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Malacocincla-abbotti-abbotts-babbler-khao-yai-national-park.jpg/1000px-Malacocincla-abbotti-abbotts-babbler-khao-yai-national-park.jpg",
    "female_image": "//upload.wikimedia.org/wikipedia/commons/thumb/7/7c/Abbott%27s_babbler_%28Malacocincla_abbotti%29.jpg/1000px-Abbott%27s_babbler_%28Malacocincla_abbotti%29.jpg",
    "conservation_status": "Least Concern",
    "domain": "Eukaryota",
    "kingdom": "Animalia",
    "phylum": "Chordata",
    "class": "Aves",
    "order": "Passeriformes",
    "family": "Pellorneidae",
    "genus": "Malacocincla",
    "species": "M. abbotti",
    "sound": "https://xeno-canto.org/983127/download",
    "description": "Abbott's babbler (Malacocincla abbotti) is a species of bird in the family Pellorneidae. It is widely distributed along the Himalayas in South Asia and extending into the forests of Southeast Asia. They are short-tailed and stout birds which forage in pairs in dense undergrowth close to the ground and their presence is indicated by their distinctive calls.",
    "sources": "https://en.wikipedia.org/wiki/Abbott's_babbler",
    "other_images": [
      {
        "name": "Unnamed",
        "source": "//upload.wikimedia.org/wikipedia/commons/thumb/5/5a/Status_iucn3.1_LC.svg/1000px-Status_iucn3.1_LC.svg.png"
      },
      {
        "name": "Unnamed",
        "source": "//upload.wikimedia.org/wikipedia/commons/thumb/3/32/MalacocinclaAbbottiFBI.jpg/1000px-MalacocinclaAbbottiFBI.jpg"
      },
      {
        "name": "Unnamed",
        "source": "//upload.wikimedia.org/wikipedia/commons/thumb/c/cc/TrichostomaAbbotti.jpg/1000px-TrichostomaAbbotti.jpg"
      }
    ]
}
```

---

## License

This project is licensed under the **Academic Non-Commercial License**. It is free to use for academic, research, and educational purposes only.

**Please credit Maxi Aditya Kusuma Winarjo if you use this work.**  
Commercial use is not allowed without prior written permission.
