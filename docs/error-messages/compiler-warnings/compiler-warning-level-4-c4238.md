---
title: Derleyici Uyarısı (düzey 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: cc913a4f92963437347fbc708eca03c25ab9d403
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991469"
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
