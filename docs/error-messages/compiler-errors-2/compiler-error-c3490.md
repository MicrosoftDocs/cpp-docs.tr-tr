---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3490'
title: Derleyici hatası C3490
ms.date: 11/04/2016
f1_keywords:
- C3490
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
ms.openlocfilehash: 03896872fd0c683e3011aa7edbacb6a0a01ceaef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113369"
---
# <a name="compiler-error-c3490"></a>Derleyici hatası C3490

' var ' değiştirilemez çünkü bir const nesnesi üzerinden erişildi

Bir yöntemde belirtilen lambda ifadesi, **`const`** kesilebilir üye verilerini değiştiremez.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- **`const`** Yöntem bildirimindeki değiştiriciyi kaldırın.

## <a name="examples"></a>Örnekler

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
