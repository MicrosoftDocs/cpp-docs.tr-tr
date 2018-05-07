---
title: CRichEditView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 353a45cad513e9c862b6ae6c15ab5383d3d65d48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cricheditview-class"></a>CRichEditView sınıfı
İle [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) ve [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), zengin düzenleme denetimine MFC'nin belge görünüm mimarisi bağlamında işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CRichEditView : public CCtrlView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRichEditView::CRichEditView](#cricheditview)|Oluşturan bir `CRichEditView` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|Bir iletişim kutusu taşır, böylece geçerli seçim soyutlamaması değil.|  
|[CRichEditView::CanPaste](#canpaste)|Pano zengin düzenleme görünüme yapıştırılabilmesi için verileri içerip içermediğini belirtir.|  
|[CRichEditView::DoPaste](#dopaste)|OLE öğesi bu zengin düzenleme görünüme gönderebilir.|  
|[CRichEditView::FindText](#findtext)|Bekleme imleci çağırma Belirtilen metni bulur.|  
|[CRichEditView::FindTextSimple](#findtextsimple)|Belirtilen metni bulur.|  
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|Geçerli seçim için öznitelikler biçimlendirme karakteri alır.|  
|[CRichEditView::GetDocument](#getdocument)|Bir işaretçi ilgili alır [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|  
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|Şu anda yerinde etkin bir zengin düzenleme görünümünde OLE öğesi alır.|  
|[CRichEditView::GetMargins](#getmargins)|Bu zengin düzenleme görünümü kenar boşluklarını alır.|  
|[CRichEditView::GetPageRect](#getpagerect)|Bu zengin düzenleme görünümü için sayfa dikdörtgen alır.|  
|[CRichEditView::GetPaperSize](#getpapersize)|Bu zengin düzenleme görünümü kağıt boyutunu alır.|  
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|Geçerli seçim için öznitelikler paragraf alır.|  
|[CRichEditView::GetPrintRect](#getprintrect)|Bu zengin düzenleme görünümü için yazdırma dikdörtgen alır.|  
|[CRichEditView::GetPrintWidth](#getprintwidth)|Bu zengin düzenleme görünümü yazdırma genişliğini alır.|  
|[CRichEditView::GetRichEditCtrl](#getricheditctrl)|Zengin düzenleme denetimine alır.|  
|[CRichEditView::GetSelectedItem](#getselecteditem)|Seçili öğeyi zengin düzenleme görünümden alır.|  
|[CRichEditView::GetTextLength](#gettextlength)|Zengin düzenleme görünümü metnin uzunluğunu alır.|  
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|Karakter veya zengin düzenleme görünümü bayt sayısını alır. Uzunluğu belirlemek yöntemi için genişletilmiş bayrağı listesi.|  
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|Bir dosya OLE öğesi ekler.|  
|[CRichEditView::InsertItem](#insertitem)|OLE öğesi olarak yeni bir öğe ekler.|  
|[CRichEditView::IsRichEditFormat](#isricheditformat)|Pano bir zengin düzenleme veya metin biçimi verileri içerip içermediğini belirtir.|  
|[CRichEditView::OnCharEffect](#onchareffect)|Geçerli seçim için biçimlendirme karakter değiştirir.|  
|[CRichEditView::OnParaAlign](#onparaalign)|Paragrafları hizalamasını değiştirir.|  
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|Karakter ortak üye işlevleri komutu UI güncelleştirir.|  
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|Paragraf ortak üye işlevleri komutu UI güncelleştirir.|  
|[CRichEditView::PrintInsideRect](#printinsiderect)|Belirtilen metni belirtilen dikdörtgenin içindeki biçimlendirir.|  
|[CRichEditView::PrintPage](#printpage)|Verilen sayfa içinde belirtilen metin biçimlendirir.|  
|[CRichEditView::SetCharFormat](#setcharformat)|Karakter biçimlendirme öznitelikleri geçerli seçim için ayarlar.|  
|[CRichEditView::SetMargins](#setmargins)|Ayarlar kenar boşlukları bu zengin için görünümü düzenleyin.|  
|[CRichEditView::SetPaperSize](#setpapersize)|Kağıt boyutu bu zengin düzenleme görünümü için ayarlar.|  
|[CRichEditView::SetParaFormat](#setparaformat)|Geçerli seçim için öznitelikler paragraf ayarlar.|  
|[CRichEditView::TextNotFound](#textnotfound)|Denetimin iç arama durumunu sıfırlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRichEditView::GetClipboardData](#getclipboarddata)|Bu zengin düzenleme görünümü içindeki bir aralık için Pano nesnesi alır.|  
|[CRichEditView::GetContextMenu](#getcontextmenu)|Doğru bir fare düğmesini kullanmak için bir bağlam menüsü alır.|  
|[CRichEditView::IsSelected](#isselected)|Verilen OLE öğe veya seçili olup olmadığını gösterir.|  
|[CRichEditView::OnFindNext](#onfindnext)|Bir alt dizenin sonraki örneğini bulur.|  
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|Yenileme ilk çalıştırıldığında bir görünüm belgeye eklenmiş.|  
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|Yerel veri OLE öğeyi alır.|  
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|Belirtilen aygıta yazdırma özelliklerini ayarlar.|  
|[CRichEditView::OnReplaceAll](#onreplaceall)|Belirtilen dizenin tüm oluşumlarını yeni bir dizeyle değiştirir.|  
|[CRichEditView::OnReplaceSel](#onreplacesel)|Geçerli seçim yerini alır.|  
|[CRichEditView::OnTextNotFound](#ontextnotfound)|İstenen metin bulunamadı kullanıcı bildirimi işler.|  
|[CRichEditView::QueryAcceptData](#queryacceptdata)|İlgili verileri görmek için sorguları `IDataObject`.|  
|[CRichEditView::WrapChanged](#wrapchanged)|Görünüm değerine göre bu zengin düzenleme için hedef çıktı aygıtının ayarlar `m_nWordWrap`.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|Madde işareti listeler için girinti miktarını gösterir.|  
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|Sözcük kaydırma kısıtlamaları gösterir.|  
  
## <a name="remarks"></a>Açıklamalar  
 "Zengin düzenleme denetimi" kullanıcı girin ve metin düzenleme bir penceredir. Metin karakter ve paragraf biçimlendirmesini atanabilir ve katıştırılmış OLE nesnelerine içerebilir. Zengin düzenleme denetimlerinde metin biçimlendirme için bir programlama arabirimi sağlar. Ancak, bir uygulamanın tüm biçimlendirme işlemlerini kullanıcı için kullanılabilir hale getirmek için gerekli olan kullanıcı arabirimi bileşenlerini uygulamalıdır.  
  
 `CRichEditView` metin ve biçimlendirme karakteristiğini metin, tutar. `CRichEditDoc` OLE istemci görünümünde olan bir öğe listesini tutar. `CRichEditCntrItem` OLE istemci öğesi kapsayıcı tarafı erişim sağlar.  
  
 Bu Windows yaygın bir denetim (ve bu nedenle [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) yalnızca Windows 95/98 ve Windows NT sürümler 3.51 altında çalışan programları için kullanılabilir ve üzerinde desteklenir.  
  
 Zengin düzenleme görünümü bir MFC uygulamasında kullanma örneği için bkz: [WORDPAD](../../visual-cpp-samples.md) örnek uygulama.  
  
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
 Geçerli seçim soyutlamaması olmayan şekilde verilen iletişim kutusu taşımak için bu işlevini çağırın.  
  
```  
void AdjustDialogPosition(CDialog* pDlg);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDlg*  
 İşaretçi bir `CDialog` nesnesi.  
  
##  <a name="canpaste"></a>  CRichEditView::CanPaste  
 Pano bu zengin düzenleme görünümü yapıştırdığınız bilgileri içerip içermediğini belirlemek için bu işlevini çağırın.  
  
```  
BOOL CanPaste() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pano verileri bu zengin düzenleme görünümü kabul edebileceği bir biçimde içeriyorsa, sıfır olmayan; Aksi takdirde, 0.  
  
##  <a name="cricheditview"></a>  CRichEditView::CRichEditView  
 Oluşturmak için bu işlevi çağırmak bir `CRichEditView` nesnesi.  
  
```  
CRichEditView();
```  
  
##  <a name="dopaste"></a>  CRichEditView::DoPaste  
 OLE öğesi yapıştırmak için bu işlevi çağırmak `dataobj` belge/görünüm bu zengin düzenleme.  
  
```  
void DoPaste(
    COleDataObject& dataobj,  
    CLIPFORMAT cf,  
    HMETAFILEPICT hMetaPict);
```  
  
### <a name="parameters"></a>Parametreler  
 `dataobj`  
 [COleDataObject](../../mfc/reference/coledataobject-class.md) yapıştırmak için verileri içeren.  
  
 `cf`  
 İstenen Pano biçimi.  
  
 `hMetaPict`  
 Yapıştırılmasına öğeyi temsil eden meta dosyası.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework varsayılan uygulaması bir parçası olarak bu işlev çağrıları [QueryAcceptData](#queryacceptdata).  
  
 Bu işlev işleyici sonuçlarına için Özel Yapıştır dayalı Yapıştır türünü belirler. Varsa `cf` 0'dır, geçerli simge gösterimini yeni öğesini kullanır. Varsa `cf` sıfır dışında olan ve `hMetaPict` değil **NULL**, yeni öğesini kullanan `hMetaPict` kendi gösterimi için.  
  
##  <a name="findtext"></a>  CRichEditView::FindText  
 Belirtilen metni Bul ve geçerli seçim olmasını ayarlamak için bu işlevini çağırın.  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFind`  
 Aranacak dizeyi içerir.  
  
 `bCase`  
 Arama büyük küçük harfe duyarlı olup olmadığını gösterir.  
  
 `bWord`  
 Arama yalnızca tam sözcükleri sözcükleri bölümlerini eşleşmesi gereken gösterir.  
  
 `bNext`  
 Arama yönünü belirtir. Varsa **doğru**, Arama yönü arabelleğin sonuna doğru olur. Varsa **yanlış**, arama yönünü arabellek doğru başlangıcıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `lpszFind` metin bulunursa; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bulma işlemi sırasında bekleme imleci görüntüler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]  
  
##  <a name="findtextsimple"></a>  CRichEditView::FindTextSimple  
 Belirtilen metni Bul ve geçerli seçim olmasını ayarlamak için bu işlevini çağırın.  
  
```  
BOOL FindTextSimple(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFind`  
 Aranacak dizeyi içerir.  
  
 `bCase`  
 Arama büyük küçük harfe duyarlı olup olmadığını gösterir.  
  
 `bWord`  
 Arama yalnızca tam sözcükleri sözcükleri bölümlerini eşleşmesi gereken gösterir.  
  
 `bNext`  
 Arama yönünü belirtir. Varsa **doğru**, Arama yönü arabelleğin sonuna doğru olur. Varsa **yanlış**, arama yönünü arabellek doğru başlangıcıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `lpszFind` metin bulunursa; Aksi halde 0.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRichEditView::FindText](#findtext).  
  
##  <a name="getcharformatselection"></a>  CRichEditView::GetCharFormatSelection  
 Geçerli seçim özniteliklerini biçimlendirme karakteri elde etmek için bu işlevini çağırın.  
  
```  
CHARFORMAT2& GetCharFormatSelection();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) karakter geçerli seçim özniteliklerini biçimlendirme içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) ileti ve [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) Windows SDK'sındaki yapısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="getclipboarddata"></a>  CRichEditView::GetClipboardData  
 Framework işlenmesini bir parçası olarak bu işlev çağrıları [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315).  
  
```  
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,  
    DWORD dwReco,  
    LPDATAOBJECT lpRichDataObj,  
    LPDATAOBJECT* lplpdataobj);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpchrg`  
 İşaretçi [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) karakterleri (ve OLE öğeleri) tarafından belirtilen veri nesnesine kopyalamak için aralığını belirterek yapısı `lplpdataobj`.  
  
 `dwReco`  
 Pano işlemi bayrağı. Şu değerlerden biri olabilir.  
  
- **RECO_COPY** panoya kopyala.  
  
- **RECO_CUT** panoya kesin.  
  
- **RECO_DRAG** sürükleme işlemi (Sürükle ve bırak).  
  
- **RECO_DROP** bırakma işlemi (Sürükle ve bırak).  
  
- **RECO_PASTE** Pano'dan Yapıştır.  
  
 `lpRichDataObj`  
 İşaretçi bir [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) zengin Pano veri içeren bir nesne düzenleme denetimi ( [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341)).  
  
 `lplpdataobj`  
 İşaretçi adresini alır işaretçi değişken `IDataObject` belirtilen aralık temsil eden nesne `lpchrg` parametresi. Değeri `lplpdataobj` bir hata döndürülürse, göz ardı edilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `HRESULT` işlemi başarısını raporlama değeri. Daha fazla bilgi için `HRESULT`, bkz: [COM hata kodları yapısı](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK'sındaki.  
  
### <a name="remarks"></a>Açıklamalar  
 Başarılı, dönüş değerini gösteriyorsa, **IRichEditOleCallback::GetClipboardData** döndürür `IDataObject` tarafından erişilen `lplpdataobj`; Aksi takdirde tarafından erişilen bir döndürür `lpRichDataObj`. Kendi Pano veri sağlamak için bu işlevi geçersiz kılar. Bu işlev varsayılan uygulamasını döndürür **E_NOTIMPL**.  
  
 Gelişmiş budur geçersiz kılınabilir.  
  
 Daha fazla bilgi için bkz: [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341), [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315), ve [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Windows SDK ve bakın [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Windows SDK.  
  
##  <a name="getcontextmenu"></a>  CRichEditView::GetContextMenu  
 Framework işlenmesini bir parçası olarak bu işlev çağrıları [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317).  
  
```  
virtual HMENU GetContextMenu(
    WORD seltyp,  
    LPOLEOBJECT lpoleobj,  
    CHARRANGE* lpchrg);
```  
  
### <a name="parameters"></a>Parametreler  
 *seltyp*  
 Seçim türü. Seçim türü değerleri açıklamalar bölümünde açıklanmıştır.  
  
 `lpoleobj`  
 İşaretçi bir **OLEOBJECT** yapısı bir veya daha fazla OLE öğeleri seçimi içeriyorsa, ilk seçilen OLE nesnesi belirtme. Seçimi bir öğe içeriyorsa `lpoleobj` olan **NULL**. **OLEOBJECT** yapısı bir OLE nesne v tablo için bir işaretçi tutar.  
  
 `lpchrg`  
 İşaretçi bir [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) geçerli seçim içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlam menüsüne işleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, sağ fare düğmesini basılı işleme, tipik bir parçasıdır.  
  
 Seçim türünü aşağıdaki bayraklar herhangi bir bileşimini olabilir:  
  
- `SEL_EMPTY` Geçerli seçim olduğunu gösterir.  
  
- `SEL_TEXT` Geçerli seçim metin içerdiğini gösterir.  
  
- `SEL_OBJECT` Geçerli seçim en az bir OLE öğesi içerdiğini gösterir.  
  
- `SEL_MULTICHAR` Geçerli seçim metnin birden fazla karakter içerdiğini gösterir.  
  
- `SEL_MULTIOBJECT` Geçerli seçim birden fazla OLE nesnesi içerdiğini gösterir.  
  
 Varsayılan uygulama döndürür **NULL**. Gelişmiş budur geçersiz kılınabilir.  
  
 Daha fazla bilgi için bkz: [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317) ve [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Windows SDK'sındaki.  
  
 Daha fazla bilgi için **OLEOBJECT** yazın, OLE veri yapılarını ve yapı ayırma makalesine bakın *OLE Bilgi Bankası*.  
  
##  <a name="getdocument"></a>  CRichEditView::GetDocument  
 Bir işaretçi almak için bu işlevi çağırmak `CRichEditDoc` bu görünüm ile ilişkilendirilen.  
  
```  
CRichEditDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) ilişkili nesne, `CRichEditView` nesnesi.  
  
##  <a name="getinplaceactiveitem"></a>  CRichEditView::GetInPlaceActiveItem  
 OLE almak için bu işlevi öğesi çağrı bu yerinde şu anda etkinleştirilirse `CRichEditView` nesnesi.  
  
```  
CRichEditCntrItem* GetInPlaceActiveItem() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek, yerinde etkin bir işaretçi [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) bu zengin düzenleme görünümü; nesnesinde **NULL** varsa OLE öğe şu anda yerinde etkin durumda.  
  
##  <a name="getmargins"></a>  CRichEditView::GetMargins  
 Yazdırma işleminde kullanılan geçerli kenar boşlukları almak için bu işlevini çağırın.  
  
```  
CRect GetMargins() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazdırma işleminde kullanılan kenar boşluklarını ölçülen `MM_TWIPS`.  
  
##  <a name="getpagerect"></a>  CRichEditView::GetPageRect  
 Yazdırma işleminde kullanılan sayfa boyutları almak için bu işlevini çağırın.  
  
```  
CRect GetPageRect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazdırma işleminde kullanılan sayfa sınırları ölçülen `MM_TWIPS`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer kağıt boyutuna bağlıdır.  
  
##  <a name="getpapersize"></a>  CRichEditView::GetPaperSize  
 Geçerli kağıt boyutu almak için bu işlevini çağırın.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazdırma işleminde kullanılan kağıt boyutunu ölçülen `MM_TWIPS`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]  
  
##  <a name="getparaformatselection"></a>  CRichEditView::GetParaFormatSelection  
 Geçerli seçim özniteliklerini paragraf almak için bu işlevini çağırın.  
  
```  
PARAFORMAT2& GetParaFormatSelection();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) paragraf geçerli seçim özniteliklerini biçimlendirme içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182) ileti ve [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) Windows SDK'sındaki yapısı.  
  
##  <a name="getprintrect"></a>  CRichEditView::GetPrintRect  
 Sayfa dikdörtgenin içindeki yazdırma alanını sınırlarına almak için bu işlevini çağırın.  
  
```  
CRect GetPrintRect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazdırma işleminde kullanılan görüntü alanını sınırlarına ölçülen `MM_TWIPS`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]  
  
##  <a name="getprintwidth"></a>  CRichEditView::GetPrintWidth  
 Yazdırma alanını genişliğini belirlemek için bu işlevini çağırın.  
  
```  
int GetPrintWidth() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazdırma alanını genişliğini ölçülen `MM_TWIPS`.  
  
##  <a name="getricheditctrl"></a>  CRichEditView::GetRichEditCtrl  
 Almak için bu işlevi çağırmak [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ilişkili nesne `CRichEditView` nesne.  
  
```  
CRichEditCtrl& GetRichEditCtrl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `CRichEditCtrl` Bu görünüm için nesne.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRichEditView::FindText](#findtext).  
  
##  <a name="getselecteditem"></a>  CRichEditView::GetSelectedItem  
 OLE öğesi almak için bu işlevi çağırmak (bir `CRichEditCntrItem` nesnesi) şu anda bu seçili `CRichEditView` nesnesi.  
  
```  
CRichEditCntrItem* GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) seçili nesne `CRichEditView` nesne; **NULL** hiçbir madde bu görünümde seçili değilse.  
  
##  <a name="gettextlength"></a>  CRichEditView::GetTextLength  
 Bu metnin uzunluğunu almak için bu işlevi çağırmak `CRichEditView` nesnesi.  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu metnin uzunluğunu `CRichEditView` nesnesi.  
  
##  <a name="gettextlengthex"></a>  CRichEditView::GetTextLengthEx  
 Bu metnin uzunluğunu hesaplamak için bu üye işlevini çağırın `CRichEditView` nesnesi.  
  
```  
long GetTextLengthEx(
    DWORD dwFlags,  
    UINT uCodePage = -1) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `dwFlags`  
 Metin uzunluğu belirlerken kullanılacak yöntemini belirten değer. Bu üye biri veya daha fazla değeri listelenen bayrakları üyesi, [GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915) Windows SDK'ın açıklanmaktadır.  
  
 `uCodePage`  
 Kod sayfası çeviri (CP_ACP ANSI kod sayfası, 1200 Unicode için).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karakter veya düzenleme denetimindeki bayt sayısı. Uyumsuz bayrakları ayarlandıysa `dwFlags`, bu üye işlevinin döndürdüğü `E_INVALIDARG`.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetTextLengthEx` metnin uzunluğu belirlemek ek yollar sağlar. Zengin düzenleme 2.0 işlevselliği destekler. Daha fazla bilgi için bkz: [hakkında zengin düzenleme denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb787873) Windows SDK.  
  
##  <a name="insertfileasobject"></a>  CRichEditView::InsertFileAsObject  
 Belirtilen dosya eklemek için bu işlevi çağırmak (olarak bir [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) nesnesi) zengin bir görünümü düzenleyin.  
  
```  
void InsertFileAsObject(LPCTSTR lpszFileName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFileName`  
 Eklenecek dosyanın adını içeren dize.  
  
##  <a name="insertitem"></a>  CRichEditView::InsertItem  
 Eklemek için bu işlevi çağırmak bir [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) bir zengin düzenleme görünümü nesnesine.  
  
```  
HRESULT InsertItem(CRichEditCntrItem* pItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 İşaretçi eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `HRESULT` ekleme başarısını belirten değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için `HRESULT`, bkz: [COM hata kodları yapısı](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK'sındaki.  
  
##  <a name="isricheditformat"></a>  CRichEditView::IsRichEditFormat  
 Belirlemek için bu işlevi çağırmak `cf` metin, zengin metin veya OLE öğeleri içeren zengin metin olan bir Pano biçimidir.  
  
```  
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```  
  
### <a name="parameters"></a>Parametreler  
 `cf`  
 Pano biçimi ilgi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `cf` bir zengin düzenleme veya metin Pano biçimi.  
  
##  <a name="isselected"></a>  CRichEditView::IsSelected  
 Belirtilen OLE öğesi bu görünümde seçili olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDocItem`  
 Görünümde bir nesne işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne seçiliyse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilmiş görünüm sınıfınız OLE öğelerin seçimini işlemek için farklı bir yöntemi varsa, bu işlev geçersiz kılar.  
  
##  <a name="m_nbulletindent"></a>  CRichEditView::m_nBulletIndent  
 Bir listedeki madde işareti öğeleri girinti; 1/2 inç olan varsayılan olarak, 720 birimleri.  
  
```  
int m_nBulletIndent;  
```  
  
##  <a name="m_nwordwrap"></a>  CRichEditView::m_nWordWrap  
 Sözcük kaydırma bu zengin düzenleme görünümü türünü belirtir.  
  
```  
int m_nWordWrap;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki değerlerden biri:  
  
- `WrapNone` Otomatik sözcük kaydırma yok gösterir.  
  
- `WrapToWindow` Sözcük kaydırma pencere genişliğine göre gösterir.  
  
- `WrapToTargetDevice` Sözcük kaydırma hedef cihaz özelliklerine göre gösterir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRichEditView::WrapChanged](#wrapchanged).  
  
##  <a name="onchareffect"></a>  CRichEditView::OnCharEffect  
 Karakter biçimlendirme efektlerini geçerli seçim için geçiş yapmak için bu işlevini çağırın.  
  
```  
void OnCharEffect(
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwMask`  
 Geçerli seçim değiştirmek için etkileri biçimlendirme karakter.  
  
 `dwEffect`  
 Karakter biçimlendirme efektlerini geçiş yapmak için istenen listesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev için her çağrı geçerli seçim için belirtilen biçimlendirme efektleri değiştirir.  
  
 Daha fazla bilgi için `dwMask` ve `dwEffect` parametreler ve olası değerleri görmek karşılık gelen veri üyeleri [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]  
  
##  <a name="onfindnext"></a>  CRichEditView::OnFindNext  
 Bul ve Değiştir iletişim kutusundan komutlarının işlenmesi çerçevesi tarafından çağrılır.  
  
```  
virtual void OnFindNext(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFind`  
 Bulunacak dize.  
  
 `bNext`  
 Arama yönünü: **TRUE** aşağı; gösterir **Yanlış**, en fazla.  
  
 `bCase`  
 Arama büyük küçük harfe duyarlı olup olmadığını gösterir.  
  
 `bWord`  
 Arama yalnızca veya değil tam sözcükleri eşleştirmeye olup olmadığını gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 İçindeki metni bulmak için bu işlevi çağırmak `CRichEditView`. Bu işlev, türetilmiş görünüm sınıfı için arama özelliklerini değiştirmek için geçersiz kılar.  
  
##  <a name="oninitialupdate"></a>  CRichEditView::OnInitialUpdate  
 Görünüm ilk belgeye eklendikten sonra ancak görünümü başlangıçta görüntülenmeden önce çerçevesi tarafından çağrılır.  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulamasını çağıran [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) hiçbir ipucu bilgilerle üye işlevi (diğer bir deyişle, 0 için varsayılan değerleri kullanılarak `lHint` parametre ve **NULL** için `pHint` parametresi). Belge hakkındaki bilgileri gerektiren herhangi bir kerelik başlatma gerçekleştirmek için bu işlevi geçersiz kılar. Örneğin, sabit boyutlu belgeleri uygulamanız varsa, belge boyutuna göre bir görünümün kayan sınırları başlatmak için bu işlevi kullanabilirsiniz. Uygulamanızın değişken boyutlu belgeleri destekliyorsa kullanın `OnUpdate` kaydırma güncelleştirmek için belge değişiklikleri her zaman sınırlar.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRichEditView::m_nWordWrap](#m_nwordwrap).  
  
##  <a name="onpastenativeobject"></a>  CRichEditView::OnPasteNativeObject  
 Katıştırılmış bir öğeden yerel veri yüklemek için bu işlevi kullanın.  
  
```  
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpStg*  
 İşaretçi bir [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde, 0;  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, oluşturarak bunu bir [COleStreamFile](../../mfc/reference/colestreamfile-class.md) geçici `IStorage`. `COleStreamFile` Arşive eklenebilecek ve [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) verileri yüklemek için çağrılır.  
  
 Gelişmiş budur geçersiz kılınabilir.  
  
 Daha fazla bilgi için bkz: [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) Windows SDK'sındaki.  
  
##  <a name="onparaalign"></a>  CRichEditView::OnParaAlign  
 Seçili paragraf Paragraf hizalamasını değiştirmek için bu işlevini çağırın.  
  
```  
void OnParaAlign(WORD wAlign);
```  
  
### <a name="parameters"></a>Parametreler  
 `wAlign`  
 İstenen paragraf hizalaması. Aşağıdaki değerlerden biri:  
  
- `PFA_LEFT` Sol kenar boşluğu ile paragrafları hizalayın.  
  
- `PFA_RIGHT` Sağ kenar boşluğu ile paragrafları hizalayın.  
  
- `PFA_CENTER` Kenar boşlukları arasındaki paragrafları ortalayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]  
  
##  <a name="onprinterchanged"></a>  CRichEditView::OnPrinterChanged  
 Yazıcı değiştirdiğinde bu zengin düzenleme görünümü özelliklerini değiştirmek için bu işlevi geçersiz kılar.  
  
```  
virtual void OnPrinterChanged(const CDC& dcPrinter);
```  
  
### <a name="parameters"></a>Parametreler  
 `dcPrinter`  
 A [CDC](../../mfc/reference/cdc-class.md) yeni yazıcı nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama kağıt boyutu fiziksel yüksekliğini ve genişliğini çıktı aygıtının (yazıcı) ayarlar. Hiçbir cihaz bağlamı varsa ilişkili `dcPrinter`, varsayılan uygulama 8.5 x 11 inç kağıt boyutunu belirler.  
  
##  <a name="onreplaceall"></a>  CRichEditView::OnReplaceAll  
 Değiştir iletişim kutusundan yerine tüm komutları işlenirken çerçevesi tarafından çağrılır.  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFind`  
 Değiştirilecek metin.  
  
 `lpszReplace`  
 Değiştirilen metin.  
  
 `bCase`  
 Arama büyük küçük harfe duyarlı olup olmadığını gösterir.  
  
 `bWord`  
 Arama tam sözcükleri veya seçerseniz gerekir gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Başka bir dizeyle bazı verilen metni tüm oluşumlarını değiştirmek için bu işlevini çağırın. Bu görünüm için arama özelliklerini değiştirmek için bu işlevi geçersiz kılar.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRichEditView::FindText](#findtext).  
  
##  <a name="onreplacesel"></a>  CRichEditView::OnReplaceSel  
 Değiştir iletişim kutusundan Değiştir komutlarının işlenmesi çerçevesi tarafından çağrılır.  
  
```  
virtual void OnReplaceSel(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    BOOL bWord,  
    LPCTSTR lpszReplace);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFind`  
 Değiştirilecek metin.  
  
 `bNext`  
 Arama yönünü belirtir: **TRUE** kapalı; **Yanlış**, en fazla.  
  
 `bCase`  
 Arama büyük küçük harfe duyarlı olup olmadığını gösterir.  
  
 `bWord`  
 Arama tam sözcükleri veya seçerseniz gerekir gösterir.  
  
 `lpszReplace`  
 Değiştirilen metin.  
  
### <a name="remarks"></a>Açıklamalar  
 Başka bir dizeyle bazı verilen metni bir örneğini değiştirmek için bu işlevini çağırın. Bu görünüm için arama özelliklerini değiştirmek için bu işlevi geçersiz kılar.  
  
##  <a name="ontextnotfound"></a>  CRichEditView::OnTextNotFound  
 Arama başarısız olduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFind`  
 Bulunamadı metin.  
  
### <a name="remarks"></a>Açıklamalar  
 Çıktı bildirimden değiştirmek için bu işlevi geçersiz bir [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356).  
  
 Daha fazla bilgi için bkz: [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]  
  
##  <a name="onupdatechareffect"></a>  CRichEditView::OnUpdateCharEffect  
 Framework'te karakter etkisi komutlar için kullanıcı Arabirimi komutu güncelleştirmek için bu işlevi çağırır.  
  
```  
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,  
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCmdUI`  
 İşaretçi bir [Ccmduı](../../mfc/reference/ccmdui-class.md) nesnesi.  
  
 `dwMask`  
 Karakter maskesi biçimlendirme gösterir.  
  
 `dwEffect`  
 Karakter etkisi biçimlendirme gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Maske `dwMask` hangi denetlemek için biçimlendirme öznitelikleri karakter belirtir. Bayrakları `dwEffect` karakter kümesi/temizlenmesi için öznitelikler biçimlendirme listesi.  
  
 Daha fazla bilgi için `dwMask` ve `dwEffect` parametreler ve olası değerleri görmek karşılık gelen veri üyeleri [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]  
  
##  <a name="onupdateparaalign"></a>  CRichEditView::OnUpdateParaAlign  
 Framework ' % s'komut UI paragraf etkisi komutları için güncelleştirmek için bu işlevi çağırır.  
  
```  
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,  
    WORD wAlign);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCmdUI`  
 İşaretçi bir [Ccmduı](../../mfc/reference/ccmdui-class.md) nesnesi.  
  
 `wAlign`  
 Denetlenecek paragraf hizalaması. Aşağıdaki değerlerden biri:  
  
- `PFA_LEFT` Sol kenar boşluğu ile paragrafları hizalayın.  
  
- `PFA_RIGHT` Sağ kenar boşluğu ile paragrafları hizalayın.  
  
- `PFA_CENTER` Kenar boşlukları arasındaki paragrafları ortalayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]  
  
##  <a name="printinsiderect"></a>  CRichEditView::PrintInsideRect  
 Metnin sığması için bir zengin düzenleme denetimindeki bir dizi biçimlendirmek için bu işlevi çağırmak *rectLayout* tarafından belirtilen cihaz için `pDC`.  
  
```  
long PrintInsideRect(
    CDC* pDC,  
    RECT& rectLayout,  
    long nIndexStart,  
    long nIndexStop,  
    BOOL bOutput);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Çıkış alanı için bir cihaz bağlamı işaretçi.  
  
 *rectLayout*  
 [RECT](../../mfc/reference/rect-structure1.md) veya [CRect](../../atl-mfc-shared/reference/crect-class.md) çıktı alanını tanımlar.  
  
 `nIndexStart`  
 Biçimlendirilecek ilk karakter sıfır tabanlı dizini.  
  
 `nIndexStop`  
 Biçimlendirilecek son karakter sıfır tabanlı dizini.  
  
 *bOutput*  
 Metin işlenip işlenmeyeceğini belirtir. Varsa **yanlış**, metin yalnızca ölçülür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çıkış alanı artı bir uygun son karakter dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, bu çağrı bir çağrı arkasından [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) çıktısı oluşturur.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRichEditView::GetPaperSize](#getpapersize).  
  
##  <a name="printpage"></a>  CRichEditView::PrintPage  
 Bir aralık tarafından belirtilen çıkış aygıtı için bir zengin düzenleme denetimindeki metnin biçimlendirmek için bu işlevi çağırmak `pDC`.  
  
```  
long PrintPage(
    CDC* pDC,  
    long nIndexStart,  
    long nIndexStop);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Sayfa çıktısı için bir cihaz bağlamı işaretçi.  
  
 `nIndexStart`  
 Biçimlendirilecek ilk karakter sıfır tabanlı dizini.  
  
 `nIndexStop`  
 Biçimlendirilecek son karakter sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sayfa artı bir taneyi üzerinde uygun son karakter dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Her sayfanın düzenini tarafından denetlenen [GetPageRect](#getpagerect) ve [GetPrintRect](#getprintrect). Genellikle, bu çağrı bir çağrı arkasından [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) çıktısı oluşturur.  
  
 Kenar boşluklarını fiziksel sayfa göre mantıksal sayfa olduğunu unutmayın. Bu nedenle, birçok yazıcı sayfasında yazdırılamayan alanlara sahip olduğundan kenar boşlukları sıfır genellikle metni küçük. Metninizi kırpma önlemek için çağırmalıdır [SetMargins](#setmargins) ve yazdırma önce makul kenar boşluklarını ayarlayın.  
  
##  <a name="queryacceptdata"></a>  CRichEditView::QueryAcceptData  
 Zengin düzenleme bir nesne yapıştırmak için framework tarafından çağrılır.  
  
```  
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,  
    CLIPFORMAT* lpcfFormat,  
    DWORD dwReco,  
    BOOL bReally,  
    HGLOBAL hMetaFile);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpdataobj*  
 İşaretçi [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) sorgulanamıyor.  
  
 *lpcfFormat*  
 Kabul edilebilir veri biçimi işaretçidir.  
  
 `dwReco`  
 Kullanılmadı.  
  
 *bReally*  
 Yapıştırma işlemi veya devam edip etmediğini gösterir.  
  
 `hMetaFile`  
 Öğenin simgesini çizmek için kullanılan meta dosyası için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `HRESULT` işlemi başarısını raporlama değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Farklı bir kuruluşta, türetilen belge sınıfı COM öğelerinin işlemek için bu işlev geçersiz kılar. Gelişmiş budur geçersiz kılınabilir.  
  
 Daha fazla bilgi için `HRESULT` ve `IDataObject`, bkz: [yapısı COM hata kodları](http://msdn.microsoft.com/library/windows/desktop/ms690088) ve [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421), sırasıyla Windows SDK.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]  
  
##  <a name="setcharformat"></a>  CRichEditView::SetCharFormat  
 Bu yeni metin özniteliklerini biçimlendirme karakter kümesi için bu işlevi çağırmak `CRichEditView` nesnesi.  
  
```  
void SetCharFormat(CHARFORMAT2 cf);
```  
  
### <a name="parameters"></a>Parametreler  
 `cf`  
 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) biçimlendirme özniteliklerini yeni varsayılan karakter içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca tarafından belirtilen öznitelikler **dwMask** üyesi `cf` bu işlev tarafından değiştirildi.  
  
 Daha fazla bilgi için bkz: [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) ileti ve [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) Windows SDK'sındaki yapısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="setmargins"></a>  CRichEditView::SetMargins  
 Bu zengin düzenleme görünümü yazdırma kenar boşluklarını belirlemek için bu işlevini çağırın.  
  
```  
void SetMargins(const CRect& rectMargin);
```  
  
### <a name="parameters"></a>Parametreler  
 *rectMargin*  
 Yazdırma, yeni kenar boşluğu değerlerini ölçülen `MM_TWIPS`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa [m_nWordWrap](#m_nwordwrap) olan `WrapToTargetDevice`, çağırmalısınız [WrapChanged](#wrapchanged) yazdırma özelliklerini ayarlamak için bu işlevi kullandıktan sonra.  
  
 Kenar boşlukları kullandığı Not [PrintPage](#printpage) olan fiziksel sayfa göre mantıksal sayfada değil. Bu nedenle, birçok yazıcı sayfasında yazdırılamayan alanlara sahip olduğundan kenar boşlukları sıfır genellikle metni küçük. Metninizi kırpma önlemek için kullanım çağırmalıdır `SetMargins` makul yazıcı kenar boşluklarını yazdırma önce belirlemek için.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRichEditView::GetPaperSize](#getpapersize).  
  
##  <a name="setpapersize"></a>  CRichEditView::SetPaperSize  
 Bu zengin düzenleme görünümü yazdırma kağıt boyutunu ayarlamak için bu işlevini çağırın.  
  
```  
void SetPaperSize(CSize sizePaper);
```  
  
### <a name="parameters"></a>Parametreler  
 *sizePaper*  
 Yazdırma için yeni kağıt boyutu değerleri ölçülen `MM_TWIPS`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa [m_nWordWrap](#m_nwordwrap) olan `WrapToTargetDevice`, çağırmalısınız [WrapChanged](#wrapchanged) yazdırma özelliklerini ayarlamak için bu işlevi kullandıktan sonra.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]  
  
##  <a name="setparaformat"></a>  CRichEditView::SetParaFormat  
 Bu geçerli seçim için öznitelikler paragraf ayarlamak için bu işlevi çağırmak `CRichEditView` nesnesi.  
  
```  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>Parametreler  
 `pf`  
 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) yeni varsayılan içeren yapısını paragraf biçimlendirme öznitelikleri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde, 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca tarafından belirtilen öznitelikler **dwMask** üyesi `pf` bu işlev tarafından değiştirildi.  
  
 Daha fazla bilgi için bkz: [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276) ileti ve [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) Windows SDK'sındaki yapısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]  
  
##  <a name="textnotfound"></a>  CRichEditView::TextNotFound  
 İç arama durumunu sıfırlamak için bu işlevi çağırmak [CRichEditView](../../mfc/reference/cricheditview-class.md) denetim başarısız çağrı sonra [FindText](#findtext).  
  
```  
void TextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFind`  
 Bulunamadı metin dizesi içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem başarısız çağrılar hemen sonra çağrılması önerilir [FindText](#findtext) böylece denetimi iç arama durumunu doğru şekilde sıfırlayın.  
  
 `lpszFind` Parametresi için sağlanan dize olarak aynı içerik içermelidir [FindText](#findtext). Bu yöntem iç arama durumu sıfırlanıyor sonra çağıracaktır [OnTextNotFound](#ontextnotfound) sağlanan arama dizesiyle yöntemi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRichEditView::FindText](#findtext).  
  
##  <a name="wrapchanged"></a>  CRichEditView::WrapChanged  
 Yazdırma özelliklerini değiştirdikten sonra bu işlev çağrısı ( [SetMargins](#setmargins) veya [SetPaperSize](#setpapersize)).  
  
```  
virtual void WrapChanged();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Zengin düzenleme görünümü şekilde değiştirmek için bu işlevi yanıt değişikliklere geçersiz kılma [m_nWordWrap](#m_nwordwrap) veya yazdırma özelliklerini ( [OnPrinterChanged](#onprinterchanged)).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek WORDPAD](../../visual-cpp-samples.md)   
 [CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc sınıfı](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditCntrItem Sınıfı](../../mfc/reference/cricheditcntritem-class.md)
