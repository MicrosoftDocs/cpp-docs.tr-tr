---
title: Irowsetcreatorımpl::setsite | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetCreatorImpl.SetSite
- IRowsetCreatorImpl<T>::SetSite
- IRowsetCreatorImpl::SetSite
- SetSite
- ATL.IRowsetCreatorImpl.SetSite
- ATL::IRowsetCreatorImpl<T>::SetSite
- ATL::IRowsetCreatorImpl::SetSite
- ATL.IRowsetCreatorImpl<T>.SetSite
dev_langs:
- C++
helpviewer_keywords:
- SetSite method
ms.assetid: e92e63d5-93e4-4ee0-9ef7-bb6583cc8091
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: af2883b261b754cee04e2c5090d1ef9b9887c04f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101390"
---
# <a name="irowsetcreatorimplsetsite"></a>IRowsetCreatorImpl::SetSite
Satır kümesi nesnesi içeren siteyi ayarlar. Daha fazla bilgi için bkz: [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD(SetSite )(IUnknown* pCreator);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pCreator`  
 [in] İşaretçi **IUnknown** satır kümesi nesnesi yönetme site arabirimi işaretçisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrıca, `IRowsetCreatorImpl::SetSite` OLE DB etkinleştirir **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS** özellikleri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetCreatorImpl Sınıfı](../../data/oledb/irowsetcreatorimpl-class.md)