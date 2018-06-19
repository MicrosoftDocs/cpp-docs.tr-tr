---
title: _heapset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _heapset
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _heapset
- heapset
dev_langs:
- C++
helpviewer_keywords:
- checking heap
- heapset function
- heaps, checking
- debugging [CRT], heap-related problems
- _heapset function
ms.assetid: 9667eeb0-55bc-4c19-af5f-d1fd0a142b3c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c45c4cc3e6e6ffe23378ce0b4f26383369e92058
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391593"
---
# <a name="heapset"></a>_heapset
Yığınları en az tutarlılığını denetler ve ücretsiz girişler için belirtilen değere ayarlar.  
  
> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015'te başlayarak, CRT kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _heapset(   
   unsigned int fill   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fill`  
 Karakter doldurun.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_heapset` Malloc.h içinde tanımlanan tamsayı bildirim sabitlerden birini döndürür.  
  
 `_HEAPBADBEGIN`  
 İlk üst bilgileri bulunamadı veya geçersiz.  
  
 `_HEAPBADNODE`  
 Yığın bozulmuş veya hatalı düğüm bulundu.  
  
 `_HEAPEMPTY`  
 Yığın başlatılmadı.  
  
 `_HEAPOK`  
 Yığın tutarlı gibi görünüyor.  
  
 Ayrıca, bir hata oluşursa, `_heapset` ayarlar `errno` için `ENOSYS`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_heapset` İşlevi boş bellek konumları veya yanlışlıkla üzerine düğümleri gösterir.  
  
 `_heapset` en az tutarlılık yığında denetler ve her bir öbek 's ücretsiz girişlere bayt ayarlar `fill` değeri. Bu bilinen bir değerle bırakılmış belleğe kasıtsız olarak yazılmış veri içerir ve ücretsiz düğümler hangi Öbek bellek konumlarını içeren gösterir. İşletim sistemini desteklemiyor, `_heapset`işlevi (örneğin, Windows 98), döndürür `_HEAPOK` ve ayarlar `errno` için `ENOSYS`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_heapset`|\<malloc.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_heapset.c  
// This program checks the heap and  
// fills in free entries with the character 'Z'.  
  
#include <malloc.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int heapstatus;  
   char *buffer;  
  
   if( (buffer = malloc( 1 )) == NULL ) // Make sure heap is   
      exit( 0 );                        //    initialized       
   heapstatus = _heapset( 'Z' );        // Fill in free entries   
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf( "OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf( "OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
   free( buffer );  
}  
```  
  
```Output  
OK - heap is fine  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../c-runtime-library/memory-allocation.md)   
 [_heapadd](../c-runtime-library/heapadd.md)   
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../c-runtime-library/reference/heapmin.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)