---
title: Nesne makroları eklentisini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
dev_langs:
- C++
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6dee93d395a86cc2c06945f9f6f1e84ced6558af
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879413"
---
# <a name="snap-in-object-macros"></a>Ek Bileşen Nesne makroları
Bu makrolar eklentisini uzantılar için destek sağlar.  
  
|||  
|-|-|  
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Ek bileşenini nesnesi için ek uzantı veri sınıfı eşlemesi başlangıcını işaretler.|  
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Ek bileşenini nesnesi için araç harita başlangıcını işaretler.|  
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Bir ek bileşen nesne için ek uzantı veri sınıfı haritanın sonunu işaretler.|  
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Bir ek bileşen nesne için araç harita sonunu işaretler.|  
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Ek uzantı veri sınıfının veri üyesi oluşturur.|  
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Ek uzantı veri sınıfı eklentisini nesne ek uzantı veri sınıfı eşlemeye girer.|  
|[SNAPINMENUID](#snapinmenuid)|Ek bileşenini nesne tarafından kullanılan bağlam menüsü Kimliğini bildirir.|  
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Araç çubuğu eklentisini nesne araç eşlemeye girer.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsnap.h 
   
##  <a name="begin_extension_snapin_nodeinfo_map"></a>  BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP  
 Ek Uzantı sınıfı verilerim başlangıcını işaretler.  
  
```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```  
  
### <a name="parameters"></a>Parametreler  
 *ClassName*  
 [in] Ek uzantı veri sınıfı adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Ek uzantı haritanızı BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP makro başlatın, ek uzantısı veri türlerinin her biri için girişler ekleyin [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) makro ve haritaylatamamlayın[ END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) makrosu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="begin_snapintoolbarid_map"></a>  BEGIN_SNAPINTOOLBARID_MAP  
 Ek Bileşen Nesne için araç Kimliğe eşleme başına bildirir.  
  
```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```  
  
### <a name="parameters"></a>Parametreler  
 *_sınıfı*  
 [in] Ek bileşenini nesne sınıfını belirtir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]  
  
##  <a name="end_extension_snapin_nodeinfo_map"></a>  END_EXTENSION_SNAPIN_NODEINFO_MAP  
 Ek Uzantı sınıfı verilerim sonunu işaretler.  
  
```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ek uzantı haritanızı Başlat [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) makro ile uzantı ek veri türlerinin her biri için girişler ekleyin [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) makrosu, ve harita END_EXTENSION_SNAPIN_NODEINFO_MAP makro tamamlayın.  
  
### <a name="example"></a>Örnek  
 Örneğin bakın [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="end_snapintoolbarid_map"></a>  END_SNAPINTOOLBARID_MAP  
 Araç çubuğu Kimliğe eşleme eklentisini nesnesinin sonuna bildirir.  
  
```
END_SNAPINTOOLBARID_MAP( _class )
```  
  
### <a name="parameters"></a>Parametreler  
 *_sınıfı*  
 [in] Ek bileşenini nesne sınıfını belirtir.  
  
### <a name="example"></a>Örnek  
 Örneğin bakın [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
##  <a name="extension_snapin_dataclass"></a>  EXTENSION_SNAPIN_DATACLASS  
 Bir veri üyesi için ek uzantı veri sınıfı ekler bir **ISnapInItemImpl**-türetilmiş sınıf.  
  
```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```  
  
### <a name="parameters"></a>Parametreler  
 *dataClass*  
 [in] Ek uzantı veri sınıfı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf ayrıca ek uzantı veri sınıfı eşlemeye girilmesi gerekir. Sahip ek uzantısı veri sınıfı eşlemi Başlat [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) makro ek uzantısı veri türlerinin her biri için girişler ekleyin [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)makro ve haritayla tamamlamak [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) makrosu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="extension_snapin_nodeinfo_entry"></a>  EXTENSION_SNAPIN_NODEINFO_ENTRY  
 Ek uzantı veri sınıf uzantısı ek veri sınıfı haritaya ekler.  
  
```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```  
  
### <a name="parameters"></a>Parametreler  
 *dataClass*  
 [in] Ek uzantı veri sınıfı.  
  
### <a name="remarks"></a>Açıklamalar  
 Sahip ek uzantısı veri sınıfı eşlemi Başlat [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) makro EXTENSION_SNAPIN_NODEINFO_ENTRY makrosu sahip ek uzantısı veri türlerinin her biri için girişler ekleyin ve harita tamamlayın ile [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) makrosu.  
  
### <a name="example"></a>Örnek  
 Örneğin bakın [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="snapinmenuid"></a>  SNAPINMENUID  
 Bu makro, bağlam menüsü kaynak ek bileşenini nesnenin bildirmek için kullanın.  
  
```
SNAPINMENUID( id )
```  
  
### <a name="parameters"></a>Parametreler  
 *id*  
 [in] Bağlam menüsünde ek bileşen nesne tanımlar.  
  
##  <a name="snapintoolbarid_entry"></a>  SNAPINTOOLBARID_ENTRY  
 Bir araç Kimliğine ek bileşenini nesnenin araç kimliği eşlemeye girmek için bu makroyu kullanın.  
  
```
SNAPINTOOLBARID_ENTRY( id )
```  
  
### <a name="parameters"></a>Parametreler  
 *id*  
 [in] Araç çubuğu denetimi tanımlar.  
  
### <a name="remarks"></a>Açıklamalar  
 [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) makrosu araç Kimliğe eşleme başlangıcını işaretler; [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) makrosu sonunu işaretler.  
  
### <a name="example"></a>Örnek  
 Örneğin bakın [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
