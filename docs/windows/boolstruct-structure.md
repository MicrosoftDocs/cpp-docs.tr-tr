---
title: "BoolStruct yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::BoolStruct
dev_langs: C++
helpviewer_keywords: BoolStruct structure
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0fdbaf9af73940ab342e915edb475f9f35027eaa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="boolstruct-structure"></a>BoolStruct Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct BoolStruct;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 BoolStruct yapısı bir ComPtr bir arabirim nesne ömrü yönetme olup olmadığını tanımlar. BoolStruct tarafından dahili olarak kullanılan [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) işleci.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[BoolStruct::Member veri üyesi](../windows/boolstruct-member-data-member.md)|Belirleyen bir [ComPtr](../windows/comptr-class.md) , veya bir arabirim nesne ömrü yönetme değil,.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `BoolStruct`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** internal.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtr::operator Microsoft::WRL::Details::BoolType işleci](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)