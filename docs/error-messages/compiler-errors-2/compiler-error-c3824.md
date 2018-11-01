---
title: Derleyici Hatası C3824
ms.date: 11/04/2016
f1_keywords:
- C3824
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
ms.openlocfilehash: d7c55ede285d027b1a65b33adbf6407df243f068
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635645"
---
# <a name="compiler-error-c3824"></a>Derleyici Hatası C3824

'member': Bu tür bu bağlamda (işlev parametresi, dönüş türü veya bir statik üye) yer alamaz

Sabitleme işaretçileri işlev parametre, dönüş türü olamaz ya da bildirilen `static`.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3824 oluşturur:

```
// C3824a.cpp
// compile with: /clr /c
void func() {
   static pin_ptr<int> a; // C3824
   pin_ptr<int> b; // OK
}
```
