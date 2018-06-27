---
title: Verifyınheritancehelper yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
dev_langs:
- C++
helpviewer_keywords:
- VerifyInheritanceHelper structure
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d758f4b44990d1f03ff698f0740c2aa8491367a5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889709"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename I,  
   typename Base  
>  
struct VerifyInheritanceHelper;  
template <  
   typename I  
>  
struct VerifyInheritanceHelper<I, Nil>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `I`  
 Bir tür.  
  
 `Base`  
 Başka bir tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Başka bir arabiriminden bir arabirim türetilmiş olup olmadığını sınar.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[VerifyInheritanceHelper::Verify Metodu](../windows/verifyinheritancehelper-verify-method.md)|Geçerli şablon parametrelerle belirtilen iki arabirim sınar ve bir arabirim diğer türetilmiş olup olmadığını belirler.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `VerifyInheritanceHelper`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)