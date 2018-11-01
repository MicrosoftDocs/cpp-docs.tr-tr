---
title: Derleyici Uyarısı (düzey 1) C4508
ms.date: 11/04/2016
f1_keywords:
- C4508
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
ms.openlocfilehash: c96db3d4bd1124c96b22363531b7739d0757b613
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624022"
---
# <a name="compiler-warning-level-1-c4508"></a>Derleyici Uyarısı (düzey 1) C4508

'function': işlev bir değer; döndürmelidir 'void' dönüş türü varsayıldı

İşlevi, belirtilen hiçbir dönüş türüne sahip. Bu durumda, C4430 da harekete ve derleyici (varsayılan değer int'dır) C4430 tarafından bildirilen düzeltme uygular.

Bu uyarıyı çözmek için açıkça işlevlerin dönüş türü bildirin.

Aşağıdaki örnek, C4508 oluşturur:

```
// C4508.cpp
// compile with: /W1 /c
#pragma warning (disable : 4430)
func() {}   // C4508
void func2() {}   // OK
```