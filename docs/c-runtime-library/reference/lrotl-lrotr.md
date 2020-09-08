---
title: _lrotl, _lrotr
description: '_Lrotl Ve _lrotr için API başvurusu; bitleri sola (_lrotl) veya sağa (_lrotr) döndürün. '
ms.date: 04/04/2018
api_name:
- _lrotl
- _lrotr
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
- api-ms-win-crt-utility-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- lrotr
- lrotl
- _lrotr
- _lrotl
helpviewer_keywords:
- lrotl function
- bits
- _lrotr function
- lrotr function
- rotating bits
- _lrotl function
- bits, rotating
ms.assetid: d42f295b-35f9-49d2-9ee4-c66896ffe68e
ms.openlocfilehash: ccd14f7aa6ba3c1278063593aecee20c6789110d
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555013"
---
# <a name="_lrotl-_lrotr"></a>_lrotl, _lrotr

Bitleri sola (**_lrotl**) veya sağa (**_lrotr**) döndürür.

## <a name="syntax"></a>Söz dizimi

```C
unsigned long _lrotl( unsigned long value, int shift );
unsigned long _lrotr( unsigned long value, int shift );
```

### <a name="parameters"></a>Parametreler

*deeri*<br/>
Döndürülecektir değer.

*karakter*<br/>
Kaydırılacak bit sayısı *değeri*.

## <a name="return-value"></a>Dönüş Değeri

Her iki işlev de döndürülen değeri döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**_Lrotl** ve **_lrotr** işlevleri *değeri* , *kaydırma* bitleri ile döndürür. **_lrotl** değeri solda, daha önemli bir bite doğru döndürür. **_lrotr** değeri sağa, daha az önemli bir bite doğru döndürür. Her iki işlev de bir *değerin* sonundaki bitleri diğer bir uca kaydırır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lrotl**, **_lrotr**|\<stdlib.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_lrot.c

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   unsigned long val = 0x0fac35791;

   printf( "0x%8.8lx rotated left eight bits is 0x%8.8lx\n",
            val, _lrotl( val, 8 ) );
   printf( "0x%8.8lx rotated right four bits is 0x%8.8lx\n",
            val, _lrotr( val, 4 ) );
}
```

```Output
0xfac35791 rotated left eight bits is 0xc35791fa
0xfac35791 rotated right four bits is 0x1fac3579
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_rotl, _rotl64, _rotr, _rotr64](rotl-rotl64-rotr-rotr64.md)<br/>
