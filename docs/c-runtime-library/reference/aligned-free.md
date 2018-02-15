---
title: _aligned_free | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _aligned_free
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
- aligned_free
- _aligned_free
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30b37b6424b02ffb4eab6f1d90d03d7b2a3154b2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="alignedfree"></a>_aligned_free
İle ayrılmış bellek bloğu boşaltır [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _aligned_free (  
   void *memblock  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `memblock`  
 İçin döndürülen bellek bloğu için bir işaretçi `_aligned_malloc` veya `_aligned_offset_malloc` işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 `_aligned_free` işaretlenen `__declspec(noalias)`, işlev genel değişkenler değiştirmemeniz garanti anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md).  
  
 Bu işlev bir _aligned CRT işlevleri aksine, parametresinin doğrulamaz. Varsa `memblock` olan bir `NULL` işaretçi, bu işlev yalnızca hiçbir eylemleri gerçekleştirir. Değiştirme `errno` ve geçersiz parametre işleyicisi çağırma kullanılamaz. _Aligned işlevleri önceden bellek bloğu ayrılamıyor kullanmayan nedeniyle işlevinde bir hata oluştuğunda veya uyuşmazlığın bellek nedeniyle bazı öngörülemeyen calamity oluştuğunda, hata ayıklama rapordan işlevi oluşturur [_RPT, _RPTF, _RPTW, _ Rptfw makrosu](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_aligned_free`|\<malloc.h >|  
  
## <a name="example"></a>Örnek  
 Daha fazla bilgi için bkz: [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri Hizalama](../../c-runtime-library/data-alignment.md)