---
title: _searchenv, _wsearchenv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _searchenv
- _wsearchenv
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
- _wsearchenv
- _tsearchenv
- wsearchenv
- _searchenv
- searchenv
dev_langs: C++
helpviewer_keywords:
- _wsearchenv function
- files [C++], finding
- _searchenv function
- tsearchenv function
- environment paths, searching for files
- _tsearchenv function
- wsearchenv function
- searchenv function
- environment paths
ms.assetid: 9c944a27-d326-409b-aee6-410e8762d9d3
caps.latest.revision: "33"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9996c9aad085beaef46d2a3188503eba582602d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="searchenv-wsearchenv"></a>_searchenv, _wsearchenv
Bir dosyayı aramak için ortam yolları kullanır. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_searchenv_s, _wsearchenv_s](../../c-runtime-library/reference/searchenv-s-wsearchenv-s.md).  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _searchenv(  
   const char *filename,  
   const char *varname,  
   char *pathname   
);  
void _wsearchenv(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname   
);  
template <size_t size>  
void _searchenv(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
void _wsearchenv(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 `filename`  
 Aranacak dosya adı.  
  
 `varname`  
 Aranacak ortamı.  
  
 `pathname`  
 Tam yolunu depolamak için bir arabellek.  
  
## <a name="remarks"></a>Açıklamalar  
 `_searchenv` Rutin hedef dosya belirtilen etki alanında arar. `varname` Değişkeni herhangi bir ortam veya kullanıcı tanımlı değişken olabilir — örneğin, `PATH`, `LIB`, veya `INCLUDE`— dizin yolların listesini belirtir. Çünkü `_searchenv` , küçük harf duyarlıdır `varname` ortam değişkeni durumunun eşleşmesi gerekir.  
  
 Geçerli çalışma dizini dosyasında rutin ilk arar. Dosyayı bulamazsa, ortam değişkeni tarafından belirtilen dizin aracılığıyla arar. Hedef dosya bu dizinlerin birinde varsa, yeni oluşturulan yolu kopyalanır `pathname`. Varsa `filename` dosya bulunamadı, `pathname` null ile sonlandırılmış boş bir dize içeriyor.  
  
 `pathname` Arabellek en az olmalıdır `_MAX_PATH` karakter uzunluğunda oluşturulan yol adı tam uzunluğu uyum sağlamak için. Aksi takdirde, `_searchenv` taşması `pathname` arabellek ve beklenmeyen davranışlara neden olabilir.  
  
 `_wsearchenv`bir joker karakter sürümü `_searchenv`ve bağımsız değişkenleri `_wsearchenv` joker karakter dizelerdir. `_wsearchenv`ve `_searchenv` Aksi takdirde aynı şekilde davranır.  
  
 Varsa `filename` bu işlevlerin dönüş boş bir dize olan `ENOENT`.  
  
 Varsa `filename` veya `pathname` olan bir `NULL` işaretçi, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve `errno` için `EINVAL`.  
  
 Hakkında daha fazla bilgi için `errno` ve hata kodları bakın [errno sabitleri](../../c-runtime-library/errno-constants.md).  
  
 C++'da, bu işlevlerin daha yeni, daha güvenli ortaklarınıza çağırma şablon aşırı yüklemeleri bu işlevler vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsearchenv`|`_searchenv`|`_searchenv`|`_wsearchenv`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_searchenv`|\<stdlib.h >|  
|`_wsearchenv`|\<stdlib.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_searchenv.c  
// compile with: /W3  
// This program searches for a file in  
// a directory that's specified by an environment variable.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
  
   // Search for file in PATH environment variable:  
   _searchenv( searchfile, envvar, pathbuffer ); // C4996  
   // Note: _searchenv is deprecated; consider using _searchenv_s  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
```Output  
Path for CL.EXE:  
C:\Program Files\Microsoft Visual Studio 8\VC\BIN\CL.EXE  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizin denetimi](../../c-runtime-library/directory-control.md)   
 [GETENV, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [_searchenv_s, _wsearchenv_s](../../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)