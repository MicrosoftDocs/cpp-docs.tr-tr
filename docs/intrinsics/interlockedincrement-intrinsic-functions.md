---
title: "_InterlockedIncrement iç işlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _InterlockedIncrement_acq
- _InterlockedIncrement16_rel_cpp
- _InterlockedIncrement16_cpp
- _InterlockedIncrement64_rel
- _InterlockedIncrement_rel
- _InterlockedIncrement64_nf
- _InterlockedIncrement16_acq_cpp
- _InterlockedIncrement_rel_cpp
- _InterlockedIncrement64
- _InterlockedIncrement64_rel_cpp
- _InterlockedIncrement16_nf
- _InterlockedIncrement16_rel
- _InterlockedIncrement16_acq
- _InterlockedIncrement_nf
- _InterlockedIncrement_acq_cpp
- _InterlockedIncrement64_cpp
- _InterlockedIncrement64_acq_cpp
- _InterlockedIncrement
- _InterlockedIncrement_cpp
- _InterlockedIncrement64_acq
- _InterlockedIncrement16
dev_langs: C++
helpviewer_keywords:
- _InterlockedIncrement64_rel intrinsic
- _InterlockedIncrement16_rel intrinsic
- InterlockedIncrement64_acq intrinsic
- _InterlockedIncrement16 intrinsic
- _InterlockedIncrement16_acq intrinsic
- _InterlockedIncrement_nf intrinsic
- _InterlockedIncrement_rel intrinsic
- _InterlockedIncrement64_nf intrinsic
- InterlockedIncrement_rel intrinsic
- InterlockedIncrement_acq intrinsic
- _InterlockedIncrement64_acq intrinsic
- _InterlockedIncrement16_nf intrinsic
- _InterlockedIncrement intrinsic
- _InterlockedIncrement64 intrinsic
- InterlockedIncrement64_rel intrinsic
- InterlockedIncrement64 intrinsic
- InterlockedIncrement16 intrinsic
- _InterlockedIncrement_acq intrinsic
- InterlockedIncrement intrinsic
ms.assetid: 37700615-f372-438b-bcef-d76e11839482
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6185aee179febe77fa9f5b47793e4becd253e504
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="interlockedincrement-intrinsic-functions"></a>_InterlockedIncrement iç işlevler
**Microsoft özel**  
  
 Derleyici iç Win32 desteği sağlamak [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] [InterlockedIncrement](http://msdn.microsoft.com/library/ms683614.aspx) işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long _InterlockedIncrement(  
   long * lpAddend  
);  
long _InterlockedIncrement_acq(  
   long * lpAddend  
);  
long _InterlockedIncrement_rel(  
   long * lpAddend  
);  
long _InterlockedIncrement_nf(  
   long * lpAddend  
);  
short _InterlockedIncrement16(  
   short * lpAddend  
);  
short _InterlockedIncrement16_acq(  
   short * lpAddend  
);  
short _InterlockedIncrement16_rel(  
   short * lpAddend  
);  
short _InterlockedIncrement16_nf (  
   short * lpAddend  
);  
__int64 _InterlockedIncrement64(  
   __int64 * lpAddend  
);  
__int64 _InterlockedIncrement64_acq(  
   __int64 * lpAddend  
);  
__int64 _InterlockedIncrement64_rel(  
   __int64 * lpAddend  
);   
__int64 _InterlockedIncrement64_nf(  
   __int64 * lpAddend  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [içinde out]`lpAddend`  
 İşaretçi artırılması değişken.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri elde edilen artırılır değerdir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|Üstbilgi|  
|---------------|------------------|------------|  
|`_InterlockedIncrement`, `_InterlockedIncrement16`, `_InterlockedIncrement64`|x86, ARM,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
|`_InterlockedIncrement_acq`, `_InterlockedIncrement_rel`, `_InterlockedIncrement_nf`, `_InterlockedIncrement16_acq`, `_InterlockedIncrement16_rel`, `_InterlockedIncrement16_nf`, `_InterlockedIncrement64_acq`, `_InterlockedIncrement64_rel`, `_InterlockedIncrement64_nf`|ARM|\<intrin.h >|  
  
## <a name="remarks"></a>Açıklamalar  
 Birkaç Çeşitlemeler vardır `_InterlockedIncrement` , bunlar içeren veri türleri ve işlemci özgü olup elde göre farklılık veya yayın semantiği kullanılır.  
  
 Sırada `_InterlockedIncrement` işlev 32 bit tamsayı değerleri üzerinde çalışır `_InterlockedIncrement16` 16 bit tam sayı değerleri üzerinde çalışır ve `_InterlockedIncrement64` 64 bit tam sayı değerleri üzerinde çalışır.  
  
 İç bilgiler ile ARM platformlarda kullanın `_acq` ve `_rel` edinmeli ve yayın semantiği, gibi önemli bir bölümü başında ve sonunda varsa sonekleri. İç ile bir `_nf` ("hiçbir dilimi") soneki bir bellek engeli hareket değil.  
  
 Tarafından için değişkenin işaret `lpAddend` 32-bit sınırında parametre hizalı; Aksi takdirde, bu işlev üzerinde çok işlemcili x86 başarısız olur sistemleri ve x86 olmayan sistemler. Daha fazla bilgi için bkz: [Hizala](../cpp/align-cpp.md).  
  
 Win32 işlevi içinde bildirilen `Wdm.h` veya `Ntddk.h`.  
  
 Bu yordamlar, yalnızca iç bilgileri kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Nasıl kullanılacağına ilişkin bir örnek için `_InterlockedIncrement`, bkz: [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [X86 çakışıyor derleyici](../build/conflicts-with-the-x86-compiler.md)