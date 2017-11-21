---
title: "Olay eşlemeleri havuzu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.maps
dev_langs: C++
helpviewer_keywords: event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8319dc6cee5b5dc5c5f0ede2d8d9a9913efb7a4a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="event-sink-maps"></a>Olay İç Havuz Eşlemeleri
Katıştırılmış OLE denetimi bir olay başlatıldığında, denetimin kapsayıcı "MFC tarafından sağlanan bir olay havuz haritası," olarak adlandırılan bir mekanizma kullanarak olayı alır. Bu olay havuz eşlemesi her belirli olay yanı sıra bu olayların parametreleri için işleyici işlevleri belirler. Olay iç havuz eşlemeleri hakkında daha fazla bilgi için bkz: [ActiveX denetimi kapsayıcıları](../../mfc/activex-control-containers.md).  
  
### <a name="event-sink-maps"></a>Olay İç Havuz Eşlemeleri  
  
|||  
|-|-|  
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|Bir olay havuz eşlemesi tanımını başlatır.|  
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|Bir olay havuz eşlemesi bildirir.|  
|[END_EVENTSINK_MAP](#end_eventsink_map)|Bir olay havuz eşlemesi tanımını sona erer.|  
|[ON_EVENT](#on_event)|Belirli bir olay için bir olay işleyicisini tanımlar.|  
|[ON_EVENT_RANGE](#on_event_range)|OLE denetimleri kümesinden harekete belirli bir olay için bir olay işleyicisini tanımlar.|  
|[ON_EVENT_REFLECT](#on_event_reflect)|Denetimin kapsayıcı tarafından işlenen önce denetim tarafından tetiklenen olayları alır.|  
|[ON_PROPNOTIFY](#on_propnotify)|OLE denetimi özelliği bildirimleri işlemek için bir işleyici tanımlar.|  
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|OLE denetimleri kümesinden özelliği bildirimleri işleme için bir işleyici tanımlar.|  
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|Denetimin kapsayıcı tarafından işlenen önce denetim tarafından gönderilen özellik bildirimlerini alır.|  
  
##  <a name="begin_eventsink_map"></a>BEGIN_EVENTSINK_MAP  
 Olay iç havuz haritanızı tanımını başlar.  
  
```   
BEGIN_EVENTSINK_MAP(theClass, baseClass)  
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Olay iç havuz bu Harita Denetim sınıfın adını belirtir.  
  
 `baseClass`  
 Temel sınıfını adını belirtir `theClass`.  
  
### <a name="remarks"></a>Açıklamalar  
 Olay iç havuz Haritası sınıfınız için üye işlevleri tanımlar uygulaması (.cpp) dosyasına Başlat `BEGIN_EVENTSINK_MAP` makrosu, ardından bildirilmesini her olay için makrosu girişleri ekleyin ve olay havuz Haritası tamamlamak `END_EVENTSINK_MAP` makrosu.  
  
 Olay iç havuz eşlemeleri ve OLE denetimi kapsayıcıları hakkında daha fazla bilgi için bkz: [ActiveX denetimi kapsayıcıları](../../mfc/activex-control-containers.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="declare_eventsink_map"></a>DECLARE_EVENTSINK_MAP  
 OLE kapsayıcı, kapsayıcı olarak bildirilecek olayları belirtmek için bir olay havuz eşlemesi sağlayabilir.  
  
```   
DECLARE_EVENTSINK_MAP()   
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `DECLARE_EVENTSINK_MAP` makrosu sınıf bildiriminin sonundaki. Ardından. Üye tanımlayan CPP dosyası işlevler için sınıf, kullanın `BEGIN_EVENTSINK_MAP` makrosu, makrosu girişleri, bildirim almak için olayların her biri için ve `END_EVENTSINK_MAP` olay havuz listesinin sonuna bildirmek için makrosu.  
  
 Olay iç havuz eşlemeleri hakkında daha fazla bilgi için bkz: [ActiveX denetimi kapsayıcıları](../../mfc/activex-control-containers.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="end_eventsink_map"></a>END_EVENTSINK_MAP  
 Olay iç havuz haritanızı tanımını sona erer.  
  
```   
END_EVENTSINK_MAP()   
```  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="on_event"></a>ON_EVENT  
 Kullanım `ON_EVENT` bir olay için bir olay işleyicisi işlevi tanımlamak için makrosu OLE denetimi tarafından tetiklenir.  
  
```   
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Bu olay havuzu harita sınıfın ait olduğu.  
  
 `id`  
 OLE denetim denetim kimliği.  
  
 `dispid`  
 Denetim tarafından tetiklenen olay gönderme kimliği.  
  
 `pfnHandler`  
 Olay işleme üye işlev işaretçisi. Bu işlev olmalıdır bir **BOOL** dönüş türü ve olayın parametreleriyle eşleşen parametre türleri (bkz: `vtsParams`). İşlev döndürmelidir **TRUE** olay işlenmediyse belirtmek için **FALSE**.  
  
 `vtsParams`  
 Bir dizi **VTS_** sabitleri olayı için parametre türlerini belirtir. Gönderme harita girişler gibi kullanılan aynı sabitleri bunlar `DISP_FUNCTION`.  
  
### <a name="remarks"></a>Açıklamalar  
 `vtsParams` Değişken değeri boşlukla ayrılmış bir liste değerleri **VTS_** sabitleri. Bir veya daha fazla (değil virgüller) boşluklarla ayrılmış bu değerleri işlev parametre listesi belirtir. Örneğin:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 arkasından kısa bir tamsayı içeren bir liste belirten bir **BOOL**.  
  
 Bir listesi için **VTS_** sabitleri, bkz: [EVENT_CUSTOM](event-maps.md#event_custom).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="on_event_range"></a>ON_EVENT_RANGE  
 Kullanım `ON_EVENT_RANGE` bir olay için bir olay işleyicisi işlevi tanımlamak için makrosu harekete bitişik olarak kimlikleri aralığı içindeki bir denetim kimliği sahip herhangi bir OLE denetimi tarafından.  
  
```   
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)   
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Bu olay havuzu harita sınıfın ait olduğu.  
  
 `idFirst`  
 Aralıktaki ilk OLE denetim denetim kimliği.  
  
 `idLast`  
 Aralığın son OLE denetimindeki denetim kimliği.  
  
 `dispid`  
 Denetim tarafından tetiklenen olay gönderme kimliği.  
  
 `pfnHandler`  
 Olay işleme üye işlev işaretçisi. Bu işlev olmalıdır bir **BOOL** dönüş türü, ilk parametre türü **UINT** (için denetim kimliği) ve olayın parametreleriyle eşleşen ek parametre türleri (bkz: `vtsParams`). İşlev döndürmelidir **TRUE** olay işlenmediyse belirtmek için **FALSE**.  
  
 `vtsParams`  
 Bir dizi **VTS_** sabitleri olayı için parametre türlerini belirtir. İlk sabit değer türü olmalıdır **VTS_I4**, denetim kimliği için Gönderme harita girişler gibi kullanılan aynı sabitleri bunlar `DISP_FUNCTION`.  
  
### <a name="remarks"></a>Açıklamalar  
 `vtsParams` Değişken değeri boşlukla ayrılmış bir liste değerleri **VTS_** sabitleri. Bir veya daha fazla (değil virgüller) boşluklarla ayrılmış bu değerleri işlev parametre listesi belirtir. Örneğin:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 arkasından kısa bir tamsayı içeren bir liste belirten bir **BOOL**.  
  
 Bir listesi için **VTS_** sabitleri, bkz: [EVENT_CUSTOM](event-maps.md#event_custom).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, üç denetimleri için uygulanan MouseDown olayı için bir olay işleyicisi gösterir ( `IDC_MYCTRL1` aracılığıyla `IDC_MYCTRL3`). Olay işleyici işlevi `OnRangeMouseDown`, iletişim kutusu sınıfı üstbilgi dosyasında bildirilen ( `CMyDlg`) olarak:  
  
 [!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]  
  
 Aşağıdaki kodu iletişim kutusu sınıfı uygulama dosyasında tanımlanır.  
  
 [!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="on_event_reflect"></a>ON_EVENT_REFLECT  
 `ON_EVENT_REFLECT` Olay bir OLE denetimin sarmalayıcı sınıfı, havuz haritasını kullanıldığında makrosu denetimin kapsayıcı tarafından işlenen önce denetim tarafından tetiklenen olayları alır.  
  
```   
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Bu olay havuzu harita sınıfın ait olduğu.  
  
 DISPID  
 Denetim tarafından tetiklenen olay gönderme kimliği.  
  
 `pfnHandler`  
 Olay işleme üye işlev işaretçisi. Bu işlev olmalıdır bir **BOOL** dönüş türü ve olayın parametreleriyle eşleşen parametre türleri (bkz: `vtsParams`). İşlev döndürmelidir **TRUE** olay işlenmediyse belirtmek için **FALSE**.  
  
 `vtsParams`  
 Bir dizi **VTS_** sabitleri olayı için parametre türlerini belirtir. Gönderme harita girişler gibi kullanılan aynı sabitleri bunlar `DISP_FUNCTION`.  
  
### <a name="remarks"></a>Açıklamalar  
 `vtsParams` Değişken değeri boşlukla ayrılmış bir liste değerleri **VTS_** sabitleri.  
  
 Bir veya daha fazla (değil virgüller) boşluklarla ayrılmış bu değerleri işlev parametre listesi belirtir. Örneğin:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 arkasından kısa bir tamsayı içeren bir liste belirten bir **BOOL**.  
  
 Bir listesi için **VTS_** sabitleri, bkz: [EVENT_CUSTOM](event-maps.md#event_custom).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="on_propnotify"></a>ON_PROPNOTIFY  
 Kullanım `ON_PROPNOTIFY` OLE denetimindeki özellik bildirimlerini işleme için bir olay havuz eşleme girişi tanımlamak için makrosu.  
  
```   
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Bu olay havuzu harita sınıfın ait olduğu.  
  
 `id`  
 OLE denetim denetim kimliği.  
  
 `dispid`  
 Bildirim söz konusu özellik gönderme kimliği.  
  
 `pfnRequest`  
 İşleme bir üye işlev işaretçisi **OnRequestEdit** bu özellik için bildirim. Bu işlev olmalıdır bir **BOOL** dönüş türü ve **BOOL\***  parametresi. Bu işlev parametre ayarlamalıdır **TRUE** özelliğini değiştirmek üzere izin vermek ve **FALSE** izin vermeyecek şekilde. İşlev döndürmelidir **TRUE** bildirim işlenmediyse belirtmek için **FALSE**.  
  
 `pfnChanged`  
 İşleme bir üye işlev işaretçisi **OnChanged** bu özellik için bildirim. İşlev olmalıdır bir **BOOL** dönüş türü ve **UINT** parametresi. İşlev döndürmelidir **TRUE** bildirim işlenmediyse belirtmek için **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 `vtsParams` Değişken değeri boşlukla ayrılmış bir liste değerleri **VTS_** sabitleri. Bir veya daha fazla (değil virgüller) boşluklarla ayrılmış bu değerleri işlev parametre listesi belirtir. Örneğin:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 arkasından kısa bir tamsayı içeren bir liste belirten bir **BOOL**.  
  
 Bir listesi için **VTS_** sabitleri, bkz: [EVENT_CUSTOM](event-maps.md#event_custom).  
  
##  <a name="on_propnotify_range"></a>ON_PROPNOTIFY_RANGE  
 Kullanım `ON_PROPNOTIFY_RANGE` bitişik olarak kimlikleri aralığı içindeki bir denetim kimliği sahip herhangi bir OLE denetimi özelliği bildirimleri işlemek için bir olay havuz eşleme girişi tanımlamak için makrosu.  
  
```  
 
ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Bu olay havuzu harita sınıfın ait olduğu.  
  
 `idFirst`  
 Aralıktaki ilk OLE denetim denetim kimliği.  
  
 `idLast`  
 Aralığın son OLE denetimindeki denetim kimliği.  
  
 `dispid`  
 Bildirim söz konusu özellik gönderme kimliği.  
  
 `pfnRequest`  
 İşleme bir üye işlev işaretçisi **OnRequestEdit** bu özellik için bildirim. Bu işlev olmalıdır bir **BOOL** dönüş türü ve **UINT** ve **BOOL\***  parametreleri. İşlev parametresi ayarlamalıdır **TRUE** özelliğini değiştirmek üzere izin vermek için ve **FALSE** izin vermeyecek şekilde. İşlev döndürmelidir **TRUE** bildirim işlenmediyse belirtmek için **FALSE**.  
  
 `pfnChanged`  
 İşleme bir üye işlev işaretçisi **OnChanged** bu özellik için bildirim. İşlev olmalıdır bir **BOOL** dönüş türü ve **UINT** parametresi. İşlev döndürmelidir **TRUE** bildirim işlenmediyse belirtmek için **FALSE**.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="on_propnotify_reflect"></a>ON_PROPNOTIFY_REFLECT  
 `ON_PROPNOTIFY_REFLECT` Olay bir OLE denetimin sarmalayıcı sınıfı, havuz haritasını kullanıldığında makrosu denetimin kapsayıcı tarafından işlenen önce denetim tarafından gönderilen özellik bildirimlerini alır.  
  
```  
 
ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Bu olay havuzu harita sınıfın ait olduğu.  
  
 `dispid`  
 Bildirim söz konusu özellik gönderme kimliği.  
  
 `pfnRequest`  
 İşleme bir üye işlev işaretçisi **OnRequestEdit** bu özellik için bildirim. Bu işlev olmalıdır bir **BOOL** dönüş türü ve **BOOL\***  parametresi. Bu işlev parametre ayarlamalıdır **TRUE** özelliğini değiştirmek üzere izin vermek ve **FALSE** izin vermeyecek şekilde. İşlev döndürmelidir **TRUE** bildirim işlenmediyse belirtmek için **FALSE**.  
  
 `pfnChanged`  
 İşleme bir üye işlev işaretçisi **OnChanged** bu özellik için bildirim. İşlev olmalıdır bir **BOOL** dönüş türü ve herhangi bir parametre. İşlev döndürmelidir **TRUE** bildirim işlenmediyse belirtmek için **FALSE**.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
