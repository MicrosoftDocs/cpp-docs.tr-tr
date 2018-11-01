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
ms.openlocfilehash: e8d2a97e4d887b914d15871ce1679c95cc3cda97
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452734"
---
# <a name="function-inlining-problems"></a>İşlev Satır İçi Kullanım Sorunları

İşlev satır içi kullanım kullanıyorsanız yapmanız gerekenler şunlardır:

- Eklediğiniz üstbilgi dosyasında uygulanan satır içi işlevleri vardır.

- Sahip satır içi kullanım ON üstbilgi dosyasında açık.

```
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

Ardından,

```
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

Kullanıyorsanız `#pragma inline_depth` derleyici yönergesi emin 2 veya daha büyük kümesi değerine sahip. Sıfır değeri kapanır satır içi kullanım. Ayrıca kullandığınızdan emin olun **/Ob1** veya **/ob2** derleyici seçenekleri.

Satır içi hem de satır içi derleme seçenekleri farklı modülleri karıştırma bazen sorunlara neden olabilir. Bir C++ Kitaplığı satır içi işlev açık olarak oluşturulursa ([/Ob1](../../build/reference/ob-inline-function-expansion.md) veya [/ob2](../../build/reference/ob-inline-function-expansion.md)) ancak (seçeneği devre dışı) işlevlerini açıklayan ilgili başlık dosyası inlining'i sahip, hata LNK2001 alırsınız. İşlevleri üstbilgi dosyasından kodun içine satır içine almaz ancak bunlar kitaplık dosyasında olmadığından başvurusunu adresine yoktur.

Benzer şekilde, üst bilgi dosyası ayrıca LNK2019 alırsınız yerine satır içi işlevi kullanan bir proje henüz işlevleri bir .cpp dosyasında tanımlar. Her yerde varsaydığı üstbilgi dosyası eklenmiştir, ancak yalnızca işlevlerdir satır içine alınmış .cpp dosyası derleyici; başarılı olduğunda Bu nedenle, bağlayıcı diğer modüllerde kullanıldığında çözülmemiş dış öğeleri olarak işlev görür.

```
// LNK2019_FIP.h
struct testclass {
   void PublicStatMemFunc1(void);
};
```

Ardından,

```
// LNK2019_FIP.cpp
// compile with: /c
#include "LNK2019_FIP.h"
inline void testclass::PublicStatMemFunc1(void) {}
```

Ardından,

```
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

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Araçları Hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)