---
title: isgraph, iswgraph, _isgraph_l, _iswgraph_l
ms.date: 11/04/2016
apiname:
- isgraph
- iswgraph
- _iswgraph_l
- _isgraph_l
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
- _isgraph_l
- _iswgraph_l
- _ismbcgraph_l
- Isgraph
- _istgraph_l
- _istgraph
- iswgraph
helpviewer_keywords:
- isgraph function
- _istgraph_l function
- istgraph function
- _isgraph_l function
- iswgraph function
- _iswgraph_l function
- _istgraph function
- _ismbcgraph_l function
ms.assetid: 531a5f34-4302-4d0a-8a4f-b7ea150ad941
ms.openlocfilehash: af3fae11536a869c0c3e3ebae285ebbaca5ea907
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50664808"
---
# <a name="isgraph-iswgraph-isgraphl-iswgraphl"></a>isgraph, iswgraph, _isgraph_l, _iswgraph_l

Bir tamsayı bir grafik karakterini temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isgraph(
   int c
);
int iswgraph(
   wint_t c
);
int _isgraph_l(
   int c,
   _locale_t locale
);
int _iswgraph_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Test edilecek tamsayı.

## <a name="return-value"></a>Dönüş Değeri

Yordamların her biri bu döndürür sıfır olmayan *c* belirli bir gösterimiyse boşluk dışında yazdırılabilir bir karakter. **isgraph** sıfır olmayan bir değer döndürür *c* boşluk dışında yazdırılabilir bir karakterse. **iswgraph** sıfır olmayan bir değer döndürür *c* olduğu geniş karakter boşluğu dışında yazdırılabilir geniş karakter. Bu yordamların her biri 0 döndürür *c* test koşulu karşılamayan.

Sahip bu işlevlerin sürümleri **_l** soneki yerel ayara bağlı davranışları için geçerli yerel ayarı yerine iletilen yerel ayarı kullanır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Davranışını **isgraph** ve **_isgraph_l** tanımsızdır *c* EOF değilse veya 0-0xFF aralığındaysa aralığında. Bir hata ayıklama CRT Kitaplığı kullanıldığında ve *c* değil, bu değerleri işlevleri raise onaylama biridir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istgraph**|**isgraph**|[_ismbcgraph](ismbcgraph-functions.md)|**iswgraph**|
|**_istgraph_l**|**_isgraph_l**|[_ismbcgraph_l](ismbcgraph-functions.md)|**_iswgraph_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isgraph**|\<CType.h >|
|**iswgraph**|\<CType.h > veya \<wchar.h >|
|**_isgraph_l**|\<CType.h >|
|**_iswgraph_l**|\<CType.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
