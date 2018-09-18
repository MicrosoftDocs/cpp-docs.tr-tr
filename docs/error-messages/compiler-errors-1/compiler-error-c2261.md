---
title: Derleyici Hatası C2261 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2261
dev_langs:
- C++
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed43dc43fb6ceaf514a8e7452b06eb7bdaf7362
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051652"
---
# <a name="compiler-error-c2261"></a>Derleyici Hatası C2261

'string': derleme başvurusu geçersiz ve çözümlenemiyor

Bir değer geçerli değil.

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> arkadaş derleme belirtmek için kullanılır. Örneğin, bir arkadaş derleme olarak b.dll belirtmek a.dll isterse, (a.dll içinde) belirtmeniz gerekir: InternalsVisibleTo("b"). Çalışma zamanı sonra b.dll her şeyi a.dll (dışında özel türleri) erişim verir.

Arkadaş derlemeleri belirtirken doğru sözdizimi hakkında daha fazla bilgi için bkz. [arkadaş derlemeler (C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2261 oluşturur.

```
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```