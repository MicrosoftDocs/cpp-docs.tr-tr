---
title: CMFCPropertySheet Sınıfı
ms.date: 11/19/2018
f1_keywords:
- CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPage
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPageToTree
- AFXPROPERTYSHEET/CMFCPropertySheet::AddTreeCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::EnablePageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::GetHeaderHeight
- AFXPROPERTYSHEET/CMFCPropertySheet::GetLook
- AFXPROPERTYSHEET/CMFCPropertySheet::GetNavBarWidth
- AFXPROPERTYSHEET/CMFCPropertySheet::GetTab
- AFXPROPERTYSHEET/CMFCPropertySheet::InitNavigationControl
- AFXPROPERTYSHEET/CMFCPropertySheet::OnActivatePage
- AFXPROPERTYSHEET/CMFCPropertySheet::OnDrawPageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::OnRemoveTreePage
- AFXPROPERTYSHEET/CMFCPropertySheet::RemoveCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::RemovePage
- AFXPROPERTYSHEET/CMFCPropertySheet::SetIconsList
- AFXPROPERTYSHEET/CMFCPropertySheet::SetLook
helpviewer_keywords:
- CMFCPropertySheet [MFC], CMFCPropertySheet
- CMFCPropertySheet [MFC], AddPage
- CMFCPropertySheet [MFC], AddPageToTree
- CMFCPropertySheet [MFC], AddTreeCategory
- CMFCPropertySheet [MFC], EnablePageHeader
- CMFCPropertySheet [MFC], GetHeaderHeight
- CMFCPropertySheet [MFC], GetLook
- CMFCPropertySheet [MFC], GetNavBarWidth
- CMFCPropertySheet [MFC], GetTab
- CMFCPropertySheet [MFC], InitNavigationControl
- CMFCPropertySheet [MFC], OnActivatePage
- CMFCPropertySheet [MFC], OnDrawPageHeader
- CMFCPropertySheet [MFC], OnRemoveTreePage
- CMFCPropertySheet [MFC], RemoveCategory
- CMFCPropertySheet [MFC], RemovePage
- CMFCPropertySheet [MFC], SetIconsList
- CMFCPropertySheet [MFC], SetLook
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
ms.openlocfilehash: 9b1bb2ce9a957b9cd9f7add983b4da7a228d7a1d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750065"
---
# <a name="cmfcpropertysheet-class"></a>CMFCPropertySheet Sınıfı

