---
title: _aligned_offset_malloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_offset_malloc
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
- _aligned_offset_malloc
- aligned_offset_malloc
dev_langs: C++
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12bb22245619931732d08d3239c89380471f11b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="alignedoffsetmalloc"></a>_aligned_offset_malloc
Belirtilen hizalama sınırında bellek ayırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void * _aligned_offset_malloc(  
   size_t size,   
   size_t alignment,   
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`size`  
 İstenen bellek ayırma boyutu.  
  
 [in]`alignment`  
 Hizalama değeri bir tamsayı güç 2 olmalıdır.  
  
 [in]`offset`  
 Hizalama zorlamak için bellek ayırma içine uzaklığı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış olan bellek bloğu için bir işaretçi veya `NULL` işlemi başarısız olursa.  
  
## <a name="remarks"></a>Açıklamalar  
 `_aligned_offset_malloc`Hizalama iç içe geçmiş bir öğede burada gerektiği durumlarda kullanışlıdır. Örneğin, hizalama iç içe bir sınıf üzerinde gerekiyorsa.  
  
 `_aligned_offset_malloc`dayanır `malloc`; daha fazla bilgi için bkz: [malloc](../../c-runtime-library/reference/malloc.md).  
  
 `_aligned_offset_malloc`işaretli `__declspec(noalias)` ve `__declspec(restrict)`, işlevi genel değişkenler değiştirmemeniz sağlanır ve işaretçiyi değil diğer döndürülen anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md) ve [kısıtlamak](../../cpp/restrict.md).  
  
 Bu işlev ayarlar `errno` için `ENOMEM` bellek ayırma başarısız olursa veya istenen boyutu büyük olursa `_HEAP_MAXREQ`. Hakkında daha fazla bilgi için `errno`, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, `_aligned_offset_malloc` parametrelerini doğrular. Varsa `alignment` 2'in üssü değil veya `offset` büyük veya eşit `size` ve sıfır dışında bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür `NULL` ve ayarlar `errno` için `EINVAL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_aligned_offset_malloc`|\<malloc.h >|  
  
## <a name="example"></a>Örnek  
 Daha fazla bilgi için bkz: [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri Hizalama](../../c-runtime-library/data-alignment.md)