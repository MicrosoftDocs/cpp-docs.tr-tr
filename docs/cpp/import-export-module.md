---
title: Modül, içeri aktarma, dışarı aktarma
ms.date: 07/15/2019
f1_keywords:
- module_cpp
- import_cpp
- export_cpp
helpviewer_keywords:
- modules [C++]
- modules [C++], import
- modules [C++], export
description: Belirtilen modülde tanımlanan türlere ve işlevlere erişmek için import ifadesini kullanın.
ms.openlocfilehash: fbb9c45ec816c859edb4df38ad67dc7778247e87
ms.sourcegitcommit: 7b039b5f32f6c59be6c6bb1cffafd69c3bfadd35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68537766"
---
# <a name="module-import-export"></a>Modül, içeri aktarma, dışarı aktarma

**Modül**, **içeri aktar**ve **dışarı aktar** anahtar sözcükleri `/experimental:modules` c++ 20 ' de mevcuttur ve ile `/std:c++latest`birlikte derleyici anahtarını gerektirir. Daha fazla bilgi için bkz. [içindeki C++modüllere genel bakış ](modules-cpp.md).

## <a name="module"></a>modül

Dosya içeriğinin adlandırılmış modüle ait olduğunu belirtmek için modül uygulama dosyasının başındaki **module** ifadesini kullanın. 

```cpp
module ModuleA;
```

## <a name="export"></a>dışarı aktar

Modülün birincil arabirim dosyasında, **. IXX**uzantısı olması gereken **dışa aktarma modülü** ifadesini kullanın:

```cpp
export module ModuleA;
```

Bir arabirim dosyasında, ortak arabirimin parçası olması amaçlanan adlarda **dışarı aktarma** değiştiricisini kullanın:

```cpp
// ModuleA.ixx

export module ModuleA;

namespace Bar
{
   export int f();
   export double d();
   double internal_f(); // not exported
}
```

Dışa aktarılmamış adlar, modülünü içeri aktaran koda görünmez:

```cpp
//MyProgram.cpp

import module ModuleA;

void main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

**Export** anahtar sözcüğü bir modül uygulama dosyasında görünmeyebilir. **Dışarı aktarma** değiştiricisi bir ad alanı adına uygulandığında, ad alanındaki tüm adlar dışarı aktarılabilir.

## <a name="import"></a>içeri aktar

Modülün adlarını programınızda görünür hale getirmek için **import** ifadesini kullanın. İmport ifadesinin modül ifadesinden sonra ve herhangi bir #include yönergelerinden sonra, ancak dosyadaki herhangi bir bildirime geçmeden önce görünmesi gerekir.

```cpp
module ModuleA;

#include "custom-lib.h"
import std.core;
import std.regex;
import ModuleB;

// begin declarations here:
template <class T>
class Baz
{...};
```

## <a name="see-also"></a>Ayrıca Bkz.
[İçindeki modüllere genel bakışC++](modules-cpp.md)
