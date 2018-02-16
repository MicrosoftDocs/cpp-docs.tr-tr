---
title: IDBSchemaRowsetImpl::getschemas | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IDBSchemaRowsetImpl::GetSchemas
- GetSchemas
- IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- ATL.IDBSchemaRowsetImpl.GetSchemas
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- IDBSchemaRowsetImpl.GetSchemas
- IDBSchemaRowsetImpl::GetSchemas
dev_langs:
- C++
helpviewer_keywords:
- GetSchemas method
ms.assetid: fbe725a6-3acd-45f8-bcaf-10a6c1239cd2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 55ccad037b072e4d731462bbf89ff48b186bf068
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="idbschemarowsetimplgetschemas"></a>IDBSchemaRowsetImpl::GetSchemas
Şema satır kümeleri tarafından erişilebilen döndürür [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD (GetSchema s )(ULONG * pcSchemas,  
   GUID ** prgSchemas,  
   ULONG** prgRest);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pcSchemas*  
 [out] Bir işaretçi bir **ULONG** şemaları numarasıyla doldurulur.  
  
 *prgSchemas*  
 [out] Dolu GUID'ler dizisi için bir işaretçi bir işaretçi bir dizi şeması satır kümesi GUID'ler ile.  
  
 *prgRest*  
 [out] Bir dizi için bir işaretçi **ULONG**kısıtlama dizi ile doldurulması için s.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem sağlayıcı tarafından desteklenen tüm şema satır kümeleri bir dizi döndürür. Bkz: [IDBSchemaRowset::GetSchemas](https://msdn.microsoft.com/en-us/library/ms719605.aspx) Windows SDK.  
  
 , Bu işlev kullanıcının oturum sınıfında Eşleme Şeması sahip olmasını gerektirir. Şema eşleme bilgilerini kullanarak, bu ardından GUID'ler dizi harita şemalarda için ile yanıt verir. Bu sağlayıcı tarafından desteklenen şemaları temsil eder.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDBSchemaRowsetImpl sınıfı](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl sınıfı üyeleri](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)   
 [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx)   
 [Şema Satır Kümesi Sınıfları ve Typedef Sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)