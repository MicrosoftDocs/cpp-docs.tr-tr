---
title: Derleyici Hatası C2262
ms.date: 11/04/2016
f1_keywords:
- C2262
helpviewer_keywords:
- C2262
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
ms.openlocfilehash: 12272c21adac0e326cb8b149b359584197577941
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567069"
---
# <a name="compiler-error-c2262"></a>Derleyici Hatası C2262

'attribute_specifiers': InternalsVisibleTo bildirmelerinde belirtilmiş sürüm, kültür veya işlemci mimarisi olamaz

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Özniteliği düzgün belirtilmedi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2262 oluşturur.

```
// C2262.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262
[assembly: InternalsVisibleTo("assembly_name ")];   // OK
```