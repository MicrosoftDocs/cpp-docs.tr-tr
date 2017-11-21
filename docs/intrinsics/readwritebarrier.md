---
title: _ReadWriteBarrier | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _ReadWriteBarrier
dev_langs: C++
helpviewer_keywords:
- ReadWriteBarrier intrinsic
- _ReadWriteBarrier intrinsic
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 50f58a23f1e2f0fde4a21a4eba64795c8de97629
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="readwritebarrier"></a>_ReadWriteBarrier
**Microsoft özel**  
  
 Bellek erişimleri çağrı noktası üzerinden sıralayabilirsiniz derleyici iyileştirmelerini sınırlar.  
  
> [!CAUTION]
>  `_ReadBarrier`, `_WriteBarrier`, Ve `_ReadWriteBarrier` derleyici iç bilgileri ve `MemoryBarrier` makrosu tüm kullanım dışıdır ve kullanılmamalıdır. İş parçacığı arası iletişim için mekanizmaları gibi kullandığınız [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) ve [std::atomic\<T >](../standard-library/atomic.md), içinde tanımlanan [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md). Donanım erişimi için kullandığınız [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği ile birlikte [volatile](../cpp/volatile-cpp.md) anahtar sözcüğü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _ReadWriteBarrier(void);  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_ReadWriteBarrier`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `_ReadWriteBarrier` İç sınırları kaldırabilir veya bellek erişimleri çağrı noktası üzerinden yeniden sıralamak derleyici iyileştirmeler.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_ReadBarrier](../intrinsics/readbarrier.md)   
 [_WriteBarrier](../intrinsics/writebarrier.md)   
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)