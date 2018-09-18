---
title: Derleyici Hatası C3385 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3385
dev_langs:
- C++
helpviewer_keywords:
- C3385
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac6426e32d5cd9a11d80ddce2cf4203d6a1de0e1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038288"
---
# <a name="compiler-error-c3385"></a>Derleyici Hatası C3385

'class::function': bir DllImport özel özniteliği olan bir işlev bir sınıfın örneğini döndüremez

Belirtilen bir .dll dosyası içinde olacak şekilde tanımlanan bir işlev `DllImport` öznitelik, bir sınıfın örneğini döndüremez.

Aşağıdaki örnek, C3385 oluşturur:

```
// C3385.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

struct SomeStruct1 {};

public ref struct Wrap {
   [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ]
   static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385
};
```
