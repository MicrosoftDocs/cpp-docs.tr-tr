---
title: __min
ms.date: 04/05/2018
api_name:
- __min
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 6b5cc6517c125f91337ca0d9b12b7a49bd7c1753
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951731"
---
# <a name="__min"></a>__min

İki değerden daha küçük bir değer döndüren bir önişlemci makrosu.

## <a name="syntax"></a>Sözdizimi

```C
#define __min(a,b) (((a) < (b)) ? (a) : (b))
```

### <a name="parameters"></a>Parametreler

*a*, *b*<br/>
**<** İşlecin üzerinde çalışması gereken herhangi bir türün değerleri.

## <a name="return-value"></a>Dönüş Değeri

İki bağımsız değişkenin daha küçük olması.

## <a name="remarks"></a>Açıklamalar

**__Min** makrosu iki değeri karşılaştırır ve daha küçük bir değer döndürür. Bağımsız değişkenler, imzalanmış veya imzasız herhangi bir sayısal veri türü olabilir. Bağımsız değişkenlerin ve dönüş değerinin her ikisi de aynı veri türünde olmalıdır.

Döndürülen bağımsız değişken makro tarafından iki kez değerlendirilir. Bağımsız değişken, değerlendiriliyorsa değeri değiştiren bir ifadesiyse, `*p++`bu beklenmeyen sonuçlara yol açabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**__min**|\<Stdlib. h >|

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
