---
title: Derleyici hatası C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: 813da5a2fd79c191df731937e58100d749f8690c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223414"
---
# <a name="compiler-error-c3539"></a>Derleyici hatası C3539

' Type ': bir şablon bağımsız değişkeni ' Auto ' içeren bir tür olamaz

Belirtilen şablon bağımsız değişkeni türü, **`auto`** anahtar sözcüğünün kullanımını içeremez.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Anahtar sözcüğüyle şablon bağımsız değişkenini belirtmeyin **`auto`** .

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
