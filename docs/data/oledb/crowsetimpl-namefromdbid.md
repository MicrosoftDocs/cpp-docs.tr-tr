---
title: "CRowsetImpl::namefromdbıd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowsetImpl.NameFromDBID
- CRowsetImpl::NameFromDBID
dev_langs:
- C++
helpviewer_keywords:
- NameFromDBID method
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 623eeca73ceaf29e0cecbe80b2a4a8b447adefdc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetimplnamefromdbid"></a>CRowsetImpl::NameFromDBID
Bir dizeden ayıklar bir **DBID** ve kendisine kopyalar `bstr` geçirildi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pDBID*  
 [in] Bir işaretçi **DBID** çıkarılacağı bir dize.  
  
 `bstr`  
 [in] A [CComBSTR](../../atl/reference/ccombstr-class.md) bir kopyasını yerleştirmek için başvuru **DBID** dize.  
  
 `bIndex`  
 [in] **true** bir dizin varsa **DBID**; **false** bir tablo, **DBID**.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`. Mı bağlı olarak **DBID** bir tablo veya bir dizin (belirtilmiştir `bIndex`), yöntem olur ya da dönüş **DB_E_NOINDEX** veya **DB_E_NOTABLE**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından çağrılır `CRowsetImpl` uygulamaları [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) ve [Getcommandfromıd](../../data/oledb/crowsetimpl-getcommandfromid.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowsetImpl Sınıfı](../../data/oledb/crowsetimpl-class.md)