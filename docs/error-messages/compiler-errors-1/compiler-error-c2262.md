---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2262'
title: Derleyici hatası C2262
ms.date: 11/04/2016
f1_keywords:
- C2262
helpviewer_keywords:
- C2262
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
ms.openlocfilehash: ef4cbeeeef9a7df42510dbf4cd021dde2081d294
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134582"
---
# <a name="compiler-error-c2262"></a>Derleyici hatası C2262

' attribute_specifiers ': InternalsVisibleTo bildirimlerinde sürüm, kültür veya işlemci mimarisi belirtilemez

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Öznitelik doğru şekilde belirtilmedi.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2262 oluşturur.

```cpp
// C2262.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262
[assembly: InternalsVisibleTo("assembly_name ")];   // OK
```
