---
title: Derleyici Hatası C2528
ms.date: 11/04/2016
f1_keywords:
- C2528
helpviewer_keywords:
- C2528
ms.assetid: 2ea9d583-67a8-4b16-b35f-a50eeffc03c4
ms.openlocfilehash: 890dae7aa34103bde0168f1933bb42343d84100b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601753"
---
# <a name="compiler-error-c2528"></a>Derleyici Hatası C2528

'name': başvuruya yönelik işaretçi geçersizdir

Bir işaretçi bir başvuruya bildiremezsiniz. Değişkeni bir işaretçiye bildirmeden önce başvuru.

Aşağıdaki örnek, C2528 oluşturur:

```
// C2528.cpp
int i;
int &ir = i;
int & (*irptr) = ir;    // C2528
```