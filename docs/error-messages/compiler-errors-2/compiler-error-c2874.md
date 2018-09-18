---
title: Derleyici Hatası C2874 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2874
dev_langs:
- C++
helpviewer_keywords:
- C2874
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da285053507865d88fef31fac485c2a77a918d52
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031099"
---
# <a name="compiler-error-c2874"></a>Derleyici Hatası C2874

'symbol' birden çok bildirimi bildirim kullanımı neden olur

Bildirimi, aynı öğesini iki kez tanımlanmış olması neden olur.

Aşağıdaki örnek, C2874 oluşturur:

```
// C2874.cpp
namespace Z {
   int i;
}

int main() {
   int i;
   using Z::i;   // C2874, i already declared
}
```