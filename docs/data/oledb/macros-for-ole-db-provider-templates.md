---
title: OLE DB Sağlayıcı Şablonları için Makrolar
ms.date: 02/11/2019
f1_keywords:
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
ms.openlocfilehash: 5d29b2548102b056a21ebfccb037af3a766788ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369815"
---
# <a name="macros-for-ole-db-provider-templates"></a>OLE DB Sağlayıcı Şablonları için Makrolar

OLE DB Şablonlar Sağlayıcı makroları aşağıdaki kategorilerde işlevsellik sunar:

## <a name="property-set-map-macros"></a>Özellik Kümesi Harita Makroları

|||
|-|-|
|[BEGIN_PROPERTY_SET](#begin_property_set)|Özellik kümesinin başlangıcını işaretler.|
|[BEGIN_PROPERTY_SET_EX](#begin_property_set_ex)|Özellik kümesinin başlangıcını işaretler.|
|[BEGIN_PROPSET_MAP](#begin_propset_map)|Sağlayıcının kapsamı dışında gizlenebilen veya tanımlanabilen bir özellik kümesinin başlangıcını işaretler.|
|[CHAIN_PROPERTY_SET](#chain_property_set)|Özellik gruplarını birbirine zincirler.|
|[END_PROPERTY_SET](#end_property_set)|Özellik kümesinin sonunu işaretler.|
|[END_PROPSET_MAP](#end_propset_map)|Özellik kümesi haritasının sonunu işaretler.|
|[PROPERTY_INFO_ENTRY](#property_info_entry)|Bir özellik kümesinde belirli bir özelliği varsayılan değere ayarlar.|
|[PROPERTY_INFO_ENTRY_EX](#property_info_entry_ex)|Belirli bir özelliği sizin sağladığınız değere ayarlayarak belirli bir özellik ayarlar. Ayrıca bayrakları ve seçenekleri ayarlamanızı sağlar.|
|[PROPERTY_INFO_ENTRY_VALUE](#property_info_entry_value)|Belirli bir özelliği sizin sağladığınız değere ayarlayarak belirli bir özellik ayarlar.|

## <a name="column-map-macros"></a>Sütun Haritası Makroları

|||
|-|-|
|[BEGIN_PROVIDER_COLUMN_MAP](#begin_provider_column_map)|Sağlayıcı sütun eşlemi girişlerinin başlangıcını işaretler.|
|[END_PROVIDER_COLUMN_MAP](#end_provider_column_map)|Sağlayıcı sütun eşlemi girişlerinin sonunu işaretler.|
|[PROVIDER_COLUMN_ENTRY](#provider_column_entry)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.|
|[PROVIDER_COLUMN_ENTRY_FIXED](#provider_column_entry_fixed)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütun veri türünü belirtebilirsiniz.|
|[PROVIDER_COLUMN_ENTRY_GN](#provider_column_entry_gn)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütunun boyutunu, veri türünü, kesinliğini, ölçeğini ve şema satır kümesi GUID'i belirtebilirsiniz.|
|[PROVIDER_COLUMN_ENTRY_LENGTH](#provider_column_entry_length)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütun boyutunu belirtebilirsiniz.|
|[PROVIDER_COLUMN_ENTRY_STR](#provider_column_entry_str)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütun türünün bir dize olduğunu varsayar.|
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](#provider_column_entry_type_length)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. PROVIDER_COLUMN_ENTRY_LENGTH gibi, aynı zamanda sütunun veri türünü ve boyutunu belirtmenize de olanak tanır.|
|[PROVIDER_COLUMN_ENTRY_WSTR](#provider_column_entry_wstr)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütun türünün Unicode karakter dizesi olduğunu varsayar.|

## <a name="schema-rowset-macros"></a>Şema Rowset Makrolar

|||
|-|-|
|[BEGIN_SCHEMA_MAP](#begin_schema_map)|Şema haritasının başlangıcını işaretler.|
|[END_SCHEMA_MAP](#end_schema_map)|Şema haritasının sonunu işaretler.|
|[SCHEMA_ENTRY](#schema_entry)|Guid'i bir sınıfla ilişkilendirer.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

### <a name="begin_property_set"></a><a name="begin_property_set"></a>BEGIN_PROPERTY_SET

Özellik kümesi haritasında ayarlanan bir özelliğin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PROPERTY_SET(guid)
```

#### <a name="parameters"></a>Parametreler

*Guıd*<br/>
[içinde] Özellik GUID.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_PROPSET_MAP.](../../data/oledb/begin-propset-map.md)

### <a name="begin_property_set_ex"></a><a name="begin_property_set_ex"></a>BEGIN_PROPERTY_SET_EX

Özellik kümesi haritasında ayarlanan bir özelliğin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PROPERTY_SET_EX(guid, flags)
```

#### <a name="parameters"></a>Parametreler

*Guıd*<br/>
[içinde] Özellik GUID.

*bayraklar*<br/>
[içinde] UPROPSET_HIDDEN, açığa çıkarmak istemediğiniz özellik kümeleri veya sağlayıcının kapsamı dışında tanımlanan özellikleri açığa çıkaran bir sağlayıcı için UPROPSET_PASSTHROUGH.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_PROPSET_MAP.](../../data/oledb/begin-propset-map.md)

### <a name="begin_propset_map"></a><a name="begin_propset_map"></a>BEGIN_PROPSET_MAP

Özellik kümesi eş kayıtlarının başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PROPSET_MAP(Class)
```

#### <a name="parameters"></a>Parametreler

*Sınıfı*<br/>
[içinde] Bu özellik kümesinin belirtildiği sınıf. Bir özellik kümesi aşağıdaki OLE DB nesnelerinde belirtilebilir:

- [Veri Kaynağı Nesneler](/previous-versions/windows/desktop/ms721278(v=vs.85))

- [Oturum Nesneleri](/previous-versions/windows/desktop/ms711572(v=vs.85))

- [Komutlar](/previous-versions/windows/desktop/ms724608(v=vs.85))

#### <a name="example"></a>Örnek

Örnek özellik kümesi haritası aşağıda veda edebilirsiniz:

[!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]

### <a name="chain_property_set"></a><a name="chain_property_set"></a>CHAIN_PROPERTY_SET

Bu makro özellik gruplarını birbirine zincirler.

#### <a name="syntax"></a>Sözdizimi

```cpp
CHAIN_PROPERTY_SET(ChainClass)
```

#### <a name="parameters"></a>Parametreler

*Zincir Sınıfı*<br/>
[içinde] Özellikleri zincirlemek için sınıfın adı. Bu, zaten bir eş (oturum, komut veya veri kaynağı nesne sınıfı gibi) içeren ATL Project Sihirbazı tarafından oluşturulan bir sınıftır.

#### <a name="remarks"></a>Açıklamalar

Başka bir sınıftan kendi sınıfınıza ayarlanan bir özelliği zincirleyebilir, ardından özellikleri doğrudan sınıfınızdan erişebilirsiniz.

> [!CAUTION]
> Bu makroyu dikkatli kullanın. Yanlış kullanım, tüketicinin OLE DB uygunluk testlerinde başarısız lığa neden olabilir.

### <a name="end_property_set"></a><a name="end_property_set"></a>END_PROPERTY_SET

Özellik kümesinin sonunu işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_PROPERTY_SET(guid)
```

#### <a name="parameters"></a>Parametreler

*Guıd*<br/>
[içinde] Özellik GUID.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_PROPSET_MAP.](../../data/oledb/begin-propset-map.md)

### <a name="end_propset_map"></a><a name="end_propset_map"></a>END_PROPSET_MAP

Özellik kümesi eşkayıtlarının sonunu işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_PROPSET_MAP()
```

#### <a name="example"></a>Örnek

[Bkz. BEGIN_PROPSET_MAP.](../../data/oledb/begin-propset-map.md)

### <a name="property_info_entry"></a><a name="property_info_entry"></a>PROPERTY_INFO_ENTRY

Özellik kümesindeki belirli bir özelliği temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROPERTY_INFO_ENTRY(dwPropID)
```

#### <a name="parameters"></a>Parametreler

*dwPropID*<br/>
[içinde] Bir özelliği tanımlamak için GUID kümesi özelliği ile birlikte kullanılabilecek bir [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) değeri.

#### <a name="remarks"></a>Açıklamalar

Bu makro, türün `DWORD` özellik değerini ATLDB'de tanımlanan varsayılan değere ayarlar. H. Özelliği seçtiğiniz bir değere ayarlamak için [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)kullanın. Özellik için `VARTYPE` [dbpropflags'i](/previous-versions/windows/desktop/ms724342(v=vs.85)) aynı anda ayarlamak için [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)kullanın.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_PROPSET_MAP.](../../data/oledb/begin-propset-map.md)

### <a name="property_info_entry_ex"></a><a name="property_info_entry_ex"></a>PROPERTY_INFO_ENTRY_EX

Özellik kümesindeki belirli bir özelliği temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROPERTY_INFO_ENTRY_EX(dwPropID, vt, dwFlags, value, options)
```

#### <a name="parameters"></a>Parametreler

*dwPropID*<br/>
[içinde] Bir özelliği tanımlamak için GUID kümesi özelliği ile birlikte kullanılabilecek bir [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) değeri.

*Vt*<br/>
[içinde] Bu `VARTYPE` özellik girişinin. (Wtypes.h olarak tanımlanır)

*Dwflags*<br/>
[içinde] Bu özellik girişini açıklayan bir [DBPROPFLAGS](/previous-versions/windows/desktop/ms724342(v=vs.85)) değeri.

*Değer*<br/>
[içinde] Türünün `DWORD`özellik değeri.

*Seçenekler*<br/>
Ya DBPROPOPTIONS_REQUIRED ya da DBPROPOPTIONS_SETIFCHEAP. Normalde, tüketici tarafından ayarlanan bir sağlayıcının *seçenekleri* ayarlaması gerekmez.

#### <a name="remarks"></a>Açıklamalar

Bu makro ile, doğrudan tür `DWORD` özelliği değerinin yanı sıra seçenekleri ve bayrakları belirtebilirsiniz. Bir özelliği yalnızca ATLDB'de tanımlanan varsayılan değere ayarlamak için. H, [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)kullanın. Bir özelliği, üzerinde seçenek veya bayrak ayarlamadan seçtiğiniz bir değere ayarlamak için [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)kullanın.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_PROPSET_MAP.](../../data/oledb/begin-propset-map.md)

### <a name="property_info_entry_value"></a><a name="property_info_entry_value"></a>PROPERTY_INFO_ENTRY_VALUE

Özellik kümesindeki belirli bir özelliği temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROPERTY_INFO_ENTRY_VALUE(dwPropID, value)
```

#### <a name="parameters"></a>Parametreler

*dwPropID*<br/>
[içinde] Bir özelliği tanımlamak için GUID kümesi özelliği ile birlikte kullanılabilecek bir [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) değeri.

*Değer*<br/>
[içinde] Türünün `DWORD`özellik değeri.

#### <a name="remarks"></a>Açıklamalar

Bu makro ile, doğrudan türünün `DWORD`özellik değerini belirtebilirsiniz. Özelliği ATLDB'de tanımlanan varsayılan değere ayarlamak için. H, [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)kullanın. Özelliğin değerini, bayraklarını ve seçeneklerini ayarlamak için [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)kullanın.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_PROPSET_MAP.](../../data/oledb/begin-propset-map.md)

### <a name="begin_provider_column_map"></a><a name="begin_provider_column_map"></a>BEGIN_PROVIDER_COLUMN_MAP

Sağlayıcı sütun eşlemi girişlerinin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PROVIDER_COLUMN_MAP(theClass)
```

#### <a name="parameters"></a>Parametreler

*theClass*<br/>
[içinde] Bu haritanın ait olduğu sınıfın adı.

#### <a name="example"></a>Örnek

Örnek sağlayıcı sütun haritası aşağıda verilmiştir:

[!code-cpp[NVC_OLEDB_Provider#4](../../data/oledb/codesnippet/cpp/begin-provider-column-map_1.h)]

### <a name="end_provider_column_map"></a><a name="end_provider_column_map"></a>END_PROVIDER_COLUMN_MAP

Sağlayıcı sütun eşlemi girişlerinin sonunu işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_PROVIDER_COLUMN_MAP()
```

#### <a name="example"></a>Örnek

[Bkz. BEGIN_PROVIDER_COLUMN_MAP.](../../data/oledb/begin-provider-column-map.md)

### <a name="provider_column_entry"></a><a name="provider_column_entry"></a>PROVIDER_COLUMN_ENTRY

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY (name, ordinal, member)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[içinde] Sütun adı.

*Sıralı*<br/>
[içinde] Sütun numarası. Sütun yer işareti sütunu olmadığı sürece, sütun numarası 0 olmamalıdır.

*Üye*<br/>
[içinde] Sütuna `dataClass` karşılık gelen üye değişken.

### <a name="provider_column_entry_fixed"></a><a name="provider_column_entry_fixed"></a>PROVIDER_COLUMN_ENTRY_FIXED

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_FIXED(name, ordinal, dbtype, member)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[içinde] Sütun adı.

*Sıralı*<br/>
[içinde] Sütun numarası. Sütun yer işareti sütunu olmadığı sürece, sütun numarası 0 olmamalıdır.

*Dbtype*<br/>
[içinde] [DBTYPE'daki](/previous-versions/windows/desktop/ms711251(v=vs.85))veri türü.

*Üye*<br/>
[içinde] Bu ndaki `dataClass` üye değişken verileri depolar.

#### <a name="remarks"></a>Açıklamalar

Sütun veri türünü belirtmenizi sağlar.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_PROVIDER_COLUMN_MAP.](../../data/oledb/begin-provider-column-map.md)

### <a name="provider_column_entry_gn"></a><a name="provider_column_entry_gn"></a>PROVIDER_COLUMN_ENTRY_GN

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_GN (name, ordinal, flags, colSize, dbtype, precision, scale, guid)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[içinde] Sütun adı.

*Sıralı*<br/>
[içinde] Sütun numarası. Sütun yer işareti sütunu olmadığı sürece, sütun numarası 0 olmamalıdır.

*bayraklar*<br/>
[içinde] Verilerin nasıl döndürüldüğünü belirtir. `dwFlags` [DBBINDING Yapıları'ndaki](/previous-versions/windows/desktop/ms716845(v=vs.85))açıklamaya bakın.

*colSize*<br/>
[içinde] Sütun boyutu.

*Dbtype*<br/>
[içinde] Değerin veri türünü gösterir. `wType` [DBBINDING Yapıları'ndaki](/previous-versions/windows/desktop/ms716845(v=vs.85))açıklamaya bakın.

*Hassas*<br/>
[içinde] *dbType* DBTYPE_NUMERIC veya DBTYPE_DECIMAL ise veri alırken kullanılacak hassasiyeti gösterir. `bPrecision` [DBBINDING Yapıları'ndaki](/previous-versions/windows/desktop/ms716845(v=vs.85))açıklamaya bakın.

*Ölçek*<br/>
[içinde] dbType DBTYPE_NUMERIC veya DBTYPE_DECIMAL ise veri alırken kullanılacak ölçeği gösterir. `bScale` [DBBINDING Yapıları'ndaki](/previous-versions/windows/desktop/ms716845(v=vs.85))açıklamaya bakın.

*Guıd*<br/>
Bir şema rowset GUID. Şema satır kümelerinin ve GUID'lerinin listesi için *OLE DB Programcı Başvurusu'nda* [IDBSchemaRowset'e](/previous-versions/windows/desktop/ms713686(v=vs.85)) bakın.

#### <a name="remarks"></a>Açıklamalar

Sütunun boyutunu, veri türünü, kesinliğini, ölçeğini ve şema satır kümesi GUID'i belirtmenizi sağlar.

### <a name="provider_column_entry_length"></a><a name="provider_column_entry_length"></a>PROVIDER_COLUMN_ENTRY_LENGTH

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_LENGTH(name, ordinal, size, member)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[içinde] Sütun adı.

*Sıralı*<br/>
[içinde] Sütun numarası. Sütun yer işareti sütunu olmadığı sürece, sütun numarası 0 olmamalıdır.

*Boyutu*<br/>
[içinde] Baytlarda sütun boyutu.

*Üye*<br/>
[içinde] Bu ndaki `dataClass` üye değişken sütun verilerini depolar.

#### <a name="remarks"></a>Açıklamalar

Sütun boyutunu belirtmenizi sağlar.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_PROVIDER_COLUMN_MAP.](../../data/oledb/begin-provider-column-map.md)

### <a name="provider_column_entry_str"></a><a name="provider_column_entry_str"></a>PROVIDER_COLUMN_ENTRY_STR

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_STR(name, ordinal, member)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[içinde] Sütun adı.

*Sıralı*<br/>
[içinde] Sütun numarası. Sütun yer işareti sütunu olmadığı sürece, sütun numarası 0 olmamalıdır.

*Üye*<br/>
[içinde] Verileri depolayan veri sınıfındaki üye değişken.

#### <a name="remarks"></a>Açıklamalar

Sütun verilerinin [DBTYPE_STR](/previous-versions/windows/desktop/ms711251(v=vs.85))olduğu varsayıldığında bu makroyu kullanın.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_PROVIDER_COLUMN_MAP.](../../data/oledb/begin-provider-column-map.md)

### <a name="provider_column_entry_type_length"></a><a name="provider_column_entry_type_length"></a>PROVIDER_COLUMN_ENTRY_TYPE_LENGTH

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(name, ordinal, dbtype, size, member)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[içinde] Sütun adı.

*Sıralı*<br/>
[içinde] Sütun numarası. Sütun yer işareti sütunu olmadığı sürece, sütun numarası 0 olmamalıdır.

*Dbtype*<br/>
[içinde] [DBTYPE'daki](/previous-versions/windows/desktop/ms711251(v=vs.85))veri türü.

*Boyutu*<br/>
[içinde] Baytlarda sütun boyutu.

*Üye*<br/>
[içinde] Verileri depolayan veri sınıfındaki üye değişken.

#### <a name="remarks"></a>Açıklamalar

[PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md) benzer, aynı zamanda sütunun veri türünü ve boyutunu belirtmenizi sağlar.

### <a name="provider_column_entry_wstr"></a><a name="provider_column_entry_wstr"></a>PROVIDER_COLUMN_ENTRY_WSTR

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_WSTR(name, ordinal, member)
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
[içinde] Sütun adı.

*Sıralı*<br/>
[içinde] Sütun numarası. Sütun yer işareti sütunu olmadığı sürece, sütun numarası 0 olmamalıdır.

*Üye*<br/>
[içinde] Verileri depolayan veri sınıfındaki üye değişken.

#### <a name="remarks"></a>Açıklamalar

Sütun verileri null sonlandırılmış Unicode karakter dizesi, [DBTYPE_WSTR](/previous-versions/windows/desktop/ms711251(v=vs.85))olduğunda bu makroyu kullanın.

### <a name="begin_schema_map"></a><a name="begin_schema_map"></a>BEGIN_SCHEMA_MAP

Şema haritasının başlangıcını gösterir.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_SCHEMA_MAP(SchemaClass);
```

#### <a name="parameters"></a>Parametreler

*ŞemaSınıfı*<br/>
MAP'i içeren sınıf. Genellikle bu oturum sınıfı olacaktır.

#### <a name="remarks"></a>Açıklamalar

Şema satır kümeleri hakkında daha fazla bilgi için Windows SDK'daki [IDBSchemaRowset'e](/previous-versions/windows/desktop/ms713686(v=vs.85)) bakın.

### <a name="end_schema_map"></a><a name="end_schema_map"></a>END_SCHEMA_MAP

Şema haritasının sonunu gösterir.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_SCHEMA_MAP()
```

#### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için, [IDBSchemaRowsetImpl Sınıf](../../data/oledb/idbschemarowsetimpl-class.md)bakın.

### <a name="schema_entry"></a><a name="schema_entry"></a>SCHEMA_ENTRY

Guid'i bir sınıfla ilişkilendirer.

#### <a name="syntax"></a>Sözdizimi

```cpp
SCHEMA_ENTRY(guid,
   rowsetClass);
```

#### <a name="parameters"></a>Parametreler

*Guıd*<br/>
Bir şema rowset GUID. Şema satır kümelerinin ve GUID'lerinin listesi için *OLE DB Programcı Başvurusu'nda* [IDBSchemaRowset'e](/previous-versions/windows/desktop/ms713686(v=vs.85)) bakın.

*rowsetClass*<br/>
Şema satır kümesini temsil etmek için oluşturulacak sınıf.

#### <a name="remarks"></a>Açıklamalar

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) daha sonra GUID'lerin bir listesi için haritasorgulayabilirsiniz veya bir GUID verilirse bir satır kümesi oluşturabilirsiniz. Şema rowset `IDBSchemaRowsetImpl` oluşturur standart `CRowsetImpl`türetilmiş sınıfa benzer, ancak `Execute` aşağıdaki imzaya sahip bir yöntem sağlaması gerekir:

```cpp
HRESULT Execute (LONG* pcRowsAffected,
    ULONG cRestrictions,
    const VARIANT* rgRestrictions);
```

Bu `Execute` işlev rowset verilerini doldurur. ATL Project Wizard, [IDBSchemaRowset'te](/previous-versions/windows/desktop/ms713686(v=vs.85)) Açıklandığı *gibi, OLE DB Programcı*Referansı'nda, üç zorunlu OLE DB şemasının her biri için projedeki üç başlangıç şema satır kümesi oluşturur:

- Dbschema_tables

- Dbschema_columns

- Dbschema_provıder_types

Sihirbaz ayrıca şema haritasına karşılık gelen üç giriş ekler. Bkz. Bir sağlayıcı oluşturmak için sihirbazı kullanma hakkında daha fazla bilgi için [bir OLE DB Şablon Sağlayıcısı](../../data/oledb/creating-an-ole-db-provider.md) Oluşturma.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablon Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)<br/>
[OLE DB Sağlayıcı Şablonları Başvurusu](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB Sağlayıcı Şablonları için Makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md)
