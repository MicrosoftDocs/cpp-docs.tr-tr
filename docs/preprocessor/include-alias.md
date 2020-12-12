---
description: 'Daha fazla bilgi edinin: include_alias pragma'
title: include_alias pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.include_alias
- include_alias_CPP
helpviewer_keywords:
- pragmas, include_alias
- include_alias pragma
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
ms.openlocfilehash: 1a1855ce4c908c6678cfce7617c98aa671c57fac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236522"
---
# <a name="include_alias-pragma"></a>include_alias pragması

Bir yönergede *alias_filename* bulunduğunda `#include` derleyicinin yerine *actual_filename* yerini belirtir.

## <a name="syntax"></a>Syntax

<!-- localization note - it's important to have the italic and bold characters immediately adjacent here. -->
> **#pragma include_alias (** "*alias_filename*" **,** "*actual_filename*" **)**\
> **#pragma include_alias (** \<*alias_filename*> **,** \<*actual_filename*> **)**

## <a name="remarks"></a>Açıklamalar

**İnclude_alias** pragma yönergesi, kaynak dosyalar tarafından dahil edilen dosya adları için farklı adlara veya yollara sahip dosyaları değiştirmenize olanak sağlar. Örneğin, bazı dosya sistemleri 8,3 FAT dosya sistemi sınırından daha uzun üstbilgi dosya adlarına izin verir. Daha uzun üstbilgi dosya adlarının ilk sekiz karakteri benzersiz olabileceğinden, derleyici artık daha uzun adları 8,3 ' a kesemez. Derleyici bir yönergede *alias_filename* dizeyi her gördüğünde `#include` , bunun yerine adı *actual_filename* koyar. Sonra *actual_filename* üst bilgi dosyasını yükler. Bu pragma ilgili `#include` yönergelerinden önce görünmelidir. Örneğin:

```cpp
// First eight characters of these two files not unique.
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )

#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )

#include "AppleSystemHeaderQuickdraw.h"
#include "AppleSystemHeaderFruit.h"
#include "GraphicsMenu.h"
```

Arama yapılacak diğer ad, belirtile tam olarak eşleşmelidir. Büyük küçük harf, yazım ve çift tırnak işareti ya da açılı ayraç kullanımı tüm eşleşmelidir. **İnclude_alias** pragma, dosya adlarında basit dize eşleştirmesi yapar. Başka bir dosya adı doğrulaması yapılmaz. Örneğin, aşağıdaki yönergeler göz önünde bulundurulduğunda,

```cpp
#pragma include_alias("mymath.h", "math.h")
#include "./mymath.h"
#include "sys/mymath.h"
```

üst bilgi dosyası dizeleri tam olarak eşleşmediğinden diğer ad değiştirme yapılmaz. Ayrıca, ve derleyici seçeneklerinde bağımsız değişken olarak kullanılan üst bilgi dosya adları `/Yu` `/Yc` veya `hdrstop` pragma, yerine kullanılmaz. Örneğin, kaynak dosyanız aşağıdaki yönergeyi içeriyorsa,

```cpp
#include <AppleSystemHeaderStop.h>
```

ilgili derleyici seçeneği şöyle olmalıdır:

> **/Ycapptasystemheaderstop.h**

Herhangi bir üst bilgi dosya adını başka bir şekilde eşlemek için **include_alias** pragma 'ı kullanabilirsiniz. Örneğin:

```cpp
#pragma include_alias( "api.h", "c:\version1.0\api.h" )
#pragma include_alias( <stdio.h>, <newstdio.h> )
#include "api.h"
#include <stdio.h>
```

Açılı ayraçlar içine alınmış dosya adlarıyla çift tırnak işareti içine alınmış dosya adlarını karıştırmayın. Örneğin, yukarıdaki iki `#pragma include_alias` yönergeler verildiğinde, derleyici aşağıdaki yönergelerden herhangi bir değiştirme yapmaz `#include` :

```cpp
#include <api.h>
#include "stdio.h"
```

Ayrıca, aşağıdaki yönerge bir hata oluşturur:

```cpp
#pragma include_alias(<header.h>, "header.h")  // Error
```

Hata iletilerinde bildirilen dosya adı veya önceden tanımlanmış makronun değeri olarak `__FILE__` , değiştirme yapıldıktan sonra dosyanın adı. Örneğin, aşağıdaki yönergelerden sonra çıktıyı inceleyin:

```cpp
#pragma include_alias( "VERYLONGFILENAME.H", "myfile.h" )
#include "VERYLONGFILENAME.H"
```

VERYLONGFILENAME içinde bir hata *. H* aşağıdaki hata iletisini üretir:

```Output
myfile.h(15) : error C2059 : syntax error
```

Ayrıca, geçişlilik desteklenmediğini unutmayın. Aşağıdaki yönergeler göz önünde bulundurulduğunda,

```cpp
#pragma include_alias( "one.h", "two.h" )
#pragma include_alias( "two.h", "three.h" )
#include "one.h"
```

Derleyici, *üç. h* yerine *iki. h* dosyasını arar.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
