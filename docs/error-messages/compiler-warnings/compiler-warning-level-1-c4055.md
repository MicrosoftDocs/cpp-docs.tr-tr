---
title: Derleyici Uyarısı (düzey 1) C4052 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4055
dev_langs:
- C++
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47d7d8891b589dc8205b0d799f88466c1e7d8a59
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4055"></a>Derleyici Uyarısı (düzey 1) C4055

> '*dönüştürme*': veri işaretçi gelen '*type1*'için işlev işaretçisi'*type2*'

## <a name="remarks"></a>Açıklamalar

**Artık kullanılmıyor:** bu uyarı, Visual Studio 2017 ve sonraki sürümler tarafından oluşturulmaz.

Bir veri işaretçisi (büyük olasılıkla yanlış) bir işlev işaretçisi dönüştürün. Düzey 1 uyarısı /Za altında ve düzey 4 uyarı /Ze altında budur.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4055 oluşturur:

```C
// C4055.c
// compile with: /Za /W1 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
   return (PFUNC)pi;   // C4055
}
```

/Ze altında bir düzey 4 uyarı budur.

```C
// C4055b.c
// compile with: /W4 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
return (PFUNC)pi;   // C4055
}
```
