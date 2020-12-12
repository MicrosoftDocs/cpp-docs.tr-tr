---
description: Daha fazla bilgi için bkz. DHTML olay haritaları
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
ms.openlocfilehash: b9df8f1aa59472de033943efd28f5c688c61e706
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220129"
---
# <a name="dhtml-event-maps"></a>DHTML Olay Eşlemeleri

Aşağıdaki makrolar, DHTML olaylarını işlemek için kullanılabilir.

## <a name="dhtml-event-map-macros"></a>DHTML olay haritası makroları

Aşağıdaki makrolar, [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)ile TÜRETILMIŞ sınıflarda DHTML olaylarını işlemek için kullanılabilir.

|Ad|Açıklama|
|-|-|
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|DHTML olay eşlemesinin başlangıcını işaretler.|
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|DHTML olay eşlemesinin başlangıcını işaretler.|
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|DHTML olay haritasını bildirir.|
|[DHTML_EVENT](#dhtml_event)|Tek bir HTML öğesi için belge düzeyinde bir olayı işlemek için kullanılır.|
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|Bir ActiveX denetimi tarafından tetiklenen bir olayı işlemek için kullanılır.|
|[DHTML_EVENT_CLASS](#dhtml_event_class)|Belirli bir CSS sınıfına sahip tüm HTML öğeleri için belge düzeyindeki bir olayı işlemek için kullanılır.|
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|Öğe düzeyinde bir olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|`onafterupdate`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|`onbeforeupdate`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|`onblur`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|`onchange`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|`onclick`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|`ondataavailable`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|`ondatasetchanged`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|`ondatasetcomplete`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|`ondblclick`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|`ondragstart`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|`onerrorupdate`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|`onfilterchange`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|`onfocus`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|`onhelp`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|`onkeydown`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|`onkeypress`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|`onkeyup`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|`onmousedown`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|`onmousemove`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|`onmouseout`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|`onmouseover`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|`onmouseup`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|`onresize`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|`onrowenter`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|`onrowexit`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|`onselectstart`BIR HTML öğesinden olayı işlemek için kullanılır.|
|[DHTML_EVENT_TAG](#dhtml_event_tag)|Belirli bir HTML etiketine sahip tüm öğeler için belge düzeyindeki bir olayı işlemek için kullanılır.|
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|DHTML olay eşlemesinin sonunu işaretler.|
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|DHTML olay eşlemesinin sonunu işaretler. |

## <a name="url-event-map-macros"></a>URL olay eşleme makroları

Aşağıdaki makrolar [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)ile TÜRETILMIŞ sınıflarda DHTML olaylarını işlemek için kullanılabilir.

|Ad|Açıklama|
|-|-|
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|Çok sayfalı DHTML ve URL olay eşlemesinin başlangıcını işaretler.|
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|Katıştırılmış bir DHTML olay eşlemesinin başlangıcını işaretler.|
|[BEGIN_URL_ENTRIES](#begin_url_entries)|URL olay girişi eşlemesinin başlangıcını işaretler.|
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|Çok sayfalı DHTML ve URL olay haritasını bildirir.|
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|Çok sayfalı DHTML ve URL olay eşlemesinin sonunu işaretler.|
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|Katıştırılmış bir DHTML olay eşlemesinin sonunu işaretler.|
|[END_URL_ENTRIES](#end_url_entries)|URL olay girişi eşlemesinin sonunu işaretler.|
|[URL_EVENT_ENTRY](#url_event_entry)|Bir URL veya HTML kaynağını çok sayfalı iletişim kutusunda bir sayfayla eşleştirir.|

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="begin_dhtml_event_map"></a><a name="begin_dhtml_event_map"></a> BEGIN_DHTML_EVENT_MAP

Tarafından tanımlanan sınıfın kaynak dosyasına yerleştirildiğinde, DHTML olay eşlemesinin başlangıcını işaretler `className` .

```cpp
BEGIN_DHTML_EVENT_MAP(className)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
DHTML olay eşlemesini içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) 'dan türetilmelidir ve [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) makrosunu sınıf tanımına dahil etmelidir.

### <a name="remarks"></a>Açıklamalar

`CDHtmlDialog`HTML öğeleri veya bir Web sayfasındaki ActiveX denetimleri için tetiklenen olayları sınıfınıza ait işleyici işlevlerine yönlendirmek üzere kullanılabilecek bilgileri sağlamak için sınıfınıza BIR dhtml olay haritası ekleyin.

BEGIN_DHTML_EVENT_MAP makrosunu sınıfın uygulama (. cpp) dosyasına ve ardından sınıfın işleyeceği olaylar için DHTML_EVENT makroları (örneğin, gelme olayından olayları için DHTML_EVENT_ONMOUSEOVER) yerleştirin. Olay eşlemesinin sonunu işaretlemek için [END_DHTML_EVENT_MAP](#end_dhtml_event_map) makrosunu kullanın. Bu makrolar aşağıdaki işlevi uygular:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="begin_dhtml_event_map_inline"></a><a name="begin_dhtml_event_map_inline"></a> BEGIN_DHTML_EVENT_MAP_INLINE

, *ClassName* için sınıf tanımı içinde dhtml olay eşlemesinin başlangıcını işaretler.

```cpp
BEGIN_DHTML_EVENT_MAP_INLINE(className)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
DHTML olay eşlemesini içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) 'dan türetilmelidir ve [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) makrosunu sınıf tanımına dahil etmelidir.

### <a name="remarks"></a>Açıklamalar

`CDHtmlDialog`HTML öğeleri veya bir Web sayfasındaki ActiveX denetimleri için tetiklenen olayları sınıfınıza ait işleyici işlevlerine yönlendirmek üzere kullanılabilecek bilgileri sağlamak için sınıfınıza BIR dhtml olay haritası ekleyin.

BEGIN_DHTML_EVENT_MAP makrosunu sınıfın tanım (. h) dosyasına ve ardından sınıfın işleyeceği olaylar için DHTML_EVENT makroları (örneğin, gelme olayından olayları için DHTML_EVENT_ONMOUSEOVER) yerleştirin. Olay eşlemesinin sonunu işaretlemek için [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline) makrosunu kullanın. Bu makrolar aşağıdaki işlevi uygular:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="declare_dhtml_event_map"></a><a name="declare_dhtml_event_map"></a> DECLARE_DHTML_EVENT_MAP

Bir sınıf tanımında bir DHTML olay eşlemesi bildirir.

```cpp
DECLARE_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

Bu makro [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)ile türetilmiş sınıfların tanımında kullanılacaktır.

Eşlemeyi uygulamak için [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) veya [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) kullanın.

[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) aşağıdaki işlevi bildirir:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event"></a><a name="dhtml_event"></a> DHTML_EVENT

, *ElemName* tarafından tanımlanan html öğesi tarafından belirtilen bir *olay tarafından belirtilen* bir olayı (belge düzeyinde) işler.

```cpp
DHTML_EVENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
İşlenecek etkinliğin DISPID 'i.

*elemName*<br/>
Olayı kaynağı veya belge olaylarını işlemek için NULL olan HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_axcontrol"></a><a name="dhtml_event_axcontrol"></a> DHTML_EVENT_AXCONTROL

*ControlName* tarafından tanımlanan ActiveX denetimi tarafından tetiklenen *DISPID* tarafından tanımlanan olayı işler.

```cpp
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
İşlenecek etkinliğin dağıtım KIMLIĞI.

*Formdaki*<br/>
Olayı tetikbir denetimin HTML KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_class"></a><a name="dhtml_event_class"></a> DHTML_EVENT_CLASS

Bir HTML öğesi tarafından, *elemName* tarafından tanımlanan CSS sınıfı ile herhangi bir HTML öğesi tarafından tanımlanan *olay tarafından belirtilen* bir olayı (belge düzeyinde) işler.

```cpp
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
İşlenecek etkinliğin dağıtım KIMLIĞI.

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğelerinin CSS sınıfını tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_element"></a><a name="dhtml_event_element"></a> DHTML_EVENT_ELEMENT

*DISPID* tarafından tanımlanan bir olayı ( *elemName* tarafından tanımlanan öğede) işler.

```cpp
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
İşlenecek etkinliğin dağıtım KIMLIĞI.

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

Bu makro, kabarcıklanma olmayan olayları işlemek için kullanılırsa, etkinliğin kaynağı *elemName* tarafından tanımlanan öğe olur.

Bu makro, kabarcıklanma olaylarını işlemek için kullanılırsa, *elemName* tarafından tanımlanan öğe olayın kaynağı olamaz (kaynak, *elemName* tarafından içerilen herhangi bir öğe olabilir).

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onafterupdate"></a><a name="dhtml_event_onafterupdate"></a> DHTML_EVENT_ONAFTERUPDATE

(Belge düzeyinde) `onafterupdate` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onbeforeupdate"></a><a name="dhtml_event_onbeforeupdate"></a> DHTML_EVENT_ONBEFOREUPDATE

(Belge düzeyinde) `onbeforeupdate` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onblur"></a><a name="dhtml_event_onblur"></a> DHTML_EVENT_ONBLUR

Olayı (öğe düzeyinde) işler `onblur` . Bu, kabarcıklanma olmayan bir olaydır.

```cpp
DHTML_EVENT_ONBLUR(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onchange"></a><a name="dhtml_event_onchange"></a> DHTML_EVENT_ONCHANGE

Olayı (öğe düzeyinde) işler `onchange` . Bu, kabarcıklanma olmayan bir olaydır.

```cpp
DHTML_EVENT_ONCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onclick"></a><a name="dhtml_event_onclick"></a> DHTML_EVENT_ONCLICK

(Belge düzeyinde) `onclick` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_ondataavailable"></a><a name="dhtml_event_ondataavailable"></a> DHTML_EVENT_ONDATAAVAILABLE

(Belge düzeyinde) `ondataavailable` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_ondatasetchanged"></a><a name="dhtml_event_ondatasetchanged"></a> DHTML_EVENT_ONDATASETCHANGED

(Belge düzeyinde) `ondatasetchanged` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_ondatasetcomplete"></a><a name="dhtml_event_ondatasetcomplete"></a> DHTML_EVENT_ONDATASETCOMPLETE

`ondatasetcomplete`Tarafından tanımlanan html öğesi tarafından oluşturulan olayı (belge düzeyinde) işler `elemName` .

```cpp
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_ondblclick"></a><a name="dhtml_event_ondblclick"></a> DHTML_EVENT_ONDBLCLICK

(Belge düzeyinde) `ondblclick` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_ondragstart"></a><a name="dhtml_event_ondragstart"></a> DHTML_EVENT_ONDRAGSTART

(Belge düzeyinde) `ondragstart` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onerrorupdate"></a><a name="dhtml_event_onerrorupdate"></a> DHTML_EVENT_ONERRORUPDATE

(Belge düzeyinde) `onerrorupdate` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onfilterchange"></a><a name="dhtml_event_onfilterchange"></a> DHTML_EVENT_ONFILTERCHANGE

(Belge düzeyinde) `onfilterchange` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onfocus"></a><a name="dhtml_event_onfocus"></a> DHTML_EVENT_ONFOCUS

Olayı (öğe düzeyinde) işler `onfocus` . Bu, kabarcıklanma olmayan bir olaydır.

```cpp
DHTML_EVENT_ONFOCUS(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onhelp"></a><a name="dhtml_event_onhelp"></a> DHTML_EVENT_ONHELP

(Belge düzeyinde) `onhelp` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONHELP(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onkeydown"></a><a name="dhtml_event_onkeydown"></a> DHTML_EVENT_ONKEYDOWN

(Belge düzeyinde) `onkeydown` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onkeypress"></a><a name="dhtml_event_onkeypress"></a> DHTML_EVENT_ONKEYPRESS

(Belge düzeyinde) `onkeypress` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onkeyup"></a><a name="dhtml_event_onkeyup"></a> DHTML_EVENT_ONKEYUP

(Belge düzeyinde) `onkeyup` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONKEYUP(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onmousedown"></a><a name="dhtml_event_onmousedown"></a> DHTML_EVENT_ONMOUSEDOWN

(Belge düzeyinde) `onmousedown` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onmousemove"></a><a name="dhtml_event_onmousemove"></a> DHTML_EVENT_ONMOUSEMOVE

(Belge düzeyinde) `onmousemove` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onmouseout"></a><a name="dhtml_event_onmouseout"></a> DHTML_EVENT_ONMOUSEOUT

(Belge düzeyinde) `onmouseout` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onmouseover"></a><a name="dhtml_event_onmouseover"></a> DHTML_EVENT_ONMOUSEOVER

(Belge düzeyinde) `onmouseover` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onmouseup"></a><a name="dhtml_event_onmouseup"></a> DHTML_EVENT_ONMOUSEUP

(Belge düzeyinde) `onmouseup` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onresize"></a><a name="dhtml_event_onresize"></a> DHTML_EVENT_ONRESIZE

Olayı (öğe düzeyinde) işler `onresize` . Bu, kabarcıklanma olmayan bir olaydır.

```cpp
DHTML_EVENT_ONRESIZE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onrowenter"></a><a name="dhtml_event_onrowenter"></a> DHTML_EVENT_ONROWENTER

(Belge düzeyinde) `onrowenter` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONROWENTER(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onrowexit"></a><a name="dhtml_event_onrowexit"></a> DHTML_EVENT_ONROWEXIT

(Belge düzeyinde) `onrowexit` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_onselectstart"></a><a name="dhtml_event_onselectstart"></a> DHTML_EVENT_ONSELECTSTART

(Belge düzeyinde) `onselectstart` olayı, *elemName* tarafından tanımlanan html öğesi tarafından kaynaklı.

```cpp
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olayı kaynak olarak içeren HTML öğesinin KIMLIĞINI tutan bir LPCWSTR.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="dhtml_event_tag"></a><a name="dhtml_event_tag"></a> DHTML_EVENT_TAG

Tarafından tanımlanan bir olayı, `dispid` HTML etiketiyle birlikte *elemName* tarafından tanımlanan bir HTML öğesi tarafından belirlenen bir olaydır.

```cpp
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
İşlenecek etkinliğin dağıtım KIMLIĞI.

*elemName*<br/>
Olayı kaynak olarak belirleme HTML öğelerinin HTML etiketi.

*memberFxn*<br/>
Olay için işleyici işlevi.

### <a name="remarks"></a>Açıklamalar

Sınıfınıza [DHTML olay haritasına](#begin_dhtml_event_map_inline) bir giriş eklemek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="end_dhtml_event_map"></a><a name="end_dhtml_event_map"></a> END_DHTML_EVENT_MAP

DHTML olay eşlemesinin sonunu işaretler.

```cpp
END_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)ile birlikte kullanılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="begin_dhtml_url_event_map"></a><a name="begin_dhtml_url_event_map"></a> BEGIN_DHTML_URL_EVENT_MAP

Çok sayfalı iletişim kutusunda bir DHTML ve URL olay eşlemesinin tanımını başlatır.

```cpp
BEGIN_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

BEGIN_DHTML_URL_EVENT_MAP [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)ile türetilmiş sınıfınızın uygulama dosyasına koyun. [KATıŞTıRıLMıŞ dhtml olay haritaları](#begin_embed_dhtml_event_map) ve [URL girişleri](#begin_url_entries)ile izleyin ve [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)ile kapatın. Sınıf tanımına [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) makrosunu ekleyin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="begin_embed_dhtml_event_map"></a><a name="begin_embed_dhtml_event_map"></a> BEGIN_EMBED_DHTML_EVENT_MAP

Birden çok sayfalı iletişim kutusunda gömülü bir DHTML olay eşlemesinin tanımını başlatır.

```cpp
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Olay eşlemesini içeren sınıfın adı. Bu sınıf, [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)aracılığıyla doğrudan veya dolaylı olarak türetilmelidir. Katıştırılmış DHTML olay eşlemesi bir [DHTML ve URL olay eşlemesi](#begin_dhtml_url_event_map)içinde olmalıdır).

*mapName*<br/>
Olay haritasını bu olan sayfayı belirtir. Bu, [URL_EVENT_ENTRY](#url_event_entry) Makrodaki *MapName* Ile eşleşir ve aslında URL veya HTML kaynağını tanımlar.

### <a name="remarks"></a>Açıklamalar

Çok sayfalı bir DHTML iletişim kutusu, her biri DHTML olayları oluşturabilen birden çok HTML sayfasından oluşuyorsa, ekli olay haritaları, olayları her sayfa temelinde işleyicilerle eşlemek için kullanılır.

Bir DHTML ve URL olay haritası içindeki katıştırılmış olay haritaları, [DHTML_EVENT](#dhtml_event) makroları ve bir [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) makrosu tarafından izlenen BEGIN_EMBED_DHTML_EVENT_MAP bir makrodan oluşur.

Her katıştırılmış olay eşlemesi, *MapName* 'i (BEGIN_EMBED_DHTML_EVENT_MAP olarak belirtilen) bir URL veya HTML kaynağına eşlemek için karşılık gelen bir [URL olay girişi](#url_event_entry) gerektirir.

### <a name="example"></a>Örnek

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="begin_url_entries"></a><a name="begin_url_entries"></a> BEGIN_URL_ENTRIES

Çok sayfalı iletişim kutusunda URL olay girişi eşlemesinin tanımını başlatır.

```cpp
BEGIN_URL_ENTRIES(className)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
URL olay girdisi eşlemesini içeren sınıfın adı. Bu sınıf, [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)aracılığıyla doğrudan veya dolaylı olarak türetilmelidir. URL olay girişi eşlemesi bir [DHTML ve URL olay eşlemesi](#begin_dhtml_url_event_map)içinde olmalıdır).

### <a name="remarks"></a>Açıklamalar

Çok sayfalı bir DHTML iletişim kutusu birden çok HTML sayfası içerdiğinden, URL 'Leri veya HTML kaynaklarını ilgili [KATıŞTıRıLMıŞ dhtml olay eşlemeleriyle](#begin_embed_dhtml_event_map)eşlemek için URL olay girişleri kullanılır. URL_EVENT_ENTRY makroları BEGIN_URL_ENTRIES ve [END_URL_ENTRIES](#end_url_entries) makroları arasına yerleştirin.

### <a name="example"></a>Örnek

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="declare_dhtml_url_event_map"></a><a name="declare_dhtml_url_event_map"></a> DECLARE_DHTML_URL_EVENT_MAP

Bir sınıf tanımında DHTML ve URL olay eşlemesi bildirir.

```cpp
DECLARE_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

Bu makro, [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)ile türetilmiş sınıfların tanımında kullanılacaktır.

DHTML ve URL olay haritası, DHTML olaylarını her sayfa temelinde işleyicilerle eşlemek için [KATıŞTıRıLMıŞ dhtml olay haritaları](#begin_embed_dhtml_event_map) ve [URL olay girişleri](#begin_url_entries) içerir. Eşlemeyi uygulamak için [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) kullanın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="end_dhtml_url_event_map"></a><a name="end_dhtml_url_event_map"></a> END_DHTML_URL_EVENT_MAP

Bir DHTML ve URL olay eşlemesinin sonunu işaretler.

```cpp
END_DHTML_URL_EVENT_MAP(className)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Olay eşlemesini içeren sınıfın adı. Bu sınıf, [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)aracılığıyla doğrudan veya dolaylı olarak türetilmelidir. Bu, karşılık gelen [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) makrosunda *ClassName* ile eşleşmelidir.

### <a name="example"></a>Örnek

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="end_embed_dhtml_event_map"></a><a name="end_embed_dhtml_event_map"></a> END_EMBED_DHTML_EVENT_MAP

Katıştırılmış bir DHTML olay eşlemesinin sonunu işaretler.

```cpp
END_EMBED_DHTML_EVENT_MAP()
```

### <a name="example"></a>Örnek

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="end_url_entries"></a><a name="end_url_entries"></a> END_URL_ENTRIES

URL olay girişi eşlemesinin sonunu işaretler.

```cpp
END_URL_ENTRIES()
```

### <a name="example"></a>Örnek

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="url_event_entry"></a><a name="url_event_entry"></a> URL_EVENT_ENTRY

Bir URL veya HTML kaynağını çok sayfalı iletişim kutusunda bir sayfayla eşleştirir.

```cpp
URL_EVENT_ENTRY(className, url,  mapName)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
URL olay girdisi eşlemesini içeren sınıfın adı. Bu sınıf, [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)aracılığıyla doğrudan veya dolaylı olarak türetilmelidir. URL olay girişi eşlemesi bir [DHTML ve URL olay eşlemesi](#begin_dhtml_url_event_map)içinde olmalıdır).

*'deki*<br/>
Sayfanın URL 'SI veya HTML kaynağı.

*mapName*<br/>
URL *'si URL* olan sayfayı belirtir. Bu, olayları bu sayfadan eşleyen [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) makrosunda *MapName* ile eşleşir.

### <a name="remarks"></a>Açıklamalar

Sayfa bir HTML kaynağı ise, *URL* kaynağın kimlik numarasının dize temsili olmalıdır (yani, "123", 123 veya ID_HTMLRES1).

Sayfa tanımlayıcısı, *MapName*, katıştırılmış dhtml olay haritalarını URL olay girişi eşlemelerine bağlamak için kullanılan rastgele bir simgedir. Kapsam, DHTML ve URL olay eşlemesi ile sınırlıdır.

### <a name="example"></a>Örnek

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdhtml. h

## <a name="end_dhtml_event_map_inline"></a><a name="end_dhtml_event_map_inline"></a> END_DHTML_EVENT_MAP_INLINE

DHTML olay eşlemesinin sonunu işaretler.

### <a name="syntax"></a>Syntax

```cpp
END_DHTML_EVENT_MAP_INLINE( )
```

### <a name="remarks"></a>Açıklamalar

[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)ile birlikte kullanılmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdhtml. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)
