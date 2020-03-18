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
ms.openlocfilehash: b11455c1de13321bce52fbc3be906014b2844aee
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442409"
---
# <a name="macros-for-ole-db-provider-templates"></a>OLE DB Sağlayıcı Şablonları için Makrolar

OLE DB şablonları sağlayıcı makroları aşağıdaki kategorilerdeki işlevleri sunar:

## <a name="property-set-map-macros"></a>Özellik kümesi eşleme makroları

|||
|-|-|
|[BEGIN_PROPERTY_SET](#begin_property_set)|Bir özellik kümesinin başlangıcını işaretler.|
|[BEGIN_PROPERTY_SET_EX](#begin_property_set_ex)|Bir özellik kümesinin başlangıcını işaretler.|
|[BEGIN_PROPSET_MAP](#begin_propset_map)|Bir özellik kümesinin başlangıcını, bu,, sağlayıcının kapsamı dışında gizli veya tanımlanmış olacak şekilde işaretler.|
|[CHAIN_PROPERTY_SET](#chain_property_set)|Özellik gruplarını birlikte zincirler.|
|[END_PROPERTY_SET](#end_property_set)|Bir özellik kümesinin sonunu işaretler.|
|[END_PROPSET_MAP](#end_propset_map)|Özellik kümesi eşlemesinin sonunu işaretler.|
|[PROPERTY_INFO_ENTRY](#property_info_entry)|Bir özellik kümesindeki belirli bir özelliği varsayılan değere ayarlar.|
|[PROPERTY_INFO_ENTRY_EX](#property_info_entry_ex)|Bir özellik kümesindeki belirli bir özelliği sizin tarafınızdan sağlanan bir değere ayarlar. Ayrıca bayrakları ve seçenekleri ayarlamanıza olanak sağlar.|
|[PROPERTY_INFO_ENTRY_VALUE](#property_info_entry_value)|Bir özellik kümesindeki belirli bir özelliği sizin tarafınızdan sağlanan bir değere ayarlar.|

## <a name="column-map-macros"></a>Sütun Haritası makroları

|||
|-|-|
|[BEGIN_PROVIDER_COLUMN_MAP](#begin_provider_column_map)|Sağlayıcı sütun eşleme girdilerinin başlangıcını işaretler.|
|[END_PROVIDER_COLUMN_MAP](#end_provider_column_map)|Sağlayıcı sütun eşleme girdilerinin sonunu işaretler.|
|[PROVIDER_COLUMN_ENTRY](#provider_column_entry)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.|
|[PROVIDER_COLUMN_ENTRY_FIXED](#provider_column_entry_fixed)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütun veri türünü belirtebilirsiniz.|
|[PROVIDER_COLUMN_ENTRY_GN](#provider_column_entry_gn)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütunun boyutunu, veri türünü, duyarlılığını, ölçeğini ve şema satır kümesi GUID 'sini belirtebilirsiniz.|
|[PROVIDER_COLUMN_ENTRY_LENGTH](#provider_column_entry_length)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütun boyutunu belirtebilirsiniz.|
|[PROVIDER_COLUMN_ENTRY_STR](#provider_column_entry_str)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütun türünün bir dize olduğunu varsayar.|
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](#provider_column_entry_type_length)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. PROVIDER_COLUMN_ENTRY_LENGTH gibi, ancak sütunun veri türünü de ve boyutunu belirtmenize de olanak tanır.|
|[PROVIDER_COLUMN_ENTRY_WSTR](#provider_column_entry_wstr)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütun türünün bir Unicode karakter dizesi olduğunu varsayar.|

## <a name="schema-rowset-macros"></a>Şema satır kümesi makroları

|||
|-|-|
|[BEGIN_SCHEMA_MAP](#begin_schema_map)|Şema eşlemesinin başlangıcını işaretler.|
|[END_SCHEMA_MAP](#end_schema_map)|Bir şema eşlemesinin sonunu işaretler.|
|[SCHEMA_ENTRY](#schema_entry)|GUID 'ı bir sınıf ile ilişkilendirir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

### <a name="begin_property_set"></a>BEGIN_PROPERTY_SET

Özellik kümesi eşlemesinde bir özelliğin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PROPERTY_SET(guid)
```

#### <a name="parameters"></a>Parametreler

*'ini*<br/>
'ndaki Özellik GUID 'SI.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="begin_property_set_ex"></a>BEGIN_PROPERTY_SET_EX

Özellik kümesi eşlemesinde bir özelliğin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PROPERTY_SET_EX(guid, flags)
```

#### <a name="parameters"></a>Parametreler

*'ini*<br/>
'ndaki Özellik GUID 'SI.

*larına*<br/>
'ndaki Göstermek istemediğiniz herhangi bir özellik kümesi için UPROPSET_HIDDEN veya sağlayıcının kapsamı dışında tanımlanan özellikleri açığa çıkaran bir sağlayıcı için UPROPSET_PASSTHROUGH.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="begin_propset_map"></a>BEGIN_PROPSET_MAP

Özellik kümesi eşleme girdilerinin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PROPSET_MAP(Class)
```

#### <a name="parameters"></a>Parametreler

*Sınıfı*<br/>
'ndaki Bu özellik kümesinin belirtildiği sınıf. Aşağıdaki OLE DB nesnelerinde bir özellik kümesi belirtilebilir:

- [Veri kaynağı nesneleri](/previous-versions/windows/desktop/ms721278(v=vs.85))

- [Oturum nesneleri](/previous-versions/windows/desktop/ms711572(v=vs.85))

- [Komut](/previous-versions/windows/desktop/ms724608(v=vs.85))

#### <a name="example"></a>Örnek

Örnek özellik kümesi eşlemesi aşağıda verilmiştir:

[!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]

### <a name="chain_property_set"></a>CHAIN_PROPERTY_SET

Bu makro, özellik gruplarını birlikte zincirler.

#### <a name="syntax"></a>Sözdizimi

```cpp
CHAIN_PROPERTY_SET(ChainClass)
```

#### <a name="parameters"></a>Parametreler

*ChainClass*<br/>
'ndaki İçin özelliklerin zincirde olduğu sınıfın adı. Bu, zaten bir eşlem (örneğin, bir oturum, komut veya veri kaynağı nesne sınıfı) içeren ATL Proje Sihirbazı tarafından oluşturulan bir sınıftır.

#### <a name="remarks"></a>Açıklamalar

Başka bir sınıftan bir özellik kümesini kendi sınıfınıza zincirleyebilir, sonra doğrudan sınıfınızdan özelliklere erişebilirsiniz.

> [!CAUTION]
>  Bu makroyu dikkatli bir şekilde kullanın. Hatalı kullanım, bir tüketicinin OLE DB uygunluk testlerini başarısız olmasına neden olabilir.

### <a name="end_property_set"></a>END_PROPERTY_SET

Bir özellik kümesinin sonunu işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_PROPERTY_SET(guid)
```

#### <a name="parameters"></a>Parametreler

*'ini*<br/>
'ndaki Özellik GUID 'SI.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="end_propset_map"></a>END_PROPSET_MAP

Özellik kümesi eşleme girdilerinin sonunu işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_PROPSET_MAP()
```

#### <a name="example"></a>Örnek

Bkz. [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="property_info_entry"></a>PROPERTY_INFO_ENTRY

Bir özellik kümesindeki belirli bir özelliği temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROPERTY_INFO_ENTRY(dwPropID)
```

#### <a name="parameters"></a>Parametreler

*Dwpropıd*<br/>
'ndaki Bir özelliği tanımlamak için özellik kümesi GUID 'SI ile birlikte kullanılabilen bir [Dbpropid](/previous-versions/windows/desktop/ms723882(v=vs.85)) değeri.

#### <a name="remarks"></a>Açıklamalar

Bu makro, `DWORD` türü özellik değerini ATLDB içinde tanımlanan varsayılan değere ayarlar. Olsun. Özelliği seçtiğiniz bir değere ayarlamak için [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)kullanın. Özelliği için `VARTYPE` ve [dbpropflags](/previous-versions/windows/desktop/ms724342(v=vs.85)) 'i aynı anda ayarlamak için [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)kullanın.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="property_info_entry_ex"></a>PROPERTY_INFO_ENTRY_EX

Bir özellik kümesindeki belirli bir özelliği temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROPERTY_INFO_ENTRY_EX(dwPropID, vt, dwFlags, value, options)
```

#### <a name="parameters"></a>Parametreler

*Dwpropıd*<br/>
'ndaki Bir özelliği tanımlamak için özellik kümesi GUID 'SI ile birlikte kullanılabilen bir [Dbpropid](/previous-versions/windows/desktop/ms723882(v=vs.85)) değeri.

*z*<br/>
'ndaki Bu özellik girişinin `VARTYPE`. (WTypes. h içinde tanımlanır)

*dwFlags*<br/>
'ndaki Bu özellik girişini açıklayan bir [dbpropflags](/previous-versions/windows/desktop/ms724342(v=vs.85)) değeri.

*value*<br/>
'ndaki `DWORD`türünün Özellik değeri.

*Seçenekler*<br/>
Ya DBPROPOPTIONS_REQUIRED ya da DBPROPOPTIONS_SETIFCHEAP. Normalde, bir sağlayıcının tüketici tarafından ayarlandığı bu yana *seçenekleri* ayarlaması gerekmez.

#### <a name="remarks"></a>Açıklamalar

Bu makro ile, tür ve bayrakların özellik değerini doğrudan belirtebilirsiniz `DWORD`. Yalnızca bir özelliği ATLDB 'de tanımlanan varsayılan bir değere ayarlamak için. H, [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)kullanın. Bir özelliği seçtiğiniz bir değere ayarlamak için, üzerinde seçenek veya bayrak ayarlamadan [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)kullanın.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="property_info_entry_value"></a>PROPERTY_INFO_ENTRY_VALUE

Bir özellik kümesindeki belirli bir özelliği temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROPERTY_INFO_ENTRY_VALUE(dwPropID, value)
```

#### <a name="parameters"></a>Parametreler

*Dwpropıd*<br/>
'ndaki Bir özelliği tanımlamak için özellik kümesi GUID 'SI ile birlikte kullanılabilen bir [Dbpropid](/previous-versions/windows/desktop/ms723882(v=vs.85)) değeri.

*value*<br/>
'ndaki `DWORD`türünün Özellik değeri.

#### <a name="remarks"></a>Açıklamalar

Bu makro ile, `DWORD`türünün özellik değerini doğrudan belirtebilirsiniz. Özelliği, ATLDB 'de tanımlanan varsayılan değere ayarlamak için. H, [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)kullanın. Özelliğin değerini, bayraklarını ve seçeneklerini ayarlamak için [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)kullanın.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="begin_provider_column_map"></a>BEGIN_PROVIDER_COLUMN_MAP

Sağlayıcı sütun eşleme girdilerinin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PROVIDER_COLUMN_MAP(theClass)
```

#### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
'ndaki Bu haritanın ait olduğu sınıfın adı.

#### <a name="example"></a>Örnek

Örnek sağlayıcı sütun eşlemesi aşağıda verilmiştir:

[!code-cpp[NVC_OLEDB_Provider#4](../../data/oledb/codesnippet/cpp/begin-provider-column-map_1.h)]

### <a name="end_provider_column_map"></a>END_PROVIDER_COLUMN_MAP

Sağlayıcı sütun eşleme girdilerinin sonunu işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_PROVIDER_COLUMN_MAP()
```

#### <a name="example"></a>Örnek

Bkz. [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry"></a>PROVIDER_COLUMN_ENTRY

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY (name, ordinal, member)
```

#### <a name="parameters"></a>Parametreler

*ada*<br/>
'ndaki Sütun adı.

*numarasını*<br/>
'ndaki Sütun numarası. Sütun bir yer Işareti sütunu değilse, sütun numarası 0 olmamalı.

*üyesidir*<br/>
'ndaki Sütununa karşılık gelen `dataClass` üye değişkeni.

### <a name="provider_column_entry_fixed"></a>PROVIDER_COLUMN_ENTRY_FIXED

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_FIXED(name, ordinal, dbtype, member)
```

#### <a name="parameters"></a>Parametreler

*ada*<br/>
'ndaki Sütun adı.

*numarasını*<br/>
'ndaki Sütun numarası. Sütun bir yer Işareti sütunu değilse, sütun numarası 0 olmamalı.

*DbType*<br/>
'ndaki [DbType](/previous-versions/windows/desktop/ms711251(v=vs.85))içindeki veri türü.

*üyesidir*<br/>
'ndaki Verileri depolayan `dataClass` üye değişkeni.

#### <a name="remarks"></a>Açıklamalar

Sütun veri türünü belirtmenize izin verir.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry_gn"></a>PROVIDER_COLUMN_ENTRY_GN

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_GN (name, ordinal, flags, colSize, dbtype, precision, scale, guid)
```

#### <a name="parameters"></a>Parametreler

*ada*<br/>
'ndaki Sütun adı.

*numarasını*<br/>
'ndaki Sütun numarası. Sütun bir yer Işareti sütunu değilse, sütun numarası 0 olmamalı.

*larına*<br/>
'ndaki Verilerin nasıl döndürüleceğini belirtir. [Dbbinding yapılarında](/previous-versions/windows/desktop/ms716845(v=vs.85))`dwFlags` açıklamasına bakın.

*colSize*<br/>
'ndaki Sütun boyutu.

*DbType*<br/>
'ndaki Değerin veri türünü gösterir. [Dbbinding yapılarında](/previous-versions/windows/desktop/ms716845(v=vs.85))`wType` açıklamasına bakın.

*duyarlılık*<br/>
'ndaki *DbType* DBTYPE_NUMERIC veya DBTYPE_DECIMAL olduğunda veri alırken kullanılacak duyarlığı gösterir. [Dbbinding yapılarında](/previous-versions/windows/desktop/ms716845(v=vs.85))`bPrecision` açıklamasına bakın.

*ölçek*<br/>
'ndaki DbType DBTYPE_NUMERIC veya DBTYPE_DECIMAL olduğunda veri alırken kullanılacak ölçeği gösterir. [Dbbinding yapılarında](/previous-versions/windows/desktop/ms716845(v=vs.85))`bScale` açıklamasına bakın.

*'ini*<br/>
Şema satır kümesi GUID 'SI. Şema satır kümelerinin listesi ve bunların GUID 'Leri için *OLE DB Programcı başvurusu* Içindeki [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) öğesine bakın.

#### <a name="remarks"></a>Açıklamalar

Sütunun boyutunu, veri türünü, duyarlılığını, ölçeğini ve şema satır kümesi GUID 'INI belirtmenize olanak tanır.

### <a name="provider_column_entry_length"></a>PROVIDER_COLUMN_ENTRY_LENGTH

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_LENGTH(name, ordinal, size, member)
```

#### <a name="parameters"></a>Parametreler

*ada*<br/>
'ndaki Sütun adı.

*numarasını*<br/>
'ndaki Sütun numarası. Sütun bir yer Işareti sütunu değilse, sütun numarası 0 olmamalı.

*boyutla*<br/>
'ndaki Bayt cinsinden sütun boyutu.

*üyesidir*<br/>
'ndaki Sütun verilerini depolayan `dataClass` üye değişkeni.

#### <a name="remarks"></a>Açıklamalar

Sütun boyutunu belirtmenize izin verir.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry_str"></a>PROVIDER_COLUMN_ENTRY_STR

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_STR(name, ordinal, member)
```

#### <a name="parameters"></a>Parametreler

*ada*<br/>
'ndaki Sütun adı.

*numarasını*<br/>
'ndaki Sütun numarası. Sütun bir yer Işareti sütunu değilse, sütun numarası 0 olmamalı.

*üyesidir*<br/>
'ndaki Verileri depolayan veri sınıfındaki üye değişkeni.

#### <a name="remarks"></a>Açıklamalar

Sütun verilerinin [dbtype_str](/previous-versions/windows/desktop/ms711251(v=vs.85))olduğu kabul edildiğinde bu makroyu kullanın.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry_type_length"></a>PROVIDER_COLUMN_ENTRY_TYPE_LENGTH

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(name, ordinal, dbtype, size, member)
```

#### <a name="parameters"></a>Parametreler

*ada*<br/>
'ndaki Sütun adı.

*numarasını*<br/>
'ndaki Sütun numarası. Sütun bir yer Işareti sütunu değilse, sütun numarası 0 olmamalı.

*DbType*<br/>
'ndaki [DbType](/previous-versions/windows/desktop/ms711251(v=vs.85))içindeki veri türü.

*boyutla*<br/>
'ndaki Bayt cinsinden sütun boyutu.

*üyesidir*<br/>
'ndaki Verileri depolayan veri sınıfındaki üye değişkeni.

#### <a name="remarks"></a>Açıklamalar

[PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md) benzer ancak sütunun veri türünü ve boyutunu belirtmenize de olanak tanır.

### <a name="provider_column_entry_wstr"></a>PROVIDER_COLUMN_ENTRY_WSTR

Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
PROVIDER_COLUMN_ENTRY_WSTR(name, ordinal, member)
```

#### <a name="parameters"></a>Parametreler

*ada*<br/>
'ndaki Sütun adı.

*numarasını*<br/>
'ndaki Sütun numarası. Sütun bir yer Işareti sütunu değilse, sütun numarası 0 olmamalı.

*üyesidir*<br/>
'ndaki Verileri depolayan veri sınıfındaki üye değişkeni.

#### <a name="remarks"></a>Açıklamalar

Sütun verileri boş bir sonlandırılmış Unicode karakter dizesi olduğunda bu makroyu kullanın, [dbtype_wstr](/previous-versions/windows/desktop/ms711251(v=vs.85)).

### <a name="begin_schema_map"></a>BEGIN_SCHEMA_MAP

Bir şema eşlemesinin başlangıcını gösterir.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_SCHEMA_MAP(SchemaClass);
```

#### <a name="parameters"></a>Parametreler

*SchemaClass*<br/>
HARITAYı içeren sınıf. Genellikle bu oturum sınıfı olacaktır.

#### <a name="remarks"></a>Açıklamalar

Şema satır kümeleri hakkında daha fazla bilgi için Windows SDK [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) bölümüne bakın.

### <a name="end_schema_map"></a>END_SCHEMA_MAP

Şema eşlemesinin sonunu belirtir.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_SCHEMA_MAP()
```

#### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [IDBSchemaRowsetImpl Class](../../data/oledb/idbschemarowsetimpl-class.md).

### <a name="schema_entry"></a>SCHEMA_ENTRY

GUID 'ı bir sınıf ile ilişkilendirir.

#### <a name="syntax"></a>Sözdizimi

```cpp
SCHEMA_ENTRY(guid,
   rowsetClass);
```

#### <a name="parameters"></a>Parametreler

*'ini*<br/>
Şema satır kümesi GUID 'SI. Şema satır kümelerinin listesi ve bunların GUID 'Leri için *OLE DB Programcı başvurusu* Içindeki [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) öğesine bakın.

*rowsetClass*<br/>
Şema satır kümesini temsil etmek için oluşturulacak sınıf.

#### <a name="remarks"></a>Açıklamalar

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) daha sonra bir GUID listesi için eşlemeyi sorgulayabilir veya bir GUID verildiyse bir satır kümesi oluşturabilir. `IDBSchemaRowsetImpl` şema satır kümesi, standart `CRowsetImpl`türetilmiş bir sınıfa benzer, ancak aşağıdaki imzaya sahip bir `Execute` yöntemi sağlamalıdır:

```cpp
HRESULT Execute (LONG* pcRowsAffected,
    ULONG cRestrictions,
    const VARIANT* rgRestrictions);
```

Bu `Execute` işlevi satır kümesinin verilerini doldurur. ATL Proje Sihirbazı, *OLE DB Programcı başvurusunda* [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) bölümünde açıklandığı gibi, üç zorunlu OLE DB şemasının her biri için projede üç tane ilk şema satır kümesi oluşturur:

- DBSCHEMA_TABLES

- DBSCHEMA_COLUMNS

- DBSCHEMA_PROVIDER_TYPES

Sihirbaz ayrıca şema eşlemesine üç karşılık gelen giriş ekler. Sağlayıcı oluşturmak için Sihirbazı kullanma hakkında daha fazla bilgi için bkz. [OLE DB Şablon sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md) .

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)<br/>
[OLE DB Sağlayıcı Şablonları Başvurusu](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB Sağlayıcı Şablonları için Makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md)