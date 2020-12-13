---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2462'
title: Derleyici hatası C2462
ms.date: 11/04/2016
f1_keywords:
- C2462
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
ms.openlocfilehash: f85d8f2e38c38043765b29b6e766c0cbd4fef1fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341821"
---
# <a name="compiler-error-c2462"></a>Derleyici hatası C2462

' tanımlayıcı ': ' New-Expression ' içinde tür tanımlanamaz

İşlecin işlenen alanında bir tür tanımlayamazsınız **`new`** . Tür tanımını ayrı bir deyime koyun.

Aşağıdaki örnek C2462 oluşturur:

```cpp
// C2462.cpp
int main() {
   new struct S { int i; };   // C2462
}
```
