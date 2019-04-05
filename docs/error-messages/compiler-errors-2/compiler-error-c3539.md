---
title: Derleyici Hatası C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: be1051859ebbcbdc22a9b71f8c5adba2e75c4e92
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025186"
---
# <a name="compiler-error-c3539"></a>Derleyici Hatası C3539

'type': bir şablon bağımsız değişkeni 'auto' içeren bir tür olamaz

Belirtilen şablon bağımsız değişken türü bir kullanımını içeremez `auto` anahtar sözcüğü.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Şablon bağımsız değişkeni ile belirtmeyin `auto` anahtar sözcüğü.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3539 verir.

```
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