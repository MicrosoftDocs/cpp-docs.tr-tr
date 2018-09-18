---
title: Derleyici Uyarısı (düzey 1) C4526 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4526
dev_langs:
- C++
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed6f2da3252c27b7a84b4d5b73f7e8ba52823dd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118511"
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