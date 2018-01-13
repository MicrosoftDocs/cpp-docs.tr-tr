---
title: _recalloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _recalloc
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
- _recalloc
- recalloc
dev_langs: C++
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d1f6052e71746bb05701e0d34f10585d5533be4e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recalloc"></a>_recalloc
Bir birleşimini `realloc` ve `calloc`. Bellekteki bir dizi yeniden ayırır ve 0 öğeleri başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *_recalloc(   
   void *memblock  
   size_t num,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `memblock`  
 Önceden ayrılmış bellek bloğu işaretçi.  
  
 `num`  
 Öğe sayısı.  
  
 `size`  
 Her öğenin bayt cinsinden uzunluğu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_recalloc`döndüren bir `void` bırakılan (ve muhtemelen taşınan) bellek bloğu işaretçi.  
  
 Blok verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, özgün blok değiştirilmeden olduğundan, ve `NULL` döndürülür.  
  
 İstenen boyutu sıfır ise sonra tarafından için blok işaret `memblock` serbest bırakılır; dönüş değeri `NULL`, ve `memblock` boşaltılmış bloğundaki işaret eden bırakılır.  
  
 Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun hizalanacak garanti bir depolama alanı işaret eder. Bir işaretçi bir türe dışında almak için `void`, dönüş değerini cast türünü kullanın.  
  
## <a name="remarks"></a>Açıklamalar  
 `_recalloc` İşlevi bir ayrılmış bellek bloğu boyutu değişir. `memblock` Bağımsız değişkeni bellek bloğu başlangıcına işaret eder. Varsa `memblock` olan `NULL`, `_recalloc` aynı şekilde davranır [calloc](../../c-runtime-library/reference/calloc.md) ve yeni bir blok ayırır `num`  *  `size` bayt sayısı. Her öğe 0 olarak başlatılır. Varsa `memblock` değil `NULL`, önceki bir çağrı tarafından döndürülen bir işaretçi olmalıdır `calloc`, [malloc](../../c-runtime-library/reference/malloc.md), veya [realloc](../../c-runtime-library/reference/realloc.md).  
  
 Yeni bir bellek konumda yeni blok olabileceğinden, işaretçi tarafından döndürülen `_recalloc` geçtiğini işaretçi olması garanti edilmemiştir `memblock` bağımsız değişkeni.  
  
 `_recalloc`Ayarlar `errno` için `ENOMEM` bellek ayırma başarısız olursa veya bellek miktarını aşıyor istediyseniz `_HEAP_MAXREQ`. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `recalloc`çağrıları `realloc` C++ kullanmak için [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) yeni işleyici modu ayarlamak için işlevi. Yeni işleyici modunu gösterir, hatasında kullanılıp `realloc` belirlediği yeni işleyici yordamı çağırmaktır [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). Varsayılan olarak, `realloc` yeni işleyici yordamı bellek ayırma hatası çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, `_recalloc` bellek ayırmak başarısız `realloc` yeni işleyici yordamını aynı çağırıyor biçimi `new` işleci mu aynı nedenden dolayı başarısız olduğunda. Varsayılan değer geçersiz kılmak için arama  
  
```  
_set_new_mode(1)  
```  
  
 program ya da NEWMODE.OBJ bağlantısıyla erken.  
  
 Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında `_recalloc` çözümler [_recalloc_dbg](../../c-runtime-library/reference/recalloc-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).  
  
 `_recalloc`işaretli `__declspec(noalias)` ve `__declspec(restrict)`, işlev genel değişkenler değiştirmemeniz garanti ve işaretçi döndürdü diğer adı değil anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md) ve [kısıtlamak](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_recalloc`|\<stdlib.h > ve \<malloc.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../../c-runtime-library/memory-allocation.md)   
 [_recalloc_dbg](../../c-runtime-library/reference/recalloc-dbg.md)   
 [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)   
 [_aligned_offset_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)   
 [boş](../../c-runtime-library/reference/free.md)   
 [Bağlantı Seçenekleri](../../c-runtime-library/link-options.md)