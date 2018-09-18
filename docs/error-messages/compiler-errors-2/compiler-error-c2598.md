---
title: Derleyici Hatası C2598 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2598
dev_langs:
- C++
helpviewer_keywords:
- C2598
ms.assetid: 40777c62-39ba-441e-b081-f49f94b43547
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11747df117ea714ea3c4d7ce41e9229c79becc93
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102703"
---
# <a name="compiler-error-c2598"></a>Derleyici Hatası C2598

bağlama belirtimi genel kapsamda olmalıdır

Bağlantı belirticisi, yerel kapsamda bildirilmiş.

Aşağıdaki örnek, C2598 oluşturur:

```
// C2598.cpp
// compile with: /c
void func() {
   extern "C" int func2();   // C2598
}

extern "C" int func( int i );
```