---
title: "Nesne makroları eklentisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 111fb83ed0eaae936dfa38d7047b2a0c2fb2443b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="snap-in-object-macros"></a>Ek Bileşen Nesne makroları
Bu makroları ek uzantıları için destek sağlar.  
  
|||  
|-|-|  
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Bir ek bileşen nesne için ek bileşeni uzantısı veri sınıf eşlemesi başlangıcını işaretler.|  
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Bir ek bileşenini nesnesi için araç eşleme başlangıcını işaretler.|  
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Ek bileşenini nesnesi için ek bileşeni uzantısı veri sınıf eşlemesi sonunu işaretler.|  
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Ek bileşenini nesnesi için araç harita sonunu işaretler.|  
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Ek bileşenini uzantısını verileri sınıfı için bir veri üyesi oluşturur.|  
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Bir ek bileşeni uzantısı veri sınıfı ek bileşenini nesne eklentisi uzantısını verileri sınıfı eşlemeye girer.|  
|[SNAPINMENUID](#snapinmenuid)|Ek bileşenini nesnesi tarafından kullanılan bağlam menüsü Kimliğini bildirir.|  
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Araç çubuğu eklentisi nesne araç eşlemeye girer.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsnap.h 
   
##  <a name="begin_extension_snapin_nodeinfo_map"></a>BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP  
 Ek bileşeni uzantısı veri sınıf eşlemesi başlangıcını işaretler.  
  
```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```  
  
### <a name="parameters"></a>Parametreler  
 *ClassName*  
 [in] Ek bileşenini uzantısını verileri sınıfının adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Ek bileşeni uzantısı haritanızı Başlat `BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP` makrosu, her ek bileşeni uzantısı veri türleriyle girişleri eklemek [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) makro ve Haritası tamamlamak [END_ EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) makrosu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="begin_snapintoolbarid_map"></a>BEGIN_SNAPINTOOLBARID_MAP  
 Ek bileşenini nesnesi için araç kimliği eşleme başlangıcını bildirir.  
  
```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```  
  
### <a name="parameters"></a>Parametreler  
 `_class`  
 [in] Ek bileşenini nesne sınıfını belirtir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]  
  
##  <a name="end_extension_snapin_nodeinfo_map"></a>END_EXTENSION_SNAPIN_NODEINFO_MAP  
 Ek bileşeni uzantısı veri sınıf eşlemesi sonunu işaretler.  
  
```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ek bileşeni uzantısı haritanızı Başlat [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) makrosu, her uzantı ek bileşenini veri türleriyle girişleri eklemek [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) makro ve Haritası tamamlamak `END_EXTENSION_SNAPIN_NODEINFO_MAP` makrosu.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="end_snapintoolbarid_map"></a>END_SNAPINTOOLBARID_MAP  
 Ek bileşenini nesnesi için araç kimliği eşleme sonuna bildirir.  
  
```
END_SNAPINTOOLBARID_MAP( _class )
```  
  
### <a name="parameters"></a>Parametreler  
 `_class`  
 [in] Ek bileşenini nesne sınıfını belirtir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
##  <a name="extension_snapin_dataclass"></a>EXTENSION_SNAPIN_DATACLASS  
 Ek bileşeni uzantısı veri sınıfı veri üyesi ekleyen bir **ISnapInItemImpl**-türetilmiş sınıf.  
  
```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```  
  
### <a name="parameters"></a>Parametreler  
 `dataClass`  
 [in] Ek bileşenini uzantısını verileri sınıfı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf ayrıca ek bileşenini uzantısını verileri sınıfı eşlemeye girilmesi gerekir. Ek bileşeni uzantısı veri sınıfı eşlemenizi ile başlangıç [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) makrosu, her ek bileşeni uzantısı veri türleriyle girişleri eklemek [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)makro ve Haritası tamamlamak [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) makrosu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="extension_snapin_nodeinfo_entry"></a>EXTENSION_SNAPIN_NODEINFO_ENTRY  
 Bir ek bileşeni uzantısı veri sınıfı ek bileşeni uzantısı veri sınıf eşlemesi ekler.  
  
```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```  
  
### <a name="parameters"></a>Parametreler  
 `dataClass`  
 [in] Ek bileşenini uzantısını verileri sınıfı.  
  
### <a name="remarks"></a>Açıklamalar  
 Ek bileşeni uzantısı veri sınıfı eşlemenizi ile başlangıç [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) makrosu, her ek bileşeni uzantısı veri türleriyle girişleri eklemek `EXTENSION_SNAPIN_NODEINFO_ENTRY` makro ve Haritasıtamamlamak[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) makrosu.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="snapinmenuid"></a>SNAPINMENUID  
 Bağlam menüsü kaynak ek bileşenini nesnesinin bildirmek için bu makrosu kullanın.  
  
```
SNAPINMENUID( id )
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Bağlam menüsünde ek bileşenini nesnesinin tanımlar.  
  
##  <a name="snapintoolbarid_entry"></a>SNAPINTOOLBARID_ENTRY  
 Bir araç kimliği ek bileşenini nesnenin araç kimliği eşlemeye girmek için bu makrosu kullanın.  
  
```
SNAPINTOOLBARID_ENTRY( id )
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Araç çubuğu denetimi tanımlar.  
  
### <a name="remarks"></a>Açıklamalar  
 [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) makrosu araç kimliği harita başlangıcını işaretler; [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) makrosu sonunu işaretler.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
