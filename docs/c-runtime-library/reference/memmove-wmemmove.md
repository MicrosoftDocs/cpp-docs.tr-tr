---
title: memmove, wmemmove | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- memmove
- wmemmove
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
- ntdll.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- memmove
- wmemmove
dev_langs: C++
helpviewer_keywords:
- wmemmove function
- memmove function
ms.assetid: 3a906114-9cf3-40d7-bd99-ee452004f218
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: baf823d7ab09109a4b06a15039ed3fd9d7540191
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="memmove-wmemmove"></a>memmove, wmemmove
Bir arabellek diğerine taşır. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [memmove_s, wmemmove_s](../../c-runtime-library/reference/memmove-s-wmemmove-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *memmove(  
   void *dest,  
   const void *src,  
   size_t count   
);  
wchar_t *wmemmove(  
   wchar_t *dest,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dest`  
 Hedef nesne.  
  
 `src`  
 Kaynak nesne.  
  
 `count`  
 Bayt sayısı (`memmove`) veya karakter (`wmemmove`) kopyalamak için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Değeri `dest`.  
  
## <a name="remarks"></a>Açıklamalar  
 Kopya `count` bayt (`memmove`) veya karakter (`wmemmove`) gelen `src` için `dest`. Kaynak alan ve hedef bazı bölümlerinin çakışırsa, hem işlevleri özgün kaynak bayt çakışan bölgede üzerine önce kopyalandığından emin olun.  
  
 **Güvenlik Notu** boyutu veya daha büyük kaynak arabelleği hedef arabelleği aynı olduğundan emin olun. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 `memmove` Ve `wmemmove` işlevleri yalnızca kullanım dışı varsa sabiti `_CRT_SECURE_DEPRECATE_MEMORY` olan işlevler de kullanım dışı sırayla ekleme deyimi önce tanımlanan, aşağıdaki örnekteki gibi:  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <string.h>  
or  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <wchar.h>  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`memmove`|\<String.h >|  
|`wmemmove`|\<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_memcpy.c  
// Illustrate overlapping copy: memmove  
// always handles it correctly; memcpy may handle  
// it correctly.  
//  
  
#include <memory.h>  
#include <string.h>  
#include <stdio.h>  
  
char str1[7] = "aabbcc";  
  
int main( void )  
{  
   printf( "The string: %s\n", str1 );  
   memcpy( str1 + 2, str1, 4 );  
   printf( "New string: %s\n", str1 );  
  
   strcpy_s( str1, sizeof(str1), "aabbcc" );   // reset string  
  
   printf( "The string: %s\n", str1 );  
   memmove( str1 + 2, str1, 4 );  
   printf( "New string: %s\n", str1 );  
}  
```  
  
```Output  
The string: aabbcc  
New string: aaaabb  
The string: aabbcc  
New string: aaaabb  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ara bellek düzenlemesi](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [strcpy, wcscpy, _mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)