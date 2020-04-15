---
title: _ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l
ms.date: 4/2/2020
api_name:
- _ismbcpunct_l
- _ismbcblank
- _ismbcprint
- _ismbcgraph_l
- _ismbcblank_l
- _ismbcpunct
- _ismbcprint_l
- _ismbcspace_l
- _ismbcspace
- _ismbcgraph
- _o__ismbcblank
- _o__ismbcblank_l
- _o__ismbcgraph
- _o__ismbcgraph_l
- _o__ismbcprint
- _o__ismbcprint_l
- _o__ismbcpunct
- _o__ismbcpunct_l
- _o__ismbcspace
- _o__ismbcspace_l
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
- _ismbcspace
- _ismbcgraph
- _ismbcpunct
- ismbcspace_l
- ismbcgraph
- _ismbcgraph_l
- _ismbcprint
- _ismbcspace_l
- ismbcprint
- ismbcgraph_l
- ismbcspace
- ismbcpunct
helpviewer_keywords:
- ismbcspace_l function
- _ismbcprint_l function
- ismbcspace function
- ismbcpunct function
- _ismbcspace_l function
- _ismbcprint function
- ismbcprint function
- _ismbcgraph function
- ismbcgraph_l function
- _ismbcpunct_l function
- ismbcpunct_l function
- ismbcprint_l function
- _ismbcpunct function
- ismbcgraph function
- _ismbcgraph_l function
- _ismbcspace function
ms.assetid: 8e0a5f47-ba64-4411-92a3-3c525d16e3be
ms.openlocfilehash: eb76b6ebdbe4b27ce5a7368ad1b8c2dd8f858d85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343235"
---
# <a name="_ismbcgraph-_ismbcgraph_l-_ismbcprint-_ismbcprint_l-_ismbcpunct-_ismbcpunct_l-_ismbcblank-_ismbcblank_l-_ismbcspace-_ismbcspace_l"></a>_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l

Karakterin grafik karakter mi, görüntü karakteri mi, noktalama işareti mi yoksa boşluk karakteri mi olduğunu belirler.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbcgraph(
   unsigned int c
);
int _ismbcgraph_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcprint(
   unsigned int c
);
int _ismbcprint_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcpunct(
   unsigned int c
);
int _ismbcpunct_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcblank(
   unsigned int c
);
int _ismbcblank_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcspace(
   unsigned int c
);
int _ismbcspace_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Karakter belirlenecek.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Karakter test koşulunu karşılarsa, bu yordamların her biri sıfır olmayan bir değer veya tatmin değilse 0 döndürür. *C* <= 255 ve karşılık gelen bir **_ismbb** yordamı varsa (örneğin, **_ismbcalnum** **_ismbbalnum**karşılık geliyorsa), sonuç ilgili **_ismbb** yordamının dönüş değeridir.

Bu işlevlerin sürümleri, **_l** soneklerine sahip olanların, geçerli yerel alan yerine yerel olarak bağlı davranışları için geçirilen yerel alanı kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri belirli bir koşul için belirli bir çok bayt karakteri sınar.

|Yordam|Test koşulu|Kod sayfası 932 örnek|
|-------------|--------------------|---------------------------|
|**_ismbcgraph**|Grafik|*Eğer c* beyaz bir boşluk dışında herhangi bir ASCII veya katakana yazdırılabilir karakterin tek bayt gösterimi ise sıfırsız döndürür ( ).|
|**_ismbcprint**|Yazdırılabilir|*Eğer c* beyaz bir boşluk da dahil olmak üzere herhangi bir ASCII veya katakana yazdırılabilir karakterin tek bayt gösterimi ise sıfırsız döndürür ( ).|
|**_ismbcpunct**|Noktalama işaretleri|*Eğer c* herhangi bir ASCII veya katakana noktalama karakterinin tek bayt gösterimi ise sıfırsız döndürür.|
|**_ismbcblank**|Boşluk veya yatay sekme|*C* boşluk veya yatay sekme karakteri ise sıfırsız döndürür: *c*=0x20 veya *c*=0x09.|
|**_ismbcspace**|Boşluk|C beyaz boşluk karakteri yse ve yalnızca *c* varsa sıfırsız döndürür: *c*=0x20 veya 0x09<=*c*<=0x0D.|

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbcgraph**|\<mbstring.h>|
|**_ismbcgraph_l**|\<mbstring.h>|
|**_ismbcprint**|\<mbstring.h>|
|**_ismbcprint_l**|\<mbstring.h>|
|**_ismbcpunct**|\<mbstring.h>|
|**_ismbcpunct_l**|\<mbstring.h>|
|**_ismbcblank**|\<mbstring.h>|
|**_ismbcblank_l**|\<mbstring.h>|
|**_ismbcspace**|\<mbstring.h>|
|**_ismbcspace_l**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_ismbc Rutinleri](../../c-runtime-library/ismbc-routines.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Rutinleri](../../c-runtime-library/ismbb-routines.md)<br/>
