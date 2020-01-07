---
title: modül, içeri aktarma, dışarı aktarma
ms.date: 12/12/2019
f1_keywords:
- module_cpp
- import_cpp
- export_cpp
helpviewer_keywords:
- modules [C++]
- modules [C++], import
- modules [C++], export
description: Belirtilen modülde tanımlanan türlere ve işlevlere erişmek ve bunları yayımlamak için içeri ve dışarı aktarma bildirimleri kullanın.
ms.openlocfilehash: ae28bce8e06840cafa5c92521f6e9a62aa5bfde6
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301463"
---
# <a name="module-import-export"></a>modül, içeri aktarma, dışarı aktarma

**Modül**, **içeri**ve **dışarı aktarma** bildirimleri c++ 20 ' de kullanılabilir ve [/std: C + + latest](../build/reference/std-specify-language-standard-version.md)ile birlikte [/deneysel: Module](../build/reference/experimental-module.md) derleyici anahtarını gerektirir. Daha fazla bilgi için bkz. [içindeki C++modüllere genel bakış ](modules-cpp.md).

## <a name="module"></a>modül

Dosya içeriğinin adlandırılmış modüle ait olduğunu belirtmek için modül uygulama dosyasının başına bir **Modül** bildirimi yerleştirin.

```cpp
module ModuleA;
```

## <a name="export"></a>dışarı aktar

Modülün birincil arabirim dosyası için bir **dışarı aktarma modülü** bildirimi kullanın, bu, uzantısı **. IXX**olmalıdır:

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

**Export** anahtar sözcüğü bir modül uygulama dosyasında görünmeyebilir. Bir ad alanı adına **dışarı aktarma** uygulandığında, ad alanındaki tüm adlar dışarı aktarılabilir.

## <a name="import"></a>içeri aktar

Bir modülün adlarını programınızda görünür hale getirmek için **içeri aktarma** bildirimi kullanın. İçeri aktarma bildirimi, modül bildiriminden sonra ve herhangi bir #include yönergelerinden sonra, ancak dosyadaki herhangi bir bildirime başlamadan önce gelmelidir.

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

## <a name="remarks"></a>Açıklamalar

Hem **içeri aktarma** hem de **Modül** bir mantıksal satırın başlangıcında görüntiklerinde anahtar sözcük olarak değerlendirilir:

```cpp

// OK:
module ;
module module-name
import :
import <
import "
import module-name
export module ;
export module module-name
export import :
export import <
export import "
export import module-name

// Error:
int i; module ;
```

**Microsoft 'a özgü**

Microsoft C++'ta, bir makroya bağımsız değişken olarak kullanıldıkları zaman, her zaman tanımlayıcılardır **ve hiçbir** zaman kelimeleridir **.**

### <a name="example"></a>Örnek

```cpp
#define foo(…) __VA_ARGS__
foo(
import // Always an identifier, never a keyword
)
```

**Son Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[İçindeki modüllere genel bakışC++](modules-cpp.md)
