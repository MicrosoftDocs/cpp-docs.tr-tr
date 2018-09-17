---
title: __writeeflags | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __writeeflags
dev_langs:
- C++
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c01e10a77278f0a02658778ec178f0a4226eb36
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704866"
---
# <a name="writeeflags"></a>__writeeflags
Belirtilen değer programın Yazar durumu ve denetim (EFLAGS) kaydedin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __writeeflags(unsigned Value);  
void __writeeflags(unsigned __int64 Value);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*Değer*|[in] EFLAGS kasaya yazılacak değer. `Value` Parametresi 32 bit bir 32-bit platformu için uzun ve 64 bit, 64-bit platformu için uzun.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__writeeflags`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__readeflags](../intrinsics/readeflags.md)