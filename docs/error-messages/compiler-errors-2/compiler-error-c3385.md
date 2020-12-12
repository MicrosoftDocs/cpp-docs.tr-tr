---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3385'
title: Derleyici hatası C3385
ms.date: 11/04/2016
f1_keywords:
- C3385
helpviewer_keywords:
- C3385
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
ms.openlocfilehash: d51659561deb21882532b772455cf1e3636684aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285571"
---
# <a name="compiler-error-c3385"></a>Derleyici hatası C3385

' class:: Function ': DllImport özel özniteliğine sahip bir işlev bir sınıfın örneğini döndüremez

Özniteliği ile belirtilen bir. dll dosyasında olduğu gibi tanımlanan bir işlev `DllImport` bir sınıfın örneğini döndüremez.

Aşağıdaki örnek C3385 oluşturur:

```cpp
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
