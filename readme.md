  # Software Engineering Live Coding Exam
## JSON Transformation: Category Tree Builder

### Problem Statement
Transform a flat list of product categories into a nested category tree structure.

### Input Data
```json
[
  {
    "id": 1,
    "name": "Electronics",
    "slug": "electronics",
    "parentId": null,
    "description": "Electronic devices and gadgets"
  },
  {
    "id": 2,
    "name": "Computers & Laptops",
    "slug": "computers-laptops",
    "parentId": 1,
    "description": "Desktop computers, laptops, and accessories"
  },
  {
    "id": 3,
    "name": "Mobile Phones",
    "slug": "mobile-phones",
    "parentId": 1,
    "description": "Smartphones and mobile accessories"
  },
  {
    "id": 4,
    "name": "Home & Garden",
    "slug": "home-garden",
    "parentId": null,
    "description": "Home improvement and gardening supplies"
  },
  {
    "id": 5,
    "name": "Laptops",
    "slug": "laptops",
    "parentId": 2,
    "description": "Portable computers and notebooks"
  },
  {
    "id": 6,
    "name": "Desktop Computers",
    "slug": "desktop-computers",
    "parentId": 2,
    "description": "Desktop PCs and workstations"
  },
  {
    "id": 7,
    "name": "Smartphones",
    "slug": "smartphones",
    "parentId": 3,
    "description": "Mobile phones with advanced features"
  },
  {
    "id": 8,
    "name": "Phone Accessories",
    "slug": "phone-accessories",
    "parentId": 3,
    "description": "Cases, chargers, and mobile accessories"
  },
  {
    "id": 9,
    "name": "Furniture",
    "slug": "furniture",
    "parentId": 4,
    "description": "Home and office furniture"
  },
  {
    "id": 10,
    "name": "Gaming Laptops",
    "slug": "gaming-laptops",
    "parentId": 5,
    "description": "High-performance laptops for gaming"
  },
  {
    "id": 11,
    "name": "Business Laptops",
    "slug": "business-laptops",
    "parentId": 5,
    "description": "Professional laptops for business use"
  },
  {
    "id": 12,
    "name": "Android Phones",
    "slug": "android-phones",
    "parentId": 7,
    "description": "Smartphones running Android OS"
  },
  {
    "id": 13,
    "name": "iPhones",
    "slug": "iphones",
    "parentId": 7,
    "description": "Apple iPhone devices"
  },
  {
    "id": 14,
    "name": "Office Chairs",
    "slug": "office-chairs",
    "parentId": 9,
    "description": "Ergonomic chairs for office use"
  },
  {
    "id": 15,
    "name": "Clothing",
    "slug": "clothing",
    "parentId": null,
    "description": "Apparel and fashion items"
  },
  {
    "id": 16,
    "name": "Men's Clothing",
    "slug": "mens-clothing",
    "parentId": 15,
    "description": "Clothing items for men"
  },
  {
    "id": 17,
    "name": "Women's Clothing",
    "slug": "womens-clothing",
    "parentId": 15,
    "description": "Clothing items for women"
  }
]
```

### Expected Output Format
Transform the flat structure into a nested category tree:

```json
[
  {
    "id": 1,
    "name": "Electronics",
    "slug": "electronics",
    "description": "Electronic devices and gadgets",
    "children": [
      {
        "id": 2,
        "name": "Computers & Laptops",
        "slug": "computers-laptops",
        "description": "Desktop computers, laptops, and accessories",
        "children": [
          {
            "id": 5,
            "name": "Laptops",
            "slug": "laptops",
            "description": "Portable computers and notebooks",
            "children": [
              {
                "id": 10,
                "name": "Gaming Laptops",
                "slug": "gaming-laptops",
                "description": "High-performance laptops for gaming",
                "children": []
              },
              {
                "id": 11,
                "name": "Business Laptops",
                "slug": "business-laptops",
                "description": "Professional laptops for business use",
                "children": []
              }
            ]
          },
          {
            "id": 6,
            "name": "Desktop Computers",
            "slug": "desktop-computers",
            "description": "Desktop PCs and workstations",
            "children": []
          }
        ]
      },
      {
        "id": 3,
        "name": "Mobile Phones",
        "slug": "mobile-phones",
        "description": "Smartphones and mobile accessories",
        "children": [
          {
            "id": 7,
            "name": "Smartphones",
            "slug": "smartphones",
            "description": "Mobile phones with advanced features",
            "children": [
              {
                "id": 12,
                "name": "Android Phones",
                "slug": "android-phones",
                "description": "Smartphones running Android OS",
                "children": []
              },
              {
                "id": 13,
                "name": "iPhones",
                "slug": "iphones",
                "description": "Apple iPhone devices",
                "children": []
              }
            ]
          },
          {
            "id": 8,
            "name": "Phone Accessories",
            "slug": "phone-accessories",
            "description": "Cases, chargers, and mobile accessories",
            "children": []
          }
        ]
      }
    ]
  },
  {
    "id": 4,
    "name": "Home & Garden",
    "slug": "home-garden",
    "description": "Home improvement and gardening supplies",
    "children": [
      {
        "id": 9,
        "name": "Furniture",
        "slug": "furniture",
        "description": "Home and office furniture",
        "children": [
          {
            "id": 14,
            "name": "Office Chairs",
            "slug": "office-chairs",
            "description": "Ergonomic chairs for office use",
            "children": []
          }
        ]
      }
    ]
  },
  {
    "id": 15,
    "name": "Clothing",
    "slug": "clothing",
    "description": "Apparel and fashion items",
    "children": [
      {
        "id": 16,
        "name": "Men's Clothing",
        "slug": "mens-clothing",
        "description": "Clothing items for men",
        "children": []
      },
      {
        "id": 17,
        "name": "Women's Clothing",
        "slug": "womens-clothing",
        "description": "Clothing items for women",
        "children": []
      }
    ]
  }
]
```

### Requirements
1. **Time limit**: 30-45 minutes
2. **Language**: Any (JavaScript, Python, Java, C#, etc.)

### Bonus Points
- Handle orphaned categories (categories with invalid parentId)
- Sort children alphabetically by name
- Add depth level to each category

### Real-World Context
This pattern is commonly used in:
- E-commerce product categorization
- Content management system menus
- File system hierarchies
- Organizational department structures
- Navigation menu systems
