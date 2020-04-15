---
title: DHTML Olay Eşlemeleri
ms.date: 11/04/2016
f1_keywords:
- vc.macros.shared
helpviewer_keywords:
- event map macros [MFC]
- DHTML [MFC], event map macros
- macros [MFC], DHTML event map
- DHTML events [MFC], event map
- DHTML events [MFC]
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
ms.openlocfilehash: 30c755b2901374cffab3ce91d0683811ef6624b6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365800"
---
# <a name="dhtml-event-maps"></a>DHTML Olay Eşlemeleri

Aşağıdaki makrolar DHTML olaylarını işlemek için kullanılabilir.

## <a name="dhtml-event-map-macros"></a>DHTML Olay Haritası Makroları

Aşağıdaki makrolar [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)türetilmiş sınıflarda DHTML olayları işlemek için kullanılabilir.

|||
|-|-|
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|DHTML olay haritasının başlangıcını işaretler.|
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|DHTML olay haritasının başlangıcını işaretler.|
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|DHTML olay haritasını bildirir.|
|[DHTML_EVENT](#dhtml_event)|Tek bir HTML öğesi için belge düzeyinde bir olayı işlemek için kullanılır.|
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|ActiveX denetimi tarafından ateşlenen bir olayı işlemek için kullanılır.|
|[DHTML_EVENT_CLASS](#dhtml_event_class)|Belirli bir CSS sınıfına sahip tüm HTML öğeleri için belge düzeyinde ki bir olayı işlemek için kullanılır.|
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|Öğe düzeyinde bir olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|`onafterupdate` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|`onbeforeupdate` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|`onblur` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|`onchange` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|`onclick` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|`ondataavailable` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|`ondatasetchanged` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|`ondatasetcomplete` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|`ondblclick` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|`ondragstart` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|`onerrorupdate` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|`onfilterchange` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|`onfocus` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|`onhelp` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|`onkeydown` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|`onkeypress` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|`onkeyup` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|`onmousedown` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|`onmousemove` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|`onmouseout` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|`onmouseover` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|`onmouseup` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|`onresize` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|`onrowenter` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|`onrowexit` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|`onselectstart` Olayı bir HTML öğesinden işlemek için kullanılır.|
|[DHTML_EVENT_TAG](#dhtml_event_tag)|Belirli bir HTML etiketine sahip tüm öğeler için belge düzeyindeki bir olayı işlemek için kullanılır.|
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|DHTML olay haritasının sonunu işaretler.|
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|DHTML olay haritasının sonunu işaretler. |

## <a name="url-event-map-macros"></a>URL Etkinlik Haritası Makroları

Aşağıdaki makrolar [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)türetilmiş sınıflarda DHTML olayları işlemek için kullanılabilir.

|||
|-|-|
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|Çok sayfalı DHTML ve URL olay haritasının başlangıcını işaretler.|
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|Katıştılmış bir DHTML olay haritasının başlangıcını işaretler.|
|[BEGIN_URL_ENTRIES](#begin_url_entries)|URL olay giriş haritasının başlangıcını işaretler.|
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|Çok sayfalı DHTML ve URL olay eşlesini bildirir.|
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|Çok sayfalı DHTML ve URL olay haritasının sonunu işaretler.|
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|Katıştılmış Bir DHTML olay haritasının sonunu işaretler.|
|[END_URL_ENTRIES](#end_url_entries)|URL olay giriş haritasının sonunu işaretler.|
|[URL_EVENT_ENTRY](#url_event_entry)|URL veya HTML kaynağını çok sayfalı iletişim kutusundaki bir sayfayla eşler.|

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="begin_dhtml_event_map"></a><a name="begin_dhtml_event_map"></a>BEGIN_DHTML_EVENT_MAP

`className`Tarafından tanımlanan sınıfın kaynak dosyasına yerleştirildiğinde DHTML olay haritasının başlangıcını işaretler.

```cpp
BEGIN_DHTML_EVENT_MAP(className)
```

### <a name="parameters"></a>Parametreler

*Classname*<br/>
DHTML olay eşlemini içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak [CDHtmlDialog'dan](../../mfc/reference/cdhtmldialog-class.md) türemelidir ve [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) makroyu sınıf tanımına dahil etmelidir.

### <a name="remarks"></a>Açıklamalar

Bir web sayfasında HTML öğeleri veya ActiveX denetimleri tarafından ateşlenen olayları sınıfınızdaki işleyici işlevlerine yönlendirmek için kullanılabilecek bilgileri `CDHtmlDialog` sağlamak için sınıfınıza bir DHTML olay haritası ekleyin.

sınıfın uygulama (.cpp) dosyasına BEGIN_DHTML_EVENT_MAP makroyu ve ardından sınıfın işleyeceğiniz olaylar için DHTML_EVENT makroları yerleştirin (örneğin, fare üzerinde olaylar için DHTML_EVENT_ONMOUSEOVER). Olay haritasının sonunu işaretlemek için [END_DHTML_EVENT_MAP](#end_dhtml_event_map) makroyu kullanın. Bu makrolar aşağıdaki işlevi uygular:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="begin_dhtml_event_map_inline"></a><a name="begin_dhtml_event_map_inline"></a>BEGIN_DHTML_EVENT_MAP_INLINE

*Sınıf Adı*için sınıf tanımı içinde DHTML olay haritasının başlangıcını işaretler.

```cpp
BEGIN_DHTML_EVENT_MAP_INLINE(className)
```

### <a name="parameters"></a>Parametreler

*Classname*<br/>
DHTML olay eşlemini içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak [CDHtmlDialog'dan](../../mfc/reference/cdhtmldialog-class.md) türemelidir ve [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) makroyu sınıf tanımına dahil etmelidir.

### <a name="remarks"></a>Açıklamalar

Bir web sayfasında HTML öğeleri veya ActiveX denetimleri tarafından ateşlenen olayları sınıfınızdaki işleyici işlevlerine yönlendirmek için kullanılabilecek bilgileri `CDHtmlDialog` sağlamak için sınıfınıza bir DHTML olay haritası ekleyin.

BEGIN_DHTML_EVENT_MAP makroyu sınıfın tanımı (.h) dosyasına ve ardından sınıfın işleyeceğiniz olaylar için makroDHTML_EVENT (örneğin, fare üzerinden olaylar için DHTML_EVENT_ONMOUSEOVER) yerleştirin. Olay haritasının sonunu işaretlemek için [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline) makroyu kullanın. Bu makrolar aşağıdaki işlevi uygular:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="declare_dhtml_event_map"></a><a name="declare_dhtml_event_map"></a>DECLARE_DHTML_EVENT_MAP

Bir DHTML olay haritasını sınıf tanımında bildirir.

```cpp
DECLARE_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

Bu makro [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)türetilmiş sınıfların tanımında kullanılacaktır.

Haritayı uygulamak için [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) veya [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) kullanın.

[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) aşağıdaki işlevi bildirir:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event"></a><a name="dhtml_event"></a>DHTML_EVENT

*ElemName*tarafından tanımlanan HTML öğesi tarafından ortaya çıkan *dispid* tarafından tanımlanan bir olay (belge düzeyinde) işler .

```cpp
DHTML_EVENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*Dıspıd*<br/>
Olayın DISPID ele alınacak.

*elemName*<br/>
Olayı kaynak sağlayan HTML öğesinin kimliğini tutan bir LPCWSTR veya belge olaylarını işlemek için NULL.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_axcontrol"></a><a name="dhtml_event_axcontrol"></a>DHTML_EVENT_AXCONTROL

*ControlName*tarafından tanımlanan ActiveX denetimi tarafından ateşlenen *dispid* tarafından tanımlanan olayı işler.

```cpp
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*Dıspıd*<br/>
Ele alınacak olayın sevk kimliği.

*Controlname*<br/>
Olayı ateşleten kontrol edilen denetimin HTML kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_class"></a><a name="dhtml_event_class"></a>DHTML_EVENT_CLASS

*ElemName*tarafından tanımlanan CSS sınıfı ile herhangi bir HTML öğesi tarafından kaynaklanan *dispid* tarafından tanımlanan bir olay (belge düzeyinde) işler (belge düzeyinde).

```cpp
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*Dıspıd*<br/>
Ele alınacak olayın sevk kimliği.

*elemName*<br/>
Olayı kaynak sağlayan HTML elemanlarının CSS sınıfını tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_element"></a><a name="dhtml_event_element"></a>DHTML_EVENT_ELEMENT

Tutamaçları *(elemName*tarafından tanımlanan eleman) *dispid*tarafından tanımlanan bir olay .

```cpp
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*Dıspıd*<br/>
Ele alınacak olayın sevk kimliği.

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

Bu makro, bukbilmeyen olayları işlemek için kullanılırsa, olayın kaynağı *elemName*tarafından tanımlanan öğe olacaktır.

Bu makro köpürme olaylarını işlemek için kullanılırsa, *elemName* tarafından tanımlanan öğe olayın kaynağı olmayabilir (kaynak *elemName*tarafından bulunan herhangi bir öğe olabilir).

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onafterupdate"></a><a name="dhtml_event_onafterupdate"></a>DHTML_EVENT_ONAFTERUPDATE

ElemName tarafından tanımlanan HTML `onafterupdate` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onbeforeupdate"></a><a name="dhtml_event_onbeforeupdate"></a>DHTML_EVENT_ONBEFOREUPDATE

ElemName tarafından tanımlanan HTML `onbeforeupdate` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onblur"></a><a name="dhtml_event_onblur"></a>DHTML_EVENT_ONBLUR

`onblur` Olayı işler (öğe düzeyinde). Bu bir nonbubbling olaydır.

```cpp
DHTML_EVENT_ONBLUR(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onchange"></a><a name="dhtml_event_onchange"></a>DHTML_EVENT_ONCHANGE

`onchange` Olayı işler (öğe düzeyinde). Bu bir nonbubbling olaydır.

```cpp
DHTML_EVENT_ONCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onclick"></a><a name="dhtml_event_onclick"></a>DHTML_EVENT_ONCLICK

ElemName tarafından tanımlanan HTML `onclick` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_ondataavailable"></a><a name="dhtml_event_ondataavailable"></a>DHTML_EVENT_ONDATAAVAILABLE

ElemName tarafından tanımlanan HTML `ondataavailable` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_ondatasetchanged"></a><a name="dhtml_event_ondatasetchanged"></a>DHTML_EVENT_ONDATASETCHANGED

ElemName tarafından tanımlanan HTML `ondatasetchanged` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_ondatasetcomplete"></a><a name="dhtml_event_ondatasetcomplete"></a>DHTML_EVENT_ONDATASETCOMPLETE

Tutamaçları (belge düzeyinde) `ondatasetcomplete` tarafından `elemName`tanımlanan HTML öğesi tarafından kaynaklanan olay.

```cpp
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_ondblclick"></a><a name="dhtml_event_ondblclick"></a>DHTML_EVENT_ONDBLCLICK

ElemName tarafından tanımlanan HTML `ondblclick` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_ondragstart"></a><a name="dhtml_event_ondragstart"></a>DHTML_EVENT_ONDRAGSTART

ElemName tarafından tanımlanan HTML `ondragstart` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onerrorupdate"></a><a name="dhtml_event_onerrorupdate"></a>DHTML_EVENT_ONERRORUPDATE

ElemName tarafından tanımlanan HTML `onerrorupdate` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onfilterchange"></a><a name="dhtml_event_onfilterchange"></a>DHTML_EVENT_ONFILTERCHANGE

ElemName tarafından tanımlanan HTML `onfilterchange` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onfocus"></a><a name="dhtml_event_onfocus"></a>DHTML_EVENT_ONFOCUS

`onfocus` Olayı işler (öğe düzeyinde). Bu bir nonbubbling olaydır.

```cpp
DHTML_EVENT_ONFOCUS(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onhelp"></a><a name="dhtml_event_onhelp"></a>DHTML_EVENT_ONHELP

ElemName tarafından tanımlanan HTML `onhelp` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONHELP(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onkeydown"></a><a name="dhtml_event_onkeydown"></a>DHTML_EVENT_ONKEYDOWN

ElemName tarafından tanımlanan HTML `onkeydown` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onkeypress"></a><a name="dhtml_event_onkeypress"></a>DHTML_EVENT_ONKEYPRESS

ElemName tarafından tanımlanan HTML `onkeypress` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onkeyup"></a><a name="dhtml_event_onkeyup"></a>DHTML_EVENT_ONKEYUP

ElemName tarafından tanımlanan HTML `onkeyup` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONKEYUP(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onmousedown"></a><a name="dhtml_event_onmousedown"></a>DHTML_EVENT_ONMOUSEDOWN

ElemName tarafından tanımlanan HTML `onmousedown` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onmousemove"></a><a name="dhtml_event_onmousemove"></a>DHTML_EVENT_ONMOUSEMOVE

ElemName tarafından tanımlanan HTML `onmousemove` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onmouseout"></a><a name="dhtml_event_onmouseout"></a>DHTML_EVENT_ONMOUSEOUT

ElemName tarafından tanımlanan HTML `onmouseout` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onmouseover"></a><a name="dhtml_event_onmouseover"></a>DHTML_EVENT_ONMOUSEOVER

ElemName tarafından tanımlanan HTML `onmouseover` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onmouseup"></a><a name="dhtml_event_onmouseup"></a>DHTML_EVENT_ONMOUSEUP

ElemName tarafından tanımlanan HTML `onmouseup` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onresize"></a><a name="dhtml_event_onresize"></a>DHTML_EVENT_ONRESIZE

`onresize` Olayı işler (öğe düzeyinde). Bu bir nonbubbling olaydır.

```cpp
DHTML_EVENT_ONRESIZE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onrowenter"></a><a name="dhtml_event_onrowenter"></a>DHTML_EVENT_ONROWENTER

ElemName tarafından tanımlanan HTML `onrowenter` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONROWENTER(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onrowexit"></a><a name="dhtml_event_onrowexit"></a>DHTML_EVENT_ONROWEXIT

ElemName tarafından tanımlanan HTML `onrowexit` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_onselectstart"></a><a name="dhtml_event_onselectstart"></a>DHTML_EVENT_ONSELECTSTART

ElemName tarafından tanımlanan HTML `onselectstart` öğesi tarafından ortaya çıkan *elemName*olay (belge düzeyinde) tanıtılır ..

```cpp
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak gösteren HTML öğesinin kimliğini tutan bir LPCWSTR.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="dhtml_event_tag"></a><a name="dhtml_event_tag"></a>DHTML_EVENT_TAG

ElemName tarafından tanımlanan HTML etiketine `dispid` sahip herhangi bir HTML öğesi tarafından *elemName*tanımlanan bir olayı (belge düzeyinde) işler (belge düzeyinde) işler.

```cpp
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*Dıspıd*<br/>
Ele alınacak olayın sevk kimliği.

*elemName*<br/>
Olayı kaynak gösteren HTML öğelerinin HTML etiketi.

*üyeFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınızdaki [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="end_dhtml_event_map"></a><a name="end_dhtml_event_map"></a>END_DHTML_EVENT_MAP

DHTML olay haritasının sonunu işaretler.

```cpp
END_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)ile birlikte kullanılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="begin_dhtml_url_event_map"></a><a name="begin_dhtml_url_event_map"></a>BEGIN_DHTML_URL_EVENT_MAP

Çok sayfalı bir iletişim kutusunda DHTML ve URL olay eşlemi tanımını başlatır.

```cpp
BEGIN_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

[CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)türetilmiş sınıf uygulama dosyasına BEGIN_DHTML_URL_EVENT_MAP koyun. [Katıştılmış DHTML olay haritaları](#begin_embed_dhtml_event_map) ve [URL girişleri](#begin_url_entries)ile izleyin ve ardından [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)ile kapatın. sınıf tanımına [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) makroyu ekleyin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="begin_embed_dhtml_event_map"></a><a name="begin_embed_dhtml_event_map"></a>BEGIN_EMBED_DHTML_EVENT_MAP

Çok sayfalı bir iletişim kutusunda katıştırılmış DHTML olay eşlemi tanımını başlatır.

```cpp
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)
```

### <a name="parameters"></a>Parametreler

*Classname*<br/>
Olay haritasını içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı [olarak CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)türemelidir. Katıştılmış DHTML olay eşlemi bir [DHTML ve URL olay haritasının](#begin_dhtml_url_event_map)içinde olmalıdır).

*Mapname*<br/>
Olay haritasını bu olan sayfayı belirtir. Bu, url veya HTML kaynağını tanımlayan [URL_EVENT_ENTRY](#url_event_entry) makrodaki *mapName* ile eşleşir.

### <a name="remarks"></a>Açıklamalar

Çok sayfalı bir DHTML iletişim kutusu, her biri DHTML olaylarını yükseltebilen birden çok HTML sayfasından oluştuğundan, olayları sayfa başına işleyicilerle eşlemek için katıştırılmış olay haritaları kullanılır.

DHTML ve URL olay haritasına katıştılmış olay eşlemleri, BEGIN_EMBED_DHTML_EVENT_MAP makrosu ve ardından [DHTML_EVENT](#dhtml_event) makro ve [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) makrodan oluşur.

Katıştırılmış her olay haritası, bir URL veya HTML kaynağına *mapmapName* (BEGIN_EMBED_DHTML_EVENT_MAP'de belirtilir) için karşılık gelen bir [URL olay girişi](#url_event_entry) gerektirir.

### <a name="example"></a>Örnek

[BEGIN_DHTML_URL_EVENT_MAP'daki](#begin_dhtml_url_event_map)örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="begin_url_entries"></a><a name="begin_url_entries"></a>BEGIN_URL_ENTRIES

Çok sayfalı bir iletişim kutusunda URL olay giriş haritası tanımını başlatır.

```cpp
BEGIN_URL_ENTRIES(className)
```

### <a name="parameters"></a>Parametreler

*Classname*<br/>
URL olay giriş eşlemini içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı [olarak CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)türemelidir. URL olay giriş haritası bir [DHTML ve URL olay haritasıiçinde](#begin_dhtml_url_event_map)olmalıdır).

### <a name="remarks"></a>Açıklamalar

Çok sayfalı bir DHTML iletişim kutusu birden çok HTML sayfasından oluştuğundan, URL olay girişleri URL'leri veya HTML kaynaklarını karşılık gelen [gömülü DHTML olay eşlemelerine](#begin_embed_dhtml_event_map)eşlemek için kullanılır. BEGIN_URL_ENTRIES ve [END_URL_ENTRIES](#end_url_entries) makrolar arasında URL_EVENT_ENTRY makrolar koyun.

### <a name="example"></a>Örnek

[BEGIN_DHTML_URL_EVENT_MAP'daki](#begin_dhtml_url_event_map)örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="declare_dhtml_url_event_map"></a><a name="declare_dhtml_url_event_map"></a>DECLARE_DHTML_URL_EVENT_MAP

Sınıf tanımında Bir DHTML ve URL olay haritası bildirir.

```cpp
DECLARE_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

Bu makro [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)türetilmiş sınıfların tanımında kullanılacaktır.

DHTML ve URL olay eşlemi, DHTML olaylarını sayfa başına işleyicilerle eşlemek için [gömülü DHTML olay eşlemleri](#begin_embed_dhtml_event_map) ve [URL olay girişleri](#begin_url_entries) içerir. Haritayı uygulamak için [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="end_dhtml_url_event_map"></a><a name="end_dhtml_url_event_map"></a>END_DHTML_URL_EVENT_MAP

DHTML ve URL olay haritasının sonunu işaretler.

```cpp
END_DHTML_URL_EVENT_MAP(className)
```

### <a name="parameters"></a>Parametreler

*Classname*<br/>
Olay haritasını içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı [olarak CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)türemelidir. Bu, ilgili [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) makrodaki *className* ile eşleşmelidir.

### <a name="example"></a>Örnek

[BEGIN_DHTML_URL_EVENT_MAP'daki](#begin_dhtml_url_event_map)örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="end_embed_dhtml_event_map"></a><a name="end_embed_dhtml_event_map"></a>END_EMBED_DHTML_EVENT_MAP

Katıştılmış Bir DHTML olay haritasının sonunu işaretler.

```cpp
END_EMBED_DHTML_EVENT_MAP()
```

### <a name="example"></a>Örnek

[BEGIN_DHTML_URL_EVENT_MAP'daki](#begin_dhtml_url_event_map)örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="end_url_entries"></a><a name="end_url_entries"></a>END_URL_ENTRIES

URL olay giriş haritasının sonunu işaretler.

```cpp
END_URL_ENTRIES()
```

### <a name="example"></a>Örnek

[BEGIN_DHTML_URL_EVENT_MAP'daki](#begin_dhtml_url_event_map)örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="url_event_entry"></a><a name="url_event_entry"></a>URL_EVENT_ENTRY

URL veya HTML kaynağını çok sayfalı iletişim kutusundaki bir sayfayla eşler.

```cpp
URL_EVENT_ENTRY(className, url,  mapName)
```

### <a name="parameters"></a>Parametreler

*Classname*<br/>
URL olay giriş eşlemini içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı [olarak CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)türemelidir. URL olay giriş haritası bir [DHTML ve URL olay haritasıiçinde](#begin_dhtml_url_event_map)olmalıdır).

*Url*<br/>
Sayfanın URL veya HTML kaynağı.

*Mapname*<br/>
URL'si *url*olan sayfayı belirtir. Bu, bu sayfadaki olayları eşleyen [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) makrodaki *mapName* ile eşleşir.

### <a name="remarks"></a>Açıklamalar

Sayfa bir HTML kaynağıysa, *url* kaynağın kimlik numarasının dize gösterimi olmalıdır (yani 123 veya ID_HTMLRES1 değil", "123").

Sayfa tanımlayıcısı, *mapName*, URL olay giriş haritaları gömülü DHTML olay haritaları bağlamak için kullanılan rasgele bir semboldür. Kapsamı DHTML ve URL olay haritasıile sınırlıdır.

### <a name="example"></a>Örnek

[BEGIN_DHTML_URL_EVENT_MAP'daki](#begin_dhtml_url_event_map)örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdhtml.h

## <a name="end_dhtml_event_map_inline"></a><a name="end_dhtml_event_map_inline"></a>END_DHTML_EVENT_MAP_INLINE

DHTML olay haritasının sonunu işaretler.

### <a name="syntax"></a>Sözdizimi

```cpp
END_DHTML_EVENT_MAP_INLINE( )
```

### <a name="remarks"></a>Açıklamalar

[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)ile birlikte kullanılmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdhtml.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](mfc-macros-and-globals.md)
