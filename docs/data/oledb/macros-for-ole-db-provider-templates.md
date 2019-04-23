---
title: OLE DB Sağlayıcı Şablonları için Makrolar
ms.date: 02/11/2019
f1_keywords:
- vc.templates.ole
- BEGIN_PROPERTY_SET
- BEGIN_PROPERTY_SET_EX
- BEGIN_PROPSET_MAP
- CHAIN_PROPERTY_SET
- END_PROPERTY_SET
- END_PROPSET_MAP
- PROPERTY_INFO_ENTRY
- PROPERTY_INFO_ENTRY_EX
- PROPERTY_INFO_ENTRY_VALUE
- BEGIN_PROVIDER_COLUMN_MAP
- END_PROVIDER_COLUMN_MAP
- PROVIDER_COLUMN_ENTRY
- PROVIDER_COLUMN_ENTRY_FIXED
- PROVIDER_COLUMN_ENTRY_GN
- PROVIDER_COLUMN_ENTRY_LENGTH
- PROVIDER_COLUMN_ENTRY_STR
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
- PROVIDER_COLUMN_ENTRY_WSTR
- BEGIN_SCHEMA_MAP
- END_SCHEMA_MAP
- SCHEMA_ENTRY
helpviewer_keywords:
- OLE DB provider templates, macros
- macros, OLE DB Provider Templates
- Provider Template macros (OLE DB)
- OLE DB Provider Template macros
- BEGIN_PROPERTY_SET macro
- BEGIN_PROPERTY_SET_EX macro
- BEGIN_PROPSET_MAP macro
- CHAIN_PROPERTY_SET macro
- END_PROPERTY_SET macro
- END_PROPSET_MAP macro
- PROPERTY_INFO_ENTRY macro
- PROPERTY_INFO_ENTRY_EX macro
- PROPERTY_INFO_ENTRY_VALUE macro
- BEGIN_PROVIDER_COLUMN_MAP macro
- END_PROVIDER_COLUMN_MAP macro
- PROVIDER_COLUMN_ENTRY macro
- PROVIDER_COLUMN_ENTRY_FIXED macro
- PROVIDER_COLUMN_ENTRY_GN macro
- PROVIDER_COLUMN_ENTRY_LENGTH macro
- PROVIDER_COLUMN_ENTRY_STR macro
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH macro
- PROVIDER_COLUMN_ENTRY_WSTR macro
- BEGIN_SCHEMA_MAP macro
- END_SCHEMA_MAP macro
- SCHEMA_ENTRY macro
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
ms.openlocfilehash: f5cf5e8ebadcc48dbd040225496f0a437b92555c
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415194"
---
# <a name="macros-for-ole-db-provider-templates"></a>OLE DB Sağlayıcı Şablonları için Makrolar

OLE DB Şablonları sağlayıcısı makroları işlevselliğini Aşağıdaki kategorilerde sunulur:

## <a name="property-set-map-macros"></a>Özellik kümesi eşleme makroları

