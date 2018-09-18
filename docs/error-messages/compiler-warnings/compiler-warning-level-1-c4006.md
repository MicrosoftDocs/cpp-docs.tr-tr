---
title: Derleyici Uyarısı (düzey 1) C4006 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4006
dev_langs:
- C++
helpviewer_keywords:
- C4006
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35987244498b95dfee6f285f100237c3d3a361ea
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037058"
---
# <a name="compiler-warning-level-1-c4006"></a>Derleyici Uyarısı (düzey 1) C4006

\#undef bir tanımlayıcı bekleniyor

`#undef` Yönergesi, bir tanımlayıcı tanımsız belirtmedi. Yönergeyi göz ardı edilir. Uyarıyı çözmek için bir tanımlayıcı belirttiğinizden emin olun. Aşağıdaki örnek, C4006 oluşturur:

```
// C4006.cpp
// compile with: /W1
#undef   // C4006

// try..
// #undef TEST

int main() {
}
```