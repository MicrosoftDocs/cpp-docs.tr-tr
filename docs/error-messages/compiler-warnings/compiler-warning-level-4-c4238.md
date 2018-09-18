---
title: Derleyici Uyarısı (düzey 4) C4238 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4238
dev_langs:
- C++
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f4d5f358d08f81e6b8097140ad47d54f4b3b3fed
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057034"
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