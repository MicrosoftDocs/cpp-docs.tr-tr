---
title: _makepath_s, _wmakepath_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wmakepath_s
- _makepath_s
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
- _wmakepath_s
- makepath_s
- _makepath_s
- wmakepath_s
dev_langs:
- C++
helpviewer_keywords:
- _makepath_s function
- wmakepath_s function
- paths
- _wmakepath_s function
- makepath_s function
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bef7cdbd58ba21396c78a1945e272e0a0e1baa4d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="makepaths-wmakepaths"></a>_makepath_s, _wmakepath_s
Bir yol adı bileşenlerini oluşturur. Sürümleri bunlar [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _makepath_s(  
   char *path,  
   size_t sizeInBytes,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
errno_t _wmakepath_s(  
   wchar_t *path,  
   size_t sizeInWords,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
template <size_t size>  
errno_t _makepath_s(  
   char (&path)[size],  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
); // C++ only  
template <size_t size>  
errno_t _wmakepath_s(  
   wchar_t (&path)[size],  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out] `path`  
 Tam yol arabelleği.  
  
 [in] `sizeInWords`  
 Sözcükler arabellek boyutu.  
  
 [in] `sizeInBytes`  
 Arabelleğin bayt cinsinden boyutu.  
  
 [in] `drive`  
 Bir harf (A, B vb.) içeren istenen sürücü ve bir isteğe bağlı izleyen iki nokta üst üste karşılık gelen. `_makepath_s` Eğer yoksa iki nokta üst üste bileşik yolu otomatik olarak ekler. Varsa `drive` olan `NULL` veya noktaları boş bir dize için sürücü harfi görünür bileşik `path` dize.  
  
 [in] `dir`  
 Sürücü göstergesi ya da gerçek dosya adı dahil değil, dizinleri yolunu içerir. Eğik isteğe bağlıdır ve eğik çizgi (/) veya ters eğik çizgi (\\) veya her ikisini de tek bir kullanılabilir `dir` bağımsız değişkeni. Hiçbir sondaki eğik çizgi varsa (/ veya \\) belirtilirse, otomatik olarak eklenir. Varsa `dir` olan `NULL` veya hiçbir dizin yolu boş bir dize noktalarına bileşik eklenen `path` dize.  
  
 [in] `fname`  
 Tüm dosya adı uzantıları olmadan temel dosya adı içeriyor. Varsa `fname` olan `NULL` veya bir dosya adı boş bir dize noktalarına bileşik eklenen `path` dize.  
  
 [in] `ext`  
 Gerçek dosya adı uzantısı ile veya olmadan başında nokta (.) içerir. `_makepath_s` içinde görünmüyorsa dönemi otomatik olarak ekler `ext`. Varsa `ext` olan `NULL` ya da boş bir dize, hiçbir uzantı noktalarına bileşik eklenen `path` dize.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır; hatasında bir hata kodu.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`path`|`sizeInWords` / `sizeInBytes`|Döndür|İçeriği `path`|  
|------------|------------------------------------|------------|------------------------|  
|`NULL`|tüm|`EINVAL`|değiştirilmedi|  
|tüm|<= 0|`EINVAL`|değiştirilmedi|  
  
 Yukarıdaki hata koşullardan herhangi biri meydana gelirse, bu işlevler geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevleri döndürür `EINVAL`. `NULL` Parametreler için izin verilen `drive`, `fname`, ve `ext`. Davranışı hakkında bilgi için bu parametre null işaretçiler ya da boş dize olduğunda, Açıklamalar bölümüne bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 `_makepath_s` İşlevi tek tek bileşenlerinden sonucu depolamak bileşik yol dizesi oluşturur `path`. `path` Bir sürücü harfi, dizin yolu, dosya adı ve dosya adı uzantısı içerebilir. `_wmakepath_s` bir joker karakter sürümü `_makepath_s`; bağımsız değişkenleri `_wmakepath_s` joker karakter dizelerdir. `_wmakepath_s` ve `_makepath_s` Aksi takdirde aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmakepath_s`|`_makepath_s`|`_makepath_s`|`_wmakepath_s`|  
  
 `path` Bağımsız değişken tam yolunu tutabilecek kadar büyük bir boş arabelleğe işaret etmelidir. Bileşik `path` değerinden büyük olmalı `_MAX_PATH` sabiti Stdlib.h tanımlanmış.  
  
 Yol ise `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Ayrıca, `errno` ayarlanır `EINVAL`. `NULL` diğer tüm parametreler için izin verilen değerler.  
  
 C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
 Bu işlevler hata ayıklama sürümleri ilk 0xFD arabellekle doldurun. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_makepath_s`|\<stdlib.h>|  
|`_wmakepath_s`|\<stdlib.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_makepath_s.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
   errno_t err;  
  
   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",  
                      "crt_makepath_s", "c" );  
   if (err != 0)  
   {  
      printf("Error creating path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );  
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,  
                       _MAX_FNAME, ext, _MAX_EXT );  
   if (err != 0)  
   {  
      printf("Error splitting the path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path extracted with _splitpath_s:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c  
  
Path extracted with _splitpath_s:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: crt_makepath_s  
  Ext: .c  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)