---
title: _cgets_s, _cgetws_s
ms.date: 11/04/2016
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
helpviewer_keywords:
- strings [C++], getting from console
- console, getting strings from
- _cgets_s function
- cget_s function
- _cgetws_s function
- cgetws_s function
ms.assetid: 38b74897-afe6-4dd9-a43f-36a3c0d72c5c
ms.openlocfilehash: 8341b775df3b9cbaececdfaa1f17e075d7c7416c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340591"
---
# <a name="cgetss-cgetwss"></a>_cgets_s, _cgetws_s

Konsoldan bir karakter dizesi alır. Bu sürümleri [_cgets ve _cgetws](../../c-runtime-library/cgets-cgetws.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Veri için depolama konumu.

*numberOfElements*<br/>
Okunacak karakter sayısı olan tek baytlı veya geniş karakterler, arabellek boyutu.

*pSizeRead*<br/>
Aslında okunan karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır dönüş değeridir; Aksi takdirde bir hata kodu: bir hata oluşması durumunda.

### <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*numberOfElements*|*pSizeRead*|döndürülecek|İçeriğini *arabelleği*|
|--------------|------------------------|-----------------|------------|--------------------------|
|**NULL**|Tüm|Tüm|**EINVAL**|yok|
|Değil **NULL**|sıfır|Tüm|**EINVAL**|değiştirilmedi|
|Değil **NULL**|Tüm|**NULL**|**EINVAL**|sıfır uzunluklu bir dize|

## <a name="remarks"></a>Açıklamalar

**_cgets_s** ve **_cgetws_s** konsoldan okuyup bir dize ve dize (ile bir null Sonlandırıcı) kopyalayın *arabellek*. **_cgetws_s** dışında karakter boyutu, bu iki işlev davranışını aynıdır; işlevin geniş karakter sürümüdür. Dizeyi okumak için en büyük boyutu olarak geçirilen *numberOfElements* parametresi. Bu boyut, ek bir sonlandırıcı null karakteri içermelidir. Okunan karakter sayısını yerleştirilir *pSizeRead*.

İşlemi sırasında ya da parametrelerinin doğrularken bir hata meydana gelirse, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve **EINVAL** döndürülür.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak, böylece bir boyut bağımsız değişkeni belirtme ihtiyacını ortadan kaldırır. çıkarabilir ve bunlar otomatik olarak eski ve daha az güvenli işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_cgetts_s**|**_cgets_s**|**_cgets_s**|**_cgetws_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cgets_s**|\<conio.h >|
|**_cgetws_s**|\<conio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
