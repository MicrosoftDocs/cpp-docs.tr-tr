---
title: DontUseNewUseMake sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
dev_langs:
- C++
helpviewer_keywords:
- DontUseNewUseMake class
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f343d0b47d50cd375d186c29ff55b91898aa9c61
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872334"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class DontUseNewUseMake;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İşleç engel `new` RuntimeClass içinde. Sonuç olarak, kullanmalısınız [olun işlevi](../windows/make-function.md) yerine.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[DontUseNewUseMake::operator new İşleci](../windows/dontusenewusemake-operator-new-operator.md)|İşleç aşırı yüklemeler `new` ve RuntimeClass içinde kullanılan engeller.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `DontUseNewUseMake`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [Make İşlevi](../windows/make-function.md)