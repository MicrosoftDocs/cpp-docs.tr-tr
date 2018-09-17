---
title: __svm_vmsave | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_vmsave
dev_langs:
- C++
helpviewer_keywords:
- VMSAVE instruction
- __svm_vmsave intrinsic
ms.assetid: 617a60bd-8514-4ba1-8066-bcf4dd481030
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc66784a9f5b6c953516bb30271c973779340e09
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722858"
---
# <a name="svmvmsave"></a>__svm_vmsave
**Microsoft'a özgü**  
  
 İşlemci durumu kümesini, belirtilen sanal makine denetim bloğu (VMCB) depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __svm_vmsave(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*VmcbPhysicalAddress*|[in] VMCB fiziksel adresi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `__svm_vmsave` İşlev, eşdeğer `VMSAVE` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Belge için daha fazla bilgi için arama "AMD64 mimarisi Programcı el ile birim 2: Sistem programlama" belge numarasını 24593, düzeltme 3.11 ya da en üstü [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__svm_vmsave`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmrun](../intrinsics/svm-vmrun.md)   
 [__svm_vmload](../intrinsics/svm-vmload.md)