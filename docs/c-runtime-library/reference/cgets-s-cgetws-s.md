---
title: _cgets_s, _cgetws_s
ms.date: 4/2/2020
api_name:
- _cgetws_s
- _cgets_s
- _o__cgets_s
- _o__cgetws_s
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b4871ff2c362e2c6cbe37be6a31bde4e6e258709
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333539"
---
# <a name="_cgets_s-_cgetws_s"></a>_cgets_s, _cgetws_s

Konsoldan bir karakter dizesi alır. [_cgets ve _cgetws](../../c-runtime-library/cgets-cgetws.md) bu [sürümlerinde, CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleri vardır.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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
Veriler için depolama konumu.

*numberOfElements*<br/>
Tek bayt veya geniş karakterlerdeki arabelleğin boyutu, aynı zamanda okunacak en fazla karakter sayısıdır.

*pSizeRead*<br/>
Karakterlerin sayısı gerçekten okunur.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa geri dönüş değeri sıfırdır; aksi takdirde, bir hata oluşursa bir hata kodu.

### <a name="error-conditions"></a>Hata Koşulları

|*Arabellek*|*numberOfElements*|*pSizeRead*|Dönüş|*Arabellek* içeriği|
|--------------|------------------------|-----------------|------------|--------------------------|
|**Null**|herhangi bir|herhangi bir|**Eınval**|yok|
|**NULL** değil|sıfır|herhangi bir|**Eınval**|değiştirilmemiş|
|**NULL** değil|herhangi bir|**Null**|**Eınval**|sıfır uzunlukta dize|

## <a name="remarks"></a>Açıklamalar

**_cgets_s** ve **_cgetws_s** konsoldan bir dize okumak ve *arabellek*içine dize (null terminator ile) kopyalayın. **_cgetws_s** fonksiyonun geniş karakter versiyonudur; karakter boyutu dışında, bu iki işlevin davranışı aynıdır. Okunacak dizenin en büyük boyutu *numberOfElements* parametresi olarak geçirilir. Bu boyut, sonlandırıcı null için ek bir karakter içermelidir. Okunan karakterlerin gerçek sayısı *pSizeRead*yerleştirilir.

İşlem sırasında veya parametrelerin doğrulanması sırasında bir hata oluşursa, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve **EINVAL** döndürülür.

C++'da, bu işlevlerin kullanımı şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkararak boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir ve daha eski, daha az güvenli işlevleri daha yeni ve daha güvenli karşılıklarıyla otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_cgetts_s**|**_cgets_s**|**_cgets_s**|**_cgetws_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cgets_s**|\<conio.h>|
|**_cgetws_s**|\<conio.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve Bağlantı Noktası G/Ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
