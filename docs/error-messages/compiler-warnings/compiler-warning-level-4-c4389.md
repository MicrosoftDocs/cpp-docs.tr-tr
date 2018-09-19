---
title: Derleyici Uyarısı (düzey 4) C4389 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4389
dev_langs:
- C++
helpviewer_keywords:
- C4389
ms.assetid: fc0e3a8e-f766-437c-b7f1-e61abb2a8765
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68d67ae253926e79b6bc13d339ac303cca767090
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022571"
---
# <a name="compiler-warning-level-4-c4389"></a>Derleyici Uyarısı (düzey 4) C4389

'operator': imzalı/imzasız uyuşmazlığı

İşaretli ve işaretsiz değişkenler bir işlem dahil. Bu, veri kaybına neden olabilir.

Aşağıdaki örnek, C4389 oluşturur:

```
// C4389.cpp
// compile with: /W4
#pragma warning(default: 4389)

int main()
{
   int a = 9;
   unsigned int b = 10;
   if (a == b)   // C4389
      return 0;
   else
      return 0;
};
```