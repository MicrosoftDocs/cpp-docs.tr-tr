---
title: Derleyici hatası C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: 85381b237480b86b59c33f02601a1b9dc644a5a4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761536"
---
# <a name="compiler-error-c3539"></a>Derleyici hatası C3539

' Type ': bir şablon bağımsız değişkeni ' Auto ' içeren bir tür olamaz

Belirtilen şablon bağımsız değişkeni türü `auto` anahtar sözcüğünün kullanımını içeremez.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. `auto` anahtar sözcüğüyle şablon bağımsız değişkenini belirtmeyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3539 verir.

```cpp
// C3539.cpp
// Compile with /Zc:auto
template<class T> class C{};
int main()
{
   C<auto> c;   // C3539
   return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)
