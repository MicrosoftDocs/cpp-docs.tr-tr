---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4238'
title: Derleyici Uyarısı (düzey 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: 8999d9ebeb4583256360f6223d4bf51a842fcb01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334878"
---
# <a name="compiler-warning-level-4-c4238"></a>Derleyici Uyarısı (düzey 4) C4238

Standart olmayan uzantı kullanıldı: sınıf rvalue değeri lvalue olarak kullanıldı

Önceki Visual C++ sürümleriyle uyumluluk için, Microsoft uzantıları (**/ze**), bir sınıf türünü örtük olarak, adresini dolaylı veya açık olarak alan bir bağlamda bir rvalue olarak kullanmanıza olanak tanır. Aşağıdaki örnekte olduğu gibi bazı durumlarda, bu tehlikeli olabilir.

## <a name="example"></a>Örnek

```cpp
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

Bu kullanım ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında bir hataya neden olur.
