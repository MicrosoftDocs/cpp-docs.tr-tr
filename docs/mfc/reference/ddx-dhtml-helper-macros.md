---
title: DDX_DHtml Yardımcı Makrolar
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
ms.openlocfilehash: f78a923a498713867c13ccc88e3e30c1f0a23885
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365864"
---
# <a name="ddx_dhtml-helper-macros"></a>DDX_DHtml Yardımcı Makrolar

Yardımcı makroların DDX_DHtml, html sayfasında denetimlerin yaygın olarak kullanılan özelliklerine kolay erişim sağlar.

### <a name="data-exchange-macros"></a>Veri Değişim Makroları

|||
|-|-|
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Seçili denetimden Değer özelliğini ayarlar veya alır.|
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki metni ayarlar veya alır.|
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki HTML'yi ayarlar veya alır.|
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Hedef URL'yi veya bağlantı noktasını ayarlar veya alır.|
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Hedef pencereyi veya çerçeveyi ayarlar veya alır.|
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Belgedeki görüntünün veya video klibin adını ayarlar veya alır.|
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|İlişkili çerçevenin URL'sini ayarlar veya alır.|
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|İlişkili çerçevenin URL'sini ayarlar veya alır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdhtml.h

## <a name="ddx_dhtml_anchor_href"></a><a name="ddx_dhtml_anchor_href"></a>DDX_DHtml_Anchor_Href

Hedef URL'yi veya bağlantı noktasını ayarlar veya alır.

```
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*Dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*Adı*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bu makro, DISPID_IHTMLANCHORELEMENT_HREF dispatch ID'yi kullanarak [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_anchor_target"></a><a name="ddx_dhtml_anchor_target"></a>DDX_DHtml_Anchor_Target

Hedef pencereyi veya çerçeveyi ayarlar veya alır.

```
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*Dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*Adı*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bu makro, DISPID_IHTMLANCHORELEMENT_TARGET gönderme kimliğini kullanarak [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_elementinnerhtml"></a><a name="ddx_dhtml_elementinnerhtml"></a>DDX_DHtml_ElementInnerHtml

Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki HTML'yi ayarlar veya alır.

```
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*Dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*Adı*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bu makro, DISPID_IHTMLELEMENT_INNERHTML gönderme kimliğini kullanarak [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_elementinnertext"></a><a name="ddx_dhtml_elementinnertext"></a>DDX_DHtml_ElementInnerText

Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki metni ayarlar veya alır.

```
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*Dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*Adı*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bu makro, DISPID_IHTMLELEMENT_INNERTEXT gönderme kimliğini kullanarak [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_elementvalue"></a><a name="ddx_dhtml_elementvalue"></a>DDX_DHtml_ElementValue

Seçili denetimden Değer özelliğini ayarlar veya alır.

```
DDX_DHtml_ElementValue(
    CDataExchange* dx,
    LPCTSTR name,
    var)
```

#### <a name="parameters"></a>Parametreler

*Dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*Adı*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*var*<br/>
Değiştirilen değer. CDHtmlDialog *değerine* [bakın::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).

## <a name="remarks"></a>Açıklamalar

Bu makro yalnızca Değer özelliğine sahip denetimlerde çalıştırıldığında başarılı olur. Değer özelliğine sahip denetimler, denetim kutuları, liste kutuları ve açılan kutuları içerir.

Bu makro, DISPID_A_VALUE gönderme kimliğini kullanarak [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_frame_src"></a><a name="ddx_dhtml_frame_src"></a>DDX_DHtml_Frame_Src

İlişkili çerçevenin URL'sini ayarlar veya alır.

```
DDX_DHtml_Frame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*Dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*Adı*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bu makro, DISPID_IHTMLFRAMEBASE_SRC gönderme kimliğini kullanarak [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_iframe_src"></a><a name="ddx_dhtml_iframe_src"></a>DDX_DHtml_IFrame_Src

İlişkili çerçevenin URL'sini ayarlar veya alır.

```
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*Dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*Adı*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bu makro, DISPID_IHTMLFRAMEBASE_SRC gönderme kimliğini kullanarak [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="ddx_dhtml_img_src"></a><a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src

Belgedeki bir resmin veya video klibin adını alır veya alır.

```
DDX_DHtml_Img_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parametreler

*Dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*Adı*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*var*<br/>
Değiştirilen değer.

## <a name="remarks"></a>Açıklamalar

Bir IMAGE öğesi için src özelliğini almak için DDX_DHtml_Img_Src makroyu kullanırken, Internet Explorer görüntü nesnesi görüntü kaynağıiçin tamamen kaçan URL'yi döndürür. Örneğin, bir IMAGE öğesinin src özelliğini "bazı ilginç resim" dizesine ayarlamak için DDX_DHtml_Img_Src makroyu kullanırsanız, Internet Explorer "res://d:\myapplication\myapp.exe/some%20interesting%20picture" dizesini döndürür.

Bu makro, DISPID_IHTMLIMGELEMENT_SRC sevk kimliği kullanarak [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) işlevini çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[CDHtmlDialog Sınıfı](../../mfc/reference/cdhtmldialog-class.md)