Sınıf, `CMFCPropertySheet` her özellik sayfasının bir sayfa sekmesi, araç çubuğu düğmesi, ağaç denetim düğümü veya liste öğesi tarafından belirtildiği bir özellik sayfasını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPropertySheet : public CPropertySheet
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCÖzellik Sayfası::CMFCÖzellik Sayfası](#cmfcpropertysheet)|Bir `CMFCPropertySheet` nesne inşa eder.|
|`CMFCPropertySheet::~CMFCPropertySheet`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCÖzellik Sayfası::AddPage](#addpage)|Özellik sayfasına bir sayfa ekler.|
|[CMFCÖzellik::AddPagetoTree](#addpagetotree)|Ağaç denetimine yeni bir özellik sayfası ekler.|
|[CMFCÖzellik Sayfası::AddTreeKategori](#addtreecategory)|Ağaç denetimine yeni bir düğüm ekler.|
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|Özel bir üstbilgi çizmek için her sayfanın üst kısmında yer ayırır.|
|[CMFCÖzellik::GetHeaderHeight](#getheaderheight)|Geçerli üstbilginin yüksekliğini alır.|
|[CMFCÖzellik Sayfası::GetLook](#getlook)|Geçerli özellik sayfasının görünümünü belirten bir numaralandırma değeri alır.|
|[CMFCÖzellik::GetNavBarWidth](#getnavbarwidth)|Gezinme çubuğunun genişliğini piksellerde yeniden dener.|
|[CMFCÖzellik Sayfası::GetTab](#gettab)|Geçerli özellik sayfası denetimini destekleyen iç sekme denetim nesnesini alır.|
|`CMFCPropertySheet::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|Geçerli özellik sayfası denetiminin görünümünü başolarak karşılar.|
|[CMFCÖzellik Sayfası::OnActivatePage](#onactivatepage)|Özellik sayfası etkinleştirildiğinde çerçeve tarafından çağrılır.|
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|Özel bir özellik sayfası üstbilgisini çizmek için çerçeve tarafından çağrılır.|
|`CMFCPropertySheet::OnInitDialog`|[WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) iletiyi işler. (CPropertySheet geçersiz [kılar::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCÖzellik Sayfası::OnremoveTreePage](#onremovetreepage)|Bir özellik sayfasını ağaç denetiminden kaldırmak için çerçeve tarafından çağrılır.|
|`CMFCPropertySheet::PreTranslateMessage`|Pencere iletilerini [Çeviri İletisi](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine gönderilmeden önce çevirir. (Geçersiz `CPropertySheet::PreTranslateMessage`kılar .)|
|[CMFCÖzellik Sayfası::RemoveCategory](#removecategory)|Ağaç denetiminden bir düğüm kaldırır.|
|[CMFCÖzellik Sayfası::RemovePage](#removepage)|Özellik sayfasını özellik sayfasından kaldırır.|
|[CMFCÖzellik::SetIconsList](#seticonslist)|Outlook bölmesinin gezinti denetiminde kullanılan görüntülerin listesini belirtir.|
|[CMFCÖzellik::SetLook](#setlook)|Özellik sayfasının görünümünü belirtir.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CMFCPropertySheet` sekme iletişim kutuları olarak da bilinen özellik sayfalarını temsil eder. Sınıf, `CMFCPropertySheet` bir özellik sayfasını çeşitli şekillerde görüntüleyebilir.

Uygulamanızda `CMFCPropertySheet` sınıfı kullanmak için aşağıdaki adımları gerçekleştirin:

1. Sınıftan `CMFCPropertySheet` bir sınıf türetin ve örneğin CMyPropertySheet sınıfı adlandırın.

1. Her özellik sayfası için bir [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) nesnesi oluştur.

1. CMyPropertySheet oluşturucuda [CMFCPropertySheet::SetLook](#setlook) yöntemini arayın. Bu yöntemin bir parametresi, özellik sayfalarının özellik sayfasının üst veya solundaki sekmeler olarak görüntüleneceğini belirtir; microsoft OneNote özellik sayfası stilinde sekmeler; Microsoft Outlook araç çubuğu denetimindeki düğmeler; ağaç kontrolündedüğümler; veya özellik sayfasının sol tarafındaki öğelerin listesi olarak.

1. Microsoft Outlook araç çubuğu stilinde bir özellik sayfası oluşturursanız, bir resim listesini özellik sayfalarıyla ilişkilendirmek için [CMFCPropertySheet:SetIconsList](#seticonslist) yöntemini arayın.

1. [CMFCPropertySheet'i arayın::Her](#addpage) özellik sayfası için Sayfa Ekleme yöntemi.

1. Bir `CMFCPropertySheet` denetim oluşturun `DoModal` ve yöntemini çağırın.

## <a name="illustrations"></a>Çizimler

Aşağıdaki resimde, katıştırılmış microsoft outlook araç çubuğu stilinde bir özellik sayfası gösterilmiştir. Outlook araç çubuğu özellik sayfasının sol tarafında görünür.

![CMFCPropertySheet renk kontrolleri](../../mfc/reference/media/cmfcpropertysheet_color.png "CMFCPropertySheet renk kontrolleri")

Aşağıdaki resimde [CMFCPropertyGridCtrl Sınıf](../../mfc/reference/cmfcpropertygridctrl-class.md) nesnesi içeren bir özellik sayfası gösterilmiştir. Bu nesne, standart bir ortak denetim özelliği sayfası stilinde bir özellik sayfasıdır.

![CMFCPropertySheet listesi ve özellik kontrolleri](../../mfc/reference/media/cmfcpropertysheet_list.png "CMFCPropertySheet listesi ve özellik kontrolleri")

Aşağıdaki resimde, ağaç denetimi stilinde bir özellik sayfası gösterilmiştir.

![Emlak Ağacı](../../mfc/reference/media/proptree.png "Emlak Ağacı")

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cpropertysheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCÖzellik Sayfası](../../mfc/reference/cmfcpropertysheet-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpropertysheet.h

## <a name="cmfcpropertysheetaddpage"></a><a name="addpage"></a>CMFCÖzellik Sayfası::AddPage

Özellik sayfasına bir sayfa ekler.

```cpp
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
[içinde] Bir sayfa nesnesine işaretçi. Bu parametre NULL olamaz.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen özellik sayfasını özellik sayfasındaen doğru sekme olarak ekler. Bu nedenle, sayfaları soldan sağa sırayla eklemek için bu yöntemi kullanın.

Özellik sayfası Microsoft Outlook tarzındaysa, çerçeve özellik sayfasının solunda gezinti düğmelerinin listesini görüntüler. Bu yöntem bir özellik sayfası ekledikten sonra, listeye karşılık gelen bir düğme ekler. Bir özellik sayfasını görüntülemek için ilgili düğmesini tıklatın. Özellik sayfaları stilleri hakkında daha fazla bilgi için [CMFCPropertySheet::SetLook](#setlook)sayfasına bakın.

## <a name="cmfcpropertysheetaddpagetotree"></a><a name="addpagetotree"></a>CMFCÖzellik::AddPagetoTree

Ağaç denetimine yeni bir özellik sayfası ekler.

```cpp
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,
    CMFCPropertyPage* pPage,
    int nIconNum=-1,
    int nSelIconNum=-1);
```

### <a name="parameters"></a>Parametreler

*pKategori*<br/>
[içinde] Belirtilen sayfayı üst düzey düğümle ilişkilendirmek için bir üst ağaç düğümüne veya NULL'a işaretçi. Bu işaretçiyi elde etmek için [CMFCPropertySheet::AddTreeCategory](#addtreecategory) yöntemini arayın.

*pPage*<br/>
[içinde] Özellik sayfası nesnesine işaretçi.

*nIconNum*<br/>
[içinde] Simgenin sıfır tabanlı dizini veya simge kullanılmazsa -1. Simge, sayfa seçilmediğinde ağaç denetimi özelliği sayfasının yanında görüntülenir. Varsayılan değer -1'dir.

*nSelIconNum*<br/>
[içinde] Simgenin sıfır tabanlı dizini veya simge kullanılmazsa -1. Simge, sayfa seçildiğinde ağaç denetimi özelliği sayfasının yanında görüntülenir. Varsayılan değer -1'dir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir ağaç denetiminin yaprağı olarak bir özellik sayfası ekler. Bir özellik sayfası eklemek `CMFCPropertySheet` için, bir nesne oluşturun, [CMFCPropertySheet'i arayın::Görünüm](#setlook) parametresi ayarlı *look* `CMFCPropertySheet::PropSheetLook_Tree`SetLook yöntemini ayarlayın ve ardından özellik sayfasını eklemek için bu yöntemi kullanın.

## <a name="cmfcpropertysheetaddtreecategory"></a><a name="addtreecategory"></a>CMFCÖzellik Sayfası::AddTreeKategori

Ağaç denetimine yeni bir düğüm ekler.

```
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,
    int nIconNum=-1,
    int nSelectedIconNum=-1,
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] Düğümün adı.

*nIconNum*<br/>
[içinde] Simgenin sıfır tabanlı dizini veya simge kullanılmazsa -1. Simge, sayfa seçilmediğinde ağaç denetimi özelliği sayfasının yanında görüntülenir. Varsayılan değer -1'dir.

*nSelectedIconNum*<br/>
[içinde] Simgenin sıfır tabanlı dizini veya simge kullanılmazsa -1. Simge, sayfa seçildiğinde ağaç denetimi özelliği sayfasının yanında görüntülenir. Varsayılan değer -1'dir.

*pParentKategori*<br/>
[içinde] Belirtilen sayfayı üst düzey düğümle ilişkilendirmek için bir üst ağaç düğümüne veya NULL'a işaretçi. Bu parametreyi [CMFCPropertySheet ile ayarlayın::AddTreeCategory](#addtreecategory) yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Ağaç denetiminde yeni düğüm için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Ağaç denetimine kategori olarak da adlandırılan yeni bir düğüm eklemek için bu yöntemi kullanın. `CMFCPropertySheet` Düğüm eklemek için bir nesne oluşturun, [CMFCPropertySheet'i arayın::Görünüm](#setlook) parametresi ayarlı *look* `CMFCPropertySheet::PropSheetLook_Tree`SetLook yöntemini ayarlayın ve düğüm eklemek için bu yöntemi kullanın.

CMFCPropertySheet sonraki aramalarda bu yöntemin dönüş değerini [kullanın::AddPageToTree](#addpagetotree) ve [CMFCPropertySheet::AddTreeCategory](#addtreecategory).

## <a name="cmfcpropertysheetcmfcpropertysheet"></a><a name="cmfcpropertysheet"></a>CMFCÖzellik Sayfası::CMFCÖzellik Sayfası

Bir `CMFCPropertySheet` nesne inşa eder.

```
CMFCPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);

CMFCPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);
```

### <a name="parameters"></a>Parametreler

*pszCaption*<br/>
[içinde] Özellik sayfası başlığı içeren bir dize. NULL olamaz.

*nIDCaption*<br/>
[içinde] Özellik sayfası başlığı nı içeren kaynak kimliği.

*pParentWnd*<br/>
[içinde] Özellik sayfasının üst penceresine işaretçi veya üst pencere uygulamanın ana penceresiyse NULL. Varsayılan değer NULL'dur.

*iSelectPage*<br/>
[içinde] En üst özellik sayfasının sıfır tabanlı dizin. Varsayılan değer 0’dır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) oluşturucu parametrelerine bakın.

## <a name="cmfcpropertysheetenablepageheader"></a><a name="enablepageheader"></a>CMFCPropertySheet::EnablePageHeader

Özel bir üstbilgi çizmek için her sayfanın üst kısmında yer ayırır.

```cpp
void EnablePageHeader(int nHeaderHeight);
```

### <a name="parameters"></a>Parametreler

*nHeaderYükseklik*<br/>
[içinde] Üstbilginin yüksekliği, piksel olarak.

### <a name="remarks"></a>Açıklamalar

Özel bir üstbilgi çizmek için *nHeaderHeight* parametresinin değerini kullanmak için [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) yöntemini geçersiz kılın.

## <a name="cmfcpropertysheetgetheaderheight"></a><a name="getheaderheight"></a>CMFCÖzellik::GetHeaderHeight

Geçerli üstbilginin yüksekliğini alır.

```
int GetHeaderHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üstbilginin yüksekliği, piksel olarak.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi aramadan önce [CMFCPropertySheet::EnablePageHeader](#enablepageheader) yöntemini arayın.

## <a name="cmfcpropertysheetgetlook"></a><a name="getlook"></a>CMFCÖzellik Sayfası::GetLook

Geçerli özellik sayfasının görünümünü belirten bir numaralandırma değeri alır.

```
PropSheetLook GetLook() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfasının görünümünü belirten numaralandırma değerlerinden biri. Olası değerlerin listesi için [CMFCPropertySheet'in](#setlook)Açıklamalar bölümündeki numaralandırma tablosuna bakın:SetLook .

## <a name="cmfcpropertysheetgetnavbarwidth"></a><a name="getnavbarwidth"></a>CMFCÖzellik::GetNavBarWidth

Navigasyon çubuğunun genişliğini alır.

```
int GetNavBarWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Piksellerde gezinme çubuğunun genişliği.

## <a name="cmfcpropertysheetgettab"></a><a name="gettab"></a>CMFCÖzellik Sayfası::GetTab

Geçerli özellik sayfası denetimini destekleyen iç sekme denetim nesnesini alır.

```
CMFCTabCtrl& GetTab() const;
```

### <a name="return-value"></a>Dönüş Değeri

İç sekme denetim nesnesi.

### <a name="remarks"></a>Açıklamalar

Bir özellik sayfasını, ağaç denetimi, gezinti düğmeleri listesi veya sekmeli sayfalar kümesi gibi farklı stillerde görünecek şekilde ayarlayabilirsiniz.

Bu yöntemi aramadan önce [CMFCPropertySheet::Özellik](#setlook) sayfası denetiminin görünümünü ayarlamak için SetLook yöntemini arayın. Ardından [CMFCPropertySheet'i arayın::İç](#initnavigationcontrol) sekmesi denetim nesnesini başlatmayı sağlamak için InitNavigationControl yöntemini arayın. Sekme denetim nesnesini almak ve sonra özellik sayfasındaki sekmelerle çalışmak için bu nesneyi kullanmak için bu yöntemi kullanın.

Özellik sayfası denetimi Microsoft OneNote stilinde görünecek şekilde ayarlanmazise, bu yöntem hata ayıklama modunda ileri sürülür.

## <a name="cmfcpropertysheetinitnavigationcontrol"></a><a name="initnavigationcontrol"></a>CMFCPropertySheet::InitNavigationControl

Geçerli özellik sayfası denetiminin görünümünü başolarak karşılar.

```
virtual CWnd* InitNavigationControl();
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfası denetimipenceresine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası denetimi, sekmeli sayfalar kümesi, ağaç denetimi veya gezinti düğmeleri listesi gibi birkaç farklı biçimde görünebilir. Özellik sayfası denetiminin görünümünü belirtmek için [CMFCPropertySheet::SetLook](#setlook) yöntemini kullanın.

## <a name="cmfcpropertysheetonactivatepage"></a><a name="onactivatepage"></a>CMFCÖzellik Sayfası::OnActivatePage

Özellik sayfası etkinleştirildiğinde çerçeve tarafından çağrılır.

```
virtual void OnActivatePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
[içinde] Etkin özellik sayfasını temsil eden bir özellik sayfası nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem etkin özellik sayfasının görünüme kaydırılmasını sağlar. Geçerli özellik sayfasının stili bir Microsoft Outlook bölmesi içeriyorsa, bu yöntem denetlenen duruma karşılık gelen Outlook düğmesini ayarlar.

## <a name="cmfcpropertysheetondrawpageheader"></a><a name="ondrawpageheader"></a>CMFCPropertySheet::OnDrawPageHeader

Özel bir özellik sayfası için üstbilgi çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDrawPageHeader(
    CDC* pDC,
    int nPage,
    CRect rectHeader);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*nPage*<br/>
[içinde] Sıfır tabanlı özellik sayfa numarası.

*rektHeader*<br/>
[içinde] Üstbilginin nerede çizilen yeri belirten sınırlayıcı bir dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem hiçbir şey yapmaz. Bu yöntemi geçersiz kılarsanız, çerçeve bu yöntemi çağırmadan önce [CMFCPropertySheet::EnablePageHeader](#enablepageheader) yöntemini arayın.

## <a name="cmfcpropertysheetonremovetreepage"></a><a name="onremovetreepage"></a>CMFCÖzellik Sayfası::OnremoveTreePage

Bir özellik sayfasını ağaç denetiminden kaldırmak için çerçeve tarafından çağrılır.

```
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
[içinde] Kaldırılacak özellik sayfasını temsil eden bir özellik sayfası nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cmfcpropertysheetremovecategory"></a><a name="removecategory"></a>CMFCÖzellik Sayfası::RemoveCategory

Ağaç denetiminden bir düğüm kaldırır.

```cpp
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```

### <a name="parameters"></a>Parametreler

*pKategori*<br/>
[içinde] Kaldırılacak bir kategoriye (düğüm) işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir ağaç denetiminden kategori olarak da adlandırılan düğümü kaldırmak için bu yöntemi kullanın. [CMFCPropertySheet kullanın::Ağaç](#addtreecategory) denetimine düğüm eklemek için AddTreeCategory yöntemi.

## <a name="cmfcpropertysheetremovepage"></a><a name="removepage"></a>CMFCÖzellik Sayfası::RemovePage

Özellik sayfasını özellik sayfasından kaldırır.

```cpp
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
[içinde] Kaldırılacak özellik sayfasını temsil eden özellik sayfası nesnesine işaretçi. NULL olamaz.

*nPage*<br/>
[içinde] Sayfanın sıfır tabanlı dizin kaldırmak için.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen özellik sayfasını kaldırır ve ilişkili pencereyi yok eder. *PPage* parametresinin belirttiği özellik sayfası nesnesi, [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) penceresi kapatılana kadar yok edilmez.

## <a name="cmfcpropertysheetseticonslist"></a><a name="seticonslist"></a>CMFCÖzellik::SetIconsList

Outlook bölmesinin gezinti denetiminde kullanılan görüntülerin listesini belirtir.

```
BOOL SetIconsList(
    UINT uiImageListResID,
    int cx,
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```

### <a name="parameters"></a>Parametreler

*uiImageListResID*<br/>
[içinde] Resim listesinin kaynak kimliği.

*Cx*<br/>
[içinde] Görüntü listesindeki simgelerin piksel genişliği.

*clrŞeffaf*<br/>
[içinde] Saydam görüntü rengi. Görüntünün bu renkteki bölümleri saydam olacaktır. Varsayılan değer renk macenta, RGB (255,0,255) olduğunu.

*hIcons*<br/>
[içinde] Varolan bir resim listesine bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

İlk yöntemaşırı sözdiziminde, bu yöntem başarılı olursa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası Microsoft Outlook tarzındaysa, çerçeve özellik sayfasının solunda Outlook bölme denetimi adı verilen gezinti düğmelerinin listesini görüntüler. Outlook bölme denetimi tarafından kullanılacak görüntü listesini ayarlamak için bu yöntemi kullanın.

Bu yöntemi destekleyen yöntemler hakkında daha fazla bilgi için [Bkz. CImageList::Create](../../mfc/reference/cimagelist-class.md#create) and [CImageList::Add](../../mfc/reference/cimagelist-class.md#add). Bir özellik sayfasının stilini nasıl ayarlayınız hakkında daha fazla bilgi için [CMFCPropertySheet::SetLook](#setlook)sayfasına bakın.

## <a name="cmfcpropertysheetsetlook"></a><a name="setlook"></a>CMFCÖzellik::SetLook

Özellik sayfasının görünümünü belirtir.

```cpp
void SetLook(
    PropSheetLook look,
    int nNavControlWidth=100);
```

### <a name="parameters"></a>Parametreler

*Bak*<br/>
[içinde] Özellik sayfasının görünümünü belirten numaralandırma değerlerinden biri. Bir özellik sayfası için `CMFCPropertySheet::PropSheetLook_Tabs`varsayılan stil. Daha fazla bilgi için, bu konunun Açıklamalar bölümündeki tabloya bakın.

*nNavControlWidth*<br/>
[içinde] Piksellerde gezinme denetiminin genişliği. Varsayılan değer 100’dür.

### <a name="remarks"></a>Açıklamalar

Bir özellik sayfasını varsayılan dan farklı bir stilde görüntülemek için, özellik sayfası penceresini oluşturmadan önce bu yöntemi arayın.

Aşağıdaki tabloda *görünüm* parametresinde belirtilebilen numaralandırma değerleri listelenistir.

|Değer|Açıklama|
|-----------|-----------------|
|`CMFCPropertySheet::PropSheetLook_Tabs`|(Varsayılan) Her özellik sayfası için bir sekme görüntüler. Sekmeler özellik sayfasının üst kısmında görüntülenir ve tek bir satıra sığmayacak kadar fazla sekme varsa üst üste dizilir.|
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Özellik sayfasının sol tarafında Microsoft Outlook çubuğu nun stilinde gezinti düğmelerinin listesini görüntüler. Listedeki her düğme bir özellik sayfasına karşılık gelir. Çerçeve, listenin görünür alanına sığmayacak kadar fazla düğme varsa kaydırma okları görüntüler.|
|`CMFCPropertySheet::PropSheetLook_Tree`|Özellik sayfasının sol tarafında bir ağaç denetimi görüntüler. Ağaç denetiminin her üst veya alt düğümü bir özellik sayfasına karşılık gelir. Çerçeve, ağaç denetiminin görünür alanına sığmayacak kadar düğüm varsa kaydırma okları görüntüler.|
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Her özellik sayfası için Microsoft OneNote tarzında bir sekme görüntüler. Çerçeve, özellik sayfasının üst kısmındasek görüntüler ve tek bir satıra sığmayacak kadar fazla sekme varsa okları kaydırın.|
|`CMFCPropertySheet::PropSheetLook_List`|Özellik sayfasının sol tarafında bir liste görüntüler. Her liste öğesi bir özellik sayfasına karşılık gelir. Çerçeve, listenin görünür alanına sığmayacak kadar fazla liste öğesi varsa kaydırma okları görüntüler.|

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyPage Sınıfı](../../mfc/reference/cmfcpropertypage-class.md)<br/>
[CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)
