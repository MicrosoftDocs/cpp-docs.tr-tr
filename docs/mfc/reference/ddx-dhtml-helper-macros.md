---
description: 'Daha fazla bilgi edinin: DDX_DHtml Yardımcısı makroları'
title: DDX_DHtml Yardımcısı makroları
ms.date: 11/04/2016
f1_keywords:
- AFXDHTML/DDX_DHtml_ElementValue
- AFXDHTML/DDX_DHtml_ElementInnerText
- AFXDHTML/DDX_DHtml_ElementInnerHtml
- AFXDHTML/DDX_DHtml_Anchor_Href
- AFXDHTML/DDX_DHtml_Anchor_Target
- AFXDHTML/DDX_DHtml_Img_Src
- AFXDHTML/DDX_DHtml_Frame_Src
- AFXDHTML/DDX_DHtml_IFrame_Src
helpviewer_keywords:
- macros [MFC], exchanging data with HMTL pages
- DDX macros [MFC]
- HTML pages [MFC], helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros [MFC], DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
ms.openlocfilehash: ac7df82d628c943a5ba28697cf614853e7e7dddd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220246"
---
# <a name="ddx_dhtml-helper-macros"></a>DDX_DHtml Yardımcısı makroları

DDX_DHtml Yardımcısı makroları, HTML sayfasındaki denetimlerin yaygın olarak kullanılan özelliklerine kolayca erişim sağlar.

### <a name="data-exchange-macros"></a>Veri değişimi makroları

|Ad|Açıklama|
|-|-|
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Seçili denetimden değer özelliğini ayarlar veya alır.|
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki metni ayarlar veya alır.|
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Geçerli öğenin başlangıç ve bitiş etiketleri arasında HTML ayarlar veya alır.|
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Hedef URL 'YI veya bağlantı noktasını ayarlar veya alır.|
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Hedef pencereyi veya çerçeveyi ayarlar veya alır.|
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Belgedeki bir görüntünün veya video klibinin adını ayarlar veya alır.|
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|İlişkili çerçevenin URL 'sini ayarlar veya alır.|
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|İlişkili çerçevenin URL 'sini ayarlar veya alır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdhtml. h

## <a name="ddx_dhtml_anchor_href"></a><a name="ddx_dhtml_anchor_href"></a> DDX_DHtml_Anchor_Href

Hedef URL 'YI veya bağlantı noktasını ayarlar veya alır.

```
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*ada*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*l*<br/>
Takas edilmekte olan değer.

### <a name="remarks"></a>Açıklamalar

Bu makro, DISPID_IHTMLANCHORELEMENT_HREF dağıtım KIMLIĞINI kullanarak [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_anchor_target"></a><a name="ddx_dhtml_anchor_target"></a> DDX_DHtml_Anchor_Target

Hedef pencereyi veya çerçeveyi ayarlar veya alır.

```
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*ada*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*l*<br/>
Takas edilmekte olan değer.

### <a name="remarks"></a>Açıklamalar

Bu makro, DISPID_IHTMLANCHORELEMENT_TARGET dağıtım KIMLIĞINI kullanarak [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_elementinnerhtml"></a><a name="ddx_dhtml_elementinnerhtml"></a> DDX_DHtml_ElementInnerHtml

Geçerli öğenin başlangıç ve bitiş etiketleri arasında HTML ayarlar veya alır.

```
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*ada*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*l*<br/>
Takas edilmekte olan değer.

### <a name="remarks"></a>Açıklamalar

Bu makro, DISPID_IHTMLELEMENT_INNERHTML dağıtım KIMLIĞINI kullanarak [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_elementinnertext"></a><a name="ddx_dhtml_elementinnertext"></a> DDX_DHtml_ElementInnerText

Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki metni ayarlar veya alır.

```
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*ada*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*l*<br/>
Takas edilmekte olan değer.

### <a name="remarks"></a>Açıklamalar

Bu makro, DISPID_IHTMLELEMENT_INNERTEXT dağıtım KIMLIĞINI kullanarak [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_elementvalue"></a><a name="ddx_dhtml_elementvalue"></a> DDX_DHtml_ElementValue

Seçili denetimden değer özelliğini ayarlar veya alır.

```
DDX_DHtml_ElementValue(
    CDataExchange* dx,
    LPCTSTR name,
    var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*ada*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*l*<br/>
Takas edilmekte olan değer. CDHtmlDialog içindeki *değeri* gör [::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).

### <a name="remarks"></a>Açıklamalar

Bu makro yalnızca değer özelliği olan denetimlerde çalıştırıldığında başarılı olur. Değer özelliğine sahip denetimler, düzenleme kutuları, liste kutuları ve Birleşik giriş kutuları içerir.

Bu makro, DISPID_A_VALUE dağıtım KIMLIĞINI kullanarak [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_frame_src"></a><a name="ddx_dhtml_frame_src"></a> DDX_DHtml_Frame_Src

İlişkili çerçevenin URL 'sini ayarlar veya alır.

```
DDX_DHtml_Frame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*ada*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*l*<br/>
Takas edilmekte olan değer.

### <a name="remarks"></a>Açıklamalar

Bu makro, DISPID_IHTMLFRAMEBASE_SRC dağıtım KIMLIĞINI kullanarak [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_iframe_src"></a><a name="ddx_dhtml_iframe_src"></a> DDX_DHtml_IFrame_Src

İlişkili çerçevenin URL 'sini ayarlar veya alır.

```
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*ada*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*l*<br/>
Takas edilmekte olan değer.

### <a name="remarks"></a>Açıklamalar

Bu makro, DISPID_IHTMLFRAMEBASE_SRC dağıtım KIMLIĞINI kullanarak [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_img_src"></a><a name="ddx_dhtml_img_src"></a> DDX_DHtml_Img_Src

Belgedeki bir görüntünün veya video klibinin adını alır veya alır.

```
DDX_DHtml_Img_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*DX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*ada*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*l*<br/>
Takas edilmekte olan değer.

### <a name="remarks"></a>Açıklamalar

Bir görüntü öğesi için SRC özelliğini almak üzere DDX_DHtml_Img_Src makrosunu kullanırken, Internet Explorer görüntü nesnesi görüntü kaynağı için tam kaçan URL 'YI döndürür. Örneğin, bir görüntü öğesinin SRC özelliğini "ilginç resim" dizesine ayarlamak için DDX_DHtml_Img_Src makrosunu kullanırsanız, Internet Explorer "res://d:\myapplication\myapp.exe/some%20ıntersting%20picture" dizesini döndürür.

Bu makro, DISPID_IHTMLIMGELEMENT_SRC dağıtım KIMLIĞINI kullanarak [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[CDHtmlDialog sınıfı](../../mfc/reference/cdhtmldialog-class.md)
