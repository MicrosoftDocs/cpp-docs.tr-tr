---
description: 'Daha fazla bilgi edinin: CMFCToolBarEditBoxButton sınıfı'
title: CMFCToolBarEditBoxButton sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CanBeStretched
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CopyFrom
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetByCmd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContentsAll
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetEditBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetHwnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetInvalidateRect
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::HaveHotBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::IsFlatMode
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::NotifyCommand
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnAddToCustomizePage
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnChangeParentWnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnClick
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnCtlColor
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnGlobalFontsChanged
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnMove
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnShow
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnSize
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnUpdateToolTip
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetFlatMode
helpviewer_keywords:
- CMFCToolBarEditBoxButton [MFC], CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton [MFC], CanBeStretched
- CMFCToolBarEditBoxButton [MFC], CopyFrom
- CMFCToolBarEditBoxButton [MFC], GetByCmd
- CMFCToolBarEditBoxButton [MFC], GetContentsAll
- CMFCToolBarEditBoxButton [MFC], GetContextMenuID
- CMFCToolBarEditBoxButton [MFC], GetEditBorder
- CMFCToolBarEditBoxButton [MFC], GetHwnd
- CMFCToolBarEditBoxButton [MFC], GetInvalidateRect
- CMFCToolBarEditBoxButton [MFC], HaveHotBorder
- CMFCToolBarEditBoxButton [MFC], IsFlatMode
- CMFCToolBarEditBoxButton [MFC], NotifyCommand
- CMFCToolBarEditBoxButton [MFC], OnAddToCustomizePage
- CMFCToolBarEditBoxButton [MFC], OnChangeParentWnd
- CMFCToolBarEditBoxButton [MFC], OnClick
- CMFCToolBarEditBoxButton [MFC], OnCtlColor
- CMFCToolBarEditBoxButton [MFC], OnGlobalFontsChanged
- CMFCToolBarEditBoxButton [MFC], OnMove
- CMFCToolBarEditBoxButton [MFC], OnShow
- CMFCToolBarEditBoxButton [MFC], OnSize
- CMFCToolBarEditBoxButton [MFC], OnUpdateToolTip
- CMFCToolBarEditBoxButton [MFC], SetContextMenuID
- CMFCToolBarEditBoxButton [MFC], SetFlatMode
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
ms.openlocfilehash: 1cdf401d7ef6409163334104b20d6ce92940f677
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163905"
---
# <a name="cmfctoolbareditboxbutton-class"></a>CMFCToolBarEditBoxButton sınıfı

Bir düzenleme denetimi ( [Cedıt sınıfı](../../mfc/reference/cedit-class.md)) içeren bir araç çubuğu düğmesi.

## <a name="syntax"></a>Syntax

