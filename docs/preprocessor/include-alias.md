---
title: include_alias | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.include_alias
- include_alias_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, include_alias
- include_alias pragma
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b03ec43ff213e330c88886fb485c0e18700c8a86
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="includealias"></a>include_alias

Belirleyen *short_filename* için diğer ad olarak kullanılacak *long_filename*.

## <a name="syntax"></a>Sözdizimi

> #<a name="pragma-includealiaslongfilename-shortfilename"></a>pragma include_alias ("*long_filename*","*short_filename*")  
> #<a name="pragma-includealiaslongfilename-shortfilename"></a>pragma include_alias (*long_filename*, *short_filename*)

## <a name="remarks"></a>Açıklamalar

Bazı dosya sistemleri, 8.3 FAT dosya sistemi sınırından daha uzun üstbilgi dosya adlarına izin verir. Derleyici, uzun üstbilgi dosya adlarının ilk sekiz karakteri benzersiz olmayabileceği için uzun adları 8.3'e kesemez. Her derleyici karşılaştığında *long_filename* dize, onu değiştirir *short_filename*ve üst bilgi dosyasını arar *short_filename* yerine. Bu pragma ilgili `#include` yönergelerinden önce görünmelidir. Örneğin:

```cpp
// First eight characters of these two files not unique.
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )

#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )

#include "AppleSystemHeaderQuickdraw.h"
#include "AppleSystemHeaderFruit.h"
#include "GraphicsMenu.h"
```

Aranan diğer ad belirtimle büyük/küçük harf kullanımı, yazım ve çift tırnak işareti veya açılı ayraç bakımından tamamen eşleşmelidir. **İnclude_alias** pragma gerçekleştirir üzerinde dosya adları eşleşen basit bir dize; başka bir dosya adı doğrulama gerçekleştirilir. Örneğin, aşağıdaki yönergeler göz önünde bulundurulduğunda,

```cpp
#pragma include_alias("mymath.h", "math.h")
#include "./mymath.h"
#include "sys/mymath.h"
```

üstbilgi dosya dizeleri tam olarak eşleşmediğinden hiçbir diğer ad (değiştirme) oluşturma işlemi gerçekleştirilmez. Ayrıca, üstbilgi dosya adları /Yu ve /Yc derleyici seçenekleri bağımsız değişken olarak kullanılan veya **hdrstop** pragma, değil değiştirdi. Örneğin, kaynak dosyanız aşağıdaki yönergeyi içeriyorsa,
  
```cpp
#include <AppleSystemHeaderStop.h>
```

ilgili derleyici seçeneği şöyle olmalıdır:

> /YcAppleSystemHeaderStop.h

Kullanabileceğiniz **include_alias** üstbilgi dosya diğerine eşlemek için pragması. Örneğin:

```cpp
#pragma include_alias( "api.h", "c:\version1.0\api.h" )
#pragma include_alias( <stdio.h>, <newstdio.h> )
#include "api.h"
#include <stdio.h>
```

Çift tırnak işaretlerinin içine alınmış dosya adlarını, açılı ayraçlar içine alınmış dosya adlarıyla karıştırmayın. Örneğin, yukarıdaki iki verilen **#pragma include_alias** yönergeleri, derleyici hiçbir değiştirme aşağıdakileri gerçekleştirir `#include` yönergeleri:

```cpp
#include <api.h>
#include "stdio.h"
```

Ayrıca, aşağıdaki yönerge bir hata oluşturur:

```cpp
#pragma include_alias(<header.h>, "header.h")  // Error
```

Dosya adı hata iletileri veya önceden tanımlanmış değeri olarak rapor Not **&#95; &#95; Dosya &#95; &#95;**  değiştirme gerçekleştirildikten sonra makro olduğu dosyasının adı. Örneğin, çıktı sonra aşağıdaki yönergeleri bakın:

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

[Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)