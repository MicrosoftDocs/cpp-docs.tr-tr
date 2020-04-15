---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l
ms.date: 4/2/2020
api_name:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
- _o__toupper
- _o__toupper_l
- _o__towupper_l
- _o_toupper
- _o_towupper
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 85c218fdb3f5153e572e434bffbdb64510554d07
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362318"
---
# <a name="toupper-_toupper-towupper-_toupper_l-_towupper_l"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l

Karakteri büyük harfe dönüştürün.

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

*C*<br/>
Karakter dönüştürmek için.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri *mümkünse c'nin*bir kopyasını dönüştürür ve sonucu döndürür.

*Eğer c,* **iswlower** sıfır olmayan geniş bir karakter ise ve [iswupper](isupper-isupper-l-iswupper-iswupper-l.md) sıfır olmayan karşılık gelen geniş bir karakter varsa, **çekme** karşılık gelen geniş karakter döndürür; aksi takdirde, **çekme c** *değişmeden* döner.

Bir hatayı belirtmek için ayrılmış bir iade değeri yoktur.

**Toupper'ın** beklenen sonuçları verebilmesi [için, __isascii](isascii-isascii-iswascii.md) ve [daha düşük](islower-iswlower-islower-l-iswlower-l.md) olması için her ikisinin de sıfırsız dönmesi gerekir.

## <a name="remarks"></a>Açıklamalar

Bu yordamların her biri, mümkünse ve uygunsa, belirli bir küçük harfi bir büyük harfe dönüştürür. **Çekme** servis talebinin dönüştürülmesi yerele özgüdür. Duruma göre yalnızca geçerli yerel eşle ilgili karakterler değiştirilir. **_l** sonek olmayan işlevler, şu anda ayarlanmış yerel ayaryı kullanır. Bu işlevlerin **_l** sonekli sürümleri yerel alanı bir parametre olarak alır ve şu anda ayarlanmış yerel ayar yerine bunu kullanır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

**Toupper'ın** beklenen sonuçları verebilmesi [için, __isascii](isascii-isascii-iswascii.md) ve [isupper'ın](isupper-isupper-l-iswupper-iswupper-l.md) her ikisinin de sıfırsız dönmesi gerekir.

[Veri Dönüştürme Yordamları](../../c-runtime-library/data-conversion.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**Toupper**|**_mbctoupper**|**çekme**|
|**_totupper_l**|**_toupper_l**|**_mbctoupper_l**|**_towupper_l**|

> [!NOTE]
> **_toupper_l** ve **_towupper_l** yerel bağımlılık yoktur ve doğrudan çağrılmamalıdır. **Onlar _totupper_l**tarafından iç kullanım için sağlanmaktadır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Toupper**|\<ctype.h>|
|**_toupper**|\<ctype.h>|
|**çekme**|\<ctype.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[İşlevler'deki](../../c-runtime-library/to-functions.md)örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
[to İşlevleri](../../c-runtime-library/to-functions.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
