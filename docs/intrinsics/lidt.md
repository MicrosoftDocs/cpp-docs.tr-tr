---
title: __lidt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __lidt
- __lidt_cpp
dev_langs:
- C++
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5184d925e5d6712dd547e34341d84919c50e0a43
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724717"
---
# <a name="lidt"></a>__lidt
**Microsoft'a özgü**  
  
 Değer belirtilen bellek konumunda bulunan kesme tanımlayıcısı tablosu kaydı (IDTR) yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __lidt(  
     void *Source);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*Kaynak*|[in] İşaretçi değeri için IDTR kopyalanacak.|  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__lidt`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `__lidt` İşlev, eşdeğer `LIDT` makine yönerge ve yalnızca çekirdek modunda kullanılabilir. Belge için daha fazla bilgi için arama "Intel mimarisi yazılım geliştirici el ile 2 birim: yönerge kümesi başvurusu" konumunda [Intel Corporation'da](https://software.intel.com/en-us/articles/intel-sdm) site.  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__sidt](../intrinsics/sidt.md)