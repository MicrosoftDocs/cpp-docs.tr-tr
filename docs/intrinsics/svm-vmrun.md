---
title: __svm_vmrun | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __svm_vmrun
dev_langs: C++
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 000e798dce3fba367a8666d4b5c97bd25fd53253
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="svmvmrun"></a>__svm_vmrun
**Microsoft özel**  
  
 Belirtilen sanal makine denetim bloğu (VMCB) karşılık gelen sanal makine Konuk kodunun yürütülmesini başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`VmcbPhysicalAddress`|VMCB fiziksel adresi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `__svm_vmrun` İşlevi sanal makine Konuk kodu yürütülmeye başlamaya programlandığını VMCB en az miktarda bilgi kullanır. Kullanım [__svm_vmsave](../intrinsics/svm-vmsave.md) veya [__svm_vmload](../intrinsics/svm-vmload.md) karmaşık kesme işlemek için veya başka bir konuk geçiş yapmak için daha fazla bilgi gerekiyorsa işlev.  
  
 `__svm_vmrun` İşlevi eşdeğerdir `VMRUN` makine yönergesi. Bu işlev bir ana bilgisayarın sanal makine İzleyici etkileşiminin bir konuk işletim sistemi ve uygulamaları destekler. Daha fazla bilgi için belge için arama "AMD64 mimarisi Programcı el ile birim 2: Sistem programlama" belge numarası 24593, düzeltme 3.11 ya da daha sonra [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__svm_vmrun`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmsave](../intrinsics/svm-vmsave.md)   
 [__svm_vmload](../intrinsics/svm-vmload.md)