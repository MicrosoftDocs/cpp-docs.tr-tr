---
title: Derleyici Uyarısı (düzey 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: 982457ded987f6aee4f2891bbb7d9103b830cc99
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541785"
---
# <a name="compiler-warning-level-4-c4238"></a>Derleyici Uyarısı (düzey 4) C4238

Standart olmayan uzantı kullanıldı: sınıf rvalue değeri lvalue olarak kullanıldı

Visual C++'ın önceki sürümleriyle uyumluluk için, Microsoft uzantıları ( **/ze**), adresini örtük veya açık olarak alan bir bağlamda bir rvalue olarak bir sınıf türü kullanmanıza imkan sağlar. Aşağıdaki örnekte olduğu gibi bazı durumlarda, bu tehlikeli olabilir.

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