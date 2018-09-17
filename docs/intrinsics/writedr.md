---
title: __writedr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __writedr
dev_langs:
- C++
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b559edf26c847404d718440e86037cab4026297b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704957"
---
# <a name="writedr"></a>__writedr
Belirtilen değer, belirtilen hata ayıklama kaydı için yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __writedr(unsigned DebugRegister, unsigned DebugValue);  
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue);  
```  
  
#### <a name="parameters"></a>Parametreler  
*DebugRegister*<br/>
[in] Hata ayıklama tanımlayan 0 ile 7 arasında bir sayı kaydedin.  
  
*DebugValue*<br/>
[in] Yazma hata ayıklama için bir değer kaydedin.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu iç öğeler yalnızca çekirdek modunda kullanılabilir ve yordamlar yalnızca iç öğe olarak kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__writedr`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__readdr](../intrinsics/readdr.md)