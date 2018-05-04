---
title: _cgets_s, _cgetws_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _cgetws_s
- _cgets_s
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cgets_s
- cgets_s
- cgetws_s
- _cgetws_s
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], getting from console
- console, getting strings from
- _cgets_s function
- cget_s function
- _cgetws_s function
- cgetws_s function
ms.assetid: 38b74897-afe6-4dd9-a43f-36a3c0d72c5c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48b00f9eee699b7e556c2fcc3f88abd8d783a261
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="cgetss-cgetwss"></a>_cgets_s, _cgetws_s

Bir karakter dizesi konsoldan alır. Bu sürümleri [_cgets ve _cgetws](../../c-runtime-library/cgets-cgetws.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _cgets_s(
   char *buffer,
   size_t numberOfElements,
   size_t *pSizeRead
);
errno_t _cgetws_s(
   wchar_t *buffer
   size_t numberOfElements,
   size_t *pSizeRead
);
template <size_t size>
errno_t _cgets_s(
   char (&buffer)[size],
   size_t *pSizeRead
); // C++ only
template <size_t size>
errno_t _cgetws_s(
   wchar_t (&buffer)[size],
   size_t *pSizeRead
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Verileri için depolama konumu.

*numberOfElements*<br/>
Okunacak karakter üst sınırını aynı zamanda olan tek baytlı veya uluslararası karakter, arabellek boyutu.

*pSizeRead*<br/>
Gerçekte okunan karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri başarılı olursa sıfırdır; Aksi takdirde bir hata bir hata oluşursa kodu.

### <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*numberOfElements*|*pSizeRead*|Döndür|İçeriği *arabellek*|
|--------------|------------------------|-----------------|------------|--------------------------|
|**NULL**|tüm|tüm|**EINVAL**|yok|
|değil **NULL**|sıfır|tüm|**EINVAL**|değiştirilmedi|
|değil **NULL**|tüm|**NULL**|**EINVAL**|sıfır uzunlukta bir dize|

## <a name="remarks"></a>Açıklamalar

**_cgets_s** ve **_cgetws_s** bir dize konsoldan okunan ve dizesiyle (null Sonlandırıcı) kopyalayın *arabellek*. **_cgetws_s** dışında karakter boyutu, bu iki işlevler davranışını aynıdır; işlevi, geniş karakter sürümüdür. Okunacak dize en büyük boyutu olarak geçirilen *numberOfElements* parametresi. Bu boyut sonlandırma null için fazladan bir karakter içermelidir. Okuma karakter gerçek sayısını yerleştirilir *pSizeRead*.

İşlemi sırasında veya parametrelerinin doğrulanırken bir hata meydana gelirse, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve **EINVAL** döndürülür.

C++'da, Bu işlevlerden birinin kullanımını şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı otomatik olarak, böylece bir boyutu bağımsız değişkeniyle belirtmek için gereksinimini arabellek uzunluğu çıkarımını ve bunlar otomatik olarak yeni, daha güvenli dekiler ile daha eski, daha az güvenli işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_cgetts_s**|**_cgets_s**|**_cgets_s**|**_cgetws_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cgets_s**|\<conio.h >|
|**_cgetws_s**|\<conio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
