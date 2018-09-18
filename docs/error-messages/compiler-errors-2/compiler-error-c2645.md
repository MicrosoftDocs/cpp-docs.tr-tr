---
title: Derleyici Hatası C2645 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2645
dev_langs:
- C++
helpviewer_keywords:
- C2645
ms.assetid: 6609c2fa-c3b2-4a6b-8e8d-58fb52f67175
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ada345b79c061c71bc716bf7baf96116444bcc7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076833"
---
# <a name="compiler-error-c2645"></a>Derleyici Hatası C2645

üye işaretçisinin tam adı yok (bulundu ':: *')

Bir üye işaretçisi bildirimi bir sınıf belirtmiyor.

Aşağıdaki örnek, C2645 oluşturur:

```
// C2645.cpp
class A {};
int main() {
   int B::* bp;   // C2645 B not defined
   int A::* ap;   // OK
}
```