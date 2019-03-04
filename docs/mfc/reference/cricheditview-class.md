---
title: CRichEditView sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRichEditView
- AFXRICH/CRichEditView
- AFXRICH/CRichEditView::CRichEditView
- AFXRICH/CRichEditView::AdjustDialogPosition
- AFXRICH/CRichEditView::CanPaste
- AFXRICH/CRichEditView::DoPaste
- AFXRICH/CRichEditView::FindText
- AFXRICH/CRichEditView::FindTextSimple
- AFXRICH/CRichEditView::GetCharFormatSelection
- AFXRICH/CRichEditView::GetDocument
- AFXRICH/CRichEditView::GetInPlaceActiveItem
- AFXRICH/CRichEditView::GetMargins
- AFXRICH/CRichEditView::GetPageRect
- AFXRICH/CRichEditView::GetPaperSize
- AFXRICH/CRichEditView::GetParaFormatSelection
- AFXRICH/CRichEditView::GetPrintRect
- AFXRICH/CRichEditView::GetPrintWidth
- AFXRICH/CRichEditView::GetRichEditCtrl
- AFXRICH/CRichEditView::GetSelectedItem
- AFXRICH/CRichEditView::GetTextLength
- AFXRICH/CRichEditView::GetTextLengthEx
- AFXRICH/CRichEditView::InsertFileAsObject
- AFXRICH/CRichEditView::InsertItem
- AFXRICH/CRichEditView::IsRichEditFormat
- AFXRICH/CRichEditView::OnCharEffect
- AFXRICH/CRichEditView::OnParaAlign
- AFXRICH/CRichEditView::OnUpdateCharEffect
- AFXRICH/CRichEditView::OnUpdateParaAlign
- AFXRICH/CRichEditView::PrintInsideRect
- AFXRICH/CRichEditView::PrintPage
- AFXRICH/CRichEditView::SetCharFormat
- AFXRICH/CRichEditView::SetMargins
- AFXRICH/CRichEditView::SetPaperSize
- AFXRICH/CRichEditView::SetParaFormat
- AFXRICH/CRichEditView::TextNotFound
- AFXRICH/CRichEditView::GetClipboardData
- AFXRICH/CRichEditView::GetContextMenu
- AFXRICH/CRichEditView::IsSelected
- AFXRICH/CRichEditView::OnFindNext
- AFXRICH/CRichEditView::OnInitialUpdate
- AFXRICH/CRichEditView::OnPasteNativeObject
- AFXRICH/CRichEditView::OnPrinterChanged
- AFXRICH/CRichEditView::OnReplaceAll
- AFXRICH/CRichEditView::OnReplaceSel
- AFXRICH/CRichEditView::OnTextNotFound
- AFXRICH/CRichEditView::QueryAcceptData
- AFXRICH/CRichEditView::WrapChanged
- AFXRICH/CRichEditView::m_nBulletIndent
- AFXRICH/CRichEditView::m_nWordWrap
helpviewer_keywords:
- CRichEditView [MFC], CRichEditView
- CRichEditView [MFC], AdjustDialogPosition
- CRichEditView [MFC], CanPaste
- CRichEditView [MFC], DoPaste
- CRichEditView [MFC], FindText
- CRichEditView [MFC], FindTextSimple
- CRichEditView [MFC], GetCharFormatSelection
- CRichEditView [MFC], GetDocument
- CRichEditView [MFC], GetInPlaceActiveItem
- CRichEditView [MFC], GetMargins
- CRichEditView [MFC], GetPageRect
- CRichEditView [MFC], GetPaperSize
- CRichEditView [MFC], GetParaFormatSelection
- CRichEditView [MFC], GetPrintRect
- CRichEditView [MFC], GetPrintWidth
- CRichEditView [MFC], GetRichEditCtrl
- CRichEditView [MFC], GetSelectedItem
- CRichEditView [MFC], GetTextLength
- CRichEditView [MFC], GetTextLengthEx
- CRichEditView [MFC], InsertFileAsObject
- CRichEditView [MFC], InsertItem
- CRichEditView [MFC], IsRichEditFormat
- CRichEditView [MFC], OnCharEffect
- CRichEditView [MFC], OnParaAlign
- CRichEditView [MFC], OnUpdateCharEffect
- CRichEditView [MFC], OnUpdateParaAlign
- CRichEditView [MFC], PrintInsideRect
- CRichEditView [MFC], PrintPage
- CRichEditView [MFC], SetCharFormat
- CRichEditView [MFC], SetMargins
- CRichEditView [MFC], SetPaperSize
- CRichEditView [MFC], SetParaFormat
- CRichEditView [MFC], TextNotFound
- CRichEditView [MFC], GetClipboardData
- CRichEditView [MFC], GetContextMenu
- CRichEditView [MFC], IsSelected
- CRichEditView [MFC], OnFindNext
- CRichEditView [MFC], OnInitialUpdate
- CRichEditView [MFC], OnPasteNativeObject
- CRichEditView [MFC], OnPrinterChanged
- CRichEditView [MFC], OnReplaceAll
- CRichEditView [MFC], OnReplaceSel
- CRichEditView [MFC], OnTextNotFound
- CRichEditView [MFC], QueryAcceptData
- CRichEditView [MFC], WrapChanged
- CRichEditView [MFC], m_nBulletIndent
- CRichEditView [MFC], m_nWordWrap
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
ms.openlocfilehash: 9cedcfbfb662d7d4d635a02b82ea45828c54b958
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259522"
---
# <a name="cricheditview-class"></a>CRichEditView sınıfı

