---
title: "_InterlockedAnd iç işlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _InterlockedAnd_rel
- _InterlockedAnd_cpp
- _InterlockedAnd8_nf
- _InterlockedAnd
- _InterlockedAnd_HLERelease
- _InterlockedAnd8_np
- _InterlockedAnd16_rel
- _InterlockedAnd64_np
- _InterlockedAnd_np
- _InterlockedAnd64_HLERelease
- _InterlockedAnd64
- _InterlockedAnd64_nf
- _InterlockedAnd64_HLEAcquire
- _InterlockedAnd16
- _InterlockedAnd16_nf
- _InterlockedAnd8
- _InterlockedAnd_HLEAcquire
- _InterlockedAnd_acq
- _InterlockedAnd16_np
- _InterlockedAnd64_cpp
- _InterlockedAnd64_acq
- _InterlockedAnd16_acq
- _InterlockedAnd8_acq
- _InterlockedAnd64_rel
- _InterlockedAnd_nf
- _InterlockedAnd8_rel
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedAnd64_np intrinsic
- _InterlockedAnd intrinsic
- _InterlockedAnd64 intrinsic
- _InterlockedAnd8_rel intrinsic
- InterlockedAnd64 intrinsic
- _InterlockedAnd16_np intrinsic
- _InterlockedAnd64_nf intrinsic
- _InterlockedAnd_nf intrinsic
- _InterlockedAnd_np intrinsic
- _InterlockedAnd64_HLERelease intrinsic
- _InterlockedAnd16_rel intrinsic
- _InterlockedAnd_HLERelease intrinsic
- _InterlockedAnd64_acq intrinsic
- _InterlockedAnd16 intrinsic
- _InterlockedAnd8_nf intrinsic
- _InterlockedAnd64_rel intrinsic
- _InterlockedAnd8_np intrinsic
- _InterlockedAnd_rel intrinsic
- InterlockedAnd intrinsic
- _InterlockedAnd8_acq intrinsic
- _InterlockedAnd_acq intrinsic
- _InterlockedAnd64_HLEAcquire intrinsic
- _InterlockedAnd16_acq intrinsic
- _InterlockedAnd16_nf intrinsic
- _InterlockedAnd8 intrinsic
- _InterlockedAnd_HLEAcquire intrinsic
ms.assetid: ad271dc3-42cd-47d0-9f65-30d5cfeb66fc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c1b9578accea832ceb4ff5bf58e0e750851d736
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="interlockedand-intrinsic-functions"></a>_InterlockedAnd iç işlevler
**Microsoft Specific**  
  
 Birden çok iş parçacığı tarafından paylaşılan bir değişken üzerinde atomik bit düzeyinde AND işlemi gerçekleştirmek için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long _InterlockedAnd(  
   long volatile * value,  
   long mask  
);  
long _InterlockedAnd_acq(  
   long volatile * value,  
   long mask  
);  
long _InterlockedAnd_HLEAcquire(  
   long volatile * value,  
   long mask  
);  
long _InterlockedAnd_HLERelease(  
   long volatile * value,  
   long mask  
);  
long _InterlockedAnd_nf(  
   long volatile * value,  
   long mask  
);  
long _InterlockedAnd_np(  
   long volatile * value,  
   long mask  
);  
long _InterlockedAnd_rel(  
   long volatile * value,  
   long mask  
);  
char _InterlockedAnd8(  
   char volatile * value,  
   char mask  
);  
char _InterlockedAnd8_acq(  
   char volatile * value,  
   char mask  
);  
char _InterlockedAnd8_nf(  
   char volatile * value,  
   char mask  
);  
char _InterlockedAnd8_np(  
   char volatile * value,  
   char mask  
);  
char _InterlockedAnd8_rel(  
   char volatile * value,  
   char mask  
);  
short _InterlockedAnd16(  
   short volatile * value,  
   short mask  
);  
short _InterlockedAnd16_acq(  
   short volatile * value,  
   short mask  
);  
short _InterlockedAnd16_nf(  
   short volatile * value,  
   short mask  
);  
short _InterlockedAnd16_np(  
   short volatile * value,  
   short mask  
);  
short _InterlockedAnd16_rel(  
   short volatile * value,  
   short mask  
);  
__int64 _InterlockedAnd64(  
   __int64 volatile* value,  
   __int64 mask  
);  
__int64 _InterlockedAnd64_acq(  
   __int64 volatile* value,  
   __int64 mask  
);   
__int64 _InterlockedAnd64_HLEAcquire(  
   __int64 volatile* value,  
   __int64 mask  
);  
__int64 _InterlockedAnd64_HLERelease(  
   __int64 volatile* value,  
   __int64 mask  
);  
__int64 _InterlockedAnd64_nf(  
   __int64 volatile* value,  
   __int64 mask  
);  
__int64 _InterlockedAnd64_np(  
   __int64 volatile* value,  
   __int64 mask  
);  
__int64 _InterlockedAnd64_rel(  
   __int64 volatile* value,  
   __int64 mask  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [içinde out] `value`  
 Sonuç değiştirilecek ilk işlenen bir işaretçi.  
  
 [in] `mask`  
 İkinci işlenen.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İlk işlenen özgün değeri.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|Üstbilgi|  
|---------------|------------------|------------|  
|`_InterlockedAnd`, `_InterlockedAnd8`, `_InterlockedAnd16`, `_InterlockedAnd64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
|`_InterlockedAnd_acq`, `_InterlockedAnd_nf`, `_InterlockedAnd_rel`, `_InterlockedAnd8_acq`, `_InterlockedAnd8_nf`, `_InterlockedAnd8_rel`, `_InterlockedAnd16_acq`, `_InterlockedAnd16_nf`, `_InterlockedAnd16_rel`, `_InterlockedAnd64_acq`, `_InterlockedAnd64_nf`, `_InterlockedAnd64_rel`|ARM|\<intrin.h >|  
|`_InterlockedAnd_np`, `_InterlockedAnd8_np`, `_InterlockedAnd16_np`, `_InterlockedAnd64_np`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
|`_InterlockedAnd_HLEAcquire`, `_InterlockedAnd_HLERelease`, `_InterlockedAnd64_HLEAcquire`, `_InterlockedAnd64_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h >|  
  
## <a name="remarks"></a>Açıklamalar  
 Her işlev adına bağımsız bit boyutunu belirtir.  
  
 İç bilgiler ile ARM platformlarda kullanın `_acq` ve `_rel` sonekleri edinme ve yayın anlamları gibi önemli bir bölümü başında ve sonunda. İç bilgiler ile bir `_nf` ("hiçbir dilimi") soneki bir bellek engeli hareket değil.  
  
 İç bilgiler ile bir `_np` ("hiçbir hazırlık") soneki derleyici tarafından eklenen bir olası hazırlık işlemin engelleme.  
  
 Donanım kilidi Elision (HLE) yönergeleri, iç bilgileri ile destek Intel platformlarda `_HLEAcquire` ve `_HLERelease` son ekleri kapsayacak performans donanım kilidi yazma adımda ortadan kaldırarak hızlandırabilir işlemci ipucu. Bu yapı HLE desteklemeyen platformlarda çağrıldıklarında ipucu yoksayıldı.  
  
## <a name="example"></a>Örnek  
  
```  
// InterlockedAnd.cpp  
// Compile with: /Oi  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedAnd)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FFFF00;  
        long retval;  
        retval = _InterlockedAnd(&data1, data2);  
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);   
}  
```  
  
```Output  
0xff00 0xffff00 0xff00ff00  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)