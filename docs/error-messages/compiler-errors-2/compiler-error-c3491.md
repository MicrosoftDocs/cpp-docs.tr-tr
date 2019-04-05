---
title: Derleyici Hatası C3491
ms.date: 11/04/2016
f1_keywords:
- C3491
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
ms.openlocfilehash: 12f50e48fc18fc23d078b6dbc7d21d05efa06d43
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032933"
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

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)