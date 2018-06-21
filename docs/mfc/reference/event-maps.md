---
title: Olay eşlemeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- event maps [MFC]
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4e7ab64af82e2f37104f82778d4c6f5eb12bd032
ms.sourcegitcommit: 05075fce8a0ed7fddb99f50f3931db966a91450d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271311"
---
# <a name="event-maps"></a>Olay Eşlemeleri
Bir denetim (Denetim geliştirici tarafından belirlenir) bazı eylemler (örneğin, bir tuş vuruşu, fare tıklatma veya denetimin durumunu değişiklik) gerçekleştirilmedi kapsayıcısı bildir istediği her bir olay tetikleme işlevi çağırır. Bu işlev, bazı önemli eylem ilgili olay tetikleme tarafından oluştu denetimi kapsayıcısı bildirir.  
  
 Microsoft Foundation Class Kitaplığı olaylarını tetikleme için en iyi hale getirilmiş bir programlama modeli sunar. Bu modelde, "olay eşlemeleri" belirli bir denetim için hangi olayların hangi işlevleri yangın atamak için kullanılır. Olay eşlemeleri her olay için bir makrosu içerir. Örneğin, bir olay eşlemesi hisse senedi olay şuna benzeyebilir tıklatın, başlatılır:  
  
 [!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]  
  
 **Event_stock_clıck** makrosu gösterir denetimi hisse senedi tıklatın, fare algıladığı her zaman olay ateşlenir. Diğer stok olaylar hakkında daha ayrıntılı listesi için bkz: [ActiveX denetimleri: olaylar](../../mfc/mfc-activex-controls-events.md). Makrolar özel olaylar belirtmek de kullanılabilir.  
  
 Olay eşleme makroları önemli olsa da, genellikle bunları doğrudan eklediğiniz değil. Olay tetikleme işlevleri olaylarla ilişkilendirmek için kullandığınızda Özellikler penceresini olay eşlemesi girişleri Kaynak dosyalarınız otomatik olarak oluşturur. olmasıdır. Düzenlemek veya bir olay eşlemesi giriş eklemek için istediğiniz zaman Özellikler penceresini kullanabilirsiniz.  
  
 Olay eşlemeleri desteklemek için aşağıdaki makroları MFC sağlar:  
  
### <a name="event-map-declaration-and-demarcation"></a>Olay eşleme bildirim ve düzenleme  
  
