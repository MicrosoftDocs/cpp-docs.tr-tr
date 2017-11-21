---
title: realloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: realloc
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
- _brealloc
- _nrealloc
- realloc
- _frealloc
dev_langs: C++
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d3243155fa99ec01e5401d0e5aac77d75807b6c1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="realloc"></a>realloc
Bellek bloklarını yeniden ayırma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *realloc(  
   void *memblock,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `memblock`  
 Önceden ayrılmış bellek bloğu işaretçi.  
  
 `size`  
 Yeni boyutunu bayt cinsinden.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `realloc`döndüren bir `void` bırakılan (ve muhtemelen taşınan) bellek bloğu işaretçi.  
  
 Blok verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, özgün blok değiştirilmeden olduğundan, ve `NULL` döndürülür.  
  
 Varsa `size` sıfır gösterdiği blok olduğundan `memblock` serbest bırakılır; dönüş değeri `NULL`, ve `memblock` boşaltılmış bloğundaki işaret eden bırakılır.  
  
 Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun hizalanacak garanti bir depolama alanı işaret eder. Bir işaretçi bir türe dışında almak için `void`, dönüş değerini cast türünü kullanın.  
  
## <a name="remarks"></a>Açıklamalar  
 `realloc` İşlevi bir ayrılmış bellek bloğu boyutu değişir. `memblock` Bağımsız değişkeni bellek bloğu başlangıcına işaret eder. Varsa `memblock` olan `NULL`, `realloc` aynı şekilde davranır `malloc` ve yeni bir blok ayırır `size` bayt sayısı. Varsa `memblock` değil `NULL`, önceki bir çağrı tarafından döndürülen bir işaretçi olmalıdır `calloc`, `malloc`, veya `realloc`.  
  
 `size` Bağımsız değişkeni yeni blok boyutunu bayt cinsinden verir. Yeni blok farklı bir konumda olabilir ancak blok içeriğini kadar kısa yeni ve eski boyutlarının değiştirilmemiştir. Yeni bir bellek konumda yeni blok olabileceğinden, işaretçi tarafından döndürülen `realloc` geçtiğini işaretçi olması garanti edilmemiştir `memblock` bağımsız değişkeni. `realloc`sıfır olmayan yeni ayrılan bellek arabellek büyüme söz konusu olduğunda yapar.  
  
 `realloc`Ayarlar `errno` için `ENOMEM` bellek ayırma başarısız olursa veya bellek miktarını aşıyor istediyseniz `_HEAP_MAXREQ`. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `realloc`çağrıları `malloc` C++ kullanmak için [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) yeni işleyici modu ayarlamak için işlevi. Yeni işleyici modunu gösterir, hatasında kullanılıp `malloc` belirlediği yeni işleyici yordamı çağırmaktır [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). Varsayılan olarak, `malloc` yeni işleyici yordamı bellek ayırma hatası çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, `realloc` bellek ayırmak başarısız `malloc` yeni işleyici yordamını aynı çağırıyor biçimi `new` işleci mu aynı nedenden dolayı başarısız olduğunda. Varsayılan değer geçersiz kılmak için arama  
  
```  
_set_new_mode(1)  
```  
  
 olanları erkenden program veya NEWMODE bağlantısıyla. OBJ (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).  
  
 Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında `realloc` çözümler [_realloc_dbg](../../c-runtime-library/reference/realloc-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).  
  
 `realloc`işaretli `__declspec(noalias)` ve `__declspec(restrict)`, işlev genel değişkenler değiştirmemeniz garanti ve işaretçi döndürdü diğer adı değil anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md) ve [kısıtlamak](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`realloc`|\<stdlib.h > ve \<malloc.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_realloc.c  
// This program allocates a block of memory for  
// buffer and then uses _msize to display the size of that  
// block. Next, it uses realloc to expand the amount of  
// memory used by buffer and then calls _msize again to  
// display the new amount of memory allocated to buffer.  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   long *buffer, *oldbuffer;  
   size_t size;  
  
   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )  
      exit( 1 );  
  
   size = _msize( buffer );  
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );  
  
   // Reallocate and show new size:  
   oldbuffer = buffer;     // save pointer in case realloc fails  
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))   
        ==  NULL )  
   {  
      free( oldbuffer );  // free original block  
      exit( 1 );  
   }  
   size = _msize( buffer );  
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",   
            size );  
  
   free( buffer );  
   exit( 0 );  
}  
```  
  
```Output  
Size of block after malloc of 1000 longs: 4000  
Size of block after realloc of 1000 more longs: 8000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [boş](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)