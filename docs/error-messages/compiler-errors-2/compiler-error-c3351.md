---
title: Derleyici Hatası C3351 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3351
dev_langs:
- C++
helpviewer_keywords:
- C3351
ms.assetid: c021bbbe-1067-4f51-af4f-940d2b792eb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31ab5843e6dec00755f3b4d671487da9eb87c5b7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085348"
---
# <a name="compiler-error-c3351"></a>Derleyici Hatası C3351

'object': temsilci Oluşturucu: ikinci bağımsız değişkeni, bir statik üye işlevini ya da Genel işlevin adresi olmalıdır

Derleyiciye bildirilen bir işlevi adresi beklenen `static`.

Aşağıdaki örnek, C3351 oluşturur:

```
// C3351a.cpp
// compile with: /clr
delegate int D(int, int);

ref class C {
public:
   int mf(int, int) {
      return 1;
   }

   static int mf2(int, int) {
      return 1;
   }
};

int main() {
   System::Delegate ^pD = gcnew D(nullptr, &C::mf);   // C3351
   System::Delegate ^pD2 = gcnew D(&C::mf2);
}
```
