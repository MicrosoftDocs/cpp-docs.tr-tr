---
title: __nop | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __nop
dev_langs:
- C++
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 507f00b82a407b84d374d5f7b9fad8d29101a848
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43682104"
---
# <a name="nop"></a>__nop
**Microsoft'a özgü**  
  
 İşlem gerçekleştirmeyecek bir platforma özgü makine koduna oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __nop();  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__nop`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="remarks"></a>Açıklamalar  
 `__nop` İşlev, eşdeğer `NOP` makine yönergesi. Belge için daha fazla bilgi için arama "Intel mimarisi yazılım geliştirici el ile 2 birim: yönerge kümesi başvurusu" konumunda [Intel Corporation'da](https://software.intel.com/en-us/articles/intel-sdm) site.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__noop](../intrinsics/noop.md)