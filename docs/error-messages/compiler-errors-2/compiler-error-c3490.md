---
title: Derleyici hatası C3490
ms.date: 11/04/2016
f1_keywords:
- C3490
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
ms.openlocfilehash: 940eae39222548ec74bda8ccb38e669748ffa74f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738407"
---
# <a name="compiler-error-c3490"></a>Derleyici hatası C3490

' var ' değiştirilemez çünkü bir const nesnesi üzerinden erişildi

`const` yönteminde belirtilen bir lambda ifadesi, kesilebilir üye verilerini değiştiremez.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Yöntem bildirimindeki `const` değiştiricisini kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `const` yönteminde `_i` üye değişkenini değiştirdiği için C3490 oluşturur:

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

Aşağıdaki örnek, yöntem bildiriminden `const` değiştiricisini kaldırarak C3490 çözer:

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

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
