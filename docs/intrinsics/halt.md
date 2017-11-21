---
title: __halt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __halt
- __halt_cpp
dev_langs: C++
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4153bf3a1cf219d50d8e412eec8a0113409f5f8e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="halt"></a>__halt
**Microsoft özel**  
  
 Etkin bir kesme, nonmaskable kesme (NMI) veya bir sıfırlama gerçekleşene kadar mikro durur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __halt( void );  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__halt`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `__halt` İşlevi eşdeğerdir `HLT` makine yönerge ve yalnızca çekirdek modunda kullanılabilir. Daha fazla bilgi için belge için arama "Intel mimarisi yazılım geliştirici el ile 2 birimi: yönerge kümesi başvurusu" konumundaki [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) site.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)