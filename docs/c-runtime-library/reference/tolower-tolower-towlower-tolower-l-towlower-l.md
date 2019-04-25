---
title: tolower, _tolower, towlower, _tolower_l, _towlower_l
ms.date: 11/04/2016
apiname:
- _tolower_l
- towlower
- tolower
- _tolower
- _towlower_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _totlower
- tolower
- _tolower
- towlower
helpviewer_keywords:
- tolower_l function
- _tolower_l function
- totlower function
- string conversion, to different characters
- lowercase, converting to
- tolower function
- string conversion, case
- towlower function
- _tolower function
- _totlower function
- towlower_l function
- case, converting
- characters, converting
- _towlower_l function
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
ms.openlocfilehash: f7d017235eddb19b08353dceb332a2721e7434aa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155528"
---
# <a name="tolower-tolower-towlower-tolowerl-towlowerl"></a>tolower, _tolower, towlower, _tolower_l, _towlower_l

Bir karakteri küçük harfe dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
int tolower(
   int c
);
int _tolower(
   int c
);
int towlower(
   wint_t c
);
int _tolower_l(
   int c,
   _locale_t locale
);
int _towlower_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Dönüştürülecek karakter.

*Yerel ayar*<br/>
Yerel ayara özgü çeviri için kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri bir kopyasını dönüştürür *c* dönüştürme mümkündür ve sonucu döndürür, küçük harfe. Dönüş değeri bir hatayı göstermek için ayrılmış.

## <a name="remarks"></a>Açıklamalar

Olası ve ilgili ise bu yordamların her biri belirli bir büyük harf küçük harfle dönüştürür. Büyük/küçük harfe dönüştürülmesi **towlower** yerel ayara özgü olan. Yalnızca karakterler geçerli yerel ayarına uygun durumda değiştirilir. İşlevlerin **_l** soneki kullanıp ayarlanmış yerel ayar. Sahip bu işlevlerin sürümleri **_l** soneki yerel ayar bir parametre olarak almak ve ayarlanmış yerine kullanan yerel ayar. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Sırayla **_tolower** beklenen sonuçları elde etmek için [__isascii](isascii-isascii-iswascii.md) ve [isupper](isupper-isupper-l-iswupper-iswupper-l.md) her ikisi de sıfır olmayan döndürmelidir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totlower**|**tolower**|**_mbctolower**|**towlower**|
|**_totlower_l**|**_tolower_l**|**_mbctolower_l**|**_towlower_l**|

> [!NOTE]
> **_tolower_l** ve **_towlower_l** öğelerinin yerel bağımlılığı olan ve doğrudan çağrılmak için değildirler. Tarafından iç kullanım için sağlanan **_totlower_l**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**tolower**|\<CType.h >|
|**_tolower**|\<CType.h >|
|**towlower**|\<CType.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örnekte bakın [işlevlere](../../c-runtime-library/to-functions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[to İşlevleri](../../c-runtime-library/to-functions.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
