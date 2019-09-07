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
ms.openlocfilehash: b32578cc3c9ad4f7a89b8ee76449259c0fa0b43b
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741519"
---
# <a name="cricheditview-class"></a>CRichEditView sınıfı

[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) ve [Cricheditcntridıtem](../../mfc/reference/cricheditcntritem-class.md)ile, MFC 'nin belge görünümü mimarisinin bağlamı içinde zengin düzenleme denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CRichEditView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditView:: CRichEditView](#cricheditview)|Bir `CRichEditView` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditView:: AdjustDialogPosition](#adjustdialogposition)|Bir iletişim kutusunu, geçerli seçimi gizlememe şeklinde taşımaz.|
|[CRichEditView:: CanPaste](#canpaste)|Panonun zengin düzenleme görünümüne yapıştırılabilecek veriler içerip içermediğini söyler.|
|[CRichEditView::D Oyapıştır](#dopaste)|OLE öğesini bu zengin düzenleme görünümüne yapıştırır.|
|[CRichEditView:: FindText](#findtext)|Bekleme imlecini çağırarak belirtilen metni bulur.|
|[CRichEditView:: FindTextSimple](#findtextsimple)|Belirtilen metni bulur.|
|[CRichEditView:: GetCharFormatSelection](#getcharformatselection)|Geçerli seçimin karakter biçimlendirme özniteliklerini alır.|
|[CRichEditView:: GetDocument](#getdocument)|İlgili [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)için bir işaretçi alır.|
|[CRichEditView:: Getınplaceactiveıtem](#getinplaceactiveitem)|Zengin düzenleme görünümünde Şu anda yerinde etkin olan OLE öğesini alır.|
|[CRichEditView:: Getkenar boşlukları](#getmargins)|Bu zengin düzenleme görünümü için kenar boşluklarını alır.|
|[CRichEditView:: GetPageRect](#getpagerect)|Bu zengin düzenleme görünümü için sayfa dikdörtgenini alır.|
|[CRichEditView:: GetPaperSize](#getpapersize)|Bu zengin düzenleme görünümü için kağıt boyutunu alır.|
|[CRichEditView:: GetParaFormatSelection](#getparaformatselection)|Geçerli seçimin paragraf biçimlendirme özniteliklerini alır.|
|[CRichEditView:: GetPrintRect](#getprintrect)|Bu zengin düzenleme görünümü için yazdırma dikdörtgenini alır.|
|[CRichEditView:: GetPrintWidth](#getprintwidth)|Bu zengin düzenleme görünümü için yazdırma genişliğini alır.|
|[CRichEditView:: GetRichEditCtrl](#getricheditctrl)|Zengin düzenleme denetimini alır.|
|[CRichEditView:: Getselectedidıtem](#getselecteditem)|Seçili öğeyi zengin düzenleme görünümünden alır.|
|[CRichEditView:: GetTextLength](#gettextlength)|Zengin düzenleme görünümündeki metnin uzunluğunu alır.|
|[CRichEditView:: GetTextLengthEx](#gettextlengthex)|Zengin düzenleme görünümündeki karakter veya bayt sayısını alır. Uzunluğu belirleme yöntemi için genişletilmiş bayrak listesi.|
|[CRichEditView:: ınsertfileasobject](#insertfileasobject)|OLE öğesi olarak bir dosya ekler.|
|[CRichEditView:: InsertItem](#insertitem)|OLE öğesi olarak yeni bir öğe ekler.|
|[CRichEditView:: IsRichEditFormat](#isricheditformat)|Panonun zengin düzenleme veya metin biçiminde veri içerip içermediğini söyler.|
|[CRichEditView:: OnCharEffect](#onchareffect)|Geçerli seçimin karakter biçimlendirmesini değiştirir.|
|[CRichEditView:: Onparaalıgn](#onparaalign)|Paragrafların hizalamasını değiştirir.|
|[CRichEditView:: OnUpdateCharEffect](#onupdatechareffect)|Karakter ortak üye işlevleri için komut Kullanıcı arabirimini güncelleştirir.|
|[CRichEditView:: Onupdateparamalign](#onupdateparaalign)|Paragraf ortak üye işlevleri için komut Kullanıcı arabirimini güncelleştirir.|
|[CRichEditView::P rintInsideRect](#printinsiderect)|Belirtilen dikdörtgenin içinde belirtilen metni biçimlendirir.|
|[CRichEditView::P rintPage](#printpage)|Verilen sayfa içinde belirtilen metni biçimlendirir.|
|[CRichEditView:: SetCharFormat](#setcharformat)|Geçerli seçimin karakter biçimlendirme özniteliklerini ayarlar.|
|[CRichEditView:: Setkenar boşlukları](#setmargins)|Bu zengin düzenleme görünümü için kenar boşluklarını ayarlar.|
|[CRichEditView:: SetPaperSize](#setpapersize)|Bu zengin düzenleme görünümü için kağıt boyutunu ayarlar.|
|[CRichEditView:: SetParaFormat](#setparaformat)|Geçerli seçimin paragraf biçimlendirme özniteliklerini ayarlar.|
|[CRichEditView:: TextNotFound](#textnotfound)|Denetimin iç arama durumunu sıfırlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditView:: GetClipboardData](#getclipboarddata)|Bu zengin düzenleme görünümü içinde bir Aralık için Pano nesnesi alır.|
|[CRichEditView:: GetContextMenu](#getcontextmenu)|Sağ fare düğmesi üzerinde kullanmak için bir bağlam menüsü alır.|
|[CRichEditView:: IsSelected](#isselected)|Verilen OLE öğesinin seçili olup olmadığını gösterir.|
|[CRichEditView:: onsonra](#onfindnext)|Bir alt dizenin sonraki tekrarını bulur.|
|[CRichEditView:: OnInitialUpdate](#oninitialupdate)|Bir belgeye ilk eklendiğinde bir görünümü yeniler.|
|[CRichEditView:: OnPasteNativeObject](#onpastenativeobject)|Bir OLE öğesinden yerel verileri alır.|
|[CRichEditView:: OnPrinterChanged](#onprinterchanged)|Yazdırma özelliklerini verilen cihaza ayarlar.|
|[CRichEditView:: OnReplaceAll](#onreplaceall)|Belirli bir dizenin tüm oluşumlarını yeni bir dizeyle değiştirir.|
|[CRichEditView:: OnReplaceSel](#onreplacesel)|Geçerli seçimi değiştirir.|
|[CRichEditView:: OnTextNotFound](#ontextnotfound)|İstenen metnin bulunamadığını belirten Kullanıcı bildirimini işler.|
|[CRichEditView:: QueryAcceptData](#queryacceptdata)|Üzerinde veriler hakkında bilgi almak için sorgular `IDataObject`.|
|[CRichEditView:: WrapChanged](#wrapchanged)|Bu zengin düzenleme görünümü için hedef çıktı cihazını değerine `m_nWordWrap`göre ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditView:: m_nBulletIndent](#m_nbulletindent)|Madde işareti listeleri için girinti miktarını gösterir.|
|[CRichEditView:: m_nWordWrap](#m_nwordwrap)|Sözcük kaydır kısıtlamalarını gösterir.|

## <a name="remarks"></a>Açıklamalar

"Zengin düzenleme denetimi", kullanıcının metin girebileceği ve düzenleyebileceği bir penceredir. Metne karakter ve paragraf biçimlendirme atanabilir ve katıştırılmış OLE nesneleri dahil edilebilir. Zengin düzenleme denetimleri, metin biçimlendirme için bir programlama arabirimi sağlar. Ancak, bir uygulamanın biçimlendirme işlemlerini Kullanıcı için kullanılabilir hale getirmek için gereken herhangi bir kullanıcı arabirimi bileşenini uygulaması gerekir.

`CRichEditView`metnin metin ve biçimlendirme özelliklerini korur. `CRichEditDoc`görünümdeki OLE istemci öğelerinin listesini tutar. `CRichEditCntrItem`OLE istemci öğesine kapsayıcı tarafı erişimi sağlar.

Bu Windows ortak denetimi (ve bu nedenle [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) yalnızca Windows 95/98 ve Windows NT sürümleri 3,51 ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Bir MFC uygulamasında zengin düzenleme görünümü kullanmanın bir örneği için bkz. [WordPad](../../overview/visual-cpp-samples.md) örnek uygulaması.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CRichEditView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrich. h

##  <a name="adjustdialogposition"></a>CRichEditView:: AdjustDialogPosition

Belirtilen iletişim kutusunu geçerli seçimi gizlemez olacak şekilde taşımak için bu işlevi çağırın.

```
void AdjustDialogPosition(CDialog* pDlg);
```

### <a name="parameters"></a>Parametreler

*pDlg*<br/>
Bir `CDialog` nesne işaretçisi.

##  <a name="canpaste"></a>CRichEditView:: CanPaste

Panonun bu zengin düzenleme görünümüne yapıştırılabilecek bilgiler içerip içermediğini öğrenmek için bu işlevi çağırın.

```
BOOL CanPaste() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pano, bu zengin düzenleme görünümünün kabul edebileceği bir biçimde veri içeriyorsa sıfır dışı olur; Aksi takdirde, 0.

##  <a name="cricheditview"></a>CRichEditView:: CRichEditView

Bir `CRichEditView` nesne oluşturmak için bu işlevi çağırın.

```
CRichEditView();
```

##  <a name="dopaste"></a>CRichEditView::D Oyapıştır

*Dataobj* içindeki OLE öğesini bu zengin düzenleme belgesine/görünümüne yapıştırmak için bu işlevi çağırın.

```
void DoPaste(
    COleDataObject& dataobj,
    CLIPFORMAT cf,
    HMETAFILEPICT hMetaPict);
```

### <a name="parameters"></a>Parametreler

*dataobj*<br/>
Yapıştırılacak verileri içeren [Colet](../../mfc/reference/coledataobject-class.md) .

*CF*<br/>
İstenen Pano biçimi.

*Hmetapıct*<br/>
Yapıştırılacak öğeyi temsil eden meta dosyası.

### <a name="remarks"></a>Açıklamalar

Framework, [QueryAcceptData](#queryacceptdata)uygulamasının varsayılan uygulamasının bir parçası olarak bu işlevi çağırır.

Bu işlev, yapıştırma için işleyicinin sonuçlarına göre yapıştırma türünü belirler. *CF* 0 ise, yeni öğe geçerli ıfer gösterimini kullanır. *CF* sıfır değilse ve *HMETAPıCT* null değilse, yeni öğe temsili için *hmetapıct* kullanır.

##  <a name="findtext"></a>CRichEditView:: FindText

Belirtilen metni bulmak ve geçerli seçim olacak şekilde ayarlamak için bu işlevi çağırın.

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
Aramanın büyük/küçük harfe duyarlı olup olmadığını gösterir.

*Sözcük*<br/>
Aramanın sözcüklerin parçalarını değil, yalnızca tam kelimeyle eşleşmesinin gerekip gerekmediğini gösterir.

*bNext*<br/>
Aramanın yönünü gösterir. DOĞRU ise, arama yönü arabelleğin sonuna doğru olur. FALSE ise, arama yönü arabelleğin başına doğru olur.

### <a name="return-value"></a>Dönüş Değeri

*LpszFind* metni bulunursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bulma işlemi sırasında bekleme imlecini görüntüler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]

##  <a name="findtextsimple"></a>CRichEditView:: FindTextSimple

Belirtilen metni bulmak ve geçerli seçim olacak şekilde ayarlamak için bu işlevi çağırın.

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
Aramanın büyük/küçük harfe duyarlı olup olmadığını gösterir.

*Sözcük*<br/>
Aramanın sözcüklerin parçalarını değil, yalnızca tam kelimeyle eşleşmesinin gerekip gerekmediğini gösterir.

*bNext*<br/>
Aramanın yönünü gösterir. DOĞRU ise, arama yönü arabelleğin sonuna doğru olur. FALSE ise, arama yönü arabelleğin başına doğru olur.

### <a name="return-value"></a>Dönüş Değeri

*LpszFind* metni bulunursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

  [CRichEditView:: FindText](#findtext)için örneğe bakın.

##  <a name="getcharformatselection"></a>CRichEditView:: GetCharFormatSelection

Geçerli seçimin karakter biçimlendirme özniteliklerini almak için bu işlevi çağırın.

```
CHARFORMAT2& GetCharFormatSelection();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli seçimin karakter biçimlendirme özniteliklerini içeren bir [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) yapısı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [EM_GETCHARFORMAT](/windows/win32/Controls/em-getcharformat) Iletisine ve [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) yapısına bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

##  <a name="getclipboarddata"></a>CRichEditView:: GetClipboardData

Framework, [IRichEditOleCallback:: GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditolecallback-getclipboarddata)işleminin bir parçası olarak bu işlevi çağırır.

```
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,
    DWORD dwReco,
    LPDATAOBJECT lpRichDataObj,
    LPDATAOBJECT* lplpdataobj);
```

### <a name="parameters"></a>Parametreler

*lpgid*<br/>
*Lplpdataobj*tarafından belirtilen veri nesnesine kopyalanacak karakter aralığını (ve OLE öğeleri) belirleyen, [charrange](/windows/win32/api/richedit/ns-richedit-charrange) yapısına yönelik işaretçi.

*dwReco*<br/>
Pano işlemi bayrağı. Şu değerlerden biri olabilir.

- RECO_COPY panoya kopyalayın.

- RECO_CUT panoya kes.

- RECO_DRAG sürükleme işlemi (sürükleyip bırakma).

- RECO_DROP bırakma işlemi (sürükleyip bırakma).

- RECO_PASTE panodan yapıştırın.

*lpRichDataObj*<br/>
Zengin düzenleme denetiminden Pano verilerini içeren bir [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) nesnesi Işaretçisi ( [IRichEditOle:: GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditole-getclipboarddata)).

*lplpdataobj*<br/>
`IDataObject` *Lpgid* parametresinde belirtilen aralığı temsil eden nesnenin adresini alan işaretçi değişkeninin işaretçisi. Bir hata döndürülürse, *lplpdataobj* değeri yok sayılır.

### <a name="return-value"></a>Dönüş Değeri

İşlemin başarısını bildiren bir HRESULT değeri. HRESULT hakkında daha fazla bilgi için bkz. Windows SDK [com hata kodları yapısı](/windows/win32/com/structure-of-com-error-codes) .

### <a name="remarks"></a>Açıklamalar

Dönüş değeri başarıyı gösteriyorsa, `IRichEditOleCallback::GetClipboardData` *lplpdataobj*tarafından `IDataObject` erişilen ' ı döndürür; Aksi takdirde, *lpRichDataObj*tarafından erişilen bir döndürür. Kendi Pano verilerinizi sağlamak için bu işlevi geçersiz kılın. Bu işlevin varsayılan uygulanması E_NOTIMPL döndürür.

Bu gelişmiş bir geçersiz kılınabilir.

Daha fazla bilgi için [, bkz.](/windows/win32/api/objidl/nn-objidl-idataobject) [IRichEditOle:: GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditole-getclipboarddata), [IRichEditOleCallback:: GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditolecallback-getclipboarddata)ve Windows SDK [charrange](/windows/win32/api/richedit/ns-richedit-charrange) ve Windows SDK.

##  <a name="getcontextmenu"></a>CRichEditView:: GetContextMenu

Framework, [IRichEditOleCallback:: GetContextMenu](/windows/win32/api/richole/nf-richole-iricheditolecallback-getcontextmenu)işleminin bir parçası olarak bu işlevi çağırır.

```
virtual HMENU GetContextMenu(
    WORD seltyp,
    LPOLEOBJECT lpoleobj,
    CHARRANGE* lpchrg);
```

### <a name="parameters"></a>Parametreler

*seltyp*<br/>
Seçim türü. Seçim türü değerleri, açıklamalar bölümünde açıklanmaktadır.

*lpotaobj*<br/>
Seçim bir veya `OLEOBJECT` daha fazla ole öğesi içeriyorsa, seçilen ilk OLE nesnesini belirten bir yapıya yönelik işaretçi. Seçim hiçbir öğe içermiyorsa, *lpotaobj* null olur. Yapı `OLEOBJECT` , OLE nesnesi v-tablosuna yönelik bir işaretçi tutar.

*lpgid*<br/>
Geçerli seçimi içeren bir [charrange](/windows/win32/api/richedit/ns-richedit-charrange) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bağlam menüsüne işleyin.

### <a name="remarks"></a>Açıklamalar

Bu işlev, sağ fare düğmesi aşağı işlemenin tipik bir parçasıdır.

Seçim türü aşağıdaki bayrakların herhangi bir birleşimi olabilir:

- SEL_EMPTY geçerli seçim olmadığını gösterir.

- SEL_TEXT, geçerli seçimin metin içerdiğini gösterir.

- SEL_OBJECT, geçerli seçimin en az bir OLE öğesi içerdiğini gösterir.

- SEL_MULTICHAR, geçerli seçimin birden fazla metin karakteri içerdiğini gösterir.

- SEL_MULTIOBJECT, geçerli seçimin birden fazla OLE nesnesi içerdiğini gösterir.

Varsayılan uygulama NULL değerini döndürür. Bu gelişmiş bir geçersiz kılınabilir.

Daha fazla bilgi için Windows SDK [IRichEditOleCallback:: GetContextMenu](/windows/win32/api/richole/nf-richole-iricheditolecallback-getcontextmenu) ve [charrange](/windows/win32/api/richedit/ns-richedit-charrange) bölümüne bakın.

##  <a name="getdocument"></a>CRichEditView:: GetDocument

Bu görünümle `CRichEditDoc` ilişkili bir işaretçi almak için bu işlevi çağırın.

```
CRichEditDoc* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CRichEditView` Nesneniz ile ilişkili bir [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) nesnesi işaretçisi.

##  <a name="getinplaceactiveitem"></a>CRichEditView:: Getınplaceactiveıtem

Bu `CRichEditView` nesnede etkin olan OLE öğesini almak için bu işlevi çağırın.

```
CRichEditCntrItem* GetInPlaceActiveItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu zengin düzenleme görünümündeki tek ve yerinde etkin [Cricheditcntridıtem](../../mfc/reference/cricheditcntritem-class.md) nesnesine yönelik bir işaretçi; Şu anda yerinde etkin durumda olmayan bir OLE öğesi yoksa NULL olur.

##  <a name="getmargins"></a>CRichEditView:: Getkenar boşlukları

Yazdırmada kullanılan geçerli kenar boşluklarını almak için bu işlevi çağırın.

```
CRect GetMargins() const;
```

### <a name="return-value"></a>Dönüş Değeri

Baskıda kullanılan kenar boşlukları, MM_TWIPS cinsinden ölçülür.

##  <a name="getpagerect"></a>CRichEditView:: GetPageRect

Yazdırmada kullanılan sayfanın boyutlarını almak için bu işlevi çağırın.

```
CRect GetPageRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırırken kullanılan sayfanın sınırları, MM_TWIPS cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu değer, kağıt boyutunu temel alır.

##  <a name="getpapersize"></a>CRichEditView:: GetPaperSize

Geçerli kağıt boyutunu almak için bu işlevi çağırın.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırırken kullanılan kağıdın boyutu MM_TWIPS cinsinden ölçülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]

##  <a name="getparaformatselection"></a>CRichEditView:: GetParaFormatSelection

Geçerli seçimin paragraf biçimlendirme özniteliklerini almak için bu işlevi çağırın.

```
PARAFORMAT2& GetParaFormatSelection();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli seçimin paragraf biçimlendirme özniteliklerini içeren bir [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) yapısı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [EM_GETPARAFORMAT](/windows/win32/Controls/em-getparaformat) Message and [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) Structure bölümüne bakın.

##  <a name="getprintrect"></a>CRichEditView:: GetPrintRect

Sayfa dikdörtgeninin içindeki yazdırma alanının sınırlarını almak için bu işlevi çağırın.

```
CRect GetPrintRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Baskıda kullanılan görüntü alanının sınırları, MM_TWIPS cinsinden ölçülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]

##  <a name="getprintwidth"></a>CRichEditView:: GetPrintWidth

Yazdırma alanının genişliğini öğrenmek için bu işlevi çağırın.

```
int GetPrintWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırma alanının MM_TWIPS cinsinden ölçülen genişliği.

##  <a name="getricheditctrl"></a>CRichEditView:: GetRichEditCtrl

`CRichEditView` Nesneyle ilişkili [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) nesnesini almak için bu işlevi çağırın.

```
CRichEditCtrl& GetRichEditCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu görünüm için nesne. `CRichEditCtrl`

### <a name="example"></a>Örnek

  [CRichEditView:: FindText](#findtext)için örneğe bakın.

##  <a name="getselecteditem"></a>CRichEditView:: Getselectedidıtem

`CRichEditCntrItem` Bu`CRichEditView` nesnede seçili olan OLE öğesini (nesne) almak için bu işlevi çağırın.

```
CRichEditCntrItem* GetSelectedItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CRichEditView` Nesnede seçilen bir [cricheditcntridıtem](../../mfc/reference/cricheditcntritem-class.md) nesnesi işaretçisi; Bu görünümde hiçbir öğe seçilmezse NULL.

##  <a name="gettextlength"></a>CRichEditView:: GetTextLength

Bu `CRichEditView` nesnedeki metnin uzunluğunu almak için bu işlevi çağırın.

```
long GetTextLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `CRichEditView` nesnedeki metnin uzunluğu.

##  <a name="gettextlengthex"></a>CRichEditView:: GetTextLengthEx

Bu `CRichEditView` nesnedeki metnin uzunluğunu hesaplamak için bu üye işlevi çağırın.

```
long GetTextLengthEx(
    DWORD dwFlags,
    UINT uCodePage = -1) const;
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
Metin uzunluğunu belirlemede kullanılacak yöntemi belirten değer. Bu üye, Windows SDK açıklanan [gettextlengthex](/windows/win32/api/richedit/ns-richedit-gettextlengthex) öğesinin Flags üyesinde listelenen değerlerden biri veya daha fazlası olabilir.

*Uıcodepage*<br/>
Çeviri için kod sayfası (CP_ACP for ANSI Code Page, UNICODE için 1200).

### <a name="return-value"></a>Dönüş Değeri

Düzenleme denetimindeki karakter veya bayt sayısı. *DwFlags*içinde uyumsuz bayraklar ayarlandıysa, bu üye işlevi E_INVALIDARG döndürür.

### <a name="remarks"></a>Açıklamalar

`GetTextLengthEx`metnin uzunluğunu belirlemenin ek yollarını sağlar. Zengin düzenleme 2,0 işlevini destekler. Daha fazla bilgi için, Windows SDK [zengin düzenleme denetimleri hakkında](/windows/win32/Controls/about-rich-edit-controls) bölümüne bakın.

##  <a name="insertfileasobject"></a>CRichEditView:: ınsertfileasobject

Belirtilen dosyayı ( [Cricheditcntritıtem](../../mfc/reference/cricheditcntritem-class.md) nesnesi olarak) zengin bir düzenleme görünümüne eklemek için bu işlevi çağırın.

```
void InsertFileAsObject(LPCTSTR lpszFileName);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
Eklenecek dosyanın adını içeren dize.

##  <a name="insertitem"></a>CRichEditView:: InsertItem

Bir [Cricheditcntridıtem](../../mfc/reference/cricheditcntritem-class.md) nesnesini bir zengin düzenleme görünümüne eklemek için bu işlevi çağırın.

```
HRESULT InsertItem(CRichEditCntrItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Eklenecek öğenin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Ekleme başarısını belirten bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

HRESULT hakkında daha fazla bilgi için bkz. Windows SDK [com hata kodları yapısı](/windows/win32/com/structure-of-com-error-codes) .

##  <a name="isricheditformat"></a>CRichEditView:: IsRichEditFormat

*CF* 'nin metin, zengin metın veya OLE öğeleriyle zengin metin olan bir Pano biçimi olup olmadığını öğrenmek için bu işlevi çağırın.

```
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```

### <a name="parameters"></a>Parametreler

*CF*<br/>
İlgilendiğiniz Pano biçimi.

### <a name="return-value"></a>Dönüş Değeri

*CF* zengin düzenleme veya metin panosu biçimindeyse sıfır dışı.

##  <a name="isselected"></a>CRichEditView:: IsSelected

Bu görünümde belirtilen OLE öğesinin seçili olup olmadığını öğrenmek için bu işlevi çağırın.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>Parametreler

*pDocItem*<br/>
Görünümdeki bir nesneye yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Nesne seçiliyse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Türetilmiş Görünüm sınıfınızın OLE öğelerinin seçimini işlemek için farklı bir yöntemi varsa, bu işlevi geçersiz kılın.

##  <a name="m_nbulletindent"></a>CRichEditView:: m_nBulletIndent

Bir listedeki madde işareti öğelerinin girintileme; Varsayılan olarak, 1/2 inç olan 720 birim.

```
int m_nBulletIndent;
```

##  <a name="m_nwordwrap"></a>CRichEditView:: m_nWordWrap

Bu zengin düzenleme görünümü için sözcük kaymasının türünü gösterir.

```
int m_nWordWrap;
```

### <a name="remarks"></a>Açıklamalar

Aşağıdaki değerlerden biri:

- `WrapNone`Otomatik sözcük kaydırma olmadığını gösterir.

- `WrapToWindow`Pencerenin genişliğine göre sözcük kaydırmayı gösterir.

- `WrapToTargetDevice`Hedef cihazın özelliklerine göre sözcük kaydırmayı gösterir.

### <a name="example"></a>Örnek

  [CRichEditView:: WrapChanged](#wrapchanged)için örneğe bakın.

##  <a name="onchareffect"></a>CRichEditView:: OnCharEffect

Geçerli seçimin karakter biçimlendirme efektlerini değiştirmek için bu işlevi çağırın.

```
void OnCharEffect(
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Parametreler

*dwMask*<br/>
Geçerli seçimde değişiklik yapmak için karakter biçimlendirme etkileri.

*dwEffect*<br/>
Geçiş için istenen karakter biçimlendirme etkileri listesi.

### <a name="remarks"></a>Açıklamalar

Bu işleve yapılan her çağrı, geçerli seçim için belirtilen biçimlendirme efektlerini değiştirir.

*DwMask* ve *dwEffect* parametreleri ve olası değerleri hakkında daha fazla bilgi için Windows SDK [Charformat](/windows/win32/api/richedit/ns-richedit-charformata) 'ın ilgili veri üyelerine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]

##  <a name="onfindnext"></a>CRichEditView:: onsonra

Bul/Değiştir iletişim kutusundan komutlar işlenirken Framework tarafından çağırılır.

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

*bNext*<br/>
Aramanın yönü: Doğru değeri belirtir; YANLıŞ, yukarı.

*bCase*<br/>
Aramanın büyük/küçük harfe duyarlı olup olmayacağını gösterir.

*Sözcük*<br/>
Aramanın yalnızca tüm sözcüklerden eşleşip eşleşmeyeceğini gösterir.

### <a name="remarks"></a>Açıklamalar

İçindeki metni bulmak için bu işlevi çağırın `CRichEditView`. Türetilmiş Görünüm sınıfınızın arama özelliklerini değiştirmek için bu işlevi geçersiz kılın.

##  <a name="oninitialupdate"></a>CRichEditView:: OnInitialUpdate

Görünüm belgeye ilk iliştirildikten sonra, ancak görünüm ilk görüntülenmeden önce Framework tarafından çağırılır.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması, ipucu bilgisi olmadan [CView:: OnUpdate](../../mfc/reference/cview-class.md#onupdate) üye işlevini çağırır (diğer bir deyişle, *lipucu* parametresi için 0 varsayılan değerlerini kullanarak ve *phınt* parametresi için null). Belge hakkında bilgi gerektiren tek seferlik başlatma gerçekleştirmek için bu işlevi geçersiz kılın. Örneğin, uygulamanız sabit boyutlu belgeler içeriyorsa, belgenin boyutuna bağlı olarak bir görünümün kaydırma sınırlarını başlatmak için bu işlevi kullanabilirsiniz. Uygulamanız değişken boyutlu belgeleri destekliyorsa, belgenin her değiştirilişinde `OnUpdate` kaydırma sınırlarını güncelleştirmek için kullanın.

### <a name="example"></a>Örnek

  [CRichEditView:: m_nWordWrap](#m_nwordwrap)için örneğe bakın.

##  <a name="onpastenativeobject"></a>CRichEditView:: OnPasteNativeObject

Katıştırılmış bir öğeden yerel verileri yüklemek için bu işlevi kullanın.

```
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```

### <a name="parameters"></a>Parametreler

*lpStg*<br/>
[Isstorage](/windows/win32/api/objidl/nn-objidl-istorage) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde, 0;

### <a name="remarks"></a>Açıklamalar

Genellikle bunu, `IStorage`etrafında bir [COleStreamFile](../../mfc/reference/colestreamfile-class.md) oluşturarak yapabilirsiniz. , `COleStreamFile` Verileri yüklemek için çağrılan bir arşive ve [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) öğesine eklenebilir.

Bu gelişmiş bir geçersiz kılınabilir.

Daha fazla bilgi için Windows SDK içindeki [IStorage](/windows/win32/api/objidl/nn-objidl-istorage) ' a bakın.

##  <a name="onparaalign"></a>CRichEditView:: Onparaalıgn

Seçili paragrafların paragraf hizalamasını değiştirmek için bu işlevi çağırın.

```
void OnParaAlign(WORD wAlign);
```

### <a name="parameters"></a>Parametreler

*wAlign*<br/>
İstenen paragraf hizalaması. Aşağıdaki değerlerden biri:

- PFA_LEFT, paragrafları sol kenar boşluğu ile hizalayın.

- PFA_RIGHT, paragrafları sağ kenar boşluğu ile hizalayın.

- PFA_CENTER kenar boşlukları arasındaki paragrafları ortalayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]

##  <a name="onprinterchanged"></a>CRichEditView:: OnPrinterChanged

Yazıcı değiştiğinde bu zengin düzenleme görünümünün özelliklerini değiştirmek için bu işlevi geçersiz kılın.

```
virtual void OnPrinterChanged(const CDC& dcPrinter);
```

### <a name="parameters"></a>Parametreler

*dcPrinter*<br/>
Yeni yazıcı için bir [CDC](../../mfc/reference/cdc-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, çıkış cihazının (yazıcı) fiziksel yükseklik ve genişliğine göre kağıt boyutunu ayarlar. *DcPrinter*ile ilişkili hiçbir cihaz bağlamı yoksa, varsayılan uygulama, kağıt boyutunu 11 inç olarak 8,5 olarak ayarlar.

##  <a name="onreplaceall"></a>CRichEditView:: OnReplaceAll

' In Değiştir iletişim kutusundaki tüm komutları değiştir işlemi işlenirken Framework tarafından çağırılır.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Değiştirilmekte olan metin.

*lpszReplace*<br/>
Yerine konacak metin.

*bCase*<br/>
Aramanın büyük/küçük harfe duyarlı olup olmadığını gösterir.

*Sözcük*<br/>
Aramanın tüm sözcükleri seçip seçmeyeceğini gösterir.

### <a name="remarks"></a>Açıklamalar

Belirli bir metnin tüm tekrarlamalarını başka bir dizeyle değiştirmek için bu işlevi çağırın. Bu görünümün arama özelliklerini değiştirmek için bu işlevi geçersiz kılın.

### <a name="example"></a>Örnek

  [CRichEditView:: FindText](#findtext)için örneğe bakın.

##  <a name="onreplacesel"></a>CRichEditView:: OnReplaceSel

Değiştir iletişim kutusundan Replace komutları işlenirken Framework tarafından çağırılır.

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
Değiştirilmekte olan metin.

*bNext*<br/>
Aramanın yönünü gösterir: DOĞRU değil; YANLıŞ, yukarı.

*bCase*<br/>
Aramanın büyük/küçük harfe duyarlı olup olmadığını gösterir.

*Sözcük*<br/>
Aramanın tüm sözcükleri seçip seçmeyeceğini gösterir.

*lpszReplace*<br/>
Yerine konacak metin.

### <a name="remarks"></a>Açıklamalar

Belirli bir metnin bir oluşumunu başka bir dizeyle değiştirmek için bu işlevi çağırın. Bu görünümün arama özelliklerini değiştirmek için bu işlevi geçersiz kılın.

##  <a name="ontextnotfound"></a>CRichEditView:: OnTextNotFound

Bir arama başarısız olduğunda Framework tarafından çağırılır.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Bulunamayan metin.

### <a name="remarks"></a>Açıklamalar

[Messagebip bip](/windows/win32/api/winuser/nf-winuser-messagebeep)çıkış bildirimini değiştirmek için bu işlevi geçersiz kılın.

Daha fazla bilgi için Windows SDK bakın [Messagebip](/windows/win32/api/winuser/nf-winuser-messagebeep) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]

##  <a name="onupdatechareffect"></a>CRichEditView:: OnUpdateCharEffect

Çerçeve, komut Kullanıcı arabirimini karakter efekti komutlarına güncelleştirmek için bu işlevi çağırır.

```
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
[CCmdUI](../../mfc/reference/ccmdui-class.md) nesnesine yönelik işaretçi.

*dwMask*<br/>
Karakter biçimlendirme maskesini belirtir.

*dwEffect*<br/>
Karakter biçimlendirme efektini gösterir.

### <a name="remarks"></a>Açıklamalar

Maske *dwMask* , denetlenecek karakter biçimlendirme özniteliklerini belirtir. Flags *dwEffect* , ayarlanacak/Clear karakter biçimlendirme özniteliklerini listeler.

*DwMask* ve *dwEffect* parametreleri ve olası değerleri hakkında daha fazla bilgi için Windows SDK [Charformat](/windows/win32/api/richedit/ns-richedit-charformata) 'ın ilgili veri üyelerine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]

##  <a name="onupdateparaalign"></a>CRichEditView:: Onupdateparamalign

Framework, paragraf efekti komutlarının komut Kullanıcı arabirimini güncelleştirmek için bu işlevi çağırır.

```
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,
    WORD wAlign);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
[CCmdUI](../../mfc/reference/ccmdui-class.md) nesnesine yönelik işaretçi.

*wAlign*<br/>
Denetlenecek paragraf hizalaması. Aşağıdaki değerlerden biri:

- PFA_LEFT, paragrafları sol kenar boşluğu ile hizalayın.

- PFA_RIGHT, paragrafları sağ kenar boşluğu ile hizalayın.

- PFA_CENTER kenar boşlukları arasındaki paragrafları ortalayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]

##  <a name="printinsiderect"></a>CRichEditView::P rintInsideRect

Bir zengin düzenleme denetimindeki metin aralığını, *PDC*tarafından belirtilen cihaz Için *rectLayout* içine sığacak şekilde biçimlendirmek için bu işlevi çağırın.

```
long PrintInsideRect(
    CDC* pDC,
    RECT& rectLayout,
    long nIndexStart,
    long nIndexStop,
    BOOL bOutput);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Çıkış alanı için bir cihaz bağlamı işaretçisi.

*rectLayout*<br/>
Çıktı alanını tanımlayan [Rect](/windows/win32/api/windef/ns-windef-rect) veya [CRect](../../atl-mfc-shared/reference/crect-class.md) .

*nIndexStart*<br/>
Biçimlendirilecek ilk karakterin sıfır tabanlı dizini.

*Nındexstop*<br/>
Biçimlendirilecek son karakterin sıfır tabanlı dizini.

*i koyun*<br/>
Metnin işlenip işlenmeyeceğini gösterir. YANLıŞ ise metin yalnızca ölçülmüş olur.

### <a name="return-value"></a>Dönüş Değeri

Çıktı alanına uyan son karakterin dizini ve bir.

### <a name="remarks"></a>Açıklamalar

Genellikle, bu çağrının ardından çıktıyı oluşturan [CRichEditCtrl::D ıplayband](../../mfc/reference/cricheditctrl-class.md#displayband) çağrısı vardır.

### <a name="example"></a>Örnek

  [CRichEditView:: GetPaperSize](#getpapersize)için örneğe bakın.

##  <a name="printpage"></a>CRichEditView::P rintPage

*PDC*tarafından belirtilen çıkış aygıtı için bir zengin düzenleme denetimindeki metin aralığını biçimlendirmek için bu işlevi çağırın.

```
long PrintPage(
    CDC* pDC,
    long nIndexStart,
    long nIndexStop);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Sayfa çıktısı için bir cihaz bağlamı işaretçisi.

*nIndexStart*<br/>
Biçimlendirilecek ilk karakterin sıfır tabanlı dizini.

*Nındexstop*<br/>
Biçimlendirilecek son karakterin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Sayfaya uyan son karakterin dizini ve bir.

### <a name="remarks"></a>Açıklamalar

Her sayfanın düzeni [GetPageRect](#getpagerect) ve [GetPrintRect](#getprintrect)tarafından denetlenir. Genellikle, bu çağrının ardından çıktıyı oluşturan [CRichEditCtrl::D ıplayband](../../mfc/reference/cricheditctrl-class.md#displayband) çağrısı vardır.

Kenar boşluklarının mantıksal sayfa değil fiziksel sayfaya göreli olduğunu unutmayın. Bu nedenle, çoğu yazıcının sayfada yazdırılabilir alanı olduğundan, sıfır kenar boşlukları genellikle metni kırpacaktır. Metninizi kırpmadan kaçınmak için, [Setkenar boşluklarını](#setmargins) çağırmanız ve yazdırmadan önce makul kenar boşlukları ayarlamanız gerekir.

##  <a name="queryacceptdata"></a>CRichEditView:: QueryAcceptData

Zengin düzenlemeye bir nesne yapıştırmak için Framework tarafından çağırılır.

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
Sorgu için [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) işaretçisi.

*lpcfFormat*<br/>
Kabul edilebilir veri biçimine yönelik işaretçi.

*dwReco*<br/>
Kullanılmadı.

*Bresel olarak*<br/>
Yapıştırma işleminin devam edip edemeyeceğini gösterir.

*hMetaFile*<br/>
Öğenin simgesini çizmek için kullanılan meta dosyası için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

İşlemin başarısını bildiren bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Türetilmiş belge sınıfınıza ait farklı COM öğeleri organizasyonunu işlemek için bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz kılınabilir.

HRESULT ve `IDataObject`hakkında daha fazla bilgi [için, Windows SDK](/windows/win32/api/objidl/nn-objidl-idataobject)sırasıyla [com hata kodlarının ve IDataObject 'nin yapısına](/windows/win32/com/structure-of-com-error-codes) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]

##  <a name="setcharformat"></a>CRichEditView:: SetCharFormat

Bu `CRichEditView` nesnedeki yeni metin için karakter biçimlendirme özniteliklerini ayarlamak için bu işlevi çağırın.

```
void SetCharFormat(CHARFORMAT2 cf);
```

### <a name="parameters"></a>Parametreler

*CF*<br/>
Yeni varsayılan karakter biçimlendirme özniteliklerini içeren [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) yapısı.

### <a name="remarks"></a>Açıklamalar

Yalnızca `dwMask` *CF* üyesi tarafından belirtilen öznitelikler bu işlev tarafından değiştirilir.

Daha fazla bilgi için Windows SDK [EM_SETCHARFORMAT](/windows/win32/Controls/em-setcharformat) Message and [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) Structure bölümüne bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

##  <a name="setmargins"></a>CRichEditView:: Setkenar boşlukları

Bu zengin düzenleme görünümü için yazdırma kenar boşluklarını ayarlamak için bu işlevi çağırın.

```
void SetMargins(const CRect& rectMargin);
```

### <a name="parameters"></a>Parametreler

*rectMargin*<br/>
Yazdırma için yeni kenar boşluğu değerleri MM_TWIPS cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

[M_nWordWrap](#m_nwordwrap) `WrapToTargetDevice`ise, yazdırma özelliklerini ayarlamak için bu işlevi kullandıktan sonra [WrapChanged](#wrapchanged) öğesini çağırmanız gerekir.

[PrintPage](#printpage) tarafından kullanılan kenar boşluklarının mantıksal sayfa değil fiziksel sayfaya göreli olduğunu unutmayın. Bu nedenle, çoğu yazıcının sayfada yazdırılabilir alanı olduğundan, sıfır kenar boşlukları genellikle metni kırpacaktır. Metninizin kırpılmasını önlemek için, yazdırmadan önce makul yazıcı `SetMargins` kenar boşluklarını ayarlamak üzere Use çağrısını yapmanız gerekir.

### <a name="example"></a>Örnek

  [CRichEditView:: GetPaperSize](#getpapersize)için örneğe bakın.

##  <a name="setpapersize"></a>CRichEditView:: SetPaperSize

Bu zengin düzenleme görünümünün yazdırılması için kağıt boyutunu ayarlamak üzere bu işlevi çağırın.

```
void SetPaperSize(CSize sizePaper);
```

### <a name="parameters"></a>Parametreler

*sizePaper*<br/>
Yazdırma için yeni kağıt boyutu değerleri MM_TWIPS cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

[M_nWordWrap](#m_nwordwrap) `WrapToTargetDevice`ise, yazdırma özelliklerini ayarlamak için bu işlevi kullandıktan sonra [WrapChanged](#wrapchanged) öğesini çağırmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]

##  <a name="setparaformat"></a>CRichEditView:: SetParaFormat

Bu `CRichEditView` nesnedeki geçerli seçimin paragraf biçimlendirme özniteliklerini ayarlamak için bu işlevi çağırın.

```
BOOL SetParaFormat(PARAFORMAT2& pf);
```

### <a name="parameters"></a>Parametreler

*PF*<br/>
Yeni varsayılan paragraf biçimlendirme özniteliklerini içeren [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde, 0.

### <a name="remarks"></a>Açıklamalar

Yalnızca `dwMask` *PF* üyesi tarafından belirtilen öznitelikler bu işlev tarafından değiştirilir.

Daha fazla bilgi için Windows SDK [EM_SETPARAFORMAT](/windows/win32/Controls/em-setparaformat) Message and [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) Structure bölümüne bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]

##  <a name="textnotfound"></a>CRichEditView:: TextNotFound

Başarısız bir [FindText](#findtext)çağrısından sonra [CRichEditView](../../mfc/reference/cricheditview-class.md) denetiminin iç arama durumunu sıfırlamak için bu işlevi çağırın.

```
void TextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Bulunamayan metin dizesini içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin, denetimin iç arama durumunun düzgün şekilde sıfırlanması için, [FindText](#findtext) 'e başarısız çağrılar yapıldıktan hemen sonra çağrılması önerilir.

*LpszFind* parametresi, [FindText](#findtext)için girilen dizeyle aynı içeriği içermelidir. İç arama durumu sıfırlandıktan sonra, bu yöntem, belirtilen arama dizesiyle [OnTextNotFound](#ontextnotfound) yöntemini çağırır.

### <a name="example"></a>Örnek

  [CRichEditView:: FindText](#findtext)için örneğe bakın.

##  <a name="wrapchanged"></a>CRichEditView:: WrapChanged

Yazdırma Özellikleri değiştiğinde bu işlevi çağırın ( [Setkenar boşlukları](#setmargins) veya [SetPaperSize](#setpapersize)).

```
virtual void WrapChanged();
```

### <a name="remarks"></a>Açıklamalar

Zengin düzenleme görünümünün [m_nWordWrap](#m_nwordwrap) veya yazdırma özellikleri 'ndeki değişikliklere yanıt verme şeklini değiştirmek için bu işlevi geçersiz kılın ( [OnPrinterChanged](#onprinterchanged)).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRichEditDoc Sınıfı](../../mfc/reference/cricheditdoc-class.md)<br/>
[CRichEditCntrItem Sınıfı](../../mfc/reference/cricheditcntritem-class.md)
