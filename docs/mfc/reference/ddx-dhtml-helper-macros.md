---
title: "DDX_DHtml yardımcı makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- AFXDHTML/DDX_DHtml_ElementValue
- AFXDHTML/DDX_DHtml_ElementInnerText
- AFXDHTML/DDX_DHtml_ElementInnerHtml
- AFXDHTML/DDX_DHtml_Anchor_Href
- AFXDHTML/DDX_DHtml_Anchor_Target
- AFXDHTML/DDX_DHtml_Img_Src
- AFXDHTML/DDX_DHtml_Frame_Src
- AFXDHTML/DDX_DHtml_IFrame_Src
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], exchanging data with HMTL pages
- DDX macros [MFC]
- HTML pages [MFC], helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros [MFC], DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d5a69e08d06a53dcb2f3a4be58618e9829e8c8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ddxdhtml-helper-macros"></a>DDX_DHtml yardımcı makroları
DDX_DHtml yardımcı makroları yaygın olarak kullanılan bir HTML sayfasında denetimlerin özelliklerini kolay erişim sağlar.  
  
### <a name="data-exchange-macros"></a>Veri değişimi makroları  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Seçili denetiminden değer özelliği alır veya ayarlar.|  
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki metni alır veya ayarlar.|  
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Geçerli öğenin başlangıç ve bitiş etiketleri arasında HTML alır veya ayarlar.|  
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Hedef URL veya bağlantı noktası alır veya ayarlar.|  
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Hedef penceresi veya çerçeve alır veya ayarlar.|  
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Bir görüntü veya bir video klip belgedeki adını alır veya ayarlar.|  
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|İlişkili çerçeve URL'sini alır veya ayarlar.|  
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|İlişkili çerçeve URL'sini alır veya ayarlar.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdhtml.h  

## <a name="ddx_dhtml_anchor_href"></a>DDX_DHtml_Anchor_Href
Hedef URL veya bağlantı noktası alır veya ayarlar.  
  
  
  
```  
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dx`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi.  
  
 `name`  
 HTML denetiminin kimliği parametresi için belirtilen değer.  
  
 `var`  
 Değiştirilen değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu çağırır [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLANCHORELEMENT_HREF kullanarak işlevi gönderme kimliği.

## <a name="ddx_dhtml_anchor_target"></a>DDX_DHtml_Anchor_Target
 Hedef penceresi veya çerçeve alır veya ayarlar.  
    
```  
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dx`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi.  
  
 `name`  
 HTML denetiminin kimliği parametresi için belirtilen değer.  
  
 `var`  
 Değiştirilen değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu çağırır [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLANCHORELEMENT_TARGET kullanarak işlevi gönderme kimliği.  

## <a name="ddx_dhtml_elementinnerhtml"></a>DDX_DHtml_ElementInnerHtml
 Geçerli öğenin başlangıç ve bitiş etiketleri arasında HTML alır veya ayarlar.  
  
  
  
```  
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dx`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi.  
  
 `name`  
 HTML denetiminin kimliği parametresi için belirtilen değer.  
  
 `var`  
 Değiştirilen değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu çağırır [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLELEMENT_INNERHTML kullanarak işlevi gönderme kimliği.  
  

## <a name="ddx_dhtml_elementinnertext"></a>DDX_DHtml_ElementInnerText
Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki metni alır veya ayarlar.  
  
  
  
```  
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dx`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi.  
  
 `name`  
 HTML denetiminin kimliği parametresi için belirtilen değer.  
  
 `var`  
 Değiştirilen değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu çağırır [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLELEMENT_INNERTEXT kullanarak işlevi gönderme kimliği. 

## <a name="ddx_dhtml_elementvalue"></a>DDX_DHtml_ElementValue  
Seçili denetiminden değer özelliği alır veya ayarlar.  
 
```  
DDX_DHtml_ElementValue(
    CDataExchange* dx,  
    LPCTSTR name,
    var)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dx`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi.  
  
 `name`  
 HTML denetiminin kimliği parametresi için belirtilen değer.  
  
 `var`  
 Değiştirilen değeri. Bkz: *değeri* içinde [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu yalnızca bir değer özelliği denetimlere çalıştırdığınızda başarılı olur. Bir değer özelliği denetimleri düzenleme kutularını, liste kutuları ve birleşik giriş kutuları içerir.  
  
 Bu makrosu çağırır [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_A_VALUE kullanarak işlevi gönderme kimliği.  

## <a name="ddx_dhtml_frame_src"></a>DDX_DHtml_Frame_Src
İlişkili çerçeve URL'sini alır veya ayarlar.  
  
```  
DDX_DHtml_Frame_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dx`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi.  
  
 `name`  
 HTML denetiminin kimliği parametresi için belirtilen değer.  
  
 `var`  
 Değiştirilen değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu çağırır [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLFRAMEBASE_SRC kullanarak işlevi gönderme kimliği.  

## <a name="ddx_dhtml_iframe_src"></a>DDX_DHtml_IFrame_Src
İlişkili çerçeve URL'sini alır veya ayarlar.  
  
  
  
```  
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dx`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi.  
  
 `name`  
 HTML denetiminin kimliği parametresi için belirtilen değer.  
  
 `var`  
 Değiştirilen değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu çağırır [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLFRAMEBASE_SRC kullanarak işlevi gönderme kimliği. 

## <a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src
Bir görüntü veya bir video klip belgedeki adını alır veya alır.  
  
```  
DDX_DHtml_Img_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dx`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi.  
  
 `name`  
 HTML denetiminin kimliği parametresi için belirtilen değer.  
  
 `var`  
 Değiştirilen değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanırken `DDX_DHtml_Img_Src` bir görüntü öğesi, Internet Explorer resim nesnesi src özelliği almak için makrosu görüntü kaynağı tam Atlanan URL'sini döndürür. Kullanırsanız, örneğin, `DDX_DHtml_Img_Src` makrosu bir görüntü öğesi src özelliği "bazı ilginç resim," dizesine ayarlamak için bu özelliği aldığınızda, Internet Explorer "res://d:\myapplication\myapp.exe/some% dizesi döndürür 20interesting % 20picture."  
  
 Bu makrosu çağırır [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLIMGELEMENT_SRC kullanarak işlevi gönderme kimliği.  

  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDHtmlDialog Sınıfı](../../mfc/reference/cdhtmldialog-class.md)
