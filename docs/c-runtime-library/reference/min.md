---
description: 'Hakkında daha fazla bilgi edinin: __min'
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
ms.openlocfilehash: 337d4fc7226044e41a616dc6da8230e013b2702d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340586"
---
# <a name="__min"></a>__min

İki değerden daha küçük bir değer döndüren bir önişlemci makrosu.

## <a name="syntax"></a>Sözdizimi

```C
#define __min(a,b) (((a) < (b)) ? (a) : (b))
```

### <a name="parameters"></a>Parametreler

*a*, *b*<br/>
İşlecin üzerinde çalışması gereken herhangi bir türün değerleri **<** .

## <a name="return-value"></a>Dönüş Değeri

İki bağımsız değişkenin daha küçük olması.

## <a name="remarks"></a>Açıklamalar

**__Min** makro iki değeri karşılaştırır ve daha küçük bir değer döndürür. Bağımsız değişkenler, imzalanmış veya imzasız herhangi bir sayısal veri türü olabilir. Bağımsız değişkenlerin ve dönüş değerinin her ikisi de aynı veri türünde olmalıdır.

Döndürülen bağımsız değişken makro tarafından iki kez değerlendirilir. Bağımsız değişken, değerlendiriliyorsa değeri değiştiren bir ifadesiyse, bu beklenmeyen sonuçlara yol açabilir `*p++` .

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**__min**|\<stdlib.h>|

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

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[__max](max.md)<br/>
