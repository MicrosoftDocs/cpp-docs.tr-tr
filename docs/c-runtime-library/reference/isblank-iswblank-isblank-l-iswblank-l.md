---
title: isblank, iswblank, _isblank_l, _iswblank_l
ms.date: 4/2/2020
api_name:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
- _o_isblank
- _o_iswblank
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
ms.openlocfilehash: 736a0791f1e5ee4b11e61164861cc6dc0c7a9c87
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343889"
---
# <a name="isblank-iswblank-_isblank_l-_iswblank_l"></a>isblank, iswblank, _isblank_l, _iswblank_l

Bir tamsedin boş bir karakteri temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isblank(
   int c
);
int iswblank(
   wint_t c
);
int _isblank_l(
   int c,
   _locale_t locale
);
int _iswblank_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Test etmek için sonda.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her *biri, bir* boşluk veya yatay sekme karakterinin belirli bir temsiliyse veya sözcükleri metin satırı içinde ayırmak için kullanılan yerele özgü karakter kümesinden biriyse sıfırsız döndürür. **isblank,** *boşluk* karakteri (0x20) veya yatay sekme karakteri (0x09) ise sıfır olmayan bir değer döndürür. **Boş** işlevler için test koşulunun sonucu, yerel LC_CTYPE **kategori** ayarına bağlıdır; daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md)bakın. **_l** soneki olmayan bu işlevlerin sürümleri, yerel çözüme bağlı herhangi bir davranış için geçerli yerel durumu kullanır; **_l** soneki olan sürümler, bunun yerine geçirilen yerel alanı kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

**iswblank,** standart bir *c* alana veya yatay sekme karakterine karşılık gelen geniş bir karakterse sıfır olmayan bir değer döndürür.

isblank **isblank** ve **_isblank_l** *davranışı, c* EOF değilse veya 0 ile 0xFF aralığında, dahil ise tanımsızdır. Hata ayıklama CRT kitaplığı kullanıldığında ve *c* bu değerlerden biri değilse, işlevler bir iddiayı yükseltir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istblank**|**Eboşsa**|[_ismbcblank](ismbcgraph-functions.md)|**iswblank**|
|**_istblank_l**|**_isblank_l**|[_ismbcblank_l](ismbcgraph-functions.md)|**_iswblank_l**|

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Eboşsa**|\<ctype.h>|
|**iswblank**|\<ctype.h> \<veya wchar.h>|
|**_isblank_l**|\<ctype.h>|
|**_iswblank_l**|\<ctype.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
