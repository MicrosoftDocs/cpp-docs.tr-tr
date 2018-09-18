---
title: Derleyici Hatası C2726 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2726
dev_langs:
- C++
helpviewer_keywords:
- C2726
ms.assetid: f0191bb7-c175-450b-bf09-a3213db96d09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e421839e75bcc570578d7c37eecc8ab076321d7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051281"
---
# <a name="compiler-error-c2726"></a>Derleyici Hatası C2726

'gcnew' yalnızca bir nesne oluşturmak için kullanılabilir yönetilen veya WinRT türü

Atık toplanan yığında yerel bir tür örneği oluşturulamıyor.

Aşağıdaki örnek, C2726 oluşturur ve bu sorunun nasıl gösterir:

```
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
