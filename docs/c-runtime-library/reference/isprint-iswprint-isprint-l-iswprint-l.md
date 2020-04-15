---
title: isprint, iswprint, _isprint_l, _iswprint_l
ms.date: 4/2/2020
api_name:
- iswprint
- isprint
- _isprint_l
- _iswprint_l
- _o_isprint
- _o_iswprint
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- iswprint
- _istprint
- isprint
helpviewer_keywords:
- _istprint function
- iswprint function
- _iswprint_l function
- isprint_l function
- istprint function
- isprint function
- iswprint_l function
- _isprint_l function
ms.assetid: a8bbcdb0-e8d0-4d8c-ae4e-56d3bdee6ca3
ms.openlocfilehash: f09168e8e010fb59d748c109d4a41c533318e2eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342893"
---
# <a name="isprint-iswprint-_isprint_l-_iswprint_l"></a>isprint, iswprint, _isprint_l, _iswprint_l

Bir tamsedenin yazdırılabilir bir karakteri temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isprint(
   int c
);
int iswprint(
   wint_t c
);
int _isprint_l(
   int c,
   _locale_t locale
);
int _iswprint_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Test etmek için sonda.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri *yazdırılabilir* bir karakterin belirli bir temsili ise sıfırsız döndürür. **isprint** yazdırılabilir bir *c* karakter ise sıfır olmayan bir değer döndürür—bu boşluk karakterini (0x20 - 0x7E) içerir. **iswprint** *yazdırılabilir* geniş bir karakter ise sıfır olmayan bir değer döndürür— bu alan geniş karakter içerir. *C* test koşulunu karşılamazsa bu yordamların her biri 0 döndürür.

Bu işlevler için test koşulunun sonucu, LC_CTYPE **kategori** ayarına bağlıdır; daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md) bakın. **_l** soneki olmayan bu işlevlerin sürümleri, yerel çözüme bağlı herhangi bir davranış için geçerli yerel durumu kullanır; **_l** soneki olan sürümler, bunun yerine geçirilen yerel alanı kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

isprint **isprint** ve **_isprint_l** *davranışı, c* EOF değilse veya 0 ile 0xFF aralığında, dahil ise tanımsızdır. Hata ayıklama CRT kitaplığı kullanıldığında ve *c* bu değerlerden biri değilse, işlevler bir iddiayı yükseltir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_unicode tanımlı|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istprint**|**isprint**|[_ismbcprint](ismbcgraph-functions.md)|**iswprint**|

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isprint**|\<ctype.h>|
|**iswprint**|\<ctype.h> \<veya wchar.h>|
|**_isprint_l**|\<ctype.h>|
|**_iswprint_l**|\<ctype.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
