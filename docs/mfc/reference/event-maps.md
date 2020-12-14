---
description: 'Daha fazla bilgi edinin: olay haritaları'
title: Olay Eşlemeleri
ms.date: 09/07/2019
helpviewer_keywords:
- event maps [MFC]
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
ms.openlocfilehash: f3a6e949a4dc40927fc8946610707fbb404a400b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219856"
---
# <a name="event-maps"></a>Olay Eşlemeleri

Her denetim, kapsayıcısını (denetim geliştiricisi tarafından belirlenir) bir işlemin (örneğin, bir tuş vuruşu, fare tıklaması veya denetimin durumunda bir değişiklik) meydana geldiğini bildirdiğinde olay tetikleme işlevini çağırır. Bu işlev, ilgili olayı tetikleyerek denetim kapsayıcısını bazı önemli bir eylemin oluştuğunu bildirir.

Microsoft Foundation Class Kitaplığı, olayları tetikiçin iyileştirilmiş bir programlama modeli sunar. Bu modelde, belirli bir denetim için hangi işlevlerin hangi işlevleri tetiklediği belirlemek için "olay haritaları" kullanılır. Olay haritaları her olay için bir makro içerir. Örneğin, bir stok tıklama olayını harekete uygulayan bir olay haritası şuna benzeyebilir:

[!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]

`EVENT_STOCK_CLICK`Makro, denetimin fare tıklaması her algıladığında bir stok tıklama olayını tetikleyeceği anlamına gelir. Diğer stok olaylarının daha ayrıntılı bir listesi için bkz. [ActiveX denetimleri: olaylar](../../mfc/mfc-activex-controls-events.md). Makrolar özel olayları göstermek için de kullanılabilir.

Olay eşleme makroları önemli olsa da, genellikle bunları doğrudan eklemeyin. Bunun nedeni, **Özellikler** penceresinin ( **sınıf görünümü**) olay tetikleme işlevlerini olaylar ile ilişkilendirmek için kullandığınızda kaynak dosyalarınızda otomatik olarak olay eşleme girişleri oluşturmasıdır. Herhangi bir olay eşleme girişi düzenlemek veya eklemek istediğiniz zaman, **Özellikler** penceresini kullanabilirsiniz.

MFC, olay eşlemelerini desteklemek için aşağıdaki makroları sağlar:

## <a name="event-map-macros"></a>Olay haritası makroları

### <a name="event-map-declaration-and-demarcation"></a>Olay eşleme bildirimi ve demarcation

