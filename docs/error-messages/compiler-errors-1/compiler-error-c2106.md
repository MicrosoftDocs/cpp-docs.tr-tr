---
title: Derleyici Hatası C2106 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2106
dev_langs:
- C++
helpviewer_keywords:
- C2106
ms.assetid: d5c91a2e-04e4-4770-8478-788b98c52a53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68dd34810041b9d71056d4bb4afc9beadcaffa81
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030748"
---
# <a name="compiler-error-c2106"></a>Derleyici Hatası C2106

'operator': sol işlenen l değeri olmalıdır

İşlecinin sol işleneni bir l değeri olmalıdır.

Aşağıdaki örnek, C2106 oluşturur:

```
// C2106.cpp
int main() {
   int a;
   1 = a;   // C2106
   a = 1;   // OK
}
```