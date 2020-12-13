---
description: 'Hakkında daha fazla bilgi edinin: _ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 54745c2db33a68b35236c5b6169280e5e7dacfef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334135"
---
# <a name="_ismbslead-_ismbstrail-_ismbslead_l-_ismbstrail_l"></a>_ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l

Çok baytlı karakter dizesi ön baytları ve iz baytları için bağlama duyarlı testler gerçekleştirir ve belirli bir alt dize işaretçisinin bir ön bayta mi yoksa bir iz baytına mı işaret ettiğini belirler.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*üstbilgisine*<br/>
Dizenin başlangıcına veya önceki bilinen ön bayta yönelik işaretçi.

*geçerli*<br/>
Sınanacak dizedeki konuma yönelik işaretçi.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_ismbslead** , karakter bir ön bayt ise-1 döndürür **_ismbstrail** ve karakter bir iz baytı ise-1 döndürür. Giriş dizeleri geçerliyse ancak bir ön bayt ya da iz baytı değilse, bu işlevler sıfır döndürür. Bağımsız değişken **null** Ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **null** döndürür ve **errno** , **EINVAL** olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**_ismbslead** ve **_ismbstrail** **_ismbblead** ve **_ismbbtrail** sürümlerinden daha yavaştır, çünkü dize bağlamını hesaba götürür.

**_L** sonekine sahip bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayar yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_ismbslead**|\<mbctype.h> veya \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbstrail**|\<mbctype.h> veya \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbslead_l**|\<mbctype.h> veya \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbstrail_l**|\<mbctype.h> veya \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|

\* Test koşullarına yönelik bildirim sabitleri için.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc yordamlar](../../c-runtime-library/ismbc-routines.md)<br/>
[, isw yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb yordamlar](../../c-runtime-library/ismbb-routines.md)<br/>
