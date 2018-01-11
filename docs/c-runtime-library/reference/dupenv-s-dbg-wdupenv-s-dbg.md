---
title: _dupenv_s_dbg, _wdupenv_s_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _dupenv_s_dbg
- _wdupenv_s_dbg
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
apitype: DLLExport
f1_keywords:
- _tdupenv_s_dbg
- _dupenv_s_dbg
- _wdupenv_s_dbg
dev_langs: C++
helpviewer_keywords:
- _tdupenv_s_dbg function
- dupenv_s_dbg function
- _wdupenv_s_dbg function
- environment variables
- tdupenv_s_dbg function
- wdupenv_s_dbg function
- _dupenv_s_dbg function
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 571772a5a75a36a3c49adeb560a4814a5c7fcae6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dupenvsdbg-wdupenvsdbg"></a>_dupenv_s_dbg, _wdupenv_s_dbg
Geçerli ortamından bir değer alır.  Sürümleri [_dupenv_s, _wdupenv_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md) ile bellek tahsis [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md) ek hata ayıklama bilgileri sağlamak için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _dupenv_s_dbg(  
   char **buffer,  
   size_t *numberOfElements,  
   const char *varname,  
   int blockType,  
   const char *filename,  
   int linenumber  
);  
errno_t _wdupenv_s_dbg(  
   wchar_t **buffer,  
   size_t * numberOfElements,  
   const wchar_t *varname,  
   int blockType,  
   const char *filename,  
   int linenumber  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `buffer`  
 Değişken değeri depolamak için bir arabellek.  
  
 `numberOfElements`  
 Boyutunu `buffer`.  
  
 `varname`  
 Ortam değişkeni adı.  
  
 `blockType`  
 İstenen bellek bloğu türü: `_CLIENT_BLOCK` veya `_NORMAL_BLOCK`.  
  
 `filename`  
 Kaynak dosyanın adını işaretçi veya `NULL`.  
  
 `linenumber`  
 Satır numarası kaynak dosyasında veya `NULL`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı, başarısız olduğunda bir hata kodu sıfır.  
  
 Bu işlevleri parametrelerini doğrulayın; varsa `buffer` veya `varname` olan `NULL`, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, İşlevler kümesi `errno` için `EINVAL` ve geri dönüp `EINVAL`.  
  
 Bu işlevler için yeterli bellek ayıramıyor varsa, bunlar ayarlamak `buffer` için `NULL` ve `numberOfElements` 0 ve return `ENOMEM`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_dupenv_s_dbg` Ve `_wdupenv_s_dbg` işlevleri aynı `_dupenv_s` ve `_wdupenv_s` dışında `_DEBUG` olan tanımlı, bu işlevler hata ayıklama sürümünü kullanmanız [malloc](../../c-runtime-library/reference/malloc.md), [_ malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md), ortam değişkeni değeri için bellek ayrılamadı. Hata ayıklama özellikleri hakkında bilgi için `_malloc_dbg`, bkz: [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Çoğu durumda bu işlevleri açıkça çağırmak gerekmez. Bunun yerine, bayrağı tanımlayabilirsiniz `_CRTDBG_MAP_ALLOC`. Zaman `_CRTDBG_MAP_ALLOC` tanımlanır, çağrılar `_dupenv_s` ve `_wdupenv_s` için eşleştirilir `_dupenv_s_dbg` ve `_wdupenv_s_dbg`, sırasıyla ile `blockType` kümesine `_NORMAL_BLOCK`. Bu nedenle, öbek taşı olarak işaretlemek istediğiniz sürece bu işlevleri açıkça çağırın gerekmez `_CLIENT_BLOCK`. Blok türleri hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tdupenv_s_dbg`|`_dupenv_s_dbg`|`_dupenv_s_dbg`|`_wdupenv_s_dbg`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_dupenv_s_dbg`|\<crtdbg.h >|  
|`_wdupenv_s_dbg`|\<crtdbg.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_dupenv_s_dbg.c  
#include  <stdlib.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
   char *pValue;  
   size_t len;  
   errno_t err = _dupenv_s_dbg( &pValue, &len, "pathext",  
      _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if ( err ) return -1;  
   printf( "pathext = %s\n", pValue );  
   free( pValue );  
   err = _dupenv_s_dbg( &pValue, &len, "nonexistentvariable",  
      _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if ( err ) return -1;  
   printf( "nonexistentvariable = %s\n", pValue );  
   free( pValue ); // It's OK to call free with NULL  
}  
```  
  
## <a name="sample-output"></a>Örnek Çıktı  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [Ortam sabitleri](../../c-runtime-library/environmental-constants.md)   
 [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [_putenv_s, _wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)