---
title: Derleyici Uyarısı (Düzey 2) C4150 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4150
dev_langs:
- C++
helpviewer_keywords:
- C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d317384d3708679d485ae0a77c6ee9b6622b9c83
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050430"
---
# <a name="compiler-warning-level-2-c4150"></a>Derleyici Uyarısı (Düzey 2) C4150

eksik türe 'type'; işaretçisinin silinmesi hiçbir yok edici çağrılmadı

**Sil** işleci, derleyici bir yok edici bulmanız bildirilmiş ancak tanımlı değil, bir türünü silmek için çağrılır.

Aşağıdaki örnek, C4150 oluşturur:

```
// C4150.cpp
// compile with: /W2
class  IncClass;

void NoDestruct( IncClass* pIncClass )
{
   delete pIncClass;
} // C4150, define class to resolve

int main()
{
}
```