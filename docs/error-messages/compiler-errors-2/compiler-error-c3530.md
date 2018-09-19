---
title: Derleyici Hatası C3530 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3530
dev_langs:
- C++
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5866e2ea44b84f3afeb0cef8423abc28f8e056ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094799"
---
# <a name="compiler-error-c3530"></a>Derleyici Hatası C3530

'auto' herhangi başka bir tür tanımlayıcısı ile birleştirilemez

Bir tür tanımlayıcısı ile kullanılan `auto` anahtar sözcüğü.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Bir tür belirleyiciye kullanan bir Değişken bildiriminde kullanmayın `auto` anahtar sözcüğü.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çünkü C3530 verir değişkeni `x` ikisiyle bildirilen `auto` anahtar sözcüğü ile tür `int`, ve örnek ile derlenmiş **/Zc:auto**.

```
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)