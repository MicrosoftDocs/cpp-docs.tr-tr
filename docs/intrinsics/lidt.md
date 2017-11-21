---
title: __lidt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __lidt
- __lidt_cpp
dev_langs: C++
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 729df3d4dd415891a9e89ea373e0b4f740e13c1e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="lidt"></a>__lidt
**Microsoft özel**  
  
 Değer belirtilen bellek konumuna bulunan kesme tanımlayıcısı tablosu kaydı (IDTR) yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __lidt(  
     void *Source);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`Source`|İşaretçi IDTR kopyalanacak değerine.|  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__lidt`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `__lidt` İşlevi eşdeğerdir `LIDT` makine yönerge ve yalnızca çekirdek modunda kullanılabilir. Daha fazla bilgi için belge için arama "Intel mimarisi yazılım geliştirici el ile 2 birimi: yönerge kümesi başvurusu" konumundaki [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) site.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__sidt](../intrinsics/sidt.md)