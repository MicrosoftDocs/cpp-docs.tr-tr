---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4526'
title: Derleyici Uyarısı (düzey 1) C4526
ms.date: 11/04/2016
f1_keywords:
- C4526
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
ms.openlocfilehash: 13eddea0fcf82686333fe51d253c3b24552e18c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294827"
---
# <a name="compiler-warning-level-1-c4526"></a>Derleyici Uyarısı (düzey 1) C4526

' function ': statik üye işlevi sanal işlevi geçersiz kılamaz ' Virtual function'override yoksayıldı, sanal işlev gizlenecek

Statik üye işlevi, üye işlevini hem sanal hem de statik hale getiren sanal işlevi geçersiz kılma ölçütlerini karşılar.

Aşağıdaki kod C4526 oluşturur:

```cpp
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

Aşağıdakiler olası düzeltmelerdir:

- İşlev, temel sınıf sanal işlevini geçersiz kılmak için tasarlandıysa, statik belirleyicisi kaldırın.

- İşlevin statik üye işlevi olması amaçlandıysa, temel sınıf sanal işleviyle çakışmayacak şekilde yeniden adlandırın.
