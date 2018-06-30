---
title: Olay eşlemeleri | Microsoft Docs
ms.custom: ''
ms.date: 06/20/2018
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
ms.openlocfilehash: f4522b9ea2f336f5ac88f5444edc0c7df16b5bc6
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122395"
---
# <a name="event-maps"></a>Olay Eşlemeleri

Bir denetim (Denetim geliştirici tarafından belirlenir) bazı eylemler (örneğin, bir tuş vuruşu, fare tıklatma veya denetimin durumunu değişiklik) gerçekleştirilmedi kapsayıcısı bildir istediği her bir olay tetikleme işlevi çağırır. Bu işlev, bazı önemli eylem ilgili olay tetikleme tarafından oluştu denetimi kapsayıcısı bildirir.

Microsoft Foundation Class Kitaplığı olaylarını tetikleme için en iyi hale getirilmiş bir programlama modeli sunar. Bu modelde, "olay eşlemeleri" belirli bir denetim için hangi olayların hangi işlevleri yangın atamak için kullanılır. Olay eşlemeleri her olay için bir makrosu içerir. Örneğin, bir olay eşlemesi hisse senedi olay şuna benzeyebilir tıklatın, başlatılır:

[!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]

`EVENT_STOCK_CLICK` Makrosu gösterir denetimi hisse senedi tıklatın, fare algıladığı her zaman olay ateşlenir. Diğer stok olaylar hakkında daha ayrıntılı listesi için bkz: [ActiveX denetimleri: olaylar](../../mfc/mfc-activex-controls-events.md). Makrolar özel olaylar belirtmek de kullanılabilir.

Olay eşleme makroları önemli olsa da, genellikle bunları doğrudan eklediğiniz değil. Olay tetikleme işlevleri olaylarla ilişkilendirmek için kullandığınızda Özellikler penceresini olay eşlemesi girişleri Kaynak dosyalarınız otomatik olarak oluşturur. olmasıdır. Düzenlemek veya bir olay eşlemesi giriş eklemek için istediğiniz zaman Özellikler penceresini kullanabilirsiniz.

Olay eşlemeleri desteklemek için aşağıdaki makroları MFC sağlar:

## <a name="event-map-macros"></a>Olay eşleme makroları

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

```cpp
DECLARE_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

DECLARE_EVENT_MAP makrosu sınıf bildiriminin sonundaki kullanın. Ardından, sınıf için üye işlevleri tanımlayan .cpp dosyasında begın_event_map makrosu, makrosu girişleri her biri denetim olaylarını ve END_EVENT_MAP makrosu olay listesinin sonuna bildirmek için kullanın.

Olay eşlemeleri hakkında daha fazla bilgi için bkz: [ActiveX denetimleri: olaylar](../../mfc/mfc-activex-controls-events.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxctl.h

## <a name="begin_event_map"></a>  BEGIN_EVENT_MAP

Olay eşlemesi tanımını başlar.

```cpp
BEGIN_EVENT_MAP(theClass,  baseClass)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*  
Bu harita, Olay denetimi sınıfın adını belirtir.

*baseClass*  
Temel sınıfını adını belirtir *sınıfın*.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza üye işlevleri tanımlar uygulaması (.cpp) dosyasında, olay eşlemesi begın_event_map makrosu ile başlatın ardından makrosu girişleri her olaylarınızı ekleyin ve END_EVENT_MAP makrosu ile olay eşlemesi tamamlayın.

