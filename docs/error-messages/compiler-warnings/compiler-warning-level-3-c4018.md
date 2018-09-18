---
title: Derleyici Uyarısı (Düzey 3) C4018 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4018
dev_langs:
- C++
helpviewer_keywords:
- C4018
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99ca94a47925a64c91077ad5b363e953def186b1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041330"
---
# <a name="compiler-warning-level-3-c4018"></a>Derleyici Uyarısı (Düzey 3) C4018

'expression': imzalı/imzasız uyuşmazlığı

İşaretli ve işaretsiz sayı karşılaştırma derleyici, işaretli değeri işaretsiz dönüştürmek için gereklidir.

Bu uyarı, iki tür imzalı ve imzasız türler test ederken cast düzeltilebilir.

Aşağıdaki örnek, C4018 oluşturur:

```
// C4018.cpp
// compile with: /W3
int main() {
   unsigned int uc = 0;
   int c = 0;
   unsigned int c2 = 0;

   if (uc < c) uc = 0;   // C4018

   // OK
   if (uc == c2) uc = 0;
}
```