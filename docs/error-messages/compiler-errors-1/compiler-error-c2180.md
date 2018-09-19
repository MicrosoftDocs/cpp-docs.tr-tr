---
title: Derleyici Hatası C2180 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2180
dev_langs:
- C++
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c74912b92162cbfcada3630ed6a6845b67045d0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084152"
---
# <a name="compiler-error-c2180"></a>Derleyici Hatası C2180

denetleyen ifadenin türü 'type' var

Denetim ifadesi bir `if`, `while`, `for`, veya `do` başvurusuna bir ifade deyimidir `void`. Bu sorunu gidermek için denetleme ifadesiyle üreten değiştirerek bir bir `bool` veya dönüştürülebilir bir tür `bool`.

Aşağıdaki örnek C2180 oluşturur:

```
// C2180.c

int main() {
   while ((void)1)   // C2180
      return 1;
   while (1)         // OK
      return 0;
}
```