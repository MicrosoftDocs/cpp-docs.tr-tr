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
ms.openlocfilehash: 351b38a002c470dcd3f53e8336e393f845fdb3cf
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569576"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class DontUseNewUseMake;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İşleç engel **yeni** RuntimeClass içinde. Sonuç olarak, kullanmanız gereken [olun işlevi](../windows/make-function.md) yerine.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[DontUseNewUseMake::operator new İşleci](../windows/dontusenewusemake-operator-new-operator.md)|İşleç aşırı **yeni** ve içinde RuntimeClass kullanılmasını engeller.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `DontUseNewUseMake`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [Make İşlevi](../windows/make-function.md)