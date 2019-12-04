---
title: Derleyici hatası C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: f23c2a38f8e4d6781af73fb70a25cf4737e2c4e8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758781"
---
# <a name="compiler-error-c2261"></a>Derleyici hatası C2261

' String ': derleme başvurusu geçersiz ve çözümlenemiyor

Değer geçerli değil.

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, bir arkadaş derlemesini belirtmek için kullanılır. Örneğin, bir. dll, bir Friend derlemesi olarak b. dll belirtmek isterse (bir. dll içinde) şunu belirtmeniz gerekir: InternalsVisibleTo ("b"). Çalışma zamanı daha sonra b. dll ' nin bir. dll içindeki her şeye erişmesini sağlar (özel türler hariç).

Arkadaş derlemeleri belirtirken doğru sözdizimi hakkında daha fazla bilgi için bkz. [Friend Assemblies (C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2261 oluşturur.

```cpp
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```
