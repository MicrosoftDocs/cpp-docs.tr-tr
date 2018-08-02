---
title: ArgTraitsHelper yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
dev_langs:
- C++
helpviewer_keywords:
- ArgTraitsHelper structure
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1bb8dfeff0e1f3e659e0d3c6514904df39286c45
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466643"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename TDelegateInterface>  
struct ArgTraitsHelper;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *TDelegateInterface*  
 Bir temsilci arabirimi.  
  
## <a name="remarks"></a>Açıklamalar  
 Yardımcı olur, temsilci bağımsız değişkenleri genel özelliklerini tanımlayın.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel Typedefler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`methodType`|İçin bir eşanlamlı `decltype(&TDelegateInterface::Invoke)`.|  
|`Traits`|İçin bir eşanlamlı `ArgTraits<methodType>`.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ArgTraitsHelper::args Sabiti](../windows/argtraitshelper-args-constant.md)|Yardımcı [ArgTraits::args](../windows/argtraits-args-constant.md) parametreleri sayısını takip edin `Invoke` yöntemi temsilci arabirimi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ArgTraitsHelper`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)