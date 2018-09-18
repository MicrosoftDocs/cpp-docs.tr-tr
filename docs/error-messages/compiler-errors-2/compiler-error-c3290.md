---
title: Derleyici Hatası C3290 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3290
dev_langs:
- C++
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b97818dd6ef7b38bb815e2c0a6345cc056fc45c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058932"
---
# <a name="compiler-error-c3290"></a>Derleyici Hatası C3290

'type': Önemsiz bir özellik başvuru türüne sahip olamaz

Bir özellik yanlış olarak bildirildi. Önemsiz özellik bildirimini, derleyici özelliğini güncelleştirecek bir değişken oluşturur ve bir izleme başvurusu mümkün değil bir sınıftaki değişken.

Bkz: [özelliği](../../windows/property-cpp-component-extensions.md) ve [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3290 oluşturur.

```
// C3290.cpp
// compile with: /clr /c
ref struct R {};

ref struct X {
   R^ mr;

   property R % y;   // C3290
   property R ^ x;   // OK

   // OK
   property R% prop {
      R% get() {
         return *mr;
      }

      void set(R%) {}
   }
};

int main() {
   X x;
   R% xp = x.prop;
}
```