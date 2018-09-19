---
title: Derleyici Hatası C2584 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2584
dev_langs:
- C++
helpviewer_keywords:
- C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0f8c523936473673f3af09400922e2594ed1891
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029435"
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