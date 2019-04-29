---
title: Derleyici Hatası C2110
ms.date: 11/04/2016
f1_keywords:
- C2110
helpviewer_keywords:
- C2110
ms.assetid: 48fd76ed-90d6-4a60-9c7b-f6ce9355b4ca
ms.openlocfilehash: b20e68ec032abdfae9afb1c94fed064010275149
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364434"
---
# <a name="compiler-error-c2110"></a>Derleyici Hatası C2110

'+': iki işaretçi toplanamaz

Artı kullanarak iki işaretçi değerler eklemek için bir girişimde bulunuldu ( `+` ) işleci.

Aşağıdaki örnek, C2110 oluşturur:

```
// C2110.cpp
int main() {
   int a = 0;
   int *pa;
   int *pb;
   a = pa + pb;   // C2110
}
```