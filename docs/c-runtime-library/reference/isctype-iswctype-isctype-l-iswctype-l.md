---
title: _isctype, iswctype, _isctype_l, _iswctype_l
ms.date: 11/04/2016
apiname:
- _isctype_l
- iswctype
- _iswctype_l
- _isctype
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- iswctype
- _isctype
- _isctype_l
- _iswctype
- isctype
- iswctype_l
- isctype_l
- _iswctype_l
helpviewer_keywords:
- isctype_l function
- iswctype_l function
- iswctype function
- _isctype function
- _isctype_l function
- _iswctype_l function
- isctype function
- _iswctype function
ms.assetid: cf7509b7-12fc-4d95-8140-ad2eb98173d3
ms.openlocfilehash: c5eb0b51cf0371100ed884221ee04885dfbe9ad9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563169"
---
# <a name="isctype-iswctype-isctypel-iswctypel"></a>_isctype, iswctype, _isctype_l, _iswctype_l

Testleri *c* ctype özelliği tarafından belirtilen *desc* bağımsız değişken. Her bir geçerli değerini *desc*, bir eşdeğer bir geniş karakter sınıflandırma rutini vardır.

## <a name="syntax"></a>Sözdizimi

```C
int _isctype(
   int c,
   _ctype_t desc
);
int _isctype_l(
   int c,
   _ctype_t desc,
   _locale_t locale
);
int iswctype(
   wint_t c,
   wctype_t desc
);
int _iswctype_l(
   wint_t c,
   wctype_t desc,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Test edilecek tamsayı.

*desc*<br/>
Sınanacak özellik. Bu normalde ctype kullanarak alınan veya [wctype](wctype.md).

*Yerel ayar*<br/>
Herhangi bir yerel ayara bağlı test için kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_isctype** ve **iswctype** sıfır olmayan bir değer döndürür *c* tarafından belirtilen özelliğe sahip *desc* geçerli yerel ayarı veya yoksa 0. Sahip bu işlevlerin sürümleri **_l** sonekine yerel ayara bağlı davranışları için geçerli yerel ayarı yerine iletilen yerel ayarı kullanmaları dışında. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Davranışını **_isctype** ve **_isctype_l** tanımsızdır *c* EOF değilse veya 0-0xFF aralığındaysa aralığında. Bir hata ayıklama CRT Kitaplığı kullanıldığında ve *c* değil, bu değerleri işlevleri raise onaylama biridir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|yok|**_isctype**|yok|**_iswctype**|
|yok|**_isctype_l**|yok|**_iswctype_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_isctype**|\<CType.h >|
|**iswctype**|\<CType.h > veya \<wchar.h >|
|**_isctype_l**|\<CType.h >|
|**_iswctype_l**|\<CType.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
