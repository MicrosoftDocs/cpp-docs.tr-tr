---
title: CMFCPropertySheet sınıfı
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
ms.openlocfilehash: 1168375606ef86061269454aa361a076efa331a4
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176412"
---
# <a name="cmfcpropertysheet-class"></a>CMFCPropertySheet sınıfı

`CMFCPropertySheet` Sınıfı, burada her bir özellik sayfası belirtilen bir sayfa sekmesi, araç çubuğu düğmesi, ağaç denetimi düğümü veya bir liste öğesi bir özellik sayfasını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPropertySheet : public CPropertySheet
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|Oluşturur bir `CMFCPropertySheet` nesne.|
|`CMFCPropertySheet::~CMFCPropertySheet`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPropertySheet::AddPage](#addpage)|Bir sayfa için özellik sayfası ekler.|
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|Ağaç denetimi için yeni bir özellik sayfası ekler.|
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|Yeni bir düğüm için ağaç denetimi ekler.|
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|Özel bir başlık çizmek için her sayfanın üst kısmındaki yer ayırır.|
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|Geçerli üstbilgisinin yüksekliğini alır.|
|[CMFCPropertySheet::GetLook](#getlook)|Geçerli özellik sayfasının görünümünü belirten sabit listesi değeri alır.|
|[CMFCPropertySheet::GetNavBarWidth](#getnavbarwidth)|Gezinti çubuğunun piksel cinsinden genişliğini yeniden dener.|
|[CMFCPropertySheet::GetTab](#gettab)|Geçerli özellik sayfası denetimi destekleyen iç sekme denetim nesnesi alır.|
|`CMFCPropertySheet::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|Geçerli özellik listesi denetiminin görünümünü başlatır.|
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|Özellik sayfası etkinleştirildiğinde framework tarafından çağırılır.|
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|Özel özellik sayfa üstbilgisi çizmek için framework tarafından çağırılır.|
|`CMFCPropertySheet::OnInitDialog`|İşleme [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) ileti. (Geçersiz kılmaları [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|Özellik sayfası bir ağaç denetiminden kaldırmak için framework tarafından çağırılır.|
|`CMFCPropertySheet::PreTranslateMessage`|Pencere iletileri için dağıtılmadan önce çevirir [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows işlevleri. (Geçersiz kılmaları `CPropertySheet::PreTranslateMessage`.)|
|[CMFCPropertySheet::RemoveCategory](#removecategory)|Bir düğüm ağaç denetiminden kaldırır.|
|[CMFCPropertySheet::RemovePage](#removepage)|Özellik sayfası özellik sayfası'ndan kaldırır.|
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Outlook bölmesinin Gezinti denetimde kullanılan görüntülerin listesini belirtir.|
|[CMFCPropertySheet::SetLook](#setlook)|Özellik Sayfası görünümünü belirtir.|

## <a name="remarks"></a>Açıklamalar

`CMFCPropertySheet` Sınıfı temsil eder, özellik sayfaları iletişim kutusu olarak da bilinir. `CMFCPropertySheet` Sınıfı bir özellik sayfası çeşitli şekillerde görüntüleyebilirsiniz.

Kullanmak için aşağıdaki adımları gerçekleştirin `CMFCPropertySheet` uygulamanızdaki sınıf:

1. Öğesinden bir sınıf türetin `CMFCPropertySheet` sınıfı ve örneğin CMyPropertySheet sınıfı adı.

1. Oluşturmak bir [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) her bir özellik sayfası nesnesi.

1. Çağrı [CMFCPropertySheet::SetLook](#setlook) CMyPropertySheet oluşturucuda yöntemi. Özellik sayfaları görüntülenen bu yöntemin bir parametre belirtir üst veya sol özellik sayfasının; sekmeleri olarak Microsoft OneNote özellik sayfası stilini sekmelerde; Microsoft Outlook araç çubuğu denetimi düğmelerini; Ağaç denetimi düğümlerinde; veya özellik sayfasının sol tarafındaki öğelerin listesini olarak.

1. Microsoft Outlook araç stilinde bir özellik sayfası oluşturun, çağrı [CMFCPropertySheet::SetIconsList](#seticonslist) özellik sayfaları ile birlikte bir görüntü listesi ilişkilendirmek için yöntemi.

1. Çağrı [CMFCPropertySheet::AddPage](#addpage) her bir özellik sayfası için yöntemi.

1. Oluşturma bir `CMFCPropertySheet` denetlemek ve çağrı kendi `DoModal` yöntemi.

## <a name="illustrations"></a>Çizimler

Aşağıdaki çizimde, bir gömülü Microsoft Outlook araç stilinde bir özellik sayfası gösterilmektedir. Outlook araç özellik sayfasının sol tarafında görünür.

![CMFCPropertySheet renk denetimleri](../../mfc/reference/media/cmfcpropertysheet_color.png "CMFCPropertySheet renk denetimleri")

Aşağıdaki çizimde gösterilmektedir içeren bir özellik sayfası bir [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md) nesne. Bu özellik sayfasında standart bir ortak denetimleri özellik sayfası stilini nesnedir.

![CMFCPropertySheet liste ve özellik denetimleri](../../mfc/reference/media/cmfcpropertysheet_list.png "CMFCPropertySheet liste ve özellik denetimleri")

Aşağıdaki çizimde, bir ağaç denetimi stilinde bir özellik sayfası gösterilmektedir.

![Özellik ağacı](../../mfc/reference/media/proptree.png "özellik ağacı")

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxpropertysheet.h

##  <a name="addpage"></a>  CMFCPropertySheet::AddPage

Bir sayfa için özellik sayfası ekler.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*fsayfa*<br/>
[in] Bir sayfa nesnesine yönelik işaretçi. Bu parametre NULL olamaz.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, özellik sayfasında en sağdaki sekme olarak belirtilen özellik sayfası ekler. Bu nedenle, soldan sağa doğru sırayla sayfalar eklemek için bu yöntemi kullanın.

Microsoft Outlook stilinde özellik sayfası ise framework özellik sayfasının sol gezinti düğmeleri listesini görüntüler. Bu yöntem, özellik sayfası ekledikten sonra karşılık gelen bir düğme listesine ekler. Bir özellik sayfasını görüntülemek için karşılık gelen düğmeye tıklayın. Özellik sayfaları stilleri hakkında daha fazla bilgi için bkz. [CMFCPropertySheet::SetLook](#setlook).

##  <a name="addpagetotree"></a>  CMFCPropertySheet::AddPageToTree

Ağaç denetimi için yeni bir özellik sayfası ekler.

```
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,
    CMFCPropertyPage* pPage,
    int nIconNum=-1,
    int nSelIconNum=-1);
```

### <a name="parameters"></a>Parametreler

*pCategory*<br/>
[in] Bir üst ağaç düğümü veya belirtilen sayfa üst düzey düğüm ile ilişkilendirmek için NULL işaretçisi. Çağrı [CMFCPropertySheet::AddTreeCategory](#addtreecategory) this işaretçisi elde etmek için yöntemi.

*fsayfa*<br/>
[in] Bir özellik sayfası nesnesi için işaretçi.

*nIconNum*<br/>
[in] Simge veya herhangi bir simge kullanılıyorsa, -1 sıfır tabanlı dizini. Sayfanın seçili olmadığında simgenin yanındaki ağaç denetimi özellik sayfası görüntülenir. Varsayılan değer -1'dir.

*nSelIconNum*<br/>
[in] Simge veya herhangi bir simge kullanılıyorsa, -1 sıfır tabanlı dizini. Sayfa seçildiğinde simge yanındaki ağaç denetimi özellik sayfası görüntülenir. Varsayılan değer -1'dir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir ağaç denetimi bir yaprak özellik sayfası ekler. Özellik sayfası eklemek için oluşturun bir `CMFCPropertySheet` nesne, çağrı [CMFCPropertySheet::SetLook](#setlook) yöntemiyle *Ara* parametresini `CMFCPropertySheet::PropSheetLook_Tree`ve ardından özellik sayfasını eklemek için bu yöntemi kullanın .

##  <a name="addtreecategory"></a>  CMFCPropertySheet::AddTreeCategory

Yeni bir düğüm için ağaç denetimi ekler.

```
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,
    int nIconNum=-1,
    int nSelectedIconNum=-1,
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
[in] Düğümün adı.

*nIconNum*<br/>
[in] Simge veya herhangi bir simge kullanılıyorsa, -1 sıfır tabanlı dizini. Sayfanın seçili olmadığında simgenin yanındaki ağaç denetimi özellik sayfası görüntülenir. Varsayılan değer -1'dir.

*nSelectedIconNum*<br/>
[in] Simge veya herhangi bir simge kullanılıyorsa, -1 sıfır tabanlı dizini. Sayfa seçildiğinde simge yanındaki ağaç denetimi özellik sayfası görüntülenir. Varsayılan değer -1'dir.

*pParentCategory*<br/>
[in] Bir üst ağaç düğümü veya belirtilen sayfa üst düzey düğüm ile ilişkilendirmek için NULL işaretçisi. Bu parametre ile [CMFCPropertySheet::AddTreeCategory](#addtreecategory) yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Ağaç denetimindeki yeni düğüm için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Ağaç denetimi için de bir kategori olarak adlandırılan, yeni bir düğüm eklemek için bu yöntemi kullanın. Bir düğüm eklemek için oluşturun bir `CMFCPropertySheet` nesne, çağrı [CMFCPropertySheet::SetLook](#setlook) yöntemiyle *Ara* parametresini `CMFCPropertySheet::PropSheetLook_Tree`ve ardından düğümü eklemek için bu yöntemi kullanın.

Bu yöntemin dönüş değerini yapılan sonraki çağrılar kullanmak [CMFCPropertySheet::AddPageToTree](#addpagetotree) ve [CMFCPropertySheet::AddTreeCategory](#addtreecategory).

##  <a name="cmfcpropertysheet"></a>  CMFCPropertySheet::CMFCPropertySheet

Oluşturur bir `CMFCPropertySheet` nesne.

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
[in] Özellik sayfası başlığını içeren bir dize. NULL olamaz.

*nIDCaption*<br/>
[in] Özellik sayfası başlığını içeren bir kaynak kimliği.

*pParentWnd*<br/>
[in] Üst penceresine özellik sayfası ya da üst pencere uygulamanın ana pencere ise NULL işaretçisi. Varsayılan değer NULL olur.

*iSelectPage*<br/>
[in] Üst özellik sayfasının sıfır tabanlı dizini. Varsayılan değer 0’dır.

### <a name="remarks"></a>Açıklamalar

Parametreler için daha fazla bilgi için bkz. [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) Oluşturucusu.

##  <a name="enablepageheader"></a>  CMFCPropertySheet::EnablePageHeader

Özel bir başlık çizmek için her sayfanın üst kısmındaki yer ayırır.

```
void EnablePageHeader(int nHeaderHeight);
```

### <a name="parameters"></a>Parametreler

*nHeaderHeight*<br/>
[in] Başlık piksel cinsinden yüksekliği.

### <a name="remarks"></a>Açıklamalar

Değerini kullanacak şekilde *nHeaderHeight* parametre özel üst bilgi çizmek için geçersiz kılma [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) yöntemi.

##  <a name="getheaderheight"></a>  CMFCPropertySheet::GetHeaderHeight

Geçerli üstbilgisinin yüksekliğini alır.

```
int GetHeaderHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başlık piksel cinsinden yüksekliği.

### <a name="remarks"></a>Açıklamalar

Çağrı [CMFCPropertySheet::EnablePageHeader](#enablepageheader) bu yöntemi çağırmadan önce yöntemi.

##  <a name="getlook"></a>  CMFCPropertySheet::GetLook

Geçerli özellik sayfasının görünümünü belirten sabit listesi değeri alır.

```
PropSheetLook GetLook() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özellik Sayfası görünümünü belirten numaralandırma değerlerinden biri. Olası değerler listesi için açıklamalar bölümünde numaralandırma tabloya bakın [CMFCPropertySheet::SetLook](#setlook).

##  <a name="getnavbarwidth"></a>  CMFCPropertySheet::GetNavBarWidth

Gezinti çubuğunun genişliğini alır.

```
int GetNavBarWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gezinti çubuğunun piksel cinsinden genişliği.

##  <a name="gettab"></a>  CMFCPropertySheet::GetTab

Geçerli özellik sayfası denetimi destekleyen iç sekme denetim nesnesi alır.

```
CMFCTabCtrl& GetTab() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir iç sekme denetim nesnesi.

### <a name="remarks"></a>Açıklamalar

Gezinti düğmelerini veya sekmeli sayfalar kümesi listesini bir ağaç denetimi gibi farklı stillerde görünmesi bir özellik sayfası ayarlayabilirsiniz.

Bu yöntemi çağırmadan önce çağrı [CMFCPropertySheet::SetLook](#setlook) özellik sayfası denetiminin görünümünü ayarlamak için yöntemi. Ardından çağırın [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) iç sekme denetim nesnesi başlatmak için yöntemi. Sekme denetim nesnesi almak ve ardından bu nesne özellik sayfasında sekmeleri ile çalışmak için bu yöntemi kullanın.

Bu yöntem, özellik sayfası denetimi için Microsoft OneNote stilinde görünür ayarlanmamışsa hata ayıklama modunda onaylar.

##  <a name="initnavigationcontrol"></a>  CMFCPropertySheet::InitNavigationControl

Geçerli özellik listesi denetiminin görünümünü başlatır.

```
virtual CWnd* InitNavigationControl();
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfası denetimi penceresine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir özellik sayfası denetimi sekmeli sayfalar, bir ağaç denetimi ve Gezinti düğmelerinin listesini bir dizi gibi birçok farklı biçimleri görüntülenebilir. Kullanım [CMFCPropertySheet::SetLook](#setlook) özellik sayfası denetiminin görünümünü belirtmek için yöntemi.

##  <a name="onactivatepage"></a>  CMFCPropertySheet::OnActivatePage

Özellik sayfası etkinleştirildiğinde framework tarafından çağırılır.

```
virtual void OnActivatePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*fsayfa*<br/>
[in] Etkinleştirilen özellik sayfasını temsil eden bir özellik sayfa nesnesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, etkin bir özellik sayfası görünüme kaydırılan, bu yöntem sağlar. Geçerli özellik sayfası stilini Microsoft Outlook bölmesi içeriyorsa, bu yöntem, karşılık gelen bir Outlook düğme işaretli durumuna ayarlar.

##  <a name="ondrawpageheader"></a>  CMFCPropertySheet::OnDrawPageHeader

Bir özel özellik sayfası için başlığı çizilmesi gerektiğinde framework tarafından çağırılır.

```
virtual void OnDrawPageHeader(
    CDC* pDC,
    int nPage,
    CRect rectHeader);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı işaretçisi.

*nPage*<br/>
[in] Sıfır tabanlı özellik sayfa numarası.

*rectHeader*<br/>
[in] Üst bilgi nerede belirtir sınırlayıcı bir dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntemi hiçbir şey yapmaz. Bu yöntemi geçersiz kılarsanız, çağrı [CMFCPropertySheet::EnablePageHeader](#enablepageheader) framework bu yöntemi çağırmadan önce yöntemi.

##  <a name="onremovetreepage"></a>  CMFCPropertySheet::OnRemoveTreePage

Özellik sayfası bir ağaç denetiminden kaldırmak için framework tarafından çağırılır.

```
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*fsayfa*<br/>
[in] Kaldırmak için özellik sayfasını temsil eden bir özellik sayfası nesnesi için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

##  <a name="removecategory"></a>  CMFCPropertySheet::RemoveCategory

Bir düğüm ağaç denetiminden kaldırır.

```
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```

### <a name="parameters"></a>Parametreler

*pCategory*<br/>
[in] İşaretçi kaldırmak için bir kategoriye (node).

### <a name="remarks"></a>Açıklamalar

Ayrıca bir kategori olarak ağaç denetiminden adlandırılan bir düğümü kaldırmak için bu yöntemi kullanın. Kullanım [CMFCPropertySheet::AddTreeCategory](#addtreecategory) bir ağaç denetimi için bir düğüm eklemek için yöntemi.

##  <a name="removepage"></a>  CMFCPropertySheet::RemovePage

Özellik sayfası özellik sayfası'ndan kaldırır.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Parametreler

*fsayfa*<br/>
[in] Kaldırmak için özellik sayfasını temsil eden özellik sayfa nesnesi işaretçisi. NULL olamaz.

*nPage*<br/>
[in] Sayfasında, kaldırmak için sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen özellik sayfasını kaldırır ve onun ilişkili penceresini yok eder. Özellik sayfası nesnesi *fsayfa* parametresinin belirttiği yok edildiğinde kadar [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) penceresi kapatılır.

##  <a name="seticonslist"></a>  CMFCPropertySheet::SetIconsList

Outlook bölmesinin Gezinti denetimde kullanılan görüntülerin listesini belirtir.

```
BOOL SetIconsList(
    UINT uiImageListResID,
    int cx,
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```

### <a name="parameters"></a>Parametreler

*uiImageListResID*<br/>
[in] Görüntü listesi kaynak kimliği.

*CX*<br/>
[in] Simge görüntü listesinde piksel cinsinden genişliği.

*clrTransparent*<br/>
[in] Resmi saydam rengi. Bu renk bölümleri resminin saydam olacak. Renk Eflatun RGB(255,0,255) varsayılan değerdir.

*hIcons*<br/>
[in] Varolan bir görüntü listesi için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

İlk yöntemde sözdizimi, bu yöntem başarılı olursa TRUE aşırı yükleme; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Microsoft Outlook stilinde özellik sayfası ise framework gezinti düğmeleri, Outlook bölmesi denetimi özellik sayfasının sol adlı listesini görüntüler. Outlook bölmesi denetimi tarafından kullanılmak üzere görüntü listesinin ayarlamak için bu yöntemi kullanın.

Bu yöntem destekleyen yöntemler hakkında daha fazla bilgi için bkz. [CImageList::Create](../../mfc/reference/cimagelist-class.md#create) ve [CImageList::Add](../../mfc/reference/cimagelist-class.md#add). Bir özellik sayfası stilini ayarlama hakkında daha fazla bilgi için bkz. [CMFCPropertySheet::SetLook](#setlook).

##  <a name="setlook"></a>  CMFCPropertySheet::SetLook

Özellik Sayfası görünümünü belirtir.

```
void SetLook(
    PropSheetLook look,
    int nNavControlWidth=100);
```

### <a name="parameters"></a>Parametreler

*Ara*<br/>
[in] Özellik Sayfası görünümünü belirten numaralandırma değerlerinden biri. Bir özellik sayfası için varsayılan stili `CMFCPropertySheet::PropSheetLook_Tabs`. Daha fazla bilgi için bu konunun Açıklamalar bölümü içindeki tabloya bakın.

*nNavControlWidth*<br/>
[in] Gezinti denetimin piksel cinsinden genişliği. Varsayılan değer 100’dür.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası pencerenin oluşturmadan önce bir özellik sayfası varsayılan dışındaki bir stil görüntülemek için bu yöntemi çağırın.

Aşağıdaki tabloda belirtilebilir numaralandırma değerlerinin *Ara* parametresi.

|Değer|Açıklama|
|-----------|-----------------|
|`CMFCPropertySheet::PropSheetLook_Tabs`|(Varsayılan) Her bir özellik sayfası için bir sekme görüntüler. Sekmeler, özellik sayfasının üst kısmında görüntülenir ve tek bir satırda sığmayacak kadar çok daha fazla sekme varsa yığılır.|
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Microsoft Outlook çubuğu, özellik sayfasının sol tarafında stilini gezinti düğmeleri listesini görüntüler. Listedeki her düğme için bir özellik sayfası karşılık gelir. Liste görünür alanında sığmayacak kadar çok daha fazla düğme varsa framework kaydırma okları görüntüler.|
|`CMFCPropertySheet::PropSheetLook_Tree`|Özellik sayfasının sol tarafta bir ağaç denetimi görüntüler. Ağaç denetimi üst veya alt her düğüme bir özellik sayfasına karşılık gelir. Ağaç denetimi görünür alanında sığmayacak kadar çok daha fazla düğüm varsa framework kaydırma okları görüntüler.|
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Microsoft OneNote stilinde her bir özellik sayfası için bir sekme görüntüler. Framework sekmeleri özellik sayfasının üst kısmında görüntülenir ve kaydırma oklarının değerinden daha fazla sekme varsa tek bir satırda sığacak.|
|`CMFCPropertySheet::PropSheetLook_List`|Özellik sayfasının sol tarafa bir listesini görüntüler. Her liste öğesi, bir özellik sayfasına karşılık gelir. Liste görünür alanında sığmayacak kadar çok daha fazla liste öğesi yoksa framework kaydırma okları görüntüler.|

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyPage Sınıfı](../../mfc/reference/cmfcpropertypage-class.md)<br/>
[CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)
