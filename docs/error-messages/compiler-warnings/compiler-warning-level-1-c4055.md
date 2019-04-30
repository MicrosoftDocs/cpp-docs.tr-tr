---
title: Derleyici Uyarısı (düzey 1) C4052
ms.date: 11/04/2016
f1_keywords:
- C4055
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: e9fcb4356d993d86b622fd49c4a75d587554f7c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388611"
---
# <a name="compiler-warning-level-1-c4055"></a>Derleyici Uyarısı (düzey 1) C4055

> '*dönüştürme*':'veri işaretçisinden '*type1*'için işlev işaretçisi'*type2*'

## <a name="remarks"></a>Açıklamalar

**Eski:** Bu uyarı, Visual Studio 2017 ve sonraki sürümler tarafından oluşturulmaz.

Veri işaretçisine (büyük olasılıkla hatalı) bir işlev işaretçisi türüne dönüştürülür. Düzey 1 uyarısı /Za altında ve düzey 4 uyarısı /Ze altındaki budur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4055 oluşturur:

```C
// C4055.c
// compile with: /Za /W1 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
   return (PFUNC)pi;   // C4055
}
```

/Ze düzey 4 uyarısı budur.

```C
// C4055b.c
// compile with: /W4 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
return (PFUNC)pi;   // C4055
}
```
