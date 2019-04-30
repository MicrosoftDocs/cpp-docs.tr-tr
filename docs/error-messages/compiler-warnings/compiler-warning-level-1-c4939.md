---
title: Derleyici Uyarısı (düzey 1) C4939
ms.date: 11/04/2016
f1_keywords:
- C4939
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
ms.openlocfilehash: 00526b3dae5035fe96ec1abb50bbdd056ceecfaf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408257"
---
# <a name="compiler-warning-level-1-c4939"></a>Derleyici Uyarısı (düzey 1) C4939

\#pragma vtordisp kullanım dışı ve Visual C++'ın gelecek sürümde kaldırılacak.

[Vtordisp](../../preprocessor/vtordisp.md) pragma Visual C++'ın gelecek sürümde kaldırılacak.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4939 oluşturur.

```
// C4939.cpp
// compile with: /c /W1
#pragma vtordisp(off)   // C4939
```