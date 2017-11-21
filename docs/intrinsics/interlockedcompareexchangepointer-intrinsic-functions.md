---
title: "_InterlockedCompareExchangePointer iç işlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _InterlockedCompareExchangePointer_HLERelease
- _InterlockedCompareExchangePointer_rel
- _InterlockedCompareExchangePointer_acq_cpp
- _InterlockedCompareExchangePointer
- _InterlockedCompareExchangePointer_cpp
- _InterlockedCompareExchangePointer_np
- _InterlockedCompareExchangePointer_rel_cpp
- _InterlockedCompareExchangePointer_HLEAcquire
- _InterlockedCompareExchangePointer_acq
- _InterlockedCompareExchangePointer_nf
dev_langs: C++
helpviewer_keywords:
- InterlockedCompareExchangePointer_acq intrinsic
- _InterlockedCompareExchangePointer_rel intrinsic
- _InterlockedCompareExchangePointer_acq intrinsic
- InterlockedCompareExchangePointer_rel intrinsic
- InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_HLERelease intrinsic
- _InterlockedCompareExchangePointer_HLEAcquire intrinsic
- _InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_nf intrinsic
- _InterlockedCompareExchangePointer_np intrinsic
ms.assetid: 97fde59d-2bf9-42aa-a0fe-a5b6befdd44b
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9570a609f4775a8ec6d7f3d69da566ca4bb69a11
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="interlockedcompareexchangepointer-intrinsic-functions"></a>_InterlockedCompareExchangePointer iç işlevler
**Microsoft özel**  
  
 Depolar atomik bir işlem gerçekleştirir `Exchange` içinde adres `Destination` adres `Comparand` ve `Destination` adresi eşit.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void * _InterlockedCompareExchangePointer (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_acq (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_HLEAcquire (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_HLERelease (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_nf (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_np (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
long _InterlockedCompareExchangePointer_rel (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [içinde out]`Destination`  
 Hedef değeri için bir işaretçi işaretçi. Oturum açma göz ardı edilir.  
  
 [in]`Exchange`  
 Exchange işaretçi. Oturum açma göz ardı edilir.  
  
 [in]`Comparand`  
 Hedefe Karşılaştırılacak işaretçi. Oturum açma göz ardı edilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri hedef ilk değerdir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|Üstbilgi|  
|---------------|------------------|------------|  
|`_InterlockedCompareExchangePointer`|x86, ARM,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
|`_InterlockedCompareExchangePointer_acq`, `_InterlockedCompareExchangePointer_nf`, `_InterlockedCompareExchangePointer_rel`|ARM|\<iiintrin.h >|  
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h >|  
  
## <a name="remarks"></a>Açıklamalar  
 `_InterlockedCompareExchangePointer`bir atomik karşılaştırması gerçekleştirir `Destination` ele `Comparand` adresi. Varsa `Destination` adresidir eşit `Comparand` adresi `Exchange` adresi tarafından belirtilen adresi depolanır `Destination`. Aksi takdirde, hiçbir işlem yapılmadı.  
  
 `_InterlockedCompareExchangePointer`derleyici iç Win32 desteği sağlar [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] [_InterlockedCompareExchangePointer](http://msdn.microsoft.com/library/ff547863.aspx) işlevi.  
  
 Nasıl kullanılacağını gösteren bir örnek `_InterlockedCompareExchangePointer`, bkz: [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
 İç bilgiler ile ARM platformlarda kullanın `_acq` ve `_rel` edinmeli ve yayın semantiği, gibi önemli bir bölümü başında ve sonunda varsa sonekleri. ARM iç bilgileri ile bir `_nf` ("hiçbir dilimi") soneki bir bellek engeli hareket değil.  
  
 İç bilgiler ile bir `_np` ("hiçbir hazırlık") soneki derleyici tarafından eklenen bir olası hazırlık işlemin engelleme.  
  
 Donanım kilidi Elision (HLE) yönergeleri, iç bilgileri ile destek Intel platformlarda `_HLEAcquire` ve `_HLERelease` son ekleri kapsayacak performans donanım kilidi yazma adımda ortadan kaldırarak hızlandırabilir işlemci ipucu. Bu yapı HLE desteklemeyen platformlarda çağrıldıklarında ipucu yoksayıldı.  
  
 Bu yordamlar, yalnızca iç bilgileri kullanılabilir.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)