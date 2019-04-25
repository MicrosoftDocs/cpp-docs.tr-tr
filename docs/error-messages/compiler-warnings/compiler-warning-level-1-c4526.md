---
title: Derleyici Uyarısı (düzey 1) C4526
ms.date: 11/04/2016
f1_keywords:
- C4526
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
ms.openlocfilehash: 892e6c37e54a868be48ced35354a1096aa7bf9d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160750"
---
# <a name="compiler-warning-level-1-c4526"></a>Derleyici Uyarısı (düzey 1) C4526

'function': statik üye işlevini sanal işlevini geçersiz kılamaz ' yoksayıldı, sanal function'override sanal işlev gizlenecek

Statik üye işlevini hem sanal hem de statik üye işlevini kılan sanal işlev geçersiz kılmak için ölçütleri karşılar.

Aşağıdaki kod C4526 oluşturur:

```
// C4526.cpp
// compile with: /W1 /c
// C4526 expected
struct myStruct1 {
   virtual void __stdcall func( int ) = 0;
};

struct myStruct2: public myStruct1 {
   static void __stdcall func( int );
};
```

Olası düzeltmeleri şunlardır:

- İşlev temel sınıf sanal işlevi geçersiz kılmak için tasarlanmıştı statik belirteci kaldırın.

- İşlev bir statik üye işlevi olarak kullanılması, temel sınıf sanal işlevi ile çakışmadığından şekilde yeniden adlandırın.