---
title: __min
ms.date: 04/05/2018
apiname:
- __min
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- __min
- min
- _min
helpviewer_keywords:
- __min macro
- min macro
- minimum macro
- _min macro
ms.assetid: 2037f26c-b48a-4a69-8870-22519f052a3c
ms.openlocfilehash: f9e867cd1f3e3519e440c91895e61e317d9688a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156557"
---
# <a name="min"></a>__min

İki değerin daha küçük döndürür önişlemci makrosu.

## <a name="syntax"></a>Sözdizimi

```C
#define __min(a,b) (((a) < (b)) ? (a) : (b))
```

### <a name="parameters"></a>Parametreler

*a*, *b*<br/>
Herhangi bir değer türü **<** işleci çalışır.

## <a name="return-value"></a>Dönüş Değeri

Küçük iki bağımsız değişken.

## <a name="remarks"></a>Açıklamalar

**__Min** makrosu iki değeri karşılaştırır ve daha küçük bir değer döndürür. Bağımsız değişkenler, imzalı veya imzasız veri türü, bir sayı olabilir. Hem bağımsız değişkenler ve dönüş değeri, aynı veri türünde olmalıdır.

Döndürülen bağımsız değişkeni iki kez makro tarafından değerlendirilir. Bunu, aşağıdaki gibi değerlendirildiğinde değerini değiştiren bir ifade bağımsız değişken ise bu beklenmeyen sonuçlara neden olabilir `*p++`.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**__min**|\<stdlib.h >|

## <a name="example"></a>Örnek

```C
// crt_minmax.c

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int a = 10;
   int b = 21;

   printf( "The larger of %d and %d is %d\n",  a, b, __max( a, b ) );
   printf( "The smaller of %d and %d is %d\n", a, b, __min( a, b ) );
}
```

```Output
The larger of 10 and 21 is 21
The smaller of 10 and 21 is 10
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[__max](max.md)<br/>
