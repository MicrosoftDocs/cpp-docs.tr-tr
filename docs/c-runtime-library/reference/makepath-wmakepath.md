---
title: _makepath, _wmakepath | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _makepath
- _wmakepath
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
dev_langs:
- C++
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbbaa2f4191d36fb92af5e157990fde6f053df55
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="makepath-wmakepath"></a>_makepath, _wmakepath
Bir yol adı bileşenlerini oluşturun. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _makepath(  
   char *path,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
void _wmakepath(  
   wchar_t *path,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `path`  
 Tam yol arabelleği.  
  
 `drive`  
 Bir harf (A, B vb.) içeren istenen sürücü ve bir isteğe bağlı izleyen iki nokta üst üste karşılık gelen. `_makepath` Eğer yoksa iki nokta üst üste bileşik yolu otomatik olarak ekler. Varsa `drive` olan `NULL` veya noktaları boş bir dize için sürücü harfi görünür bileşik `path` dize.  
  
 `dir`  
 Sürücü göstergesi ya da gerçek dosya adı dahil değil, dizinleri yolunu içerir. Eğik isteğe bağlıdır ve eğik çizgi (/) veya ters eğik çizgi (\\) veya her ikisini de tek bir kullanılabilir `dir` bağımsız değişkeni. Hiçbir sondaki eğik çizgi varsa (/ veya \\) belirtilirse, otomatik olarak eklenir. Varsa `dir` olan `NULL` veya hiçbir dizin yolu boş bir dize noktalarına bileşik eklenen `path` dize.  
  
 `fname`  
 Tüm dosya adı uzantıları olmadan temel dosya adı içeriyor. Varsa `fname` olan `NULL` veya bir dosya adı boş bir dize noktalarına bileşik eklenen `path` dize.  
  
 `ext`  
 Gerçek dosya adı uzantısı ile veya olmadan başında nokta (.) içerir. `_makepath` içinde görünmüyorsa dönemi otomatik olarak ekler `ext`. Varsa `ext` olan `NULL` ya da boş bir dize, hiçbir uzantı noktalarına bileşik eklenen `path` dize.  
  
## <a name="remarks"></a>Açıklamalar  
 `_makepath` İşlevi tek tek bileşenlerinden sonucu depolamak bileşik yol dizesi oluşturur `path`. `path` Bir sürücü harfi, dizin yolu, dosya adı ve dosya adı uzantısı içerebilir. `_wmakepath` bir joker karakter sürümü `_makepath`; bağımsız değişkenleri `_wmakepath` joker karakter dizelerdir. `_wmakepath` ve `_makepath` Aksi takdirde aynı şekilde davranır.  
  
 **Güvenlik Notu** null sonlandırılmış bir dize kullanın. Arabellek Taşması önlemek için null ile sonlandırılmış dize boyutu aşmamalıdır `path` arabellek. `_makepath` Bileşik yol dizesi uzunluğu için en fazla emin olun `_MAX_PATH`. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmakepath`|`_makepath`|`_makepath`|`_wmakepath`|  
  
 `path` Bağımsız değişken tam yolunu tutabilecek kadar büyük bir boş arabelleğe işaret etmelidir. Bileşik `path` değerinden büyük olmalı `_MAX_PATH` sabiti Stdlib.h tanımlanmış.  
  
 Yol ise `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Ayrıca, `errno` ayarlanır `EINVAL`. `NULL` diğer tüm parametreler için izin verilen değerler.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_makepath`|\<stdlib.h>|  
|`_wmakepath`|\<stdlib.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_makepath.c  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
  
   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996  
   // Note: _makepath is deprecated; consider using _makepath_s instead  
   printf( "Path created with _makepath: %s\n\n", path_buffer );  
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996  
   // Note: _splitpath is deprecated; consider using _splitpath_s instead  
   printf( "Path extracted with _splitpath:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
```Output  
Path created with _makepath: c:\sample\crt\makepath.c  
  
Path extracted with _splitpath:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: makepath  
  Ext: .c  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)