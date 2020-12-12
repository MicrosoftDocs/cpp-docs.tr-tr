---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3491'
title: Derleyici hatası C3491
ms.date: 11/04/2016
f1_keywords:
- C3491
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
ms.openlocfilehash: 8bd01c47e05d7cf266a22dfc713ae28bffe08e49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315652"
---
# <a name="compiler-error-c3491"></a>Derleyici hatası C3491

' var ': değere göre yakalama, kesilebilir olmayan bir lambda içinde değiştirilemez

Kesilebilir olmayan bir lambda ifadesi, değere göre yakalanan bir değişkenin değerini değiştiremez.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Lambda ifadenizi **`mutable`** anahtar sözcükle bildirin veya

- Değişkeni lambda ifadesinin yakalama listesine başvuruya göre geçirin.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, kesilebilir olmayan bir lambda ifadesinin gövdesi yakalama değişkenini değiştirdiği için C3491 oluşturur `m` :

```cpp
// C3491a.cpp

int main()
{
   int m = 55;
   [m](int n) { m = n; }(99); // C3491
}
```

Aşağıdaki örnek, lambda ifadesini anahtar sözcüğüyle bildirerek C3491 çözer **`mutable`** :

```cpp
// C3491b.cpp

int main()
{
   int m = 55;
   [m](int n) mutable { m = n; }(99);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
