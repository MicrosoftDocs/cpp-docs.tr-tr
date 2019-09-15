---
title: _cgets_s, _cgetws_s
ms.date: 11/04/2016
api_name:
- _cgetws_s
- _cgets_s
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
- api-ms-win-crt-conio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 2039fc32cecb768c3c3fbc239446abedeb48f188
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939273"
---
# <a name="_cgets_s-_cgetws_s"></a>_cgets_s, _cgetws_s

Konsolundan bir karakter dizesi alır. [_Cal ve _cgetws](../../c-runtime-library/cgets-cgetws.md) 'nin bu SÜRÜMLERINDE, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*arabelleğin*<br/>
Veriler için depolama konumu.

*numberOfElements*<br/>
Tek baytlık veya geniş karakterdeki arabelleğin boyutu, ayrıca okunacak en fazla karakter sayısıdır.

*pSizeRead*<br/>
Gerçekte okunan karakterlerin sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa dönüş değeri sıfırdır; Aksi takdirde, bir hata oluşursa hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*arabelleğin*|*numberOfElements*|*pSizeRead*|döndürülmesini|*Arabelleğin* içeriği|
|--------------|------------------------|-----------------|------------|--------------------------|
|**DEĞER**|Kaydedilmemiş|Kaydedilmemiş|**EINVAL**|yok|
|**Null** değil|sıfır|Kaydedilmemiş|**EINVAL**|değiştirilmedi|
|**Null** değil|Kaydedilmemiş|**DEĞER**|**EINVAL**|sıfır uzunluklu dize|

## <a name="remarks"></a>Açıklamalar

**_cgets_s** ve **_cgetws_s** konsolundan bir dize okur ve dizeyi (null Sonlandırıcı ile) *arabelleğe*kopyalayın. **_cgetws_s** , işlevinin geniş karakter sürümüdür; karakter boyutu dışında, bu iki işlevin davranışı aynıdır. Okunacak dizenin en büyük boyutu *numberOfElements* parametresi olarak geçirilir. Bu boyut, Sonlandırıcı null değeri için fazladan bir karakter içermelidir. Okunan karakterlerin gerçek sayısı *pSizeRead*içine yerleştirilir.

İşlem sırasında veya parametrelerin doğrulanması sırasında bir hata oluşursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md) bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve **EINVAL** döndürülür.

' C++De, bu işlevlerin kullanımı şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir, böylece bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır ve daha eski, daha az güvenli işlevleri, daha yeni ve daha güvenli karşılıklarıyla otomatik olarak değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_cgetts_s**|**_cgets_s**|**_cgets_s**|**_cgetws_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cgets_s**|\<conio. h >|
|**_cgetws_s**|\<conio. h > veya \<wchar. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