|||
|-|-|
|[BEGIN_PROPERTY_SET](#begin_property_set)|Bir özellik kümesi başlangıcını işaretler.|
|[BEGIN_PROPERTY_SET_EX](#begin_property_set_ex)|Bir özellik kümesi başlangıcını işaretler.|
|[BEGIN_PROPSET_MAP](#begin_propset_map)|Bir özelliğin başına kümesi işaretleri gizli veya sağlayıcı kapsamı dışında tanımlanmış.|
|[CHAIN_PROPERTY_SET](#chain_property_set)|Özellik gruplarını zincir.|
|[END_PROPERTY_SET](#end_property_set)|Bir özellik kümesi sonunu işaretler.|
|[END_PROPSET_MAP](#end_propset_map)|Bir özellik kümesi eşlemesini sonunu işaretler.|
|[PROPERTY_INFO_ENTRY](#property_info_entry)|Bir özellik için varsayılan bir değer kümesi içinde belirli bir özellik ayarlar.|
|[PROPERTY_INFO_ENTRY_EX](#property_info_entry_ex)|Belirli bir özellik, sizin tarafınızdan sağlanan bir değere özellik ayarlar. Ayrıca bayrakları ve seçenekleri ayarlamanıza olanak sağlar.|
|[PROPERTY_INFO_ENTRY_VALUE](#property_info_entry_value)|Belirli bir özellik, sizin tarafınızdan sağlanan bir değere özellik ayarlar.|

## <a name="column-map-macros"></a>Sütun eşleme makroları

|||
|-|-|
|[BEGIN_PROVIDER_COLUMN_MAP](#begin_provider_column_map)|Sağlayıcı sütun eşleme girişleri başlangıcını işaretler.|
|[END_PROVIDER_COLUMN_MAP](#end_provider_column_map)|Sağlayıcı sütun eşleme girişleri sonunu işaretler.|
|[PROVIDER_COLUMN_ENTRY](#provider_column_entry)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.|
|[PROVIDER_COLUMN_ENTRY_FIXED](#provider_column_entry_fixed)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütunun veri türünü belirtebilir.|
|[PROVIDER_COLUMN_ENTRY_GN](#provider_column_entry_gn)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütun boyutu, veri türü, kesinlik, ölçek ve şeması satır kümesi GUID'si belirtebilirsiniz.|
|[PROVIDER_COLUMN_ENTRY_LENGTH](#provider_column_entry_length)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütun boyutu belirtebilirsiniz.|
|[PROVIDER_COLUMN_ENTRY_STR](#provider_column_entry_str)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Bu sütun türü bir dize olduğunu varsayar.|
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](#provider_column_entry_type_length)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Provıder_column_entry_length ister, ancak ayrıca boyutu yanı sıra, sütunun veri türünü belirtmenize olanak sağlar.|
|[PROVIDER_COLUMN_ENTRY_WSTR](#provider_column_entry_wstr)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Bu şekilde, bir Unicode karakter dizesi sütun türü olduğunu varsayar.|

## <a name="schema-rowset-macros"></a>Şema satır kümesi makroları

|||
|-|-|
|[BEGIN_SCHEMA_MAP](#begin_schema_map)|Bir şema eşlemesine başlangıcını işaretler.|
|[END_SCHEMA_MAP](#end_schema_map)|Şema eşleme sonunu işaretler.|
|[SCHEMA_ENTRY](#schema_entry)|Bir GUID, bir sınıf ile ilişkilendirir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

### <a name="begin_property_set"></a> BEGIN_PROPERTY_SET

Bir özelliğin başına bir özelliği ayarlamak işaretleri eşlemesi ayarlayın.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PROPERTY_SET(guid)
```

#### <a name="parameters"></a>Parametreler

*GUID*<br/>
[in] Özellik GUID.

#### <a name="example"></a>Örnek

Bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="begin_property_set_ex"></a> BEGIN_PROPERTY_SET_EX

Bir özelliğin başına bir özelliği ayarlamak işaretleri eşlemesi ayarlayın.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PROPERTY_SET_EX(guid, flags)
```

#### <a name="parameters"></a>Parametreler

*GUID*<br/>
[in] Özellik GUID.

*bayrakları*<br/>
[in] UPROPSET_HIDDEN göstermek istemediğiniz herhangi bir özellik kümeleri veya UPROPSET_PASSTHROUGH sağlayıcı kapsamı dışında tanımlanan özellikleri kullanıma sunan bir sağlayıcı için.

#### <a name="example"></a>Örnek

Bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="begin_propset_map"></a> BEGIN_PROPSET_MAP

İşaretleri özelliğinin başına eşleme girişleri ayarlayın.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PROPSET_MAP(Class)
```

#### <a name="parameters"></a>Parametreler

*Sınıfı*<br/>
[in] Bu özelliği ayarlamak, sınıfın belirtilir. Bir özellik kümesi, OLE DB nesneleri belirtilebilir:

- [Veri kaynağı nesneleri](/previous-versions/windows/desktop/ms721278(v=vs.85))

- [Oturum nesneleri](/previous-versions/windows/desktop/ms711572(v=vs.85))

- [Komutları](/previous-versions/windows/desktop/ms724608(v=vs.85))

#### <a name="example"></a>Örnek

Örnek özellik kümesi eşlemesi şu şekildedir:

[!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]

### <a name="chain_property_set"></a> CHAIN_PROPERTY_SET

Bu makro özellik gruplarını zincir.

#### <a name="syntax"></a>Sözdizimi

```cpp
CHAIN_PROPERTY_SET(ChainClass)
```

#### <a name="parameters"></a>Parametreler

*ChainClass*<br/>
[in] Zincir özelliklerini sınıfı adı. Bu, zaten (örneğin, bir oturum, komut veya veri kaynağı nesne sınıfı) bir harita içeren ATL Proje Sihirbazı tarafından oluşturulan bir sınıftır.

#### <a name="remarks"></a>Açıklamalar

Zincir kendi sınıf başka bir sınıftaki bir özellik kümesi, ardından sınıftan doğrudan erişim özellikleri.

> [!CAUTION]
>  Bu makro tedbirli şekilde kullanın. Hatalı kullanımı, bir tüketici OLE DB uygunluk testlerini başarısız olmasına neden olabilir.

### <a name="end_property_set"></a> END_PROPERTY_SET

Bir özellik kümesi sonunu işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_PROPERTY_SET(guid)
```

#### <a name="parameters"></a>Parametreler

*GUID*<br/>
[in] Özellik GUID.

#### <a name="example"></a>Örnek

Bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="end_propset_map"></a> END_PROPSET_MAP

İşaretleri özelliği sonuna eşleme girişleri ayarlayın.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_PROPSET_MAP()
```

#### <a name="example"></a>Örnek

Bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="property_info_entry"></a> PROPERTY_INFO_ENTRY

Bir özellik kümesi içinde belirli bir özelliği temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROPERTY_INFO_ENTRY(dwPropID)
```

#### <a name="parameters"></a>Parametreler

*dwPropID*<br/>
[in] A [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) özelliği ile birlikte kullanılan değeri ayarlanmış bir özelliği tanımlayan GUID.

#### <a name="remarks"></a>Açıklamalar

Bu makro türü özellik değerini ayarlar `DWORD` ATLDB içinde tanımlanmış bir varsayılan değer. H Bir değerine özellik ayarlamak için kullanın [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md). Ayarlanacak `VARTYPE` ve [DBPROPFLAGS](/previous-versions/windows/desktop/ms724342(v=vs.85)) özelliği için aynı anda kullanmak [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md).

#### <a name="example"></a>Örnek

Bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="property_info_entry_ex"></a> PROPERTY_INFO_ENTRY_EX

Bir özellik kümesi içinde belirli bir özelliği temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROPERTY_INFO_ENTRY_EX(dwPropID, vt, dwFlags, value, options)
```

#### <a name="parameters"></a>Parametreler

*dwPropID*<br/>
[in] A [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) özelliği ile birlikte kullanılan değeri ayarlanmış bir özelliği tanımlayan GUID.

*vt*<br/>
[in] `VARTYPE` Bu özelliği giriş. (Wtypes.h içinde tanımlanmıştır)

*CertOpenStore*<br/>
[in] A [DBPROPFLAGS](/previous-versions/windows/desktop/ms724342(v=vs.85)) bu özellik girdisini tanımlayan değer.

*value*<br/>
[in] Özellik değeri türü `DWORD`.

*Seçenekler*<br/>
DBPROPOPTIONS_REQUIRED veya DBPROPOPTIONS_SETIFCHEAP. Normalde, bir sağlayıcı ayarlayın gerekmez *seçenekleri* çünkü tüketici tarafından ayarlanır.

#### <a name="remarks"></a>Açıklamalar

Bu makro, özellik değeri türü doğrudan belirtebilirsiniz `DWORD` yanı sıra seçenekleri ve bayrakları. Yalnızca ATLDB içinde tanımlanan varsayılan değerine özellik ayarlamak için. H, kullanım [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Bir değere seçeneklerini ayarlama ya da bayrakları olmadan tercih ettiğiniz bir özelliği ayarlamak üzere kullanımı [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md).

#### <a name="example"></a>Örnek

Bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="property_info_entry_value"></a> PROPERTY_INFO_ENTRY_VALUE

Bir özellik kümesi içinde belirli bir özelliği temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROPERTY_INFO_ENTRY_VALUE(dwPropID, value)
```

#### <a name="parameters"></a>Parametreler

*dwPropID*<br/>
[in] A [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) özelliği ile birlikte kullanılan değeri ayarlanmış bir özelliği tanımlayan GUID.

*value*<br/>
[in] Özellik değeri türü `DWORD`.

#### <a name="remarks"></a>Açıklamalar

Bu makro, özellik değeri türü doğrudan belirtebilirsiniz `DWORD`. ATLDB içinde tanımlanan varsayılan değerine özellik ayarlamak için. H, kullanım [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Değer, bayraklar ve özellik seçeneklerini ayarlamak için kullanın [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md).

#### <a name="example"></a>Örnek

Bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="begin_provider_column_map"></a> BEGIN_PROVIDER_COLUMN_MAP

Sağlayıcı sütun eşleme girişleri başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PROVIDER_COLUMN_MAP(theClass)
```

#### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
[in] Bu harita ait olduğu sınıfın adı.

#### <a name="example"></a>Örnek

Bir örnek sağlayıcısı sütun eşlemesi şu şekildedir:

[!code-cpp[NVC_OLEDB_Provider#4](../../data/oledb/codesnippet/cpp/begin-provider-column-map_1.h)]

### <a name="end_provider_column_map"></a> END_PROVIDER_COLUMN_MAP

Sağlayıcı sütun eşleme girişleri sonunu işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_PROVIDER_COLUMN_MAP()
```

#### <a name="example"></a>Örnek

Bkz: [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry"></a> PROVIDER_COLUMN_ENTRY

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY (name, ordinal, member)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[in] Sütun adı.

*Sıra*<br/>
[in] Sütun numarası. Bir yer işareti sütunu bir sütun olmadığı sürece, sütun numarası 0 olmalıdır.

*Üyesi*<br/>
[in] Üye değişkeni `dataClass` sütununa karşılık gelen.

### <a name="provider_column_entry_fixed"></a> PROVIDER_COLUMN_ENTRY_FIXED

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_FIXED(name, ordinal, dbtype, member)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[in] Sütun adı.

*Sıra*<br/>
[in] Sütun numarası. Bir yer işareti sütunu bir sütun olmadığı sürece, sütun numarası 0 olmalıdır.

*DbType*<br/>
[in] Veri türü olarak [DBTYPE](/previous-versions/windows/desktop/ms711251(v=vs.85)).

*Üyesi*<br/>
[in] Üye değişkeni `dataClass` , verileri depolar.

#### <a name="remarks"></a>Açıklamalar

Sütun veri türü belirtmenizi sağlar.

#### <a name="example"></a>Örnek

Bkz: [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry_gn"></a> PROVIDER_COLUMN_ENTRY_GN

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_GN (name, ordinal, flags, colSize, dbtype, precision, scale, guid)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[in] Sütun adı.

*Sıra*<br/>
[in] Sütun numarası. Bir yer işareti sütunu bir sütun olmadığı sürece, sütun numarası 0 olmalıdır.

*bayrakları*<br/>
[in] Veriler nasıl döndürülür belirtir. Bkz: `dwFlags` açıklamasında [IAccessor::CreateAccessor'ı yapıları](/previous-versions/windows/desktop/ms716845(v=vs.85)).

*colSize*<br/>
[in] Sütun boyutu.

*DbType*<br/>
[in] Değeri veri türünü belirtir. Bkz: `wType` açıklamasında [IAccessor::CreateAccessor'ı yapıları](/previous-versions/windows/desktop/ms716845(v=vs.85)).

*Duyarlık*<br/>
[in] Veri alma sırasında kullanılacak duyarlık gösterir *dbType* DBTYPE_NUMERIC veya DBTYPE_DECIMAL. Bkz: `bPrecision` açıklamasında [IAccessor::CreateAccessor'ı yapıları](/previous-versions/windows/desktop/ms716845(v=vs.85)).

*Ölçek*<br/>
[in] DbType DBTYPE_NUMERIC veya DBTYPE_DECIMAL ise veri alınırken kullanılacak ölçek gösterir. Bkz: `bScale` açıklamasında [IAccessor::CreateAccessor'ı yapıları](/previous-versions/windows/desktop/ms716845(v=vs.85)).

*GUID*<br/>
Bir şema satır kümesi GUID'si. Bkz: [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) içinde *OLE DB Programcının Başvurusu* şema satır kümeleri ve GUID'ler listesi.

#### <a name="remarks"></a>Açıklamalar

Sütun boyutu, veri türü, kesinlik, ölçek ve şeması satır kümesi GUID'si belirtmenizi sağlar.

### <a name="provider_column_entry_length"></a> PROVIDER_COLUMN_ENTRY_LENGTH

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_LENGTH(name, ordinal, size, member)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[in] Sütun adı.

*Sıra*<br/>
[in] Sütun numarası. Bir yer işareti sütunu bir sütun olmadığı sürece, sütun numarası 0 olmalıdır.

*Boyutu*<br/>
[in] Sütun boyutu bayt cinsinden.

*Üyesi*<br/>
[in] Üye değişkeni `dataClass` , sütun verilerini depolar.

#### <a name="remarks"></a>Açıklamalar

Sütun boyutu belirtmenizi sağlar.

#### <a name="example"></a>Örnek

Bkz: [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry_str"></a> PROVIDER_COLUMN_ENTRY_STR

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_STR(name, ordinal, member)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[in] Sütun adı.

*Sıra*<br/>
[in] Sütun numarası. Bir yer işareti sütunu bir sütun olmadığı sürece, sütun numarası 0 olmalıdır.

*Üyesi*<br/>
[in] Veri depolayan veri sınıfı üye değişkeni.

#### <a name="remarks"></a>Açıklamalar

Sütun verileri varsayılır Bu makroyu kullanın [DBTYPE_STR](/previous-versions/windows/desktop/ms711251(v=vs.85)).

#### <a name="example"></a>Örnek

Bkz: [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry_type_length"></a> PROVIDER_COLUMN_ENTRY_TYPE_LENGTH

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(name, ordinal, dbtype, size, member)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[in] Sütun adı.

*Sıra*<br/>
[in] Sütun numarası. Bir yer işareti sütunu bir sütun olmadığı sürece, sütun numarası 0 olmalıdır.

*DbType*<br/>
[in] Veri türü olarak [DBTYPE](/previous-versions/windows/desktop/ms711251(v=vs.85)).

*Boyutu*<br/>
[in] Sütun boyutu bayt cinsinden.

*Üyesi*<br/>
[in] Veri depolayan veri sınıfı üye değişkeni.

#### <a name="remarks"></a>Açıklamalar

Benzer şekilde [provıder_column_entry_length](../../data/oledb/provider-column-entry-length.md) ancak ayrıca boyutu yanı sıra, sütunun veri türünü belirtmenize olanak sağlar.

### <a name="provider_column_entry_wstr"></a> PROVIDER_COLUMN_ENTRY_WSTR

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_WSTR(name, ordinal, member)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[in] Sütun adı.

*Sıra*<br/>
[in] Sütun numarası. Bir yer işareti sütunu bir sütun olmadığı sürece, sütun numarası 0 olmalıdır.

*Üyesi*<br/>
[in] Veri depolayan veri sınıfı üye değişkeni.

#### <a name="remarks"></a>Açıklamalar

Sütun verileri bir null sonlandırılmış Unicode karakter dizesi olduğunda bu makroyu kullanın [DBTYPE_WSTR](/previous-versions/windows/desktop/ms711251(v=vs.85)).

### <a name="begin_schema_map"></a> BEGIN_SCHEMA_MAP

Şema eşleme başına gösterir.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_SCHEMA_MAP(SchemaClass);
```

#### <a name="parameters"></a>Parametreler

*SchemaClass*<br/>
Harita içeren sınıf. Genellikle bu oturum sınıfının olacaktır.

#### <a name="remarks"></a>Açıklamalar

Bkz: [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) şema satır kümeleri hakkında daha fazla bilgi için Windows SDK.

### <a name="end_schema_map"></a> END_SCHEMA_MAP

Şema eşleme sonuna gösterir.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_SCHEMA_MAP()
```

#### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [IDBSchemaRowsetImpl sınıfı](../../data/oledb/idbschemarowsetimpl-class.md).

### <a name="schema_entry"></a> SCHEMA_ENTRY

Bir GUID, bir sınıf ile ilişkilendirir.

#### <a name="syntax"></a>Sözdizimi

```cpp
SCHEMA_ENTRY(guid,
   rowsetClass);
```

#### <a name="parameters"></a>Parametreler

*GUID*<br/>
Bir şema satır kümesi GUID'si. Bkz: [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) içinde *OLE DB Programcının Başvurusu* şema satır kümeleri ve GUID'ler listesi.

*RowsetClass*<br/>
Şema satır kümesi temsil etmek için oluşturulan sınıf.

#### <a name="remarks"></a>Açıklamalar

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) sonra eşleme GUID'lerinin listesi için sorgu yapabilirsiniz veya bir GUID verilirse, bir satır kümesi oluşturabilirsiniz. Şema satır kümesi `IDBSchemaRowsetImpl` oluşturur standart benzer `CRowsetImpl`-sağlamanız gerekir ancak türetilmiş bir sınıf, bir `Execute` şu imzaya sahip yöntemi:

```cpp
HRESULT Execute (LONG* pcRowsAffected,
    ULONG cRestrictions,
    const VARIANT* rgRestrictions);
```

Bu `Execute` işlevi satır kümesinin veri doldurur. ATL projesi Sihirbazı oluşturur açıklandığı [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) içinde *OLE DB Programcının Başvurusu*, üç ilk şema satır kümeleri projedeki her üç zorunlu OLE DB şemaları için:

- DBSCHEMA_TABLES

- DBSCHEMA_COLUMNS

- DBSCHEMA_PROVIDER_TYPES

Sihirbaz, ayrıca şema haritada üç karşılık gelen girişler ekler. Bkz: [OLE DB Şablon sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md) bir sağlayıcı oluşturmak için sihirbazı kullanma hakkında daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)<br/>
[OLE DB Sağlayıcı Şablonları Başvurusu](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB Sağlayıcı Şablonları için Makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md)