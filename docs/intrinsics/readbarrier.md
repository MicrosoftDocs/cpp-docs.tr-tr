---
title: _ReadBarrier | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _ReadBarrier
dev_langs:
- C++
helpviewer_keywords:
- _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e188089af114abb3e52ef5c0e289f5c8fa013b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33329377"
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
|`_ReadBarrier`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `_ReadBarrier` İç kaldırabilir veya bellek erişim işlemleri çağrı noktası üzerinden yeniden sıralamak derleyici iyileştirmeler sınırlar.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)