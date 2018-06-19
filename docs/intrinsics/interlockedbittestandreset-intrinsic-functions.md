---
title: _interlockedbittestandreset iç işlevler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _interlockedbittestandreset_rel
- _interlockedbittestandreset64
- _interlockedbittestandreset64_HLERelease
- _interlockedbittestandreset_HLERelease
- _interlockedbittestandreset_HLEAcquire
- _interlockedbittestandreset_acq
- _interlockedbittestandreset_cpp
- _interlockedbittestandreset_nf
- _interlockedbittestandreset64_cpp
- _interlockedbittestandreset64_HLEAcquire
- _interlockedbittestandreset
dev_langs:
- C++
helpviewer_keywords:
- lock_btr instruction
- _interlockedbittestandreset64 intrinsic
- _interlockedbittestandreset intrinsic
ms.assetid: 9bbb1442-f2e9-4dc2-b0da-97f3de3493b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c292d344727f2cc473dc444853a2c46d94150dd0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340456"
---
# <a name="interlockedbittestandreset-intrinsic-functions"></a>_interlockedbittestandreset iç işlevler
**Microsoft özel**  
  
 Bit ayarlayan bir yönerge oluşturur `b` adresinin `a` sıfır ve özgün değeri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char _interlockedbittestandreset(  
   long *a,  
   long b  
);  
unsigned char _interlockedbittestandreset_acq(  
   long *a,  
   long b  
);  
unsigned char _interlockedbittestandreset_HLEAcquire(  
   long *a,  
   long b  
);  
unsigned char _interlockedbittestandreset_HLERelease(  
   long *a,  
   long b  
);  
unsigned char _interlockedbittestandreset_nf(  
   long *a,  
   long b  
);  
unsigned char _interlockedbittestandreset_rel(  
   long *a,  
   long b  
);   
unsigned char _interlockedbittestandreset64(  
   __int64 *a,  
   __int64 b  
);   
unsigned char _interlockedbittestandreset64_HLEAcquire(  
   __int64 *a,  
   __int64 b  
);  
unsigned char _interlockedbittestandreset64_HLERelease(  
   __int64 *a,  
   __int64 b  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `a`  
 İncelemek için bellek için bir işaretçi.  
  
 [in] `b`  
 Test etmek için bit konumu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Özgün değeri tarafından belirtilen konumdaki bit `b`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|Üstbilgi|  
|---------------|------------------|------------|  
|`_interlockedbittestandreset`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
|`_interlockedbittestandreset_acq`, `_interlockedbittestandreset_nf`, `_interlockedbittestandreset_rel`|ARM|\<intrin.h >|  
|`_interlockedbittestandreset_HLEAcquire`, `_interlockedbittestandreset_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h >|  
|`_interlockedbittestandreset64`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
|`_interlockedbittestandreset64_HLEAcquire`, `_interlockedbittestandreset64_HLERelease`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h >|  
  
## <a name="remarks"></a>Açıklamalar  
 X86 üzerinde ve [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] işlemciler, bu ön tanımlı kullanan `lock btr` okuyan ve sıfır olarak belirtilen atomik bir işlem bitini yönerge.  
  
 ARM işlemci ile iç bilgileri kullanmak `_acq` ve `_rel` sonekleri edinme ve yayın anlamları gibi önemli bir bölümü başında ve sonunda. ARM iç bilgileri ile bir `_nf` ("hiçbir dilimi") soneki bir bellek engeli hareket değil.  
  
 Donanım kilidi Elision (HLE) yönergeleri, iç bilgileri ile destekleyen Intel işlemcileri üzerinde `_HLEAcquire` ve `_HLERelease` son ekleri kapsayacak performans donanım kilidi yazma adımda ortadan kaldırarak hızlandırabilir işlemci ipucu. Bu yapı HLE desteklemeyen işlemci çağrıldıklarında ipucu yoksayıldı.  
  
 Bu yordamlar, yalnızca iç bilgileri kullanılabilir.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)