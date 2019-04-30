---
title: Derleyici Hatası C2528
ms.date: 11/04/2016
f1_keywords:
- C2528
helpviewer_keywords:
- C2528
ms.assetid: 2ea9d583-67a8-4b16-b35f-a50eeffc03c4
ms.openlocfilehash: 890dae7aa34103bde0168f1933bb42343d84100b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408595"
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