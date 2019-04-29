---
title: getenv_s, _wgetenv_s
ms.date: 11/04/2016
apiname:
- getenv_s
- _wgetenv_s
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
- getenv_s
- _tgetenv_s
- _wgetenv_s
helpviewer_keywords:
- _tgetenv_s function
- wgetenv_s function
- _wgetenv_s function
- getenv_s function
- environment variables
- tgetenv_s function
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
ms.openlocfilehash: eac3c036e2f4f271c7bc2d77c8ae82bec28d3617
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331746"
---
# <a name="getenvs-wgetenvs"></a>getenv_s, _wgetenv_s

Geçerli ortamdan bir değer alır. Bu sürümleri [getenv, _wgetenv](getenv-wgetenv.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t getenv_s(
   size_t *pReturnValue,
   char* buffer,
   size_t numberOfElements,
   const char *varname
);
errno_t _wgetenv_s(
   size_t *pReturnValue,
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *varname
);
template <size_t size>
errno_t getenv_s(
   size_t *pReturnValue,
   char (&buffer)[size],
   const char *varname
); // C++ only
template <size_t size>
errno_t _wgetenv_s(
   size_t *pReturnValue,
   wchar_t (&buffer)[size],
   const wchar_t *varname
); // C++ only
```

### <a name="parameters"></a>Parametreler

*pReturnValue*<br/>
Gerekli arabellek boyutu veya 0 değişkeni bulunamadı.

*Arabellek*<br/>
Ortam değişkeninin değerini depolayan arabellek.

*numberOfElements*<br/>
Boyutu *arabellek*.

*varName*<br/>
Ortam değişkeni adı.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi takdirde bir hata kodu hatası.

### <a name="error-conditions"></a>Hata koşulları

|*pReturnValue*|*Arabellek*|*numberOfElements*|*varName*|Dönüş Değeri|
|--------------------|--------------|------------------------|---------------|------------------|
|**NULL**|Tüm|Tüm|Tüm|**EINVAL**|
|Tüm|**NULL**|>0|Tüm|**EINVAL**|
|Tüm|Tüm|Tüm|**NULL**|**EINVAL**|

Bu hata durumlardan herhangi biri çağırır, geçersiz parametre işleyicisini açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse işlevler **errno** için **EINVAL** ve dönüş **EINVAL**.

Ayrıca, bu işlevler arabellek çok küçük ise, dönüş **ERANGE**. Geçersiz parametre işleyicisi çağırma kullanılamaz. Bunlar gerekli arabellek boyutu kullanıma yazma *pReturnValue*ve böylece daha büyük bir arabellek ile yeniden işlevi çağırmak programları etkinleştirin.

## <a name="remarks"></a>Açıklamalar

**Getenv_s** işlevi için ortam değişkenleri listesi arar *varname*. **getenv_s** Windows işletim sistemi büyük/küçük harfe duyarlı değildir. **getenv_s** ve [_putenv_s](putenv-s-wputenv-s.md) genel değişkeni tarafından işaret edilen ortamın kopyasını kullanın **_environ** ortama erişmek için. **getenv_s** çalışma zamanı kitaplığının erişilebildiği veri yapıları ve ortam işlem için işletim sistemi tarafından oluşturulan "segment" üzerinde çalışır. Bu nedenle, kullanan programlar *envp* bağımsız değişkeni [ana](../../cpp/main-program-startup.md) veya [wmain](../../cpp/main-program-startup.md) geçersiz bilgiler almak.

**_wgetenv_s** geniş karakterli sürümüdür **getenv_s**; bağımsız değişkeni ve dönüş değeri **_wgetenv_s** geniş karakterli dizelerdir. **_Wenviron** genel değişkeni, bir geniş karakter sürümünü **_environ**.

Bir MBCS programında (örneğin, programda bir ASCII SBCS) **_wenviron** başlangıçta **NULL** çünkü ortam çok baytlı karakter dizeleri kümesinden oluşur. Daha sonra yapılan ilk çağrıda [_wputenv](putenv-wputenv.md), veya yapılan ilk çağrıda **_wgetenv_s**, (MBCS) ortamı zaten varsa, karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve ardından tarafından işaret edilen **_wenviron**.

Benzer şekilde, bir Unicode (**_wmain**) programı **_environ** başlangıçta **NULL** çünkü ortam geniş karakter dizeleri kümesinden oluşur. Daha sonra yapılan ilk çağrıda [_putenv](putenv-wputenv.md), veya yapılan ilk çağrıda **getenv_s** (Unicode) ortamı zaten varsa, karşılık gelen bir MBCS ortamı oluşturulur ve ardından tarafından işaret edilen **_ environ**.

Ortam (MBCS ve Unicode) iki kopyasını aynı anda bir programda varsa, çalışma zamanı sistemi her iki kopyasında koruması gerekir ve bu daha yavaş yürütme süresi neden olur. Örneğin, çağırdığınızda **_putenv**, bir çağrı **_wputenv** böylece iki ortam dizeleri karşılık da otomatik olarak yürütülür.

> [!CAUTION]
> Çalışma zamanı sistemi, hem Unicode sürümü hem de çok baytlı bir sürüm ortamının muhafaza ederken nadir durumlarda, iki ortam sürümleri tam olarak karşılık gelmeyebilir. Benzersiz bir çok baytlı karakterli dize benzersiz bir Unicode dizesini eşleştirir ancak bir çok baytlı karakter dizesi benzersiz bir Unicode dize eşleme mutlaka benzersiz olmadığı için meydana gelir. Daha fazla bilgi için [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv_s** ve **_getenv_s** işlev aileleri iş parçacığı açısından güvenli değildir. **_getenv_s** dize işaretçisini döndürebilir **_putenv_s** dize değiştirme ve böylece rastgele hatalara neden olur. Bu işlevlere aramaların eşitlendiğinden emin olun.

C++'da, bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak tanım Çıkarsama ve böylece bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kullanabilirsiniz. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv_s**|**getenv_s**|**getenv_s**|**_wgetenv_s**|

Denetleyin ya da değerini değiştirmek için **TZ** ortam değişkenini kullanmak **getenv_s**, **_putenv**, ve **_tzset**gerektirdiği gibi. Hakkında daha fazla bilgi için **TZ**, bkz: [_tzset](tzset.md) ve [_daylight, _dstbias, _timezone ve _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**getenv_s**|\<stdlib.h >|
|**_wgetenv_s**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_getenv_s.c
// This program uses getenv_s to retrieve
// the LIB environment variable and then uses
// _putenv to change it to a new value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char* libvar;
   size_t requiredSize;

   getenv_s( &requiredSize, NULL, 0, "LIB");
   if (requiredSize == 0)
   {
      printf("LIB doesn't exist!\n");
      exit(1);
   }

   libvar = (char*) malloc(requiredSize * sizeof(char));
   if (!libvar)
   {
      printf("Failed to allocate memory!\n");
      exit(1);
   }

   // Get the value of the LIB environment variable.
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );

   printf( "Original LIB variable is: %s\n", libvar );

   // Attempt to change path. Note that this only affects
   // the environment variable of the current process. The command
   // processor's environment is not changed.
   _putenv_s( "LIB", "c:\\mylib;c:\\yourlib" );

   getenv_s( &requiredSize, NULL, 0, "LIB");

   libvar = (char*) realloc(libvar, requiredSize * sizeof(char));
   if (!libvar)
   {
      printf("Failed to allocate memory!\n");
      exit(1);
   }

   // Get the new value of the LIB environment variable.
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );

   printf( "New LIB variable is: %s\n", libvar );

   free(libvar);
}
```

```Output
Original LIB variable is: c:\vctools\lib;c:\vctools\atlmfc\lib;c:\vctools\PlatformSDK\lib;c:\vctools\Visual Studio SDKs\DIA Sdk\lib;c:\vctools\Visual Studio SDKs\BSC Sdk\lib
New LIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[Ortam Sabitleri](../../c-runtime-library/environmental-constants.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md)<br/>
