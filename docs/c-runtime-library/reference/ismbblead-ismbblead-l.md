---
title: _ismbblead, _ismbblead_l
description: Microsoft C Runtime Kitaplığı (CRT) _ismbblead ve _ismbblead_l işlevleriaçıklar.
ms.date: 4/2/2020
api_name:
- _ismbblead_l
- _ismbblead
- _o__ismbblead
- _o__ismbblead_l
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ismbblead_l
- istlead
- _ismbblead
- _ismbblead_l
- ismbblead
- _istlead
helpviewer_keywords:
- _ismbblead_l function
- ismbblead function
- _ismbblead function
- istlead function
- ismbblead_l function
- _istlead function
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
ms.openlocfilehash: ee3085d49a27f2f3c97c6578463cf3a0598b73c7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343572"
---
# <a name="_ismbblead-_ismbblead_l"></a>_ismbblead, _ismbblead_l

Çok bayt karakterli bir kurşun bayt olup olmadığını belirlemek için bir karakteri sınar.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbblead(
   unsigned int c
);
int _ismbblead_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*\
İnteger test edilecek.

*Yerel ayar*\
Kullanılacak yerel yer.

## <a name="return-value"></a>Döndürülen değer

Tamsayı *c* çok bayt karakterin ilk bayt ise sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

Çok bayt karakterler bir kurşun bayt ve ardından bir iz bırakan bayt oluşur. Kurşun baytlar belirli bir karakter kümesi için belirli bir aralıkta olmak tarafından ayırt edilir. Örneğin, yalnızca kod sayfası 932'de, kurşun baytları 0x81 - 0x9F ve 0xE0 - 0xFC arasında değişir.

**_ismbblead,** yerel e-regörere bağımlı davranış için geçerli yerel alanı kullanır. **_ismbblead_l,** bunun yerine geçirilen yerel liği kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Yerel utf-8 olduğunda, **_ismbblead** ve **_ismbblead_l** her zaman 0 (yanlış) dönmek, *c* kurşun bayt olsun ya da olmasın.

**_ismbblead** ve **_ismbblead_l,** Standart C kitaplığınbir parçası değildir, Microsoft'a özgüdeğildir. Bunları taşınabilir kodu istediğiniz yerde kullanmanızı önermiyoruz. Standart C uyumluluğu için bunun yerine **mbrlen** kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel metin yordam eşlemeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istlead**|Her zaman yanlış döndürür|**_ismbblead**|Her zaman yanlış döndürür|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_ismbblead**|\<mbctype.h> \<veya mbstring.h>|\<ctype.h>,* \<limits.h \<>, stdlib.h>|
|**_ismbblead_l**|\<mbctype.h> \<veya mbstring.h>|\<ctype.h>,* \<limits.h \<>, stdlib.h>|

\*Test koşulları için manifesto sabitleri için.

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Bayt sınıflandırması](../../c-runtime-library/byte-classification.md)\
[_ismbb rutinleri](../../c-runtime-library/ismbb-routines.md)\
[mbrlen](mbrlen.md)
