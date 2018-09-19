---
title: Derleyici Hatası C3638 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3638
dev_langs:
- C++
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f1d135dd69155de39b097d59cf139eb47354d4f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107691"
---
# <a name="compiler-error-c3638"></a>Derleyici Hatası C3638

'operator': standart kutulama ve kutudan çıkarma dönüştürme işleçleri yeniden tanımlanamaz

Derleyici örtük olarak kutulama desteklemek için her bir yönetilen sınıf için dönüştürme işleci tanımlar. Bu işleci tanımlanamaz.

Daha fazla bilgi için [örtük kutulama](../../windows/boxing-cpp-component-extensions.md).

Aşağıdaki örnek, C3638 oluşturur:

```
// C3638.cpp
// compile with: /clr
value struct V {
   V(){}
   static operator V^(V);   // C3638
};

int main() {
   V myV;
   V ^ pmyV = myV;   // operator supports implicit boxing
}
```