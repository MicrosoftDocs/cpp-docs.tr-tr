---
title: Kategori makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1fff338bfce32f8233cd58aa7c0790508ce542c
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882889"
---
# <a name="category-macros"></a>Kategori makroları
Bu makrolar kategori eşlemelerini tanımlar.  
  
|||  
|-|-|  
|[BEGIN_CATEGORY_MAP](#begin_category_map)|Kategori harita başlangıcını işaretler.|  
|[END_CATEGORY_MAP](#end_category_map)|Kategori harita sonunu işaretler.|  
|[IMPLEMENTED_CATEGORY](#implemented_category)|COM nesne tarafından uygulanan kategorileri gösterir.|  
|[REQUIRED_CATEGORY](#required_category)|Kapsayıcı COM nesnesi tarafından gerekli olan kategorileri gösterir.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  

##  <a name="begin_category_map"></a>  BEGIN_CATEGORY_MAP  
 Kategori harita başlangıcını işaretler.  
  
```
BEGIN_CATEGORY_MAP(theClass)
```  
  
### <a name="parameters"></a>Parametreler  
 *Sınıfın*  
 [in] Kategori harita içeren sınıfın adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kategori harita COM sınıfı uygulayan ve isteğe bağlı olarak kategorilerini kendi kapsayıcısından gerektirir bileşen kategorilerini belirtmek için kullanılır.  
  
 Ekleme bir [IMPLEMENTED_CATEGORY](#implemented_category) COM sınıfı tarafından uygulanan her kategori için eşleme girişi. Ekleme bir [REQUIRED_CATEGORY](#required_category) uygulamak istemcileri sınıfı gerektiren her kategori için eşleme girişi. Haritayla sonunu işaretlemek [END_CATEGORY_MAP](#end_category_map) makrosu.  
  
 İlişkili bir sınıfı varsa modülü kaydedildiğinde haritada listelenen bileşen kategorileri otomatik olarak kaydedilecek [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) veya [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) .  
  
> [!NOTE]
>  ATL ve standart bileşen kategorilerini yöneticisinin bileşen kategorileri kaydetmek için kullanır. Modül kaydedildiğinde manager sistemde mevcut değilse, kayıt başarılı, ancak bileşen kategorileri o sınıf için kayıtlı değil.  
  
 Bileşen kategorileri hakkında daha fazla bilgi için bkz. [bileşen kategorileri nedir ve nasıl çalıştıkları](http://msdn.microsoft.com/library/windows/desktop/ms694322) Windows SDK.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="end_category_map"></a>  END_CATEGORY_MAP  
 Kategori harita sonunu işaretler.  
  
```
END_CATEGORY_MAP()
```  
  
### <a name="example"></a>Örnek  
 Örneğin bakın [BEGIN_CATEGORY_MAP](#begin_category_map).  
  
##  <a name="implemented_category"></a>  IMPLEMENTED_CATEGORY  
 IMPLEMENTED_CATEGORY makrosu, bileşenin ekleme [kategori harita](#begin_category_map) uygulama tarafından tanımlanan bir kategori olarak kaydedilmelidir belirtmek için *catID* parametresi.  
  
```
IMPLEMENTED_CATEGORY(catID)
```  
  
### <a name="parameters"></a>Parametreler  
 *catID*  
 [in] CatID sabiti veya uygulanan kategori için genel benzersiz tanıtıcısı (GUID) tutan değişken. Adresini *catID* alınır ve eşlemesine eklenir. Stok kategori seçimi için aşağıdaki tabloya bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 İlişkili bir sınıfı varsa modülü kaydedildiğinde haritada listelenen bileşen kategorileri otomatik olarak kaydedilecek [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) veya [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) Makro.  
  
 İstemciler, bir örneğini oluşturmak zorunda kalmadan özelliklerini ve gereksinimlerini belirlemek için sınıf için kayıtlı kategori bilgilerini kullanabilir.  
  
 Bileşen kategorileri hakkında daha fazla bilgi için bkz. [bileşen kategorileri nedir ve nasıl çalıştıkları](http://msdn.microsoft.com/library/windows/desktop/ms694322) Windows SDK.  
  
### <a name="a-selection-of-stock-categories"></a>Stok kategori seçimi  
  
|Açıklama|Sembol|Kayıt defteri GUID|  
|-----------------|------------|-------------------|  
|Komut dosyası için güvenli|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|Güvenli başlatma|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|Basit çerçeve Site kapsamı|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|Basit veri bağlama|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|Gelişmiş veri bağlama|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|Penceresiz denetimleri|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|Internet kullanan nesneler|Bkz: [Internet kullanan nesneler](http://msdn.microsoft.com/library/windows/desktop/ms690561) örnek bir liste için Windows SDK.||  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="required_category"></a>  REQUIRED_CATEGORY  
 Bileşenin REQUIRED_CATEGORY makro Ekle [kategori harita](#begin_category_map) tarafından tanımlanan kategori gerektiren olarak kaydedilmelidir belirtmek için *catID* parametresi.  
  
```
REQUIRED_CATEGORY( catID )
```  
  
### <a name="parameters"></a>Parametreler  
 *catID*  
 [in] CatID sabiti veya genel benzersiz tanıtıcısı (GUID) için gerekli Kategori tutan değişken. Adresini *catID* alınır ve eşlemesine eklenir. Stok kategori seçimi için aşağıdaki tabloya bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 İlişkili bir sınıfı varsa modülü kaydedildiğinde haritada listelenen bileşen kategorileri otomatik olarak kaydedilecek [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) veya [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) Makro.  
  
 İstemciler, bir örneğini oluşturmak zorunda kalmadan özelliklerini ve gereksinimlerini belirlemek için sınıf için kayıtlı kategori bilgilerini kullanabilir. Örneğin, bir kapsayıcı veri bağlamayı destekleyen bir denetimi gerektirebilir. Kapsayıcı özellikleri denetleyen tarafından gerekli kategorileri için kategori Yöneticisi sorgulayarak denetimini barındırmak gerekli olup olmadığını öğrenebilirsiniz. Kapsayıcı gerekli bir özellik desteklemiyorsa, COM nesnesi barındırmak reddedebilir.  
  
 Bir örnek listesi dahil olmak üzere, bileşen kategorileri hakkında daha fazla bilgi için bkz. [bileşen kategorileri nedir ve nasıl çalıştıkları](http://msdn.microsoft.com/library/windows/desktop/ms694322) Windows SDK.  
  
### <a name="a-selection-of-stock-categories"></a>Stok kategori seçimi  
  
|Açıklama|Sembol|Kayıt defteri GUID|  
|-----------------|------------|-------------------|  
|Komut dosyası için güvenli|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|Güvenli başlatma|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|Basit çerçeve Site kapsamı|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|Basit veri bağlama|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|Gelişmiş veri bağlama|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|Penceresiz denetimleri|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|Internet kullanan nesneler|Bkz: [Internet kullanan nesneler](http://msdn.microsoft.com/library/windows/desktop/ms690561) örnek bir liste için Windows SDK.||  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
