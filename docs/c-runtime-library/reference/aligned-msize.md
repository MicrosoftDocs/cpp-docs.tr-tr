---
title: _aligned_msize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_msize
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
- _aligned_msize
- aligned_msize
dev_langs: C++
helpviewer_keywords:
- aligned_msize function
- _aligned_msize function
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f94bf064f4fe6e604675eba28867ccdc460530d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="alignedmsize"></a>_aligned_msize
Yığın ayrılan bellek bloğu boyutu döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t _msize(  
   void *memblock,  
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`memblock`  
 Bellek bloğu işaretçi.  
  
 [in]`alignment`  
 Hizalama değeri bir tamsayı güç 2 olmalıdır.  
  
 [in]`offset`  
 Hizalama zorlamak için bellek ayırma içine uzaklığı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Boyutu (bayt) imzalanmamış tamsayı olarak döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_aligned_msize` İşlevi için bir çağrı tarafından ayrılan bellek bloğu bayt cinsinden boyutu döndürüyor [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_realloc](../../c-runtime-library/reference/aligned-realloc.md). `alignment` Ve `offset` değerleri blok ayrılan işleve değerleri aynı olmalıdır.  
  
 Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında `_aligned_msize` çözümler [_aligned_msize_dbg](../../c-runtime-library/reference/aligned-msize-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).  
  
 Bu işlev, parametre doğrular. Varsa `memblock` null işaretçi veya `alignment` 2 ' nin güç değil `_msize` açıklandığı gibi bir geçersiz parametre işleyiciyi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Hata işleniyorsa işlevi ayarlar `errno` için `EINVAL` ve -1 döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_msize`|\<malloc.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek Ayırma](../../c-runtime-library/memory-allocation.md)