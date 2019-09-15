---
title: _ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l
ms.date: 11/04/2016
api_name:
- _ismbclegal_l
- _ismbclegal
- _ismbcsymbol
- _ismbcsymbol_l
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
- ismbcsymbol_l
- _ismbcsymbol_l
- _ismbcsymbol
- _ismbclegal_l
- _ismbclegal
- ismbclegal_l
- ismbcsymbol
- ismbclegal
helpviewer_keywords:
- ismbcsymbol function
- ismbclegal_l function
- _istlegal_l function
- istlegal function
- _istlegal function
- _ismbcsymbol function
- _ismbclegal_l function
- ismbclegal function
- ismbcsymbol_l function
- _ismbclegal function
- _ismbcsymbol_l function
- istlegal_l function
ms.assetid: 31bf1ea5-b56f-4e28-b21e-b49a2cf93ffc
ms.openlocfilehash: 4e040db584725322e98d0a82b28912eea100aff7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953798"
---
# <a name="_ismbclegal-_ismbclegal_l-_ismbcsymbol-_ismbcsymbol_l"></a>_ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l

Çok baytlı bir karakterin geçerli veya sembol karakteri olup olmadığını denetler.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _ismbclegal(
   unsigned int c
);
int _ismbclegal_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcsymbol(
   unsigned int c
);
int _ismbcsymbol_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Sınanacak karakter.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, karakter test koşulunu karşılıyorsa veya 0 değilse sıfır dışında bir değer döndürür. *C*< = 255 ise ve karşılık gelen bir **_ismbb** yordamı varsa (örneğin, **_ismbcalnum** , **_ismbbalnum**öğesine karşılık gelir), sonuç karşılık gelen **_ismbb** yordamının dönüş değeridir.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, belirli bir koşul için verilen bir çok baytlı karakteri sınar.

**_L** sonekine sahip bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayar yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

|Yordam|Test koşulu|Kod sayfası 932 örneği|
|-------------|--------------------|---------------------------|
|**_ismbclegal**|Geçerli çok baytlı|Yalnızca *c* 'nin ilk baytı 0x81-0x9F veya 0xE0-0xFC aralığında ise, ikinci bayt 0x40-0x7E veya 0X80-FC aralığında olduğunda sıfır olmayan bir değer döndürür.|
|**_ismbcsymbol**|Çok baytlı simgesi|Yalnızca 0x8141 < =*c*< = 0x81AC ise sıfır dışında bir değer döndürür.|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istyasal**|Her zaman yanlış döndürür|**_ismbclegal**|Her zaman false döndürür.|
|**_istlegal_l**|Her zaman yanlış döndürür|**_ismbclegal_l**|Her zaman false döndürür.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbclegal**, **_ismbclegal_l**|\<mbstring. h >|
|**_ismbcsymbol**, **_ismbcsymbol_l**|\<mbstring. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
