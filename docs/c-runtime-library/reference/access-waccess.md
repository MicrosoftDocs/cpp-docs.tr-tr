---
title: _access, _waccess | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _access
- _waccess
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
- _waccess
- _access
- taccess
- waccess
- _taccess
dev_langs: C++
helpviewer_keywords:
- access function
- _taccess function
- waccess function
- _access function
- _waccess function
- taccess function
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8523e2f2e0a3550c6b996fa26387b278b6df94ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="access-waccess"></a>_access, _waccess
Bir dosya salt okunur olup olmadığını belirler. Daha güvenli sürümlerinde kullanılabilir; bkz: [_access_s, _waccess_s](../../c-runtime-library/reference/access-s-waccess-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _access(   
   const char *path,   
   int mode   
);  
int _waccess(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `path`  
 Dosya veya dizin yolu.  
  
 `mode`  
 Okuma/yazma özniteliği.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Verilen modu dosya varsa, her işlev 0 döndürür. Adlı dosya yok veya verilen modu yok ise -1 fonksiyonunu döndürür; Bu durumda, `errno` aşağıdaki tabloda gösterilen şekilde ayarlayın.  
  
 `EACCES`  
 Erişim reddedildi: dosya izni ayarı, belirtilen erişim izin vermez.  
  
 `ENOENT`  
 Dosya adı veya yolu bulunamadı.  
  
 `EINVAL`  
 Geçersiz parametre.  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Dosyaları ile kullanıldığında `_access` işlevi, belirtilen dosya veya dizin yok ve değeri tarafından belirtilen özniteliklere sahip olup olmadığını belirler `mode`. Dizinleri ile kullanıldığında `_access` yalnızca belirtilen dizin var olup olmadığını; belirler, [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] ve tüm dizinleri okuma ve yazma erişimi daha sonra işletim sistemleri,.  
  
|`mode`değer|Dosya denetimleri için|  
|------------------|---------------------|  
|00|Yalnızca varlığı|  
|02|Salt yazılır|  
|04|Salt okunur|  
|06|Okuma ve yazma|  
  
 Bu işlev yalnızca dosya ve dizin veya değil, dosya sistemi güvenlik ayarları denetlemez salt okunur olup olmadığını denetler. Bunun için bir erişim belirteci gerekir. Dosya sistemi güvenlik hakkında daha fazla bilgi için bkz: [erişim belirteçleri](http://msdn.microsoft.com/library/windows/desktop/aa374909). Bu işlevselliği sağlayacak şekilde bir ATL sınıf mevcut; bkz: [CAccessToken sınıfı](../../atl/reference/caccesstoken-class.md).  
  
 `_waccess`bir joker karakter sürümü `_access`; `path` bağımsız değişkeni `_waccess` bir joker karakter dizesidir. `_waccess`ve `_access` Aksi takdirde aynı şekilde davranır.  
  
 Bu işlev parametrelerini doğrular. Varsa `path` olan `NULL` veya `mode` geçerli bir moda belirtmiyor açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, işlevi ayarlar `errno` için `EINVAL` ve -1 döndürür.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_taccess`|`_access`|`_access`|`_waccess`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|----------------------|  
|`_access`|\<io.h >|\<errno.h >|  
|`_waccess`|\<wchar.h > veya \<io.h >|\<errno.h >|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `_access` crt_ACCESS adlı dosyayı denetlemek için. Var olup ve yazma izin verilip verilmeyeceğini görmek için C.  
  
```  
// crt_access.c  
// compile with: /W1  
// This example uses _access to check the file named  
// crt_ACCESS.C to see if it exists and if writing is allowed.  
  
#include  <io.h>  
#include  <stdio.h>  
#include  <stdlib.h>  
  
int main( void )  
{  
    // Check for existence.  
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )  
    {  
        printf_s( "File crt_ACCESS.C exists.\n" );  
  
        // Check for write permission.  
        // Assume file is read-only.  
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )  
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );  
    }  
}  
```  
  
```Output  
File crt_ACCESS.C exists.  
File crt_ACCESS.C does not have write permission.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_stat, _wstat işlevleri](../../c-runtime-library/reference/stat-functions.md)