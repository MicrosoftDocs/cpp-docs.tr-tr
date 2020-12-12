---
description: 'Daha fazla bilgi edinin: Kategori makroları'
title: Kategori makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CATEGORY_MAP
- atlcom/ATL::END_CATEGORY_MAP
- atlcom/ATL::IMPLEMENTED_CATEGORY
- atlcom/ATL::REQUIRED_CATEGORY
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
ms.openlocfilehash: 31cbef36ca02fb990ba8935915837074d7dd4116
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165088"
---
# <a name="category-macros"></a>Kategori makroları

Bu makrolar kategori eşlemelerini tanımlar.

|Makroya|Açıklama|
|-|-|
|[BEGIN_CATEGORY_MAP](#begin_category_map)|Kategori eşlemesinin başlangıcını işaretler.|
|[END_CATEGORY_MAP](#end_category_map)|Kategori eşlemesinin sonunu işaretler.|
|[IMPLEMENTED_CATEGORY](#implemented_category)|COM nesnesi tarafından uygulanan kategorileri gösterir.|
|[REQUIRED_CATEGORY](#required_category)|COM nesnesi tarafından kapsayıcı için gerekli olan kategorileri gösterir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="begin_category_map"></a><a name="begin_category_map"></a> BEGIN_CATEGORY_MAP

Kategori eşlemesinin başlangıcını işaretler.

```cpp
BEGIN_CATEGORY_MAP(theClass)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
'ndaki Kategori eşlemesini içeren sınıfın adı.

### <a name="remarks"></a>Açıklamalar

Kategori Haritası, COM sınıfının hangi bileşen kategorilerinin uygulanacağını ve kapsayıcısından hangi kategorilerin gerektirdiğini belirtmek için kullanılır.

COM sınıfı tarafından uygulanan her kategori için haritaya bir [IMPLEMENTED_CATEGORY](#implemented_category) girişi ekleyin. Sınıfın istemcilerinin uygulanmasını gerektirdiği her kategori için haritaya bir [REQUIRED_CATEGORY](#required_category) girişi ekleyin. Haritanın sonunu [END_CATEGORY_MAP](#end_category_map) makroyla işaretleyin.

Haritada listelenen Bileşen kategorileri, sınıf ilişkili bir [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) veya [object_entry_non_createable_ex_auto](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto)varsa, modül kaydedildiğinde otomatik olarak kaydedilir.

> [!NOTE]
> ATL, bileşen kategorilerini kaydetmek için standart Bileşen kategorileri yöneticisini kullanır. Modül kaydedildiğinde yönetici sistemde yoksa, kayıt başarılı olur, ancak Bileşen kategorileri bu sınıf için kaydedilmeyecektir.

Bileşen kategorileri hakkında daha fazla bilgi için bkz. [Bileşen kategorileri nedir ve Windows SDK nasıl çalışır](/windows/win32/com/component-categories-and-how-they-work) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

## <a name="end_category_map"></a><a name="end_category_map"></a> END_CATEGORY_MAP

Kategori eşlemesinin sonunu işaretler.

```cpp
END_CATEGORY_MAP()
```

### <a name="example"></a>Örnek

[BEGIN_CATEGORY_MAP](#begin_category_map)için örneğe bakın.

## <a name="implemented_category"></a><a name="implemented_category"></a> IMPLEMENTED_CATEGORY

Bir IMPLEMENTED_CATEGORY makrosunu, *catID* parametresi tarafından tanımlanan kategoriyi uygulayarak kaydedilmesi gerektiğini belirtmek için bileşeninizin [Kategori haritasına](#begin_category_map) ekleyin.

```cpp
IMPLEMENTED_CATEGORY(catID)
```

### <a name="parameters"></a>Parametreler

*CATID*<br/>
'ndaki Uygulanan kategorinin genel benzersiz tanımlayıcısını (GUID) tutan bir CATıD sabiti veya değişkeni. *CatID* adresi alınır ve haritaya eklenir. Stok kategorilerinin seçilmesi için aşağıdaki tabloya bakın.

### <a name="remarks"></a>Açıklamalar

Modülün ilişkili bir [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) veya [object_entry_non_createable_ex_auto](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) makrosu varsa, haritada listelenen Bileşen kategorileri otomatik olarak kaydedilir.

İstemciler, bir örneği oluşturmak zorunda kalmadan özelliklerini ve gereksinimlerini belirlemede sınıf için kayıtlı kategori bilgilerini kullanabilir.

Bileşen kategorileri hakkında daha fazla bilgi için bkz. [Bileşen kategorileri nedir ve Windows SDK nasıl çalışır](/windows/win32/com/component-categories-and-how-they-work) .

### <a name="a-selection-of-stock-categories"></a>Stok kategorilerinin bir seçimi

|Açıklama|Sembol|Kayıt defteri GUID 'SI|
|-----------------|------------|-------------------|
|Betik Için güvenli|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|
|Başlatma Için güvenli|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|
|Basit çerçeve site kapsama|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|Basit veri bağlama|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|Gelişmiş veri bağlama|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|Penceresiz denetimler|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|Internet-Aware nesneleri|Örnek bir liste için Windows SDK [Internet 'e duyarlı nesneleri](/windows/win32/com/internet-aware-objects) inceleyin.||

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

## <a name="required_category"></a><a name="required_category"></a> REQUIRED_CATEGORY

Bir REQUIRED_CATEGORY makrosunu, *catID* parametresi tarafından tanımlanan kategorinin gerektirdiği şekilde kaydedilmesi gerektiğini belirtmek için bileşeninizin [Kategori haritasına](#begin_category_map) ekleyin.

```cpp
REQUIRED_CATEGORY( catID )
```

### <a name="parameters"></a>Parametreler

*CATID*<br/>
'ndaki Gerekli kategorinin genel benzersiz tanımlayıcısını (GUID) tutan bir CATıD sabiti veya değişkeni. *CatID* adresi alınır ve haritaya eklenir. Stok kategorilerinin seçilmesi için aşağıdaki tabloya bakın.

### <a name="remarks"></a>Açıklamalar

Modülün ilişkili bir [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) veya [object_entry_non_createable_ex_auto](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) makrosu varsa, haritada listelenen Bileşen kategorileri otomatik olarak kaydedilir.

İstemciler, bir örneği oluşturmak zorunda kalmadan özelliklerini ve gereksinimlerini belirlemede sınıf için kayıtlı kategori bilgilerini kullanabilir. Örneğin, bir Denetim kapsayıcının veri bağlamayı desteklemesini gerektirebilir. Kapsayıcı, denetim için gereken kategorilerin kategori yöneticisini sorgulayarak, denetimi barındırmak için gereken yeteneklere sahip olup olmadığını bulabilir. Kapsayıcı gerekli bir özelliği desteklemiyorsa COM nesnesini barındırmak reddedebilir.

Örnek liste dahil Bileşen kategorileri hakkında daha fazla bilgi için bkz. [Bileşen kategorileri nedir ve Windows SDK nasıl çalışır](/windows/win32/com/component-categories-and-how-they-work) .

### <a name="a-selection-of-stock-categories"></a>Stok kategorilerinin bir seçimi

|Açıklama|Sembol|Kayıt defteri GUID 'SI|
|-----------------|------------|-------------------|
|Betik Için güvenli|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|
|Başlatma Için güvenli|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|
|Basit çerçeve site kapsama|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|Basit veri bağlama|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|Gelişmiş veri bağlama|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|Penceresiz denetimler|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|Internet-Aware nesneleri|Örnek bir liste için Windows SDK [Internet 'e duyarlı nesneleri](/windows/win32/com/internet-aware-objects) inceleyin.||

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
