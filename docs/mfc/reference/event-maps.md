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
ms.openlocfilehash: 21b9efe8fc1ce5cb7ab90edd30b38253d44dabc0
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106814"
---
# <a name="event-maps"></a>Olay Eşlemeleri

Bir denetim kapsayıcısı (örneğin, bir tuş vuruşu, fare tıklatın veya denetimin durumunu değişiklik) gerçekleşen bazı eylemleri (denetim geliştiricisi tarafından belirlenir) bildirmek istediği her bir olay tetikleyicisinin tetikleme işlevi çağırır. Bu işlev, bazı önemli eylem ilgili olay tetikleme tarafından oluştu denetim kapsayıcısı bildirir.

Microsoft Foundation Class Kitaplığı olayları tetikleme için en iyi duruma getirilmiş bir programlama modeli sunar. Bu modelde, "olay eşlemeleri" belirli bir denetim için hangi olayların hangi işlevleri yangın belirlemek için kullanılır. Olay eşlemeleri, her olay için bir makro içerir. Örneğin, bir olay eşlemesi, hisse senedi Click olay şuna benzeyebilir başlatılır:

[!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]

`EVENT_STOCK_CLICK` Makrosu gösteren denetimi hisse senedi tıklatın, bir fare algıladığı her zaman olay ateşlenir. Stok diğer olaylar daha ayrıntılı bir listesi için bkz [ActiveX denetimleri: olaylar](../../mfc/mfc-activex-controls-events.md). Makrolar özel olayları göstermek de kullanılabilir.

Olay eşleme makroları önemli olsa da, genellikle bunları doğrudan eklediğiniz değil. Özellikler penceresinde olay eşleme girişleri olay tetikleyicisinin tetikleme işlevleri olaylarla ilişkilendirmek için kullandığınızda, kaynak dosyaları otomatik olarak oluşturur. olmasıdır. Düzenlemek veya bir olay eşlemesi giriş eklemek için istediğiniz zaman, Özellikler penceresini kullanabilirsiniz.

Olay eşlemeleri desteklemek için aşağıdaki makroları MFC sağlar:

## <a name="event-map-macros"></a>Olay eşleme makroları

### <a name="event-map-declaration-and-demarcation"></a>Olay eşleme bildirim ve düzenleme

