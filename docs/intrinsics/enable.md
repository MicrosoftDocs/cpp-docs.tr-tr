---
title: _tcp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _enable
- _enable_cpp
dev_langs:
- C++
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86e6c8ba9fc1b4dff9b1ad947a770ae901937611
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330951"
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
|`_enable`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `_enable` İşlemci Kesme bayrağı ayarlanamadı bildirir. X86 üzerinde sistemleri, bu işlev Kesme bayrağı ayarlanmış oluşturur (`sti`) yönerge.  
  
 Bu işlev yalnızca çekirdek modunda kullanılabilir. Kullanıcı modunda kullandıysanız, ayrıcalıklı yönerge özel durum oluşur.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)