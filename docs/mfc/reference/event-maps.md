---
title: Olay Eşlemeleri
ms.date: 09/07/2019
helpviewer_keywords:
- event maps [MFC]
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
ms.openlocfilehash: c79d2fb1ac73947ddb13adcbd444ff7b5d50bdb4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365746"
---
# <a name="event-maps"></a>Olay Eşlemeleri

Bir denetim, kapsayıcısına bazı eylemlerin (denetim geliştiricisi tarafından belirlenir) gerçekleştiğini (tuş vuruşu, fare tıklaması veya denetimin durumuna yapılan bir değişiklik gibi) bildirmek istediğinde, olay çıkarma işlevini çağırır. Bu işlev, denetim kabına ilgili olayı ateşleyerek bazı önemli eylemlerin meydana geldiğini belirtir.

Microsoft Hazırlık Sınıf Kitaplığı, olayları ateşlemek için optimize edilmiş bir programlama modeli sunar. Bu modelde, "olay haritaları" belirli bir denetim için hangi işlevleri yangın belirlemek için kullanılır. Olay eşlemleri her olay için bir makro içerir. Örneğin, bir stok Tıklama olayı yangınları bir olay haritası şu şekilde görünebilir:

[!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]

Makro, `EVENT_STOCK_CLICK` denetimin bir hisse senedi tıklaması olayını her fare tıklaması algıladığında ateşedeceğini gösterir. Diğer stok olaylarının daha ayrıntılı bir listesi için [ActiveX Denetimleri: Olaylar](../../mfc/mfc-activex-controls-events.md)makalesine bakın. Makrolar da özel olayları belirtmek için kullanılabilir.

Olay eşlemi makroları önemli olsa da, genellikle bunları doğrudan eklemezsiniz. Bunun nedeni, olay çıkarma işlevlerini olaylarla ilişkilendirmek için kullandığınızda **Özellikler** penceresinin **(Sınıf Görünümünde)** kaynak dosyalarınızda otomatik olarak olay eşlemi girişleri oluşturmasıdır. Bir olay eşlemi girişini ne zaman bir olay eşlemi eklemek istediğinizde, **Özellikler** penceresini kullanabilirsiniz.

Olay eşlemlerini desteklemek için MFC aşağıdaki makroları sağlar:

## <a name="event-map-macros"></a>Olay Haritası makroları

### <a name="event-map-declaration-and-demarcation"></a>Olay Haritası Bildirimi ve Çizimi

