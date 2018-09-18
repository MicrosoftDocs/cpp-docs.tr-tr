---
title: Derleyici Uyarısı (düzey 4) C4670 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4670
dev_langs:
- C++
helpviewer_keywords:
- C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f1f406442e763175da1bb0220925a1a43d8825d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118264"
---
# <a name="compiler-warning-level-4-c4670"></a>Derleyici Uyarısı (düzey 4) C4670

'identifier': Bu taban sınıfına erişilemez

Belirtilen temel sınıf harekete geçirilmesine bir nesnenin bir **deneyin** bloğu, erişilebilir değil. Bu durum oluşturulursa nesne oluşturulamıyor. Temel sınıfı ile doğru erişim belirticisi devralınır denetleyin.

Aşağıdaki örnek, C4670 oluşturur:

```
// C4670.cpp
// compile with: /EHsc /W4
class A
{
};

class B : /* public */ A
{
} b;   // inherits A with private access by default

int main()
{
    try
    {
       throw b;   // C4670
    }
    catch( B )
    {
    }
}
```