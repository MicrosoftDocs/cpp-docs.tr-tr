---
title: Derleyici Hatası C3539 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3539
dev_langs:
- C++
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b2f78b69e00290dcc283e3fc340d25a4a071776
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091887"
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

## <a name="see-also"></a>Ayrıca Bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)