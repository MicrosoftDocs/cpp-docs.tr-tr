---
title: Derleyici Hatası C3491
ms.date: 11/04/2016
f1_keywords:
- C3491
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
ms.openlocfilehash: d0440e05970c344da22d3322bcb587714b41614d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537923"
---
# <a name="compiler-error-c3491"></a>Derleyici Hatası C3491

'var': değişemeyen bir lambda içinde bir değere göre yakalama değiştirilemez

Değişemeyen bir lambda ifadesi değere göre yakalanan bir değişkenin değerini değiştiremezsiniz.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- İle lambda ifadesi bildirir `mutable` anahtar sözcüğü, veya

- Değişkeni, lambda ifadesinin yakalama listesine başvuruya göre geçirin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3491 oluşturur, yakalama değişkeni değişemeyen bir lambda ifadesinin gövdesinin değiştirir çünkü `m`:

```
// C3491a.cpp

int main()
{
   int m = 55;
   [m](int n) { m = n; }(99); // C3491
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, lambda ifadesi ile bildirerek C3491 çözümler `mutable` anahtar sözcüğü:

```
// C3491b.cpp

int main()
{
   int m = 55;
   [m](int n) mutable { m = n; }(99);
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)