---
title: Özellik eşleme makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_PROP_MAP
- atlcom/ATL::PROP_DATA_ENTRY
- atlcom/ATL::PROP_ENTRY_TYPE
- atlcom/ATL::PROP_ENTRY_TYPE_EX
- atlcom/ATL::PROP_PAGE
- atlcom/ATL::END_PROP_MAP
dev_langs:
- C++
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 718028385b3910b955c49ab9e0abddf23b443967
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="property-map-macros"></a>Özellik eşleme makroları
Bu makroları özellik eşlemeleri ve girişleri tanımlayın.  
  
|||  
|-|-|  
|[BEGIN_PROP_MAP](#begin_prop_map)|ATL özellik eşlemesi başlangıcını işaretler.|  
|[PROP_DATA_ENTRY](#prop_data_entry)|Uzantı ya da bir ActiveX denetiminin boyutları gösterir.|  
|[PROP_ENTRY_TYPE](#prop_entry_type)|Özellik açıklaması, özellik DISPID ve özellik sayfası CLSID özelliği eşlemeye girer.|  
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|Özellik açıklaması, özellik DISPID, özellik sayfası CLSID, girer ve `IDispatch` IID içine özellik eşlemesi.|  
|[PROP_PAGE](#prop_page)|Özellik sayfası CLSID özelliği eşlemeye girer.|  
|[END_PROP_MAP](#end_prop_map)|ATL özellik eşlemesi sonunu işaretler.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
   
##  <a name="begin_prop_map"></a>  BEGIN_PROP_MAP  
 Nesnenin özellik eşlemesi başlangıcını işaretler.  
  
```
BEGIN_PROP_MAP(theClass)
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 [in] Özellik eşlemesi içeren sınıf belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik açıklamaları, özellik DISPID değerleri, özellik sayfası CLSID, özellik eşlemesi depolar ve `IDispatch` IID'leri. Sınıfları [IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md), [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md), [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), ve [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)özellik eşlemesi almak ve bu bilgileri ayarlamak için kullanın.  
  
 ATL Proje Sihirbazı'yla bir nesne oluşturduğunuzda, sihirbaz boş özellik eşlemesi belirterek oluşturacak `BEGIN_PROP_MAP` arkasından [END_PROP_MAP](#end_prop_map).  
  
 `BEGIN_PROP_MAP` hiçbir uzantı olması gereken şekilde özellik eşlemesi kullanan bir nesne bir kullanıcı arabirimi olmayabilir çünkü bir özellik eşlemesi ölçüde (boyutlar) kaydetmez. Nesne kullanıcı arabirimi ile bir ActiveX denetimi ise, bir uzantı var. Bu durumda, belirtmelisiniz [PROP_DATA_ENTRY](#prop_data_entry) ölçüde sağlamak için özellik eşlemesi içinde.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]  
  
##  <a name="prop_data_entry"></a>  PROP_DATA_ENTRY  
 Uzantı ya da bir ActiveX denetiminin boyutları gösterir.  
  
```
PROP_DATA_ENTRY( szDesc, member, vt)
```    
  
### <a name="parameters"></a>Parametreler  
 `szDesc`  
 [in] Özellik açıklaması.  
  
 `member`  
 [in] Uzantı içeren veri üyesi; Örneğin, `m_sizeExtent`.  
  
 *vt*  
 [in] Özellik değişken türünü belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu kalıcı olmasını belirtilen veri üyesi neden olur.  
  
 ActiveX denetimi oluşturduğunuzda, sihirbaz bu makrosu sonra özellik eşlemesi makrosu ekler. [BEGIN_PROP_MAP](#begin_prop_map) ve özellik eşlemesi makrosu önce [END_PROP_MAP](#end_prop_map).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte, nesne kapsamını ( `m_sizeExtent`) kalıcı.  
  
 [!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]  
  
##  <a name="prop_entry_type"></a>  PROP_ENTRY_TYPE  
 Özellik açıklaması, özellik DISPID ve özellik sayfası CLSID nesnenin özellik eşlemeye girmek için bu makrosu kullanın.  
  
```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```  
  
### <a name="parameters"></a>Parametreler  
 `szDesc`  
 [in] Özellik açıklaması.  
  
 `dispid`  
 [in] Özelliğin DISPID.  
  
 `clsid`  
 [in] İlişkili özellik sayfası CLSID. Özel değerini kullanmak `CLSID_NULL` ilişkili özellik sayfası sahip olmayan bir özellik için.  
  
 `vt`  
 [in] Özelliğin türü.  
  
### <a name="remarks"></a>Açıklamalar  
 `PROP_ENTRY` Makrosu güvenli ve kullanım dışı. İle değiştirilmiştir `PROP_ENTRY_TYPE`.  
  
 [BEGIN_PROP_MAP](#begin_prop_map) makrosu özellik eşlemesi başlangıcını işaretler; [END_PROP_MAP](#end_prop_map) makrosu sonunu işaretler.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [BEGIN_PROP_MAP](#begin_prop_map).  
  
##  <a name="prop_entry_type_ex"></a>  PROP_ENTRY_TYPE_EX  
 Benzer şekilde [PROP_ENTRY_TYPE](#prop_entry_type), ancak belirttiğiniz belirli IID nesnenizin birden çok çift arabirimler destekliyorsa verir.  
  
```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```    
  
### <a name="parameters"></a>Parametreler  
 `szDesc`  
 [in] Özellik açıklaması.  
  
 `dispid`  
 [in] Özelliğin DISPID.  
  
 `clsid`  
 [in] İlişkili özellik sayfası CLSID. Özel değerini kullanmak `CLSID_NULL` ilişkili özellik sayfası sahip olmayan bir özellik için.  
  
 `iidDispatch`  
 [in] Özellik tanımlama çift arabirim IID.  
  
 `vt`  
 [in] Özelliğin türü.  
  
### <a name="remarks"></a>Açıklamalar  
 `PROP_ENTRY_EX` Makrosu güvenli ve kullanım dışı. İle değiştirilmiştir `PROP_ENTRY_TYPE_EX`.  
  
 [BEGIN_PROP_MAP](#begin_prop_map) makrosu özellik eşlemesi başlangıcını işaretler; [END_PROP_MAP](#end_prop_map) makrosu sonunu işaretler.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek girişlerinde grupları `IMyDual1` için bir giriş ve ardından `IMyDual2`. Çift arabirim gruplandırarak performansı iyileştirir.  
  
 [!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]  
  
##  <a name="prop_page"></a>  PROP_PAGE  
 Özellik sayfası CLSID nesnenin özellik eşlemeye girmek için bu makrosu kullanın.  
  
```
PROP_PAGE(clsid)
```  
  
### <a name="parameters"></a>Parametreler  
 `clsid`  
 [in] Özellik sayfası CLSID.  
  
### <a name="remarks"></a>Açıklamalar  
 `PROP_PAGE` benzer [PROP_ENTRY_TYPE](#prop_entry_type), ancak özellik açıklama veya DISPID gerektirmez.  
  
> [!NOTE]
>  CLSID zaten girdiyseniz `PROP_ENTRY_TYPE` veya [PROP_ENTRY_TYPE_EX](#prop_entry_type_ex), olan ek bir giriş yapmak gerekmez `PROP_PAGE`.  
  
 [BEGIN_PROP_MAP](#begin_prop_map) makrosu özellik eşlemesi başlangıcını işaretler; [END_PROP_MAP](#end_prop_map) makrosu sonunu işaretler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]  
  
##  <a name="end_prop_map"></a>  END_PROP_MAP  
 Nesnenin özellik eşlemesi sonunu işaretler.  
  
```
END_PROP_MAP()
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL Proje Sihirbazı'yla bir nesne oluşturduğunuzda, sihirbaz boş özellik eşlemesi belirterek oluşturacak [BEGIN_PROP_MAP](#begin_prop_map) arkasından `END_PROP_MAP`.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [BEGIN_PROP_MAP](#begin_prop_map).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
