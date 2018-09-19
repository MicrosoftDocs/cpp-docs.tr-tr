---
title: Derleyici Hatası C2053 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2053
dev_langs:
- C++
helpviewer_keywords:
- C2053
ms.assetid: 13324c85-13a8-4996-bd42-a31bfe7ff80f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 711debdfe82db617e7974afbfb75b2116eec0260
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102011"
---
# <a name="compiler-error-c2053"></a>Derleyici Hatası C2053

'identifier': geniş dize uyuşmazlığı

Geniş dize uyumsuz bir türe atanır.

Aşağıdaki örnek, C2053 oluşturur:

```
// C2053.c
int main() {
   char array[] = L"Rika";   // C2053
}
```