|||
|-|-|
|[DECLARE_EVENT_MAP](#declare_event_map)|Olayları olay çıkarma işlevleriyle eşlemek için bir sınıfta bir olay haritası kullanılacağını bildirir (sınıf bildiriminde kullanılmalıdır).|
|[BEGIN_EVENT_MAP](#begin_event_map)|Olay haritasının tanımını başla (sınıf uygulamasında kullanılmalıdır).|
|[END_EVENT_MAP](#end_event_map)|Olay haritası tanımını sona erdirer (sınıf uygulamasında kullanılmalıdır).|

### <a name="event-mapping-macros"></a>Olay Eşleme Makroları

|||
|-|-|
|[EVENT_CUSTOM](#event_custom)|Belirtilen olayı hangi olay ateşleme işlevinin ateşleyeceğini gösterir.|
|[EVENT_CUSTOM_ID](#event_custom_id)|Belirtilen olayı, belirlenmiş bir sevk kimliğiyle hangi olay ateşleme işlevinin ateşleyeceğini gösterir.|

### <a name="message-mapping-macros"></a>İleti Eşleme Makroları

|||
|-|-|
|[ON_OLEVERB](#on_oleverb)|OLE denetimi tarafından işlenen özel bir fiili gösterir.|
|[ON_STDOLEVERB](#on_stdoleverb)|OLE denetiminin standart bir fiil eşlemi geçersiz kılar.|

## <a name="declare_event_map"></a><a name="declare_event_map"></a>DECLARE_EVENT_MAP

Programınızdaki türetilmiş her `COleControl`sınıf, denetiminizin ateş edeceği olayları belirtmek için bir olay haritası sağlayabilir.

```cpp
DECLARE_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

Sınıf bildirgenizin sonundaki DECLARE_EVENT_MAP makroyu kullanın. Ardından, sınıfın üye işlevlerini tanımlayan .cpp dosyasında, BEGIN_EVENT_MAP makroyu, denetimin her olayı için makro girişlerini ve olay listesinin sonunu bildirmek için makroyu END_EVENT_MAP kullanın.

Olay haritaları hakkında daha fazla bilgi için [ActiveX Denetimleri: Olaylar](../../mfc/mfc-activex-controls-events.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxctl.h

## <a name="begin_event_map"></a><a name="begin_event_map"></a>BEGIN_EVENT_MAP

Olay haritanızın tanımını başlayır.

```cpp
BEGIN_EVENT_MAP(theClass,  baseClass)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Olay haritası bu olan denetim sınıfının adını belirtir.

*Baseclass*<br/>
*Sınıfın*taban sınıfının adını belirtir.

### <a name="remarks"></a>Açıklamalar

Sınıfınızın üye işlevlerini tanımlayan uygulama (.cpp) dosyasında, olay haritasını BEGIN_EVENT_MAP makrosuyla başlatın, ardından her etkinliğiniz için makro girişleri ekleyin ve END_EVENT_MAP makrosuyla olay haritasını tamamlayın.

Olay haritaları ve BEGIN_EVENT_MAP makrosu hakkında daha fazla bilgi için [ActiveX Denetimleri: Olaylar](../../mfc/mfc-activex-controls-events.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxctl.h

## <a name="end_event_map"></a><a name="end_event_map"></a>END_EVENT_MAP

Olay haritanızın tanımını sona erdirmek için END_EVENT_MAP makroyu kullanın.

```cpp
END_EVENT_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxctl.h

## <a name="event_custom"></a><a name="event_custom"></a>EVENT_CUSTOM

Özel bir olay için olay haritası girişi tanımlar.

```cpp
EVENT_CUSTOM(pszName, pfnFire,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*pszName*<br/>
Olayın adı.

*pfnAteş*<br/>
Olay atış işlevinin adı.

*vtsParams*<br/>
İşlevin parametre listesini belirten bir veya daha fazla sabitin boşluktan ayrılmış listesi.

### <a name="remarks"></a>Açıklamalar

*vtsParams* `VTS_` parametresi, sabitlerden ayrılan değerlerin boşluklu bir listesidir. Boşluklarla ayrılan bu değerlerden biri veya birkaçı (virgül değil) işlevin parametre listesini belirtir. Örneğin:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

RGB renk değerini temsil eden 32 bit'lik bir tamsayı içeren bir liste `IFontDisp` yi ve ardından bir OLE yazı tipi nesnesinin arabirimine işaretçi belirtir.

Sabitler `VTS_` ve anlamları aşağıdaki gibidir:

|Sembol|Parametre türü|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**long**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_COLOR|Ole_color|
|VTS_CY|PARA BİRİMİ|
|VTS_DATE|DATE|
|VTS_BSTR|**const** __\* char__|
|VTS_DISPATCH|LPDISPATCH|
|VTS_FONT|`IFontDispatch*`|
|VTS_HANDLE|Işlemek|
|VTS_SCODE|SCODE|
|VTS_BOOL|Bool|
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
> VTS_FONT ve VTS_PICTURE dışında, varyant veri sabitine işaretçi sağlayan tüm varyant türleri için ek varyant sabitleri tanımlanmıştır. Bu sabitler `VTS_Pconstantname` kuralı kullanılarak adlandırılır. Örneğin, VTS_PCOLOR VTS_COLOR sabiti için bir işaretçidir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxctl.h

## <a name="event_custom_id"></a><a name="event_custom_id"></a>EVENT_CUSTOM_ID

*Dispid*tarafından belirtilen sevk kimliğine ait özel bir olay için olay çıkarma işlevini tanımlar.

```cpp
EVENT_CUSTOM_ID(
    pszName,
    dispid,
    pfnFire,
    vtsParams)
```

### <a name="parameters"></a>Parametreler

*pszName*<br/>
Olayın adı.

*Dıspıd*<br/>
Olayı ateşlerken denetim tarafından kullanılan sevk kimliği.

*pfnAteş*<br/>
Olay atış işlevinin adı.

*vtsParams*<br/>
Olay ateşlendiğinde kontrol kabına geçirilen parametrelerin değişken listesi.

### <a name="remarks"></a>Açıklamalar

*vtsParams* bağımsız `VTS_` değişkeni, sabitlerden gelen değerlerin boşluktan ayrılmış bir listesidir. Bu değerlerden biri veya birkaçı virgülle değil, boşluklarla ayrılmış, işlevin parametre listesini belirtir. Örneğin:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

RGB renk değerini temsil eden 32 bit'lik bir tamsayı içeren bir liste `IFontDisp` yi ve ardından bir OLE yazı tipi nesnesinin arabirimine işaretçi belirtir.

`VTS_` Sabitlerin listesi için [bkz. EVENT_CUSTOM.](#event_custom)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxctl.h

## <a name="on_oleverb"></a><a name="on_oleverb"></a>ON_OLEVERB

Bu makro, özel bir fiili denetiminizin belirli bir üye işleviyle eşleyen bir ileti eşlemi tanımlar.

```cpp
ON_OLEVERB(idsVerbName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*idsVerbName*<br/>
Fiilin adının string kaynak kimliği.

*üyeFxn*<br/>
Fiil çağrıldığında çerçeve tarafından çağrılan işlev.

### <a name="remarks"></a>Açıklamalar

Kaynak düzenleyici, dize tablonuza eklenen özel fiil adları oluşturmak için kullanılabilir.

*üye Fxn* için fonksiyon prototipi:

```cpp
BOOL memberFxn(
   LPMSG    lpMsg,
   HWND     hWndParent,
   LPCRECT  lpRect);
```

*lpMsg*, *hWndParent*ve *lpRect* parametrelerinin değerleri `IOleObject::DoVerb` üye fonksiyonun karşılık gelen parametrelerinden alınır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxole.h

## <a name="on_stdoleverb"></a><a name="on_stdoleverb"></a>ON_STDOLEVERB

Standart bir fiilin varsayılan davranışını geçersiz kılmak için bu makroyu kullanın.

```cpp
ON_STDOLEVERB(iVerb, memberFxn)
```

### <a name="parameters"></a>Parametreler

*iFiil*<br/>
Geçersiz kılınan fiilin standart fiil dizini.

*üyeFxn*<br/>
Fiil çağrıldığında çerçeve tarafından çağrılan işlev.

### <a name="remarks"></a>Açıklamalar

Standart fiil dizini formun `OLEIVERB_`, ardından bir eylemdir. OLEIVERB_SHOW, OLEIVERB_HIDE ve OLEIVERB_UIACTIVATE standart fiillere örnektir.

*ÜyeFxn* parametresi olarak kullanılacak işlev prototipinin açıklaması için [ON_OLEVERB](#on_oleverb) bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** afxole.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
