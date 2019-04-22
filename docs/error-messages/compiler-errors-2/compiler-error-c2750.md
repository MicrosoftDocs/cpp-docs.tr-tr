---
title: Derleyici Hatası C2750
ms.date: 11/04/2016
f1_keywords:
- C2750
helpviewer_keywords:
- C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
ms.openlocfilehash: 34d19e8e9f51c90c48ec0d429f98bb82e3d829d4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777204"
---
# <a name="compiler-error-c2750"></a>Derleyici Hatası C2750

'type': başvuru türü üzerinde; 'new' kullanılamaz Bunun yerine 'gcnew' kullanın

Örneği atık toplanan yığında yerleştirilmesini neden olan, bir CLR türünün örneğini oluşturmak için kullanmanız gerekir [gcnew](../../extensions/ref-new-gcnew-cpp-component-extensions.md).

Aşağıdaki örnek, C2750 oluşturur:

```
// C2750.cpp
// compile with: /clr
ref struct Y1 {};

int main() {
   Y1 ^ x = new Y1;   // C2750

   // try the following line instead
   Y1 ^ x2 = gcnew Y1;
}
```