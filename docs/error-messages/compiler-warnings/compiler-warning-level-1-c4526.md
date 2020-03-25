---
title: Derleyici Uyarısı (düzey 1) C4526
ms.date: 11/04/2016
f1_keywords:
- C4526
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
ms.openlocfilehash: d4d772f3e505979a6ea5c3e7923fefa621601370
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186510"
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
