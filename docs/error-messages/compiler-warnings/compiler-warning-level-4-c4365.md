---
title: Derleyici Uyarısı (düzey 4) C4365 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4365
dev_langs:
- C++
helpviewer_keywords:
- C4365
ms.assetid: af4b4191-bdfd-4dbb-8229-3ba4405df257
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8188e3fc861573025a4855102e3ced14d3136fb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079706"
---
# <a name="compiler-warning-level-4-c4365"></a>Derleyici Uyarısı (düzey 4) C4365

'action': 'type_1' öğesinden 'type_2', imzalı/imzasız uyuşmazlığı öğesine dönüştürme

Örneğin, işaretsiz bir değere bir imzalı değerine dönüştürmek çalıştı.

Varsayılan olarak C4365 kapalıdır.  Daha fazla bilgi için [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4365 oluşturur.

```
// C4365.cpp
// compile with: /W4
#pragma warning(default:4365)

int f(int) { return 0; }
void Test(size_t i) {}

int main() {
   unsigned int n = 10;
   int o = 10;
   n++;
   f(n);   // C4365
   f(o);   // OK

   Test( -19 );   // C4365
}
```