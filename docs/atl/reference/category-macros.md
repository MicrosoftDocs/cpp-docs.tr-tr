---
title: Kategori Makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CATEGORY_MAP
- atlcom/ATL::END_CATEGORY_MAP
- atlcom/ATL::IMPLEMENTED_CATEGORY
- atlcom/ATL::REQUIRED_CATEGORY
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
ms.openlocfilehash: 1d8bbae4608aa661bbc612604f7d85855f325f5f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321594"
---
# <a name="category-macros"></a>Kategori Makroları

Bu makrolar kategori eşlemlerini tanımlar.

|||
|-|-|
|[BEGIN_CATEGORY_MAP](#begin_category_map)|Kategori haritasının başlangıcını işaretler.|
|[END_CATEGORY_MAP](#end_category_map)|Kategori haritasının sonunu işaretler.|
|[IMPLEMENTED_CATEGORY](#implemented_category)|COM nesnesi tarafından uygulanan kategorileri gösterir.|
|[REQUIRED_CATEGORY](#required_category)|COM nesnesi tarafından kapsayıcının gerekli olduğu kategorileri gösterir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="begin_category_map"></a><a name="begin_category_map"></a>BEGIN_CATEGORY_MAP

Kategori haritasının başlangıcını işaretler.

```
BEGIN_CATEGORY_MAP(theClass)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
[içinde] Kategori eşlemini içeren sınıfın adı.

### <a name="remarks"></a>Açıklamalar

Kategori eşlemi, COM sınıfının hangi bileşen kategorilerini uygulayacağını ve kapsayıcısından hangi kategorileri gerektireceğini belirtmek için kullanılır.

COM sınıfı tarafından uygulanan her kategori için haritaya [IMPLEMENTED_CATEGORY](#implemented_category) girişi ekleyin. Sınıfın istemcilerinin uygulaması gereken her kategori için haritaya [REQUIRED_CATEGORY](#required_category) bir giriş ekleyin. Haritanın sonunu [END_CATEGORY_MAP](#end_category_map) makrosuyla işaretleyin.

Haritada listelenen bileşen kategorileri, sınıfın ilişkili bir [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) veya [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto)varsa, modül kaydedildiğinde otomatik olarak kaydedilir.

> [!NOTE]
> ATL, bileşen kategorilerini kaydetmek için standart bileşen kategorileri yöneticisini kullanır. Modül kaydedildiğinde yönetici sistemde yoksa, kayıt başarılı olur, ancak bileşen kategorileri o sınıf için kaydedilmez.

Bileşen kategorileri hakkında daha fazla bilgi için, [Bileşen Kategorileri nedir ve](/windows/win32/com/component-categories-and-how-they-work) Windows SDK'da nasıl çalışırlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

## <a name="end_category_map"></a><a name="end_category_map"></a>END_CATEGORY_MAP

Kategori haritasının sonunu işaretler.

```
END_CATEGORY_MAP()
```

### <a name="example"></a>Örnek

[BEGIN_CATEGORY_MAP](#begin_category_map)için örneğe bakın.

## <a name="implemented_category"></a><a name="implemented_category"></a>IMPLEMENTED_CATEGORY

*CatID* parametresi tarafından tanımlanan kategoriyi uygularken kaydedilmesi gerektiğini belirtmek için bileşeninizin [kategori haritasına](#begin_category_map) IMPLEMENTED_CATEGORY bir makro ekleyin.

```
IMPLEMENTED_CATEGORY(catID)
```

### <a name="parameters"></a>Parametreler

*Catıd*<br/>
[içinde] Uygulanan kategori için genel olarak benzersiz tanımlayıcıyı (GUID) tutan CATID sabiti veya değişkeni. *CatID* adresi alınacak ve haritaya eklenecektir. Stok kategorileri seçimi için aşağıdaki tabloya bakın.

### <a name="remarks"></a>Açıklamalar

Haritada listelenen bileşen kategorileri, sınıfın ilişkili bir [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) veya [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) makrosu varsa, modül kaydedildiğinde otomatik olarak kaydedilir.

İstemciler, bir örnek oluşturmak zorunda kalmadan yeteneklerini ve gereksinimlerini belirlemek için sınıf için kayıtlı kategori bilgilerini kullanabilir.

Bileşen kategorileri hakkında daha fazla bilgi için, [Bileşen Kategorileri nedir ve](/windows/win32/com/component-categories-and-how-they-work) Windows SDK'da nasıl çalışırlar.

### <a name="a-selection-of-stock-categories"></a>Stok Kategorilerinden Seçmeler

|Açıklama|Sembol|Kayıt DEFTERI GUID|
|-----------------|------------|-------------------|
|Komut Dosyası Için Güvenli|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|
|Başlatma için güvenli|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|
|Basit Çerçeve Site Çevreleme|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|Basit Veri Bağlama|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|Gelişmiş Veri Bağlama|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|Penceresiz Denetimler|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|Internet'e Duyarlı Nesneler|Örnek bir liste için Windows SDK'daki [Internet Farkında Nesnelere](/windows/win32/com/internet-aware-objects) bakın.||

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

## <a name="required_category"></a><a name="required_category"></a>REQUIRED_CATEGORY

*CatID* parametresi tarafından tanımlanan kategoriyi gerektiren olarak kaydedilmesi gerektiğini belirtmek için bileşeninizin [kategori haritasına](#begin_category_map) bir REQUIRED_CATEGORY makro ekleyin.

```
REQUIRED_CATEGORY( catID )
```

### <a name="parameters"></a>Parametreler

*Catıd*<br/>
[içinde] CatID sabiti veya değişkeni, gerekli kategori için genel olarak benzersiz tanımlayıcıyı (GUID) tutar. *CatID* adresi alınacak ve haritaya eklenecektir. Stok kategorileri seçimi için aşağıdaki tabloya bakın.

### <a name="remarks"></a>Açıklamalar

Haritada listelenen bileşen kategorileri, sınıfın ilişkili bir [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) veya [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) makrosu varsa, modül kaydedildiğinde otomatik olarak kaydedilir.

İstemciler, bir örnek oluşturmak zorunda kalmadan yeteneklerini ve gereksinimlerini belirlemek için sınıf için kayıtlı kategori bilgilerini kullanabilir. Örneğin, bir denetim, bir kapsayıcı destek veri bağlama gerektirebilir. Kapsayıcı, bu denetimin gerektirdiği kategoriler için kategori yöneticisini sorgulayarak denetimi barındırmak için gereken özelliklere sahip olup olmadığını öğrenebilir. Kapsayıcı gerekli bir özelliği desteklemiyorsa, COM nesnesini barındırmayı reddedebilir.

Örnek liste de dahil olmak üzere bileşen kategorileri hakkında daha fazla bilgi için, [Bileşen Kategorileri nedir ve](/windows/win32/com/component-categories-and-how-they-work) Windows SDK'da nasıl çalışırlar bakın.

### <a name="a-selection-of-stock-categories"></a>Stok Kategorilerinden Seçmeler

|Açıklama|Sembol|Kayıt DEFTERI GUID|
|-----------------|------------|-------------------|
|Komut Dosyası Için Güvenli|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|
|Başlatma için güvenli|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|
|Basit Çerçeve Site Çevreleme|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|Basit Veri Bağlama|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|Gelişmiş Veri Bağlama|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|Penceresiz Denetimler|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|Internet'e Duyarlı Nesneler|Örnek bir liste için Windows SDK'daki [Internet Farkında Nesnelere](/windows/win32/com/internet-aware-objects) bakın.||

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
