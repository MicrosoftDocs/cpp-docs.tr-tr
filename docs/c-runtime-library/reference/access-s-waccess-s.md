---
title: _access_s, _waccess_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _access_s
- _waccess_s
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
- waccess_s
- access_s
- _waccess_s
- _access_s
dev_langs: C++
helpviewer_keywords:
- access_s function
- taccess_s function
- _taccess_s function
- waccess_s function
- _access_s function
- _waccess_s function
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f562d62f3edb1f09fe6d7ebe7b509411ad2dc8c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="accesss-waccesss"></a>_access_s, _waccess_s
Dosya okuma/yazma izinleri belirler. Bu bir sürümüdür [_access, _waccess](../../c-runtime-library/reference/access-waccess.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _access_s(   
   const char *path,   
   int mode   
);  
errno_t _waccess_s(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `path`  
 Dosya veya dizin yolu.  
  
 `mode`  
 İzni ayarı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Verilen modu dosya varsa, her işlev 0 döndürür. Adlandırılmış dosya yok veya verilen modunda erişilebilir değilse işlevi bir hata kodu döndürür. Bu durumda, işlevi bir hata kodu kümesinden gibi döndürür ve ayrıca ayarlar `errno` aynı değere.  
  
 `EACCES`  
 Erişim reddedildi. Dosya izni ayarı belirtilen erişim izin vermiyor.  
  
 `ENOENT`  
 Dosya adı veya yolu bulunamadı.  
  
 `EINVAL`  
 Geçersiz parametre.  
  
 Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Dosyaları ile kullanıldığında `_access_s` işlevi belirtilen dosyanın var olduğundan ve olarak erişilebilir olup olmadığını belirleyen değeri tarafından belirtilen `mode`. Dizinleri ile kullanıldığında `_access_s` yalnızca belirtilen dizin var olup olmadığını belirler. İçinde [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] ve tüm dizinleri okuma ve yazma erişimi daha sonra işletim sistemleri,.  
  
|mod değeri|Dosya denetimleri için|  
|----------------|---------------------|  
|00|Yalnızca varlığı.|  
|02|Yazma izni.|  
|04|Okuma izni.|  
|06|Okuma ve yazma izni.|  
  
 Okuma veya yazma izni dosyayı açma olanağı sağlamak yeterli değil. Bir dosyayı başka bir işlem tarafından kilitlenmiş, örneğin, bunu bile erişilebilir olmayabilir `_access_s` 0 döndürür.  
  
 `_waccess_s`bir joker karakter sürümü `_access_s`, burada `path` bağımsız değişkeni `_waccess_s` bir joker karakter dizesidir. Aksi takdirde, `_waccess_s` ve `_access_s` aynı şekilde davranır.  
  
 Bu işlevler kendi parametreleri doğrulayın. Varsa `path` olan `NULL` veya `mode` geçerli bir moda belirtmiyor açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL` ve geri dönüp `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_taccess_s`|`_access_s`|`_access_s`|`_waccess_s`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_access_s`|\<io.h >|\<errno.h >|  
|`_waccess_s`|\<wchar.h > veya \<io.h >|\<errno.h >|  
  
## <a name="example"></a>Örnek  
 Bu örnekte `_access_s` var olup ve yazma izin verilip verilmeyeceğini görmek için crt_access_s.c adlı dosyayı denetlemek için.  
  
```  
// crt_access_s.c  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    errno_t err = 0;  
  
    // Check for existence.   
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )  
    {  
        printf_s( "File crt_access_s.c exists.\n" );  
  
        // Check for write permission.   
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )  
        {  
            printf_s( "File crt_access_s.c does have "  
                      "write permission.\n" );  
        }  
        else  
        {  
            printf_s( "File crt_access_s.c does not have "  
                      "write permission.\n" );  
        }  
    }  
    else  
    {  
        printf_s( "File crt_access_s.c does not exist.\n" );  
    }  
}  
```  
  
```Output  
File crt_access_s.c exists.  
File crt_access_s.c does not have write permission.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_stat, _wstat işlevleri](../../c-runtime-library/reference/stat-functions.md)