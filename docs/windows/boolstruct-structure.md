---
title: BoolStruct yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
dev_langs:
- C++
helpviewer_keywords:
- BoolStruct structure
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14e3d81ca273bf96b4812f08a46904c9d521c5cf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650488"
---
# <a name="boolstruct-structure"></a>BoolStruct Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
struct BoolStruct;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **BoolStruct** yapısını tanımlar olup olmadığını bir `ComPtr` bir arabirimin nesne ömrü yönetimi. **BoolStruct** tarafından dahili olarak kullanılan [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) işleci.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[BoolStruct::Member Veri Üyesi](../windows/boolstruct-member-data-member.md)|Belirten bir [ComPtr](../windows/comptr-class.md) ya da bir arabirimin nesnenin ömrünü yönetmek değildir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `BoolStruct`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** internal.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtr::operator Microsoft::WRL::Details::BoolType İşleci](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)