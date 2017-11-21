---
title: _heapchk | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _heapchk
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _heapchk
- heapchk
dev_langs: C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- consistency checking of heaps
- heapchk function
- heaps, checking consistency
- _heapchk function
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9fcbafbb98385878dbc84f300e8d2bf0dac581c7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="heapchk"></a>_heapchk
Öbek üzerinde tutarlılık denetimleri çalıştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _heapchk( void );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_heapchk`Malloc.h içinde tanımlanan tamsayı bildirim sabitlerden birini döndürür.  
  
 `_HEAPBADBEGIN`  
 İlk üst bilgileri bozuk veya bulunamıyor.  
  
 `_HEAPBADNODE`  
 Hatalı düğüm bulunamadı veya yığın bozulmuş.  
  
 `_HEAPBADPTR`  
 İşaretçi öbek halinde geçerli değil.  
  
 `_HEAPEMPTY`  
 Yığın başlatılmadı.  
  
 `_HEAPOK`  
 Yığın tutarlı gibi görünüyor.  
  
 Ayrıca, bir hata oluşursa, `_heapchk` ayarlar `errno` için `ENOSYS`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_heapchk` İşlevi yığın ile ilgili sorunlar için en az öbek tutarlılık denetimi tarafından hata ayıklama yardımcı olur. İşletim sistemini desteklemiyor, `_heapchk`işlevi (örneğin, Windows 98), döndürür `_HEAPOK` ve ayarlar `errno` için `ENOSYS`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_heapchk`|\<malloc.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_heapchk.c  
// This program checks the heap for  
// consistency and prints an appropriate message.  
  
#include <malloc.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  heapstatus;  
   char *buffer;  
  
   // Allocate and deallocate some memory  
   if( (buffer = (char *)malloc( 100 )) != NULL )  
      free( buffer );  
  
   // Check heap status  
   heapstatus = _heapchk();  
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf(" OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf(" OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
}  
```  
  
```Output  
OK - heap is fine  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../../c-runtime-library/memory-allocation.md)   
 [_heapadd](../../c-runtime-library/heapadd.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_heapset](../../c-runtime-library/heapset.md)   
 [_heapwalk](../../c-runtime-library/reference/heapwalk.md)