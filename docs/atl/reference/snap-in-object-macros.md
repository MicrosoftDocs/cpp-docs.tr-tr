---
title: Ek Bileşen Nesne Makroları
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
ms.openlocfilehash: 6a57cdb3c9b6a4448bc954ff754ac9b18fa0b393
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325867"
---
# <a name="snap-in-object-macros"></a>Ek Bileşen Nesne Makroları

Bu makrolar, snap-in uzantıları için destek sağlar.

|||
|-|-|
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Snap-In nesnesi için snap-in uzantısı veri sınıfı haritasının başlangıcını işaretler.|
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Snap-In nesnesi için araç çubuğu haritasının başlangıcını işaretler.|
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Snap-In nesnesi için snap-in uzantısı veri sınıfı haritasının sonunu işaretler.|
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Snap-In nesnesi için araç çubuğu haritasının sonunu işaretler.|
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Snap-in uzantısı veri sınıfı için bir veri üyesi oluşturur.|
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Snap-In nesnesinin snap-in uzantısı veri sınıfı haritasına bir tutturma uzantısı veri sınıfı girer.|
|[SNAPINMENUID](#snapinmenuid)|Snap-In nesnesi tarafından kullanılan bağlam menüsünün kimliğini bildirir.|
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Snap-In nesnesinin araç çubuğuna bir araç çubuğu girer.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsnap.h

## <a name="begin_extension_snapin_nodeinfo_map"></a><a name="begin_extension_snapin_nodeinfo_map"></a>BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP

Snap-in uzantısı veri sınıfı haritasının başlangıcını işaretler.

```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```

### <a name="parameters"></a>Parametreler

*Classname*<br/>
[içinde] Snap-in uzantısı veri sınıfının adı.

### <a name="remarks"></a>Açıklamalar

BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP makrosuyla giriş uzantısı haritanızı başlatın, [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) makroile snap-in uzantılı veri türlerinin her biri için girişler ekleyin ve [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) makrosuyla haritayı tamamlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="begin_snapintoolbarid_map"></a><a name="begin_snapintoolbarid_map"></a>BEGIN_SNAPINTOOLBARID_MAP

Snap-In nesnesi için araç çubuğu kimlik haritasının başlangıcını bildirir.

```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```

### <a name="parameters"></a>Parametreler

*_class*<br/>
[içinde] Snap-In nesnesi sınıfını belirtir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]

## <a name="end_extension_snapin_nodeinfo_map"></a><a name="end_extension_snapin_nodeinfo_map"></a>END_EXTENSION_SNAPIN_NODEINFO_MAP

Snap-in uzantısı veri sınıfı haritasının sonunu işaretler.

```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```

### <a name="remarks"></a>Açıklamalar

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) makrosuyla giriş uzantısı haritanızı başlatın, [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) makroile uzantılı veri türlerinin her biri için girişler ekleyin ve END_EXTENSION_SNAPIN_NODEINFO_MAP makrosuyla haritayı tamamlayın.

### <a name="example"></a>Örnek

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)için örneğe bakın.

## <a name="end_snapintoolbarid_map"></a><a name="end_snapintoolbarid_map"></a>END_SNAPINTOOLBARID_MAP

Snap-In nesnesi için araç çubuğu kimlik eşleminin sonunu bildirir.

```
END_SNAPINTOOLBARID_MAP( _class )
```

### <a name="parameters"></a>Parametreler

*_class*<br/>
[içinde] Snap-In nesnesi sınıfını belirtir.

### <a name="example"></a>Örnek

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)için örneğe bakın.

## <a name="extension_snapin_dataclass"></a><a name="extension_snapin_dataclass"></a>EXTENSION_SNAPIN_DATACLASS

**ISnapInItemImpl**türetilmiş bir sınıf için snap-in uzantısı veri sınıfına bir veri üyesi ekler.

```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```

### <a name="parameters"></a>Parametreler

*dataClass*<br/>
[içinde] Snap-in uzantısı veri sınıfı.

### <a name="remarks"></a>Açıklamalar

Bu sınıf da bir snap-in uzantısı veri sınıfı eşlemesi girilmelidir. [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) makrosuyla giriş uzantısı veri sınıfı haritanızı başlatın, [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) makroile birlikte giriş lerinizin her biri için girişler ekleyin ve [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) makrosuyla haritayı tamamlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="extension_snapin_nodeinfo_entry"></a><a name="extension_snapin_nodeinfo_entry"></a>EXTENSION_SNAPIN_NODEINFO_ENTRY

Snap-in uzantısı veri sınıfı haritasına bir yapışma uzantısı veri sınıfı ekler.

```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```

### <a name="parameters"></a>Parametreler

*dataClass*<br/>
[içinde] Snap-in uzantısı veri sınıfı.

### <a name="remarks"></a>Açıklamalar

BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP makrosuyla giriş uzantısı veri [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) sınıfı haritanızı başlatın, EXTENSION_SNAPIN_NODEINFO_ENTRY makroile birlikte snap-in uzantısı veri türlerinin her biri için girişler ekleyin ve [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) makrosuyla haritayı tamamlayın.

### <a name="example"></a>Örnek

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)için örneğe bakın.

## <a name="snapinmenuid"></a><a name="snapinmenuid"></a>SNAPINMENUID

Snap-In nesnesinin bağlam menüsü kaynağını bildirmek için bu makroyu kullanın.

```
SNAPINMENUID( id )
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] Snap-In nesnesinin bağlam menüsünü tanımlar.

## <a name="snapintoolbarid_entry"></a><a name="snapintoolbarid_entry"></a>SNAPINTOOLBARID_ENTRY

Snap-In nesnesinin araç çubuğu kimlik haritasına bir araç çubuğu kimliği girmek için bu makroyu kullanın.

```
SNAPINTOOLBARID_ENTRY( id )
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] Araç çubuğu denetimini tanımlar.

### <a name="remarks"></a>Açıklamalar

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) makrosu araç çubuğu kimlik haritasının başlangıcını işaretler; [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) makro sonunu işaretler.

### <a name="example"></a>Örnek

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
