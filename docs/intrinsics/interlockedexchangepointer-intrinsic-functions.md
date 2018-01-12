---
title: "_InterlockedExchangePointer iç işlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _InterlockedExchangePointer_cpp
- _InterlockedExchangePointer_rel
- _InterlockedExchangePointer_nf
- _InterlockedExchangePointer_HLERelease
- _InterlockedExchangePointer_acq
- _InterlockedExchangePointer
- _InterlockedExchangePointer_acq_cpp
- _InterlockedExchangePointer_HLEAcquire
dev_langs: C++
helpviewer_keywords:
- _InterlockedExchangePointer_rel intrinsic
- _InterlockedExchangePointer_HLERelease intrinsic
- _InterlockedExchangePointer intrinsic
- _InterlockedExchangePointer_nf intrinsic
- _InterlockedExchangePointer_acq intrinsic
- _InterlockedExchangePointer_HLEAcquire intrinsic
- InterlockedExchangePointer_acq intrinsic
- InterlockedExchangePointer intrinsic
ms.assetid: 0eaca0b0-d79e-406b-892d-b3b462c50bbb
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ba9b7ac5c20c7b4bd4c43db3d76fbb5cfcb331c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="interlockedexchangepointer-intrinsic-functions"></a>_InterlockedExchangePointer iç işlevler
**Microsoft özel**  
  
 İkinci bağımsız değişken olarak geçirilen ilk adresi kopyalar ve ilk özgün adresini döndüren bir atomik exchange işlemi gerçekleştirin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void * _InterlockedExchangePointer(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_acq(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_rel(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_nf(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_HLEAcquire(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_HLERelease(  
   void * volatile * Target,  
   void * Value  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [içinde out]`Target`  
 Exchange için değeri işaretçisine işaretçi. İşlevin değeri ayarlar `Value` ve önceki değerine döndürür.  
  
 [in]`Value`  
 Tarafından değeriyle değiştirilebilmesi için değer işaret için `Target`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlevi gösterdiği ilk değerini döndürür `Target`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|Üstbilgi|  
|---------------|------------------|------------|  
|`_InterlockedExchangePointer`|x86, ARM,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
|`_InterlockedExchangePointer_acq`, `_InterlockedExchangePointer_rel`, `_InterlockedExchangePointer_nf`|ARM|\<intrin.h >|  
|`_InterlockedExchangePointer_HLEAcquire`, `_InterlockedExchangePointer_HLERelease`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]HLE desteği|\<immintrin.h >|  
  
 X86 üzerinde mimarisi, `_InterlockedExchangePointer` çağıran makro `_InterlockedExchange`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir 64-bit sistemde parametreler 64 bit ve 64-bit sınırları hizalanması gerekir; Aksi takdirde, işlev başarısız olur. Bir 32 bit sistemdeki parametreler 32 bit ve 32-bit sınırları hizalanması gerekir. Daha fazla bilgi için bkz: [Hizala](../cpp/align-cpp.md).  
  
 İç bilgiler ile ARM platformlarda kullanın `_acq` ve `_rel` edinmeli ve yayın semantiği, gibi önemli bir bölümü başında ve sonunda varsa sonekleri. İç ile bir `_nf` ("hiçbir dilimi") soneki bir bellek engeli hareket değil.  
  
 Donanım kilidi Elision (HLE) yönergeleri, iç bilgileri ile destek Intel platformlarda `_HLEAcquire` ve `_HLERelease` son ekleri kapsayacak performans donanım kilidi yazma adımda ortadan kaldırarak hızlandırabilir işlemci ipucu. Bu yapı HLE desteklemeyen platformlarda çağrıldıklarında ipucu yoksayıldı.  
  
 Bu yordamlar, yalnızca iç bilgileri kullanılabilir.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)