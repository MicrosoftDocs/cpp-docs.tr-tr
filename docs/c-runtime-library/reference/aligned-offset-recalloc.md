---
title: _aligned_offset_recalloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_offset_recalloc
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
- aligned_offset_recalloc
- _aligned_offset_recalloc
dev_langs: C++
helpviewer_keywords:
- aligned_offset_recalloc function
- _aligned_offset_recalloc function
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 201bdc8956ec33c6bfa105a534ed796d84e7064c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="alignedoffsetrecalloc"></a>_aligned_offset_recalloc
İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) ve 0 belleği başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void * _aligned_offset_recalloc(  
   void *memblock,   
   size_t num,   
   size_t size,   
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `memblock`  
 Geçerli bellek bloğu işaretçisi.  
  
 `num`  
 Öğe sayısı.  
  
 `size`  
 Her öğenin bayt cinsinden uzunluğu.  
  
 `alignment`  
 Hizalama değeri bir tamsayı güç 2 olmalıdır.  
  
 `offset`  
 Hizalama zorlamak için bellek ayırma içine uzaklığı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_aligned_offset_recalloc`void işaretçi ayrılabilecek (ve muhtemelen taşınan) bellek bloğuna döndürür. Dönüş değeri `NULL` boyutu sıfır ise ve arabellek bağımsız değişken değil `NULL`, veya blok verilen boyuta genişletmek için yeterli kullanılabilir bellek değilse. İlk durumda, özgün blok serbest bırakılır. İkinci durumda, özgün blok değiştirilmez. Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun hizalanacak garanti bir depolama alanı işaret eder. Dönüş değerini cast türü void, kullanım dışında bir tür için bir işaretçi almak için.  
  
 `_aligned_offset_recalloc`işaretli `__declspec(noalias)` ve `__declspec(restrict)`, işlevi genel değişkenler değiştirmemeniz sağlanır ve işaretçiyi değil diğer döndürülen anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md) ve [kısıtlamak](../../cpp/restrict.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Gibi [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md), `_aligned_offset_recalloc` yapısı içinde bir uzaklığındaki hizalanacak yapısı sağlar.  
  
 `_aligned_offset_recalloc`dayanır `malloc`. Kullanma hakkında daha fazla bilgi için `_aligned_offset_malloc`, bkz: [malloc](../../c-runtime-library/reference/malloc.md). Varsa `memblock` olan `NULL`, işlev çağrıları `_aligned_offset_malloc` dahili olarak.  
  
 Bu işlev ayarlar `errno` için `ENOMEM` bellek ayırma başarısız olursa veya istenen boyuta (`num` * `size`) daha büyük olan `_HEAP_MAXREQ`. Hakkında daha fazla bilgi için `errno`, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, `_aligned_offset_recalloc` parametrelerini doğrular. Varsa `alignment` 2'in üssü değil veya `offset` daha büyük veya eşit istenen boyuta ve sıfır olmayan, bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür `NULL` ve ayarlar `errno` için `EINVAL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_aligned_offset_recalloc`|\<malloc.h >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri hizalama](../../c-runtime-library/data-alignment.md)   
 [_recalloc](../../c-runtime-library/reference/recalloc.md)   
 [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)