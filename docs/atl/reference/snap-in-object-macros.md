---
description: 'Hakkında daha fazla bilgi edinin: Snap-In nesne makroları'
title: Nesne makrolarını Snap-In
ms.date: 11/04/2016
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
ms.openlocfilehash: d775c1d5f66f16fb63b9a7adeda2bc8e74046acf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157691"
---
# <a name="snap-in-object-macros"></a>Nesne makrolarını Snap-In

Bu makrolar ek bileşen uzantıları için destek sağlar.

|Ad|Açıklama|
|-|-|
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Snap-In nesnesi için ek bileşen uzantısı veri sınıfı eşlemesinin başlangıcını işaretler.|
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Snap-In nesnesi için araç çubuğu eşlemesinin başlangıcını işaretler.|
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Snap-In nesnesi için ek bileşen uzantısı veri sınıfı eşlemesinin sonunu işaretler.|
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Snap-In nesne için araç çubuğu eşlemesinin sonunu işaretler.|
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Ek bileşen uzantısının veri sınıfı için bir veri üyesi oluşturur.|
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Snap-In nesnesinin ek bileşen uzantısı veri sınıfı eşlemesine bir ek bileşen uzantısı veri sınıfı girer.|
|[SNAPıNMENUID](#snapinmenuid)|Snap-In nesnesi tarafından kullanılan bağlam menüsünün KIMLIĞINI bildirir.|
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Snap-In nesnesinin araç çubuğu eşlemesine bir araç çubuğu girer.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsnap. h

## <a name="begin_extension_snapin_nodeinfo_map"></a><a name="begin_extension_snapin_nodeinfo_map"></a> BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP

Ek bileşen uzantısı veri sınıfı eşlemesinin başlangıcını işaretler.

```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```

### <a name="parameters"></a>Parametreler

*sınıf*<br/>
'ndaki Ek bileşen uzantısı veri sınıfının adı.

### <a name="remarks"></a>Açıklamalar

Ek bileşen uzantınızı BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP makroyla başlatın, ek bileşen uzantısı veri türlerinizin her biri için [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) makrosunu ekleyerek giriş ekleyin ve [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) makroyla Haritayı doldurun.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="begin_snapintoolbarid_map"></a><a name="begin_snapintoolbarid_map"></a> BEGIN_SNAPINTOOLBARID_MAP

Snap-In nesnesi için araç çubuğu KIMLIĞI eşlemesinin başlangıcını bildirir.

```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```

### <a name="parameters"></a>Parametreler

*_class*<br/>
'ndaki Snap-In nesne sınıfını belirtir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]

## <a name="end_extension_snapin_nodeinfo_map"></a><a name="end_extension_snapin_nodeinfo_map"></a> END_EXTENSION_SNAPIN_NODEINFO_MAP

Ek bileşen uzantısı veri sınıfı eşlemesinin sonunu işaretler.

```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```

### <a name="remarks"></a>Açıklamalar

Ek bileşen uzantınızı [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) makroyla başlatın, uzantı ek bileşeni veri türlerinizin her biri için [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) makroyla giriş ekleyin ve END_EXTENSION_SNAPIN_NODEINFO_MAP makrosu ile Haritayı doldurun.

### <a name="example"></a>Örnek

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)için örneğe bakın.

## <a name="end_snapintoolbarid_map"></a><a name="end_snapintoolbarid_map"></a> END_SNAPINTOOLBARID_MAP

Snap-In nesnesi için araç çubuğu KIMLIĞI eşlemesinin sonunu bildirir.

```
END_SNAPINTOOLBARID_MAP( _class )
```

### <a name="parameters"></a>Parametreler

*_class*<br/>
'ndaki Snap-In nesne sınıfını belirtir.

### <a name="example"></a>Örnek

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)için örneğe bakın.

## <a name="extension_snapin_dataclass"></a><a name="extension_snapin_dataclass"></a> EXTENSION_SNAPIN_DATACLASS

**Inapinitemımpl**-Derived sınıfı için ek bileşen uzantısı veri sınıfına bir veri üyesi ekler.

```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```

### <a name="parameters"></a>Parametreler

*dataClass*<br/>
'ndaki Ek bileşen uzantısının veri sınıfı.

### <a name="remarks"></a>Açıklamalar

Bu sınıf Ayrıca bir ek bileşen uzantısı veri sınıfı eşlemesine de girilmelidir. Ek bileşen uzantısı veri sınıfı eşlemenizi [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) makroyla başlatın, ek bileşen uzantısı veri türlerinizin her biri için [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) makroyla giriş ekleyin ve [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) makrosu ile Haritayı doldurun.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="extension_snapin_nodeinfo_entry"></a><a name="extension_snapin_nodeinfo_entry"></a> EXTENSION_SNAPIN_NODEINFO_ENTRY

Ek bileşen uzantısı veri sınıfı eşlemesine bir ek bileşen uzantısı veri sınıfı ekler.

```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```

### <a name="parameters"></a>Parametreler

*dataClass*<br/>
'ndaki Ek bileşen uzantısının veri sınıfı.

### <a name="remarks"></a>Açıklamalar

Ek bileşen uzantısı veri sınıfı eşlemenizi [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) makroyla başlatın, ek bileşen uzantısı veri türlerinizin her biri için EXTENSION_SNAPIN_NODEINFO_ENTRY makroyla giriş ekleyin ve [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) makrosu ile Haritayı doldurun.

### <a name="example"></a>Örnek

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)için örneğe bakın.

## <a name="snapinmenuid"></a><a name="snapinmenuid"></a> SNAPıNMENUID

Snap-In nesnenin bağlam menüsü kaynağını bildirmek için bu makroyu kullanın.

```
SNAPINMENUID( id )
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Snap-In nesnesinin bağlam menüsünü tanımlar.

## <a name="snapintoolbarid_entry"></a><a name="snapintoolbarid_entry"></a> SNAPINTOOLBARID_ENTRY

Snap-In nesnenin araç çubuğu KIMLIĞI eşlemesine bir araç çubuğu KIMLIĞI girmek için bu makroyu kullanın.

```
SNAPINTOOLBARID_ENTRY( id )
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Araç çubuğu denetimini tanımlar.

### <a name="remarks"></a>Açıklamalar

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) makro, araç çubuğu kimliği haritasının başlangıcını belirtir; [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) makro bitişi işaretler.

### <a name="example"></a>Örnek

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
