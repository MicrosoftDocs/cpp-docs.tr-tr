---
title: Derleyici Hatası C2110 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2110
dev_langs:
- C++
helpviewer_keywords:
- C2110
ms.assetid: 48fd76ed-90d6-4a60-9c7b-f6ce9355b4ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 749e96748698da9b2c08e805d68e0c2ba333d22f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074909"
---
# <a name="compiler-error-c2110"></a>Derleyici Hatası C2110

'+': iki işaretçi toplanamaz

Artı kullanarak iki işaretçi değerler eklemek için bir girişimde bulunuldu ( `+` ) işleci.

Aşağıdaki örnek, C2110 oluşturur:

```
// C2110.cpp
int main() {
   int a = 0;
   int *pa;
   int *pb;
   a = pa + pb;   // C2110
}
```