---
title: IDBSchemaRowsetImpl::createschemarowset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl::CreateSchemaRowset
- ATL::IDBSchemaRowsetImpl::CreateSchemaRowset
- CreateSchemaRowset
- IDBSchemaRowsetImpl.CreateSchemaRowset
- ATL.IDBSchemaRowsetImpl.CreateSchemaRowset
dev_langs:
- C++
helpviewer_keywords:
- CreateSchemaRowset method
ms.assetid: ad3e3e4d-45b9-461c-b7b8-3af6843631b1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e819805f9c73b2f8622b21b999b0db5f6771ecbe
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="idbschemarowsetimplcreateschemarowset"></a>IDBSchemaRowsetImpl::CreateSchemaRowset
Şablon parametresi tarafından belirtilen nesne için bir COM nesnesi oluşturucu işlevi uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
template template <class SchemaRowsetClass>  
HRESULT CreateSchemaRowset(IUnknown *pUnkOuter,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   SchemaRowsetClass*& pSchemaRowset);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pUnkOuter`  
 [in] Bir dış [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) , aksi takdirde toplanırken **NULL**.  
  
 `cRestrictions`  
 [in] Şema satır kümesi için uygulanan kısıtlamaları sayısı.  
  
 `rgRestrictions`  
 [in] Bir dizi `cRestrictions` **değişken**satır kümesi için uygulanacak s.  
  
 `riid`  
 [in] Arabirimine [QueryInterface](../../atl/queryinterface.md) için çıktıyı **IUnknown**.  
  
 `cPropertySets`  
 [in] Ayarlamak için özellik sayısını ayarlar.  
  
 `rgPropertySets`  
 [in] Bir dizi [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) yapıları ayarlanan özelliklerini belirtin.  
  
 `ppRowset`  
 [out] Giden **IUnknown** tarafından istenen `riid`. Bu **IUnknown** şema satır kümesi nesnesi üzerinde bir arabirimdir.  
  
 `pSchemaRowset`  
 [out] Şema satır kümesi sınıfının bir örneği için bir işaretçi. Genellikle, bu parametre kullanılmaz, ancak bir COM nesnesi gönderdikten önce şema satır kümesi üzerinde daha fazla iş gerçekleştirmelisiniz değilse kullanılabilir. Yaşam süresi `pSchemaRowset` tarafından bağlı `ppRowset`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev bir Genel oluşturucu şema satır kümeleri tüm türleri için uygular. Genellikle, kullanıcı bu işlev çağırmaz. Şema eşleme uygulaması tarafından çağrılır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDBSchemaRowsetImpl sınıfı](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl sınıfı üyeleri](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)   
 [Şema Satır Kümesi Sınıfları ve Typedef Sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)