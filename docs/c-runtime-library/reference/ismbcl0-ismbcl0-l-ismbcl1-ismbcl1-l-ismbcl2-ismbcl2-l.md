---
title: _ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l
ms.date: 11/04/2016
apiname:
- _ismbcl2
- _ismbcl1
- _ismbcl0
- _ismbcl2_l
- _ismbcl1_l
- _ismbcl0_l
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
- ismbcl0
- _ismbcl1_l
- _ismbcl0
- ismbcl1
- ismbcl0_l
- _ismbcl2_l
- ismbcl2
- ismbcl1_l
- _ismbcl1
- _ismbcl0_l
- _ismbcl2
- ismbcl2_l
helpviewer_keywords:
- _ismbcl0_l function
- _ismbcl2 function
- _ismbcl1_l function
- ismbcl2 function
- _ismbcl1 function
- ismbcl0_l function
- ismbcl2_l function
- ismbcl1_l function
- ismbcl0 function
- ismbcl1 function
- _ismbcl2_l function
- _ismbcl0 function
ms.assetid: ee15ebd1-462c-4a43-95f3-6735836d626a
ms.openlocfilehash: b4ea5a165e5fb06229c3fdf69c53cdf82c4f35f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430894"
---
# <a name="ismbcl0-ismbcl0l-ismbcl1-ismbcl1l-ismbcl2-ismbcl2l"></a>_ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l

**Kod sayfası 932 özel işlevler**, geçerli yerel ayarı veya belirtilen LC_CTYPE dönüştürme durumu kategorisini kullanarak.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _ismbcl0(
   unsigned int c
);
int _ismbcl0_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcl1(
   unsigned int c
);
int _ismbcl1_l(
   unsigned int c ,
   _locale_t locale
);
int _ismbcl2(
   unsigned int c
);
int _ismbcl2_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Test edilecek karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Karakter test koşulunu veya 0 karşılıyorsa kullanmıyorsa bu yordamların her biri sıfır dışında bir değeri döndürür. Varsa *c* < = 255 ve karşılık gelen **_ismbb** yordamı (örneğin, **_ismbcalnum** karşılık gelen **_ismbbalnum**), Sonuç, karşılık gelen dönüş değeri olduğu **_ismbb** yordamı.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, belirli bir koşul için belirli bir çok baytlı karakteri test eder.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı kullanır bu yerel ayara bağlı davranışı için; sürümleriyle **_l** sonekine bunların yerel ayar parametresini kullanmalarıdır Bunun yerine iletilmiş. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

|Yordam|Test koşulu (yalnızca kod sayfası 932)|
|-------------|-------------------------------------------|
|**_ismbcl0**|JIS olmayan Kanji: 0x8140 < =*c*< 0x889E =.|
|**_ismbcl0_l**|JIS olmayan Kanji: 0x8140 < =*c*< 0x889E =.|
|**_ismbcl1**|Düzey JIS-1: 0x889F < =*c*< 0x9872 =.|
|**_ismbcl1_l**|Düzey JIS-1: 0x889F < =*c*< 0x9872 =.|
|**_ismbcl2**|JIS düzey 2: 0x989F < =*c*< 0xEAA4 =.|
|**_ismbcl2_l**|JIS düzey 2: 0x989F < =*c*< 0xEAA4 =.|

İşlevleri kontrol belirtilen değere *c* test koşulları yukarıda açıklanan ancak denetlemez eşleşme *c* geçersiz bir çok baytlı karakter. Düşük bayt 0x00-0x3F, 0x7F veya 0xFD - aralıklardaki 0xFF aralıklarındaysa, bu işlevler, karakterin sınama koşulunu karşıladığını belirterek sıfır dışında bir değeri döndürür. Kullanım [_ismbbtrail](ismbbtrail-ismbbtrail-l.md) çok baytlı karakterin tanımlanıp tanımlanmadığını sınamak için.

**End kod sayfası 932 özel**

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbcl0**|\<Mbstring.h >|
|**_ismbcl0_l**|\<Mbstring.h >|
|**_ismbcl1**|\<Mbstring.h >|
|**_ismbcl1_l**|\<Mbstring.h >|
|**_ismbcl2**|\<Mbstring.h >|
|**_ismbcl2_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
