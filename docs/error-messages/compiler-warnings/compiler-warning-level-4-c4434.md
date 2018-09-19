---
title: Derleyici Uyarısı (düzey 4) C4434 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4434
dev_langs:
- C++
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec0d9e4cfbed2d2871e35631df918f17a342f653
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025769"
---
# <a name="compiler-warning-level-4-c4434"></a>Derleyici Uyarısı (düzey 4) C4434

bir sınıf oluşturucusu özel erişilebilirliği olmalıdır; özel erişim olarak değiştiriliyor

C4434, derleyici bir statik Oluşturucu erişilebilirliğini değiştiğini gösterir. Bunlar yalnızca ortak dil çalışma zamanı tarafından çağrılacak yöneliktir gibi statik oluşturucular özel erişilebilirliği olmalıdır. Daha fazla bilgi için [statik oluşturucular](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4434 oluşturur.

```
// C4434.cpp
// compile with: /W4 /c /clr
public ref struct R {
   static R(){}   // C4434
};
```