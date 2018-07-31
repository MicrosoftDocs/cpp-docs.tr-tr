---
title: IDBSchemaRowsetImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl
- CheckRestrictions
- IDBSchemaRowsetImpl::CheckRestrictions
- IDBSchemaRowsetImpl.CheckRestrictions
- IDBSchemaRowsetImpl::CreateSchemaRowset
- ATL::IDBSchemaRowsetImpl::CreateSchemaRowset
- CreateSchemaRowset
- IDBSchemaRowsetImpl.CreateSchemaRowset
- ATL.IDBSchemaRowsetImpl.CreateSchemaRowset
- IDBSchemaRowsetImpl::SetRestrictions
- SetRestrictions
- IDBSchemaRowsetImpl.SetRestrictions
- ATL::IDBSchemaRowsetImpl::GetRowset
- ATL.IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl<SessionClass>::GetRowset
- IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl::GetRowset
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset
- GetRowset
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
- IDBSchemaRowsetImpl class
- CheckRestrictions method
- CreateSchemaRowset method
- SetRestrictions method
- GetRowset method
- GetSchemas method
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eaea6922f7755295535c0e81d6b9023a10c1317a
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339620"
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl Sınıfı
Şema satır kümeleri uygulamasını sağlar.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
### <a name="parameters"></a>Parametreler  
 *SessionClass*  
 Sınıfı, `IDBSchemaRowsetImpl` devralınır. Genellikle, bu sınıf, kullanıcının oturum sınıfının olacaktır. 

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CheckRestrictions](#checkrestrictions)|Şema satır kümesi karşı kısıtlamaları geçerliliğini denetler.|  
|[CreateSchemaRowset](#createschemarowset)|Şablon parametresi tarafından belirtilen nesne için bir COM nesnesi oluşturan işlevi uygular.|  
|[SetRestrictions](#setrestrictions)|Belirli bir şema satır kümesinde desteklediğiniz hangi kısıtlamaları belirtir.|  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[GetRowset](#getrowset)|Şema satır kümesi döndürür.|  
|[GetSchemas](#getschemas)|Şema satır kümeleri listesi tarafından erişilebilen döndürür [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfın uyguladığı [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) arabirimi ve şablonlaştırılmış oluşturucu işlevi [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md).  
  
 OLE DB sağlayıcı veriler hakkındaki veriler döndürmek için şema satır kümelerini kullanır. Bu tür veriler genellikle "meta veri" olarak adlandırılır Varsayılan olarak, her zaman bir sağlayıcı desteklemelidir `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`, ve `DBSCHEMA_PROVIDER_TYPES`anlatılan şekilde [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu*. Şema satır kümeleri bir şema eşleminde atanır. Şema eşleme girişleri hakkında daha fazla bilgi için bkz. [SCHEMA_ENTRY](../../data/oledb/schema-entry.md).  
  
 OLE DB sağlayıcısı Sihirbazı, ATL nesnesi Sihirbazı'nda, otomatik olarak projenize bir şema satır kümeleri için kod oluşturur. (Varsayılan olarak, sihirbaz daha önce bahsedilen zorunlu şema satır kümelerini destekler.) ATL nesnesi Sihirbazı'nı kullanarak bir tüketici oluşturduğunuzda, sihirbaz şema satır kümeleri için doğru verileri bir sağlayıcısına bağlamak için kullanır. Doğru meta verilerini sağlamak için şema satır kümeleri kullanılmaz, sihirbaz doğru veri bağlanamaz.  
  
 Sağlayıcınızdaki şema satır kümelerini destekleme hakkında daha fazla bilgi için bkz: [şema satır kümelerini destekleme](../../data/oledb/supporting-schema-rowsets.md).  
  
 Şema satır kümeleri hakkında daha fazla bilgi için bkz: [şema satır kümeleri](https://msdn.microsoft.com/library/ms712921.aspx) içinde *OLE DB Programcının Başvurusu*.  

## <a name="checkrestrictions"></a> IDBSchemaRowsetImpl::CheckRestrictions
Şema satır kümesi karşı kısıtlamaları geçerliliğini denetler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT CheckRestrictions(REFGUID rguidSchema,  
   ULONG cRestrictions,  const VARIANT rgRestrictions[]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *rguidSchema*  
 [in] İstenen şeması satır kümesi GUID'si başvuru (örneğin, `DBSCHEMA_TABLES`).  
  
 *cRestrictions*  
 [in] Tüketici şeması satır kümesi için geçirilen kısıtlama sayısı.  
  
 *rgRestrictions*  
 [in] Bir dizi uzunluğu *cRestrictions* kısıtlama değerleri ayarlamak için. Daha fazla bilgi için açıklamasına bakın *rgRestrictions* parametresinde [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CheckRestrictions` kısıtlamaları şeması satır kümesi karşı geçerliliğini denetlemek için. İlgili bir kısıtlama denetler `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`, ve `DBSCHEMA_PROVIDER_TYPES` şema satır kümeleri. Bir tüketici 's belirlemek için çağrısından çağrısı `IDBSchemaRowset::GetRowset` doğrudur. Şema satır kümeleri üstündeki listelenenler dışında desteklemek istiyorsanız, bu görevi gerçekleştirmek için kendi işlev oluşturmanız gerekir.  
  
 `CheckRestrictions` Tüketici aradığı belirler [GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) doğru kısıtlama ve sağlayıcının desteklediği doğru kısıtlama türü (örneğin, bir dizeyi VT_BSTR). Kısıtlama sayısı doğru desteklenip desteklenmediğini belirler. Varsayılan olarak, `CheckRestrictions` sağlayıcısı aracılığıyla ister [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) çağrısı, belirli bir satır kümesinde destekliyorsa, hangi kısıtlamaları. Ardından bir tüketici kısıtlamaları bu sağlayıcı tarafından desteklenen karşı karşılaştırır ve başarılı veya başarısız olur.  
  
 Şema satır kümeleri hakkında daha fazla bilgi için bkz. [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK.  

## <a name="createschemarowset"></a> IDBSchemaRowsetImpl::createschemarowset
Şablon parametresi tarafından belirtilen nesne için bir COM nesnesi oluşturan işlevi uygular.  
  
### <a name="syntax"></a>Sözdizimi  
  
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
 *pUnkOuter*  
 [in] Bir dış [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) toplanırken, aksi takdirde NULL.  
  
 *cRestrictions*  
 [in] Şema satır kümesi için uygulanan kısıtlamalara sayısı.  
  
 *rgRestrictions*  
 [in] Bir dizi `cRestrictions` **değişken**s satır kümesi için uygulanacak.  
  
 *riid*  
 [in] Arabirimi [QueryInterface](../../atl/queryinterface.md) için çıktıyı `IUnknown`.  
  
 *cPropertySets*  
 [in] Ayarlanacak özellik sayısını ayarlar.  
  
 *rgPropertySets*  
 [in] Bir dizi [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) yapıları ayarlanan özellikleri belirtin.  
  
 *ppRowset*  
 [out] Giden `IUnknown` tarafından istenen *riid*. Bu `IUnknown` şeması satır kümesi nesnesi bir arabirimdir.  
  
 *pSchemaRowset*  
 [out] Şema satır kümesi sınıfının bir örneği için bir işaretçi. Genellikle, bu parametre kullanılmaz, ancak, daha fazla iş şeması satır kümesi üzerinde bir COM nesnesi için teslim etme önce gerçekleştirmeniz gerekirse kullanılabilir. Ömrünü *pSchemaRowset* bağlı olan *ppRowset*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, şema satır kümeleri tüm türleri için genel bir oluşturucu uygular. Genellikle, kullanıcı bu işlev çağırmaz. Şema eşleme uygulaması tarafından çağırılır. 

## <a name="setrestrictions"></a> IDBSchemaRowsetImpl::SetRestrictions
Belirli bir şema satır kümesinde desteklediğiniz hangi kısıtlamaları belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
void SetRestrictions(ULONG cRestrictions,  
   GUID* /* rguidSchema */,  
   ULONG* rgRestrictions);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *cRestrictions*  
 [in] Bazı kısıtlamalar *rgRestrictions* dizisi ve GUID'leri sayısını *rguidSchema* dizisi.  
  
 *rguidSchema*  
 [in] Şema satır kümeleri hangi kısıtlamaları getirmek için GUID'lerini dizisi. Her dizi öğesi bir şeması satır kümesi GUID'si içerir (örneğin, `DBSCHEMA_TABLES`).  
  
 *rgRestrictions*  
 [in] Bir dizi uzunluğu *cRestrictions* kısıtlama değerleri ayarlamak için. Her öğe GUID ile tanımlanan şema satır kümesi kısıtlamalarına karşılık gelir. Şema satır kümesi sağlayıcı tarafından desteklenmiyorsa, öğenin sıfır olarak ayarlanır. Aksi takdirde, **ULONG** değeri içeren bu şeması satır kümesi üzerinde desteklenen kısıtlamaları temsil eden bir bit maskesi. Üzerinde kısıtlamaları karşılık gelen bir belirli şeması satır kümesi için daha fazla bilgi için tablonun şeması satır kümesi GUID'leri başvurun içinde [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu* Windows içinde SDK.  
  
### <a name="remarks"></a>Açıklamalar  
 `IDBSchemaRowset` Nesne çağrıları `SetRestrictions` hangi kısıtlamaları belirlemek için üzerinde bir belirli şeması satır kümesi desteği (çağrılır [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) upcasted bir işaretçi aracılığıyla). Kısıtlamalar yalnızca eşleşen satırları getirilecek tüketiciler izin ver (örneğin, tüm sütunları tabloda "MyTable" Bul). Kısıtlamaları isteğe bağlıdır ve durumda hiçbiri desteklenir (varsayılan), tüm veriler her zaman döndürülür.  
  
 Bu yöntem varsayılan uygulaması ayarlar *rgRestrictions* 0 öğeleri dizisi. Varsayılan oturum sınıfınızda varsayılan dışındaki kısıtlamalarını ayarlamak için geçersiz kılın.  
  
 Şema satır kümesi desteği uygulama hakkında daha fazla bilgi için bkz: [şema satır kümelerini destekleme](../../data/oledb/supporting-schema-rowsets.md).  
  
 Şema satır kümeleri destekleyen bir sağlayıcı örneği için bkz: [UpdatePV](../../visual-cpp-samples.md) örnek.  
  
 Şema satır kümeleri hakkında daha fazla bilgi için bkz. [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK. 
  
## <a name="getrowset"></a> IDBSchemaRowsetImpl::GetRowset
Şema satır kümesi döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
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
 *pUnkOuter*  
 [in] Bir dış `IUnknown` toplama; Aksi takdirde NULL olduğunda.  
  
 *rguidSchema*  
 [in] İstenen şeması satır kümesi GUID'si başvuru (örneğin, `DBSCHEMA_TABLES`).  
  
 *cRestrictions*  
 [in] Satır kümesi için uygulanacak olan kısıtlamaları sayısı.  
  
 *rgRestrictions*  
 [in] Bir dizi `cRestrictions` **değişken**kısıtlamaları temsil eden s.  
  
 *riid*  
 [in] Yeni oluşturulan şeması satır kümesi istemek için bir IID.  
  
 *cPropertySets*  
 [in] Ayarlanacak özellik sayısını ayarlar.  
  
 *rgPropertySets*  
 [daraltma/genişletme] Bir dizi [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) yapılar yeni oluşturulan şeması satır kümesi üzerinde ayarlamak için.  
  
 *ppRowset*  
 [out] Yeni oluşturulan şeması satır kümesi üzerinde istenen arabirim işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem kullanıcının oturumu sınıfı, eşleme bir şemaya sahip olmasını gerektirir. Şema eşleme bilgilerini kullanarak `GetRowset` belirtilen satır kümesi nesnesi oluşturur *rguidSchema* parametre eşleme girişleri GUID'leri birine eşit. Bkz: [SCHEMA_ENTRY](../../data/oledb/schema-entry.md) eşleme girişi açıklaması.  
  
 Bkz: [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/library/ms722634.aspx) Windows SDK içinde.  

## <a name="getschemas"></a> IDBSchemaRowsetImpl::getschemas
Şema satır kümeleri listesi tarafından erişilebilen döndürür [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD (GetSchema s )(ULONG * pcSchemas,  
   GUID ** prgSchemas,  
   ULONG** prgRest);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pcSchemas*  
 [out] Bir işaretçi bir **ULONG** şemaları sayısı ile doldurulur.  
  
 *prgSchemas*  
 [out] Şeması satır kümesi GUID'leri bir dizi işaretçisi ile doldurulan bir dizi GUID'leri işaretçisi.  
  
 *prgRest*  
 [out] Bir dizi işaretçi **ULONG**kısıtlama dizi ile doldurulacak olan s.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, sağlayıcı tarafından desteklenen tüm şema satır kümeleri bir dizi döndürür. Bkz: [IDBSchemaRowset::GetSchemas](https://msdn.microsoft.com/library/ms719605.aspx) Windows SDK içinde.  
  
 Bu işlev uygulaması kullanıcının oturumu sınıfı, eşleme bir şemaya sahip olmasını gerektirir. Şema eşleme bilgileri kullanarak, bunu ardından haritadaki şemaları için GUID'leri dizisi ile yanıt verir. Bu sağlayıcı tarafından desteklenen şema temsil eder.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [IDBSchemaRowsetImpl sınıfı üyeleri](http://msdn.microsoft.com/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Şema satır kümelerini destekleme](../../data/oledb/supporting-schema-rowsets.md)    
 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)    
 [UpdatePV](../../visual-cpp-samples.md)