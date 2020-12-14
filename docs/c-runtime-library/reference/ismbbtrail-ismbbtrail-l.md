---
description: 'Hakkında daha fazla bilgi edinin: _ismbbtrail _ismbbtrail_l'
title: _ismbbtrail, _ismbbtrail_l
ms.date: 4/2/2020
api_name:
- _ismbbtrail
- _ismbbtrail_l
- _o__ismbbtrail
- _o__ismbbtrail_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbbtrail
- ismbbtrail
- _ismbbtrail_l
- ismbbtrail_l
helpviewer_keywords:
- ismbbtrail_l function
- _ismbbtrail function
- _ismbbtrail_l function
- ismbbtrail function
ms.assetid: dfdd0292-960b-4c1d-bf11-146e0fc80247
ms.openlocfilehash: 4c9737cb0d4c3e4d1acf35e0c0cbea18ccba3f69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256438"
---
# <a name="_ismbbtrail-_ismbbtrail_l"></a>_ismbbtrail, _ismbbtrail_l

Bir baytın çok baytlı bir karakterin sondaki baytı olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbbtrail(
   unsigned int c
);
int _ismbbtrail_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*,*<br/>
Sınanacak tamsayı.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_ismbbtrail** *, tam sayı* karakter bir çok baytlı karakterin ikinci baytı ise sıfır dışında bir değer döndürür. Örneğin, yalnızca kod sayfası 932 ' de geçerli aralıklar 0x40 ile 0x7E ve 0x80 ile 0xFC arasındadır.

## <a name="remarks"></a>Açıklamalar

**_ismbbtrail** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_ismbbtrail_l** , bunun yerine geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_ismbbtrail**|\<mbctype.h> veya \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbbtrail_l**|\<mbctype.h> veya \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|

\* Test koşullarına yönelik bildirim sabitleri için.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb yordamlar](../../c-runtime-library/ismbb-routines.md)<br/>
