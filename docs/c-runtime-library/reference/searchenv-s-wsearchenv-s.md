---
title: _searchenv_s, _wsearchenv_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsearchenv_s
- _searchenv_s
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
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
dev_langs: C++
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
caps.latest.revision: "32"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6f1089aa1f772832417168a2262fa72069b3ede7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="searchenvs-wsearchenvs"></a>_searchenv_s, _wsearchenv_s
Ortam yolları kullanarak bir dosyayı arar. Bu sürümleri [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char *pathname,  
   size_t numberOfElements  
);  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`filename`  
 Aranacak dosya adı.  
  
 [in]`varname`  
 Aranacak ortamı.  
  
 [out]`pathname`  
 Tam yolunu depolamak için bir arabellek.  
  
 [in]`numberOfElements`  
 Boyutunu `pathname` arabellek.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır; hatasında bir hata kodu.  
  
 Varsa `filename` boş bir dize dönüş değeri `ENOENT`.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`filename`|`varname`|`pathname`|`numberOfElements`|Dönüş değeri|İçeriği`pathname`|  
|----------------|---------------|----------------|------------------------|------------------|----------------------------|  
|tüm|tüm|`NULL`|tüm|`EINVAL`|yok|  
|`NULL`|tüm|tüm|tüm|`EINVAL`|değiştirilmedi|  
|tüm|tüm|tüm|<= 0|`EINVAL`|değiştirilmedi|  
  
 Bu hata koşullardan herhangi biri meydana gelirse, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL` ve geri dönüp `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_searchenv_s` Rutin hedef dosya belirtilen etki alanında arar. `varname` Değişkeni herhangi bir ortam veya dizin yolları listesini gibi belirtir, kullanıcı tanımlı değişken olabilir `PATH`, `LIB`, ve `INCLUDE`. Çünkü `_searchenv_s` , küçük harf duyarlıdır `varname` ortam değişkeni durumunun eşleşmesi gerekir. Varsa `varname` bir ortam değişkeni adı tanımlı işlemin ortamında eşleşmediğinden yok, sıfır işlevi döndürür ve `pathname` değişkenidir değişmez.  
  
 Yordam önce geçerli çalışma dizini dosyasında arar. Dosyayı bulamazsa, ortam değişkeni tarafından belirtilen dizin aracılığıyla sonraki arar. Hedef dosya bu dizinlerin birinde varsa, yeni oluşturulan yolu kopyalanır `pathname`. Varsa `filename` dosya bulunamadı, `pathname` null ile sonlandırılmış boş bir dize içeriyor.  
  
 `pathname` Arabellek en az olmalıdır `_MAX_PATH` karakter uzunluğunda oluşturulan yol adı tam uzunluğu uyum sağlamak için. Aksi takdirde, `_searchenv_s` taşması `pathname` beklenmeyen davranışlara kaynaklanan arabellek.  
  
 `_wsearchenv_s`bir joker karakter sürümü `_searchenv_s`; bağımsız değişkenleri `_wsearchenv_s` joker karakter dizelerdir. `_wsearchenv_s`ve `_searchenv_s` Aksi takdirde aynı şekilde davranır.  
  
 C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsearchenv_s`|`_searchenv_s`|`_searchenv_s`|`_wsearchenv_s`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_searchenv_s`|\<stdlib.h >|  
|`_wsearchenv_s`|\<stdlib.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_searchenv_s.c  
/* This program searches for a file in  
 * a directory specified by an environment variable.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
   errno_t err;  
  
   /* Search for file in PATH environment variable: */  
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );  
   if (err != 0)  
   {  
      printf("Error searching the path. Error code: %d\n", err);  
   }  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
```Output  
Path for CL.EXE:  
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizin denetimi](../../c-runtime-library/directory-control.md)   
 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)   
 [GETENV, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)