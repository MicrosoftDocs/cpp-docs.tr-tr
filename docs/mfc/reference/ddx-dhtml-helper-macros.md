---
title: DDX_DHtml yardımcı makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 841a140236c092ad14501698db90007bce0322ec
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054884"
---
# <a name="ddxdhtml-helper-macros"></a>DDX_DHtml yardımcı makroları

DDX_DHtml yardımcı makroları, yaygın olarak kullanılan bir HTML sayfasında denetimlerin özelliklerini kolay erişim sağlar.

### <a name="data-exchange-macros"></a>Veri Değişim makroları

|||
|-|-|
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Seçili denetiminden Value özelliği alır veya belirler.|
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki metni alır veya ayarlar.|
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Geçerli öğenin başlangıç ve bitiş etiketleri arasında HTML alır veya ayarlar.|
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Hedef URL veya bağlantı noktası alır veya ayarlar.|
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Hedef pencere veya çerçeve alır veya ayarlar.|
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Bir görüntü veya video klip belgedeki adını alır veya ayarlar.|
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|İlişkili çerçeve URL'sini alır veya ayarlar.|
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|İlişkili çerçeve URL'sini alır veya ayarlar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdhtml.h

## <a name="ddx_dhtml_anchor_href"></a> DDX_DHtml_Anchor_Href

Hedef URL veya bağlantı noktası alır veya ayarlar.

```
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne.

*Adı*<br/>
HTML denetiminin kimliği parametresi için belirtilen değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bu makroyu çağıran [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevi DISPID_IHTMLANCHORELEMENT_HREF kullanarak dağıtım kimliği

## <a name="ddx_dhtml_anchor_target"></a>  DDX_DHtml_Anchor_Target

Hedef pencere veya çerçeve alır veya ayarlar.

```
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne.

*Adı*<br/>
HTML denetiminin kimliği parametresi için belirtilen değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bu makroyu çağıran [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevi DISPID_IHTMLANCHORELEMENT_TARGET kullanarak dağıtım kimliği

## <a name="ddx_dhtml_elementinnerhtml"></a>  DDX_DHtml_ElementInnerHtml

Geçerli öğenin başlangıç ve bitiş etiketleri arasında HTML alır veya ayarlar.

```
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne.

*Adı*<br/>
HTML denetiminin kimliği parametresi için belirtilen değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bu makroyu çağıran [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevi DISPID_IHTMLELEMENT_INNERHTML kullanarak dağıtım kimliği

## <a name="ddx_dhtml_elementinnertext"></a>  DDX_DHtml_ElementInnerText

Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki metni alır veya ayarlar.

```
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne.

*Adı*<br/>
HTML denetiminin kimliği parametresi için belirtilen değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bu makroyu çağıran [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevi DISPID_IHTMLELEMENT_INNERTEXT kullanarak dağıtım kimliği

## <a name="ddx_dhtml_elementvalue"></a> DDX_DHtml_ElementValue

Seçili denetiminden Value özelliği alır veya belirler.

```
DDX_DHtml_ElementValue(
    CDataExchange* dx,
    LPCTSTR name,
    var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne.

*Adı*<br/>
HTML denetiminin kimliği parametresi için belirtilen değer.

*var*<br/>
Değiştirilen değer. Bkz: *değer* içinde [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).

## <a name="remarks"></a>Açıklamalar

Bu makro, bir değer özelliği olan denetimlere çalıştırdığınızda yalnızca başarılı olur. Bir değer özelliği olan denetimleri düzenleme kutuları, liste kutuları ve birleşik giriş kutuları içerir.

Bu makroyu çağıran [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevi DISPID_A_VALUE kullanarak dağıtım kimliği

## <a name="ddx_dhtml_frame_src"></a> DDX_DHtml_Frame_Src

İlişkili çerçeve URL'sini alır veya ayarlar.

```
DDX_DHtml_Frame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne.

*Adı*<br/>
HTML denetiminin kimliği parametresi için belirtilen değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bu makroyu çağıran [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevi DISPID_IHTMLFRAMEBASE_SRC kullanarak dağıtım kimliği

## <a name="ddx_dhtml_iframe_src"></a> DDX_DHtml_IFrame_Src

İlişkili çerçeve URL'sini alır veya ayarlar.

```
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne.

*Adı*<br/>
HTML denetiminin kimliği parametresi için belirtilen değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bu makroyu çağıran [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevi DISPID_IHTMLFRAMEBASE_SRC kullanarak dağıtım kimliği

## <a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src

Alır veya bir görüntü veya video klip belgedeki adını alır.

```
DDX_DHtml_Img_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne.

*Adı*<br/>
HTML denetiminin kimliği parametresi için belirtilen değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bir görüntü öğesi için kaynak özelliği almak için DDX_DHtml_Img_Src makrosu kullanırken, Internet Explorer resim nesnesi tamamen kaçan görüntü kaynağı URL'sini döndürür. Bir görüntü öğesi src özelliğini "bazı ilginç resim" dizesine ayarlamak için DDX_DHtml_Img_Src makro kullanırsanız, örneğin, bu özellik Internet Explorer aldığınızda "res://d:\myapplication\myapp.exe/some% dize döndürür 20interesting % 20picture."

Bu makroyu çağıran [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevi DISPID_IHTMLIMGELEMENT_SRC kullanarak dağıtım kimliği

## <a name="see-also"></a>Ayrıca Bkz.

[CDHtmlDialog Sınıfı](../../mfc/reference/cdhtmldialog-class.md)
