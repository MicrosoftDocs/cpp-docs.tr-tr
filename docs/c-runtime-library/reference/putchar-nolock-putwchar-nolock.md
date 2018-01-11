---
title: _putchar_nolock, _putwchar_nolock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _putchar_nolock
- _putwchar_nolock
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
- putwchar_nolock
- _puttchar_nolock
- _putchar_nolock
- _putwchar_nolock
- putchar_nolock
dev_langs: C++
helpviewer_keywords:
- _puttchar_nolock function
- putchar_nolock function
- characters, writing
- standard output, writing to
- putwchar_nolock function
- _putchar_nolock function
- _putwchar_nolock function
- puttchar_nolock function
ms.assetid: 9ac68092-bfc3-4352-b486-c3e780220575
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c4183b9ab4b15e4e39ec685934a9c2c591303f78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="putcharnolock-putwcharnolock"></a>_putchar_nolock, _putwchar_nolock
Bir karakter Yazar **stdout** iş parçacığı kilitleme olmadan.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int _putchar_nolock(  
   int c   
);  
wint_t _putwchar_nolock(  
   wchar_t c   
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Yazılacak karakter.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bkz: **putchar, putwchar**.  
  
## <a name="remarks"></a>Açıklamalar  
 **putchar_nolock** ve `_putwchar_nolock` sürümleri için özdeş **_nolock** diğer iş parçacıkları tarafından girişime korunmayan dışında soneki. Bunlar başka bir iş parçacığı kilitleme zahmetine değil olduğundan daha hızlı olabilir. Bu işlevler yalnızca iş parçacığı bağlamları tek iş parçacıklı uygulamalar veya arama kapsamı zaten iş parçacığı yalıtım işleme olduğu gibi kullanın.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_puttchar_nolock`|`_putchar_nolock`|`_putchar_nolock`|`_putwchar_nolock`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_putchar_nolock`|\<stdio.h >|  
|`_putwchar_nolock`|\<stdio.h > veya \<wchar.h >|  
  
 Konsol desteklenmeyen [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Konsol ile ilişkili standart akış tanıtıcıları —`stdin`, `stdout`, ve `stderr`— C çalışma zamanı işlevleri de kullanabilmek için önce yeniden yönlendirilmesi gerekiyor [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_putchar_nolock.c  
/* This program uses putchar to write buffer  
 * to stdout. If an error occurs, the program  
 * stops before writing the entire buffer.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char *p, buffer[] = "This is the line of output\n";  
   int  ch;  
  
   ch = 0;  
  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = _putchar_nolock( *p );  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
This is the line of output  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)