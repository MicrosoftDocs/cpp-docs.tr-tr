---
title: Derleyici Hatası C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: 2df788efd93fb531822d858ea5aee1722487db81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387054"
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