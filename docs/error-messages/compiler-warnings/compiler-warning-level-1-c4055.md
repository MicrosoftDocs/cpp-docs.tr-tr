---
title: Derleyici Uyarısı (düzey 1) C4055
ms.date: 11/04/2016
f1_keywords:
- C4055
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: 47883f60c3205125a8ee88b804c1d622b3ba0b41
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041035"
---
# <a name="compiler-warning-level-1-c4055"></a>Derleyici Uyarısı (düzey 1) C4055

> '*dönüştürme*': '*Type1*' veri işaretçisinden '*type2*' işlev işaretçisine

## <a name="remarks"></a>Açıklamalar

**Kullanımdan kalktı:** Bu uyarı, Visual Studio 2017 ve sonraki sürümleri tarafından oluşturulmaz.

Bir veri işaretçisi, bir işlev işaretçisine (büyük olasılıkla yanlış) dönüştürüldü. Bu,/za altında bir düzey 1 uyarıdır ve/Zein altında düzey 4 uyarısı olur.

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

/Ze altında bu 4. düzey bir uyarıdır.

```C
// C4055b.c
// compile with: /W4 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
return (PFUNC)pi;   // C4055
}
```
