---
title: "DHTML olay eşlemeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.macros.shared
dev_langs: C++
helpviewer_keywords:
- event map macros [MFC]
- DHTML [MFC], event map macros
- macros [MFC], DHTML event map
- DHTML events [MFC], event map
- DHTML events [MFC]
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5588f716cfc7aec0caba7fd6943770353e7b2b1e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dhtml-event-maps"></a>DHTML Olay Eşlemeleri
Aşağıdaki makroları DHTML olayları işlemek için kullanılabilir.  
  
## <a name="dhtml-event-map-macros"></a>DHTML olay eşleme makroları  
 Aşağıdaki makroları DHTML olayları işlemek için kullanılan [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-türetilmiş sınıfları.  
  
|||  
|-|-|  
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|DHTML olay eşlemesi başlangıcını işaretler.|  
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|DHTML olay eşlemesi başlangıcını işaretler.|  
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|DHTML olay eşlemesi bildirir.|  
|[DHTML_EVENT](#dhtml_event)|Tek bir HTML öğesi için belge düzeyinde bir olayını işlemek için kullanılır.|  
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|ActiveX denetimi tarafından tetiklenen bir olayı işlemek için kullanılır.|  
|[DHTML_EVENT_CLASS](#dhtml_event_class)|Belirli bir CSS sınıfı ile tüm HTML öğeleri için belge düzeyinde bir olayını işlemek için kullanılır.|  
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|Öğe düzeyinde bir olayını işlemek için kullanılır.|  
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|İşlemek için kullanılan **onafterupdate** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|İşlemek için kullanılan **onbeforeupdate** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|İşlemek için kullanılan **onblur** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|İşlemek için kullanılan `onchange` bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|İşlemek için kullanılan **onclick** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|İşlemek için kullanılan **ondataavailable** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|İşlemek için kullanılan **onDataSetComplete** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|İşlemek için kullanılan **satır almayı** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|İşlemek için kullanılan **ondblclick** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|İşlemek için kullanılan **ondragstart** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|İşlemek için kullanılan **onerrorupdate** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|İşlemek için kullanılan **onfilterchange** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|İşlemek için kullanılan **onfocus** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|İşlemek için kullanılan `onhelp` bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|İşlemek için kullanılan **onkeydown** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|İşlemek için kullanılan **onkeypress** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|İşlemek için kullanılan **onkeyup** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|İşlemek için kullanılan **onmousedown** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|İşlemek için kullanılan `onmousemove` bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|İşlemek için kullanılan **onmouseout** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|İşlemek için kullanılan **onmouseover** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|İşlemek için kullanılan **onmouseup** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|İşlemek için kullanılan **onresize** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|İşlemek için kullanılan **onrowenter** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|İşlemek için kullanılan **onrowexit** bir HTML öğesi olayından.|  
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|İşlemek için kullanılan **onselectstart** bir HTML öğesi olayından.|  
|[DHTML_EVENT_TAG](#dhtml_event_tag)|Belirli bir HTML etiketi ile tüm öğeler için belge düzeyinde bir olayını işlemek için kullanılır.|  
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|DHTML olay eşlemesi sonunu işaretler.|  
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|DHTML olay eşlemesi sonunu işaretler. |
  
## <a name="url-event-map-macros"></a>URL olay eşleme makroları  
 Aşağıdaki makroları DHTML olayları işlemek için kullanılan [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-türetilmiş sınıfları.  
  
|||  
|-|-|  
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|Birden çok DHTML ve URL olay eşlemesi başlangıcını işaretler.|  
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|Katıştırılmış bir DHTML olay eşlemesi başlangıcını işaretler.|  
|[BEGIN_URL_ENTRIES](#begin_url_entries)|Bir URL olay girişi eşlemesi başlangıcını işaretler.|  
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|Birden çok DHTML ve URL olay eşlemesi bildirir.|  
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|Birden çok DHTML ve URL olay eşlemesi sonunu işaretler.|  
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|Katıştırılmış bir DHTML olay eşlemesi sonunu işaretler.|  
|[END_URL_ENTRIES](#end_url_entries)|Bir URL olay girişi eşlemesi sonunu işaretler.|  
|[URL_EVENT_ENTRY](#url_event_entry)|Birden çok sayfa iletişim sayfasında URL veya HTML kaynak eşler.|  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="begin_dhtml_event_map"></a>BEGIN_DHTML_EVENT_MAP  
 Tarafından tanımlanan sınıfı için kaynak dosyasında yerleştirildiğinde DHTML olay eşlemesi başlangıcını işaretleyen `className`.  
  
```   
BEGIN_DHTML_EVENT_MAP(className)   
```  
  
### <a name="parameters"></a>Parametreler  
 `className`  
 DHTML olay eşlemesi içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak öğesinden türetilen [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) ve dahil [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) makrosu sınıf tanımına içinde.  
  
### <a name="remarks"></a>Açıklamalar  
 DHTML olay eşlemesi bilgiler sağlamak için sınıfına ekleyin **CDHtmlDialog** HTML öğeleri ya da bir web sayfasında işleyici işlevlerle sınıfınızda ActiveX denetimlerini tarafından tetiklenen rota olayları için kullanılabilir.  
  
 Yer `BEGIN_DHTML_EVENT_MAP` sınıfının uygulaması (.cpp) dosyasındaki makro arkasından `DHTML_EVENT` olaylar için makrolar sınıftır işlemek için (örneğin, `DHTML_EVENT_ONMOUSEOVER` fare üzerinde olayları için). Kullanım [END_DHTML_EVENT_MAP](#end_dhtml_event_map) makrosu olay eşlemesi sonunu işaretler. Bu makroları aşağıdaki işlevini uygulayın:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="begin_dhtml_event_map_inline"></a>BEGIN_DHTML_EVENT_MAP_INLINE  
 DHTML olay eşlemesi için sınıf tanımının içinde başlangıcını işaretleyen `className`.  
  
```   
BEGIN_DHTML_EVENT_MAP_INLINE(className)   
```  
  
### <a name="parameters"></a>Parametreler  
 `className`  
 DHTML olay eşlemesi içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak öğesinden türetilen [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) ve dahil [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) makrosu sınıf tanımına içinde.  
  
### <a name="remarks"></a>Açıklamalar  
 DHTML olay eşlemesi bilgiler sağlamak için sınıfına ekleyin **CDHtmlDialog** HTML öğeleri ya da bir web sayfasında işleyici işlevlerle sınıfınızda ActiveX denetimlerini tarafından tetiklenen rota olayları için kullanılabilir.  
  
 Yer `BEGIN_DHTML_EVENT_MAP` sınıfının tanımını (.h) dosyasındaki makro arkasından `DHTML_EVENT` olaylar için makrolar sınıftır işlemek için (örneğin, `DHTML_EVENT_ONMOUSEOVER` fare üzerinde olayları için). Kullanım [end_dhtml_event_map_ınlıne](#end_dhtml_event_map_inline) makrosu olay eşlemesi sonunu işaretler. Bu makroları aşağıdaki işlevini uygulayın:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  

  
##  <a name="declare_dhtml_event_map"></a>DECLARE_DHTML_EVENT_MAP  
 DHTML olay eşlemesi sınıf tanımında bildirir.  
  
```   
DECLARE_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu tanımında kullanılacaksa [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-türetilmiş sınıfları.  
  
 Kullanım [begın_dhtml_event_map](#begin_dhtml_event_map) veya [begın_dhtml_event_map_ınlıne](#begin_dhtml_event_map_inline) eşleme uygulamak için.  
  
 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) aşağıdaki işlevi bildirir:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event"></a>DHTML_EVENT  
 (Belge düzeyinde) tarafından tanımlanan bir olay işleme `dispid` tarafından tanımlanan HTML öğesi tarafından kaynaklanan `elemName`.  
  
```   
DHTML_EVENT(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `dispid`  
 İşlenecek Olay DISPID.  
  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran veya **NULL** belge olayları işlemek için.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_axcontrol"></a>DHTML_EVENT_AXCONTROL  
 Tarafından tanımlanan olayını işler `dispid` tarafından tanımlanan ActiveX denetimi tarafından tetiklenen `controlName`.  
  
```   
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)  
```  
  
### <a name="parameters"></a>Parametreler  
 `dispid`  
 İşlenecek Olay gönderme kimliği.  
  
 `controlName`  
 Bir `LPCWSTR` olay tetikleme denetimin HTML kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_class"></a>DHTML_EVENT_CLASS  
 (Belge düzeyinde) tarafından tanımlanan bir olay işleme `dispid` tarafından herhangi bir HTML öğesi tarafından tanımlanan CSS sınıfı ile kaynaklanan `elemName`.  
  
```   
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `dispid`  
 İşlenecek Olay gönderme kimliği.  
  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğeleri CSS sınıfının bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_element"></a>DHTML_EVENT_ELEMENT  
 İşleme (tarafından tanımlanan öğede `elemName`) tarafından tanımlanan bir olay `dispid`.  
  
```   
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn) 
```  
  
### <a name="parameters"></a>Parametreler  
 `dispid`  
 İşlenecek Olay gönderme kimliği.  
  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
 Bu makrosu nonbubbling olayları işlemek için kullanılır, olay kaynağı tarafından tanımlanan öğe olacaktır `elemName`.  
  
 Bu makrosu kabarcıklanma olayları işlemek için kullanılırsa, öğe tanımlanan `elemName` olay kaynağı olmayabilir (kaynak tarafından bulunan herhangi bir öğe olabilir `elemName`).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onafterupdate"></a>DHTML_EVENT_ONAFTERUPDATE  
 İşleme (belge düzeyinde) **onafterupdate** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```   
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onbeforeupdate"></a>DHTML_EVENT_ONBEFOREUPDATE  
 İşleme (belge düzeyinde) **onbeforeupdate** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```   
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onblur"></a>DHTML_EVENT_ONBLUR  
 İşleme (öğe düzeyinde) **onblur** olay. Bu nonbubbling bir olaydır.  
  
```   
DHTML_EVENT_ONBLUR(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onchange"></a>DHTML_EVENT_ONCHANGE  
 İşleme (öğe düzeyinde) `onchange` olay. Bu nonbubbling bir olaydır.  
  
```   
DHTML_EVENT_ONCHANGE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onclick"></a>DHTML_EVENT_ONCLICK  
 İşleme (belge düzeyinde) **onclick** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```   
DHTML_EVENT_ONCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_ondataavailable"></a>DHTML_EVENT_ONDATAAVAILABLE  
 İşleme (belge düzeyinde) **ondataavailable** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```   
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_ondatasetchanged"></a>DHTML_EVENT_ONDATASETCHANGED  
 İşleme (belge düzeyinde) **onDataSetComplete** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```   
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_ondatasetcomplete"></a>DHTML_EVENT_ONDATASETCOMPLETE  
 İşleme (belge düzeyinde) **satır almayı** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```   
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn) 
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_ondblclick"></a>DHTML_EVENT_ONDBLCLICK  
 İşleme (belge düzeyinde) **ondblclick** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```   
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_ondragstart"></a>DHTML_EVENT_ONDRAGSTART  
 İşleme (belge düzeyinde) **ondragstart** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```   
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onerrorupdate"></a>DHTML_EVENT_ONERRORUPDATE  
 İşleme (belge düzeyinde) **onerrorupdate** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```   
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onfilterchange"></a>DHTML_EVENT_ONFILTERCHANGE  
 İşleme (belge düzeyinde) **onfilterchange** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onfocus"></a>DHTML_EVENT_ONFOCUS  
 İşleme (öğe düzeyinde) **onfocus** olay. Bu nonbubbling bir olaydır.  
  
```  
 
DHTML_EVENT_ONFOCUS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onhelp"></a>DHTML_EVENT_ONHELP  
 İşleme (belge düzeyinde) `onhelp` olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONHELP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onkeydown"></a>DHTML_EVENT_ONKEYDOWN  
 İşleme (belge düzeyinde) **onkeydown** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onkeypress"></a>DHTML_EVENT_ONKEYPRESS  
 İşleme (belge düzeyinde) **onkeypress** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onkeyup"></a>DHTML_EVENT_ONKEYUP  
 İşleme (belge düzeyinde) **onkeyup** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONKEYUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onmousedown"></a>DHTML_EVENT_ONMOUSEDOWN  
 İşleme (belge düzeyinde) **onmousedown** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onmousemove"></a>DHTML_EVENT_ONMOUSEMOVE  
 İşleme (belge düzeyinde) `onmousemove` olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onmouseout"></a>DHTML_EVENT_ONMOUSEOUT  
 İşleme (belge düzeyinde) **onmouseout** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onmouseover"></a>DHTML_EVENT_ONMOUSEOVER  
 İşleme (belge düzeyinde) **onmouseover** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onmouseup"></a>DHTML_EVENT_ONMOUSEUP  
 İşleme (belge düzeyinde) **onmouseup** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onresize"></a>DHTML_EVENT_ONRESIZE  
 İşleme (öğe düzeyinde) **onresize** olay. Bu nonbubbling bir olaydır.  
  
```  
 
DHTML_EVENT_ONRESIZE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onrowenter"></a>DHTML_EVENT_ONROWENTER  
 İşleme (belge düzeyinde) **onrowenter** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONROWENTER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onrowexit"></a>DHTML_EVENT_ONROWEXIT  
 İşleme (belge düzeyinde) **onrowexit** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_onselectstart"></a>DHTML_EVENT_ONSELECTSTART  
 İşleme (belge düzeyinde) **onselectstart** olayın oluştuğu tarafından tanımlanan HTML öğesi tarafından `elemName`.  
  
```  
 
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `elemName`  
 Bir `LPCWSTR` olay kaynak Hizmeti'nden HTML öğesi kimliği bulunduran.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="dhtml_event_tag"></a>DHTML_EVENT_TAG  
 (Belge düzeyinde) tarafından tanımlanan bir olay işleme `dispid` tarafından herhangi bir HTML öğesi tarafından tanımlanan HTML etiketi ile kaynaklanan `elemName`.  
  
```   
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Parametreler  
 `dispid`  
 İşlenecek Olay gönderme kimliği.  
  
 `elemName`  
 Olay kaynak Hizmeti'nden HTML öğeleri HTML etiketi.  
  
 `memberFxn`  
 Olay işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir giriş eklemek için bu makrosu kullanma [DHTML olay eşlemesi](#begin_dhtml_event_map_inline) sınıfınızda.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="end_dhtml_event_map"></a>END_DHTML_EVENT_MAP  
 DHTML olay eşlemesi sonunu işaretler.  
  
```   
END_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Açıklamalar  
 İle birlikte kullanılmalıdır [begın_dhtml_event_map](#begin_dhtml_event_map).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="begin_dhtml_url_event_map"></a>BEGIN_DHTML_URL_EVENT_MAP  
 DHTML ve URL olay eşlemesi tanımını birden çok sayfa iletişim kutusunda başlatır.  
  
```  
BEGIN_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>Açıklamalar  
 PUT `BEGIN_DHTML_URL_EVENT_MAP` uygulama dosyasındaki, [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-türetilmiş sınıf. İle izleyerek [DHTML olay eşlemeleri katıştırılmış](#begin_embed_dhtml_event_map) ve [URL girişleri](#begin_url_entries)ve ardından kapatmak [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map). Dahil [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) makrosu sınıf tanımı içinde.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="begin_embed_dhtml_event_map"></a>BEGIN_EMBED_DHTML_EVENT_MAP  
 Birden çok sayfa iletişim kutusunda bir katıştırılmış DHTML olay eşlemesi tanımını başlatır.  
  
```  
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `className`  
 Olay eşleme içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak öğesinden türetilen [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Katıştırılmış DHTML olay eşlemesi içinde olmalıdır bir [DHTML ve URL olay eşlemesi](#begin_dhtml_url_event_map)).  
  
 *mapName*  
 Olay eşleme bu sayfa belirtir. Bu eşleşen *mapName* içinde [URL_EVENT_ENTRY](#url_event_entry) makrosu gerçekte URL veya HTML kaynak tanımlama.  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok sayfa DHTML iletişim her biri DHTML olayları oluşturabilir, birden çok HTML sayfaları, oluştuğundan ekli olay eşlemeleri olay işleyicileri sayfa başına temelinde eşlemek için kullanılır.  
  
 DHTML ve URL olay eşlemesi içinde ekli olay eşlemeleri oluşur bir `BEGIN_EMBED_DHTML_EVENT_MAP` makrosu arkasından [DHTML_EVENT](#dhtml_event) makroları ve bir [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) makrosu.  
  
 Karşılık gelen her katıştırılmış olay eşlemesi gerektirir [URL olay girdisi](#url_event_entry) eşlemek için *mapName* (belirtilen `BEGIN_EMBED_DHTML_EVENT_MAP`) bir URL veya HTML kaynağa.  
  
### <a name="example"></a>Örnek  
 Örnekte bkz [begın_dhtml_url_event_map](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="begin_url_entries"></a>BEGIN_URL_ENTRIES  
 Bir URL olay girişi eşlemesi tanımını birden çok sayfa iletişim kutusunda başlatır.  
  
```  
BEGIN_URL_ENTRIES(className)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `className`  
 URL olay girişi eşleme içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak öğesinden türetilen [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). URL olay girişi eşlemesi içinde olmalıdır bir [DHTML ve URL olay eşlemesi](#begin_dhtml_url_event_map)).  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok sayfa DHTML iletişim birden çok HTML sayfalarını oluştuğundan, URL olay girişler URL'leri veya HTML eşlemek için kullanılır karşılık gelen kaynakları [DHTML olay eşlemeleri katıştırılmış](#begin_embed_dhtml_event_map). PUT `URL_EVENT_ENTRY` makrolar arasında `BEGIN_URL_ENTRIES` ve [end_url_entrıes](#end_url_entries) makroları.  
  
### <a name="example"></a>Örnek  
 Örnekte bkz [begın_dhtml_url_event_map](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="declare_dhtml_url_event_map"></a>DECLARE_DHTML_URL_EVENT_MAP  
 DHTML ve URL olay eşlemesi sınıf tanımında bildirir.  
  
```  
DECLARE_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu tanımında kullanılacaksa [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-türetilmiş sınıfları.  
  
 DHTML ve URL olay eşlemesi içeren [DHTML olay eşlemeleri katıştırılmış](#begin_embed_dhtml_event_map) ve [URL olay girdileri](#begin_url_entries) DHTML olayları sayfa başına temelinde işleyicileri eşlemek için. Kullanım [begın_dhtml_url_event_map](#begin_dhtml_url_event_map) eşleme uygulamak için.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="end_dhtml_url_event_map"></a>END_DHTML_URL_EVENT_MAP  
 DHTML ve URL olay eşlemesi sonunu işaretler.  
  
```  
END_DHTML_URL_EVENT_MAP(className)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 `className`  
 Olay eşleme içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak öğesinden türetilen [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Bu eşleşmelidir `className` karşılık gelen [begın_dhtml_url_event_map](#begin_dhtml_url_event_map) makrosu.  
  
### <a name="example"></a>Örnek  
 Örnekte bkz [begın_dhtml_url_event_map](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="end_embed_dhtml_event_map"></a>END_EMBED_DHTML_EVENT_MAP  
 Katıştırılmış bir DHTML olay eşlemesi sonunu işaretler.  
  
```  
END_EMBED_DHTML_EVENT_MAP()  
 
```  
  
### <a name="example"></a>Örnek  
 Örnekte bkz [begın_dhtml_url_event_map](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="end_url_entries"></a>END_URL_ENTRIES  
 Bir URL olay girişi eşlemesi sonunu işaretler.  
  
```  
END_URL_ENTRIES()  
 
```  
  
### <a name="example"></a>Örnek  
 Örnekte bkz [begın_dhtml_url_event_map](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  
  
##  <a name="url_event_entry"></a>URL_EVENT_ENTRY  
 Birden çok sayfa iletişim sayfasında URL veya HTML kaynak eşler.  
  
```  
URL_EVENT_ENTRY(className, url,  mapName)   
```  
  
### <a name="parameters"></a>Parametreler  
 `className`  
 URL olay girişi eşleme içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak öğesinden türetilen [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). URL olay girişi eşlemesi içinde olmalıdır bir [DHTML ve URL olay eşlemesi](#begin_dhtml_url_event_map)).  
  
 *URL*  
 URL veya HTML kaynak sayfası.  
  
 *mapName*  
 URL sayfası belirtir *url*. Bu eşleşen *mapName* içinde [begın_embed_dhtml_event_map](#begin_embed_dhtml_event_map) bu sayfadan olayları eşlemeleri makrosu.  
  
### <a name="remarks"></a>Açıklamalar  
 Sayfa bir HTML kaynak ise *url* kaynağın kimlik numarası (diğer bir deyişle, "123", değil 123 veya ID_HTMLRES1) dize gösterimi olmalıdır.  
  
 Sayfa tanımlayıcı *mapName*, olan bağlamak için kullanılan rastgele bir simge katıştırılmış DHTML olay eşlemeleri URL olay girişi eşlemeleri için. DHTML ve URL olay eşlemesi için kapsamdaki sınırlıdır.  
  
### <a name="example"></a>Örnek  
 Örnekte bkz [begın_dhtml_url_event_map](#begin_dhtml_url_event_map).  

  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdhtml.h  

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
