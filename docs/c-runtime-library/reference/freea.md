---
title: _freea | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _freea
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
- freea
- _freea
dev_langs:
- C++
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6bf2bd2d3dacba307f529798727e7af745bf7cf9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="freea"></a>_freea
Kaldırır veya bir bellek bloğu boşaltır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _freea(   
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `memblock`  
 Boşaltılacak bellek bloğu önceden ayrılmış.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yok.  
  
## <a name="remarks"></a>Açıklamalar  
 `_freea` İşlevi bir bellek bloğu kaldırır (`memblock`) önceden ayrılmış bir çağrı tarafından [_malloca](../../c-runtime-library/reference/malloca.md). `_freea` Öbek veya yığın belleği ayrıldı olmadığını görmek için denetler. Yığında ayırdığınızda `_freea` hiçbir şey yapmaz. Yığında ayrılmış olan, bloğu ayrıldı, istenen bayt sayısı boşaltılmış bayt sayısı eşdeğerdir. Varsa `memblock` olan `NULL`, işaretçi yok sayılır ve `_freea` hemen döndürür. Geçersiz bir işaretçi serbest bırakma girişimi (tarafından ayrılmamış bir bellek bloğu için bir işaretçi `_malloca`) sonraki ayırma isteklerini etkiler ve hatalara neden olabilir.  
  
 `_freea` çağrıları `free` dahili olarak bellek öbek üzerinde ayrılır bulursa. Bellek öbek üzerinde olduğu ya da yığın işaretleyicisi tarafından belirlenir bellek tahsis edilen bellek hemen önceki adresindeki yerleştirilir.  
  
 Bellek boşaltma içinde bir hata meydana gelirse `errno` bilgilerle hata işletim sisteminden yapısı üzerinde ayarlanır. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Bir bellek bloğu serbest sonra [_heapmin](../../c-runtime-library/reference/heapmin.md) kullanılmayan bölgeler birleştirmesi ve işletim sistemine geri serbest öbek boş bellek miktarı en aza indirir. İşletim sistemine serbest bırakılmış belleği serbest havuza geri ve yeniden ayırma için kullanılamıyor.  
  
 Çağrı `_freea` tüm çağrıları eşlik gerekir `_malloca`. Ayrıca çağırmak için bir hata olduğunu `_freea` aynı bellek üzerindeki iki kez. Ne zaman uygulamanın bağlı olduğu C çalışma zamanı kitaplıkları ile bir hata ayıklama sürümü özellikle [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md) tanımlayarak etkin Özellikler `_CRTDBG_MAP_ALLOC`, Bul eksik veya yinelenen çağrıları için daha kolay `_freea`. Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).  
  
 `_freea` işaretlenen `__declspec(noalias)`, işlev genel değişkenler değiştirmemeniz garanti anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_freea`|\<stdlib.h > ve \<malloc.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_malloca](../../c-runtime-library/reference/malloca.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../../c-runtime-library/memory-allocation.md)   
 [_malloca](../../c-runtime-library/reference/malloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)