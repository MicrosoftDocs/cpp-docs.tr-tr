---
title: Derleyici Hatası C2584
ms.date: 11/04/2016
f1_keywords:
- C2584
helpviewer_keywords:
- C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
ms.openlocfilehash: b61ad65555b5d5232468206f6170223c5f160a34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360482"
---
# <a name="compiler-error-c2584"></a>Derleyici Hatası C2584

'Class': doğrudan temel 'Base2' erişilemez; zaten bir 'Base1' tabanı

`Class` doğrudan zaten türetilen `Base1`. `Base2` Ayrıca türetildiği `Base1`. `Class` öğesinden türetilemiyor `Base2` , (dolaylı olarak) dan devralan anlamına gelir çünkü `Base1` yeniden değil yasal çünkü `Base1` zaten bir doğrudan temel sınıftır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2584 oluşturur.

```
// C2584.cpp
// compile with: /c
struct A1 {
   virtual int MyFunction();
};

struct A2 {
    virtual int MyFunction();
};

struct B1: public virtual A1, virtual A2 {
    virtual int MyFunction();
};

struct B2: public virtual A2, virtual A1 {
    virtual int MyFunction();
};

struct C: virtual B1, B2 {
    virtual int MyFunction();
};

struct Z : virtual B2, virtual C {   // C2584
// try the following line insted
// struct Z : virtual C {
    virtual int MyFunction();
};
```