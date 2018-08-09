---
title: Isbaseofstrict yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
dev_langs:
- C++
helpviewer_keywords:
- IsBaseOfStrict structure
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4690c15adac7be66ca916b1fc0f769e6c50190c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017909"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <  
   typename Base,  
   typename Derived  
>  
  
struct IsBaseOfStrict;  
template <  
   typename Base  
>  
struct IsBaseOfStrict<Base, Base>;  
```  
  
### <a name="parameters"></a>Parametreler  
 *temel*  
 Temel türü.  
  
 *Türetilmiş*  
 Türetilmiş bir tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Başka bir taban bir türü olup olmadığını sınar.  
  
 İlk şablon yield bir temel tür türetilmiş bir tür olup olmadığını test **true** veya **false**. İkinci şablon türetilmiş bir tür kendisinden, her zaman veren olmadığını sınar **false**.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IsBaseOfStrict::value Sabiti](../windows/isbaseofstrict-value-constant.md)|Başka bir taban bir türü olup olmadığını gösterir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IsBaseOfStrict`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** internal.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)