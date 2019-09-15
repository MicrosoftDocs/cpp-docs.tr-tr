---
title: _ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l
ms.date: 11/04/2016
api_name:
- _ismbstrail
- _ismbslead_l
- _ismbslead
- _ismbstrail_l
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
ms.openlocfilehash: 71a5d2a82c01a41f945ef3fa8c7652f846f05103
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953775"
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

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_ismbslider** , karakter bir ön bayt ise ve **_ismbstraıl** , karakter bir iz baytı ise-1 döndürürse-1 döndürür. Giriş dizeleri geçerliyse ancak bir ön bayt ya da iz baytı değilse, bu işlevler sıfır döndürür. Bağımsız değişken **null**Ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **null** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**_ismbslider** ve **_ismbstraıl** , dize bağlamını hesaba attıkları için **_ismbblider** ve **_ismbbiz** sürümlerinden daha yavaştır.

**_L** sonekine sahip bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayar yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_ismbslider**|\<Mbctype. h > veya \<mbstring. h >|\<CType. h >, * \<limit. h >, \<Stdlib. h >|
|**_ismbstrail**|\<Mbctype. h > veya \<mbstring. h >|\<CType. h >, * \<limit. h >, \<Stdlib. h >|
|**_ismbslead_l**|\<Mbctype. h > veya \<mbstring. h >|\<CType. h >, * \<limit. h >, \<Stdlib. h >|
|**_ismbstrail_l**|\<Mbctype. h > veya \<mbstring. h >|\<CType. h >, * \<limit. h >, \<Stdlib. h >|

\*Test koşullarına yönelik bildirim sabitleri için.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
