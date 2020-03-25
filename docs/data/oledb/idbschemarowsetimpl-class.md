---
title: IDBSchemaRowsetImpl Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- IDBSchemaRowsetImpl class
- CheckRestrictions method
- CreateSchemaRowset method
- SetRestrictions method
- GetRowset method
- GetSchemas method
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
ms.openlocfilehash: f6af0f61ca425a2a1fba98b4041a92163e2f1d4e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210632"
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl Sınıfı

Şema satır kümeleri için uygulama sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class SessionClass>
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset
```

### <a name="parameters"></a>Parametreler

*SessionClass*<br/>
`IDBSchemaRowsetImpl` Devralındığı sınıf. Genellikle, bu sınıf kullanıcının oturum sınıfı olacaktır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CheckRestrictions](#checkrestrictions)|Bir şema satır kümesi için kısıtlamaların geçerliliğini denetler.|
|[CreateSchemaRowset](#createschemarowset)|Şablon parametresi tarafından belirtilen nesne için bir COM nesnesi Oluşturucu işlevi uygular.|
|[SetRestrictions](#setrestrictions)|Belirli bir şema satır kümesinde hangi kısıtlamaları destekliyoruz belirtir.|

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[GetRowset](#getrowset)|Bir şema satır kümesi döndürür.|
|[GetSchemas](#getschemas)|[IDBSchemaRowsetImpl:: GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)tarafından erişilebilen şema satır kümelerinin bir listesini döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) arabirimini ve şablonıtilen Oluşturucu Işlevi [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)uygular.

OLE DB, bir sağlayıcıdaki verilerle ilgili verileri döndürmek için şema satır kümelerini kullanır. Bu tür veriler genellikle "metadata" olarak adlandırılır. Varsayılan olarak, bir sağlayıcının `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`ve `DBSCHEMA_PROVIDER_TYPES`her zaman desteklemesi gerekir, *OLE DB Programcı başvurusunda* [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) bölümünde açıklandığı gibi. Şema satır kümeleri bir şema eşlemesinde atanır. Şema eşleme girişleri hakkında daha fazla bilgi için bkz. [SCHEMA_ENTRY](../../data/oledb/schema-entry.md).

OLE DB sağlayıcı Sihirbazı, ATL nesne sihirbazında, projenizdeki şema satır kümeleri için otomatik olarak kod oluşturur. (Varsayılan olarak, sihirbaz daha önce bahsedilen zorunlu şema satır kümelerini destekler.) ATL nesne Sihirbazı 'nı kullanarak bir tüketici oluşturduğunuzda, sihirbaz doğru verileri bir sağlayıcıya bağlamak için şema satır kümelerini kullanır. Doğru meta verileri sağlamak için şema satır kümelerinizi uygulamadıysanız, sihirbaz doğru verileri bağmaz.

Sağlayıcınızdaki şema satır kümelerini destekleme hakkında daha fazla bilgi için bkz. [şema satır kümelerini destekleme](../../data/oledb/supporting-schema-rowsets.md).

Şema satır kümeleri hakkında daha fazla bilgi için, *OLE DB Programcı başvurusunda* [şema satır kümeleri](/previous-versions/windows/desktop/ms712921(v=vs.85)) bölümüne bakın.

## <a name="idbschemarowsetimplcheckrestrictions"></a><a name="checkrestrictions"></a>IDBSchemaRowsetImpl:: CheckRestrictions

Bir şema satır kümesi için kısıtlamaların geçerliliğini denetler.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CheckRestrictions(REFGUID rguidSchema,
   ULONG cRestrictions,  const VARIANT rgRestrictions[]);
```

#### <a name="parameters"></a>Parametreler

*rguidSchema*<br/>
'ndaki İstenen şema satır kümesi GUID 'sine (örneğin, `DBSCHEMA_TABLES`) başvuru.

*cRestrictions*<br/>
'ndaki Şema satır kümesi için tüketicinin geçirildiği kısıtlamaların sayısı.

*rgRestrictions*<br/>
'ndaki Ayarlanacak kısıtlama *değerlerinin bir dizi uzunluğu kümesi* . Daha fazla bilgi için [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)Içindeki *rgRestrictions* parametresinin açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Şema satır kümesine karşı kısıtlamaların geçerliliğini denetlemek için `CheckRestrictions` kullanın. `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`ve `DBSCHEMA_PROVIDER_TYPES` şema satır kümelerine yönelik kısıtlamaları denetler. Bir tüketicinin `IDBSchemaRowset::GetRowset` çağrısının doğru olup olmadığını anlamak için bunu çağırın. Yukarıda listelenenlerin dışında şema satır kümelerini desteklemek istiyorsanız, bu görevi gerçekleştirmek için kendi işlevinizi oluşturmanız gerekir.

