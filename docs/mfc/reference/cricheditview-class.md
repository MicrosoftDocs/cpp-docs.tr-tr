---
title: CRichEditView Sınıfı
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
ms.openlocfilehash: 2d832f3cc07d39ace9e679901c5344a376cea03c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318631"
---
# <a name="cricheditview-class"></a>CRichEditView Sınıfı

[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) ve [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)ile, MFC'nin belge görünümü mimarisi bağlamında zengin edit denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CRichEditView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CRichEditView::CRichEditView](#cricheditview)|Bir `CRichEditView` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRichEditView::AyarlamaDialogPosition](#adjustdialogposition)|Geçerli seçimi gizlememesi için bir iletişim kutusu taşır.|
|[CRichEditView::CanPaste](#canpaste)|Panozengin edit görünümüne yapıştırılabilir veri bulunup olmadığını söyler.|
|[CRichEditView::DoPaste](#dopaste)|Bu zengin edit görünümüne bir OLE öğesi yapıştırır.|
|[CRichEditView::FindText](#findtext)|Bekleme imlecini çağırarak belirtilen metni bulur.|
|[CRichEditView::FindTextSimple](#findtextsimple)|Belirtilen metni bulur.|
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|Geçerli seçim için karakter biçimlendirme özniteliklerini alır.|
|[CRichEditView::GetDocument](#getdocument)|İlgili [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)için bir işaretçi alır.|
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|Zengin edit görünümünde şu anda etkin olan OLE öğesini alır.|
|[CRichEditView::GetMargins](#getmargins)|Bu zengin edit görünümü için kenar boşluklarını alır.|
|[CRichEditView::GetPageRect](#getpagerect)|Bu zengin edit görünümü için sayfa dikdörtgenini alır.|
|[CRichEditView::GetPaperSize](#getpapersize)|Bu zengin edit görünümü için kağıt boyutunu alır.|
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|Geçerli seçim için paragraf biçimlendirme özniteliklerini alır.|
|[CRichEditView::GetPrintRect](#getprintrect)|Bu zengin edit görünümü için yazdırma dikdörtgenini alır.|
|[CRichEditView::GetPrintWidth](#getprintwidth)|Bu zengin edit görünümü için yazdırma genişliğini alır.|
|[CRichEditView::GetRichEditCtrl](#getricheditctrl)|Zengin edit denetimini alır.|
|[CRichEditView::GetSelectedItem](#getselecteditem)|Seçili öğeyi zengin edit görünümünden alır.|
|[CRichEditView::GetTextLength](#gettextlength)|Zengin edit görünümünde metnin uzunluğunu alır.|
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|Zengin düzenleme görünümünde karakter veya bayt sayısını alır. Uzunluğu belirleme yöntemi için genişletilmiş bayrak listesi.|
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|Dosyayı OLE öğesi olarak ekler.|
|[CRichEditView::InsertItem](#insertitem)|Yeni bir öğeyi OLE öğesi olarak ekler.|
|[CRichEditView::IsRichEditFormat](#isricheditformat)|Panozengin bir edit veya metin biçiminde veri içerip içermediğini söyler.|
|[CRichEditView::OnCharEffect](#onchareffect)|Geçerli seçim için karakter biçimlendirmesini geçişe çıkarır.|
|[CRichEditView::OnParaAlign](#onparaalign)|Paragrafların hizalanmasını değiştirir.|
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|Karakter ortak üye işlevleri için Komut UI'sini güncelleştirir.|
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|Paragraf ortak üye işlevleri için Komut UI'sini güncelleştirir.|
|[CRichEditView::PrintInsideRect](#printinsiderect)|Belirtilen metni verilen dikdörtgen içinde biçimlendirin.|
|[CRichEditView::PrintPage](#printpage)|Verilen sayfadaki belirtilen metni biçimlendirin.|
|[CRichEditView::SetCharFormat](#setcharformat)|Geçerli seçim için karakter biçimlendirme özniteliklerini ayarlar.|
|[CRichEditView::SetMargins](#setmargins)|Bu zengin edit görünümü için kenar boşluklarını ayarlar.|
|[CRichEditView::SetPaperSize](#setpapersize)|Bu zengin edit görünümü için kağıt boyutunu ayarlar.|
|[CRichEditView::SetParaFormat](#setparaformat)|Geçerli seçim için paragraf biçimlendirme özniteliklerini ayarlar.|
|[CRichEditView::TextNotFound](#textnotfound)|Denetimin iç arama durumunu sıfırlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRichEditView::GetClipboardData](#getclipboarddata)|Bu zengin edit görünümünde bir aralık için bir Pano nesnesi alır.|
|[CRichEditView::GetContextMenu](#getcontextmenu)|Sağ fare düğmesinde kullanmak üzere bir bağlam menüsü alır.|
|[CRichEditView::Seçili](#isselected)|Verilen OLE öğesinin seçilip seçilmediğini gösterir.|
|[CRichEditView::OnFindNext](#onfindnext)|Bir alt dizenin bir sonraki oluşumunu bulur.|
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|Bir belgeye ilk eklendiğinde görünümü yeniler.|
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|Bir OLE öğesinden yerel verileri alır.|
|[CRichEditView::OnPrinterDeğiştirildi](#onprinterchanged)|Verilen aygıta yazdırma özelliklerini ayarlar.|
|[CRichEditView::OnReplaceAll](#onreplaceall)|Belirli bir dizedeki tüm oluşumları yeni bir dizeyle değiştirir.|
|[CRichEditView::OnReplaceSel](#onreplacesel)|Geçerli seçimin yerine alır.|
|[CRichEditView::OnTextNotFound](#ontextnotfound)|İstenen metnin bulunamadıklarına dair kullanıcı bildirimini işler.|
|[CRichEditView::QueryAcceptData](#queryacceptdata)|Üzerinde veri hakkında görmek için `IDataObject`sorgular .|
|[CRichEditView::WrapChanged](#wrapchanged)|Bu zengin edit görünümü için hedef çıktı aygıtını. `m_nWordWrap`|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|Madde işareti listeleri için girintin miktarını gösterir.|
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|Kaydırma sözcük kısıtlamalarını gösterir.|

## <a name="remarks"></a>Açıklamalar

"Zengin bir edit denetimi", kullanıcının metni girip atabildiği bir penceredir. Metin karakter ve paragraf biçimlendirme atanabilir ve katışılmış OLE nesneleri içerebilir. Zengin edit denetimleri metni biçimlendirmek için bir programlama arabirimi sağlar. Ancak, bir uygulama, biçimlendirme işlemlerini kullanıcının kullanımına açmak için gereken kullanıcı arabirimi bileşenlerini uygulamalıdır.

`CRichEditView`metnin metin ve biçimlendirme özelliğini korur. `CRichEditDoc`görünümde bulunan OLE istemci öğelerinin listesini tutar. `CRichEditCntrItem`OLE istemci öğesine kapsayıcı tarafı erişimi sağlar.

Bu Windows Ortak denetimi (ve dolayısıyla [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) yalnızca Windows 95/98 ve Windows NT sürümleri 3.51 ve sonraki sürümler altında çalışan programlar için kullanılabilir.

Bir MFC uygulamasında zengin bir edit görünümü kullanma örneği için [WORDPAD](../../overview/visual-cpp-samples.md) örnek uygulamasına bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cview](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CRichEditView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrich.h

## <a name="cricheditviewadjustdialogposition"></a><a name="adjustdialogposition"></a>CRichEditView::AyarlamaDialogPosition

Geçerli seçimi gizlememesi için verilen iletişim kutusunu taşımak için bu işlevi arayın.

```
void AdjustDialogPosition(CDialog* pDlg);
```

### <a name="parameters"></a>Parametreler

*pDlg*<br/>
Bir `CDialog` nesneye işaretçi.

## <a name="cricheditviewcanpaste"></a><a name="canpaste"></a>CRichEditView::CanPaste

Pano'nun bu zengin edit görünümüne yapıştırılabilen bilgiler içerip içermediğini belirlemek için bu işlevi arayın.

```
BOOL CanPaste() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pano, bu zengin edit görünümünün kabul edebileceği bir biçimde veri içeriyorsa sıfıra inme; aksi takdirde, 0.

## <a name="cricheditviewcricheditview"></a><a name="cricheditview"></a>CRichEditView::CRichEditView

Bir `CRichEditView` nesne oluşturmak için bu işlevi çağırın.

```
CRichEditView();
```

## <a name="cricheditviewdopaste"></a><a name="dopaste"></a>CRichEditView::DoPaste

*Dataobj'deki* OLE öğesini bu zengin edit belgesine/görünümüne yapıştırmak için bu işlevi arayın.

```
void DoPaste(
    COleDataObject& dataobj,
    CLIPFORMAT cf,
    HMETAFILEPICT hMetaPict);
```

### <a name="parameters"></a>Parametreler

*dataobj*<br/>
Yapıştırılabilmek için verileri içeren [COleDataObject.](../../mfc/reference/coledataobject-class.md)

*Cf*<br/>
İstenilen Pano biçimi.

*hMetaPict*<br/>
Yapıştırılacak öğeyi temsil eden metadosya.

### <a name="remarks"></a>Açıklamalar

Çerçeve [QueryAcceptData](#queryacceptdata)varsayılan uygulamasının bir parçası olarak bu işlevi çağırır.

Bu işlev, Yapıştır Özel için işleyicisonuçlarına göre yapıştırın türünü belirler. *CF* 0 ise, yeni öğe geçerli ikonik gösterimi kullanır. *CF* sıfır değilse ve *hMetaPict* NULL değilse, yeni öğe temsili için *hMetaPict* kullanır.

## <a name="cricheditviewfindtext"></a><a name="findtext"></a>CRichEditView::FindText

Belirtilen metni bulmak için bu işlevi arayın ve geçerli seçim olarak ayarlayın.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszBul*<br/>
Aranacak dizeyi içerir.

*bCase*<br/>
Aramanın büyük/küçük harf duyarlı olup olmadığını gösterir.

*bWord*<br/>
Aramanın sözcüklerin bölümleriyle değil, yalnızca tüm sözcüklerle eşleşip eşleşmediğini gösterir.

*bSonraki*<br/>
Aramanın yönünü gösterir. DOĞRUysa, arama yönü arabelleğin sonuna doğru. FALSE ise, arama yönü arabelleğin başına doğru.

### <a name="return-value"></a>Dönüş Değeri

*LpszFind metni bulunursa* sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bulma işlemi sırasında bekleme imlecini görüntüler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]

## <a name="cricheditviewfindtextsimple"></a><a name="findtextsimple"></a>CRichEditView::FindTextSimple

Belirtilen metni bulmak için bu işlevi arayın ve geçerli seçim olarak ayarlayın.

```
BOOL FindTextSimple(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszBul*<br/>
Aranacak dizeyi içerir.

*bCase*<br/>
Aramanın büyük/küçük harf duyarlı olup olmadığını gösterir.

*bWord*<br/>
Aramanın sözcüklerin bölümleriyle değil, yalnızca tüm sözcüklerle eşleşip eşleşmediğini gösterir.

*bSonraki*<br/>
Aramanın yönünü gösterir. DOĞRUysa, arama yönü arabelleğin sonuna doğru. FALSE ise, arama yönü arabelleğin başına doğru.

### <a name="return-value"></a>Dönüş Değeri

*LpszFind metni bulunursa* sıfır olmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

  [CRichEditView örneğine bakın:FindText](#findtext).

## <a name="cricheditviewgetcharformatselection"></a><a name="getcharformatselection"></a>CRichEditView::GetCharFormatSelection

Geçerli seçimin karakter biçimlendirme özniteliklerini almak için bu işlevi arayın.

```
CHARFORMAT2& GetCharFormatSelection();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli seçimin karakter biçimlendirme özniteliklerini içeren [charformat2](/windows/win32/api/richedit/ns-richedit-charformat2w) yapısı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için, Windows SDK'daki [EM_GETCHARFORMAT](/windows/win32/Controls/em-getcharformat) iletive [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) yapısına bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

## <a name="cricheditviewgetclipboarddata"></a><a name="getclipboarddata"></a>CRichEditView::GetClipboardData

Çerçeve [IRichEditOleCallback](/windows/win32/api/richole/nf-richole-iricheditolecallback-getclipboarddata)işleme nin bir parçası olarak bu işlevi çağırır::GetClipboardData .

```
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,
    DWORD dwReco,
    LPDATAOBJECT lpRichDataObj,
    LPDATAOBJECT* lplpdataobj);
```

### <a name="parameters"></a>Parametreler

*lpchrg*<br/>
*LPLPdataobj*tarafından belirtilen veri nesnesine kopyalamak için karakter (ve OLE öğeleri) aralığını belirten [CHARRANGE](/windows/win32/api/richedit/ns-richedit-charrange) yapısına işaretçi.

*dwReco*<br/>
Pano operasyon bayrağı. Bu değerlerden biri olabilir.

- panoya RECO_COPY kopyalayın.

- panoya RECO_CUT kes.

- RECO_DRAG Sürükleme işlemi (sürükle ve bırak).

- RECO_DROP Bırak işlemi (sürükle ve bırak).

- Panodan RECO_PASTE Yapıştır.

*lpRichDataObj*<br/>
Zengin edit denetiminden Pano verilerini içeren bir [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) nesnesine işaretçi [(IRichEditOle::GetClipboardData).](/windows/win32/api/richole/nf-richole-iricheditole-getclipboarddata)

*lplpdataobj*<br/>
*Lpchrg* parametresinde belirtilen aralığı `IDataObject` temsil eden nesnenin adresini alan işaretçi değişkenini işaretçi. Bir hata döndürülürse *lplpdataobj* değeri yoksayılır.

### <a name="return-value"></a>Dönüş Değeri

Operasyonun başarısını bildiren bir HRESULT değeri. HRESULT hakkında daha fazla bilgi için Windows SDK'daki [COM Hata Kodlarının Yapısı'na](/windows/win32/com/structure-of-com-error-codes) bakın.

### <a name="remarks"></a>Açıklamalar

İade değeri başarıyı `IRichEditOleCallback::GetClipboardData` gösteriyorsa, `IDataObject` *lplpdataobj*tarafından erişilen leri döndürür; aksi takdirde, *lpRichDataObj*tarafından erişilen bir döndürür. Kendi Pano verilerinizi sağlamak için bu işlevi geçersiz kılın. Bu işlevin varsayılan uygulaması E_NOTIMPL döndürür.

Bu gelişmiş bir geçersiz.

Daha fazla bilgi için, [Bkz. IRichEditOle::GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditole-getclipboarddata), [IRichEditOleCallback::GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditolecallback-getclipboarddata)ve [CHARRANGE](/windows/win32/api/richedit/ns-richedit-charrange) Windows SDK'da ve Windows SDK'da [IDataObject'e](/windows/win32/api/objidl/nn-objidl-idataobject) bakın.

## <a name="cricheditviewgetcontextmenu"></a><a name="getcontextmenu"></a>CRichEditView::GetContextMenu

Çerçeve [IRichEditOleCallback](/windows/win32/api/richole/nf-richole-iricheditolecallback-getcontextmenu)işleme nin bir parçası olarak bu işlevi çağırır::GetContextMenu .

```
virtual HMENU GetContextMenu(
    WORD seltyp,
    LPOLEOBJECT lpoleobj,
    CHARRANGE* lpchrg);
```

### <a name="parameters"></a>Parametreler

*seltyp*<br/>
Seçim türü. Seçim türü değerleri Açıklamalar bölümünde açıklanmıştır.

*lpoleobj*<br/>
Seçim bir `OLEOBJECT` veya daha fazla OLE öğesi içeriyorsa, ilk seçili OLE nesnesini belirten bir yapıyı işaretçi. Seçim öğe *içermisse, lpoleobj* NULL'dur. Yapı, `OLEOBJECT` OLE nesnesi v-tablosuna işaretçi tutar.

*lpchrg*<br/>
Geçerli seçimi içeren bir [CHARRANGE](/windows/win32/api/richedit/ns-richedit-charrange) yapısı için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bağlam menüsüne işleyin.

### <a name="remarks"></a>Açıklamalar

Bu işlev, sağ fare düğmesi aşağı işlemetipik bir parçasıdır.

Seçim türü aşağıdaki bayrakların herhangi bir birleşimi olabilir:

- SEL_EMPTY Geçerli bir seçim olmadığını gösterir.

- SEL_TEXT Geçerli seçimin metin içerdiğini gösterir.

- SEL_OBJECT Geçerli seçimin en az bir OLE öğesi içerdiğini gösterir.

- SEL_MULTICHAR Geçerli seçimin birden fazla metin karakterini içerdiğini gösterir.

- SEL_MULTIOBJECT Geçerli seçilimin birden fazla OLE nesnesi içerdiğini gösterir.

Varsayılan uygulama NULL döndürür. Bu gelişmiş bir geçersiz.

Daha fazla bilgi için Windows SDK'da [IRichEditOleCallback::GetContextMenu](/windows/win32/api/richole/nf-richole-iricheditolecallback-getcontextmenu) ve [CHARRANGE'a](/windows/win32/api/richedit/ns-richedit-charrange) bakın.

## <a name="cricheditviewgetdocument"></a><a name="getdocument"></a>CRichEditView::GetDocument

Bu görünümle `CRichEditDoc` ilişkili bir işaretçi almak için bu işlevi arayın.

```
CRichEditDoc* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenizle ilişkili bir [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) nesnesine `CRichEditView` işaretçi.

## <a name="cricheditviewgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a>CRichEditView::GetInPlaceActiveItem

Şu anda bu `CRichEditView` nesnede yerinde etkinleştirilen OLE öğesini almak için bu işlevi arayın.

```
CRichEditCntrItem* GetInPlaceActiveItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu zengin edit görünümünde tek, yerinde etkin [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) nesnesine işaretçi; Şu anda yerinde etkin durumda olan OLE öğesi yoksa NULL.

## <a name="cricheditviewgetmargins"></a><a name="getmargins"></a>CRichEditView::GetMargins

Yazdırmada kullanılan geçerli kenar boşluklarını almak için bu işlevi arayın.

```
CRect GetMargins() const;
```

### <a name="return-value"></a>Dönüş Değeri

Baskıda kullanılan kenar boşlukları, MM_TWIPS olarak ölçülür.

## <a name="cricheditviewgetpagerect"></a><a name="getpagerect"></a>CRichEditView::GetPageRect

Yazdırmada kullanılan sayfanın boyutlarını almak için bu işlevi arayın.

```
CRect GetPageRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırmada kullanılan sayfanın sınırları, MM_TWIPS cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu değer kağıt boyutuna bağlıdır.

## <a name="cricheditviewgetpapersize"></a><a name="getpapersize"></a>CRichEditView::GetPaperSize

Geçerli kağıt boyutunu almak için bu işlevi arayın.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Baskıda kullanılan kağıdın boyutu, MM_TWIPS cinsinden ölçülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]

## <a name="cricheditviewgetparaformatselection"></a><a name="getparaformatselection"></a>CRichEditView::GetParaFormatSelection

Geçerli seçimin paragraf biçimlendirme özniteliklerini almak için bu işlevi arayın.

```
PARAFORMAT2& GetParaFormatSelection();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli seçimin paragraf biçimlendirme özniteliklerini içeren bir [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) yapısı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [EM_GETPARAFORMAT](/windows/win32/Controls/em-getparaformat) ileti ve [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) yapısına bakın.

## <a name="cricheditviewgetprintrect"></a><a name="getprintrect"></a>CRichEditView::GetPrintRect

Sayfa dikdörtgeni içindeki yazdırma alanının sınırlarını almak için bu işlevi arayın.

```
CRect GetPrintRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Baskıda kullanılan görüntü alanının sınırları, MM_TWIPS cinsinden ölçülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]

## <a name="cricheditviewgetprintwidth"></a><a name="getprintwidth"></a>CRichEditView::GetPrintWidth

Yazdırma alanının genişliğini belirlemek için bu işlevi arayın.

```
int GetPrintWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırma alanının genişliği, MM_TWIPS cinsinden ölçülür.

## <a name="cricheditviewgetricheditctrl"></a><a name="getricheditctrl"></a>CRichEditView::GetRichEditCtrl

Nesneyle ilişkili [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) nesnesini `CRichEditView` almak için bu işlevi arayın.

```
CRichEditCtrl& GetRichEditCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `CRichEditCtrl` görünüm için nesne.

### <a name="example"></a>Örnek

  [CRichEditView örneğine bakın:FindText](#findtext).

## <a name="cricheditviewgetselecteditem"></a><a name="getselecteditem"></a>CRichEditView::GetSelectedItem

Şu anda bu `CRichEditCntrItem` `CRichEditView` nesnede seçili olan OLE öğesini (bir nesne) almak için bu işlevi çağırın.

```
CRichEditCntrItem* GetSelectedItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnede seçilen [cricheditCntrItem](../../mfc/reference/cricheditcntritem-class.md) nesnesine `CRichEditView` işaretçi; Bu görünümde öğe seçili değilse NULL.

## <a name="cricheditviewgettextlength"></a><a name="gettextlength"></a>CRichEditView::GetTextLength

Bu `CRichEditView` nesnedeki metnin uzunluğunu almak için bu işlevi çağırın.

```
long GetTextLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `CRichEditView` nesnedeki metnin uzunluğu.

## <a name="cricheditviewgettextlengthex"></a><a name="gettextlengthex"></a>CRichEditView::GetTextLengthEx

Bu `CRichEditView` nesnedeki metnin uzunluğunu hesaplamak için bu üye işlevi arayın.

```
long GetTextLengthEx(
    DWORD dwFlags,
    UINT uCodePage = -1) const;
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
Metin uzunluğunu belirlemede kullanılacak yöntemi belirten değer. Bu üye, Windows SDK'da açıklanan [GETTEXTLENGTHEX'in](/windows/win32/api/richedit/ns-richedit-gettextlengthex) bayraklarında listelenen değerlerden biri veya birkaçı olabilir.

*uCodePage*<br/>
Çeviri için kod sayfası (ANSI Kod Sayfası için CP_ACP, Unicode için 1200).

### <a name="return-value"></a>Dönüş Değeri

Düzenleme denetimindeki karakter veya bayt sayısı. *dwFlags'de*uyumsuz bayraklar ayarlanmışsa, bu üye işlev E_INVALIDARG döndürür.

### <a name="remarks"></a>Açıklamalar

`GetTextLengthEx`metnin uzunluğunu belirlemenin ek yollarını sağlar. Zengin Edit 2.0 işlevini destekler. Daha fazla bilgi için Windows SDK'daki [Zengin Edit Denetimleri Hakkında'ya](/windows/win32/Controls/about-rich-edit-controls) bakın.

## <a name="cricheditviewinsertfileasobject"></a><a name="insertfileasobject"></a>CRichEditView::InsertFileAsObject

Belirtilen dosyayı [(CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) nesnesi olarak) zengin bir edit görünümüne eklemek için bu işlevi arayın.

```
void InsertFileAsObject(LPCTSTR lpszFileName);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
Eklenecek dosyanın adını içeren dize.

## <a name="cricheditviewinsertitem"></a><a name="insertitem"></a>CRichEditView::InsertItem

Zengin bir edit görünümüne [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) nesnesi eklemek için bu işlevi arayın.

```
HRESULT InsertItem(CRichEditCntrItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Eklenecek öğeyi işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Eklemenin başarısını gösteren bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

HRESULT hakkında daha fazla bilgi için Windows SDK'daki [COM Hata Kodlarının Yapısı'na](/windows/win32/com/structure-of-com-error-codes) bakın.

## <a name="cricheditviewisricheditformat"></a><a name="isricheditformat"></a>CRichEditView::IsRichEditFormat

*CF'nin* metin, zengin metin veya OLE öğelerine sahip zengin metin olan Pano biçimi olup olmadığını belirlemek için bu işlevi arayın.

```
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```

### <a name="parameters"></a>Parametreler

*Cf*<br/>
İlgi Panosu biçimi.

### <a name="return-value"></a>Dönüş Değeri

*Nonzero* cf zengin bir edit veya metin Pano biçimi ise.

## <a name="cricheditviewisselected"></a><a name="isselected"></a>CRichEditView::Seçili

Belirtilen OLE öğesinin bu görünümde şu anda seçilip seçilmeip seçilmeyip seçilmeyip seçilmeyini belirlemek için bu işlevi arayın.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>Parametreler

*pDocItem*<br/>
Görünümdeki bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Nesne seçilirse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Türemiş görünüm sınıfınızda OLE öğelerinin seçimi için farklı bir yöntem varsa bu işlevi geçersiz kılın.

## <a name="cricheditviewm_nbulletindent"></a><a name="m_nbulletindent"></a>CRichEditView::m_nBulletIndent

Bir listedeki madde işareti öğelerinin girintisi; varsayılan olarak, 720 adet, hangi inç.

```
int m_nBulletIndent;
```

## <a name="cricheditviewm_nwordwrap"></a><a name="m_nwordwrap"></a>CRichEditView::m_nWordWrap

Bu zengin edit görünümü için sözcük kaydırma türünü gösterir.

```
int m_nWordWrap;
```

### <a name="remarks"></a>Açıklamalar

Aşağıdaki değerlerden biri:

- `WrapNone`Otomatik sözcük kaydırma olmadığını gösterir.

- `WrapToWindow`Pencerenin genişliğine göre sözcük kaydırmayı gösterir.

- `WrapToTargetDevice`Hedef aygıtın özelliklerine göre sözcük kaydırmayı gösterir.

### <a name="example"></a>Örnek

  [CRichEditView örneğine bakın:WrapChanged](#wrapchanged).

## <a name="cricheditviewonchareffect"></a><a name="onchareffect"></a>CRichEditView::OnCharEffect

Geçerli seçim için karakter biçimlendirme efektlerini geçiş için bu işlevi arayın.

```
void OnCharEffect(
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Parametreler

*Dwmask*<br/>
Geçerli seçimde değiştirmek için karakter biçimlendirme efektleri.

*dwEffect*<br/>
Geçiş için karakter biçimlendirme efektleri istenilen liste.

### <a name="remarks"></a>Açıklamalar

Bu işleve yapılan her çağrı, geçerli seçim için belirtilen biçimlendirme efektlerini geçiştir.

*dwMask* ve *dwEffect* parametreleri ve bunların olası değerleri hakkında daha fazla bilgi için Windows SDK'daki [CHARFORMAT'ın](/windows/win32/api/richedit/ns-richedit-charformata) ilgili veri üyelerine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]

## <a name="cricheditviewonfindnext"></a><a name="onfindnext"></a>CRichEditView::OnFindNext

Bul/Değiştir iletişim kutusundan komutları işlerken çerçeve tarafından çağrılır.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Parametreler

*lpszBul*<br/>
Bulunacak dize.

*bSonraki*<br/>
Arama yönü: TRUE aşağı gösterir; YANLIŞ, yukarı.

*bCase*<br/>
Aramanın büyük/küçük harf duyarlı olup olmadığını gösterir.

*bWord*<br/>
Aramanın tüm sözcüklerle eşleşip eşleşmeyecek olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

İçindeki metni bulmak için `CRichEditView`bu işlevi arayın. Türemiş görünüm sınıfınızın arama özelliklerini değiştirmek için bu işlevi geçersiz kılın.

## <a name="cricheditviewoninitialupdate"></a><a name="oninitialupdate"></a>CRichEditView::OnInitialUpdate

Görünüm belgeye ilk iliştirildikten sonra çerçeve tarafından çağrılır, ancak görünüm ilk görüntülenmeden önce.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması [CView çağırır::OnUpdate](../../mfc/reference/cview-class.md#onupdate) üye işlevi hiçbir ipucu bilgi ile (yani, *lHint* parametresi için 0 varsayılan değerleri kullanarak ve *pHint* parametresi için NULL). Belge hakkında bilgi gerektiren tek seferlik başlatmayı gerçekleştirmek için bu işlevi geçersiz kılın. Örneğin, uygulamanızda sabit boyutlu belgeler varsa, belge boyutuna bağlı olarak görünümün kaydırma sınırlarını başlatmayı sağlamak için bu işlevi kullanabilirsiniz. Uygulamanız değişken boyutlu belgeleri destekliyorsa, belge her değiştiğinde kaydırma sınırlarını güncelleştirmek için kullanın. `OnUpdate`

### <a name="example"></a>Örnek

  [CRichEditView örneğine bakın:m_nWordWrap.](#m_nwordwrap)

## <a name="cricheditviewonpastenativeobject"></a><a name="onpastenativeobject"></a>CRichEditView::OnPasteNativeObject

Katışdırılmış bir öğeden yerel verileri yüklemek için bu işlevi kullanın.

```
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```

### <a name="parameters"></a>Parametreler

*lpStg*<br/>
[IStorage](/windows/win32/api/objidl/nn-objidl-istorage) nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde, 0;

### <a name="remarks"></a>Açıklamalar

Genellikle, etrafında bir [COleStreamFile](../../mfc/reference/colestreamfile-class.md) oluşturarak bunu `IStorage`yapardı. Bir `COleStreamFile` arşive eklenebilir ve [CObject::Verileri](../../mfc/reference/cobject-class.md#serialize) yüklemek için çağrılan serialize.

Bu gelişmiş bir geçersiz.

Daha fazla bilgi için Windows SDK'daki [IStorage'a](/windows/win32/api/objidl/nn-objidl-istorage) bakın.

## <a name="cricheditviewonparaalign"></a><a name="onparaalign"></a>CRichEditView::OnParaAlign

Seçili paragraflar için paragraf hizalamasını değiştirmek için bu işlevi çağırın.

```
void OnParaAlign(WORD wAlign);
```

### <a name="parameters"></a>Parametreler

*wAlign*<br/>
İstenilen paragraf hizalaması. Aşağıdaki değerlerden biri:

- PFA_LEFT Paragrafları sol kenar boşluğuyla hizala.

- PFA_RIGHT Paragrafları doğru kenar boşluğuyla hizala.

- PFA_CENTER Kenar boşlukları arasındaki paragrafları ortalar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]

## <a name="cricheditviewonprinterchanged"></a><a name="onprinterchanged"></a>CRichEditView::OnPrinterDeğiştirildi

Yazıcı değiştiğinde bu zengin edit görünümü için özelliklerini değiştirmek için bu işlevi geçersiz kılın.

```
virtual void OnPrinterChanged(const CDC& dcPrinter);
```

### <a name="parameters"></a>Parametreler

*dcYazıcı*<br/>
Yeni yazıcı için [cdc](../../mfc/reference/cdc-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, kağıt boyutunu çıktı aygıtının (yazıcı) fiziksel yüksekliğine ve genişliğine ayarlar. *dcPrinter*ile ilişkili aygıt bağlamı yoksa, varsayılan uygulama kağıt boyutunu 8,5 x 11 inç olarak ayarlar.

## <a name="cricheditviewonreplaceall"></a><a name="onreplaceall"></a>CRichEditView::OnReplaceAll

Değiştir iletişim kutusundan Tüm komutları değiştir'i işlerken çerçeve tarafından çağrılır.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Parametreler

*lpszBul*<br/>
Değiştirilecek metin.

*lpszDeğiştir*<br/>
Değiştirilen metin.

*bCase*<br/>
Aramanın büyük/küçük harf duyarlı olup olmadığını gösterir.

*bWord*<br/>
Aramanın tüm sözcükleri seçip seçmemesi gerektiğini gösterir.

### <a name="remarks"></a>Açıklamalar

Belirli bir metnin tüm oluşumlarını başka bir dizeyle değiştirmek için bu işlevi çağırın. Bu görünüm için arama özelliklerini değiştirmek için bu işlevi geçersiz kılın.

### <a name="example"></a>Örnek

  [CRichEditView örneğine bakın:FindText](#findtext).

## <a name="cricheditviewonreplacesel"></a><a name="onreplacesel"></a>CRichEditView::OnReplaceSel

Değiştir iletişim kutusundan Değiştir komutlarını işlerken çerçeve tarafından çağrılır.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>Parametreler

*lpszBul*<br/>
Değiştirilecek metin.

*bSonraki*<br/>
Aramanın yönünü gösterir: TRUE düştü; YANLIŞ, yukarı.

*bCase*<br/>
Aramanın büyük/küçük harf duyarlı olup olmadığını gösterir.

*bWord*<br/>
Aramanın tüm sözcükleri seçip seçmemesi gerektiğini gösterir.

*lpszDeğiştir*<br/>
Değiştirilen metin.

### <a name="remarks"></a>Açıklamalar

Belirli bir metnin bir oluşumunu başka bir dizeyle değiştirmek için bu işlevi çağırın. Bu görünüm için arama özelliklerini değiştirmek için bu işlevi geçersiz kılın.

## <a name="cricheditviewontextnotfound"></a><a name="ontextnotfound"></a>CRichEditView::OnTextNotFound

Bir arama başarısız olduğunda çerçeve tarafından çağrılır.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parametreler

*lpszBul*<br/>
Bulunamayan metin.

### <a name="remarks"></a>Açıklamalar

[Bir MessageBeep'ten](/windows/win32/api/winuser/nf-winuser-messagebeep)çıktı bildirimini değiştirmek için bu işlevi geçersiz kılın.

Daha fazla bilgi için Windows SDK'daki [MessageBeep'e](/windows/win32/api/winuser/nf-winuser-messagebeep) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]

## <a name="cricheditviewonupdatechareffect"></a><a name="onupdatechareffect"></a>CRichEditView::OnUpdateCharEffect

Çerçeve, karakter efekti komutları için komut UI'yi güncelleştirmek için bu işlevi çağırır.

```
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
[CCmdUI](../../mfc/reference/ccmdui-class.md) nesnesine işaretçi.

*Dwmask*<br/>
Karakter biçimlendirme maskesini gösterir.

*dwEffect*<br/>
Karakter biçimlendirme efektini gösterir.

### <a name="remarks"></a>Açıklamalar

Maske *dwMask* hangi karakter biçimlendirme özniteliklerini denetlemek için belirtir. Bayraklar *dwEffect* ayarlamak /temizlemek için karakter biçimlendirme öznitelikleri listeleyin.

*dwMask* ve *dwEffect* parametreleri ve bunların olası değerleri hakkında daha fazla bilgi için Windows SDK'daki [CHARFORMAT'ın](/windows/win32/api/richedit/ns-richedit-charformata) ilgili veri üyelerine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]

## <a name="cricheditviewonupdateparaalign"></a><a name="onupdateparaalign"></a>CRichEditView::OnUpdateParaAlign

Çerçeve, paragraf efekti komutları için komut UI'yi güncelleştirmek için bu işlevi çağırır.

```
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,
    WORD wAlign);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
[CCmdUI](../../mfc/reference/ccmdui-class.md) nesnesine işaretçi.

*wAlign*<br/>
Denetlemek için paragraf hizalaması. Aşağıdaki değerlerden biri:

- PFA_LEFT Paragrafları sol kenar boşluğuyla hizala.

- PFA_RIGHT Paragrafları doğru kenar boşluğuyla hizala.

- PFA_CENTER Kenar boşlukları arasındaki paragrafları ortalar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]

## <a name="cricheditviewprintinsiderect"></a><a name="printinsiderect"></a>CRichEditView::PrintInsideRect

*PDC*tarafından belirtilen aygıt için *rectLayout* sığacak şekilde zengin bir düzenleme denetiminde metin aralığı biçimlendirmek için bu işlevi arayın.

```
long PrintInsideRect(
    CDC* pDC,
    RECT& rectLayout,
    long nIndexStart,
    long nIndexStop,
    BOOL bOutput);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Çıkış alanı için aygıt bağlamını işaretçi.

*rektLayout*<br/>
Çıkış alanını tanımlayan [RECT](/windows/win32/api/windef/ns-windef-rect) veya [CRect.](../../atl-mfc-shared/reference/crect-class.md)

*nIndexStart*<br/>
Biçimlendirilecek ilk karakterin sıfır tabanlı dizin.

*nIndexStop*<br/>
Biçimlendirilecek son karakterin sıfır tabanlı dizin.

*bÇıktı*<br/>
Metnin işlenmemesi gerektiğini gösterir. FALSE ise, metin sadece ölçülür.

### <a name="return-value"></a>Dönüş Değeri

Çıktı alanına uyan son karakterin dizini artı bir.

### <a name="remarks"></a>Açıklamalar

Genellikle, bu çağrıyı [cricheditCtrl::Dçıktıüreten isplayBand'e](../../mfc/reference/cricheditctrl-class.md#displayband) yapılan bir çağrı takip eder.

### <a name="example"></a>Örnek

  [CRichEditView örneğine bakın:GetPaperSize](#getpapersize).

## <a name="cricheditviewprintpage"></a><a name="printpage"></a>CRichEditView::PrintPage

*pDC*tarafından belirtilen çıkış aygıtı için zengin bir düzenleme denetiminde bir metin aralığını biçimlendirmek için bu işlevi arayın.

```
long PrintPage(
    CDC* pDC,
    long nIndexStart,
    long nIndexStop);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Sayfa çıktısı için aygıt bağlamını işaretçi.

*nIndexStart*<br/>
Biçimlendirilecek ilk karakterin sıfır tabanlı dizin.

*nIndexStop*<br/>
Biçimlendirilecek son karakterin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Sayfaya uyan son karakterin dizini artı bir.

### <a name="remarks"></a>Açıklamalar

Her sayfanın düzeni [GetPageRect](#getpagerect) ve [GetPrintRect](#getprintrect)tarafından denetlenir. Genellikle, bu çağrıyı [cricheditCtrl::Dçıktıüreten isplayBand'e](../../mfc/reference/cricheditctrl-class.md#displayband) yapılan bir çağrı takip eder.

Kenar boşluklarının mantıksal sayfaya değil, fiziksel sayfaya göre olduğunu unutmayın. Böylece, birçok yazıcının sayfada yazdırılamayan alanları olduğundan, sıfır kenar boşlukları genellikle metni keser. Metninizi kırpmaktan kaçınmak [için, SetMargins'i](#setmargins) aramalı ve yazdırmadan önce makul kenar boşlukları ayarlamalısınız.

## <a name="cricheditviewqueryacceptdata"></a><a name="queryacceptdata"></a>CRichEditView::QueryAcceptData

Bir nesneyi zengin düzenlemeye yapıştırmak için çerçeve tarafından çağrılır.

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
Kabul edilebilir veri biçimini işaretçi.

*dwReco*<br/>
Kullanılmadı.

*bGerçekten*<br/>
Yapıştırma işleminin devam edip etmediğini gösterir.

*hMetaFile*<br/>
Öğenin simgesini çizmek için kullanılan metafile için bir tutamaç.

### <a name="return-value"></a>Dönüş Değeri

Operasyonun başarısını bildiren bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Türemiş belge sınıfınızdaki com öğelerinin farklı organizasyonunu işlemek için bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz.

HRESULT ve `IDataObject`, Windows SDK'da sırasıyla [COM Hata Kodları](/windows/win32/com/structure-of-com-error-codes) ve [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject)Yapısı hakkında daha fazla bilgi için bkz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]

## <a name="cricheditviewsetcharformat"></a><a name="setcharformat"></a>CRichEditView::SetCharFormat

Bu `CRichEditView` nesnedeki yeni metin için karakter biçimlendirme özniteliklerini ayarlamak için bu işlevi çağırın.

```
void SetCharFormat(CHARFORMAT2 cf);
```

### <a name="parameters"></a>Parametreler

*Cf*<br/>
Yeni varsayılan karakter biçimlendirme özniteliklerini içeren [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) yapısı.

### <a name="remarks"></a>Açıklamalar

Bu işlev le `dwMask` yalnızca *cf* üyesi tarafından belirtilen öznitelikler değiştirilir.

Daha fazla bilgi için Windows [SDK'daki EM_SETCHARFORMAT](/windows/win32/Controls/em-setcharformat) ileti ve [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) yapısına bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

## <a name="cricheditviewsetmargins"></a><a name="setmargins"></a>CRichEditView::SetMargins

Bu zengin edit görünümü için yazdırma kenar boşluklarını ayarlamak için bu işlevi arayın.

```
void SetMargins(const CRect& rectMargin);
```

### <a name="parameters"></a>Parametreler

*rektMargin*<br/>
Yazdırma için MM_TWIPS cinsinden ölçülen yeni kenar boşluğu değerleri.

### <a name="remarks"></a>Açıklamalar

[m_nWordWrap](#m_nwordwrap) ise, `WrapToTargetDevice`yazdırma özelliklerini ayarlamak için bu işlevi kullandıktan sonra [WrapChanged'i](#wrapchanged) aramalısınız.

[PrintPage](#printpage) tarafından kullanılan kenar boşluklarının mantıksal sayfaya değil, fiziksel sayfaya göre olduğunu unutmayın. Böylece, birçok yazıcının sayfada yazdırılamayan alanları olduğundan, sıfır kenar boşlukları genellikle metni keser. Metninizi kırpmaktan kaçınmak için yazdırmadan önce makul yazıcı kenar boşlukları ayarlamak için kullanımı `SetMargins` aramalısınız.

### <a name="example"></a>Örnek

  [CRichEditView örneğine bakın:GetPaperSize](#getpapersize).

## <a name="cricheditviewsetpapersize"></a><a name="setpapersize"></a>CRichEditView::SetPaperSize

Bu zengin edit görünümünü yazdırmak için kağıt boyutunu ayarlamak için bu işlevi arayın.

```
void SetPaperSize(CSize sizePaper);
```

### <a name="parameters"></a>Parametreler

*boyutKağıt*<br/>
Yazdırma için yeni kağıt boyutu değerleri, MM_TWIPS cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

[m_nWordWrap](#m_nwordwrap) ise, `WrapToTargetDevice`yazdırma özelliklerini ayarlamak için bu işlevi kullandıktan sonra [WrapChanged'i](#wrapchanged) aramalısınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]

## <a name="cricheditviewsetparaformat"></a><a name="setparaformat"></a>CRichEditView::SetParaFormat

Bu `CRichEditView` nesnedeki geçerli seçim için paragraf biçimlendirme özniteliklerini ayarlamak için bu işlevi çağırın.

```
BOOL SetParaFormat(PARAFORMAT2& pf);
```

### <a name="parameters"></a>Parametreler

*Pf*<br/>
[ParaFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) yapısı yeni varsayılan paragraf biçimlendirme özniteliklerini içerir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde, 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev le `dwMask` yalnızca *pf* üyesi tarafından belirtilen öznitelikler değiştirilir.

Daha fazla bilgi için Windows SDK'daki [EM_SETPARAFORMAT](/windows/win32/Controls/em-setparaformat) ileti ve [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) yapısına bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]

## <a name="cricheditviewtextnotfound"></a><a name="textnotfound"></a>CRichEditView::TextNotFound

[FindText'e](#findtext)yapılan başarısız bir çağrıdan sonra [CRichEditView](../../mfc/reference/cricheditview-class.md) denetiminin dahili arama durumunu sıfırlamak için bu işlevi arayın.

```
void TextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parametreler

*lpszBul*<br/>
Bulunamayan metin dizesini içerir.

### <a name="remarks"></a>Açıklamalar

Denetimin iç arama durumunun düzgün bir şekilde sıfırlanabilmesi için bu yöntemin [FindText'e](#findtext) yapılan başarısız çağrılardan hemen sonra çağrılması önerilir.

*lpszFind* parametresi [FindText'e](#findtext)sağlanan dizeyle aynı içeriği içermelidir. İç arama durumunu sıcattıktan sonra, bu yöntem sağlanan arama dizesiyle [OnTextNotFound](#ontextnotfound) yöntemini çağırır.

### <a name="example"></a>Örnek

  [CRichEditView örneğine bakın:FindText](#findtext).

## <a name="cricheditviewwrapchanged"></a><a name="wrapchanged"></a>CRichEditView::WrapChanged

Yazdırma özellikleri değiştiğinde [(SetMargins](#setmargins) veya [SetPaperSize)](#setpapersize)bu işlevi arayın.

```
virtual void WrapChanged();
```

### <a name="remarks"></a>Açıklamalar

Zengin edit [görünümünün m_nWordWrap](#m_nwordwrap) veya yazdırma özelliklerindeki değişikliklere yanıt verme biçimini değiştirmek için bu işlevi geçersiz kılın [(OnPrinterChanged).](#onprinterchanged)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRichEditDoc Sınıfı](../../mfc/reference/cricheditdoc-class.md)<br/>
[CRichEditCntrItem Sınıfı](../../mfc/reference/cricheditcntritem-class.md)
