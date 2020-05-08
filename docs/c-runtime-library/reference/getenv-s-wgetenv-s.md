---
title: getenv_s, _wgetenv_s
description: Microsoft C çalışma zamanı kitaplığı getenv_s ve _wgetenv_s işlevlerini açıklar.
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 0713ed5735916c31edaab1a178a5e9b1b7cf5377
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913677"
---
# <a name="getenv_s-_wgetenv_s"></a>getenv_s, _wgetenv_s

Geçerli ortamdan bir değer alır. Bu [getenv sürümünde,](getenv-wgetenv.md) [CRT 'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri _wgetenv.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Ön kapatma değeri*<br/>
Gerekli arabellek boyutu veya değişken bulunamazsa 0.

*arabelleğin*<br/>
Ortam değişkeninin değerini depolayan arabellek.

*numberOfElements*<br/>
*Arabelleğin*boyutu.

*varname*<br/>
Ortam değişkeni adı.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi takdirde hata durumunda hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*Ön kapatma değeri*|*arabelleğin*|*numberOfElements*|*varname*|Dönüş Değeri|
|--------------------|--------------|------------------------|---------------|------------------|
|**DEĞER**|kaydedilmemiş|kaydedilmemiş|kaydedilmemiş|**EıNVAL**|
|kaydedilmemiş|**DEĞER**|>0|kaydedilmemiş|**EıNVAL**|
|kaydedilmemiş|kaydedilmemiş|kaydedilmemiş|**DEĞER**|**EıNVAL**|

Bu hata koşullarından herhangi biri, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, işlevler **errno** olarak **EINVAL** ve **EINVAL**döndürür.

Ayrıca, arabellek çok küçükse, bu işlevler **ERANGE**döndürür. Geçersiz parametre işleyicisi çağırmazlar. Zorunlu arabellek boyutunu *önceden yapılan değer*olarak yazar ve böylece programların işlevi daha büyük bir arabellekle yeniden çağırmasını sağlar.

## <a name="remarks"></a>Açıklamalar

**Getenv_s** işlevi, *varname*için ortam değişkenlerinin listesini arar. **Getenv_s** Windows işletim sisteminde büyük küçük harfe duyarlı değildir. **getenv_s** ve [_putenv_s](putenv-s-wputenv-s.md) , ortama erişmek için **_environ** genel değişken tarafından işaret edilen ortamın kopyasını kullanın. **getenv_s** , işletim sistemi tarafından işlem için oluşturulan "segment" ortamında değil, yalnızca çalışma zamanı kitaplığı tarafından erişilebilen veri yapıları üzerinde çalışır. Bu nedenle, [ana](../../cpp/main-function-command-line-args.md) veya [wmain](../../cpp/main-function-command-line-args.md) için *envp* bağımsız değişkenini kullanan programlar geçersiz bilgileri alabilir.

**_wgetenv_s** , **getenv_s**geniş karakterli bir sürümüdür; **_wgetenv_s** bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir. **_Wenviron** genel değişkeni, **_environ**geniş karakterli bir sürümüdür.

Bir MBCS programında (örneğin, bir SBCS ASCII programında), ortam çok baytlı karakter dizelerinden oluştuğu için başlangıçta **NULL** **_wenviron** . Daha sonra, [_wputenv](putenv-wputenv.md)için ilk çağrıda veya **_wgetenv_s**Ilk çağrıda, (MBCS) bir ortam zaten mevcutsa, buna karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve ardından **_wenviron**tarafından gösterilir.

Benzer şekilde, bir Unicode (**_wmain**) programında, ortam geniş karakter dizelerinden oluştuğu için **_environ** başlangıçta **null** olur. Ardından, [_putenv](putenv-wputenv.md)ilk çağrısında veya bir (Unicode) ortamı zaten varsa **getenv_s** ilk çağrıda, karşılık gelen bir MBCS ortamı oluşturulur ve ardından **_environ**tarafından gösterilir.

Ortamın iki kopyası (MBCS ve Unicode) bir programda aynı anda mevcut olduğunda, çalışma zamanı sisteminin her iki kopyayı da koruması gerekir ve bu, daha yavaş yürütme süresine neden olur. Örneğin, **_putenv**çağırdığınızda, iki ortam dizesinin karşılık gelmesi için bir **_wputenv** çağrısı de otomatik olarak yürütülür.

> [!CAUTION]
> Nadir örneklerde, çalışma zamanı sistemi hem Unicode sürümü hem de ortamın çok baytlı bir sürümünü kullanırken, iki ortam sürümü tam olarak karşılamayabilir. Bunun nedeni, benzersiz bir çok baytlı karakter dizesinin benzersiz bir Unicode dizesine eşlenmesine karşın, benzersiz bir Unicode dizesinden çok baytlı karakter dizesine eşlemenin benzersiz olması gerekir. Daha fazla bilgi için bkz. [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> İşlevlerin **_putenv_s** ve **_getenv_s** aileleri iş parçacığı açısından güvenli değildir. **_getenv_s** , **_putenv_s** dizeyi değiştirirken bir dize işaretçisi döndürebilir ve bu nedenle rastgele hatalara neden olabilir. Bu işlevlere yapılan çağrıların eşitlendiğinden emin olun.

C++ ' da, bu işlevlerin kullanımı şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir ve böylece bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv_s**|**getenv_s**|**getenv_s**|**_wgetenv_s**|

**TZ** ortam değişkeninin değerini denetlemek veya değiştirmek için, gerektiği gibi **getenv_s**, **_putenv**ve **_tzset**kullanın. **TZ**hakkında daha fazla bilgi için bkz. [_tzset](tzset.md) ve [_daylight, _dstbias, _timezone ve _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**getenv_s**|\<Stdlib. h>|
|**_wgetenv_s**|\<Stdlib. h> veya \<wchar. h>|

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
[Çevresel sabitler](../../c-runtime-library/environmental-constants.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md)<br/>
