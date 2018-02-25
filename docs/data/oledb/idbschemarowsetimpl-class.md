---
title: "IDBSchemaRowsetImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBSchemaRowsetImpl class
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2895aeebd49e38b157ab55912fcc4b7c52ba953e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl Sınıfı
Şema satır kümeleri uygulamasını sağlar.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
#### <a name="parameters"></a>Parametreler  
 `SessionClass`  
 Sınıfı, `IDBSchemaRowsetImpl` devralınır. Genellikle, bu sınıf, kullanıcının oturum sınıfı olacaktır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)|Bir şema satır kümesi karşı kısıtlamaların geçerliliğini denetler.|  
|[CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)|Şablon parametresi tarafından belirtilen nesne için bir COM nesnesi oluşturucu işlevi uygular.|  
|[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)|Belirli şema satır kümesinde destek hangi kısıtlamaları belirtir.|  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)|Bir şema satır kümesi döndürür.|  
|[GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)|Şema satır kümeleri tarafından erişilebilen döndürür [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf uygulayan [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) arabirimi ve şablonlaştırılmış creator işlevi [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md).  
  
 OLE DB sağlayıcı verilerle ilgili veriler döndürmek için şema satır kümeleri kullanır. Bu tür veriler genellikle "meta veriler." olarak adlandırılır Varsayılan olarak, her zaman bir sağlayıcı desteklemelidir `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**, ve **DBSCHEMA_PROVIDER_TYPES**açıklandığı gibi [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu*. Şema satır kümeleri şema eşlemesinde atanır. Şema eşleme girdileri hakkında daha fazla bilgi için bkz: [SCHEMA_ENTRY](../../data/oledb/schema-entry.md).  
  
 OLE DB Sağlayıcı Sihirbazı, ATL nesnesi Sihirbazı'nda otomatik olarak projenizdeki şema satır kümeleri için kod oluşturur. (Varsayılan olarak, daha önce bahsedilen zorunlu şema satır kümeleri Sihirbazı'nı destekler.) ATL nesnesi Sihirbazı'nı kullanarak bir tüketici oluşturduğunuzda, sihirbaz şema satır kümeleri doğru veri sağlayıcısı için bağlamak için kullanır. Doğru meta verilerini sağlamak için şema satır kümeleri kullanılmaz, sihirbaz doğru veri bağlanamaz.  
  
 Sağlayıcınızdaki şema satır kümelerini destekleme hakkında daha fazla bilgi için bkz: [şema satır kümelerini destekleme](../../data/oledb/supporting-schema-rowsets.md).  
  
 Şema satır kümeleri hakkında daha fazla bilgi için bkz: [şema satır kümeleri](https://msdn.microsoft.com/en-us/library/ms712921.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDBSchemaRowsetImpl sınıfı üyeleri](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Şema Satır Kümelerini Destekleme](../../data/oledb/supporting-schema-rowsets.md)