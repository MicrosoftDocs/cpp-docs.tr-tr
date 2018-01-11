---
title: __vmx_off | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __vmx_off
dev_langs: C++
helpviewer_keywords:
- VMXOFF instruction
- __vmx_off intrinsic
ms.assetid: 78a32d46-9291-406c-b982-a550855aff18
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcd5f3065e3d388e0b671c048bbffc81a11d3ce5
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="vmxoff"></a>__vmx_off
**Microsoft özel**  
  
 Sanal makine Uzantıları (VMX) işlemci işlemindeki devre dışı bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __vmx_off();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `__vmx_off` İşlevi eşdeğerdir `VMXOFF` makine yönergesi. Bu işlev bir ana bilgisayarın sanal makine İzleyici etkileşiminin bir konuk işletim sistemi ve uygulamaları destekler. Daha fazla bilgi için belge, "Intel Sanallaştırma teknik belirtim IA-32 Intel mimarisi," için arama sırasında numara C97063-002, belge [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__vmx_off`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)