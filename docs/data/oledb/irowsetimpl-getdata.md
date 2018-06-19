---
title: Irowsetımpl::GetData | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetImpl.GetData
- ATL::IRowsetImpl::GetData
- IRowsetImpl::GetData
- IRowsetImpl.GetData
dev_langs:
- C++
helpviewer_keywords:
- GetData method [OLE DB]
ms.assetid: cb15f1cc-bd25-4b74-93c3-db71aa93829c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3e2a20e8f1948078aec6994516e05f83e95cdcc1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102611"
---
# <a name="irowsetimplgetdata"></a>IRowsetImpl::GetData
Satır satır kümesinin kopyadan verileri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD(GetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pDstData);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: ['yı](https://msdn.microsoft.com/en-us/library/ms716988.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 Bazı parametreler karşılık *OLE DB Programcının Başvurusu* açıklanan farklı adlar parametrelerinin **'yı**:  
  
|OLE DB Şablon parametreleri|*OLE DB Programcının Başvurusu* parametreleri|  
|--------------------------------|------------------------------------------------|  
|*pDstData*|`pData`|  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrıca veri dönüştürme OLE DB veri dönüştürme DLL kullanarak işler.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetImpl Sınıfı](../../data/oledb/irowsetimpl-class.md)