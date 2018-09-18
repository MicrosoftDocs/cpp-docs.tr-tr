---
title: Derleyici Uyarısı (düzey 1) C4003 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4003
dev_langs:
- C++
helpviewer_keywords:
- C4003
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b2c6d281f4a5e7f59e0e7a34fb77d2d18b295e7d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029903"
---
# <a name="compiler-warning-level-1-c4003"></a>Derleyici Uyarısı (düzey 1) C4003

Makro 'identifier' yeterli sayıda gerçek parametre

Makro gerçek parametre sayısı Makro tanımında biçimsel parametre sayısını aşıyor. Makro genişletme eksik parametre boş metin yerini alır.

Aşağıdaki örnek, C4003 oluşturur:

```
// C4003.cpp
// compile with: /WX
#define test(a,b) (a+b)

int main()
{
   int a = 1;
   int b = 2;
   a = test(b);   // C4003
   // try..
   a = test(a,b);
}
```