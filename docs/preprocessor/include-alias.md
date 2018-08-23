---
title: include_alias | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.include_alias
- include_alias_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, include_alias
- include_alias pragma
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26e59888a26b5f71b697e398e81b16012dd35e3a
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465066"
---
# <a name="includealias"></a>include_alias

Belirten *short_filename* için bir diğer ad olarak kullanılacak *long_filename*.

## <a name="syntax"></a>Sözdizimi

> #<a name="pragma-includealiaslongfilename-shortfilename"></a>include_alias pragması ("*long_filename*","*short_filename*")  
> #<a name="pragma-includealiaslongfilename-shortfilename"></a>include_alias pragması (*long_filename*, *short_filename*)

## <a name="remarks"></a>Açıklamalar

Bazı dosya sistemleri, 8.3 FAT dosya sistemi sınırından daha uzun üstbilgi dosya adlarına izin verir. Derleyici, uzun üstbilgi dosya adlarının ilk sekiz karakteri benzersiz olmayabileceği için uzun adları 8.3'e kesemez. Her derleyici karşılaştığında *long_filename* dizesiyle *short_filename*ve üstbilgi dosyasını arar *short_filename* yerine. Bu pragma ilgili `#include` yönergelerinden önce görünmelidir. Örneğin:

```cpp
// First eight characters of these two files not unique.
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )

#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )

#include "AppleSystemHeaderQuickdraw.h"
#include "AppleSystemHeaderFruit.h"
#include "GraphicsMenu.h"
```

Aranan diğer ad belirtimle büyük/küçük harf kullanımı, yazım ve çift tırnak işareti veya açılı ayraç bakımından tamamen eşleşmelidir. **İnclude_alias** pragma eşleşen dosya adları üzerinde basit dize gerçekleştirir; başka bir dosya adı doğrulama gerçekleştirilir. Örneğin, aşağıdaki yönergeler göz önünde bulundurulduğunda,

```cpp
#pragma include_alias("mymath.h", "math.h")
#include "./mymath.h"
#include "sys/mymath.h"
```

üstbilgi dosya dizeleri tam olarak eşleşmediğinden hiçbir diğer ad (değiştirme) oluşturma işlemi gerçekleştirilmez. Ayrıca, bağımsız değişkenleri olarak kullanılan üstbilgi dosya `/Yu` ve `/Yc` derleyici seçenekleri veya `hdrstop` pragması değiştirilmez. Örneğin, kaynak dosyanız aşağıdaki yönergeyi içeriyorsa,
  
```cpp
#include <AppleSystemHeaderStop.h>
```

ilgili derleyici seçeneği şöyle olmalıdır:

> /YcAppleSystemHeaderStop.h

Kullanabileceğiniz **include_alias** diğerine üstbilgi dosya adını eşleştirmek için pragması. Örneğin:

```cpp
#pragma include_alias( "api.h", "c:\version1.0\api.h" )
#pragma include_alias( <stdio.h>, <newstdio.h> )
#include "api.h"
#include <stdio.h>
```

Çift tırnak işaretlerinin içine alınmış dosya adlarını, açılı ayraçlar içine alınmış dosya adlarıyla karıştırmayın. Örneğin, yukarıdaki iki verilen `#pragma include_alias` yönergeleri, derleyici aşağıdaki hiçbir değişim gerçekleştirir `#include` yönergeleri:

```cpp
#include <api.h>
#include "stdio.h"
```

Ayrıca, aşağıdaki yönerge bir hata oluşturur:

```cpp
#pragma include_alias(<header.h>, "header.h")  // Error
```

Dosya adında hata iletilerinde veya önceden tanımlanmış değer olarak bildirilen Not `__FILE__` makro gerçekleştirildikten sonra dosyanın adı olan. Örneğin, aşağıdaki yönergelerden sonra çıktıyı görürsünüz:

```cpp
#pragma include_alias( "VeryLongFileName.H", "myfile.h" )
#include "VeryLongFileName.H"
```

VERYLONGFILENAME bir hata oluştu. H aşağıdaki hata iletisini oluşturur:

```Output
myfile.h(15) : error C2059 : syntax error
```

Ayrıca geçişliliğin desteklenmediğini unutmayın. Aşağıdaki yönergeler göz önünde bulundurulduğunda,

```cpp
#pragma include_alias( "one.h", "two.h" )
#pragma include_alias( "two.h", "three.h" )
#include "one.h"
```

derleyici THREE.H yerine TWO.H dosyasını arar.  

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)