İle [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) ve [Cricheditcntrıtem](../../mfc/reference/cricheditcntritem-class.md), MFC'nin belge görüntüleme mimarisi bağlamında zengin düzenleme denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CRichEditView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditView::CRichEditView](#cricheditview)|Oluşturur bir `CRichEditView` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|Geçerli seçimi gizlememeniz olmayan bir iletişim kutusu taşır.|
|[CRichEditView::CanPaste](#canpaste)|Pano zengin düzenleme görünümüne yapıştırılabilir veri içerip içermediğini belirtir.|
|[CRichEditView::DoPaste](#dopaste)|OLE öğesini bu zengin düzenleme görünümünü yapıştırır.|
|[CRichEditView::FindText](#findtext)|Bekleme imleci çağırma metnin belirtilen bulur.|
|[CRichEditView::FindTextSimple](#findtextsimple)|Belirtilen metni bulur.|
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|Geçerli seçim için öznitelikleri biçimlendirme karakter alır.|
|[CRichEditView::GetDocument](#getdocument)|İlgili bir işaretçi alır [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|Zengin düzenleme Görünümü'nde şu anda yerinde etkin OLE öğesini alır.|
|[CRichEditView::GetMargins](#getmargins)|Zengin düzenleme kenar boşluklarını alır.|
|[CRichEditView::GetPageRect](#getpagerect)|Zengin düzenleme sayfası dikdörtgeni alır.|
|[CRichEditView::GetPaperSize](#getpapersize)|Zengin düzenleme için sayfa boyutunu alır.|
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|Geçerli seçim için öznitelikleri paragraf alır.|
|[CRichEditView::GetPrintRect](#getprintrect)|Zengin düzenleme için yazdırma dikdörtgen alır.|
|[CRichEditView::GetPrintWidth](#getprintwidth)|Zengin düzenleme yazdırma genişliğini alır.|
|[CRichEditView::GetRichEditCtrl](#getricheditctrl)|Zengin düzenleme denetimi alır.|
|[CRichEditView::GetSelectedItem](#getselecteditem)|Zengin Düzenleme görünümünde seçili öğeyi alır.|
|[CRichEditView::GetTextLength](#gettextlength)|Zengin düzenleme Görünümü'nde metnin uzunluğunu alır.|
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|Karakter veya zengin düzenleme Görünümü'nde bayt sayısını alır. Uzunluğu belirlemek yöntemi için genişletilmiş bayrağı listesi.|
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|Bir dosya OLE öğesini ekler.|
|[CRichEditView::InsertItem](#insertitem)|OLE öğesini yeni bir öğe ekler.|
|[CRichEditView::IsRichEditFormat](#isricheditformat)|Panoya bir zengin düzenleme veya metin biçimi verileri içerip içermediğini belirtir.|
|[CRichEditView::OnCharEffect](#onchareffect)|Geçerli seçim için biçimlendirme karakter değiştirir.|
|[CRichEditView::OnParaAlign](#onparaalign)|Paragraf hizalamasını değiştirir.|
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|Karakter genel üye işlevleri için komut UI güncelleştirir.|
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|Paragraf genel üye işlevleri için komut UI güncelleştirir.|
|[CRichEditView::PrintInsideRect](#printinsiderect)|Verilen dikdörtgenin içindeki belirtilen metin olarak biçimlendirir.|
|[CRichEditView::PrintPage](#printpage)|Verilen sayfa içinde belirtilen metin olarak biçimlendirir.|
|[CRichEditView::SetCharFormat](#setcharformat)|Karakter öznitelikleri geçerli seçim için biçimlendirme ayarlar.|
|[CRichEditView::SetMargins](#setmargins)|Ayarlar bu zengin kenar boşluklarını görünümü düzenleyin.|
|[CRichEditView::SetPaperSize](#setpapersize)|Zengin düzenleme için sayfa boyutunu ayarlar.|
|[CRichEditView::SetParaFormat](#setparaformat)|Paragraf biçimlendirme öznitelikleri geçerli seçim için ayarlar.|
|[CRichEditView::TextNotFound](#textnotfound)|Denetimin iç arama durumunu sıfırlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditView::GetClipboardData](#getclipboarddata)|Bir aralıktaki bir zengin düzenleme için bir Pano nesnesi alır.|
|[CRichEditView::GetContextMenu](#getcontextmenu)|Bir sağ fare düğmesi üzerinde kullanmak için bir bağlam menüsü alır.|
|[CRichEditView::IsSelected](#isselected)|Belirtilen OLE öğesini veya seçili olup olmadığını gösterir.|
|[CRichEditView::OnFindNext](#onfindnext)|Bir alt dizenin bir sonraki tekrarını bulur.|
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|Yenilemeler ilk çalıştırıldığında bir görünüm bir belgeye ekli.|
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|OLE öğesinden yerel veri alır.|
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|Belirli bir cihazın yazdırma özelliklerini ayarlar.|
|[CRichEditView::OnReplaceAll](#onreplaceall)|Belirli bir dize tüm oluşumlarını yeni bir dize ile değiştirir.|
|[CRichEditView::OnReplaceSel](#onreplacesel)|Şu anki seçimi yerleştirir.|
|[CRichEditView::OnTextNotFound](#ontextnotfound)|İstenen metin bulunamadı kullanıcı bildirimi işler.|
|[CRichEditView::QueryAcceptData](#queryacceptdata)|İlgili verileri görmek için sorgular `IDataObject`.|
|[CRichEditView::WrapChanged](#wrapchanged)|Bu zengin değerine göre görüntüleme, düzenleme için hedef çıkış cihazını ayarlar `m_nWordWrap`.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|Madde işareti listeleri için girinti miktarını belirtir.|
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|Sözcük kaydırmayı kısıtlamaları gösterir.|

## <a name="remarks"></a>Açıklamalar

"Zengin düzenleme denetimi" kullanıcı girin ve metin düzenleme bir penceredir. Metnin karakteri ve paragraf biçimlendirme atanabilir ve katıştırılmış OLE nesnelerine içerebilir. Zengin düzenleme denetimleri, metin biçimlendirmesi için bir programlama arabirimi sağlar. Ancak, bir uygulamanın tüm biçimlendirme işlemlerini kullanıcı tarafından kullanılabilir hale getirmek için gerekli olan kullanıcı arabirimi bileşenleri uygulamalıdır.

`CRichEditView` metin biçimlendirme özelliği ve metin tutar. `CRichEditDoc` OLE istemci Görünümü'nde olan öğelerin listesini tutar. `CRichEditCntrItem` bir OLE istemci öğesi kapsayıcı tarafı erişim sağlar.

Bu Windows ortak denetimi (ve bu nedenle [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) ve üzeri yalnızca Windows 95/98 ve Windows NT sürümler 3.51 altında çalışan programlar için kullanılabilir.

Bir MFC uygulamasında bir zengin düzenleme görünümünü kullanma örneği için bkz: [WORDPAD](../../visual-cpp-samples.md) örnek uygulama.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CRichEditView`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrich.h

##  <a name="adjustdialogposition"></a>  CRichEditView::AdjustDialogPosition

Belirli bir iletişim kutusu geçerli seçimi getirmeyecek şekilde taşımak için bu işlevi çağırın.

```
void AdjustDialogPosition(CDialog* pDlg);
```

### <a name="parameters"></a>Parametreler

*pDlg*<br/>
İşaretçi bir `CDialog` nesne.

##  <a name="canpaste"></a>  CRichEditView::CanPaste

Pano bu zengin düzenleme görünümüne yapıştırılabilir bilgileri içerip içermediğini belirlemek için bu işlevi çağırın.

```
BOOL CanPaste() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pano verileri zengin düzenleme kabul edebilen bir biçimde olursa sıfır dışı; Aksi takdirde 0.

##  <a name="cricheditview"></a>  CRichEditView::CRichEditView

Oluşturmak için bu işlevi çağırın bir `CRichEditView` nesne.

```
CRichEditView();
```

##  <a name="dopaste"></a>  CRichEditView::DoPaste

OLE öğesinde yapıştırmak için bu işlevi çağırın *dataobj* bu belge/görünüm zengin düzenleme.

```
void DoPaste(
    COleDataObject& dataobj,
    CLIPFORMAT cf,
    HMETAFILEPICT hMetaPict);
```

### <a name="parameters"></a>Parametreler

*dataobj*<br/>
[COleDataObject](../../mfc/reference/coledataobject-class.md) yapıştırmak için verileri içeren.

*cf*<br/>
İstediğiniz Pano biçimi.

*hMetaPict*<br/>
Yapıştırılacak öğe temsil eden meta dosyası.

### <a name="remarks"></a>Açıklamalar

Framework varsayılan uygulaması bir parçası olarak bu işlevi çağıran [QueryAcceptData](#queryacceptdata).

Bu işlev için Özel Yapıştır işleyici sonuçlarına dayalı Yapıştır türünü belirler. Varsa *cf* 0 ise, yeni öğenin geçerli icon gösterimi kullanır. Varsa *cf* sıfır dışında olan ve *hMetaPict* NULL değil yeni öğe kullanan *hMetaPict* gösterimine için.

##  <a name="findtext"></a>  CRichEditView::FindText

Belirtilen metni Bul ve geçerli seçimi olarak ayarlamak için bu işlevi çağırın.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Aranacak dizeyi içerir.

*bCase*<br/>
Arama büyük/küçük harfe duyarlı olup olmadığını gösterir.

*bWord*<br/>
Arama yalnızca, tam sözcükleri sözcükler bölümlerini eşleşmesi olup olmadığını gösterir.

*bİleri*<br/>
Arama yönünü belirtir. TRUE ise arama yönünü arabelleğin sonuna doğru ' dir. FALSE ise, arama yönünü arabellek doğru başlangıcıdır.

### <a name="return-value"></a>Dönüş Değeri

Yalnız *lpszFind* metni bulundu; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev bulma işlemi sırasında bekleme imleci görüntüler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]

##  <a name="findtextsimple"></a>  CRichEditView::FindTextSimple

Belirtilen metni Bul ve geçerli seçimi olarak ayarlamak için bu işlevi çağırın.

```
BOOL FindTextSimple(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Aranacak dizeyi içerir.

*bCase*<br/>
Arama büyük/küçük harfe duyarlı olup olmadığını gösterir.

*bWord*<br/>
Arama yalnızca, tam sözcükleri sözcükler bölümlerini eşleşmesi olup olmadığını gösterir.

*bİleri*<br/>
Arama yönünü belirtir. TRUE ise arama yönünü arabelleğin sonuna doğru ' dir. FALSE ise, arama yönünü arabellek doğru başlangıcıdır.

### <a name="return-value"></a>Dönüş Değeri

Yalnız *lpszFind* metni bulundu; Aksi durumda 0.

### <a name="example"></a>Örnek

  Örneğin bakın [CRichEditView::FindText](#findtext).

##  <a name="getcharformatselection"></a>  CRichEditView::GetCharFormatSelection

Geçerli seçimi özniteliklerini biçimlendirme karakter almak için bu işlevi çağırın.

```
CHARFORMAT2& GetCharFormatSelection();
```

### <a name="return-value"></a>Dönüş Değeri

A [CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) yapısının biçimlendirme öznitelikleri geçerli seçimin karakterini içeriyor.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [EM_GETCHARFORMAT](/windows/desktop/Controls/em-getcharformat) ileti ve [CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) Windows SDK'sındaki yapısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

##  <a name="getclipboarddata"></a>  CRichEditView::GetClipboardData

Framework işlenmesini bir parçası olarak bu işlevi çağıran [IRichEditOleCallback::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getclipboarddata).

```
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,
    DWORD dwReco,
    LPDATAOBJECT lpRichDataObj,
    LPDATAOBJECT* lplpdataobj);
```

### <a name="parameters"></a>Parametreler

*lpchrg*<br/>
İşaretçi [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) yapısı tarafından belirlenen veri nesnesine kopyalamak için karakter (ve OLE öğeleri) aralığı belirtme *lplpdataobj*.

*dwReco*<br/>
Pano işlemi bayrak. Şu değerlerden biri olabilir.

- Panoya RECO_COPY Kopyala.

- RECO_CUT panoya Kes.

- RECO_DRAG sürükleme işlemi (Sürükle ve bırak).

- RECO_DROP bırakma işlemi (Sürükle ve bırak).

- Panodan RECO_PASTE yapıştırın.

*lpRichDataObj*<br/>
İşaretçi bir [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) içeren zengin bir Pano veri nesnesi düzenleme denetimi ( [IRichEditOle::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditole-getclipboarddata)).

*lplpdataobj*<br/>
İşaretçi adresi alan işaretçi değişkeninin `IDataObject` belirtilen aralığı temsil eden nesne *lpchrg* parametresi. Değerini *lplpdataobj* bir hata döndürülürse göz ardı edilir.

### <a name="return-value"></a>Dönüş Değeri

HRESULT değerini raporlama işlemi başarılı. HRESULT hakkında daha fazla bilgi için bkz. [yapısı COM hata kodlarını](/windows/desktop/com/structure-of-com-error-codes) Windows SDK.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri başarılı gösterir, `IRichEditOleCallback::GetClipboardData` döndürür `IDataObject` tarafından erişilen *lplpdataobj*; Aksi takdirde, erişilebilir bir döndürür *lpRichDataObj*. Kendi Pano verilerini sağlamak için bu işlevi geçersiz kılar. Bu işlev varsayılan uygulamasını E_NOTIMPL döndürür.

Bu gelişmiş bir, geçersiz kılınabilir.

Daha fazla bilgi için [IRichEditOle::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditole-getclipboarddata), [IRichEditOleCallback::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getclipboarddata), ve [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) bakınveWindowsSDK'sı[IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) Windows SDK içinde.

##  <a name="getcontextmenu"></a>  CRichEditView::GetContextMenu

Framework işlenmesini bir parçası olarak bu işlevi çağıran [IRichEditOleCallback::GetContextMenu](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getcontextmenu).

```
virtual HMENU GetContextMenu(
    WORD seltyp,
    LPOLEOBJECT lpoleobj,
    CHARRANGE* lpchrg);
```

### <a name="parameters"></a>Parametreler

*seltyp*<br/>
Seçim türü. Seçim türü değerleri açıklamalar bölümünde açıklanmıştır.

*lpoleobj*<br/>
İşaretçi bir `OLEOBJECT` yapısı ilk seçili OLE nesne seçim bir veya daha fazla OLE öğeleri içeriyorsa belirtme. Seçim hiçbir öğe içeriyorsa *lpoleobj* null. `OLEOBJECT` Yapısı bir OLE nesne v-tablosuna bir işaretçi tutar.

*lpchrg*<br/>
İşaretçi bir [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) geçerli seçimi içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Bağlam menüsüne işleyin.

### <a name="remarks"></a>Açıklamalar

Bu işlev, tipik bir işleme sağ fare düğmesi parçasıdır.

Seçim türü aşağıdaki bayrakları herhangi bir birleşimi olabilir:

- SEL_EMPTY, geçerli seçim yok olduğunu gösterir.

- Geçerli seçim metni içeren SEL_TEXT gösterir.

- SEL_OBJECT seçilen en az bir OLE öğesini içerdiğini gösterir.

- Geçerli seçimi metnin birden fazla karakter içeren SEL_MULTICHAR gösterir.

- SEL_MULTIOBJECT geçerli seçimi birden fazla OLE nesne içerdiğini gösterir.

Varsayılan uygulama, NULL döndürür. Bu gelişmiş bir, geçersiz kılınabilir.

Daha fazla bilgi için [IRichEditOleCallback::GetContextMenu](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getcontextmenu) ve [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) Windows SDK.

##  <a name="getdocument"></a>  CRichEditView::GetDocument

Bir işaretçi almak için bu işlevi çağırın `CRichEditDoc` Bu görünümle ilişkilendirilen.

```
CRichEditDoc* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçi bir [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) ilişkili nesne, `CRichEditView` nesne.

##  <a name="getinplaceactiveitem"></a>  CRichEditView::GetInPlaceActiveItem

OLE almak için bu işlevi öğesi çağrı bu yerinde şu anda etkinleştirilirse `CRichEditView` nesne.

```
CRichEditCntrItem* GetInPlaceActiveItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tek ve yerinde etkin bir işaretçiye [Cricheditcntrıtem](../../mfc/reference/cricheditcntritem-class.md) bu zengin düzenleme görünümünde; nesnesi Yoksa hiçbir OLE öğesini şu anda yerinde etkin durumda NULL.

##  <a name="getmargins"></a>  CRichEditView::GetMargins

Geçerli kenar boşlukları baskılarda almak için bu işlevi çağırın.

```
CRect GetMargins() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırma işleminde kullanılan kenar boşlukları içinde MM_TWIPS ölçülür.

##  <a name="getpagerect"></a>  CRichEditView::GetPageRect

Yazdırma kullanılan sayfa boyutuna almak için bu işlevi çağırın.

```
CRect GetPageRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Baskı, kullanılan sayfa sınırları içinde MM_TWIPS ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu değer kağıt boyutu temel alınır.

##  <a name="getpapersize"></a>  CRichEditView::GetPaperSize

Geçerli sayfa boyutunu almak için bu işlevi çağırın.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırma işleminde kullanılan boyutunu MM_TWIPS içinde ölçülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]

##  <a name="getparaformatselection"></a>  CRichEditView::GetParaFormatSelection

Paragraf biçimlendirme öznitelikleri geçerli seçimi almak için bu işlevi çağırın.

```
PARAFORMAT2& GetParaFormatSelection();
```

### <a name="return-value"></a>Dönüş Değeri

A [PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) paragraf biçimlendirme öznitelikleri geçerli seçimin içeren yapısı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [EM_GETPARAFORMAT](/windows/desktop/Controls/em-getparaformat) ileti ve [PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) Windows SDK'sındaki yapısı.

##  <a name="getprintrect"></a>  CRichEditView::GetPrintRect

Sayfa dikdörtgenin içindeki yazdırma alanını sınırları almak için bu işlevi çağırın.

```
CRect GetPrintRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırma işleminde kullanılan alan görüntü sınırları içinde MM_TWIPS ölçülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]

##  <a name="getprintwidth"></a>  CRichEditView::GetPrintWidth

Yazdırma alanını genişliğini belirlemek için bu işlevi çağırın.

```
int GetPrintWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırma alanını MM_TWIPS içinde ölçülen genişliği.

##  <a name="getricheditctrl"></a>  CRichEditView::GetRichEditCtrl

Almak için bu işlevi çağırın [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ilişkili nesne `CRichEditView` nesne.

```
CRichEditCtrl& GetRichEditCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CRichEditCtrl` Bu görünüm için nesne.

### <a name="example"></a>Örnek

  Örneğin bakın [CRichEditView::FindText](#findtext).

##  <a name="getselecteditem"></a>  CRichEditView::GetSelectedItem

OLE öğesini almak için bu işlevi çağırın (bir `CRichEditCntrItem` nesne) şu anda bu seçili `CRichEditView` nesne.

```
CRichEditCntrItem* GetSelectedItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçi bir [Cricheditcntrıtem](../../mfc/reference/cricheditcntritem-class.md) seçili nesne `CRichEditView` nesne; Bu görünümde hiçbir öğe seçili değilse null değerini DÖNDÜRÜR.

##  <a name="gettextlength"></a>  CRichEditView::GetTextLength

Bu metnin uzunluğunu almak için bu işlevi çağırın `CRichEditView` nesne.

```
long GetTextLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu metnin uzunluğunda `CRichEditView` nesne.

##  <a name="gettextlengthex"></a>  CRichEditView::GetTextLengthEx

Bu metnin uzunluğunu hesaplamak için bu üye işlevi çağrısı `CRichEditView` nesne.

```
long GetTextLengthEx(
    DWORD dwFlags,
    UINT uCodePage = -1) const;
```

### <a name="parameters"></a>Parametreler

*CertOpenStore*<br/>
Metin uzunluğu belirlemede kullanılacak yöntemi belirten değer. Bu üye biri veya daha fazla değer bayrakları üyesi, listelenen [GETTEXTLENGTHEX](/windows/desktop/api/richedit/ns-richedit-_gettextlengthex) Windows SDK'da açıklanmaktadır.

*uCodePage*<br/>
Kod sayfası için çeviri (CP_ACP ANSI kod sayfası 1200 Unicode için).

### <a name="return-value"></a>Dönüş Değeri

Karakter veya bayt düzenleme denetiminde sayısı. Uyumsuz bayraklar belirlenmişse *CertOpenStore*, bu üye işlevi E_INVALIDARG döndürür.

### <a name="remarks"></a>Açıklamalar

`GetTextLengthEx` metnin uzunluğunu belirleme ek yollar sağlar. Bu, zengin düzenleme 2.0 işlevlerini destekler. Daha fazla bilgi için [hakkında zengin düzenleme denetimleri](/windows/desktop/Controls/about-rich-edit-controls) Windows SDK.

##  <a name="insertfileasobject"></a>  CRichEditView::InsertFileAsObject

Belirtilen dosya eklemek için bu işlevi çağırın (olarak bir [Cricheditcntrıtem](../../mfc/reference/cricheditcntritem-class.md) nesnesi) zengin bir görünümü düzenleme.

```
void InsertFileAsObject(LPCTSTR lpszFileName);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
Eklenecek dosyanın adını içeren dize.

##  <a name="insertitem"></a>  CRichEditView::InsertItem

Eklemek için bu işlevi çağırın bir [Cricheditcntrıtem](../../mfc/reference/cricheditcntritem-class.md) nesnesine bir zengin düzenleme görünümü.

```
HRESULT InsertItem(CRichEditCntrItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Eklenecek öğe işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

HRESULT değerini başarının ekleme.

### <a name="remarks"></a>Açıklamalar

HRESULT hakkında daha fazla bilgi için bkz. [yapısı COM hata kodlarını](/windows/desktop/com/structure-of-com-error-codes) Windows SDK.

##  <a name="isricheditformat"></a>  CRichEditView::IsRichEditFormat

Belirlemek için bu işlevi çağırın *cf* metin, zengin metin ya da zengin metin OLE öğeleri ile bir pano biçimi.

```
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```

### <a name="parameters"></a>Parametreler

*cf*<br/>
İlgilendiğiniz Pano biçimi.

### <a name="return-value"></a>Dönüş Değeri

Yalnız *cf* bir zengin düzenleme veya metin Pano biçimi.

##  <a name="isselected"></a>  CRichEditView::IsSelected

Belirtilen OLE öğesi bu görünümde seçili olup olmadığını belirlemek için bu işlevi çağırın.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>Parametreler

*pDocItem*<br/>
Görünümde bir nesneye yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Seçili bir nesne olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

OLE öğelerinin seçimini işlemek için farklı bir yöntem türetilmiş görünüm sınıfınız varsa, bu işlev geçersiz kılar.

##  <a name="m_nbulletindent"></a>  CRichEditView::m_nBulletIndent

Madde işareti bir listedeki öğeler için Girintileme; 1/2 inç olan varsayılan 720 birimleri.

```
int m_nBulletIndent;
```

##  <a name="m_nwordwrap"></a>  CRichEditView::m_nWordWrap

Zengin düzenleme için sözcük kaydırmayı türünü belirtir.

```
int m_nWordWrap;
```

### <a name="remarks"></a>Açıklamalar

Aşağıdaki değerlerden biri:

- `WrapNone` Otomatik sözcük kaydırma yok gösterir.

- `WrapToWindow` Sözcük kaydırma üzerinde pencerenin genişliğini göre gösterir.

- `WrapToTargetDevice` Hedef cihaz özelliklerine dayanan sözcük kaydırma gösterir.

### <a name="example"></a>Örnek

  Örneğin bakın [CRichEditView::WrapChanged](#wrapchanged).

##  <a name="onchareffect"></a>  CRichEditView::OnCharEffect

Geçerli seçim için etkileri biçimlendirme karakter geçiş yapmak için bu işlevi çağırın.

```
void OnCharEffect(
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Parametreler

*dwMask*<br/>
Geçerli seçimi değiştirmek için etkileri biçimlendirme karakter.

*dwEffect*<br/>
Karakter etkileri geçiş yapmak için biçimlendirme istenen listesi.

### <a name="remarks"></a>Açıklamalar

Bu işleve yapılan her çağrı, geçerli seçim için belirtilen biçimlendirme efektleri değiştirir.

Daha fazla bilgi için *dwMask* ve *dwEffect* parametreler ve olası değerleri bkz karşılık gelen veri üyeleri [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]

##  <a name="onfindnext"></a>  CRichEditView::OnFindNext

Bul/Değiştir iletişim kutusundan komutları işlenirken framework tarafından çağırılır.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Bulunacak dize.

*bİleri*<br/>
Arama yönü: TRUE, aşağı gösterir; YANLIŞ çalışır.

*bCase*<br/>
Arama büyük/küçük harfe duyarlı olup olmadığını gösterir.

*bWord*<br/>
Arama yalnızca veya değil, tam sözcükleri eşleştirmeye olup olmadığını gösterir.

### <a name="remarks"></a>Açıklamalar

İçindeki metni bulmak için bu işlevi çağırın `CRichEditView`. Bu işlev, türetilmiş görünüm sınıfınız için arama özelliklerini değiştirmek için geçersiz kılın.

##  <a name="oninitialupdate"></a>  CRichEditView::OnInitialUpdate

Görünüm ilk belgeye eklendikten sonra ancak görünüm başlangıçta görüntülenmeden önce framework tarafından çağırılır.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını çağırır [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) üye işlev hiçbir ipucu bilgilerle (diğer bir deyişle, varsayılan değerleri için 0'ı kullanarak *lHint* parametresi ve içinNULL*pHint* parametresi). Bu işlev, belge hakkındaki bilgileri gerektiren herhangi bir kez başlatma gerçekleştirmek için geçersiz kılın. Örneğin, uygulamanızın sabit boyutlu belgeleri varsa, belge boyutunu temel alan bir görünümün kaydırma limitleri başlatmak için bu işlevi kullanabilirsiniz. Uygulamanızın değişken boyutlu belgeleri destekliyorsa `OnUpdate` kaydırma güncelleştirilecek limitleri her zaman belge değişiklikleri.

### <a name="example"></a>Örnek

  Örneğin bakın [CRichEditView::m_nWordWrap](#m_nwordwrap).

##  <a name="onpastenativeobject"></a>  CRichEditView::OnPasteNativeObject

Katıştırılmış bir öğesinden yerel veri yüklemek için bu işlevi kullanın.

```
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```

### <a name="parameters"></a>Parametreler

*lpStg*<br/>
İşaretçi bir [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage) nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0;

### <a name="remarks"></a>Açıklamalar

Genellikle, bu oluşturarak yaptığınız bir [COleStreamFile](../../mfc/reference/colestreamfile-class.md) etrafında `IStorage`. `COleStreamFile` Arşive eklenebilir ve [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) verileri yüklemek için çağrılır.

Bu gelişmiş bir, geçersiz kılınabilir.

Daha fazla bilgi için [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage) Windows SDK.

##  <a name="onparaalign"></a>  CRichEditView::OnParaAlign

Seçili paragraf Paragraf hizalamasını değiştirmek için bu işlevi çağırın.

```
void OnParaAlign(WORD wAlign);
```

### <a name="parameters"></a>Parametreler

*wAlign*<br/>
İstenen paragraf hizalaması. Aşağıdaki değerlerden biri:

- PFA_LEFT paragrafları sol kenar boşluğu ile hizalar.

- PFA_RIGHT paragrafları sağ kenar boşluğu ile hizalar.

- PFA_CENTER paragraflar kenar boşlukları arasındaki ortalayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]

##  <a name="onprinterchanged"></a>  CRichEditView::OnPrinterChanged

Bu işlev, yazıcı değiştiğinde zengin düzenleme özelliklerini değiştirmek için geçersiz kılın.

```
virtual void OnPrinterChanged(const CDC& dcPrinter);
```

### <a name="parameters"></a>Parametreler

*dcPrinter*<br/>
A [CDC](../../mfc/reference/cdc-class.md) yeni yazıcı nesnesi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama fiziksel yüksekliğini ve genişliğini çıktı cihazına (yazıcısı) için sayfa boyutunu ayarlar. Varsa, hiçbir cihaz bağlamı ile ilişkili *dcPrinter*, varsayılan uygulama 8.5 x 11 inç için sayfa boyutunu ayarlar.

##  <a name="onreplaceall"></a>  CRichEditView::OnReplaceAll

Tümünü Değiştir Değiştir iletişim kutusu komutları işlenirken framework tarafından çağırılır.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Değiştirilecek metin.

*lpszReplace*<br/>
Yerine konacak metin.

*bCase*<br/>
Arama büyük/küçük harfe duyarlı olup olmadığını gösterir.

*bWord*<br/>
Arama veya tam sözcükleri seçmelisiniz varsa gösterir.

### <a name="remarks"></a>Açıklamalar

Başka bir dize ile verilen bazı metnin tüm oluşumları değiştirmek için bu işlevi çağırın. Bu görünüm için arama özelliklerini değiştirmek için bu işlevi geçersiz kılar.

### <a name="example"></a>Örnek

  Örneğin bakın [CRichEditView::FindText](#findtext).

##  <a name="onreplacesel"></a>  CRichEditView::OnReplaceSel

Değiştir iletişim kutusundan Değiştir komutları işlenirken framework tarafından çağırılır.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Değiştirilecek metin.

*bİleri*<br/>
Arama yönünü gösterir: Aşağı True'dur; YANLIŞ çalışır.

*bCase*<br/>
Arama büyük/küçük harfe duyarlı olup olmadığını gösterir.

*bWord*<br/>
Arama veya tam sözcükleri seçmelisiniz varsa gösterir.

*lpszReplace*<br/>
Yerine konacak metin.

### <a name="remarks"></a>Açıklamalar

Belirli metin bir örneğini başka bir dizeyle değiştirmeniz için bu işlevi çağırın. Bu görünüm için arama özelliklerini değiştirmek için bu işlevi geçersiz kılar.

##  <a name="ontextnotfound"></a>  CRichEditView::OnTextNotFound

Bir arama başarısız olduğunda framework tarafından çağırılır.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Metni bulunamadı.

### <a name="remarks"></a>Açıklamalar

Çıkış bildirimden değiştirmek için bu işlevi geçersiz bir [MessageBeep](/windows/desktop/api/winuser/nf-winuser-messagebeep).

Daha fazla bilgi için [MessageBeep](/windows/desktop/api/winuser/nf-winuser-messagebeep) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]

##  <a name="onupdatechareffect"></a>  CRichEditView::OnUpdateCharEffect

Framework ' % s'komutu kullanıcı Arabirimi karakter etkisi komutları için güncelleştirmek için bu işlevi çağırır.

```
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
İşaretçi bir [Ccmduı](../../mfc/reference/ccmdui-class.md) nesne.

*dwMask*<br/>
Karakter maskesi biçimlendirmesini belirtir.

*dwEffect*<br/>
Karakter etkisi biçimlendirmesini belirtir.

### <a name="remarks"></a>Açıklamalar

Maske *dwMask* hangi karakter kontrol etmek için biçimlendirme öznitelikleri belirtir. Bayrakları *dwEffect* karakter öznitelikleri kümesi/clear biçimlendirme listesi.

Daha fazla bilgi için *dwMask* ve *dwEffect* parametreler ve olası değerleri bkz karşılık gelen veri üyeleri [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]

##  <a name="onupdateparaalign"></a>  CRichEditView::OnUpdateParaAlign

Framework ' % s'komutu kullanıcı Arabirimi paragraf etkisi komutları için güncelleştirmek için bu işlevi çağırır.

```
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,
    WORD wAlign);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
İşaretçi bir [Ccmduı](../../mfc/reference/ccmdui-class.md) nesne.

*wAlign*<br/>
Denetlenecek paragraf hizalaması. Aşağıdaki değerlerden biri:

- PFA_LEFT paragrafları sol kenar boşluğu ile hizalar.

- PFA_RIGHT paragrafları sağ kenar boşluğu ile hizalar.

- PFA_CENTER paragraflar kenar boşlukları arasındaki ortalayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]

##  <a name="printinsiderect"></a>  CRichEditView::PrintInsideRect

Bir dizi içinde uyacak şekilde bir zengin düzenleme denetimindeki metni biçimlendirmek için bu işlevi çağırın *rectLayout* tarafından belirtilen cihaz için *pDC*.

```
long PrintInsideRect(
    CDC* pDC,
    RECT& rectLayout,
    long nIndexStart,
    long nIndexStop,
    BOOL bOutput);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Çıkış alanı için bir cihaz bağlamı işaretçisi.

*rectLayout*<br/>
[RECT](/windows/desktop/api/windef/ns-windef-tagrect) veya [CRect](../../atl-mfc-shared/reference/crect-class.md) çıkış alanı tanımlar.

*nIndexStart*<br/>
Biçimlendirilecek ilk karakter sıfır tabanlı dizini.

*nIndexStop*<br/>
Biçimlendirilecek ve son karakterin sıfır tabanlı dizini.

*bOutput*<br/>
Metin işlenip işlenmeyeceğini belirtir. FALSE ise, metin yalnızca ölçülür.

### <a name="return-value"></a>Dönüş Değeri

Çıkış alanı artı bir en uygun ve son karakterin dizini.

### <a name="remarks"></a>Açıklamalar

Genellikle, bu çağrı bir çağrı arkasından [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) çıktı oluşturur.

### <a name="example"></a>Örnek

  Örneğin bakın [CRichEditView::GetPaperSize](#getpapersize).

##  <a name="printpage"></a>  CRichEditView::PrintPage

Bir dizi tarafından belirtilen çıkış cihaz için bir zengin düzenleme denetimindeki metni biçimlendirmek için bu işlevi çağırın *pDC*.

```
long PrintPage(
    CDC* pDC,
    long nIndexStart,
    long nIndexStop);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Bir cihaz bağlamı için sayfa çıktısını işaretçisi.

*nIndexStart*<br/>
Biçimlendirilecek ilk karakter sıfır tabanlı dizini.

*nIndexStop*<br/>
Biçimlendirilecek ve son karakterin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Sayfa artı bir en uygun ve son karakterin dizini.

### <a name="remarks"></a>Açıklamalar

Her sayfanın düzeni tarafından denetlenir [GetPageRect](#getpagerect) ve [GetPrintRect](#getprintrect). Genellikle, bu çağrı bir çağrı arkasından [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) çıktı oluşturur.

Kenar boşluklarını fiziksel sayfa göre mantıksal sayfa olduğunu unutmayın. Bu nedenle, birçok yazıcı sayfasında yazdırılamayan alanlara sahip olduğundan sıfır kenar boşluklarını genellikle metni küçük. Metni kırpma önlemek için çağırmalıdır [SetMargins](#setmargins) ve yazdırmadan önce makul kenar boşluklarını ayarlama.

##  <a name="queryacceptdata"></a>  CRichEditView::QueryAcceptData

Zengin düzenleme bir nesne yapıştırmak için framework tarafından çağırılır.

```
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,
    CLIPFORMAT* lpcfFormat,
    DWORD dwReco,
    BOOL bReally,
    HGLOBAL hMetaFile);
```

### <a name="parameters"></a>Parametreler

*lpdataobj*<br/>
İşaretçi [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) sorgulanamıyor.

*lpcfFormat*<br/>
Kabul edilebilir veri biçimi için işaretçi.

*dwReco*<br/>
Kullanılmadı.

*bReally*<br/>
Yapıştırma işlemi veya devam edip etmediğini belirtir.

*hMetaFile*<br/>
Öğenin simgeyi çizmek için kullanılan meta dosyası için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

HRESULT değerini raporlama işlemi başarılı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, türetilmiş belge sınıfı içinde COM öğelerin farklı Kuruluş işlemek için geçersiz kılın. Bu gelişmiş bir, geçersiz kılınabilir.

HRESULT hakkında daha fazla bilgi ve `IDataObject`, bakın [yapısı COM hata kodlarını](/windows/desktop/com/structure-of-com-error-codes) ve [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject)sırasıyla Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]

##  <a name="setcharformat"></a>  CRichEditView::SetCharFormat

Bu yeni metin özniteliklerini biçimlendirme karakter kümesi için bu işlevi çağırın `CRichEditView` nesne.

```
void SetCharFormat(CHARFORMAT2 cf);
```

### <a name="parameters"></a>Parametreler

*cf*<br/>
[CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) öznitelikleri biçimlendirme yeni varsayılan karakter içeren yapısı.

### <a name="remarks"></a>Açıklamalar

Yalnızca belirtilen öznitelikler `dwMask` üyesi *cf* bu işlev tarafından değiştirilir.

Daha fazla bilgi için [EM_SETCHARFORMAT](/windows/desktop/Controls/em-setcharformat) ileti ve [CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) Windows SDK'sındaki yapısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

##  <a name="setmargins"></a>  CRichEditView::SetMargins

Zengin düzenleme yazdırma kenar boşluklarını ayarlamak için bu işlevi çağırın.

```
void SetMargins(const CRect& rectMargin);
```

### <a name="parameters"></a>Parametreler

*rectMargin*<br/>
Yazdırma işlemi için yeni kenar boşluğu değerleri MM_TWIPS ölçülür.

### <a name="remarks"></a>Açıklamalar

Varsa [m_nWordWrap](#m_nwordwrap) olduğu `WrapToTargetDevice`, çağırmalısınız [WrapChanged](#wrapchanged) yazdırma özelliklerini ayarlamak için bu işlevi kullandıktan sonra.

Kenar boşluklarını tarafından kullanılan Not [PrintPage](#printpage) olan fiziksel sayfa göre mantıksal sayfa. Bu nedenle, birçok yazıcı sayfasında yazdırılamayan alanlara sahip olduğundan sıfır kenar boşluklarını genellikle metni küçük. Metni kırpma önlemek için kullanım çağırmalıdır `SetMargins` yazdırmadan önce makul yazıcı kenar boşluklarını ayarlamak için.

### <a name="example"></a>Örnek

  Örneğin bakın [CRichEditView::GetPaperSize](#getpapersize).

##  <a name="setpapersize"></a>  CRichEditView::SetPaperSize

Zengin düzenleme yazdırma için sayfa boyutunu ayarlamak için bu işlevi çağırın.

```
void SetPaperSize(CSize sizePaper);
```

### <a name="parameters"></a>Parametreler

*sizePaper*<br/>
Yazdırma işlemi için yeni kağıt boyutu değerleri MM_TWIPS içinde ölçülür.

### <a name="remarks"></a>Açıklamalar

Varsa [m_nWordWrap](#m_nwordwrap) olduğu `WrapToTargetDevice`, çağırmalısınız [WrapChanged](#wrapchanged) yazdırma özelliklerini ayarlamak için bu işlevi kullandıktan sonra.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]

##  <a name="setparaformat"></a>  CRichEditView::SetParaFormat

Bu geçerli seçim için öznitelikleri paragraf ayarlamak için bu işlevi çağırın `CRichEditView` nesne.

```
BOOL SetParaFormat(PARAFORMAT2& pf);
```

### <a name="parameters"></a>Parametreler

*PF*<br/>
[PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) yapısı içeren yeni varsayılan paragraf biçimlendirme öznitelikleri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yalnızca belirtilen öznitelikler `dwMask` üyesi *pf* bu işlev tarafından değiştirilir.

Daha fazla bilgi için [EM_SETPARAFORMAT](/windows/desktop/Controls/em-setparaformat) ileti ve [PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) Windows SDK'sındaki yapısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]

##  <a name="textnotfound"></a>  CRichEditView::TextNotFound

İç arama durumunu sıfırlamak için bu işlevi çağırın [CRichEditView](../../mfc/reference/cricheditview-class.md) başarısız çağrısı yapıldıktan sonra Denetim [FindText](#findtext).

```
void TextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Nebyl nalezen metin dizesi içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem için başarısız çağrılar hemen sonra çağrılabilir önerilir [FindText](#findtext) böylece denetimin iç arama durumu düzgün bir şekilde sıfırlanır.

*LpszFind* parametresi için sağlanan dizenin aynı içeriğe içermelidir [FindText](#findtext). İç arama durumu sıfırlanıyor sonra bu yöntemi çağıran [OnTextNotFound](#ontextnotfound) sağlanan arama dizesiyle yöntemi.

### <a name="example"></a>Örnek

  Örneğin bakın [CRichEditView::FindText](#findtext).

##  <a name="wrapchanged"></a>  CRichEditView::WrapChanged

Yazdırma özellikleri değiştiğinde bu işlevi çağırın ( [SetMargins](#setmargins) veya [SetPaperSize](#setpapersize)).

```
virtual void WrapChanged();
```

### <a name="remarks"></a>Açıklamalar

Zengin düzenleme görünümü değiştirmek için bu işlevi yanıt değişikliklere geçersiz kılma [m_nWordWrap](#m_nwordwrap) veya yazdırma özelliklerini ( [OnPrinterChanged](#onprinterchanged)).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek WORDPAD](../../visual-cpp-samples.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRichEditDoc Sınıfı](../../mfc/reference/cricheditdoc-class.md)<br/>
[CRichEditCntrItem Sınıfı](../../mfc/reference/cricheditcntritem-class.md)
