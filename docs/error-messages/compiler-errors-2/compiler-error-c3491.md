---
title: Derleyici Hatası C3491 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3491
dev_langs:
- C++
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 64d7b2e4bd602a53afeba2f77293c31bb28902d3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068773"
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