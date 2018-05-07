---
title: CRowsetImpl::namefromdbıd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl.NameFromDBID
- CRowsetImpl::NameFromDBID
dev_langs:
- C++
helpviewer_keywords:
- NameFromDBID method
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 54ee345d4bf97c6f77398e62d1cb31614868a568
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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