---
title: _Interlockedıncrement iç işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 900200eb1894a4f7065a008aeada9b90e71c6fcd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42575794"
---
# <a name="interlockedincrement-intrinsic-functions"></a>_Interlockedıncrement iç işlevleri
**Microsoft'a özgü**  
  
 Win32 Windows SDK'sı derleyici iç desteği [InterlockedIncrement](/windows/desktop/api/winbase/nf-winbase-interlockedincrement) işlevi.  
  
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
 [out içinde] `lpAddend`  
 Arttırılacak değişken işaretçisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri elde edilen artan değerdir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|Üstbilgi|  
|---------------|------------------|------------|  
|`_InterlockedIncrement`, `_InterlockedIncrement16`, `_InterlockedIncrement64`|x86, ARM, x64|\<intrin.h >|  
|`_InterlockedIncrement_acq`, `_InterlockedIncrement_rel`, `_InterlockedIncrement_nf`, `_InterlockedIncrement16_acq`, `_InterlockedIncrement16_rel`, `_InterlockedIncrement16_nf`, `_InterlockedIncrement64_acq`, `_InterlockedIncrement64_rel`, `_InterlockedIncrement64_nf`|ARM|\<intrin.h >|  
  
## <a name="remarks"></a>Açıklamalar  
 Bazı farklılıklar vardır `_InterlockedIncrement` , bunlar içeren veri türleri ve olup işlemciye özgü alma göre farklılık veya release semantikleri kullanılır.  
  
 Sırada `_InterlockedIncrement` işlevi 32-bit tamsayı değerleri üzerinde çalışır `_InterlockedIncrement16` 16 bit tam sayı değerler üzerinde çalışır ve `_InterlockedIncrement64` 64-bit tamsayı değerler üzerinde çalışır.  
  
 ARM platformlarında, yapı içleri ile kullanmak `_acq` ve `_rel` almak ve yayın semantiğini gibi kritik bir bölüm başında ve sonunda sonekleri. İç bir `_nf` ("hiçbir sınır") soneki bellek önünde bir engel davranmaz.  
  
 Değişkeni tarafından işaret edilen `lpAddend` parametresi bir 32-bit sınırında hizalanmış olmalıdır; aksi takdirde, bu işlev üzerinde çok işlemcili x86 başarısız sistemleri ve x86 olmayan sistemler. Daha fazla bilgi için [hizalama](../cpp/align-cpp.md).  
  
 Win32 işlevi içinde bildirilen `Wdm.h` veya `Ntddk.h`.  
  
 Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Nasıl kullanılacağını gösteren bir örnek `_InterlockedIncrement`, bkz: [_ınterlockeddecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)