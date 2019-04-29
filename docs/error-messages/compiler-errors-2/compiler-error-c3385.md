---
title: Derleyici Hatası C3385
ms.date: 11/04/2016
f1_keywords:
- C3385
helpviewer_keywords:
- C3385
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
ms.openlocfilehash: 0cf8f75588339420c688db6e808a62a9fb0ac15c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328776"
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
