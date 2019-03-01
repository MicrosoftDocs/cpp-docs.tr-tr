---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l
ms.date: 11/04/2016
apiname:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- towupper
- _toupper
- _totupper
- toupper
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
ms.openlocfilehash: 6dd564a27ee7f3c2bb095564e5c9423249d6babc
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210620"
---
# <a name="toupper-toupper-towupper-toupperl-towupperl"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l

Karakteri büyük harfe Dönüştür.

## <a name="syntax"></a>Sözdizimi

```C
int toupper(
   int c
);
int _toupper(
   int c
);
int towupper(
   wint_t c
);
int _toupper_l(
   int c ,
   _locale_t locale
);
int _towupper_l(
   wint_t c ,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Dönüştürülecek karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri bir kopyasını dönüştürür *c*, mümkün olduğunda ve sonucu döndürür.

Varsa *c* bir geniş karakter olduğu **iswlower** sıfır dışında olan ve bir karşılık gelen geniş karakter [iswupper](isupper-isupper-l-iswupper-iswupper-l.md) sıfır değilse, **towupper** karşılık gelen geniş karakter; döndürür Aksi takdirde, **towupper** döndürür *c* değişmez.

Dönüş değeri bir hatayı göstermek için ayrılmış.

Sırayla **toupper** beklenen sonuçları elde etmek için [__isascii](isascii-isascii-iswascii.md) ve [islower](islower-iswlower-islower-l-iswlower-l.md) her ikisi de sıfır olmayan döndürmelidir.

## <a name="remarks"></a>Açıklamalar

Bu yordamların her biri, belirli bir küçük harf mümkünse büyük harfe dönüştürür ve uygun. Büyük/küçük harfe dönüştürülmesi **towupper** yerel ayara özgü olan. Yalnızca karakterler geçerli yerel ayarına uygun durumda değiştirilir. İşlevlerin **_l** soneki kullanıp ayarlanmış yerel ayar. Sahip bu işlevlerin sürümleri **_l** soneki yerel ayar bir parametre olarak almak ve ayarlanmış yerine kullanan yerel ayar. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Sırayla **toupper** beklenen sonuçları elde etmek için [__isascii](isascii-isascii-iswascii.md) ve [isupper](isupper-isupper-l-iswupper-iswupper-l.md) her ikisi de sıfır olmayan döndürmelidir.

[Veri dönüştürme rutinleri](../../c-runtime-library/data-conversion.md)

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**toupper**|**_mbctoupper**|**towupper**|
|**_totupper_l**|**_toupper_l**|**_mbctoupper_l**|**_towupper_l**|

> [!NOTE]
> **_toupper_l** ve **_towupper_l** öğelerinin yerel bağımlılığı olan ve doğrudan çağrılmak için değildirler. Tarafından iç kullanım için sağlanan **_totupper_l**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**toupper**|\<CType.h >|
|**_toupper**|\<CType.h >|
|**towupper**|\<CType.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örnekte bakın [işlevlere](../../c-runtime-library/to-functions.md).

## <a name="see-also"></a>Ayrıca bkz.

[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[to İşlevleri](../../c-runtime-library/to-functions.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
