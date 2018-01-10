---
title: __writecr4 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _writecr4
dev_langs: C++
helpviewer_keywords: _writecr4 intrinsic
ms.assetid: ab7651d7-b86b-4be7-a0a0-7263099c70fc
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab0ffbd7fab174f42cf5ad10eaad7032f5352567
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="writecr4"></a>__writecr4
**Microsoft özel**  
  
 Değer Yazar `Data` CR4 kaydı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void writecr4(   
   unsigned __int64 Data   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`Data`  
 CR4 kasaya yazılacak değer.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__writecr4`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu iç yalnızca çekirdek modunda kullanılabilir ve yordam yalnızca bir iç kullanılabilir.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)