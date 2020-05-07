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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: a265a37ba4c16dd15e6b50035dcc65bc8afbe7c7
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919576"
---
# <a name="_mbccpy-_mbccpy_l"></a>_mbccpy, _mbccpy_l

Çok baytlı bir karakteri bir dizeden başka bir dizeye kopyalar. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_mbccpy_s, _mbccpy_s_l](mbccpy-s-mbccpy-s-l.md).

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*HD*<br/>
Hedefi Kopyala.

*src*<br/>
Kopyalanacak çok baytlı karakter.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="remarks"></a>Açıklamalar

**_Mbccpy** işlevi bir çok baytlı karakteri *src* 'den *hedefe*kopyalar.

Bu işlev, parametrelerini doğrular. **_Mbccpy** *hedef* veya *src*için null bir işaretçi geçirtiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL**olarak ayarlanır.

**_mbccpy** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_mbccpy_l** , **_mbccpy** bir yerel ayara bağımlı davranış için geçirilen yerel ayarı kullanması dışında, **_mbccpy_l** aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

**Güvenlik notunun** Null ile sonlandırılmış bir dize kullanın. Null ile sonlandırılmış dize, hedef arabelleğin boyutunu aşmamalıdır. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns). Arabellek taşması sorunları, sistem saldırılarına karşı sık kullanılan bir yöntemdir ve bu da garanti edilmemiş ayrıcalık yükselmesine neden olur.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy**|Makroya veya satır içi işleve eşlenir|**_mbccpy**|Makroya veya satır içi işleve eşlenir|
|**_tccpy_l**|yok|**_mbccpy_l**|yok|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbccpy**|\<Mbctype. h>|
|**_mbccpy_l**|\<Mbctype. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
