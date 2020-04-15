---
title: _ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l
ms.date: 4/2/2020
api_name:
- _ismbstrail
- _ismbslead_l
- _ismbslead
- _ismbstrail_l
- _o__ismbslead
- _o__ismbslead_l
- _o__ismbstrail
- _o__ismbstrail_l
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
- _ismbslead
- ismbs
- ismbslead_l
- _ismbs
- ismbstrail_l
- ismbslead
- _ismbstrail
- _ismbstrail_l
- ismbstrail
- _ismbslead_l
helpviewer_keywords:
- ismbstrail function
- _ismbslead function
- ismbslead function
- ismbslead_l function
- _ismbstrail function
- _ismbslead_l function
- ismbstrail_l function
- _ismbstrail_l function
ms.assetid: 86d2cd7a-3cff-443a-b713-14cc17a231e9
ms.openlocfilehash: d4c9bfcec1deab8c00eb490dc044e62a6124aba3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342910"
---
# <a name="_ismbslead-_ismbstrail-_ismbslead_l-_ismbstrail_l"></a>_ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l

Çok bayt karakterli kurşun baytlar ve iz baytları için içeriğe duyarlı testler gerçekleştirir ve belirli bir alt dize işaretçisi bir müşteri adayı baytına mı yoksa bir iz baytına mı işaret ettiğini belirler.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbslead(
   const unsigned char *str,
   const unsigned char *current
);
int _ismbstrail(
   const unsigned char *str,
   const unsigned char *current
);
int _ismbslead_l(
   const unsigned char *str,
   const unsigned char *current,
   _locale_t locale
);
int _ismbstrail_l(
   const unsigned char *str,
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Dize veya önceki bilinen kurşun bayt başlangıcıiçin işaretçi.

*geçerli*<br/>
Test edilecek dizedeki konuma işaretçi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_ismbslead** -1 döndürür eğer karakter bir kurşun bayt ise ve karakter bir iz bayt ise **_ismbstrail** -1 döndürür. Giriş dizeleri geçerli yse ancak bir müşteri adayı bayt veya iz bayt ı değilse, bu işlevler sıfır döndürer. Her iki bağımsız değişken **null**ise, geçersiz parametre işleyicisi, [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, bu işlevler **NULL** döndürdü ve **EINVAL** **için errno** ayarlayın.

## <a name="remarks"></a>Açıklamalar

**_ismbslead** ve **_ismbstrail,** dize bağlamını hesaba kattığı için **_ismbblead** ve **_ismbbtrail** sürümlerden daha yavaşdır.

**_l** soneki olan bu işlevlerin sürümleri, yerelliğe bağımlı davranışları için geçerli yerel yerine geçen yerel alanı kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_ismbslead**|\<mbctype.h> \<veya mbstring.h>|\<ctype.h>,* \<limits.h \<>, stdlib.h>|
|**_ismbstrail**|\<mbctype.h> \<veya mbstring.h>|\<ctype.h>,* \<limits.h \<>, stdlib.h>|
|**_ismbslead_l**|\<mbctype.h> \<veya mbstring.h>|\<ctype.h>,* \<limits.h \<>, stdlib.h>|
|**_ismbstrail_l**|\<mbctype.h> \<veya mbstring.h>|\<ctype.h>,* \<limits.h \<>, stdlib.h>|

\*Test koşulları için manifesto sabitleri için.

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Rutinleri](../../c-runtime-library/ismbc-routines.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Rutinleri](../../c-runtime-library/ismbb-routines.md)<br/>
