---
title: _mbccpy, _mbccpy_l
ms.date: 4/2/2020
api_name:
- _mbccpy
- _mbccpy_l
- _o__mbccpy
- _o__mbccpy_l
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
- _mbccpy
- tccpy
- ftccpy
- mbccpy
- _tccpy
- _ftccpy
helpviewer_keywords:
- _tccpy function
- _tccpy_l function
- tccpy_l function
- tccpy function
- mbccpy function
- _mbccpy_l function
- _mbccpy function
- mbccpy_l function
ms.assetid: 13f4de6e-7792-41ac-b319-dd9b135433aa
ms.openlocfilehash: 45f93e370e11cf38fc17da3557b21c636fcbc623
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341260"
---
# <a name="_mbccpy-_mbccpy_l"></a>_mbccpy, _mbccpy_l

Çok baytlı bir karakteri bir dizeden diğerine kopyalar. Bu işlevlerin daha güvenli sürümleri mevcuttur; [_mbccpy_s, _mbccpy_s_l](mbccpy-s-mbccpy-s-l.md)bakın.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
void _mbccpy(
   unsigned char *dest,
   const unsigned char *src
);
void _mbccpy_l(
   unsigned char *dest,
   const unsigned char *src,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Dest*<br/>
Hedefi kopyalayın.

*src*<br/>
Kopyalanması gereken çok bayt karakter.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="remarks"></a>Açıklamalar

**_mbccpy** işlevi *src* den *dest*bir multibayt karakter kopyalar.

Bu işlev parametrelerini doğrular. **_mbccpy** *dest* veya *src*için null işaretçisi geçirilirse, Geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, **errno** **EINVAL**olarak ayarlanır.

**_mbccpy,** yerel e-eşe bağlı herhangi bir davranış için geçerli yerel alanı kullanır. **_mbccpy_l,** **_mbccpy_l'nin** herhangi bir yerele bağımlı davranış için geçirilen yerelliği kullanması dışında **_mbccpy** ile aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

**Güvenlik Notu** Null-terminatedli dize kullanın. Null-sonlandırılan dize hedef arabellek boyutunu aşmamalıdır. Daha fazla bilgi için [bkz.](/windows/win32/SecBP/avoiding-buffer-overruns) Arabellek taşma sorunları, sık karşılaşılan bir sistem saldırısı yöntemidir ve bu da haksız bir ayrıcalık yükselmesine neden olabilir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy**|Makro veya satır çizgisi işlevine eşler|**_mbccpy**|Makro veya satır çizgisi işlevine eşler|
|**_tccpy_l**|yok|**_mbccpy_l**|yok|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbccpy**|\<mbctype.h>|
|**_mbccpy_l**|\<mbctype.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