```
class CMFCToolBarEditBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarEditBoxButton:: CMFCToolBarEditBoxButton](#cmfctoolbareditboxbutton)|Bir `CMFCToolBarEditBoxButton` nesnesi oluşturur.|
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarEditBoxButton:: Canbeesnetilen](#canbestretched)|Kullanıcının özelleştirme sırasında düğmeyi uzatılamayacağını belirtir. ( [CMFCToolBarButton:: Canbeesnei](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)geçersiz kılar.)|
|[CMFCToolBarEditBoxButton:: CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesinin özelliklerini geçerli düğmeye kopyalar. ( [CMFCToolBarButton:: CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton:: CreateEdit](#createedit)|Düğmede yeni bir düzenleme denetimi oluşturur.|
|`CMFCToolBarEditBoxButton::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|[CMFCToolBarEditBoxButton:: GetByCmd](#getbycmd)|`CMFCToolBarEditBoxButton`Uygulamadaki belirtilen komut kimliğine sahip ilk nesneyi alır.|
|[CMFCToolBarEditBoxButton:: GetContentsAll](#getcontentsall)|Belirtilen komut KIMLIĞINE sahip olan ilk düzenleme kutusu araç çubuğu denetiminin metnini alır.|
|[CMFCToolBarEditBoxButton:: GetContextMenuID](#getcontextmenuid)|Düğmeyle ilişkili kısayol menüsünün kaynak KIMLIĞINI alır.|
|[CMFCToolBarEditBoxButton:: GetEditBorder](#geteditborder)|Düzenleme kutusu düğmesinin düzenleme bölümünün sınırlayıcı dikdörtgenini alır.|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton:: GetEditBox](#geteditbox)|Düğmeye gömülü olan düzenleme denetimine yönelik bir işaretçi döndürür.|
|[CMFCToolBarEditBoxButton:: GetHwnd](#gethwnd)|Araç çubuğu düğmesiyle ilişkili pencere tanıtıcısını alır. ( [CMFCToolBarButton:: GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).) öğesini geçersiz kılar|
|[CMFCToolBarEditBoxButton:: GetInvalidateRect](#getinvalidaterect)|Yeniden çizilmesi gereken düğmenin istemci alanının bölgesini alır. ( [CMFCToolBarButton:: GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect)geçersiz kılınır.)|
|`CMFCToolBarEditBoxButton::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCToolBarEditBoxButton:: HaveHotBorder](#havehotborder)|Kullanıcı düğmeye tıkladığında düğme kenarlığının görüntülenip görüntülenmeyeceğini belirler. ( [CMFCToolBarButton:: HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder)geçersiz kılar.)|
|[CMFCToolBarEditBoxButton:: ısyataymode](#isflatmode)|Düzenleme kutusu düğmelerinin düz bir stile sahip olup olmadığını belirler.|
|[CMFCToolBarEditBoxButton:: NotifyCommand](#notifycommand)|Düğmenin [WM_COMMAND](/windows/win32/menurc/wm-command) iletisini işlemediğini belirtir. ( [CMFCToolBarButton:: NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).) öğesini geçersiz kılar|
|[CMFCToolBarEditBoxButton:: OnAddToCustomizePage](#onaddtocustomizepage)|Düğme bir **Özelleştirme** iletişim kutusuna eklendiğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).) öğesini geçersiz kılar|
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Belirtilen cihaz bağlamı ve yerleştirme durumu için düğmenin boyutunu hesaplamak üzere Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).) öğesini geçersiz kılar|
|[CMFCToolBarEditBoxButton:: OnChangeParentWnd](#onchangeparentwnd)|Düğme yeni bir araç çubuğuna eklendiğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)geçersiz kılar.)|
|[CMFCToolBarEditBoxButton:: OnClick](#onclick)|Kullanıcı fare düğmesine tıkladığında Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)geçersiz kılar.)|
|[CMFCToolBarEditBoxButton:: OnCtlColor](#onctlcolor)|Ana araç çubuğu bir WM_CTLCOLOR iletisini işlediğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).) öğesini geçersiz kılar|
|`CMFCToolBarEditBoxButton::OnDraw`|Belirtilen stilleri ve seçenekleri kullanarak düğmeyi çizmek için Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw)geçersiz kılar.)|
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|**Özelleştirme** Iletişim kutusunun **Komutlar** bölmesinde düğme çizmek için Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).) öğesini geçersiz kılar|
|[CMFCToolBarEditBoxButton:: OnGlobalFontsChanged](#onglobalfontschanged)|Genel yazı tipi değiştirildiğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)geçersiz kılınır.)|
|[CMFCToolBarEditBoxButton:: OnMove](#onmove)|Ana araç çubuğu taşırken Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)geçersiz kılar.)|
|[CMFCToolBarEditBoxButton:: OnShow](#onshow)|Düğme görünür veya görünmez hale geldiğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).) öğesini geçersiz kılar|
|[CMFCToolBarEditBoxButton:: OnSize](#onsize)|Ana araç çubuğu boyutunu veya konumunu değiştirdiğinde Framework tarafından çağırılır ve bu değişiklik düğmenin boyutunu değiştirmesine neden olur. ( [CMFCToolBarButton:: OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)geçersiz kılar.)|
|[CMFCToolBarEditBoxButton:: OnUpdateToolTip](#onupdatetooltip)|Ana araç çubuğu kendi araç ipucu metnini güncelleştirdiğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)' i geçersiz kılar.)|
|`CMFCToolBarEditBoxButton::Serialize`|Bu nesneyi bir arşivden okur veya bir arşive yazar. ( [CMFCToolBarButton:: Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)geçersiz kılar.)|
|`CMFCToolBarEditBoxButton::SetACCData`|`CAccessibilityData`Araç çubuğu düğmesinden, belirtilen nesneyi erişilebilirlik verileriyle doldurur. ( [CMFCToolBarButton:: SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata)geçersiz kılar.)|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton:: SetContents](#setcontents)|Düğmenin düzenleme denetimindeki metni ayarlar.|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton:: SetContentsAll](#setcontentsall)|Belirtilen komut KIMLIĞINE sahip olan düzenleme denetimi düğmesini bulur ve bu düğmenin düzenleme denetimindeki metni ayarlar.|
|[CMFCToolBarEditBoxButton:: SetContextMenuID](#setcontextmenuid)|Düğmeyle ilişkili kısayol menüsünün kaynak KIMLIĞINI belirtir.|
|[CMFCToolBarEditBoxButton:: Setyataymod](#setflatmode)|Uygulamadaki düzenleme kutusu düğmelerinin düz stil görünümünü belirtir.|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton:: SetStyle](#setstyle)|Düğmenin stilini belirtir. ( [CMFCToolBarButton:: SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle)geçersiz kılar)|

## <a name="remarks"></a>Açıklamalar

Bir araç çubuğuna düzenleme kutusu düğmesi eklemek için aşağıdaki adımları izleyin:

1. Ana araç çubuğu kaynağında düğme için bir kukla kaynak KIMLIĞI ayırın.

2. Bir `CMFCToolBarEditBoxButton` nesne oluşturun.

3. AFX_WM_RESETTOOLBAR iletisini işleyen ileti işleyicisinde, [CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)öğesini kullanarak kukla düğmesini Yeni Birleşik giriş kutusu düğmesiyle değiştirin.

Daha fazla bilgi için bkz. [Izlenecek yol: denetimleri araç çubuklarına yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir `CMFCToolBarEditBoxButton` . Örnek, özelleştirme sırasında bir kullanıcının düğmeyi ne şekilde uzatılabildiği gösterilmektedir, Kullanıcı düğmeye tıkladığında düğme kenarlığının görüntülendiğini, metin kutusu denetimindeki metni ayarlamanıza, uygulamadaki düzenleme kutusu düğmelerinin düz stil görünümünü belirtmesini ve bir araç çubuğu düzenleme kutusu denetiminin stilini belirtmenize olanak sağlar.

[!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

`CMFCToolBarEditBoxButton`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbareditboxbutton. h

## <a name="cmfctoolbareditboxbuttoncanbestretched"></a><a name="canbestretched"></a> CMFCToolBarEditBoxButton:: Canbeesnetilen

Kullanıcının özelleştirme sırasında düğmeyi uzatılamayacağını belirtir.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, çerçeve özelleştirme sırasında kullanıcının bir araç çubuğu düğmesini uzamasına izin vermez. Bu yöntem, kullanıcının özelleştirme sırasında bir düzenleme kutusu araç çubuğu düğmesini genişlemesine izin vererek temel sınıf uygulamasını ( [CMFCToolBarButton:: Canbeınesne)](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)genişletir.

## <a name="cmfctoolbareditboxbuttoncmfctoolbareditboxbutton"></a><a name="cmfctoolbareditboxbutton"></a> CMFCToolBarEditBoxButton:: CMFCToolBarEditBoxButton

[CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) nesnesi oluşturur.

```
CMFCToolBarEditBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=ES_AUTOHSCROLL,
    int iWidth=0);
```

### <a name="parameters"></a>Parametreler

*Uııd*<br/>
'ndaki Denetim KIMLIĞINI belirtir.

*IImage*<br/>
'ndaki Bir araç çubuğu görüntüsünün sıfır tabanlı dizinini belirtir. Resim, [CMFCToolBar sınıf](../../mfc/reference/cmfctoolbar-class.md) sınıfının tuttuğu [CMFCToolBarImages sınıfı](../../mfc/reference/cmfctoolbarimages-class.md) nesnesinde bulunur.

*dwStyle*<br/>
'ndaki Düzenleme denetim stilini belirtir.

*ıwidth*<br/>
'ndaki Düzenleme denetiminin piksel cinsinden genişliğini belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu, düzenleme denetim stilini aşağıdaki bileşime ayarlar:

WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL

Denetimin varsayılan genişliği 150 pikseldir.

## <a name="cmfctoolbareditboxbuttoncopyfrom"></a><a name="copyfrom"></a> CMFCToolBarEditBoxButton:: CopyFrom

Başka bir araç çubuğu düğmesinin özelliklerini geçerli düğmeye kopyalar.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
'ndaki Kopyalanacak kaynak düğmesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu araç çubuğu düğmesine başka bir araç çubuğu düğmesi kopyalamak için bu yöntemi çağırın. *src* türünde olmalıdır `CMFCToolBarEditBoxButton` .

## <a name="cmfctoolbareditboxbuttoncreateedit"></a><a name="createedit"></a> CMFCToolBarEditBoxButton:: CreateEdit

Düğmede yeni bir düzenleme denetimi oluşturur.

```
virtual CEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Düzenleme denetiminin üst penceresini belirtir. NULL olmaması gerekir.

*Rect*<br/>
'ndaki Düzenleme denetiminin boyutunu ve konumunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan düzenleme denetimine yönelik bir işaretçi; denetimin oluşturulması ve eki başarısız olursa bu NULL olur.

### <a name="remarks"></a>Açıklamalar

`CMFCToolBarEditBoxButton`İki adımda bir nesne oluşturursunuz. Önce oluşturucuyu çağırın ve sonra `CreateEdit` Windows düzenleme denetimini oluşturan ve bunu nesnesine ekleyen çağırın `CMFCToolBarEditBoxButton` .

## <a name="cmfctoolbareditboxbuttongetbycmd"></a><a name="getbycmd"></a> CMFCToolBarEditBoxButton:: GetByCmd

`CMFCToolBarEditBoxButton`Uygulamadaki belirtilen komut kimliğine sahip ilk nesneyi alır.

```
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Alınacak düğmenin komut KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

`CMFCToolBarEditBoxButton`Uygulamada belirtilen komut kimliğine sahip olan ilk nesne veya böyle bir nesne yoksa null.

### <a name="remarks"></a>Açıklamalar

Bu paylaşılan yardımcı program yöntemi [CMFCToolBarEditBoxButton:: SetContentsAll](#setcontentsall) ve [CMFCToolBarEditBoxButton:: GetContentsAll](#getcontentsall) gibi yöntemler tarafından, belirtilen komut kimliğine sahip ilk düzenleme kutusu araç çubuğu denetiminin metnini ayarlamak ya da almak için kullanılır.

## <a name="cmfctoolbareditboxbuttongetcontentsall"></a><a name="getcontentsall"></a> CMFCToolBarEditBoxButton:: GetContentsAll

Belirtilen komut KIMLIĞINE sahip olan ilk düzenleme kutusu araç çubuğu denetiminin metnini alır.

```
static CString __stdcall GetContentsAll(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki İçeriğin alınacağı düğmenin komut KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

`CString`Belirtilen komut kimliğine sahip olan ilk düzenleme kutusu araç çubuğu denetiminin metnini içeren nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, hiçbir `CMFCToolBarEditBoxButton` nesne belirtilen komut kimliğine sahip değilse boş dizeyi döndürür.

## <a name="cmfctoolbareditboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a> CMFCToolBarEditBoxButton:: GetContextMenuID

Düğmeyle ilişkili kısayol menüsünün kaynak KIMLIĞINI alır.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin ilişkili kısayol menüsü yoksa, düğme veya 0 ile ilişkili kısayol menüsünün kaynak KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Çerçeve, düğmeye sağ tıkladığı zaman kısayol menüsünü oluşturmak için kaynak KIMLIĞINI kullanır.

## <a name="cmfctoolbareditboxbuttongeteditborder"></a><a name="geteditborder"></a> CMFCToolBarEditBoxButton:: GetEditBorder

Düzenleme kutusu düğmesinin düzenleme bölümünün sınırlayıcı dikdörtgenini alır.

```
virtual void GetEditBorder(CRect& rectBorder);
```

### <a name="parameters"></a>Parametreler

*rectBorder*<br/>
dışı `CRect` Sınırlayıcı dikdörtgeni alan nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, istemci koordinatlarındaki düzenleme denetiminin sınırlayıcı dikdörtgenini alır. Dikdörtgenin boyutunu her yönde bir piksel genişletir.

[CMFCVisualManager:: OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) yöntemi bir nesne etrafında kenarlık çizerken bu yöntemi çağırır `CMFCToolBarEditBoxButton` .

## <a name="cmfctoolbareditboxbuttongeteditbox"></a><a name="geteditbox"></a> CMFCToolBarEditBoxButton:: GetEditBox

Düğmeye gömülü olan [CEdit sınıf](../../mfc/reference/cedit-class.md) denetimine bir işaretçi döndürür.

```
CEdit* GetEditBox() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin içerdiği [Cedıt sınıfı](../../mfc/reference/cedit-class.md) denetimine yönelik bir işaretçi. `CEdit`Denetim henüz OLUŞTURULMADıYSA null olur.

### <a name="remarks"></a>Açıklamalar

Bu `CEdit` denetimi [CMFCToolBarEditBoxButton:: CreateEdit](#createedit)çağırarak oluşturursunuz.

## <a name="cmfctoolbareditboxbuttongethwnd"></a><a name="gethwnd"></a> CMFCToolBarEditBoxButton:: GetHwnd

Araç çubuğu düğmesiyle ilişkili pencere tanıtıcısını alır.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmeyle ilişkilendirilen pencere tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, düzenleme kutusu düğmesinin düzenleme denetimi bölümünün pencere tanıtıcısını döndürerek [CMFCToolBarButton:: GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) yöntemini geçersiz kılar.

## <a name="cmfctoolbareditboxbuttongetinvalidaterect"></a><a name="getinvalidaterect"></a> CMFCToolBarEditBoxButton:: GetInvalidateRect

Yeniden çizilmesi gereken düğmenin istemci alanının bölgesini alır.

```
virtual const CRect GetInvalidateRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeniden `CRect` çizilmesi gereken bölgeyi belirten nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, metin etiketinin bölgesine dahil ederek, [CMFCToolBarButton:: GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect)temel sınıf uygulamasını genişletir.

## <a name="cmfctoolbareditboxbuttonhavehotborder"></a><a name="havehotborder"></a> CMFCToolBarEditBoxButton:: HaveHotBorder

Kullanıcı düğmeye tıkladığında düğme kenarlığının görüntülenip görüntülenmeyeceğini belirler.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili olduğunda bir düğme kenarlığını görüntülüyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetim görünür durumdaysa sıfır dışında bir değer döndürerek, [CMFCToolBarButton:: HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder)temel sınıf uygulamasını genişletir.

## <a name="cmfctoolbareditboxbuttonisflatmode"></a><a name="isflatmode"></a> CMFCToolBarEditBoxButton:: ısyataymode

Düzenleme kutusu düğmelerinin düz bir stile sahip olup olmadığını belirler.

```
static BOOL __stdcall IsFlatMode();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmelerin düz bir stili varsa sıfır dışı; Aksi takdirde, 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, düzenleme kutusu düğmelerinin düz bir stili vardır. Uygulamanızın düz stil görünümünü değiştirmek için [CMFCToolBarEditBoxButton:: Setyataymode](#setflatmode) metodunu kullanın.

## <a name="cmfctoolbareditboxbuttonnotifycommand"></a><a name="notifycommand"></a> CMFCToolBarEditBoxButton:: NotifyCommand

Düğmenin [WM_COMMAND](/windows/win32/menurc/wm-command) iletisini işlemediğini belirtir.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parametreler

*iNotifyCode*<br/>
'ndaki Komutuyla ilişkili bildirim iletisi.

### <a name="return-value"></a>Dönüş Değeri

Düğme WM_COMMAND iletisini işliyorsa TRUE, iletinin üst araç çubuğu tarafından işlenmesi gerektiğini belirtmek için FALSE.

### <a name="remarks"></a>Açıklamalar

Framework, ana pencereye bir [WM_COMMAND](/windows/win32/menurc/wm-command) iletisi göndermek üzere olduğunda bu yöntemi çağırır.

Bu yöntem, [EN_UPDATE](/windows/win32/Controls/en-update) bildirimini işleyerek temel sınıf uygulamasını ( [CMFCToolBarButton:: NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) genişletir. Bu nesneyle aynı komut KIMLIĞINE sahip her bir düzenleme kutusu için, metin etiketini bu nesnenin metin etiketine ayarlar.

## <a name="cmfctoolbareditboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a> CMFCToolBarEditBoxButton:: OnAddToCustomizePage

Düğme bir **Özelleştirme** iletişim kutusuna eklendiğinde Framework tarafından çağırılır.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, özellikleri bu nesneyle aynı komut KIMLIĞINE sahip olan herhangi bir araç çubuğunda düzenleme kutusu denetiminden kopyalayarak temel sınıf uygulamasını ( [CMFCToolBarButton:: OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) genişletir. Bu yöntem, bir araç çubuğunun aynı komut KIMLIĞINE sahip bir düzenleme kutusu denetimine sahip olmadığı hiçbir şey yapmaz.

**Özelleştirme** iletişim kutusu hakkında daha fazla bilgi için bkz. [CMFCToolBarsCustomizeDialog Class](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

## <a name="cmfctoolbareditboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a> CMFCToolBarEditBoxButton:: OnChangeParentWnd

Düğme yeni bir araç çubuğuna eklendiğinde Framework tarafından çağırılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Yeni ana pencereye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç nesneyi yeniden oluşturarak temel sınıf uygulamasını ( [CMFCToolBarButton:: OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) geçersiz kılar `CEdit` .

## <a name="cmfctoolbareditboxbuttononclick"></a><a name="onclick"></a> CMFCToolBarEditBoxButton:: OnClick

Kullanıcı fare düğmesine tıkladığında Framework tarafından çağırılır.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Kullanılmayan.

*bDelay*<br/>
'ndaki Kullanılmayan.

### <a name="return-value"></a>Dönüş Değeri

Düğme tıklama iletisini işliyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç nesne görünür durumdaysa sıfır dışında bir değer döndürerek temel sınıf uygulamasını ( [CMFCToolBarButton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)) geçersiz kılar `CEdit` .

## <a name="cmfctoolbareditboxbuttononctlcolor"></a><a name="onctlcolor"></a> CMFCToolBarEditBoxButton:: OnCtlColor

Ana araç çubuğu bir WM_CTLCOLOR iletisini işlediğinde Framework tarafından çağırılır.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Düğmeyi görüntüleyen cihaz bağlamı.

*nCtlColor*<br/>
'ndaki Kullanılmayan.

### <a name="return-value"></a>Dönüş Değeri

Genel pencere fırçasının bir tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen cihaz bağlamının metin ve arka plan renklerini sırasıyla genel metin ve arka plan renkleriyle ayarlayarak temel sınıf uygulamasını ( [CMFCToolBarButton:: OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)) geçersiz kılar.

Uygulamanız için kullanılabilen genel seçenekler hakkında daha fazla bilgi için bkz. [AFX_GLOBAL_DATA yapısı](../../mfc/reference/afx-global-data-structure.md).

## <a name="cmfctoolbareditboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a> CMFCToolBarEditBoxButton:: OnGlobalFontsChanged

Genel yazı tipi değiştirildiğinde Framework tarafından çağırılır.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetimin yazı tipini genel yazı tipi ile değiştirerek temel sınıf uygulamasını ( [CMFCToolBarButton:: OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) genişletir.

Uygulamanız için kullanılabilen genel seçenekler hakkında daha fazla bilgi için bkz. [AFX_GLOBAL_DATA yapısı](../../mfc/reference/afx-global-data-structure.md).

## <a name="cmfctoolbareditboxbuttononmove"></a><a name="onmove"></a> CMFCToolBarEditBoxButton:: OnMove

Ana araç çubuğu taşırken Framework tarafından çağırılır.

```
virtual void OnMove();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç nesnenin konumunu güncelleştirerek varsayılan sınıf uygulamasını ( [CMFCToolBarButton:: OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) geçersiz kılar `CEdit`

## <a name="cmfctoolbareditboxbuttononshow"></a><a name="onshow"></a> CMFCToolBarEditBoxButton:: OnShow

Düğme görünür veya görünmez hale geldiğinde Framework tarafından çağırılır.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
'ndaki Düğmenin görünür olup olmadığını belirtir. Bu parametre TRUE ise, düğme görünür olur. Aksi takdirde, düğme görünür değildir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *BSHOW* true ise düğmeyi görüntüleyerek temel sınıf uygulamasını ( [CMFCToolBarButton:: OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) genişletir. Aksi takdirde, bu yöntem düğmeyi gizler.

## <a name="cmfctoolbareditboxbuttononsize"></a><a name="onsize"></a> CMFCToolBarEditBoxButton:: OnSize

Ana araç çubuğu boyutunu veya konumunu değiştirdiğinde Framework tarafından çağırılır ve bu değişiklik düğmenin boyutunu değiştirmesine neden olur.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parametreler

*iSize*<br/>
'ndaki Düğmenin piksel cinsinden yeni genişliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç nesnenin boyutunu ve konumunu güncelleştirerek [CMFCToolBarButton:: OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)varsayılan sınıf uygulamasını geçersiz kılar `CEdit` .

## <a name="cmfctoolbareditboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a> CMFCToolBarEditBoxButton:: OnUpdateToolTip

Ana araç çubuğu kendi araç ipucu metnini güncelleştirdiğinde Framework tarafından çağırılır.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Kullanılmayan.

*ıbuttonındex*<br/>
'ndaki Kullanılmayan.

*wndToolTip*<br/>
'ndaki Araç ipucu metnini görüntüleyen denetim.

*üstbilgisine*<br/>
dışı `CString` Güncelleştirilmiş araç ipucu metnini alan nesne.

### <a name="return-value"></a>Dönüş Değeri

Yöntem araç ipucu metnini güncelleştirse sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, düğmenin düzenleme bölümüyle ilişkili araç ipucu metnini görüntüleyerek temel sınıf uygulamasını ( [CMFCToolBarButton:: OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) genişletir. İç `CEdit` nesne null ise veya nesnenin pencere tutamacı `CEdit` varolan bir pencereyi tanımlamaz, bu yöntem hiçbir şey yapmaz ve false döndürür.

## <a name="cmfctoolbareditboxbuttonsetcontents"></a><a name="setcontents"></a> CMFCToolBarEditBoxButton:: SetContents

Metin kutusu denetimindeki metni ayarlar.

```
virtual void SetContents(const CString& sContents);
```

### <a name="parameters"></a>Parametreler

*sContents*<br/>
'ndaki Ayarlanacak yeni metni belirtir.

## <a name="cmfctoolbareditboxbuttonsetcontentsall"></a><a name="setcontentsall"></a> CMFCToolBarEditBoxButton:: SetContentsAll

Belirtilen komut KIMLIĞINE sahip bir [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) nesnesi bulur ve metin kutusu içinde belirtilen metni ayarlar.

```
static BOOL SetContentsAll(
    UINT uiCmd,
    const CString& strContents);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Metnin değiştirildiği denetimin komut KIMLIĞINI belirtir.

*strContents*<br/>
'ndaki Ayarlanacak yeni metni belirtir.

### <a name="return-value"></a>Dönüş Değeri

Metin ayarlandıysa sıfır dışı; `CMFCToolBarEditBoxButton` belirtilen komut kimliğine sahip denetim yoksa 0.

## <a name="cmfctoolbareditboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a> CMFCToolBarEditBoxButton:: SetContextMenuID

Düğmeyle ilişkili kısayol menüsünün kaynak KIMLIĞINI belirtir.

```cpp
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Kısayol menüsünün kaynak KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Çerçeve, Kullanıcı araç çubuğu düğmesine sağ tıkladığında kısayol menüsünü oluşturmak için kaynak KIMLIĞINI kullanır.

## <a name="cmfctoolbareditboxbuttonsetflatmode"></a><a name="setflatmode"></a> CMFCToolBarEditBoxButton:: Setyataymod

Uygulamadaki düzenleme kutusu düğmelerinin düz stil görünümünü belirtir.

```
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```

### <a name="parameters"></a>Parametreler

*bFlat*<br/>
'ndaki Düzenleme kutusu düğmelerinin düz stili. Bu parametre TRUE ise düz stil görünümü etkinleştirilir; Aksi halde düz stil görünümü devre dışıdır.

### <a name="remarks"></a>Açıklamalar

Düzenleme kutusu düğmelerinin varsayılan düz stili doğru. Uygulamanızın düz stil görünümünü almak için [CMFCToolBarEditBoxButton:: ısyataymode](#isflatmode) metodunu kullanın.

## <a name="cmfctoolbareditboxbuttonsetstyle"></a><a name="setstyle"></a> CMFCToolBarEditBoxButton:: SetStyle

Bir araç çubuğu düzenleme kutusu denetiminin stilini belirtir.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
'ndaki Ayarlanacak yeni bir stil.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CMFCToolBarButton:: M_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) *nStyle* 'a ayarlar ve uygulama özelleştirme modundayken metin kutusunu devre dışı bırakır ve uygulama özelleştirme modunda olmadığında bunu sağlar (bkz. [CMFCToolBar:: SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) ve [CMFCToolBar:: IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). Geçerli stil bayrakları listesi için bkz. [ToolBar denetim stilleri](../../mfc/reference/toolbar-control-styles.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Cedıt sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[İzlenecek yol: araç çubuklarına denetimler yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
