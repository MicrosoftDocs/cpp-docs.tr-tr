---
title: _CrtIsValidHeapPointer | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtIsValidHeapPointer
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
- CrtlsValidHeapPointer
- _CrtIsValidHeapPointer
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsValidHeapPointer function
- CrtIsValidHeapPointer function
ms.assetid: caf597ce-1b05-4764-9f37-0197a982bec5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f888466e0b1625f93c4e1cf66fab0bb85678094
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="crtisvalidheappointer"></a>_CrtIsValidHeapPointer
Belirtilen bir işaretçi bazı C çalışma zamanı kitaplığı, ancak mutlaka tarafından arayanın CRT kitaplık ayrılmış yığın olduğunu doğrular. Visual Studio 2010 önce CRT sürümlerinde, bu belirtilen işaretçi yerel yığın (yalnızca hata ayıklama sürümü) olduğunu doğrular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int _CrtIsValidHeapPointer(   
   const void *userData   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `userData`  
 Ayrılmış bellek bloğu başlangıcı işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_CrtIsValidHeapPointer` Belirtilen işaretçi tüm CRT kitaplık örnekleri tarafından paylaşılan yığınındaki ise TRUE değerini döndürür. Visual Studio 2010 önce CRT sürümlerinde, belirtilen işaretçi yerel yığınında ise bu TRUE döndürür. Aksi takdirde işlevi FALSE değerini döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev kullanmanızı önermiyoruz. Visual Studio 2010 CRT kitaplık ile başlayarak, bir işletim sistemi yığın tüm CRT kitaplıkları paylaşma *işlem yığın*. `_CrtIsValidHeapPointer` İşlevi işaretçiyi CRT yığınında arayanın CRT kitaplık tarafından ayrılan ayrıldı ancak olup olmadığını bildirir. Örneğin, CRT kitaplık Visual Studio 2010 sürümü kullanılarak ayrılmış bir blok göz önünde bulundurun. Varsa `_CrtIsValidHeapPointer` CRT kitaplık Visual Studio 2012 sürümü tarafından dışarı aktarılan işlevin işaretçinin testleri, TRUE döndürür. Bu artık yararlı bir denemedir. Visual Studio 2010 önce CRT kitaplık sürümlerinde işlevi belirli bellek adresi yerel yığın içinde olduğundan emin olmak için kullanılır. Yerel yığın oluşturulur ve C çalışma zamanı kitaplığı belirli bir örneği tarafından yönetilen yığın ifade eder. Dinamik bağlantı kitaplığı (DLL) çalışma zamanı kitaplığı için statik bir bağlantı içeriyorsa, çalışma zamanı öbek ve bu nedenle, uygulamanın yerel yığın bağımsız kendi yığın kendi örneğine sahip. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar `_CrtIsValidHeapPointer` ön işleme sırasında kaldırılır.  
  
 Bu işlev TRUE veya false değeri döndürdüğünden, aşağıdakilerden birini geçirilebilir [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makroları işleme mekanizması basit bir hata ayıklama hata oluştur. Belirtilen adres yerel yığın içinde bulunduğu değilse, aşağıdaki örnekte bir onaylama işlemi hatasına neden olur:  
  
```  
_ASSERTE( _CrtIsValidHeapPointer( userData ) );  
```  
  
 Hakkında daha fazla bilgi için `_CrtIsValidHeapPointer` diğer hata ayıklama işlevleri ve makrolar kullanılabilmesi için bkz: [raporlama makroları](/visualstudio/debugger/macros-for-reporting). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_CrtIsValidHeapPointer`|\<crtdbg.h>|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, Visual Studio 2010 önce C çalışma zamanı kitaplıkları ile kullanıldığında bellek geçerli olup olmadığını sınamak gösterilmiştir. Bu örnekte, eski CRT kitaplık kodu kullanıcılar için sağlanır.  
  
```  
// crt_isvalid.c  
/*  
 * This program allocates a block of memory using _malloc_dbg  
 * and then tests the validity of this memory by calling   
 * _CrtIsMemoryBlock,_CrtIsValidPointer, and _CrtIsValidHeapPointer.  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
#define  TRUE   1  
#define  FALSE  0  
  
int main( void )  
{  
        char *my_pointer;  
  
        /*   
         * Call _malloc_dbg to include the filename and line number  
         * of our allocation request in the header information  
         */  
        my_pointer = (char *)_malloc_dbg( sizeof(char) * 10,   
        _NORMAL_BLOCK, __FILE__, __LINE__ );  
  
        // Ensure that the memory got allocated correctly  
        _CrtIsMemoryBlock((const void *)my_pointer, sizeof(char) * 10,   
        NULL, NULL, NULL );  
  
         // Test for read/write accessibility  
        if (_CrtIsValidPointer((const void *)my_pointer,   
        sizeof(char) * 10, TRUE))  
                printf("my_pointer has read and write accessibility.\n");  
        else  
                printf("my_pointer only has read access.\n");  
  
        // Make sure my_pointer is within the local heap  
        if (_CrtIsValidHeapPointer((const void *)my_pointer))  
                printf("my_pointer is within the local heap.\n");  
        else  
                printf("my_pointer is not located within the local"  
                       " heap.\n");  
  
        free(my_pointer);  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
my_pointer has read and write accessibility.  
my_pointer is within the local heap.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)