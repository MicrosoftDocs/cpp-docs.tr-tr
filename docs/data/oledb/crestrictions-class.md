---
title: "CRestrictions sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
dev_langs: C++
helpviewer_keywords: CRestrictions class
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 88ba3c853bbd12c1512dbb8c70c0941718b1396f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="crestrictions-class"></a>CRestrictions Sınıfı
Şema satır kümeleri için kısıtlamalar belirtmenize olanak tanır genel bir sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <   
   class T,   
   short nRestrictions,   
   const GUID* pguid   
>  
class CRestrictions : public CSchemaRowset <   
   T,   
   nRestrictions   
>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Erişimci için kullanılan sınıf.  
  
 `nRestrictions`  
 Şema satır kümesi için kısıtlama sütun sayısı.  
  
 `pguid`  
 Bir işaretçi şeması için GUID.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Açık](../../data/oledb/crestrictions-open.md)|Kullanıcı tarafından sağlanan göre sınırlamalar bir sonuç döndürür.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)