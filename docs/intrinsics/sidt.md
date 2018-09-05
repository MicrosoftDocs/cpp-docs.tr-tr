---
title: __sidt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __sidt
dev_langs:
- C++
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 202e982d30fd0877814fa0c0fe967091057f920f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685983"
---
# <a name="sidt"></a>__sidt
**Microsoft'a özgü**  
  
 Kesme tanımlayıcısı tablosu kaydı (IDTR) değeri, belirtilen bellek konumunda depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __sidt(  
     void *Destination);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `Destination`|IDTR depolandığı konumun bellek işaretçisi.|  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__sidt`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `__sidt` İşlev, eşdeğer `SIDT` makine yönergesi. Belge için daha fazla bilgi için arama "Intel mimarisi yazılım geliştirici el ile 2 birim: yönerge kümesi başvurusu" konumunda [Intel Corporation'da](https://software.intel.com/en-us/articles/intel-sdm) site.  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__lidt](../intrinsics/lidt.md)