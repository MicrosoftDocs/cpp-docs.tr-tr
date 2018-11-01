---
title: _putenv, _wputenv
ms.date: 11/04/2016
apiname:
- _putenv
- _wputenv
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
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
helpviewer_keywords:
- _putenv function
- environment variables, deleting
- putenv function
- tputenv function
- environment variables, creating
- wputenv function
- _wputenv function
- _tputenv function
- environment variables, modifying
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
ms.openlocfilehash: 952a4d62f6ceb6b689091ac09f6ca338d0b10864
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432519"
---
# <a name="putenv-wputenv"></a>_putenv, _wputenv

Oluşturur, değiştirir veya ortam değişkenlerini kaldırır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _putenv(
   const char *envstring
);
int _wputenv(
   const wchar_t *envstring
);
```

### <a name="parameters"></a>Parametreler

*envstrıng*<br/>
Ortam dizesi tanımı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 veya bir hata durumunda -1 döndürür.

## <a name="remarks"></a>Açıklamalar

**_Putenv** işlevi yeni ortam değişkenleri ekler veya varolan ortam değişkenlerinin değerlerini değiştirir. Ortam değişkenlerini (örneğin, bir programla bağlanacak kitaplıklara varsayılan arama yolu) bir işlem yürütür ortamı tanımlar. **_wputenv** geniş karakterli sürümüdür **_putenv**; *envstrıng* bağımsız değişkeni **_wputenv** geniş karakterli bir dizedir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

*Envstrıng* biçiminde bir dizeye bir işaretçi bağımsız değişkeni olmalıdır *varname*=*value_string*burada *varname* olduğu eklenecek veya değiştirilecek ortam değişkenini adını ve *value_string* değişkenin değeridir. Varsa *varname* zaten ortamın bir parçası olan alt değer ile değiştirilir *value_string*; Aksi takdirde, yeni *varname* değişkeni ve onun *value_string*  değeri ortama eklenir. Boş bir belirterek ortamdan bir değişkeni kaldırabilirsiniz *value_string*, veya başka bir deyişle, yalnızca belirterek *varname*=.

**_putenv** ve **_wputenv** yalnızca geçerli işlemin yerel olduğu ortamı etkiler; komut düzeyindeki ortamı değiştirmek için kullanamazsınız. Diğer bir deyişle, bu işlevler yalnızca çalışma zamanı kitaplığının erişilebildiği veri yapıları ve olmayan bir işlem için işletim sistemi tarafından oluşturulan ortam dilimi üzerinde çalışır. Geçerli işlem sonlandırıldığında, ortam (çoğu durumda, işletim sistemi düzeyi) çağırma işleminin düzeyine döner. Ancak değiştirilmiş ortam tarafından oluşturulan yeni süreçlere geçirilebilir **_spawn**, **_exec**, veya **sistem**, ve bu yeni süreçler tarafındaneklenenyeniöğelerial **_putenv** ve **_wputenv**.

Doğrudan bir ortam girdisini değiştirmeyin: bunun yerine, **_putenv** veya **_wputenv** değiştirmek için. Özellikle, doğrudan serbest öğeleri **_environ []** genel dizi hedeflenen geçersiz belleğe için neden olabilir.

**GETENV** ve **_putenv** genel değişkenin **_environ** ; ortam tablosuna erişmek için **_wgetenv** ve **_wputenv** kullanın **_wenviron**. **_putenv** ve **_wputenv** değerini değişebilir **_environ** ve **_wenviron**, kılarak **_envp** bağımsız değişken **ana** ve **_wenvp** bağımsız değişkeni **wmain**. Bu nedenle, kullanılacak güvenli **_environ** veya **_wenviron** ortam bilgilerine erişmek için. İlişkisi hakkında daha fazla bilgi için **_putenv** ve **_wputenv** genel değişkenler için bkz. [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv** ve **_getenv** işlev aileleri iş parçacığı açısından güvenli değildir. **_getenv** dize işaretçisini döndürebilir **_putenv** rastgele hatalara neden dize değiştirme. Bu işlevlere aramaların eşitlendiğinden emin olun.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_putenv**|\<stdlib.h >|
|**_wputenv**|\<stdlib.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek **_putenv**, bkz: [getenv, _wgetenv](getenv-wgetenv.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
