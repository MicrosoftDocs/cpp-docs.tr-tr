---
title: Derleyici Uyarısı (düzey 4) C4434
ms.date: 11/04/2016
f1_keywords:
- C4434
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
ms.openlocfilehash: fccc37ec531768adbe332ddf9fd91ceb708c7185
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990820"
---
# <a name="compiler-warning-level-4-c4434"></a>Derleyici Uyarısı (düzey 4) C4434

sınıf oluşturucusunun özel erişilebilirliği olmalıdır; özel erişime değiştirme

C4434, derleyicinin statik bir oluşturucunun erişilebilirliğini değiştirdiğini gösterir. Statik oluşturucuların yalnızca ortak dil çalışma zamanı tarafından çağrılması amaçlanan özel erişilebilirliği olmalıdır. Daha fazla bilgi için bkz. [statik oluşturucular](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4434 oluşturur.

```cpp
// C4434.cpp
// compile with: /W4 /c /clr
public ref struct R {
   static R(){}   // C4434
};
```
