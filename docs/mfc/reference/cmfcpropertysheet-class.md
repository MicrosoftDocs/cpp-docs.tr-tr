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
ms.openlocfilehash: f7c9d2b472a443d8bf556d0b12dfe202ea8607a1
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "69505083"
---
# <a name="cmfcpropertysheet-class"></a>CMFCPropertySheet Sınıfı

`CMFCPropertySheet` Sınıfı, her özellik sayfasının bir sayfa sekmesi, bir araç çubuğu düğmesi, bir ağaç denetim düğümü veya bir liste öğesi tarafından belirtilen bir özellik sayfasını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPropertySheet : public CPropertySheet
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPropertySheet:: CMFCPropertySheet](#cmfcpropertysheet)|Bir `CMFCPropertySheet` nesnesi oluşturur.|
|`CMFCPropertySheet::~CMFCPropertySheet`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPropertySheet:: AddPage](#addpage)|Özellik sayfasına bir sayfa ekler.|
|[CMFCPropertySheet:: AddPageToTree](#addpagetotree)|Ağaç denetimine yeni bir özellik sayfası ekler.|
|[CMFCPropertySheet:: AddTreeCategory](#addtreecategory)|Ağaç denetimine yeni bir düğüm ekler.|
|[CMFCPropertySheet:: EnablePageHeader](#enablepageheader)|Özel üst bilgi çizmek için her sayfanın üst kısmındaki alanı ayırır.|
|[CMFCPropertySheet:: GetHeaderHeight](#getheaderheight)|Geçerli üstbilginin yüksekliğini alır.|
|[CMFCPropertySheet:: GetLook](#getlook)|Geçerli özellik sayfasının görünümünü belirten bir sabit listesi değeri alır.|
|[CMFCPropertySheet:: GetNavBarWidth](#getnavbarwidth)|Gezinme çubuğunun genişliğini piksel cinsinden yeniden dener.|
|[CMFCPropertySheet:: GetTab](#gettab)|Geçerli özellik sayfası denetimini destekleyen iç sekme denetim nesnesini alır.|
|`CMFCPropertySheet::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCPropertySheet:: InitNavigationControl](#initnavigationcontrol)|Geçerli özellik sayfası denetiminin görünümünü başlatır.|
|[CMFCPropertySheet:: OnActivatePage](#onactivatepage)|Bir özellik sayfası etkinleştirildiğinde Framework tarafından çağırılır.|
|[CMFCPropertySheet:: OnDrawPageHeader](#ondrawpageheader)|Özel bir özellik sayfası üst bilgisi çizmek için Framework tarafından çağırılır.|
|`CMFCPropertySheet::OnInitDialog`|[WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) iletisini işler. ( [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)geçersiz kılar.)|
|[CMFCPropertySheet:: OnRemoveTreePage](#onremovetreepage)|Bir ağaç denetiminden bir özellik sayfasını kaldırmak için Framework tarafından çağırılır.|
|`CMFCPropertySheet::PreTranslateMessage`|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce pencere iletilerini çevirir. (Geçersiz `CPropertySheet::PreTranslateMessage`kılmalar.)|
|[CMFCPropertySheet:: RemoveCategory](#removecategory)|Ağaç denetiminden bir düğümü kaldırır.|
|[CMFCPropertySheet:: RemovePage](#removepage)|Özellik sayfasından özellik sayfasını kaldırır.|
|[CMFCPropertySheet:: SetIconsList](#seticonslist)|Outlook bölmesinin gezinti denetiminde kullanılan görüntülerin listesini belirtir.|
|[CMFCPropertySheet:: SetLook](#setlook)|Özellik sayfasının görünümünü belirtir.|

## <a name="remarks"></a>Açıklamalar

`CMFCPropertySheet` Sınıfı, sekme iletişim kutusu olarak da bilinen özellik sayfalarını temsil eder. Sınıfı `CMFCPropertySheet` , bir özellik sayfasını çeşitli yollarla gösterebilir.

Uygulamanızda `CMFCPropertySheet` sınıfını kullanmak için aşağıdaki adımları gerçekleştirin:

1. Sınıfından bir sınıf `CMFCPropertySheet` türetirsiniz ve sınıfı adlandırın, örneğin, CMyPropertySheet.

1. Her özellik sayfası için bir [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) nesnesi oluşturun.

1. CMyPropertySheet oluşturucusunda [CMFCPropertySheet:: SetLook](#setlook) metodunu çağırın. Bu yöntemin parametresi, özellik sayfalarının, özellik sayfasının üst veya sol tarafında sekme olarak görüntüleneceğini belirtir; bir Microsoft OneNote özellik sayfasının stilindeki sekmeler; Microsoft Outlook araç çubuğu denetimindeki düğmeler; ağaç denetimindeki düğümler; ya da Özellik sayfasının sol tarafındaki öğelerin listesi.

1. Bir Microsoft Outlook araç çubuğunun stilinde bir özellik sayfası oluşturursanız, bir görüntü listesini özellik sayfalarıyla ilişkilendirmek için [CMFCPropertySheet:: SetIconsList](#seticonslist) yöntemini çağırın.

1. Her özellik sayfası için [CMFCPropertySheet:: AddPage](#addpage) yöntemini çağırın.

1. Bir `CMFCPropertySheet` denetim oluşturun ve `DoModal` metodunu çağırın.

## <a name="illustrations"></a>Çizimler

Aşağıdaki çizimde, katıştırılmış bir Microsoft Outlook araç çubuğunun stilinde olan bir özellik sayfası gösterilmektedir. Outlook araç çubuğu, özellik sayfasının sol tarafında görünür.

![CMFCPropertySheet renk denetimleri](../../mfc/reference/media/cmfcpropertysheet_color.png "CMFCPropertySheet renk denetimleri")

Aşağıdaki çizimde, bir [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md) nesnesi içeren bir özellik sayfası gösterilmektedir. Bu nesne, standart ortak denetimler Özellik sayfası stilindeki bir özellik sayfası.

![CMFCPropertySheet listesi ve özellik denetimleri](../../mfc/reference/media/cmfcpropertysheet_list.png "CMFCPropertySheet listesi ve özellik denetimleri")

Aşağıdaki çizimde bir ağaç denetiminin stilinde olan bir özellik sayfası gösterilmektedir.

![Özellik ağacı](../../mfc/reference/media/proptree.png "Özellik ağacı")

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpropertysheet. h

##  <a name="addpage"></a>CMFCPropertySheet:: AddPage

Özellik sayfasına bir sayfa ekler.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
'ndaki Sayfa nesnesi işaretçisi. Bu parametre NULL olamaz.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen özellik sayfasını Özellik sayfasına en sağdaki sekme olarak ekler. Bu nedenle, sayfaları soldan sağa düzende eklemek için bu yöntemi kullanın.

Özellik sayfası Microsoft Outlook tarzuysa, Framework, özellik sayfasının sol tarafında bulunan gezinti düğmelerinin bir listesini görüntüler. Bu yöntem bir özellik sayfası ekledikten sonra listeye karşılık gelen bir düğme ekler. Bir özellik sayfasını göstermek için ilgili düğmeye tıklayın. Özellik sayfası stilleri hakkında daha fazla bilgi için bkz. [CMFCPropertySheet:: SetLook](#setlook).

##  <a name="addpagetotree"></a>CMFCPropertySheet:: AddPageToTree

Ağaç denetimine yeni bir özellik sayfası ekler.

```
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,
    CMFCPropertyPage* pPage,
    int nIconNum=-1,
    int nSelIconNum=-1);
```

### <a name="parameters"></a>Parametreler

*pCategory*<br/>
'ndaki Üst ağaç düğümünün işaretçisi veya belirtilen sayfanın üst düzey düğümle ilişkilendirilmesi için NULL. Bu işaretçiyi almak için [CMFCPropertySheet:: AddTreeCategory](#addtreecategory) metodunu çağırın.

*pPage*<br/>
'ndaki Özellik sayfası nesnesine yönelik işaretçi.

*nIconNum*<br/>
'ndaki Bir simgenin sıfır tabanlı dizini veya hiçbir simge kullanılmazsa-1. Simge, sayfa seçilmediğinde ağaç denetimi özellik sayfasının yanında görüntülenir. Varsayılan değer-1 ' dir.

*nSelIconNum*<br/>
'ndaki Bir simgenin sıfır tabanlı dizini veya hiçbir simge kullanılmazsa-1. Simge, sayfa seçildiğinde ağaç denetimi özellik sayfasının yanında görüntülenir. Varsayılan değer-1 ' dir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir ağaç denetiminin yaprağı olarak bir özellik sayfası ekler. Bir özellik sayfası eklemek için, bir `CMFCPropertySheet` nesne oluşturun, *Bak* parametresi olarak `CMFCPropertySheet::PropSheetLook_Tree`ayarlanmış [CMFCPropertySheet:: SetLook](#setlook) metodunu çağırın ve sonra özellik sayfasını eklemek için bu yöntemi kullanın.

##  <a name="addtreecategory"></a>CMFCPropertySheet:: AddTreeCategory

Ağaç denetimine yeni bir düğüm ekler.

```
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,
    int nIconNum=-1,
    int nSelectedIconNum=-1,
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki Düğümün adı.

*nIconNum*<br/>
'ndaki Bir simgenin sıfır tabanlı dizini veya hiçbir simge kullanılmazsa-1. Simge, sayfa seçilmediğinde ağaç denetimi özellik sayfasının yanında görüntülenir. Varsayılan değer-1 ' dir.

*nSelectedIconNum*<br/>
'ndaki Bir simgenin sıfır tabanlı dizini veya hiçbir simge kullanılmazsa-1. Simge, sayfa seçildiğinde ağaç denetimi özellik sayfasının yanında görüntülenir. Varsayılan değer-1 ' dir.

*pParentCategory*<br/>
'ndaki Üst ağaç düğümünün işaretçisi veya belirtilen sayfanın üst düzey düğümle ilişkilendirilmesi için NULL. Bu parametreyi [CMFCPropertySheet:: AddTreeCategory](#addtreecategory) yöntemiyle ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

Ağaç denetimindeki yeni düğüme yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Ağaç denetimine kategori olarak da adlandırılan yeni bir düğüm eklemek için bu yöntemi kullanın. Bir düğüm eklemek için bir nesne oluşturun `CMFCPropertySheet` , bir nesne oluşturun, *Bak* parametresi olarak `CMFCPropertySheet::PropSheetLook_Tree`ayarlanmış [CMFCPropertySheet:: SetLook](#setlook) metodunu çağırın ve ardından bu yöntemi kullanarak düğümü ekleyin.

Bu yöntemin dönüş değerini [CMFCPropertySheet:: AddPageToTree](#addpagetotree) ve [CMFCPropertySheet:: AddTreeCategory](#addtreecategory)için sonraki çağrılarda kullanın.

##  <a name="cmfcpropertysheet"></a>CMFCPropertySheet:: CMFCPropertySheet

Bir `CMFCPropertySheet` nesnesi oluşturur.

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
'ndaki Özellik sayfası başlığını içeren bir dize. NULL olamaz.

*nIDCaption*<br/>
'ndaki Özellik sayfası başlığını içeren bir kaynak KIMLIĞI.

*pParentWnd*<br/>
'ndaki Özellik sayfasının üst penceresine yönelik işaretçi veya üst pencere uygulamanın ana penceresi ise NULL. Varsayılan değer NULL.

*ıselectpage*<br/>
'ndaki Üstteki Özellik sayfasının sıfır tabanlı dizini. Varsayılan değer 0’dır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [CPropertySheet:: CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) Oluşturucusu parametreleri.

##  <a name="enablepageheader"></a>CMFCPropertySheet:: EnablePageHeader

Özel üst bilgi çizmek için her sayfanın üst kısmındaki alanı ayırır.

```
void EnablePageHeader(int nHeaderHeight);
```

### <a name="parameters"></a>Parametreler

*nHeaderHeight*<br/>
'ndaki Üstbilginin piksel cinsinden yüksekliği.

### <a name="remarks"></a>Açıklamalar

Özel üst bilgi çizmek için *nHeaderHeight* parametresinin değerini kullanmak Için [CMFCPropertySheet:: OnDrawPageHeader](#ondrawpageheader) metodunu geçersiz kılın.

##  <a name="getheaderheight"></a>CMFCPropertySheet:: GetHeaderHeight

Geçerli üstbilginin yüksekliğini alır.

```
int GetHeaderHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üstbilginin piksel cinsinden yüksekliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağırabilmeniz için [CMFCPropertySheet:: EnablePageHeader](#enablepageheader) metodunu çağırın.

##  <a name="getlook"></a>CMFCPropertySheet:: GetLook

Geçerli özellik sayfasının görünümünü belirten bir sabit listesi değeri alır.

```
PropSheetLook GetLook() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfasının görünümünü belirten sabit listesi değerlerinden biri. Olası değerler listesi için [CMFCPropertySheet:: SetLook](#setlook)' ın açıklamalar bölümünde numaralandırma tablosuna bakın.

##  <a name="getnavbarwidth"></a>CMFCPropertySheet:: GetNavBarWidth

Gezinti çubuğunun genişliğini alır.

```
int GetNavBarWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gezinme çubuğunun piksel cinsinden genişliği.

##  <a name="gettab"></a>CMFCPropertySheet:: GetTab

Geçerli özellik sayfası denetimini destekleyen iç sekme denetim nesnesini alır.

```
CMFCTabCtrl& GetTab() const;
```

### <a name="return-value"></a>Dönüş Değeri

İç sekme denetim nesnesi.

### <a name="remarks"></a>Açıklamalar

Bir özellik sayfasını ağaç denetimi, gezinti düğmelerinin listesi veya sekmeli bir sayfa kümesi gibi farklı stillerde görüntülenecek şekilde ayarlayabilirsiniz.

Bu yöntemi çağırmadan önce, özellik sayfası denetiminin görünümünü ayarlamak için [CMFCPropertySheet:: SetLook](#setlook) metodunu çağırın. Ardından, iç sekme denetim nesnesini başlatmak için [CMFCPropertySheet:: InitNavigationControl](#initnavigationcontrol) metodunu çağırın. Tab denetim nesnesini almak için bu yöntemi kullanın ve ardından bu nesneyi kullanarak özellik sayfasındaki sekmelerle çalışın.

Bu yöntem, özellik sayfası denetimi Microsoft OneNote stilinde görüntülenecek şekilde ayarlanmamışsa hata ayıklama modunda onay sağlar.

##  <a name="initnavigationcontrol"></a>CMFCPropertySheet:: InitNavigationControl

Geçerli özellik sayfası denetiminin görünümünü başlatır.

```
virtual CWnd* InitNavigationControl();
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfası denetiminin penceresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir özellik sayfası denetimi, sekmeli sayfalar kümesi, ağaç denetimi veya gezinti düğmeleri listesi gibi çeşitli farklı formlarda görünebilir. Özellik sayfası denetiminin görünümünü belirtmek için [CMFCPropertySheet:: SetLook](#setlook) metodunu kullanın.

##  <a name="onactivatepage"></a>CMFCPropertySheet:: OnActivatePage

Bir özellik sayfası etkinleştirildiğinde Framework tarafından çağırılır.

```
virtual void OnActivatePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
'ndaki Etkin özellik sayfasını temsil eden bir özellik sayfası nesnesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem etkin özellik sayfasının görünüme kaydırılmasını sağlar. Geçerli özellik sayfasının stili bir Microsoft Outlook bölmesi içeriyorsa, bu yöntem ilgili Outlook düğmesini işaretli duruma ayarlar.

##  <a name="ondrawpageheader"></a>CMFCPropertySheet:: OnDrawPageHeader

Özel bir özellik sayfası için üst bilgi çizmek üzere Framework tarafından çağırılır.

```
virtual void OnDrawPageHeader(
    CDC* pDC,
    int nPage,
    CRect rectHeader);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamı işaretçisi.

*Nsayfa*<br/>
'ndaki Sıfır tabanlı özellik sayfa numarası.

*rectHeader*<br/>
'ndaki Üstbilginin nerede çizileceğini belirten bir sınırlayıcı dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem hiçbir şey yapmaz. Bu yöntemi geçersiz kılarsınız Framework bu yöntemi çağırmadan önce [CMFCPropertySheet:: EnablePageHeader](#enablepageheader) metodunu çağırın.

##  <a name="onremovetreepage"></a>CMFCPropertySheet:: OnRemoveTreePage

Bir ağaç denetiminden bir özellik sayfasını kaldırmak için Framework tarafından çağırılır.

```
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
'ndaki Kaldırılacak özellik sayfasını temsil eden bir özellik sayfası nesnesi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

##  <a name="removecategory"></a>CMFCPropertySheet:: RemoveCategory

Ağaç denetiminden bir düğümü kaldırır.

```
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```

### <a name="parameters"></a>Parametreler

*pCategory*<br/>
'ndaki Kaldırılacak kategori (node) işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir ağaç denetiminden kategori olarak da adlandırılan bir düğümü kaldırmak için bu yöntemi kullanın. Ağaç denetimine bir düğüm eklemek için [CMFCPropertySheet:: AddTreeCategory](#addtreecategory) metodunu kullanın.

##  <a name="removepage"></a>CMFCPropertySheet:: RemovePage

Özellik sayfasından özellik sayfasını kaldırır.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
'ndaki Kaldırılacak özellik sayfasını temsil eden özellik sayfası nesnesi işaretçisi. NULL olamaz.

*Nsayfa*<br/>
'ndaki Kaldırılacak sayfanın sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen özellik sayfasını kaldırır ve ilişkili penceresini yok eder. [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) penceresi kapatılıncaya kadar *pPage* parametresinin belirttiği Özellik sayfası nesnesi yok edilmez.

##  <a name="seticonslist"></a>CMFCPropertySheet:: SetIconsList

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
'ndaki Bir görüntü listesinin kaynak KIMLIĞI.

*yazmaç*<br/>
'ndaki Görüntü listesindeki simgelerin piksel cinsinden genişliği.

*clrTransparent*<br/>
'ndaki Saydam görüntü rengi. Bu renk olan görüntünün parçaları saydam olacaktır. Varsayılan değer macenta, RGB (255, 0255) renktedir.

*Hcons*<br/>
'ndaki Varolan bir görüntü listesinin tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem aşırı yükleme sözdiziminde, bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası Microsoft Outlook tarzuysa, Framework, özellik sayfasının solunda, Outlook bölmesi denetimi olarak adlandırılan gezinti düğmelerinin bir listesini görüntüler. Outlook bölmesi denetimi tarafından kullanılacak görüntü listesini ayarlamak için bu yöntemi kullanın.

Bu yöntemi destekleyen yöntemler hakkında daha fazla bilgi için bkz. [CImageList:: Create](../../mfc/reference/cimagelist-class.md#create) ve [CImageList:: Add](../../mfc/reference/cimagelist-class.md#add). Bir özellik sayfasının stilini ayarlama hakkında daha fazla bilgi için bkz. [CMFCPropertySheet:: SetLook](#setlook).

##  <a name="setlook"></a>CMFCPropertySheet:: SetLook

Özellik sayfasının görünümünü belirtir.

```
void SetLook(
    PropSheetLook look,
    int nNavControlWidth=100);
```

### <a name="parameters"></a>Parametreler

*aþaðýdaki*<br/>
'ndaki Özellik sayfasının görünümünü belirten sabit listesi değerlerinden biri. Bir özellik sayfası `CMFCPropertySheet::PropSheetLook_Tabs`için varsayılan stil. Daha fazla bilgi için bu konunun açıklamalar bölümündeki tabloya bakın.

*nNavControlWidth*<br/>
'ndaki Gezinti denetiminin piksel cinsinden genişliği. Varsayılan değer 100’dür.

### <a name="remarks"></a>Açıklamalar

Bir özellik sayfasını varsayılan dışında bir stilde göstermek için, özellik sayfası penceresini oluşturmadan önce bu yöntemi çağırın.

Aşağıdaki tabloda, *Look* parametresinde belirtime sabit listesi değerleri listelenmektedir.

|Değer|Açıklama|
|-----------|-----------------|
|`CMFCPropertySheet::PropSheetLook_Tabs`|Varsayılanını Her özellik sayfası için bir sekme görüntüler. Sekmeler, özellik sayfasının en üstünde görüntülenir ve tek bir satıra sığacak kadar daha fazla sekme varsa yığınlanacaktır.|
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Özellik sayfasının sol tarafındaki Microsoft Outlook çubuğunun stilinde, gezinti düğmelerinin bir listesini görüntüler. Listedeki her düğme bir özellik sayfasına karşılık gelir. Çerçeve, listenin görünür alanına sığmayacak kadar çok düğme varsa kaydırma oklarını görüntüler.|
|`CMFCPropertySheet::PropSheetLook_Tree`|Özellik sayfasının sol tarafında bir ağaç denetimi görüntüler. Ağaç denetiminin her bir üst veya alt düğümü bir özellik sayfasına karşılık gelir. Çerçeve, ağaç denetiminin görünür alanına sığmayacak kadar çok düğüm varsa kaydırma oklarını görüntüler.|
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Her özellik sayfası için Microsoft OneNote stilinde bir sekme görüntüler. Çerçeve, özellikler sayfasının en üstünde sekmeleri ve tek bir satıra sığacak kadar daha fazla sekme varsa kaydırma oklarını görüntüler.|
|`CMFCPropertySheet::PropSheetLook_List`|Özellik sayfasının sol tarafında bir liste görüntüler. Her liste öğesi bir özellik sayfasına karşılık gelir. Çerçeve, listenin görünür alanına sığacak olandan daha fazla liste öğesi varsa, kaydırma oklarını görüntüler.|

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyPage Sınıfı](../../mfc/reference/cmfcpropertypage-class.md)<br/>
[CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)
