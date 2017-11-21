---
title: "Kategori makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlGetHexValue
- atlbase/ATL::AtlGetVersion
- atlenc/ATL::AtlHexDecode
- atlenc/ATL::AtlHexDecodeGetRequiredLength
- atlenc/ATL::AtlHexEncode
- atlenc/ATL::AtlHexEncodeGetRequiredLength
- atlenc/ATL::AtlHexValue
- atlenc/ATL::BEncode
- atlenc/ATL::BEncodeGetRequiredLength
- atlenc/ATL::EscapeXML
- atlenc/ATL::GetExtendedChars
- atlenc/ATL::IsExtendedChar
- atlenc/ATL::QEncode
- atlenc/ATL::QEncodeGetRequiredLength
- atlenc/ATL::QPDecode
- atlenc/ATL::QPDecodeGetRequiredLength
- atlenc/ATL::QPEncode
- atlenc/ATL::QPEncodeGetRequiredLength
- atlenc/ATL::UUDecode
- atlenc/ATL::UUDecodeGetRequiredLength
- atlenc/ATL::UUEncode
- atlenc/ATL::UUEncodeGetRequiredLength
dev_langs: C++
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9c9a34bcc230ebbb55867c1412b24f10dc5134d4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="category-macros"></a>Kategori makroları
Bu makroları kategori eşlemeleri tanımlayın.  
  
