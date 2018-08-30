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
ms.openlocfilehash: 8fca6772c00715722acecd810595a42c60f77d86
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201393"
---
# <a name="mbccpy-mbccpyl"></a>_mbccpy, _mbccpy_l

Çok baytlı karakteri bir dizeden başka bir dizeye kopyalar. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_mbccpy_s, _mbccpy_s_l](mbccpy-s-mbccpy-s-l.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*src* kopyalanacak çok baytlı karakter.

*yerel ayar* kullanılacak yerel ayar.

## <a name="remarks"></a>Açıklamalar

**_Mbccpy** işlevi bir çok baytlı karakter kopyalar *src* için *dest*.

Bu işlev, parametrelerini doğrular. Varsa **_mbccpy** bir null işaretçi geçirildi *dest* veya *src*, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL**.

**_mbccpy** herhangi bir yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_mbccpy_l** aynıdır **_mbccpy** dışında **_mbccpy_l** herhangi bir yerel ayara bağımlı davranış için geçirilen yerel ayarı kullanır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

**Güvenlik Notu** null ile sonlandırılmış bir dize kullanın. Null ile sonlandırılmış dize hedef arabelleğinin boyutunu aşamaz. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns). Arabellek taşması sorunları, sistem saldırı, bir unwarranted ayrıcalık yükseltilmesi ile sonuçlanan sık kullanılan bir yöntemdir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy**|Makro veya satır içi işleve eşlenir|**_mbccpy**|Makro veya satır içi işleve eşlenir|
|**_tccpy_l**|yok|**_mbccpy_l**|yok|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbccpy**|\<Mbctype.h >|
|**_mbccpy_l**|\<Mbctype.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
