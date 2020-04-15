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
description: Belirtilen modülde tanımlanan tür ve işlevlere erişmek ve bunları yayınlamak için alma ve dışa aktarma bildirimlerini kullanın.
ms.openlocfilehash: a765e9a406660d3c945ef3d70754178b0648458c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374108"
---
# <a name="module-import-export"></a>modül, içeri aktarma, dışarı aktarma

**Modül**, **ithalat**, ve **ihracat** bildirimleri C++20 mevcuttur ve [/ std:c++ son](../build/reference/std-specify-language-standard-version.md)ile birlikte [/experimental:module](../build/reference/experimental-module.md) derleyici anahtarı gerektirir. Daha fazla bilgi için [C++ modüllerine genel bakış](modules-cpp.md)bölümüne bakın.

## <a name="module"></a>modül

Dosya içeriğinin adlandırılmış modüle ait olduğunu belirtmek için modül uygulama dosyasının başına bir **modül** bildirimi yerleştirin.

```cpp
module ModuleA;
```

## <a name="export"></a>dışarı aktar

Modülün uzantısı **.ixx**olması gereken birincil arabirim dosyası için bir **dışa aktarma modülü** bildirimi kullanın:

```cpp
export module ModuleA;
```

Arabirim dosyasında, ortak arabirimin bir parçası olması amaçlanan adlarda **dışa** aktarma değiştiriciyi kullanın:

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

Dışa aktarılmaz adlar modülü içeri aktaran kodiçin görünmez:

```cpp
//MyProgram.cpp

import module ModuleA;

int main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

**Dışa aktarma** anahtar sözcüğü bir modül uygulama dosyasında görünmeyebilir. **Dışa aktarma** bir ad alanı adına uygulandığında, ad alanındaki tüm adlar dışa aktarılır.

## <a name="import"></a>içeri aktar

Bir modülün adlarını programınızda görünür hale getirmek için **bir alma** bildirimi kullanın. İthalat beyannamesi, modül bildiriminden sonra ve #include yönergelerinden sonra, ancak dosyadaki bildirimlerden önce görünmelidir.

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

Hem **içe aktarma** hem de **modül,** yalnızca mantıksal bir satırın başında göründüklerinde anahtar kelime olarak değerlendirilir:

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

Microsoft C++'da, belirteçleri **içe aktarma** ve **modül** her zaman tanımlayıcılar ve makroya bağımsız değişken olarak kullanıldığında asla anahtar kelimeler değildir.

### <a name="example"></a>Örnek

```cpp
#define foo(…) __VA_ARGS__
foo(
import // Always an identifier, never a keyword
)
```

**Microsoft'a Özel Son**

## <a name="see-also"></a>Ayrıca Bkz.

[C++ içindeki modüllere genel bakış](modules-cpp.md)
