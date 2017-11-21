---
title: CRowsetImpl::setCommandText | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl.SetCommandText
- CRowsetImpl::SetCommandText
dev_langs: C++
helpviewer_keywords: SetCommandText method
ms.assetid: e016d7df-c1a0-4dee-b19b-c876680221fd
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a33af61311b9c202e5e0c68579ac4f21afd98f94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetimplsetcommandtext"></a>CRowsetImpl::SetCommandText
Doğrular ve depolar **DBID**iki dizeyi s ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT CRowsetBaseImpl::SetCommandText(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pTableID`  
 [in] Bir işaretçi **DBID** tablo kimliğine temsil eden  
  
 `pIndexID`  
 [in] Bir işaretçi **DBID** dizin kimliğini temsil eden  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 **SetCommentText** yöntemi çağrılır `CreateRowset`, statik şablonlaştırılmış yöntemi `IOpenRowsetImpl`.  
  
 Bu yöntemi çağrılarak çalışmasını Temsilciler [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) ve [Getcommandfromıd](../../data/oledb/crowsetimpl-getcommandfromid.md) upcasted işaretçi aracılığıyla.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowsetImpl sınıfı](../../data/oledb/crowsetimpl-class.md)