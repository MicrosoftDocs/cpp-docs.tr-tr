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
ms.openlocfilehash: 329b4176ad4d24651a41b5321c26318cf2af30e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547205"
---
# <a name="dhtml-event-maps"></a>DHTML Olay Eşlemeleri

Aşağıdaki makroları DHTML olaylarını işlemek için kullanılabilir.

## <a name="dhtml-event-map-macros"></a>DHTML olay eşleme makroları

Aşağıdaki makroları DHTML olayları işlemek için kullanılan [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-türetilmiş sınıflar.

|||
|-|-|
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|DHTML olay eşlemesi başlangıcını işaretler.|
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|DHTML olay eşlemesi başlangıcını işaretler.|
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|DHTML olay eşlemesi bildirir.|
|[DHTML_EVENT](#dhtml_event)|Tek bir HTML öğesi için belge düzeyindeki bir olayı işlemek için kullanılır.|
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|Bir ActiveX denetimi tarafından tetiklenen bir olayı işlemek için kullanılır.|
|[DHTML_EVENT_CLASS](#dhtml_event_class)|Belirli bir CSS sınıfı ile tüm HTML öğeleri için belge düzeyindeki bir olayı işlemek için kullanılır.|
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|Öğe düzeyinde bir olayı işlemek için kullanılır.|
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|İşlemek için kullanılan `onafterupdate` olaydan HTML öğesi.|
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|İşlemek için kullanılan `onbeforeupdate` olaydan HTML öğesi.|
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|İşlemek için kullanılan `onblur` olaydan HTML öğesi.|
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|İşlemek için kullanılan `onchange` olaydan HTML öğesi.|
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|İşlemek için kullanılan `onclick` olaydan HTML öğesi.|
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|İşlemek için kullanılan `ondataavailable` olaydan HTML öğesi.|
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|İşlemek için kullanılan `ondatasetchanged` olaydan HTML öğesi.|
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|İşlemek için kullanılan `ondatasetcomplete` olaydan HTML öğesi.|
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|İşlemek için kullanılan `ondblclick` olaydan HTML öğesi.|
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|İşlemek için kullanılan `ondragstart` olaydan HTML öğesi.|
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|İşlemek için kullanılan `onerrorupdate` olaydan HTML öğesi.|
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|İşlemek için kullanılan `onfilterchange` olaydan HTML öğesi.|
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|İşlemek için kullanılan `onfocus` olaydan HTML öğesi.|
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|İşlemek için kullanılan `onhelp` olaydan HTML öğesi.|
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|İşlemek için kullanılan `onkeydown` olaydan HTML öğesi.|
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|İşlemek için kullanılan `onkeypress` olaydan HTML öğesi.|
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|İşlemek için kullanılan `onkeyup` olaydan HTML öğesi.|
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|İşlemek için kullanılan `onmousedown` olaydan HTML öğesi.|
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|İşlemek için kullanılan `onmousemove` olaydan HTML öğesi.|
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|İşlemek için kullanılan `onmouseout` olaydan HTML öğesi.|
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|İşlemek için kullanılan `onmouseover` olaydan HTML öğesi.|
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|İşlemek için kullanılan `onmouseup` olaydan HTML öğesi.|
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|İşlemek için kullanılan `onresize` olaydan HTML öğesi.|
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|İşlemek için kullanılan `onrowenter` olaydan HTML öğesi.|
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|İşlemek için kullanılan `onrowexit` olaydan HTML öğesi.|
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|İşlemek için kullanılan `onselectstart` olaydan HTML öğesi.|
|[DHTML_EVENT_TAG](#dhtml_event_tag)|Belirli bir HTML etiketi ile tüm öğeler için belge düzeyindeki bir olayı işlemek için kullanılır.|
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|DHTML olay eşlemesi sonunu işaretler.|
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|DHTML olay eşlemesi sonunu işaretler. |

## <a name="url-event-map-macros"></a>URL olay eşleme makroları

Aşağıdaki makroları DHTML olayları işlemek için kullanılan [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-türetilmiş sınıflar.

|||
|-|-|
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|Birden çok sayfalı DHTML ve URL olay eşlemesi başlangıcını işaretler.|
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|Katıştırılmış bir DHTML olay eşlemesi başlangıcını işaretler.|
|[BEGIN_URL_ENTRIES](#begin_url_entries)|Bir URL olay girişi eşlemesi başlangıcını işaretler.|
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|Birden çok sayfalı DHTML ve URL olay eşlemesi bildirir.|
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|Birden çok sayfalı DHTML ve URL olay eşlemesi sonunu işaretler.|
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|Katıştırılmış bir DHTML olay eşlemesi sonunu işaretler.|
|[END_URL_ENTRIES](#end_url_entries)|Bir URL olay girişi eşlemesi sonunu işaretler.|
|[URL_EVENT_ENTRY](#url_event_entry)|Birden çok sayfa iletişim sayfasında URL veya HTML kaynak eşlenir.|

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="begin_dhtml_event_map"></a>  BEGIN_DHTML_EVENT_MAP

DHTML olay eşlemesi tarafından tanımlanan sınıfı için kaynak dosyasında yerleştirildiğinde başlangıcını işaretleyen `className`.

```
BEGIN_DHTML_EVENT_MAP(className)
```

### <a name="parameters"></a>Parametreler

*className*<br/>
DHTML olay eşlemesi içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak türetilmesi [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) ve [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) sınıf tanımı içinde makrosu.

### <a name="remarks"></a>Açıklamalar

DHTML olay eşlemesi bilgileri sağlamak için kendi sınıfınızı ekleyin `CDHtmlDialog` HTML öğeleri ya da ActiveX denetimlerini sınıfınızdaki işleyici işlevleri için bir web sayfasında tarafından tetiklenen rota olayları için kullanılabilir.

Begın_dhtml_event_map makrosu DHTML_EVENT makrosu olayları işlemek için sınıfı, ardından sınıf uygulama (.cpp) dosyası (örneğin, fareyi üzerine getirme olayları DHTML_EVENT_ONMOUSEOVER) yerleştirin. Kullanım [END_DHTML_EVENT_MAP](#end_dhtml_event_map) olay eşlemesi sonunu işaretlemek için makrosu. Bu makrolar aşağıdaki işlevi uygulayın:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="begin_dhtml_event_map_inline"></a>  BEGIN_DHTML_EVENT_MAP_INLINE

DHTML olay eşlemesi için sınıf tanımının içinde başlangıcını işaretleyen *className*.

```
BEGIN_DHTML_EVENT_MAP_INLINE(className)
```

### <a name="parameters"></a>Parametreler

*className*<br/>
DHTML olay eşlemesi içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak türetilmesi [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) ve [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) sınıf tanımı içinde makrosu.

### <a name="remarks"></a>Açıklamalar

DHTML olay eşlemesi bilgileri sağlamak için kendi sınıfınızı ekleyin `CDHtmlDialog` HTML öğeleri ya da ActiveX denetimlerini sınıfınızdaki işleyici işlevleri için bir web sayfasında tarafından tetiklenen rota olayları için kullanılabilir.

Begın_dhtml_event_map makrosu DHTML_EVENT makrosu olayları işlemek için sınıfı, ardından sınıfın tanımını (.h) dosyasına (örneğin, fareyi üzerine getirme olayları DHTML_EVENT_ONMOUSEOVER) koyun. Kullanım [end_dhtml_event_map_ınlıne](#end_dhtml_event_map_inline) olay eşlemesi sonunu işaretlemek için makrosu. Bu makrolar aşağıdaki işlevi uygulayın:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="declare_dhtml_event_map"></a>  DECLARE_DHTML_EVENT_MAP

DHTML olay eşlemesi bir sınıf tanımı içinde bildirir.

```
DECLARE_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

Bu Makro tanımında kullanılacak olan [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-türetilmiş sınıflar.

Kullanım [begın_dhtml_event_map](#begin_dhtml_event_map) veya [begın_dhtml_event_map_ınlıne](#begin_dhtml_event_map_inline) haritayı uygulamak için.

[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) aşağıdaki işlev bildirir:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event"></a>  DHTML_EVENT

(Belge düzeyinde) tarafından tanımlanan bir olay işleme *DISPID* tarafından tanımlanan HTML öğesi tarafından oluşturulan *elemName*.

```
DHTML_EVENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*DISPID*<br/>
DISPID olayın işlenmesi.

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR veya belge olayları işlemek için NULL.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_axcontrol"></a>  DHTML_EVENT_AXCONTROL

Tarafından tanımlanan olayını işler *DISPID* tarafından belirlenen ActiveX denetimi tarafından tetiklenen *MethodName*.

```
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*DISPID*<br/>
İşlenecek Olay gönderme kimliği.

*MethodName*<br/>
Olay tetiklenmeden denetimin HTML kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_class"></a>  DHTML_EVENT_CLASS

(Belge düzeyinde) tarafından tanımlanan bir olay işleme *DISPID* herhangi bir HTML öğesi tarafından tanımlanan CSS sınıf ile kaynaklanan *elemName*.

```
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*DISPID*<br/>
İşlenecek Olay gönderme kimliği.

*elemName*<br/>
Olay kaynağını belirleme HTML öğeleri CSS sınıfının bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_element"></a>  DHTML_EVENT_ELEMENT

İşleme (tarafından tanımlanan öğede *elemName*) tarafından tanımlanan bir olay *DISPID*.

```
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*DISPID*<br/>
İşlenecek Olay gönderme kimliği.

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

Bu makro nonbubbling olayları işlemek için kullanılan, olay kaynağı tarafından tanımlanan öğe olacaktır *elemName*.

Bu makro, tırmanma olayları işlemek için kullanılırsa, öğenin tanımlanan *elemName* olayının kaynağı, olmayabilir (kaynak tarafından bulunan herhangi bir öğe olabilecek *elemName*).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onafterupdate"></a>  DHTML_EVENT_ONAFTERUPDATE

İşleme (belge düzeyinde) `onafterupdate` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onbeforeupdate"></a>  DHTML_EVENT_ONBEFOREUPDATE

İşleme (belge düzeyinde) `onbeforeupdate` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onblur"></a>  DHTML_EVENT_ONBLUR

İşleme (öğe düzeyinde) `onblur` olay. Nonbubbling olay budur.

```
DHTML_EVENT_ONBLUR(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onchange"></a>  DHTML_EVENT_ONCHANGE

İşleme (öğe düzeyinde) `onchange` olay. Nonbubbling olay budur.

```
DHTML_EVENT_ONCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onclick"></a>  DHTML_EVENT_ONCLICK

İşleme (belge düzeyinde) `onclick` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```
DHTML_EVENT_ONCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_ondataavailable"></a>  DHTML_EVENT_ONDATAAVAILABLE

İşleme (belge düzeyinde) `ondataavailable` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_ondatasetchanged"></a>  DHTML_EVENT_ONDATASETCHANGED

İşleme (belge düzeyinde) `ondatasetchanged` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_ondatasetcomplete"></a>  DHTML_EVENT_ONDATASETCOMPLETE

İşleme (belge düzeyinde) `ondatasetcomplete` olay kaynağı tarafından tanımlanan HTML öğesi tarafından `elemName`.

```
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_ondblclick"></a>  DHTML_EVENT_ONDBLCLICK

İşleme (belge düzeyinde) `ondblclick` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_ondragstart"></a>  DHTML_EVENT_ONDRAGSTART

İşleme (belge düzeyinde) `ondragstart` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)
```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onerrorupdate"></a>  DHTML_EVENT_ONERRORUPDATE

İşleme (belge düzeyinde) `onerrorupdate` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onfilterchange"></a>  DHTML_EVENT_ONFILTERCHANGE

İşleme (belge düzeyinde) `onfilterchange` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onfocus"></a>  DHTML_EVENT_ONFOCUS

İşleme (öğe düzeyinde) `onfocus` olay. Nonbubbling olay budur.

```

DHTML_EVENT_ONFOCUS(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onhelp"></a>  DHTML_EVENT_ONHELP

İşleme (belge düzeyinde) `onhelp` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONHELP(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onkeydown"></a>  DHTML_EVENT_ONKEYDOWN

İşleme (belge düzeyinde) `onkeydown` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onkeypress"></a>  DHTML_EVENT_ONKEYPRESS

İşleme (belge düzeyinde) `onkeypress` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onkeyup"></a>  DHTML_EVENT_ONKEYUP

İşleme (belge düzeyinde) `onkeyup` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONKEYUP(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onmousedown"></a>  DHTML_EVENT_ONMOUSEDOWN

İşleme (belge düzeyinde) `onmousedown` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onmousemove"></a>  DHTML_EVENT_ONMOUSEMOVE

İşleme (belge düzeyinde) `onmousemove` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onmouseout"></a>  DHTML_EVENT_ONMOUSEOUT

İşleme (belge düzeyinde) `onmouseout` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onmouseover"></a>  DHTML_EVENT_ONMOUSEOVER

İşleme (belge düzeyinde) `onmouseover` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onmouseup"></a>  DHTML_EVENT_ONMOUSEUP

İşleme (belge düzeyinde) `onmouseup` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onresize"></a>  DHTML_EVENT_ONRESIZE

İşleme (öğe düzeyinde) `onresize` olay. Nonbubbling olay budur.

```

DHTML_EVENT_ONRESIZE(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onrowenter"></a>  DHTML_EVENT_ONROWENTER

İşleme (belge düzeyinde) `onrowenter` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONROWENTER(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onrowexit"></a>  DHTML_EVENT_ONROWEXIT

İşleme (belge düzeyinde) `onrowexit` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONROWEXIT(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_onselectstart"></a>  DHTML_EVENT_ONSELECTSTART

İşleme (belge düzeyinde) `onselectstart` olay kaynağı tarafından tanımlanan HTML öğesi tarafından *elemName*.

```

DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)

```

### <a name="parameters"></a>Parametreler

*elemName*<br/>
Olay kaynağını belirleme HTML öğesi kimliği bulunduran bir LPCWSTR.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="dhtml_event_tag"></a>  DHTML_EVENT_TAG

(Belge düzeyinde) tarafından tanımlanan bir olay işleme `dispid` tarafından tanımlanan HTML etiketi ile herhangi bir HTML öğesi tarafından oluşturulan *elemName*.

```
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parametreler

*DISPID*<br/>
İşlenecek Olay gönderme kimliği.

*elemName*<br/>
Olay kaynağını belirleme HTML öğeleri HTML etiketi.

*memberFxn*<br/>
Olay işleyicisi işlevi.

### <a name="remarks"></a>Açıklamalar

Bir giriş eklemek için bu makroyu kullanın [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızdaki.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="end_dhtml_event_map"></a>  END_DHTML_EVENT_MAP

DHTML olay eşlemesi sonunu işaretler.

```
END_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Açıklamalar

İle birlikte kullanılmalıdır [begın_dhtml_event_map](#begin_dhtml_event_map).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="begin_dhtml_url_event_map"></a>  BEGIN_DHTML_URL_EVENT_MAP

DHTML ve URL bir olay eşlemesi tanımını bir çok sayfalı iletişim kutusunda başlatır.

```
BEGIN_DHTML_URL_EVENT_MAP()

```

### <a name="remarks"></a>Açıklamalar

Begın_dhtml_url_event_map koymak uygulama dosyasında, [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-türetilmiş sınıf. İle takip [DHTML olay eşlemeleri katıştırılmış](#begin_embed_dhtml_event_map) ve [URL girişleri](#begin_url_entries)ve ardından kapatın [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map). Dahil [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) sınıf tanımı içine makrosu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="begin_embed_dhtml_event_map"></a>  BEGIN_EMBED_DHTML_EVENT_MAP

Bir çok sayfalı iletişim kutusunda bir katıştırılmış DHTML olay eşlemesi tanımını başlatır.

```
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)

```

### <a name="parameters"></a>Parametreler

*className*<br/>
Olay eşlemesi içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak türetilmesi [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Katıştırılmış DHTML olay eşlemesi içinde olmalıdır bir [DHTML ve URL olay eşlemesi](#begin_dhtml_url_event_map)).

*mapName*<br/>
Bu olayı harita sayfa belirtir. Bu eşleşen *mapName* içinde [URL_EVENT_ENTRY](#url_event_entry) makrosu gerçekten URL veya HTML kaynak tanımlama.

### <a name="remarks"></a>Açıklamalar

Her biri DHTML olayları tetikleyebilen, birden çok HTML sayfasını, bir çok sayfalı DHTML iletişim oluştuğundan katıştırılmış olay eşlemeleri olay işleyicilerini sayfa başına temelinde eşleştirmek için kullanılır.

DHTML ve URL bir olay eşlemesi içinde ekli olay eşlemeleri, arkasından bir begın_embed_dhtml_event_map makrosu oluşur [DHTML_EVENT](#dhtml_event) makroları ve [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) makrosu.

Karşılık gelen her ekli olay eşlemesi gerektirir [URL olay girişi](#url_event_entry) eşlemek için *mapName* (begın_embed_dhtml_event_map içinde belirtilen) için bir URL veya HTML kaynak.

### <a name="example"></a>Örnek

Örnekte bakın [begın_dhtml_url_event_map](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="begin_url_entries"></a>  BEGIN_URL_ENTRIES

Bir URL olay girişi eşlemesi tanımını bir çok sayfalı iletişim kutusunda başlatır.

```
BEGIN_URL_ENTRIES(className)

```

### <a name="parameters"></a>Parametreler

*className*<br/>
URL olay girişi eşlemesi içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak türetilmesi [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). URL olay girişi eşlemesi içinde olmalıdır bir [DHTML ve URL olay eşlemesi](#begin_dhtml_url_event_map)).

### <a name="remarks"></a>Açıklamalar

Bir çok sayfalı DHTML iletişim birden çok HTML sayfasını oluştuğundan, URL olay girişi URL'ler veya HTML eşleştirmek için kullanılır karşılık gelen kaynakları [DHTML olay eşlemeleri katıştırılmış](#begin_embed_dhtml_event_map). URL_EVENT_ENTRY makroları begın_url_entrıes arasında yerleştirin ve [end_url_entrıes](#end_url_entries) makroları.

### <a name="example"></a>Örnek

Örnekte bakın [begın_dhtml_url_event_map](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="declare_dhtml_url_event_map"></a>  DECLARE_DHTML_URL_EVENT_MAP

DHTML ve URL olay eşlemesi bir sınıf tanımı içinde bildirir.

```
DECLARE_DHTML_URL_EVENT_MAP()

```

### <a name="remarks"></a>Açıklamalar

Bu Makro tanımında kullanılacak olan [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-türetilmiş sınıflar.

DHTML ve URL bir olay eşlemesi içeren [DHTML olay eşlemeleri katıştırılmış](#begin_embed_dhtml_event_map) ve [URL olay girişi](#begin_url_entries) DHTML olay işleyicilerini sayfa başına temelinde eşlemek için. Kullanım [begın_dhtml_url_event_map](#begin_dhtml_url_event_map) haritayı uygulamak için.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="end_dhtml_url_event_map"></a>  END_DHTML_URL_EVENT_MAP

DHTML ve URL bir olay eşlemesi sonunu işaretler.

```
END_DHTML_URL_EVENT_MAP(className)

```

### <a name="parameters"></a>Parametreler

*className*<br/>
Olay eşlemesi içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak türetilmesi [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Bu eşleşmelidir *className* karşılık gelen [begın_dhtml_url_event_map](#begin_dhtml_url_event_map) makrosu.

### <a name="example"></a>Örnek

Örnekte bakın [begın_dhtml_url_event_map](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="end_embed_dhtml_event_map"></a>  END_EMBED_DHTML_EVENT_MAP

Katıştırılmış bir DHTML olay eşlemesi sonunu işaretler.

```
END_EMBED_DHTML_EVENT_MAP()

```

### <a name="example"></a>Örnek

Örnekte bakın [begın_dhtml_url_event_map](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="end_url_entries"></a>  END_URL_ENTRIES

Bir URL olay girişi eşlemesi sonunu işaretler.

```
END_URL_ENTRIES()

```

### <a name="example"></a>Örnek

Örnekte bakın [begın_dhtml_url_event_map](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="url_event_entry"></a>  URL_EVENT_ENTRY

Birden çok sayfa iletişim sayfasında URL veya HTML kaynak eşlenir.

```
URL_EVENT_ENTRY(className, url,  mapName)
```

### <a name="parameters"></a>Parametreler

*className*<br/>
URL olay girişi eşlemesi içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak türetilmesi [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). URL olay girişi eşlemesi içinde olmalıdır bir [DHTML ve URL olay eşlemesi](#begin_dhtml_url_event_map)).

*URL*<br/>
URL veya HTML kaynak sayfası.

*mapName*<br/>
Olan URL'sidir sayfayı belirtir *url*. Bu eşleşen *mapName* içinde [begın_embed_dhtml_event_map](#begin_embed_dhtml_event_map) olayları bu sayfadan eşleyen makrosu.

### <a name="remarks"></a>Açıklamalar

Bir HTML kaynak sayfasıysa *url* kaynak kimlik numarası (diğer bir deyişle, "123", yok 123 veya ID_HTMLRES1) dize gösterimi olmalıdır.

Sayfa tanımlayıcısı *mapName*, olan bağlantı için kullanılan rastgele bir sembol katıştırılmış DHTML olay eşlemeleri için URL olay girişi eşlemeleri. DHTML ve URL olay eşlemesi için kapsamda sınırlıdır.

### <a name="example"></a>Örnek

Örnekte bakın [begın_dhtml_url_event_map](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdhtml.h

##  <a name="end_dhtml_event_map_inline"></a>END_DHTML_EVENT_MAP_INLINE

DHTML olay eşlemesi sonunu işaretler.

### <a name="syntax"></a>Sözdizimi

```
END_DHTML_EVENT_MAP_INLINE( )
```

### <a name="remarks"></a>Açıklamalar

İle birlikte kullanılmalıdır [begın_dhtml_event_map_ınlıne](#begin_dhtml_event_map_inline).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdhtml.h

### <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](mfc-macros-and-globals.md)