|||  
|-|-|  
|[BEGIN_CATEGORY_MAP](#begin_category_map)|Kategori harita başlangıcını işaretler.|  
|[END_CATEGORY_MAP](#end_category_map)|Kategori harita sonunu işaretler.|  
|[IMPLEMENTED_CATEGORY](#implemented_category)|COM nesne tarafından uygulanan kategorileri gösterir.|  
|[REQUIRED_CATEGORY](#required_category)|Kapsayıcının COM nesnesi tarafından gerekli olan kategorileri gösterir.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  

##  <a name="begin_category_map"></a>BEGIN_CATEGORY_MAP  
 Kategori harita başlangıcını işaretler.  
  
```
BEGIN_CATEGORY_MAP(theClass)
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 [in] Kategori eşleme içeren sınıfın adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kategori Haritası COM sınıfı uygulayacak ve isteğe bağlı olarak hangi kategoriler, kapsayıcıdan gerektirir bileşen kategorileri belirtmek için kullanılır.  
  
 Ekleme bir [IMPLEMENTED_CATEGORY](#implemented_category) COM sınıfı tarafından uygulanan her kategori için eşleme girişi. Ekleme bir [REQUIRED_CATEGORY](#required_category) uygulamak, istemcileri sınıfı gerektiren her kategori için eşleme girişi. Haritası sonunu işaretlemek [END_CATEGORY_MAP](#end_category_map) makrosu.  
  
 Sınıfın ilişkili bir varsa modülü kaydedildikten sonra eşleme içinde listelenen bileşen kategorileri otomatik olarak kaydedilecek [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) veya [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) .  
  
> [!NOTE]
>  ATL standart bileşen kategorileri Yöneticisi bileşen kategorileri kaydetmek için kullanır. Modül kaydedildiğinde Yöneticisi sistemde mevcut değilse, kayıt başarılı olur, ancak bileşen kategorileri bu sınıf için kayıtlı değil.  
  
 Bileşen kategorileri hakkında daha fazla bilgi için bkz: [bileşen kategorileri nedir ve nasıl çalıştıkları](http://msdn.microsoft.com/library/windows/desktop/ms694322) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="end_category_map"></a>END_CATEGORY_MAP  
 Kategori harita sonunu işaretler.  
  
```
END_CATEGORY_MAP()
```  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [BEGIN_CATEGORY_MAP](#begin_category_map).  
  
##  <a name="implemented_category"></a>IMPLEMENTED_CATEGORY  
 Ekleme bir `IMPLEMENTED_CATEGORY` , bileşenin makrosuna [kategori harita](#begin_category_map) tarafından tanımlanan kategori uygulama olarak kaydedilmelidir belirtmek için `catID` parametresi.  
  
```
IMPLEMENTED_CATEGORY(catID)
```  
  
### <a name="parameters"></a>Parametreler  
 `catID`  
 [in] A **catID** sabit veya değişken uygulanan kategorisi için genel benzersiz tanıtıcısı (GUID) bulunduran. Adresini `catID` alınır ve eşlemesine eklenen. Stok kategorileri seçimi için aşağıdaki tabloya bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıfın ilişkili bir varsa modülü kaydedildikten sonra eşleme içinde listelenen bileşen kategorileri otomatik olarak kaydedilecek [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) veya [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) Makro.  
  
 İstemciler bir örneğini oluşturmak zorunda kalmadan, özellikleri ve gereksinimleri belirlemek için sınıf için kayıtlı kategori bilgilerini kullanabilir.  
  
 Bileşen kategorileri hakkında daha fazla bilgi için bkz: [bileşen kategorileri nedir ve nasıl çalıştıkları](http://msdn.microsoft.com/library/windows/desktop/ms694322) Windows SDK'sındaki.  
  
### <a name="a-selection-of-stock-categories"></a>Stok kategorileri seçimi  
  
|Açıklama|Simgesi|Kayıt defteri GUID|  
|-----------------|------------|-------------------|  
|Komut dosyası için güvenli|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|Başlatma için güvenli|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|Basit çerçeve Site kapsama|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|Basit veri bağlama|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|Gelişmiş veri bağlama|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|Penceresiz denetimleri|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|Internet uyumlu nesneleri|Bkz: [Internet kullanan nesneleri](http://msdn.microsoft.com/library/windows/desktop/ms690561) örnek bir liste için Windows SDK'sındaki.||  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="required_category"></a>REQUIRED_CATEGORY  
 Ekleme bir `REQUIRED_CATEGORY` , bileşenin makrosuna [kategori harita](#begin_category_map) tarafından tanımlanan kategori gerektiren olarak kaydedilmelidir belirtmek için `catID` parametresi.  
  
```
REQUIRED_CATEGORY( catID )
```  
  
### <a name="parameters"></a>Parametreler  
 `catID`  
 [in] A **catID** sabit veya değişken genel benzersiz tanıtıcısı (GUID) için gerekli olan kategorinin bulunduran. Adresini `catID` alınır ve eşlemesine eklenen. Stok kategorileri seçimi için aşağıdaki tabloya bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıfın ilişkili bir varsa modülü kaydedildikten sonra eşleme içinde listelenen bileşen kategorileri otomatik olarak kaydedilecek [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) veya [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) Makro.  
  
 İstemciler bir örneğini oluşturmak zorunda kalmadan, özellikleri ve gereksinimleri belirlemek için sınıf için kayıtlı kategori bilgilerini kullanabilir. Örneğin, bir kapsayıcı veri bağlamayı destekleyen bir denetimi gerektirebilir. Kapsayıcı özellikleri denetleyen tarafından gerekli kategorileri için kategori Yöneticisi sorgulayarak denetimi barındırmak gerekli olup olmadığını öğrenebilirsiniz. Kapsayıcı gerekli bir özellik desteklemiyorsa, COM nesnesi barındırmak reddedebilir.  
  
 Bir örnek listesi dahil olmak üzere bileşen kategorileri hakkında daha fazla bilgi için bkz: [bileşen kategorileri nedir ve nasıl çalıştıkları](http://msdn.microsoft.com/library/windows/desktop/ms694322) Windows SDK'sındaki.  
  
### <a name="a-selection-of-stock-categories"></a>Stok kategorileri seçimi  
  
|Açıklama|Simgesi|Kayıt defteri GUID|  
|-----------------|------------|-------------------|  
|Komut dosyası için güvenli|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|Başlatma için güvenli|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|Basit çerçeve Site kapsama|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|Basit veri bağlama|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|Gelişmiş veri bağlama|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|Penceresiz denetimleri|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|Internet uyumlu nesneleri|Bkz: [Internet kullanan nesneleri](http://msdn.microsoft.com/library/windows/desktop/ms690561) örnek bir liste için Windows SDK'sındaki.||  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
