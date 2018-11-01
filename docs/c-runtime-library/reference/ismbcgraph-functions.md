---
title: _ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l
ms.date: 11/04/2016
apiname:
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 05946def8c4d832751554a1653afa98c9965fee9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626219"
---
# <a name="ismbcgraph-ismbcgraphl-ismbcprint-ismbcprintl-ismbcpunct-ismbcpunctl-ismbcblank-ismbcblankl-ismbcspace-ismbcspacel"></a>_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l

Karakterin grafik karakteri, görüntü karakter, noktalama karakteri veya bir boşluk karakteri olup olmadığını belirler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Karakter test koşulunu ya da 0 karşılıyorsa mevcut değilse, bu yordamların her biri sıfır dışında bir değeri döndürür. Varsa *c* < = 255 ve karşılık gelen **_ismbb** yordamı (örneğin, **_ismbcalnum** karşılık gelen **_ismbbalnum**), Sonuç, karşılık gelen dönüş değeri olduğu **_ismbb** yordamı.

Sahip olanlar dışında bu işlevlerin sürümleri özdeş **_l** soneki geçerli yerel ayarı yerine yerel ayara bağlı davranışları için geçirilen yerel ayarı kullanır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, belirli bir koşul için belirli bir çok baytlı karakteri test eder.

|Yordam|Test koşulu|Kod sayfası 932 örneği|
|-------------|--------------------|---------------------------|
|**_ismbcgraph**|Grafiği|Yalnız ve yalnızca döndürür *c* boşluk () dışında bir ASCII veya katakana yazdırılabilir karakter tek bayt gösterimidir.|
|**_ismbcprint**|Yazdırılabilir|Yalnız ve yalnızca döndürür *c* tek baytlık bir gösterimiyse herhangi bir karakterin boşluk () dahil olmak üzere ASCII veya katakana yazdırılabilir.|
|**_ismbcpunct**|Noktalama işaretleri|Yalnız ve yalnızca döndürür *c* herhangi bir ASCII veya katakana noktalama karakterinin tek baytlık gösterimidir.|
|**_ismbcblank**|Boşluk veya yatay sekme|Yalnız ve yalnızca döndürür *c* bir boşluk veya yatay sekme karakterinin: *c*= 0x20 veya *c*= 0x09.|
|**_ismbcspace**|Boşluk|Yalnız ve yalnızca döndürür *c* bir boşluk karakteri: *c*= 0x20 veya 0x09 < =*c*< = 0x0D.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbcgraph**|\<Mbstring.h >|
|**_ismbcgraph_l**|\<Mbstring.h >|
|**_ismbcprint**|\<Mbstring.h >|
|**_ismbcprint_l**|\<Mbstring.h >|
|**_ismbcpunct**|\<Mbstring.h >|
|**_ismbcpunct_l**|\<Mbstring.h >|
|**_ismbcblank**|\<Mbstring.h >|
|**_ismbcblank_l**|\<Mbstring.h >|
|**_ismbcspace**|\<Mbstring.h >|
|**_ismbcspace_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
