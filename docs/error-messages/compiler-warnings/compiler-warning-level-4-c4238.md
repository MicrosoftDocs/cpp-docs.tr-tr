---
title: Derleyici Uyarısı (düzey 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: c5ffa07b06f010d10edc14aa7576bb614aa9dd04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401039"
---
# <a name="compiler-warning-level-4-c4238"></a>Derleyici Uyarısı (düzey 4) C4238

Standart olmayan uzantı kullanıldı: sınıf rvalue değeri lvalue olarak kullanıldı

Visual C++, Microsoft uzantıları önceki sürümleriyle uyumluluk için (**/Ze**), örtük veya açık olarak bir rvalue bir bağlamda, adresini alan gibi bir sınıf türü kullanmanıza izin verir. Aşağıdaki örnekte, gibi bazı durumlarda bu tehlikeli olabilir.

## <a name="example"></a>Örnek

```
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

Bu kullanım ANSI Uyumluluğu altında hataya neden olur ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).