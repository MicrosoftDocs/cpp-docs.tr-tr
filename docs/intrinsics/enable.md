---
title: _tcp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _enable
- _enable_cpp
dev_langs: C++
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e839a70f106ec83c9d2ee786c20f68817e0d4be6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="enable"></a>_enable
**Microsoft özel**  
  
 Kesme sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _enable(void);  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_enable`|x86, ARM,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `_enable`İşlemci Kesme bayrağı ayarlanamadı bildirir. X86 üzerinde sistemleri, bu işlev Kesme bayrağı ayarlanmış oluşturur (`sti`) yönerge.  
  
 Bu işlev yalnızca çekirdek modunda kullanılabilir. Kullanıcı modunda kullandıysanız, ayrıcalıklı yönerge özel durum oluşur.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)