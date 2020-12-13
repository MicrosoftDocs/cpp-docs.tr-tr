---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2261'
title: Derleyici hatası C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: c5156a240696f9021613b54cf7013e9372a13b45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134621"
---
# <a name="compiler-error-c2261"></a>Derleyici hatası C2261

' String ': derleme başvurusu geçersiz ve çözümlenemiyor

Değer geçerli değil.

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> bir Friend derlemesini belirtmek için kullanılır. Örneğin, a.dll bir arkadaş derleme olarak b.dll belirtmek isterse, (a.dll): InternalsVisibleTo ("b") belirtin. Çalışma zamanı daha sonra, b.dll a.dll her şeye (özel türler hariç) erişmesine izin verir.

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
