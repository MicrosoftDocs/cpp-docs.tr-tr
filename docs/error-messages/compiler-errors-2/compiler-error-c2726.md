---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2726'
title: Derleyici hatası C2726
ms.date: 11/04/2016
f1_keywords:
- C2726
helpviewer_keywords:
- C2726
ms.assetid: f0191bb7-c175-450b-bf09-a3213db96d09
ms.openlocfilehash: 9318ea0cbf695f1c42253a680143edb7b541d25e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245336"
---
# <a name="compiler-error-c2726"></a>Derleyici hatası C2726

' gcnew ' yalnızca yönetilen veya WinRT türüne sahip bir nesne oluşturmak için kullanılabilir

Atık toplanmış yığında yerel bir türün örneğini oluşturamazsınız.

Aşağıdaki örnek C2726 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2726.cpp
// compile with: /clr
using namespace System;
class U {};
ref class V {};
value class W {};

int main() {
   U* pU = gcnew U;    // C2726
   U* pU2 = new U;   // OK
   V^ p2 = gcnew V;   // OK
   W p3;   // OK

}
```
