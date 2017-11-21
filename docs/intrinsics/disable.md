---
title: _disable | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _disable_cpp
- _disable
dev_langs: C++
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 85b4b454b84767290f6c95255e4b2d3fc341dda9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="disable"></a>_disable
**Microsoft özel**  
  
 Kesme devre dışı bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _disable(void);  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_disable`|x86, ARM,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `_disable`İşlemci Kesme bayrağını Temizle bildirir. X86 üzerinde sistemleri, bu işlev kesme bayrağını Temizle oluşturur (`cli`) yönerge.  
  
 Bu işlev yalnızca çekirdek modunda kullanılabilir. Kullanıcı modunda kullandıysanız, ayrıcalıklı yönerge özel çalışma zamanında durum oluşur.  
  
 ARM platformda, bu yordam yalnızca bir iç kullanılabilir.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)