---
title: __svm_clgi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_clgi
dev_langs:
- C++
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54f1a88acef3f3f79a39a8dd68e1beb079f30fec
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42466468"
---
# <a name="svmclgi"></a>__svm_clgi
**Microsoft'a özgü**  
  
 Genel kesme bayrağını kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __svm_clgi( void );  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `__svm_clgi` İşlev, eşdeğer `CLGI` makine yönergesi. Genel kesme bayrağı mikro yoksayar, erteler veya kesme olayları gibi bir g/ç tamamlama, donanım sıcaklık uyarı veya hata ayıklama özel durumu nedeniyle işleme belirler.  
  
 Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Belge için daha fazla bilgi için arama "AMD64 mimarisi Programcı el ile birim 2: Sistem programlama" konumundaki belge numarasını 24593, düzeltme 3.11, [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__svm_clgi`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__svm_stgi](../intrinsics/svm-stgi.md)