---
title: _Interlockedexchange iç işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedExchange_rel
- _InterlockedExchange8_nf
- _InterlockedExchange_acq_cpp
- _InterlockedExchange_nf
- _InterlockedExchange64_nf
- _InterlockedExchange_HLEAcquire
- _InterlockedExchange_cpp
- _InterlockedExchange64_acq_cpp
- _InterlockedExchange64_acq
- _InterlockedExchange64_HLERelease
- _InterlockedExchange8_acq
- _InterlockedExchange16_acq
- _InterlockedExchange
- _InterlockedExchange64_HLEAcquire
- _InterlockedExchange8
- _InterlockedExchange64_rel
- _InterlockedExchange_acq
- _InterlockedExchange16
- _InterlockedExchange16_rel
- _InterlockedExchange16_nf
- _InterlockedExchange64
- _InterlockedExchange_HLERelease
- _InterlockedExchange64_cpp
- _InterlockedExchange8_rel
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedExchange8
- _InterlockedExchange64 intrinsic
- _InterlockedExchange_acq intrinsic
- InterlockedExchange64 intrinsic
- _InterlockedExchange64_acq intrinsic
- InterlockedExchange64_acq intrinsic
- _InterlockedExchange16_acq
- _InterlockedExchange8_acq
- _InterlockedExchange16
- _InterlockedExchange8_rel
- InterlockedExchange_acq intrinsic
- InterlockedExchange intrinsic
- _InterlockedExchange16_rel
- _InterlockedExchange16_nf
- _InterlockedExchange intrinsic
- _InterlockedExchange8_nf
ms.assetid: be2f232a-6301-462a-a92b-fcdeb8b0f209
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7a450d683bfa2c358e26a4109a2e8a75c04e233
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716228"
---
# <a name="interlockedexchange-intrinsic-functions"></a>_Interlockedexchange iç işlevleri
**Microsoft'a özgü**  
  
 Belirtilen değere ayarlanacak atomik bir yönerge oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long _InterlockedExchange(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_acq(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_HLEAcquire(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_HLERelease(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_nf(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_rel(  
   long volatile * Target,  
   long Value  
);  
char _InterlockedExchange8(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_acq(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_nf(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_rel(  
   char volatile * Target,  
   char Value  
);  
short _InterlockedExchange16(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_acq(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_nf(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_rel(  
   short volatile * Target,  
   short Value  
);  
__int64 _InterlockedExchange64(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_acq(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_HLEAcquire(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_HLERelease(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_nf(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_rel(  
   __int64 volatile * Target,  
   __int64 Value  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*Hedef*<br/>
[out içinde] Değiştirilecek değer işaretçisi. Bu değişken işlev ayarlar `Value` ve önceki değerini döndürür.  
  
*Değer*<br/>
[in] Değeri ile değiştirilecek değeri tarafından işaret edilen `Target`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşaret ettiği ilk değeri döndürür `Target`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|Üstbilgi|  
|---------------|------------------|------------|  
|`_InterlockedExchange`, `_InterlockedExchange8`, `_InterlockedExchange16`, `_InterlockedExchange64`|x86, ARM, x64|\<intrin.h >|  
|`_InterlockedExchange_acq`, `_InterlockedExchange_nf`, `_InterlockedExchange_rel`, `_InterlockedExchange8_acq`, `_InterlockedExchange8_nf`, `_InterlockedExchange8_rel`, `_InterlockedExchange16_acq`, `_InterlockedExchange16_nf`, `_InterlockedExchange16_rel`, `_InterlockedExchange64_acq`, `_InterlockedExchange64_nf`, `_InterlockedExchange64_rel`,|ARM|\<intrin.h >|  
|`_InterlockedExchange_HLEAcquire`, `_InterlockedExchange_HLERelease`, `_InterlockedExchange64_HLEAcquire`, `_InterlockedExchange64_HLERelease`|x86, x64|\<immintrin.h >|  
  
## <a name="remarks"></a>Açıklamalar  
 `_InterlockedExchange` Win32 Windows SDK'sı için derleyici iç desteği sağlayan [InterlockedExchange](/windows/desktop/api/winbase/nf-winbase-interlockedexchange) işlevi.  
  
 Bazı farklılıklar vardır `_InterlockedExchange` , bunlar içeren veri türleri ve olup işlemciye özgü alma göre farklılık veya release semantikleri kullanılır.  
  
 Sırada `_InterlockedExchange` işlevi 32-bit tamsayı değerleri üzerinde çalışır `_InterlockedExchange8` 8 bit tam sayı değerleri üzerinde çalışan `_InterlockedExchange16` 16 bit tam sayı değerler üzerinde çalışır ve `_InterlockedExchange64` 64-bit tamsayı değerler üzerinde çalışır.  
  
 ARM platformlarında, yapı içleri ile kullanmak `_acq` ve `_rel` sonekleri edinme ve sürüm semantiği gibi kritik bir bölüm başında ve sonunda. Yapı içleri ile bir `_nf` ("hiçbir sınır") soneki bellek önünde bir engel hareket değil.  
  
 Donanım kilit eleme (HLE) yönergeleri yapı içleri ile destekleyen Intel platformlarında `_HLEAcquire` ve `_HLERelease` sonekleri kapsayacak performans donanım kilit yazma adımda ortadan kaldırarak hızlandırabilir işlemci bir ipucu verir. Bu iç HLE desteklemeyen platformları üzerinde çağrılırsa ipucu yoksayıldı.  
  
 Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Nasıl kullanılacağını gösteren bir örnek `_InterlockedExchange`, bkz: [_ınterlockeddecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)