|||
|-|-|
|[DECLARE_EVENT_MAP](#declare_event_map)|Bir olay eşlemesi bir sınıf içinde olay tetikleyicisinin tetikleme işlevleri (sınıf bildirimi içinde kullanılmalıdır) olayları eşleştirmek için kullanılacak bildirir.|
|[BEGIN_EVENT_MAP](#begin_event_map)|Bir olay eşlemesi (sınıfı uygulamasında kullanılmalıdır) tanımını başlar.|
|[END_EVENT_MAP](#end_event_map)|Bir olay eşlemesi (sınıfı uygulamasında kullanılmalıdır) tanımını sonlandırır.|

### <a name="event-mapping-macros"></a>Olay eşleme makroları

|||
|-|-|
|[EVENT_CUSTOM](#event_custom)|Hangi olay tetikleyicisinin tetikleme işlevi belirtilen olay harekete gösterir.|
|[EVENT_CUSTOM_ID](#event_custom_id)|Hangi olay tetikleyicisinin tetikleme işlevi bir belirtilen dağıtım kimliği ile belirtilen bir olay harekete gösterir|

### <a name="message-mapping-macros"></a>İleti eşleme makroları

|||
|-|-|
|[ON_OLEVERB](#on_oleverb)|OLE denetim tarafından işlenen özel bir eylem belirtir.|
|[ON_STDOLEVERB](#on_stdoleverb)|OLE denetim standart fiili eşlemesi geçersiz kılar.|

##  <a name="declare_event_map"></a>  DECLARE_EVENT_MAP

Her `COleControl`-programınızı türetilen sınıfta denetiminiz yangın olayları belirtmek için bir olay eşlemesi sağlayabilir.

```cpp
DECLARE_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

DECLARE_EVENT_MAP makrosu, sınıf bildiriminin sonuna kullanın. Ardından, sınıfın üye işlevleri tanımlar .cpp dosyası begın_event_map makrosu, makro girişleri her biri denetim olaylarını ve END_EVENT_MAP makrosu için olay listesinin sonuna bildirmek için kullanın.

Olay eşlemeleri hakkında daha fazla bilgi için bkz [ActiveX denetimleri: olaylar](../../mfc/mfc-activex-controls-events.md).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi** afxctl.h

## <a name="begin_event_map"></a>  BEGIN_EVENT_MAP

Olay haritanızı tanımını başlar.

```cpp
BEGIN_EVENT_MAP(theClass,  baseClass)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*  
Bu olayı harita denetimi sınıfın adını belirtir.

*baseClass*  
Taban sınıfının adını belirtir *sınıfın*.

### <a name="remarks"></a>Açıklamalar

Sınıfınız için üye işlevleri tanımlayan uygulama dosyasında (.cpp), olay eşlemesi begın_event_map makrosu ile Başlat sonra her olaylarınızı makrosu girişler ekleyin ve olay eşlemesi END_EVENT_MAP makrosu ile tamamlayın.

Olay eşlemeleri ve begın_event_map makrosu hakkında daha fazla bilgi için bkz [ActiveX denetimleri: olaylar](../../mfc/mfc-activex-controls-events.md).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi** afxctl.h

##  <a name="end_event_map"></a>  END_EVENT_MAP

END_EVENT_MAP makrosu, olay eşlemesi tanımını sonlandırmak için kullanın.

```cpp
END_EVENT_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Üst bilgi** afxctl.h

## <a name="event_custom"></a>  EVENT_CUSTOM

Özel bir olay için bir olay eşlemesi giriş tanımlar.

```cpp
EVENT_CUSTOM(pszName, pfnFire,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*pszName*  
Olayın adı.

*pfnFire*  
İşlev olay adı.

*vtsParams*  
İşlevin parametre listesi belirten bir veya daha fazla sabitleri boşlukla ayrılmış listesi.

### <a name="remarks"></a>Açıklamalar

*VtsParams* parametresi, boşlukla ayrılmış bir liste değerleri `VTS_` sabitler. Bir veya daha fazla boşluk (virgül değil) ile ayırarak bu değerleri işlevin parametre listesi belirtir. Örneğin:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

bir RGB temsil eden bir 32 bit tamsayı içeren bir liste işaretçisi ardından değer rengi belirtir `IFontDisp` OLE yazı tipi nesnesinin arabirimi.

`VTS_` Sabitleri ve bunların anlamları şu şekildedir:

|Sembol|Parametre türü|
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
|VTS_HANDLE|TANITICI|
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
> Değişken veri sabit bir işaretçi sağlayan tüm değişken türleri için VTS_FONT ve vts_pıcture, hariç olmak üzere ek değişken sabitleri tanımlanmadı. Bu sabitler kullanılarak adlandırılır `VTS_Pconstantname` kuralı. Örneğin, VTS_PCOLOR VTS_COLOR sabiti bir işaretçisidir.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi** afxctl.h

## <a name="event_custom_id"></a>  EVENT_CUSTOM_ID

İşlev tarafından belirtilen dağıtım kimliği ait özel bir olay için tetikleme bir olayı tanımlar *DISPID*.

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
Olay tetikleme denetim tarafından kullanılan dağıtım kimliği.

*pfnFire*  
İşlev olay adı.

*vtsParams*  
Olay tetiklendiğinde parametrelerinin bir değişken listesi denetimi kapsayıcıya geçirildi.

### <a name="remarks"></a>Açıklamalar

*VtsParams* bağımsız değişken değerlerini boşlukla ayrılmış bir listesi verilmiştir `VTS_` sabitler. Bir veya daha fazla değil virgül, boşluk ile ayırarak bu değerleri işlevin parametre listesi belirtir. Örneğin:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

bir RGB temsil eden bir 32 bit tamsayı içeren bir liste işaretçisi ardından değer rengi belirtir `IFontDisp` OLE yazı tipi nesnesinin arabirimi.

Bir listesi için `VTS_` sabitleri bkz [EVENT_CUSTOM](#event_custom).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi** afxctl.h

## <a name="on_oleverb"></a>  ON_OLEVERB

Bu makro, özel bir fiil denetiminiz için bir özel üye işlevini eşlemeleri bir ileti eşleme girişi tanımlar.

```cpp
ON_OLEVERB(idsVerbName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*idsVerbName*<br/>
Fiili'nın adı dize kaynak kimliği.

*memberFxn*<br/>
Framework tarafından fiil çağrıldığında çağrılan işlev.

### <a name="remarks"></a>Açıklamalar

Kaynak Düzenleyicisi dize tablonuza eklenen özel eylem adları oluşturmak için kullanılabilir.

İşlev prototipi *memberFxn* olan:

```cpp
BOOL memberFxn(
   LPMSG    lpMsg,
   HWND     hWndParent,
   LPCRECT  lpRect);
```

Değerlerini *lpMsg*, *hWndParent*, ve *lpRect* parametreleri, karşılık gelen parametrelerinden alınır `IOleObject::DoVerb` üye işlevi.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi** afxole.h

## <a name="on_stdoleverb"></a>  ON_STDOLEVERB

Standart fiil varsayılan davranışı geçersiz kılmak için bu makroyu kullanın.

```cpp
ON_STDOLEVERB(iVerb, memberFxn)
```

### <a name="parameters"></a>Parametreler

*iVerb*  
Geçersiz kılınmasını fiil için standart fiili dizini.

*memberFxn*  
Framework tarafından fiil çağrıldığında çağrılan işlev.

### <a name="remarks"></a>Açıklamalar

Standart fiili dizini biçimindedir `OLEIVERB_`takip eden eylem. OLEIVERB_SHOW OLEIVERB_HIDE ve OLEIVERB_UIACTIVATE standart fiiller bazı örnekleridir.

Bkz: [ON_OLEVERB](#on_oleverb) olarak kullanılmak üzere işlev prototipi açıklamasını *memberFxn* parametresi.


### <a name="requirements"></a>Gereksinimler

**Üst bilgi** afxole.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
