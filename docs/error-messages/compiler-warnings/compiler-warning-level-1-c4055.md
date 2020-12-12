---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4055'
title: Derleyici Uyarısı (düzey 1) C4055
ms.date: 11/04/2016
f1_keywords:
- C4055
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: 0bb324b096623c8a5118999706f6f3d32d38e67a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267683"
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
