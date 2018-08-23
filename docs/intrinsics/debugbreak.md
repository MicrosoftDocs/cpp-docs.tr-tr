---
title: __debugbreak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __debugbreak_cpp
- __debugbreak
dev_langs:
- C++
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 71b7dfca165e76880370368282bdbd7728315cfa
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42464587"
---
# <a name="debugbreak"></a>__debugbreak
**Microsoft'a özgü**  
  
 Bir kesme noktası, kullanıcı hata ayıklayıcıyı çalıştırmak için burada istenir kodunuzda neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __debugbreak();  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|Üstbilgi|  
|---------------|------------------|------------|  
|`__debugbreak`|x86, ARM, x64|\<intrin.h >|  
  
## <a name="remarks"></a>Açıklamalar  
 `__debugbreak` Derleyici iç, benzer [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), bir kesme noktası neden taşınabilir bir Win32 yolu.  
  
> [!NOTE]
>  İle derlerken **/CLR**, işlevi içeren `__debugbreak` MSIL olarak derlenmiş. `asm int 3` bir işlev için yerel olarak derlenmesine neden olur. Daha fazla bilgi için [__asm](../assembler/inline/asm.md).  
  
 Örneğin:  
  
```  
main() {  
   __debugbreak();  
}  
```  
  
 benzer:  
  
```  
main() {  
   __asm {  
      int 3  
   }  
}  
```  
  
 x x86 bilgisayar.  
  
 Bu yordam yalnızca bir iç öğe olarak kullanılabilir.  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)