---
title: __svm_vmrun | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_vmrun
dev_langs:
- C++
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3777492212bbff368902acf589f0a3c46ea4ac18
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718685"
---
# <a name="svmvmrun"></a>__svm_vmrun
**Microsoft'a özgü**  
  
 Belirtilen sanal makine denetim bloğu (VMCB) karşılık gelen sanal makine Konuk kod yürütmeyi başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*VmcbPhysicalAddress*|[in] VMCB fiziksel adresi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `__svm_vmrun` İşlevi sanal makine Konuk kodu yürütmeye başlamak için VMCB içinde en az miktarda bilgi kullanır. Kullanım [__svm_vmsave](../intrinsics/svm-vmsave.md) veya [__svm_vmload](../intrinsics/svm-vmload.md) karmaşık kesmeyi işlemek için veya başka bir konuk geçiş yapmak için daha fazla bilgi gerekiyorsa işlev.  
  
 `__svm_vmrun` İşlev, eşdeğer `VMRUN` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Belge için daha fazla bilgi için arama "AMD64 mimarisi Programcı el ile birim 2: Sistem programlama" belge numarasını 24593, düzeltme 3.11 ya da en üstü [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__svm_vmrun`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmsave](../intrinsics/svm-vmsave.md)   
 [__svm_vmload](../intrinsics/svm-vmload.md)