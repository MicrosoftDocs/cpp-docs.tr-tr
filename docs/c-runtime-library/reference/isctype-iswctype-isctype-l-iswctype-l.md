---
title: _isctype, iswctype, _isctype_l, _iswctype_l
ms.date: 4/2/2020
api_name:
- _isctype_l
- iswctype
- _iswctype_l
- _isctype
- _o__isctype
- _o__isctype_l
- _o__iswctype_l
- _o_iswctype
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
ms.openlocfilehash: 5beedd8a5da6848fc8c43ab1a27ee52402fe394e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343848"
---
# <a name="_isctype-iswctype-_isctype_l-_iswctype_l"></a>_isctype, iswctype, _isctype_l, _iswctype_l

*Desc* bağımsız değişkeni tarafından belirtilen ctype özelliği için *c* testleri. *Desc*her geçerli değeri için, eşdeğer bir geniş karakter sınıflandırma yordamı vardır.

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

*C*<br/>
Test etmek için sonda.

*Desc*<br/>
Özellik için test etmek. Bu normalde ctype veya [wctype](wctype.md)kullanılarak alınır.

*Yerel ayar*<br/>
Yerele bağlı testler için kullanılacak yerel alan.

## <a name="return-value"></a>Dönüş Değeri

**_isctype** ve **iswctype,** *geçerli* yerel *desc* tarafından belirtilen özelliği varsa sıfır olmayan bir değer veya yoksa 0 döndürür. **Bu işlevlerin _l** sonekli sürümleri, yerel liğe bağımlı davranışları için geçerli yerel alan yerine geçirilen yerel liği kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

**_isctype c** EOF değilse veya *c* 0 ile 0xFF aralığında, dahil _isctype_l davranışı tanımsızdır. **_isctype_l** Hata ayıklama CRT kitaplığı kullanıldığında ve *c* bu değerlerden biri değilse, işlevler bir iddiayı yükseltir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|yok|**_isctype**|yok|**_iswctype**|
|yok|**_isctype_l**|yok|**_iswctype_l**|

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_isctype**|\<ctype.h>|
|**iswctype**|\<ctype.h> \<veya wchar.h>|
|**_isctype_l**|\<ctype.h>|
|**_iswctype_l**|\<ctype.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
