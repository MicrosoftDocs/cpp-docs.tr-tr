---
title: Derleyici Uyarısı (düzey 1) C4555 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4555
dev_langs:
- C++
helpviewer_keywords:
- C4555
ms.assetid: 50b286c1-f7bf-4292-b1fa-baaac9538611
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99adbc75bc6663e9f30950866a0c258be6e10164
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097269"
---
# <a name="compiler-warning-level-1-c4555"></a>Derleyici Uyarısı (düzey 1) C4555

ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu

Bu uyarı bir ifade etkiye sahip olduğunda sizi bilgilendirir.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Örneğin:

```
// C4555.cpp
// compile with: /W1
#pragma warning(default:4555)

void func1()
{
   1;   // C4555
}

void func2()
{
   int x;
   x;   // C4555
}

int main()
{
}
```