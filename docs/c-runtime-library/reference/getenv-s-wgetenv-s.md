---
title: getenv_s, _wgetenv_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _tgetenv_s function
- wgetenv_s function
- _wgetenv_s function
- getenv_s function
- environment variables
- tgetenv_s function
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 34ba832030e3ad5580dd46deb39c1cbe62738ee9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="getenvs-wgetenvs"></a>getenv_s, _wgetenv_s
Geçerli ortamından bir değer alır. Bu sürümleri [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
  
#### <a name="parameters"></a>Parametreler  
 `pReturnValue`  
 Gerekli olan arabellek boyutu ya da değişken bulunamazsa, 0.  
  
 `buffer`  
 Ortam değişkeninin değeri depolamak için bir arabellek.  
  
 `numberOfElements`  
 Boyutunu `buffer`.  
  
 `varname`  
 Ortam değişkeni adı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır; Aksi takdirde bir hata kodu hatası.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`pReturnValue`|`buffer`|`numberOfElements`|`varname`|Dönüş Değeri|  
|--------------------|--------------|------------------------|---------------|------------------|  
|`NULL`|tüm|tüm|tüm|`EINVAL`|  
|tüm|`NULL`|>0|tüm|`EINVAL`|  
|tüm|tüm|tüm|`NULL`|`EINVAL`|  
  
 Bu hata koşullardan herhangi biri çağıran bir geçersiz parametre işleyicisi açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, İşlevler kümesi `errno` için `EINVAL` ve geri dönüp `EINVAL`.  
  
 Arabellek çok küçük ise, bu işlevler aynı zamanda, sonuç `ERANGE`. Geçersiz parametre işleyicisi çağırma kullanılamaz. Bunlar gerekli arabellek boyutu çıkışı yazma `pReturnValue`ve böylelikle daha büyük bir arabellek işleviyle tekrar çağırmak programları etkinleştirin.  
  
## <a name="remarks"></a>Açıklamalar  
 `getenv_s` İşlevi için ortam değişkenleri listesi arar `varname`. `getenv_s` Windows işletim sisteminde büyük küçük harfe duyarlı değildir. `getenv_s` ve `_putenv_s` genel değişkeni tarafından işaret ortam kopyasını kullanmak `_environ` ortama erişmek için. `getenv_s` Çalışma Zamanı Kitaplığı'na erişilebilen veri yapılarını ve değil "işlem için işletim sistemi tarafından oluşturulan segment" ortam çalışır. Bu nedenle, kullanan programlar `envp` bağımsız değişkeni [ana](../../cpp/main-program-startup.md) veya [wmain](../../cpp/main-program-startup.md) geçersiz bilgiler almak.  
  
 `_wgetenv_s` bir joker karakter sürümü `getenv_s`; bağımsız değişkeni ve dönüş değeri `_wgetenv_s` joker karakter dizelerdir. `_wenviron` Genel değişkeni, bir joker karakter sürümü `_environ`.  
  
 MBCS programında (örneğin, bir programında SBCS ASCII), `_wenviron` başlangıçta `NULL` çok baytlı karakter dizeleri oluşturulan ortam olduğundan. Ardından, ilk çağrıda `_wputenv`, ya da ilk çağrıda `_wgetenv_s`, karşılık gelen bir joker karakter dizesi ortamı (MBCS) ortam zaten yoksa, oluşturulur ve ardından işaret ediyor `_wenviron`.  
  
 Benzer şekilde, bir Unicode `(_wmain`) programı `_environ` başlangıçta `NULL` joker karakter dizelerini oluşturulan ortam olduğundan. Ardından, ilk çağrıda `_putenv`, ya da ilk çağrıda `getenv_s` (Unicode) ortam zaten varsa, karşılık gelen bir MBCS ortamı oluşturulur ve ardından işaret ediyor `_environ`.  
  
 Ortam (MBCS ve Unicode) iki kopyasını aynı anda bir program varsa, her iki kopya çalışma zamanı Sistem Koruması gerekir ve bu yavaş yürütme süresi neden olur. Çağırdığınızda Örneğin, `_putenv`, çağrı `_wputenv` böylece iki ortam dizeleri karşılık da otomatik olarak yürütülür.  
  
> [!CAUTION]
>  Çalışma zamanı sistem Unicode sürümü ve ortam, birden çok baytlı sürümü korurken nadir durumlarda, iki ortam sürümleri tam olarak karşılık gelmeyebilir. Benzersiz bir UNICODE dizesi herhangi bir benzersiz çok baytlı karakter dizesini eşleştirir ancak çok baytlı karakter dizesi için benzersiz bir UNICODE dizesi eşlemesinden mutlaka benzersiz olmadığından bu gerçekleşir. Daha fazla bilgi için bkz: [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  `_putenv_s` Ve `_getenv_s` işlevleri aileleri iş parçacığı açısından güvenli değildir. `_getenv_s` dize işaretçisi sırasında döndürebilirsiniz `_putenv_s` dizesini değiştirmeyi ve böylece rastgele hatalara neden. Bu işlevler çağrıları eşitlendiğinden emin olun.  
  
 C++'da, Bu işlevlerden birinin kullanımını şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer ve böylece boyutu bağımsız değişkeniyle belirtmek için gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tgetenv_s`|`getenv_s`|`getenv_s`|`_wgetenv_s`|  
  
 Denetlemek veya değerini değiştirmek için `TZ` ortam değişkeni, kullanım `getenv_s`, `_putenv`, ve `_tzset`, gerektiği gibi. Hakkında daha fazla bilgi için `TZ`, bkz: [_tzset](../../c-runtime-library/reference/tzset.md) ve [_daylight, _dstbias, _timezone ve _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`getenv_s`|\<stdlib.h>|  
|`_wgetenv_s`|\<stdlib.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [Ortam sabitleri](../../c-runtime-library/environmental-constants.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [_dupenv_s, _wdupenv_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md)