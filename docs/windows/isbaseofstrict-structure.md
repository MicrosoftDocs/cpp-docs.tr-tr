---
title: "Isbaseofstrict yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::IsBaseOfStrict
dev_langs: C++
helpviewer_keywords: IsBaseOfStrict structure
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fd3d232094ed9a56db9cd0e14776ca0ec9eca8c1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
  
#### <a name="parameters"></a>Parametreler  
 `Base`  
 Temel türü.  
  
 `Derived`  
 Türetilen tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Başka bir taban bir türü olup olmadığını sınar.  
  
 İlk şablon verim bir taban türü türeyen bir tür olup olmadığını sınar **true** veya **false**. İkinci şablon türeyen bir tür kendisinden, her zaman veren olmadığını test eder **false**.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Isbaseofstrict::Value sabiti](../windows/isbaseofstrict-value-constant.md)|Bir tür başka tabanı olup olmadığını gösterir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IsBaseOfStrict`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** internal.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)