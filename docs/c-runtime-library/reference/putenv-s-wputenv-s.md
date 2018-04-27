---
title: _putenv_s, _wputenv_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b1baab00d535581f753e512797308cecbc10373
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="putenvs-wputenvs"></a>_putenv_s, _wputenv_s

Oluşturur, değiştirir veya ortam değişkenleri kaldırır. Sürümleri bunlar [_putenv, _wputenv](putenv-wputenv.md) ancak güvenlik geliştirmeleri açıklandığı gibi sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Ortam değişkeni ayarlanacak değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür veya bir hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*varName*|*value_string*|Dönüş değeri|
|------------|-------------|------------------|
|**NULL**|tüm|**EINVAL**|
|tüm|**NULL**|**EINVAL**|

Bir hata koşullarını ortaya çıkarsa, bu işlevlerin bir geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **EINVAL** ve **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Putenv_s** işlevi yeni ortam değişkenlerini ekler veya varolan ortam değişkenlerinin değerlerini değiştirir. Ortam değişkenleri, bir işlemi (örneğin, bir programla bağlanması kitaplıkları için varsayılan arama yolu) yürütür ortamı tanımlayın. **_wputenv_s** bir joker karakter sürümü **_putenv_s**; *envstrıng* bağımsız değişkeni **_wputenv_s** bir joker karakter dizesidir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tputenv_s**|**_putenv_s**|**_putenv_s**|**_wputenv_s**|

*varName* eklenemez veya değiştirilemez için ortam değişkeni adı ve *value_string* değişkenin değeridir. Varsa *varname* zaten ortamının bir parçası olan kendi değer ile değiştirilir *value_string*; Aksi takdirde, yeni *varname* değişkeni ve onun *value_string*  ortama eklenir. Boş bir dize belirterek ortamından bir değişkeni kaldırabilirsiniz (diğer bir deyişle, "") için *value_string*.

**_putenv_s** ve **_wputenv_s** geçerli işlem için yerel olan ortam etkiler; komutu düzeyi ortamı değiştirmek için kullanamazsınız. Bu işlevler Çalışma Zamanı Kitaplığı'na erişilebilen veri yapılarını ve "işletim sistemi için bir işlem oluşturur segment" ortam üzerinde çalışır. Geçerli işlem sonlandırıldığında ortamı çoğu durumda işletim sistemi düzeyi arama işlemi düzeyine geri döndürür. Ancak, değiştirilmiş ortamı tarafından oluşturulan tüm yeni işlemleri için geçirilebilir **_spawn**, **_exec**, veya **sistem**, ve bu yeni işlemler olan tüm yeni öğeler tarafından eklenen **_putenv_s** ve **_wputenv_s**.

Bir ortam giriş doğrudan değiştirmeyin; Bunun yerine, kullanın **_putenv_s** veya **_wputenv_s** değiştirmek için. Özellikle, doğrudan öğeleri boşaltma **_environ []** genel dizi ele alınması için geçersiz bellek neden olabilir.

**GETENV** ve **_putenv_s** genel değişkeni kullanmak **_environ** ortam tablosu; erişmek için **_wgetenv** ve **_wputenv_s** kullanmak **_wenviron**. **_putenv_s** ve **_wputenv_s** değerini değişebilir **_environ** ve **_wenviron**ve böylece geçersiz *envp*bağımsız değişkeni **ana** ve **_wenvp** bağımsız değişkeni **wmain**. Bu nedenle, kullanmak daha güvenli **_environ** veya **_wenviron** ortam bilgilere erişmek için. Arasındaki ilişki hakkında daha fazla bilgi için **_putenv_s** ve **_wputenv_s** genel değişkenler için bkz: [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv_s** ve **_getenv_s** işlevlerin aileleri iş parçacığı açısından güvenli değildir. **_getenv_s** sırasında dize işaretçisi döndürebilirsiniz **_putenv_s** dizesini değiştirmeyi ve böylece rastgele hatalara neden. Bu işlevler çağrıları eşitlendiğinden emin olun.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_putenv_s**|\<stdlib.h >|
|**_wputenv_s**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek için **_putenv_s**, bkz: [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