`CheckRestrictions`, tüketicinin [GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) 'in, sağlayıcının desteklediği doğru kısıtlamaya ve doğru kısıtlama türüne (örneğin, bir dize için bir VT_BSTR) çağrı oluşturup atamayacağını belirler. Ayrıca, doğru sayıda kısıtlamaların desteklenip desteklenmediğini da belirler. `CheckRestrictions`, varsayılan olarak sağlayıcıdan, belirli bir satır kümesinde desteklediği kısıtlamaları, [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) çağrısıyla sorar. Daha sonra, tüketici kısıtlamalarını sağlayıcı tarafından desteklenenlere göre karşılaştırır ve başarılı ya da başarısız olur.

Şema satır kümeleri hakkında daha fazla bilgi için, Windows SDK *OLE DB Programcı başvurusunda* [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) bölümüne bakın.

## <a name="idbschemarowsetimplcreateschemarowset"></a><a name="createschemarowset"></a>IDBSchemaRowsetImpl:: CreateSchemaRowset

Şablon parametresi tarafından belirtilen nesne için bir COM nesnesi Oluşturucu işlevi uygular.

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

*pUnkOuter*<br/>
'ndaki Toplama sırasında bir dış [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) , aksı takdirde null.

*cRestrictions*<br/>
'ndaki Şema satır kümesine uygulanan kısıtlamaların sayısı.

*rgRestrictions*<br/>
'ndaki Satır kümesine uygulanacak `cRestrictions`**VARIANT**dizisi.

*riıd*<br/>
'ndaki Çıktı `IUnknown`için [QueryInterface](../../atl/queryinterface.md) arabirimi.

*cPropertySets 'ler*<br/>
'ndaki Ayarlanacak özellik kümesi sayısı.

*rgPropertySets*<br/>
'ndaki Ayarlanan özellikleri belirten bir [dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapıları dizisi.

*ppRowset*<br/>
dışı *Riıd*tarafından istenen giden `IUnknown`. Bu `IUnknown`, şema satır kümesi nesnesindeki bir arabirimdir.

*pSchemaRowset*<br/>
dışı Şema satır kümesi sınıfının bir örneğine yönelik işaretçi. Genellikle, bu parametre kullanılmaz, ancak bir COM nesnesine teslim etmeden önce şema satır kümesinde daha fazla iş gerçekleştirmeniz gerekiyorsa kullanılabilir. *PSchemaRowset* kullanım ömrü *ppRowset*ile bağlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm şema satır kümesi türleri için genel Oluşturucu uygular. Genellikle, Kullanıcı bu işlevi çağırmaz. Şema eşlemesinin uygulamasıyla çağrılır.

## <a name="idbschemarowsetimplsetrestrictions"></a><a name="setrestrictions"></a>IDBSchemaRowsetImpl:: SetRestrictions

Belirli bir şema satır kümesinde hangi kısıtlamaları destekliyoruz belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetRestrictions(ULONG cRestrictions,
   GUID* /* rguidSchema */,
   ULONG* rgRestrictions);