|Ad|Açıklama|
|-|-|
|[DECLARE_EVENT_MAP](#declare_event_map)|Olay eşlemesinin olayları olay tetikleme işlevlerine eşlemek için bir sınıfta kullanılacağını bildirir (sınıf bildiriminde kullanılması gerekir).|
|[BEGIN_EVENT_MAP](#begin_event_map)|Bir olay eşlemesinin tanımını başlatır (sınıf uygulamasında kullanılması gerekir).|
|[END_EVENT_MAP](#end_event_map)|Bir olay eşlemesinin tanımını sonlandırır (sınıf uygulamasında kullanılması gerekir).|

### <a name="event-mapping-macros"></a>Olay eşleme makroları

|Ad|Açıklama|
|-|-|
|[EVENT_CUSTOM](#event_custom)|Hangi olay tetikleme işlevinin belirtilen olayı tetikleyemedi belirtir.|
|[EVENT_CUSTOM_ID](#event_custom_id)|Belirtilen bir dağıtım KIMLIĞIYLE, belirtilen olayı hangi olay tetikleme işlevinin tetiklendirilecektir.|

### <a name="message-mapping-macros"></a>İleti eşleme makroları

|Ad|Açıklama|
|-|-|
|[ON_OLEVERB](#on_oleverb)|OLE denetimi tarafından işlenen özel bir fiil gösterir.|
|[ON_STDOLEVERB](#on_stdoleverb)|OLE denetiminin standart bir fiil eşlemesini geçersiz kılar.|

## <a name="declare_event_map"></a><a name="declare_event_map"></a> DECLARE_EVENT_MAP

`COleControl`Programınızdaki her türetilmiş sınıf, denetiminizin tetikleneceği olayları belirtmek için bir olay eşlemesi sağlayabilir.

```cpp
DECLARE_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

Sınıf bildirimindeki sonundaki DECLARE_EVENT_MAP makrosunu kullanın. Ardından, sınıfının üye işlevlerini tanımlayan. cpp dosyasında, denetim olaylarının her biri için makro girişlerini ve olay listesinin sonunu bildirmek için END_EVENT_MAP makrosunu BEGIN_EVENT_MAP kullanın.

Olay haritaları hakkında daha fazla bilgi için bkz. [ActiveX denetimleri: olaylar](../../mfc/mfc-activex-controls-events.md).

### <a name="requirements"></a>Gereksinimler

**Başlık** afxctl. h

## <a name="begin_event_map"></a><a name="begin_event_map"></a> BEGIN_EVENT_MAP

Olay haritaınızın tanımını başlatır.

```cpp
BEGIN_EVENT_MAP(theClass,  baseClass)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Olay haritasını bu olan denetim sınıfının adını belirtir.

*baseClass*<br/>
Sınıfın temel sınıfının adını *belirtir.*

### <a name="remarks"></a>Açıklamalar

Sınıfınız için üye işlevlerini tanımlayan uygulama (. cpp) dosyasında, olay haritasını BEGIN_EVENT_MAP makroyla başlatın, sonra olaylarınızın her biri için makro girişlerini ekleyin ve olay haritasını END_EVENT_MAP makroyla doldurun.

Olay haritaları ve BEGIN_EVENT_MAP makrosu hakkında daha fazla bilgi için, [ActiveX denetimleri: olaylar](../../mfc/mfc-activex-controls-events.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

**Başlık** afxctl. h

## <a name="end_event_map"></a><a name="end_event_map"></a> END_EVENT_MAP

Olay haritaınızın tanımını sonlandırmak için END_EVENT_MAP makrosunu kullanın.

```cpp
END_EVENT_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Başlık** afxctl. h

## <a name="event_custom"></a><a name="event_custom"></a> EVENT_CUSTOM

Özel bir olay için bir olay eşleme girişi tanımlar.

```cpp
EVENT_CUSTOM(pszName, pfnFire,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*pszName*<br/>
Olayın adı.

*pfnFire*<br/>
Olay tetikleme işlevinin adı.

*vtsParams*<br/>
İşlevin parametre listesini belirten bir veya daha fazla sabitin boşlukla ayrılmış listesi.

### <a name="remarks"></a>Açıklamalar

*VtsParams* parametresi, sabitlerin değerlerinin boşlukla ayrılmış bir listesidir `VTS_` . Boşluklarla (virgüller değil) ayrılmış bir veya daha fazla değer, işlevin parametre listesini belirtir. Örneğin:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

bir RGB renk değerini temsil eden 32 bitlik bir tamsayı ve ardından `IFontDisp` OLE yazı tipi nesnesinin arabirimine yönelik bir işaretçi içeren bir liste belirtir.

`VTS_`Sabitler ve anlamları aşağıdaki gibidir:

|Sembol|Parametre türü|
|------------|--------------------|
|VTS_I2|**`short`**|
|VTS_I4|**`long`**|
|VTS_R4|**`float`**|
|VTS_R8|**`double`**|
|VTS_COLOR|OLE_COLOR|
|VTS_CY|PARA BİRİMİ|
|VTS_DATE|DATE|
|VTS_BSTR|**`const`**__char \*__|
|VTS_DISPATCH|LPDISPATCH|
|VTS_FONT|`IFontDispatch*`|
|VTS_HANDLE|TUTAMAÇLARDAN|
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
> Değişken veri sabitine bir işaretçi sağlayan VTS_FONT ve VTS_PICTURE dışında tüm değişken türleri için ek değişken sabitleri tanımlanmıştır. Bu sabitler, kuralı kullanılarak adlandırılmaktadır `VTS_Pconstantname` . Örneğin, VTS_PCOLOR VTS_COLOR sabiti için bir işaretçidir.

### <a name="requirements"></a>Gereksinimler

**Başlık** afxctl. h

## <a name="event_custom_id"></a><a name="event_custom_id"></a> EVENT_CUSTOM_ID

*DISPID* tarafından BELIRTILEN dağıtım kimliğine ait özel bir olay için olay tetikleme işlevini tanımlar.

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

*dı*<br/>
Olayı tetikleyerek denetim tarafından kullanılan dağıtım KIMLIĞI.

*pfnFire*<br/>
Olay tetikleme işlevinin adı.

*vtsParams*<br/>
Olay harekete geçirildiğinde denetim kapsayıcısına geçirilen parametrelerin değişken listesi.

### <a name="remarks"></a>Açıklamalar

*VtsParams* bağımsız değişkeni, sabitlerin değerlerinin boşlukla ayrılmış bir listesidir `VTS_` . Bu değerlerden bir veya daha fazla virgül değil, boşluklarla ayrılmış, işlevin parametre listesini belirtir. Örneğin:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

bir RGB renk değerini temsil eden 32 bitlik bir tamsayı ve ardından `IFontDisp` OLE yazı tipi nesnesinin arabirimine yönelik bir işaretçi içeren bir liste belirtir.

Sabitlerin listesi için `VTS_` bkz. [event_custom](#event_custom).

### <a name="requirements"></a>Gereksinimler

**Başlık** afxctl. h

## <a name="on_oleverb"></a><a name="on_oleverb"></a> ON_OLEVERB

Bu makro özel bir fiili, denetiminizin belirli bir üye işlevine eşleyen bir ileti eşleme girişi tanımlar.

```cpp
ON_OLEVERB(idsVerbName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*idsVerbName*<br/>
Fiil adının dize kaynak KIMLIĞI.

*memberFxn*<br/>
Fiil çağrıldığında Framework tarafından çağrılan işlev.

### <a name="remarks"></a>Açıklamalar

Kaynak Düzenleyicisi, dize tablonuza eklenen özel fiil adları oluşturmak için kullanılabilir.

*MemberFxn* için işlev prototipi:

```cpp
BOOL memberFxn(
   LPMSG    lpMsg,
   HWND     hWndParent,
   LPCRECT  lpRect);
```

*LpMsg*, *HWndParent* ve *lpRect* parametrelerinin değerleri, üye işlevinin karşılık gelen parametrelerinden alınır `IOleObject::DoVerb` .

### <a name="requirements"></a>Gereksinimler

**Başlık** afxole. h

## <a name="on_stdoleverb"></a><a name="on_stdoleverb"></a> ON_STDOLEVERB

Standart fiilin varsayılan davranışını geçersiz kılmak için bu makroyu kullanın.

```cpp
ON_STDOLEVERB(iVerb, memberFxn)
```

### <a name="parameters"></a>Parametreler

*ıverb*<br/>
Geçersiz kılınmakta olan fiil için standart fiil dizini.

*memberFxn*<br/>
Fiil çağrıldığında Framework tarafından çağrılan işlev.

### <a name="remarks"></a>Açıklamalar

Standart fiil dizini, `OLEIVERB_` bir eylem tarafından izlenir. OLEIVERB_SHOW, OLEIVERB_HIDE ve OLEIVERB_UIACTIVATE Standart fiillerin bazı örnekleridir.

*MemberFxn* parametresi olarak kullanılacak işlev prototipini açıklaması için [ON_OLEVERB](#on_oleverb) bakın.

### <a name="requirements"></a>Gereksinimler

**Başlık** afxole. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
