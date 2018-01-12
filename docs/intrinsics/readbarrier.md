---
title: _ReadBarrier | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _ReadBarrier
dev_langs: C++
helpviewer_keywords: _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c0ce47629dc26371a896085bf3094f186fd80ee1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="readbarrier"></a>_ReadBarrier  
  
**Microsoft özel**  
  
 Bellek erişim işlemleri çağrı noktası üzerinden sıralayabilirsiniz derleyici iyileştirmelerini sınırlar.  
  
> [!CAUTION]
>  `_ReadBarrier`, `_WriteBarrier`, Ve `_ReadWriteBarrier` derleyici iç bilgileri ve `MemoryBarrier` makrosu tüm kullanım dışıdır ve kullanılmamalıdır. İş parçacığı arası iletişim için mekanizmaları gibi kullandığınız [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) ve [std::atomic\<T >](../standard-library/atomic.md) içinde tanımlanan [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md). Donanım erişimi için kullandığınız [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği ile birlikte [volatile](../cpp/volatile-cpp.md) anahtar sözcüğü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _ReadBarrier(void);  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_ReadBarrier`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `_ReadBarrier` İç kaldırabilir veya bellek erişim işlemleri çağrı noktası üzerinden yeniden sıralamak derleyici iyileştirmeler sınırlar.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)