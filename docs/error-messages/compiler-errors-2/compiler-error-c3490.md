---
title: Derleyici hatası C3490
ms.date: 11/04/2016
f1_keywords:
- C3490
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
ms.openlocfilehash: 76729f49358e2a05b425730517e88ba14f2909c6
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685730"
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
