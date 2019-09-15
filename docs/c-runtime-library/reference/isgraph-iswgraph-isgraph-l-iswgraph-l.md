---
title: isgraph, iswgraph, _isgraph_l, _iswgraph_l
ms.date: 11/04/2016
api_name:
- isgraph
- iswgraph
- _iswgraph_l
- _isgraph_l
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 88219ca6dc4218fc13f7d7c0b5f2ba399c07d501
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954872"
---
# <a name="isgraph-iswgraph-_isgraph_l-_iswgraph_l"></a>isgraph, iswgraph, _isgraph_l, _iswgraph_l

Bir tamsayının bir grafik karakterini temsil edip etmediğini belirler.

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
Sınanacak tamsayı.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, *c* , boşluk dışında yazdırılabilir bir karakterin belirli bir gösterimiyse sıfır olmayan bir değer döndürür. *c* , boşluk dışında yazdırılabilir bir karakter ise, **ısgraph** sıfır dışında bir değer döndürür. *c* , geniş bir karakter alanından başka bir yazdırılabilir geniş karakter ise, **ıswgraph** sıfır dışında bir değer döndürür. Bu yordamların her biri, *c* , test koşulunu karşılamadığı takdirde 0 döndürür.

**_L** sonekine sahip bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayar yerine geçirilen yerel ayarı kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*C* , EOF veya 0 ile 0xFF (dahil) aralığında değilse, **isgraph** ve **_isgraph_l** davranışı tanımsızdır. Bir hata ayıklama CRT kitaplığı kullanıldığında ve *c* bu değerlerden biri değilse, işlevler bir onaylama işlemi yükseltir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istgraf**|**isgraph**|[_ismbcgraph](ismbcgraph-functions.md)|**iswgraf**|
|**_istgraph_l**|**_isgraph_l**|[_ismbcgraph_l](ismbcgraph-functions.md)|**_iswgraph_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isgraph**|\<CType. h >|
|**iswgraf**|\<CType. h > veya \<wchar. h >|
|**_isgraph_l**|\<CType. h >|
|**_iswgraph_l**|\<CType. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
