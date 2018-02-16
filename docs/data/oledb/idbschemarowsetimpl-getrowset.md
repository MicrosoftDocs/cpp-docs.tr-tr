---
title: IDBSchemaRowsetImpl::GetRowset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IDBSchemaRowsetImpl::GetRowset
- ATL.IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl<SessionClass>::GetRowset
- IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl::GetRowset
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset
- GetRowset
dev_langs:
- C++
helpviewer_keywords:
- GetRowset method
ms.assetid: 3ae28c22-e186-4a15-8591-b0192e784a6f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fb3e1460b4eee2de030397e05d527c219acb2bb9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="idbschemarowsetimplgetrowset"></a>IDBSchemaRowsetImpl::GetRowset
Bir şema satır kümesi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD (GetRowset)(IUnknown *pUnkOuter,  
   REFGUID rguidSchema,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown **ppRowset);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pUnkOuter`  
 [in] Bir dış **IUnknown** toplayarak; Aksi takdirde, **NULL**.  
  
 `rguidSchema`  
 [in] İstenen şema satır kümesi GUID'si başvuru (örneğin, `DBSCHEMA_TABLES`).  
  
 `cRestrictions`  
 [in] Satır kümesine uygulanacak kısıtlamaları sayısı.  
  
 `rgRestrictions`  
 [in] Bir dizi `cRestrictions` **değişken**kısıtlamaları temsil s.  
  
 `riid`  
 [in] Yeni oluşturulan şema satır kümesi istemek için IID.  
  
 `cPropertySets`  
 [in] Ayarlamak için özellik sayısını ayarlar.  
  
 `rgPropertySets`  
 [Giriş/Çıkış] Bir dizi [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) yapılar yeni oluşturulan şema satır kümesi üzerinde ayarlayın.  
  
 `ppRowset`  
 [out] Yeni oluşturulan şema satır kümesi istenen arabirimi için bir işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem kullanıcının oturum sınıfında Eşleme Şeması sahip olmasını gerektirir. Şema eşleme bilgilerini kullanarak `GetRowset` verilen satır kümesi nesnesi oluşturur `rguidSchema` parametrenin GUID'ler eşleme girdilerini birine eşit. Bkz: [SCHEMA_ENTRY](../../data/oledb/schema-entry.md) eşleme girişi açıklaması.  
  
 Bkz: [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx) Windows SDK.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDBSchemaRowsetImpl sınıfı](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl sınıfı üyeleri](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::getschemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)   
 [Şema Satır Kümesi Sınıfları ve Typedef Sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)