|||  
|-|-|  
|[DECLARE_EVENT_MAP](#declare_event_map)|Bir olay eşlemesi bir sınıfta olayları olay tetikleme işlevleri (sınıfı bildiriminde kullanılmalıdır) eşleştirmek için kullanılacak bildirir.|  
|[BEGIN_EVENT_MAP](#begin_event_map)|(Sınıfı uygulamasında kullanılmalıdır) bir olay eşlemesi tanımını başlar.|  
|[END_EVENT_MAP](#end_event_map)|(Sınıfı uygulamasında kullanılmalıdır) bir olay eşlemesi tanımını sona erer.|  
  
### <a name="event-mapping-macros"></a>Olay eşleme makroları  
  
|||  
|-|-|  
|[EVENT_CUSTOM](#event_custom)|Hangi olay tetikleme işlevi belirtilen olay ateşlenir gösterir.|  
|[EVENT_CUSTOM_ID](#event_custom_id)|Hangi olay tetikleme işlevi belirlenen gönderme kimliğiyle belirtilen olay ateşlenir gösterir|  
  
### <a name="message-mapping-macros"></a>İleti eşleme makroları  
  
|||  
|-|-|  
|[ON_OLEVERB](#on_oleverb)|OLE denetim tarafından işlenen özel bir fiil gösterir.|  
|[ON_STDOLEVERB](#on_stdoleverb)|OLE denetim standart fiil eşlemesi geçersiz kılar.|  
  
##  <a name="declare_event_map"></a>  DECLARE_EVENT_MAP  
 Her `COleControl`-programınızı türetilen sınıfta denetiminiz yangın olayları belirtmek için bir olay eşlemesi sağlayabilir.  
  
```   
DECLARE_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `DECLARE_EVENT_MAP` makrosu sınıf bildiriminin sonundaki. Ardından, sınıf için üye işlevleri tanımlayan .cpp dosyasında kullanmak `BEGIN_EVENT_MAP` makrosu, denetimin olayların her biri için makrosu girişleri ve `END_EVENT_MAP` olay listesinin sonuna bildirmek için makrosu.  
  
 Olay eşlemeleri hakkında daha fazla bilgi için bkz: [ActiveX denetimleri: olaylar](../../mfc/mfc-activex-controls-events.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="begin_event_map"></a>  BEGIN_EVENT_MAP  
 Olay eşlemesi tanımını başlar.  
  
```   
BEGIN_EVENT_MAP(theClass,  baseClass)  
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Bu harita, Olay denetimi sınıfın adını belirtir.  
  
 `baseClass`  
 Temel sınıfını adını belirtir `theClass`.  
  
### <a name="remarks"></a>Açıklamalar  
 Olay eşlemesi ile sınıfınız için üye işlevleri tanımlar uygulaması (.cpp) dosyasına Başlat `BEGIN_EVENT_MAP` makrosu, ardından makrosu girişleri her olaylarınızı ekleyin ve olay eşlemesi ile tamamlayın `END_EVENT_MAP` makrosu.  
  
 Olay hakkında daha fazla bilgi için eşler ve `BEGIN_EVENT_MAP` makrosu, makaleye bakın [ActiveX denetimleri: olaylar](../../mfc/mfc-activex-controls-events.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="end_event_map"></a>  END_EVENT_MAP  
 Kullanım `END_EVENT_MAP` olay eşlemesi tanımını sonuna makrosu.  
  
```   
END_EVENT_MAP()   
```  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="event_custom"></a>  EVENT_CUSTOM  
 Özel bir olay için bir olay eşleme girişi tanımlar.  
  
```   
EVENT_CUSTOM(pszName, pfnFire,  vtsParams) 
```  
  
### <a name="parameters"></a>Parametreler  
 `pszName`  
 Olayın adı.  
  
 `pfnFire`  
 İşlev olay adı.  
  
 `vtsParams`  
 İşlev parametre listesi belirterek bir veya daha fazla sabitleri boşlukla ayrılmış listesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `vtsParams` Parametredir boşlukla ayrılmış bir liste değerleri **VTS_** sabitleri. Bir veya daha fazla (değil virgüller) boşluklarla ayrılmış bu değerleri işlev parametre listesi belirtir. Örneğin:  
  
 [!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]  
  
 RGB temsil eden bir 32 bit tamsayı içeren bir liste için bir işaretçi arkasından değeri, renk belirtir **IFontDisp** OLE yazı tipi nesnesinin arabirimi.  
  
 **VTS_** sabitleri ve anlamlarını aşağıdaki gibidir:  
  
|Simgesi|Parametre türü|  
|------------|--------------------|  
|**VTS_I2**|**short**|  
|**VTS_I4**|**long**|  
|**VTS_R4**|**float**|  
|**VTS_R8**|**double**|  
|**VTS_COLOR**|**OLE_COLOR**|  
|**VTS_CY**|**PARA BİRİMİ**|  
|**VTS_DATE**|**TARİH**|  
|**VTS_BSTR**|**Const char\\\***|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_FONT**|**IFontDispatch\\\***|  
|**VTS_HANDLE**|`HANDLE`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**const değişken\\\***|  
|**VTS_PVARIANT**|**DEĞİŞKEN\\\***|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_OPTEXCLUSIVE**|**OLE_OPTEXCLUSIVE**|  
|**VTS_PICTURE**|**IPictureDisp\\\***|  
|**VTS_TRISTATE**|**OLE_TRISTATE**|  
|**VTS_XPOS_PIXELS**|**OLE_XPOS_PIXELS**|  
|**VTS_YPOS_PIXELS**|**OLE_YPOS_PIXELS**|  
|**VTS_XSIZE_PIXELS**|**OLE_XSIZE_PIXELS**|  
|**VTS_YSIZE_PIXELS**|**OLE_YSIZE_PIXELS**|  
|**VTS_XPOS_HIMETRIC**|**OLE_XPOS_HIMETRIC**|  
|**VTS_YPOS_HIMETRIC**|**OLE_YPOS_HIMETRIC**|  
|**VTS_XSIZE_HIMETRIC**|**OLE_XSIZE_HIMETRIC**|  
|**VTS_YSIZE_HIMETRIC**|**OLE_YSIZE_HIMETRIC**|  
  
> [!NOTE]
>  Ek değişken sabitleri dışında tüm değişken türleri için tanımlanmışsa **VTS_FONT** ve **vts_pıcture**, değişken veri sabiti gösteren bir işaretçi sağlar. Kullanarak bu sabitleri adlı **VTS_P** `constantname` kuralı. Örneğin, **VTS_PCOLOR** gösteren bir işaretçidir bir **VTS_COLOR** sabit.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="event_custom_id"></a>  EVENT_CUSTOM_ID  
 Tetikleme işlevi tarafından belirtilen gönderme kimliği ait özel bir olay için bir olay tanımlar `dispid`.  
  
```   
EVENT_CUSTOM_ID(
  pszName,   
  dispid,   
  pfnFire,
  vtsParams)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `pszName`  
 Olayın adı.  
  
 `dispid`  
 Olay tetikleme denetimi tarafından kullanılan gönderme kimliği.  
  
 `pfnFire`  
 İşlev olay adı.  
  
 `vtsParams`  
 Olay başlatıldığında bir değişken listesi parametrelerinin denetim kapsayıcıya geçirildi.  
  
### <a name="remarks"></a>Açıklamalar  
 `vtsParams` Değişken değeri boşlukla ayrılmış bir liste değerleri **VTS_** sabitleri. Bir veya daha fazla boşluklarla değil virgülle ayrılmış bu değerleri işlev parametre listesi belirtir. Örneğin:  
  
 [!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]  
  
 RGB temsil eden bir 32 bit tamsayı içeren bir liste için bir işaretçi arkasından değeri, renk belirtir **IFontDisp** OLE yazı tipi nesnesinin arabirimi.  
  
 Bir listesi için **VTS_** sabitleri, bkz: [EVENT_CUSTOM](#event_custom).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="on_oleverb"></a>  ON_OLEVERB  
 Bu makrosu denetiminizin belirli üye işlevi için özel bir fiil eşleyen bir ileti eşleme girişi tanımlar.  
  
```   
ON_OLEVERB(idsVerbName,  memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 *idsVerbName*  
 Fiili kişinin adı dize kaynak kimliği.  
  
 `memberFxn`  
 İşlev fiili çağrıldığında çerçevesi tarafından çağrılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak Düzenleyici dize tablosuna eklenen özel fiil adlar oluşturmak için kullanılabilir.  
  
 İşlev prototipi `memberFxn` değil:  
  
 `BOOL memberFxn(`    
 `LPMSG` `lpMsg` `,`   
 `HWND` `hWndParent` `,`   
 `LPCRECT` `lpRect`   `);`  
  
 Değerlerini `lpMsg`, `hWndParent`, ve `lpRect` parametreleri karşılık gelen parametrelerinden alınır **Rpc_e_serverfault** üye işlevi.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxole.h  
  
##  <a name="on_stdoleverb"></a>  ON_STDOLEVERB  
 Bu makrosu standart fiil varsayılan davranışını geçersiz kılmak için kullanın.  
  
```   
ON_STDOLEVERB(iVerb,   memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `iVerb`  
 Geçersiz kılıp fiil standart fiil dizini.  
  
 `memberFxn`  
 İşlev fiili çağrıldığında çerçevesi tarafından çağrılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Standart fiil dizin biçimidir **OLEIVERB_** takip eden bir eylem. `OLEIVERB_SHOW`, `OLEIVERB_HIDE`, ve `OLEIVERB_UIACTIVATE` standart fiillerin bazı örnekleri şunlardır.  
  
 Bkz: [ON_OLEVERB](#on_oleverb) olarak kullanılacak işlev prototipi açıklaması `memberFxn` parametresi.  

  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxole.h  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
