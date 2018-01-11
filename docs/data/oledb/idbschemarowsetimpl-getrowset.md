---
title: IDBSchemaRowsetImpl::GetRowset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: GetRowset method
ms.assetid: 3ae28c22-e186-4a15-8591-b0192e784a6f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5164bcd56c61868649af6185c8b84ebf20098b18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="idbschemarowsetimplgetrowset"></a>IDBSchemaRowsetImpl::GetRowset
Bir şema satır kümesi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD (GetRowset)(  
   IUnknown *pUnkOuter,  
   REFGUID rguidSchema,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown **ppRowset   
);  
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