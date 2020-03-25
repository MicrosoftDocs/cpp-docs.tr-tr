---
title: İşlev Satır İçi Kullanım Sorunları
ms.date: 11/04/2016
helpviewer_keywords:
- /Ob1 C++ compiler option
- inline functions, problems
- -Ob1 C++ compiler option
- /Ob2 C++ compiler option
- -Ob2 C++ compiler option
- function inlining problems
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
ms.openlocfilehash: cb4653bd2f03683b9abad1eea0e9ffa88222090e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80184248"
---
# <a name="function-inlining-problems"></a>İşlev Satır İçi Kullanım Sorunları

İşlev satır içi kullanıyorsanız, şunları yapmanız gerekir:

- Satır içi işlevlerin dahil ettiğiniz başlık dosyasında uygulanıp uygulanmamalıdır.

- Üst bilgi dosyasında giriş açık.

```cpp
// LNK2019_function_inline.cpp
// compile with: /c
// post-build command: lib LNK2019_function_inline.obj
#include <stdio.h>
struct _load_config_used {
   void Test();
   void Test2() { printf("in Test2\n"); }
};

void _load_config_used::Test() { printf("in Test\n"); }
```

ardından,

```cpp
// LNK2019_function_inline_2.cpp
// compile with: LNK2019_function_inline.lib
struct _load_config_used {
   void Test();
   void Test2();
};

int main() {
   _load_config_used x;
   x.Test();
   x.Test2();   // LNK2019
}
```

`#pragma inline_depth` derleyici yönergesini kullanıyorsanız, 2 veya daha büyük bir değer ayarlamış olduğunuzdan emin olun. Sıfır değeri satır içine alınır. Ayrıca, **/OB1** veya **/Ob2** derleyici seçeneklerini kullandığınızdan emin olun.

Farklı modüllerde satır içi ve satır içi derleme seçeneklerini karıştırma bazen soruna neden olabilir. Bir C++ kitaplık, ([/OB1](../../build/reference/ob-inline-function-expansion.md) veya [/Ob2](../../build/reference/ob-inline-function-expansion.md)) işleviyle birlikte oluşturulduysa, ancak işlevleri açıklayan ilgili üstbilgi dosyası satır içine alınır (hiçbir seçenek yoksa), LNK2001 hatasıyla karşılaşacaktır. İşlevler, üstbilgi dosyasındaki koda satır içine alınmaz, ancak kitaplık dosyasında olmadıklarından başvuruyu çözecek bir adres yoktur.

Benzer şekilde, işlev ıntıl kullanan bir proje henüz, başlık dosyası yerine bir. cpp dosyasındaki işlevleri tanımlar LNK2019 de alır. Üst bilgi dosyası, uygun kabul edilen her yerde dahil edilir, ancak işlevler yalnızca. cpp dosyası derleyicide geçtiğinde satır içine alınır; Bu nedenle, bağlayıcı, diğer modüllerde kullanıldığında, işlevleri çözümlenmemiş dışlar olarak görür.

```cpp
// LNK2019_FIP.h
struct testclass {
   void PublicStatMemFunc1(void);
};
```

ardından,

```cpp
// LNK2019_FIP.cpp
// compile with: /c
#include "LNK2019_FIP.h"
inline void testclass::PublicStatMemFunc1(void) {}
```

ardından,

```cpp
// LNK2019_FIP_2.cpp
// compile with: LNK2019_FIP.cpp
// LNK2019 expected
#include "LNK2019_FIP.h"
int main() {
   testclass testclsObject;

   // module cannot see the implementation of PublicStatMemFunc1
   testclsObject.PublicStatMemFunc1();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları Hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
