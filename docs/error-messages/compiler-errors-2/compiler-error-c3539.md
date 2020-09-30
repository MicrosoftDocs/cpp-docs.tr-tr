---
title: Derleyici hatası C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: e30ea0713229bfd8da395baef710571f8dfd49e9
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508145"
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

[auto Anahtar Sözcüğü](../../cpp/auto-cpp.md)
