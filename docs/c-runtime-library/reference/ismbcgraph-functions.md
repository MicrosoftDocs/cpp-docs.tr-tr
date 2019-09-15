---
title: _ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l
ms.date: 11/04/2016
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
ms.openlocfilehash: 25136896555128339aaa4c79cec2ca9bf3ded43c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953899"
---
# <a name="_ismbcgraph-_ismbcgraph_l-_ismbcprint-_ismbcprint_l-_ismbcpunct-_ismbcpunct_l-_ismbcblank-_ismbcblank_l-_ismbcspace-_ismbcspace_l"></a>_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l

Karakterin bir grafik karakter, bir görüntüleme karakteri, bir noktalama karakteri veya boşluk karakteri olup olmadığını belirler.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*c*<br/>
Belirlenecek karakter.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, karakter test koşulunu karşılıyorsa sıfır olmayan bir değer döndürür veya değilse 0 olur. *C* < = 255 ise ve karşılık gelen bir **_ismbb** yordamı varsa (örneğin, **_ismbcalnum** , **_ismbbalnum**öğesine karşılık gelir), sonuç karşılık gelen **_ismbb** yordamının dönüş değeridir.

Bu işlevlerin sürümleri aynıdır, ancak **_l** sonekine sahip olanlar, geçerli yerel ayar yerine yerel ayara bağlı davranışı için geçirilen yerel ayarı kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, belirli bir koşul için verilen bir çok baytlı karakteri sınar.

|Yordam|Test koşulu|Kod sayfası 932 örneği|
|-------------|--------------------|---------------------------|
|**_ismbcgraph**|Graphic|Ve yalnızca *c* , boşluk () dışında HERHANGI bir ASCII veya Katakana yazılabilir karakterinin tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür.|
|**_ismbcprint**|Görüntünüzün|Ve yalnızca *c* , boşluk () dahil olmak üzere HERHANGI bir ASCII veya Katakana yazılabilir karakterinin tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür.|
|**_ismbcpunct**|Noktalama işaretleri|Yalnızca *c* , HERHANGI bir ASCII veya Katakana noktalama karakterinin tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür.|
|**_ismbcblank**|Boşluk veya yatay sekme|Yalnızca *c* bir boşluk veya yatay sekme karakteriyse sıfır olmayan bir değer döndürür: *c*= 0x20 veya *c*= 0x09.|
|**_ismbcspace**|Boşluk|Yalnızca *c* bir boşluk karakteri ise, sıfır dışında bir değer döndürür: *c*= 0x20 veya 0x09 < =*c*< = 0x0D.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbcgraph**|\<mbstring. h >|
|**_ismbcgraph_l**|\<mbstring. h >|
|**_ismbcprint**|\<mbstring. h >|
|**_ismbcprint_l**|\<mbstring. h >|
|**_ismbcpunct**|\<mbstring. h >|
|**_ismbcpunct_l**|\<mbstring. h >|
|**_ismbcblank**|\<mbstring. h >|
|**_ismbcblank_l**|\<mbstring. h >|
|**_ismbcspace**|\<mbstring. h >|
|**_ismbcspace_l**|\<mbstring. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