Olay eşlemeleri ve begın_event_map makrosu hakkında daha fazla bilgi için bkz: [ActiveX denetimleri: olaylar](../../mfc/mfc-activex-controls-events.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxctl.h

##  <a name="end_event_map"></a>  END_EVENT_MAP

Olay eşlemesi tanımını sonlandırmak için END_EVENT_MAP makrosu kullanın.

```cpp
END_EVENT_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxctl.h

## <a name="event_custom"></a>  EVENT_CUSTOM

Özel bir olay için bir olay eşleme girişi tanımlar.

```cpp
EVENT_CUSTOM(pszName, pfnFire,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*pszName*  
Olayın adı.

*pfnFire*  
İşlev olay adı.

*vtsParams*  
İşlev parametre listesi belirterek bir veya daha fazla sabitleri boşlukla ayrılmış listesi.

### <a name="remarks"></a>Açıklamalar

*VtsParams* parametredir boşlukla ayrılmış bir liste değerleri `VTS_` sabitleri. Bir veya daha fazla (değil virgüller) boşluklarla ayrılmış bu değerleri işlev parametre listesi belirtir. Örneğin:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

RGB temsil eden bir 32 bit tamsayı içeren bir liste için bir işaretçi arkasından değeri, renk belirtir `IFontDisp` OLE yazı tipi nesnesinin arabirimi.

`VTS_` Sabitleri ve anlamlarını aşağıdaki gibidir:

|Simgesi|Parametre türü|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**long**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_COLOR|OLE_COLOR|
|VTS_CY|PARA BİRİMİ|
|VTS_DATE|TARİH|
|VTS_BSTR|**const** __char\*__|
|VTS_DISPATCH|LPDISPATCH|
|VTS_FONT|`IFontDispatch*`|
|VTS_HANDLE|İŞLEME|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_UNKNOWN|LPUNKNOWN|
|VTS_OPTEXCLUSIVE|OLE_OPTEXCLUSIVE|
|VTS_PICTURE|`IPictureDisp*`|
|VTS_TRISTATE|OLE_TRISTATE|
|VTS_XPOS_PIXELS|OLE_XPOS_PIXELS|
|VTS_YPOS_PIXELS|OLE_YPOS_PIXELS|
|VTS_XSIZE_PIXELS|OLE_XSIZE_PIXELS|
|VTS_YSIZE_PIXELS|OLE_YSIZE_PIXELS|
|TS_XPOS_HIMETRIC|OLE_XPOS_HIMETRIC|
|VTS_YPOS_HIMETRIC|OLE_YPOS_HIMETRIC|
|VTS_XSIZE_HIMETRIC|OLE_XSIZE_HIMETRIC|
|VTS_YSIZE_HIMETRIC|OLE_YSIZE_HIMETRIC|

> [!NOTE]
> Değişken veri sabiti gösteren bir işaretçi sağlayan tüm değişken türleri için VTS_FONT ve vts_pıcture, hariç olmak üzere ek değişken sabitleri tanımlanmadı. Kullanarak bu sabitleri adlı `VTS_Pconstantname` kuralı. Örneğin, VTS_PCOLOR gösteren bir işaretçidir VTS_COLOR sabiti.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxctl.h

## <a name="event_custom_id"></a>  EVENT_CUSTOM_ID

Tetikleme işlevi tarafından belirtilen gönderme kimliği ait özel bir olay için bir olay tanımlar *DISPID*.

```cpp
EVENT_CUSTOM_ID(
  pszName,
  dispid,
  pfnFire,
  vtsParams)
```

### <a name="parameters"></a>Parametreler

*pszName*  
Olayın adı.

*DISPID*  
Olay tetikleme denetimi tarafından kullanılan gönderme kimliği.

*pfnFire*  
İşlev olay adı.

*vtsParams*  
Olay başlatıldığında bir değişken listesi parametrelerinin denetim kapsayıcıya geçirildi.

### <a name="remarks"></a>Açıklamalar

*VtsParams* değişken değeri boşlukla ayrılmış bir liste değerleri `VTS_` sabitleri. Bir veya daha fazla boşluklarla değil virgülle ayrılmış bu değerleri işlev parametre listesi belirtir. Örneğin:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

RGB temsil eden bir 32 bit tamsayı içeren bir liste için bir işaretçi arkasından değeri, renk belirtir `IFontDisp` OLE yazı tipi nesnesinin arabirimi.

Bir listesi için `VTS_` sabitleri, bkz: [EVENT_CUSTOM](#event_custom).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxctl.h

## <a name="on_oleverb"></a>  ON_OLEVERB

Bu makrosu denetiminizin belirli üye işlevi için özel bir fiil eşleyen bir ileti eşleme girişi tanımlar.

```cpp
ON_OLEVERB(idsVerbName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*idsVerbName* fiili kişinin adı dize kaynak kimliği.

*memberFxn*  
İşlev fiili çağrıldığında çerçevesi tarafından çağrılır.

### <a name="remarks"></a>Açıklamalar

Kaynak Düzenleyici dize tablosuna eklenen özel fiil adlar oluşturmak için kullanılabilir.

İşlev prototipi *memberFxn* değil:

```cpp
BOOL memberFxn(
   LPMSG    lpMsg,
   HWND     hWndParent,
   LPCRECT  lpRect);
```

Değerlerini *lpMsg*, *hWndParent*, ve *lpRect* parametreleri karşılık gelen parametrelerinden alınır `IOleObject::DoVerb` üye işlevi.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxole.h

## <a name="on_stdoleverb"></a>  ON_STDOLEVERB

Bu makrosu standart fiil varsayılan davranışını geçersiz kılmak için kullanın.

```cpp
ON_STDOLEVERB(iVerb, memberFxn)
```

### <a name="parameters"></a>Parametreler

*iVerb*  
Geçersiz kılıp fiil standart fiil dizini.

*memberFxn*  
İşlev fiili çağrıldığında çerçevesi tarafından çağrılır.

### <a name="remarks"></a>Açıklamalar

Standart fiil dizin biçimidir `OLEIVERB_`takip eden bir eylem. OLEIVERB_SHOW, OLEIVERB_HIDE ve OLEIVERB_UIACTIVATE bazı standart fiillerin gösterilebilir.

Bkz: [ON_OLEVERB](#on_oleverb) olarak kullanılacak işlev prototipi açıklaması *memberFxn* parametresi.


### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxole.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
