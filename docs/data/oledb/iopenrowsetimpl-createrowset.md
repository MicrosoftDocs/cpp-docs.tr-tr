---
title: "Iopenrowsetımpl::createrowset | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IOpenRowsetImpl.CreateRowset
- IOpenRowsetImpl::CreateRowset
- CreateRowset
dev_langs:
- C++
helpviewer_keywords:
- CreateRowset method
ms.assetid: 69041cf6-7a2f-4409-a26e-6e984c24986e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7aa478d86ba21dd482c3507352fb7f321df2ee0e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="iopenrowsetimplcreaterowset"></a>IOpenRowsetImpl::CreateRowset
Bir satır kümesi nesnesi oluşturur. Doğrudan kullanıcı tarafından adı değil. Bkz: [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) içinde *OLE DB Programcının Başvurusu.*  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      template template <class RowsetClass  
      >  
HRESULT CreateRowset(IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `RowsetClass`  
 Kullanıcının satır kümesi sınıfı temsil eden bir şablon sınıfı üyesi. Genellikle sihirbaz tarafından oluşturulan.  
  
 `pRowsetObj`  
 [out] Satır kümesi nesnesi için bir işaretçi. Genellikle bu parametre kullanılmaz, ancak bir COM nesnesi geçirmeden önce satır kümesi üzerinde daha fazla iş gerçekleştirmelisiniz değilse kullanılabilir. Yaşam süresi `pRowsetObj` tarafından bağlı `ppRowset`.  
  
 Diğer parametreler için bkz: [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) içinde *OLE DB Programcının Başvurusu.*  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IOpenRowsetImpl Sınıfı](../../data/oledb/iopenrowsetimpl-class.md)