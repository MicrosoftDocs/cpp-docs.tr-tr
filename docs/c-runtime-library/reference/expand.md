---
title: "siteyi g_enişlet | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _expand
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
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
dev_langs: C++
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 09906e3cdf8455a2a221601f475074a18a72b1b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="expand"></a>_expand
Bellek blok boyutunu değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *_expand(   
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
 `_expand`void işaretçi ayrılabilecek bellek bloğuna döndürür. `_expand`, farklı `realloc`, bir blok boyutunu değiştirmek için taşıyamazsınız. Bu nedenle, blok, taşımadan genişletmek kullanılabilir yeterli bellek varsa `memblock` parametresi `_expand` dönüş değeri ile aynıdır.  
  
 `_expand`döndürür `NULL` ne zaman bir hata algılandığında, işlem sırasında. Örneğin, varsa `_expand` olan bir bellek bloğu daraltmak için kullanılan, küçük blok yığın veya geçersiz blok işaretçi Bozulması algılamak ve dönüş `NULL`.  
  
 Olup olmadığını taşımadan blok verilen boyuta genişletmek kullanılabilir bellek yetersiz, işlevi döndürür `NULL`. `_expand`hiçbir zaman bir boyut istenen'den genişletilmiş bir blok döndürür. Bir hata oluşursa `errno` hatanın yapısını gösterir. Hakkında daha fazla bilgi için `errno`, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun hizalanacak garanti bir depolama alanı işaret eder. Yeni öğe boyutunu denetlemek için kullanmak `_msize`. Bir işaretçi bir türe dışında almak için `void`, dönüş değerini cast türünü kullanın.  
  
## <a name="remarks"></a>Açıklamalar  
 `_expand` İşlevi genişletin veya yığın konumunda taşımadan blok sözleşme çalışılırken tarafından önceden ayrılmış bellek bloğu boyutu değişir. `memblock` Parametresi blok başlangıcına işaret eder. `size` Parametresi yeni blok boyutunu bayt cinsinden verir. Blok içeriğini kadar kısa yeni ve eski boyutlarının değiştirilmemiştir. `memblock`serbest bırakılmış bir blok olmamalıdır.  
  
> [!NOTE]
>  64 bit platformlarda `_expand` blok boyutu 16 K'dan az ise ve bu nedenle Düşük Parçalanma Yığın ayrılan yeni boyutu geçerli boyutundan; özellikle, düşükse blok sözleşme değil `_expand` değişmeden blok bırakır ve döndürür `memblock`.  
  
 Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında `_expand` çözümler [_expand_dbg](../../c-runtime-library/reference/expand-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).  
  
 Bu işlev parametrelerini doğrular. Varsa `memblock` null işaretçi açıklandığı gibi bir geçersiz parametre işleyicisi bu işlevi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `NULL`. Varsa `size` değerinden daha büyük `_HEAP_MAXREQ`, `errno` ayarlanır `ENOMEM` ve işlevi döndürür `NULL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_expand`|\<malloc.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_expand.c  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char *bufchar;  
   printf( "Allocate a 512 element buffer\n" );  
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )  
      exit( 1 );  
   printf( "Allocated %d bytes at %Fp\n",   
         _msize( bufchar ), (void *)bufchar );  
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )  
      printf( "Can't expand" );  
   else  
      printf( "Expanded block to %d bytes at %Fp\n",   
            _msize( bufchar ), (void *)bufchar );  
   // Free memory   
   free( bufchar );  
   exit( 0 );  
}  
```  
  
```Output  
Allocate a 512 element buffer  
Allocated 512 bytes at 002C12BC  
Expanded block to 1024 bytes at 002C12BC  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [boş](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_msize](../../c-runtime-library/reference/msize.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)