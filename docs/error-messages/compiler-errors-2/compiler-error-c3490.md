---
title: Derleyici hatası C3490
ms.date: 11/04/2016
f1_keywords:
- C3490
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
ms.openlocfilehash: ea7341b9c587a764c7366fa7b7c89e4fc67bc7d8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230863"
---
# <a name="compiler-error-c3490"></a>Derleyici hatası C3490

' var ' değiştirilemez çünkü bir const nesnesi üzerinden erişildi

Bir yöntemde belirtilen lambda ifadesi, **`const`** kesilebilir üye verilerini değiştiremez.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- **`const`** Yöntem bildirimindeki değiştiriciyi kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir yöntemde üye değişkenini değiştirdiği için C3490 oluşturur `_i` **`const`** :

```cpp
// C3490a.cpp
// compile with: /c

class C
{
   void f() const
   {
      auto x = [=]() { _i = 20; }; // C3490
   }

   int _i;
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, **`const`** yöntem bildiriminden değiştiriciyi kaldırarak C3490 'i çözer:

```cpp
// C3490b.cpp
// compile with: /c

class C
{
   void f()
   {
      auto x = [=]() { _i = 20; };
   }

   int _i;
};
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
