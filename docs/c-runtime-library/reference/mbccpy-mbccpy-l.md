---
title: _mbccpy, _mbccpy_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbccpy
- _mbccpy_l
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
- _mbccpy
- tccpy
- ftccpy
- mbccpy
- _tccpy
- _ftccpy
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d79ab8362eaa911b7a4aa936d6351aa29f610fa8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="mbccpy-mbccpyl"></a>_mbccpy, _mbccpy_l

Birden çok baytlı karakter başka bir dizeye bir dizeden kopyalar. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_mbccpy_s, _mbccpy_s_l](mbccpy-s-mbccpy-s-l.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Hedef* kopyalama hedefi.

*src* kopyalamak için birden çok baytlı karakter.

*yerel ayar* kullanılacak yerel ayar.

## <a name="remarks"></a>Açıklamalar

**_Mbccpy** işlevi bir çok baytlı karakter kopyalar *src* için *taşınmaya*.

Bu işlev parametrelerini doğrular. Varsa **_mbccpy** null işaretçi geçirilen *taşınmaya* veya *src*, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL**.

**_mbccpy** için tüm yerel ayara bağımlı davranış geçerli yerel ayarı kullanır. **_mbccpy_l** aynıdır **_mbccpy** dışında **_mbccpy_l** geçirilen tüm yerel ayara bağımlı davranışını yerel ayar kullanır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

**Güvenlik Notu** null sonlandırılmış bir dize kullanın. Sonlandırılmış dize hedef arabellek boyutunu aşmamalıdır. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795). Arabellek Taşması, sık yöntemi bir unwarranted ayrıcalıkların sonuçlanan sistem saldırı sorunlardır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy**|Makro veya satır içi işlev eşlemeleri|**_mbccpy**|Makro veya satır içi işlev eşlemeleri|
|**_tccpy_l**|yok|**_mbccpy_l**|yok|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbccpy**|\<Mbctype.h >|
|**_mbccpy_l**|\<Mbctype.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
