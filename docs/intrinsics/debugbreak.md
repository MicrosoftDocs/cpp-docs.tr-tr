---
title: __debugbreak | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e9aa50ee6cf450276dce70bfa38162a2f6392ed
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="debugbreak"></a>__debugbreak
**Microsoft Specific**  
  
 Bir kesme noktası hata ayıklayıcı çalıştırmak için kullanıcı burada istenir kodunuzda neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __debugbreak();  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|Üstbilgi|  
|---------------|------------------|------------|  
|`__debugbreak`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
  
## <a name="remarks"></a>Açıklamalar  
 `__debugbreak` Derleyici iç, benzer [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), bir kesme noktası neden taşınabilir Win32 yoludur.  
  
> [!NOTE]
>  İle derleme yapılırken **/CLR**, içeren bir işlev `__debugbreak` MSIL için derlenmiş. `asm int 3` bir işlev için yerel derlenecek neden olur. Daha fazla bilgi için bkz: [__asm](../assembler/inline/asm.md).  
  
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
  
 bir x86 üzerinde bilgisayar.  
  
 Bu yordam yalnızca bir iç kullanılabilir.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)