```

#### <a name="parameters"></a>Parametreler

*cRestrictions*<br/>
'ndaki *RgRestrictions* dizisindeki kısıtlamaların sayısı ve *rguidSchema* dizisindeki GUID sayısı.

*rguidSchema*<br/>
'ndaki Kısıtlamaların getirileceği şema satır kümelerinin GUID 'Leri dizisi. Her dizi öğesi bir şema satır kümesinin GUID 'INI içerir (örneğin, `DBSCHEMA_TABLES`).

*rgRestrictions*<br/>
'ndaki Ayarlanacak kısıtlama *değerlerinin bir dizi uzunluğu kümesi* . Her öğe, GUID tarafından tanımlanan şema satır kümesi kısıtlamalarına karşılık gelir. Bir şema satır kümesi sağlayıcı tarafından desteklenmiyorsa, öğe sıfır olarak ayarlanır. Aksi takdirde, **ulong** değeri, bu şema satır kümesinde desteklenen kısıtlamaları temsil eden bir bit maskesi içerir. Belirli bir şema satır kümesine karşılık gelen kısıtlamalar hakkında daha fazla bilgi için, Windows SDK *Programcı başvurusu OLE DB* Içindeki [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) Içindeki şema satır kümesi GUID 'lerinin tablosuna bakın.

### <a name="remarks"></a>Açıklamalar

`IDBSchemaRowset` nesnesi, belirli bir şema satır kümesinde hangi kısıtlamaların destekleyeceğini belirleyen `SetRestrictions` çağırır (bilinen bir işaretçi aracılığıyla [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) tarafından çağrılır). Kısıtlamalar tüketicilere yalnızca eşleşen satırları getirme izni verir (örneğin, "MyTable" tablosundaki tüm sütunları bulur). Kısıtlamalar isteğe bağlıdır ve hiçbirinin desteklenme durumunda (varsayılan), tüm veriler her zaman döndürülür.

Bu yöntemin varsayılan uygulamasında *rgRestrictions* dizi öğeleri 0 olarak ayarlanır. Varsayılan değer dışındaki kısıtlamaları ayarlamak için oturum sınıfınıza varsayılan ayarı geçersiz kılın.

Şema satır kümesi desteğini uygulama hakkında daha fazla bilgi için bkz. [şema satır kümelerini destekleme](../../data/oledb/supporting-schema-rowsets.md).

Şema satır kümelerini destekleyen bir sağlayıcıya örnek için bkz. [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) örneği.

Şema satır kümeleri hakkında daha fazla bilgi için, Windows SDK *OLE DB Programcı başvurusunda* [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) bölümüne bakın.

## <a name="idbschemarowsetimplgetrowset"></a><a name="getrowset"></a>IDBSchemaRowsetImpl:: GetRowset

Bir şema satır kümesi döndürür.

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

*pUnkOuter*<br/>
'ndaki Toplama sırasında bir dış `IUnknown`; Aksi takdirde NULL.

*rguidSchema*<br/>
'ndaki İstenen şema satır kümesi GUID 'sine (örneğin, `DBSCHEMA_TABLES`) başvuru.

*cRestrictions*<br/>
'ndaki Satır kümesine uygulanacak kısıtlamaların sayısı.

*rgRestrictions*<br/>
'ndaki Kısıtlamaları temsil eden `cRestrictions`**VARIANT**öğeleri dizisi.

*riıd*<br/>
'ndaki Yeni oluşturulan şema satır kümesinin istemesi için IID.

*cPropertySets 'ler*<br/>
'ndaki Ayarlanacak özellik kümesi sayısı.

*rgPropertySets*<br/>
[ın/out] Yeni oluşturulan şema satır kümesinde ayarlanacak bir [dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapıları dizisi.

*ppRowset*<br/>
dışı Yeni oluşturulan şema satır kümesinde istenen arabirime yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanıcının oturum sınıfında bir şema eşlemesine sahip olmasını gerektirir. Şema eşleme bilgilerini kullanarak, *rguidSchema* parametresi eşleme girdilerinin GUID 'lerinin birine eşitse `GetRowset` belirli bir satır kümesi nesnesi oluşturur. Harita girişinin açıklaması için bkz. [SCHEMA_ENTRY](../../data/oledb/schema-entry.md) .

Windows SDK [IDBSchemaRowset:: GetRowset](/previous-versions/windows/desktop/ms722634(v=vs.85)) öğesine bakın.

## <a name="idbschemarowsetimplgetschemas"></a><a name="getschemas"></a>IDBSchemaRowsetImpl:: GetSchemas

[IDBSchemaRowsetImpl:: GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)tarafından erişilebilen şema satır kümelerinin bir listesini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetSchema s )(ULONG * pcSchemas,
   GUID ** prgSchemas,
   ULONG** prgRest);
```

#### <a name="parameters"></a>Parametreler

*pcSchemas*<br/>
dışı Şemaların sayısıyla doldurulmuş bir **ulong** için bir işaretçi.

*prgSchemas*<br/>
dışı Bir şema satır kümesi GUID 'Leri dizisine işaret eden bir işaretçi ile doldurulmuş Guid dizisine yönelik bir işaretçi.

*prgRest*<br/>
dışı Kısıtlama dizisiyle doldurulacak bir **ulong**dizisine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, sağlayıcı tarafından desteklenen tüm şema satır kümelerinin bir dizisini döndürür. Windows SDK [IDBSchemaRowset:: GetSchemas](/previous-versions/windows/desktop/ms719605(v=vs.85)) öğesine bakın.

Bu işlevin uygulanması, kullanıcının oturum sınıfında bir şema eşlemesine sahip olmasını gerektirir. Şema eşleme bilgilerini kullanarak haritadaki şemalar için GUID dizisi ile yanıt verir. Bu, sağlayıcı tarafından desteklenen şemaları temsil eder.

## <a name="see-also"></a>Ayrıca bkz.

[Şema Satır Kümesi Sınıfları ve Typedef Sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)<br/>
[Şema Satır Kümelerini Destekleme](../../data/oledb/supporting-schema-rowsets.md)<br/>
[SCHEMA_ENTRY](../../data/oledb/schema-entry.md)<br/>
[UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider)
