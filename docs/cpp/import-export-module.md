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
ms.openlocfilehash: 5be1618d7e64f6887cf78bd863d428d6710eaf7e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87187198"
---
# <a name="module-import-export"></a>modül, içeri aktarma, dışarı aktarma

**Modül**, **içeri aktar**ve **`export`** Bildirimler c++ 20 ' de kullanılabilir ve [/std: C + + latest](../build/reference/std-specify-language-standard-version.md)ile birlikte [/deneysel: Module](../build/reference/experimental-module.md) derleyici anahtarını gerektirir. Daha fazla bilgi için bkz. [C++ ' da modüllere genel bakış](modules-cpp.md).

## <a name="module"></a>modül

Dosya içeriğinin adlandırılmış modüle ait olduğunu belirtmek için modül uygulama dosyasının başına bir **Modül** bildirimi yerleştirin.

```cpp
module ModuleA;
```

## <a name="export"></a>dışarı aktarma

Modülün birincil arabirim dosyası için bir **dışarı aktarma modülü** bildirimi kullanın, bu, uzantısı **. IXX**olmalıdır:

```cpp
export module ModuleA;
```

Bir arabirim dosyasında, **`export`** genel arabirimin parçası olmak üzere tasarlanan adlarla ilgili değiştirici kullanın:

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

int main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

**`export`** Anahtar sözcüğü bir modül uygulama dosyasında görünmeyebilir. **`export`** Bir ad alanı adına uygulandığında, ad alanındaki tüm adlar verilir.

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

**Microsoft'a Özgü**

Microsoft C++ ' da, bir makroya bağımsız değişken olarak kullanıldıkları zaman, her zaman tanımlayıcılardır **ve hiçbir** zaman kelimelerdir **.**

### <a name="example"></a>Örnek

```cpp
#define foo(…) __VA_ARGS__
foo(
import // Always an identifier, never a keyword
)
```

**Son Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[C++ içindeki modüllere genel bakış](modules-cpp.md)
