---
title: Interfacelist yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
dev_langs:
- C++
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 318738e5f4ac623987b1002e5204739407adcdb9
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017769"
---
# <a name="interfacelist-structure"></a>InterfaceList Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <  
   typename T,  
   typename U  
>  
struct InterfaceList;  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Arabirim adı; özyinelemeli listedeki ilk arabirim.  
  
 *U*  
 Arabirim adı; özyinelemeli listesinde kalan arabirimler.  
  
## <a name="remarks"></a>Açıklamalar  
 Arabirimleri özyinelemeli listesini oluşturmak için kullanılır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel Typedefler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`FirstT`|Şablon parametresi için eş anlamlı *T*.|  
|`RestT`|Şablon parametresi için eş anlamlı *U*.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `InterfaceList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)