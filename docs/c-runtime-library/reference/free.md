---
title: "Ücretsiz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: free
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
f1_keywords: free
dev_langs: C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1be3f7141a8483aa7b0d43195b08506691e34fe3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="free"></a>serbest
Kaldırır veya bir bellek bloğu boşaltır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void free(   
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `memblock`  
 Boşaltılacak bellek bloğu önceden ayrılmış.  
  
## <a name="remarks"></a>Açıklamalar  
 `free` İşlevi bir bellek bloğu kaldırır (`memblock`) önceden ayrılmış bir çağrı tarafından `calloc`, `malloc`, veya `realloc`. Boşaltılmış bayt sayısı bloğu ayrıldı, istenen bayt sayısı eşdeğerdir (veya yeniden tahsis edilmesini durumunda `realloc`). Varsa `memblock` olan `NULL`, işaretçi yok sayılır ve `free` hemen döndürür. Geçersiz bir işaretçi serbest bırakma girişimi (tarafından ayrılmamış bir bellek bloğu için bir işaretçi `calloc`, `malloc`, veya `realloc`) sonraki ayırma isteklerini etkiler ve hatalara neden olabilir.  
  
 Bellek boşaltma içinde bir hata meydana gelirse `errno` bilgilerle hata işletim sisteminden yapısı üzerinde ayarlanır. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Bir bellek bloğu serbest sonra [_heapmin](../../c-runtime-library/reference/heapmin.md) kullanılmayan bölgeler birleştirmesi ve işletim sistemine geri serbest öbek boş bellek miktarı en aza indirir. İşletim sistemine serbest bırakılmış belleği serbest havuza geri ve yeniden ayırma için kullanılamıyor.  
  
 Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında `free` çözümler [_free_dbg](../../c-runtime-library/reference/free-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).  
  
 `free`işaretlenen `__declspec(noalias)`, işlev genel değişkenler değiştirmemeniz garanti anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md).  
  
 İle ayrılan belleği boşaltmak için [_malloca](../../c-runtime-library/reference/malloca.md), kullanın [_freea](../../c-runtime-library/reference/freea.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`free`|\<stdlib.h > ve \<malloc.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [malloc](../../c-runtime-library/reference/malloc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../../c-runtime-library/memory-allocation.md)   
 [_alloca](../../c-runtime-library/reference/alloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_freea](../../c-runtime-library/reference/freea.md)