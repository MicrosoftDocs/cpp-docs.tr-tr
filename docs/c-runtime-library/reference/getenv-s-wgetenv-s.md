---
title: getenv_s, _wgetenv_s
description: Microsoft C çalışma zamanı getenv_s _wgetenv_s kitaplığını ve işlevlerini açıklar.
ms.date: 4/2/2020
api_name:
- getenv_s
- _wgetenv_s
- _o__wgetenv_s
- _o_getenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
no-loc:
- getenv_s
- _wgetenv_s
- _putenv_s
- main
- wmain
- errno
- EINVAL
- ERANGE
- _environ
- _wenviron
- _putenv
- _wputenv
- _tgetenv_s
- _tzset
- _dupenv_s
- _wdupenv_s
ms.openlocfilehash: 17c4e001f7f4637f6f66f218c94378368976901f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344277"
---
# <a name="getenv_s-_wgetenv_s"></a>getenv_s, _wgetenv_s

Geçerli ortamdan bir değer alır. CRT Güvenlik [Özellikleri](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi [getenv, _wgetenv](getenv-wgetenv.md) bu sürümleri güvenlik geliştirmeleri var.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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
Gerekli arabellek boyutu veya değişken bulunamazsa 0.

*Arabellek*<br/>
Ortam değişkeninin değerini depolamak için arabellek.

*numberOfElements*<br/>
*Arabellek*boyutu.

*Varname*<br/>
Çevre değişken adı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır; aksi takdirde, hata bir hata kodu.

### <a name="error-conditions"></a>Hata Koşulları

|*pReturnValue*|*Arabellek*|*numberOfElements*|*Varname*|Dönüş Değeri|
|--------------------|--------------|------------------------|---------------|------------------|
|**Null**|herhangi bir|herhangi bir|herhangi bir|**Eınval**|
|herhangi bir|**Null**|>0|herhangi bir|**Eınval**|
|herhangi bir|herhangi bir|herhangi bir|**Null**|**Eınval**|

Bu hata koşullarından herhangi biri, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisini çağırır. Yürütme devam etmesine izin verilirse, işlevleri **EINVAL** **için errno** ayarlayın ve **EINVAL**döndürün.

Ayrıca, arabellek çok küçükse, bu işlevler **ERANGE**döndürür. Geçersiz bir parametre işleyicisi çağırmaz. Onlar *pReturnValue*gerekli arabellek boyutunu yazmak ve bu nedenle daha büyük bir arabellek ile işlevi yeniden aramak için programlar etkinleştirmek.

## <a name="remarks"></a>Açıklamalar

**getenv_s** işlevi *varname*için ortam değişkenleri listesini arar. **getenv_s** Windows işletim sisteminde büyük/küçük harf duyarlı değildir. **getenv_s** ve [_putenv_s,](putenv-s-wputenv-s.md) genel **değişkenin** işaret ettiği ortamın kopyasını _environ çevreye erişmek için kullanırlar. **getenv_s** yalnızca çalışma zamanı kitaplığı için erişilebilen veri yapılarında çalışır, işletim sistemi tarafından işlem için oluşturulan ortam "segmenti"nde değil. Bu nedenle, [ana](../../cpp/main-function-command-line-args.md) veya [wmain](../../cpp/main-function-command-line-args.md) *için envp* bağımsız değişkeni kullanan programlar geçersiz bilgi alabilir.

**_wgetenv_s** **getenv_s**geniş karakterli bir versiyonudur; _wgetenv_s bağımsız değişkeni **_wgetenv_s** ve geri dönüş değeri geniş karakterli dizeleridir. **_wenviron** global **değişken, _environ**geniş karakterli bir sürümüdür.

Bir MBCS programında (örneğin, bir SBCS ASCII programında), ortam çok bayt karakterli dizelerden oluştuğuiçin **_wenviron** başlangıçta **NULL'dur.** Daha sonra, [_wputenv](putenv-wputenv.md)için ilk çağrıda , ya da **_wgetenv_s**için ilk çağrıda , bir (MBCS) ortamı zaten varsa, karşılık gelen geniş karakterli dize ortamı oluşturulur ve daha sonra **_wenviron**tarafından işaret edilir.

Benzer şekilde, unicode **(_wmain**) programında da ortam geniş karakterli dizeleri **oluşturduğundan, _environ** başlangıçta **NULL'dur.** Daha sonra, [_putenv](putenv-wputenv.md)için ilk çağrıda, ya da **getenv_s** için ilk aramada eğer (Unicode) bir ortam zaten var, ilgili bir MBCS ortamı oluşturulur ve daha sonra **_environ**tarafından işaret edilir.

Bir programda ortamın iki kopyası (MBCS ve Unicode) aynı anda varsa, çalışma zamanı sisteminin her iki kopyayı da tutması gerekir ve bu da yürütme süresinin daha yavaş olmasına neden olur. Örneğin, **_putenv,** **_wputenv** için bir çağrı da otomatik olarak böylece iki ortam dizeleri karşılık yürütülür çağırır.

> [!CAUTION]
> Çalışma zamanı sistemi hem Unicode sürümünü hem de ortamın çok bayt sürümünü korurken, iki ortam sürümü tam olarak karşılık sızmayabilir. Bu, benzersiz bir çok bayt karakterli dize yle eşlemesine rağmen, benzersiz bir Unicode dizesinden çok bayt karakterli bir dize eşlemenin benzersiz olmaması nedeniyle gerçekleşir. Daha fazla bilgi için [_environ _wenviron.](../../c-runtime-library/environ-wenviron.md)

> [!NOTE]
> Işlevlerin **_putenv_s** ve **_getenv_s** aileleri iş parçacığı için güvenli değildir. **_getenv_s,** **_putenv_s** dizeyi değiştirirken bir dize işaretçisi döndürebilir ve bu nedenle rasgele hatalara neden olabilir. Bu işlevlere yapılan çağrıların eşitlendirildiğinden emin olun.

C++'da, bu işlevlerin kullanımı şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabiliyor ve bu şekilde boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv_s**|**getenv_s**|**getenv_s**|**_wgetenv_s**|

**TZ** ortam değişkeninin değerini kontrol etmek veya değiştirmek için, gerektiğinde **getenv_s,** **_putenv**ve **_tzset**kullanın. **TZ**hakkında daha fazla bilgi için [_tzset](tzset.md) ve [_daylight, _dstbias, _timezone ve _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**getenv_s**|\<stdlib.h>|
|**_wgetenv_s**|\<stdlib.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
[Çevre Sabitleri](../../c-runtime-library/environmental-constants.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md)<br/>
