---
title: Derleyici hatası C3491
ms.date: 11/04/2016
f1_keywords:
- C3491
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
ms.openlocfilehash: 78f90ee1c44a0d42e529a027b1e7fc90a0da3cdb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738329"
---
# <a name="compiler-error-c3491"></a>Derleyici hatası C3491

' var ': değere göre yakalama, kesilebilir olmayan bir lambda içinde değiştirilemez

Kesilebilir olmayan bir lambda ifadesi, değere göre yakalanan bir değişkenin değerini değiştiremez.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- `mutable` anahtar sözcüğüyle lambda ifadenizi bildirin veya

- Değişkeni lambda ifadesinin yakalama listesine başvuruya göre geçirin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3491 üretir çünkü kesilebilir olmayan bir lambda ifadesinin gövdesi, yakalama değişkenini `m`değiştirir:

```cpp
// C3491a.cpp

int main()
{
   int m = 55;
   [m](int n) { m = n; }(99); // C3491
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, `mutable` anahtar sözcüğüyle lambda ifadesini bildirerek C3491 çözer:

```cpp
// C3491b.cpp

int main()
{
   int m = 55;
   [m](int n) mutable { m = n; }(99);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
