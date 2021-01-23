---
description: pragmaMicrosoft C/C++ ' da include_alias yönergesi hakkında daha fazla bilgi edinin
title: include_alias pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.include_alias
- include_alias_CPP
helpviewer_keywords:
- pragma, include_alias
- include_alias pragma
no-loc:
- pragma
ms.openlocfilehash: a9586748794704b3b3bcaf3d8ede7ef2f2f74545
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713603"
---
# <a name="include_alias-no-locpragma"></a>`include_alias` pragma

Bir yönergede *alias_filename* bulunduğunda `#include` derleyicinin yerine *actual_filename* yerini belirtir.

## <a name="syntax"></a>Syntax

<!-- localization note - it's important to have the italic and bold characters immediately adjacent here. -->
> **`#pragma include_alias(`** "*alias_filename*" **`,`** "*actual_filename*" **`)`**\
> **`#pragma include_alias(`** \<*alias_filename*> **`,`** \<*actual_filename*> **`)`**

## <a name="remarks"></a>Açıklamalar

**`include_alias`** pragma Yönergesi, kaynak dosyaları tarafından dahil edilen dosya adları için farklı adlara veya yollara sahip dosyaları değiştirmenize olanak sağlar. Örneğin, bazı dosya sistemleri 8,3 FAT dosya sistemi sınırından daha uzun üstbilgi dosya adlarına izin verir. Daha uzun üstbilgi dosya adlarının ilk sekiz karakteri benzersiz olabileceğinden, derleyici artık daha uzun adları 8,3 ' a kesemez. Derleyici bir yönergede *alias_filename* dizeyi her gördüğünde `#include` , bunun yerine adı *actual_filename* koyar. Sonra *actual_filename* üst bilgi dosyasını yükler. Bu pragma , karşılık gelen `#include` yönergelerden önce gelmelidir. Örneğin:

```cpp
// First eight characters of these two files not unique.
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )

#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )

#include "AppleSystemHeaderQuickdraw.h"
#include "AppleSystemHeaderFruit.h"
#include "GraphicsMenu.h"
```

Arama yapılacak diğer ad, belirtile tam olarak eşleşmelidir. Büyük küçük harf, yazım ve çift tırnak işareti ya da açılı ayraç kullanımı tüm eşleşmelidir. , **`include_alias`** pragma Dosya adlarında basit dize eşleşmesi yapar. Başka bir dosya adı doğrulaması yapılmaz. Örneğin, aşağıdaki yönergeler göz önünde bulundurulduğunda,

```cpp
#pragma include_alias("mymath.h", "math.h")
#include "./mymath.h"
#include "sys/mymath.h"
```

üst bilgi dosyası dizeleri tam olarak eşleşmediğinden diğer ad değiştirme yapılmaz. Ayrıca, ve derleyici seçeneklerinde bağımsız değişken olarak kullanılan üst bilgi dosya adları **`/Yu`** **`/Yc`** veya, `hdrstop` pragma yerine kullanılmaz. Örneğin, kaynak dosyanız aşağıdaki yönergeyi içeriyorsa,

```cpp
#include <AppleSystemHeaderStop.h>
```

ilgili derleyici seçeneği şöyle olmalıdır:

> **`/YcAppleSystemHeaderStop.h`**

**`include_alias`** pragma Herhangi bir üst bilgi dosya adını diğerine eşlemek için öğesini kullanabilirsiniz. Örneğin:

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

İçindeki bir hata *`VERYLONGFILENAME.H`* Şu hata iletisini üretir:

```Output
myfile.h(15) : error C2059 : syntax error
```

Ayrıca, geçişlilik desteklenmediğini unutmayın. Aşağıdaki yönergeler göz önünde bulundurulduğunda,

```cpp
#pragma include_alias( "one.h", "two.h" )
#pragma include_alias( "two.h", "three.h" )
#include "one.h"
```

Derleyici, yerine dosyayı arar *`two.h`* *`three.h`* .

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
