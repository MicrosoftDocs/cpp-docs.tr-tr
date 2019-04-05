---
title: Derleyici Hatası C3538
ms.date: 11/04/2016
f1_keywords:
- C3538
helpviewer_keywords:
- C3538
ms.assetid: ef3698a5-7356-4c62-b9af-5d3a4baed958
ms.openlocfilehash: e8b97c8c6e5d23c406bf2d5831279810e7de0902
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035036"
---
# <a name="compiler-error-c3538"></a>Derleyici Hatası C3538

bir bildirimci listesinde 'auto' her zaman aynı tür olarak çözümlenmelidir

Bir bildirim listesinde bildirilen tüm değişkenleri aynı türe çözümlemeyin.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Emin tüm `auto` listesinde bildirimleri aynı türe türetme.

## <a name="example"></a>Örnek

Aşağıdaki deyimleri C3538 yield. Her deyim her kullanımının ancak birden fazla değişken bildirir `auto` anahtar sözcüğü, aynı türe türetme değil.

```
// C3538.cpp
// Compile with /Zc:auto
// C3538 expected
int main()
{
// Variable x1 is a pointer to char, but y1 is a double.
   auto * x1 = "a", y1 = 3.14;
// Variable c is a char and c1 is char*, but c2, and c3 are pointers to pointers.
   auto c = 'a', *c1 = &c, * c2 = &c1, * c3 = &c2;
// Variable x2 is an int, but y2 is a double and z is a char.
   auto x2(1), y2(0.0), z = 'a';
// Variable a is a pointer to int, but b is a pointer to double.
   auto *a = new auto(1), *b = new auto(2.0);
   return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)