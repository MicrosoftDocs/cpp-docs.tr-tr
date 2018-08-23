---
title: _putenv_s, _wputenv_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wputenv_s
- _putenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- putenv_s
- wputenv_s
- _wputenv_s
- _putenv_s
dev_langs:
- C++
helpviewer_keywords:
- wputenv_s function
- _putenv_s function
- environment variables, deleting
- putenv_s function
- _wputenv_s function
- environment variables, creating
- environment variables, modifying
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de777c05d3b5186966e78b80e6fb1b10221d031a
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42464645"
---
# <a name="putenvs-wputenvs"></a>_putenv_s, _wputenv_s

Oluşturur, değiştirir veya ortam değişkenlerini kaldırır. Bunlar sürümleridir [_putenv, _wputenv](putenv-wputenv.md) açıklandığı gibi güvenlik geliştirmeleri vardır, ancak [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _putenv_s(
   const char *varname,
   const char *value_string
);
errno_t _wputenv_s(
   const wchar_t *varname,
   const wchar_t *value_string
);
```

### <a name="parameters"></a>Parametreler

*varName*<br/>
Ortam değişkeni adı.

*value_string*<br/>
Ortam değişkenini ayarlamak değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür veya bir hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*varName*|*value_string*|Dönüş değeri|
|------------|-------------|------------------|
|**NULL**|Tüm|**EINVAL**|
|Tüm|**NULL**|**EINVAL**|

Hata durumlardan biri oluşursa, bu işlevler geçersiz parametre işleyicisini de açıklandığı gibi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **EINVAL** ayarlayıp **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Putenv_s** işlevi yeni ortam değişkenleri ekler veya varolan ortam değişkenlerinin değerlerini değiştirir. Ortam değişkenlerini (örneğin, bir programla bağlanacak kitaplıklara varsayılan arama yolu) bir işlem yürütür ortamı tanımlar. **_wputenv_s** geniş karakterli sürümüdür **_putenv_s**; *envstrıng* bağımsız değişkeni **_wputenv_s** geniş karakterli bir dizedir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tputenv_s**|**_putenv_s**|**_putenv_s**|**_wputenv_s**|

*varName* eklenecek veya değiştirilecek ortam değişkenini adıdır ve *value_string* değişkenin değeridir. Varsa *varname* zaten ortamın bir parçası olan alt değer ile değiştirilir *value_string*; Aksi takdirde, yeni *varname* değişkeni ve onun *value_string*  ortama eklenir. Boş bir dize belirterek ortamdan bir değişkeni kaldırabilirsiniz (diğer bir deyişle, "") için *value_string*.

**_putenv_s** ve **_wputenv_s** yalnızca geçerli işlemin yerel olduğu ortamı etkiler; komut düzeyindeki ortamı değiştirmek için kullanamazsınız. Bu işlevler, çalışma zamanı kitaplığının erişilebildiği veri yapıları ve "işletim sistemi için bir işlem oluşturur segment" ortam üzerinde çalışır. Geçerli işlem sonlandırıldığında, ortam, çoğu durumda işletim sistemi düzeyi çağırma işleminin düzeyine döner. Ancak değiştirilmiş ortam tarafından oluşturulan yeni süreçlere geçirilebilir **_spawn**, **_exec**, veya **sistem**, ve bu yeni süreçler olan yeni öğeleri alır. tarafından eklenen **_putenv_s** ve **_wputenv_s**.

Doğrudan bir ortam girdisini değiştirmeyin; Bunun yerine, **_putenv_s** veya **_wputenv_s** değiştirmek için. Özellikle, doğrudan serbest öğeleri **_environ []** genel dizi ele alınması için geçersiz belleğe neden olabilir.

**GETENV** ve **_putenv_s** genel değişkenin **_environ** ; ortam tablosuna erişmek için **_wgetenv** ve **_wputenv_s** kullanın **_wenviron**. **_putenv_s** ve **_wputenv_s** değerini değişebilir **_environ** ve **_wenviron**ve böylece geçersiz *envp*bağımsız değişkeni **ana** ve **_wenvp** bağımsız değişkeni **wmain**. Bu nedenle, kullanılacak güvenli **_environ** veya **_wenviron** ortam bilgilerine erişmek için. İlişkiyi hakkında daha fazla bilgi için **_putenv_s** ve **_wputenv_s** genel değişkenler için bkz. [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv_s** ve **_getenv_s** işlev aileleri iş parçacığı açısından güvenli değildir. **_getenv_s** dize işaretçisini döndürebilir **_putenv_s** dizeyi değiştirme ve böylece rastgele hatalara neden olur. Bu işlevlere aramaların eşitlendiğinden emin olun.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_putenv_s**|\<stdlib.h >|
|**_wputenv_s**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek için **_putenv_s**, bkz: [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
