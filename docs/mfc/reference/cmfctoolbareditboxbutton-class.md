---
title: CMFCToolBarEditBoxButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a346cf75a0afebcfdcb31259a0ba72d3a8f6c22
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397331"
---
# <a name="cmfctoolbareditboxbutton-class"></a>CMFCToolBarEditBoxButton sınıfı

Bir düzenleme denetimi içeren bir araç çubuğu düğmesi ( [CEdit sınıfı](../../mfc/reference/cedit-class.md)).

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarEditBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](#cmfctoolbareditboxbutton)|Oluşturur bir `CMFCToolBarEditBoxButton` nesne.|
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|Bir kullanıcı, düğme özelleştirme sırasında esnetme olup olmadığını belirtir. (Geçersiz kılmaları [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesi özelliklerini geçerli düğmeyi kopyalar. (Geçersiz kılmaları [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::CreateEdit](#createedit)|Yeni bir düzenleme denetimi düğmesi oluşturur.|
|`CMFCToolBarEditBoxButton::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|İlk alır `CMFCToolBarEditBoxButton` belirtilen komut kimliği olan bir uygulama nesnesi|
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|Belirtilen komut kimliği olduğundan ilk düzenleme kutusu araç çubuğu denetimi metnini alır.|
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|Kısayol menüsünün düğmesi ile ilişkili kaynak Kimliğini alır.|
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|Düzenleme kutusu düğmesi düzenleme parçası sınırlayıcı dikdörtgenini alır.|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|Düğmeye katıştırılmış düzenleme denetimi için bir işaretçi döndürür.|
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|Araç çubuğu düğmesi ile ilişkili olan bir pencere tutucu alır. (Geçersiz kılmaları [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|Bölge çizilmesini gerekir düğmenin istemci alanının alır. (Geçersiz kılmaları [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|
|`CMFCToolBarEditBoxButton::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|Bir kullanıcı düğmeye tıkladığında düğmenin kenarlık görüntülenip görüntülenmeyeceğini belirler. (Geçersiz kılmaları [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|Düzenleme kutusu düğmeleri, düz bir stil sahip olup olmadığını belirler.|
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|Düğme işler olup olmadığını belirtir [WM_COMMAND](/windows/desktop/menurc/wm-command) ileti. (Geçersiz kılmaları [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|Framework tarafından düğmenin eklendiğinde çağırılır bir **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Yerleştirme durumu ve belirtilen bir cihaz bağlamı için düğmenin boyutunu hesaplamak için framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|Yeni bir araç çubuğu düğmesi eklendiğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|Kullanıcı fare düğmesine tıkladığında framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|Üst araç çubuğunda WM_CTLCOLOR iletisi işlediğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarEditBoxButton::OnDraw`|Belirtilen stillerini ve seçeneklerini kullanarak bir düğme çizmek için framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Düğme çizim için framework tarafından çağırılır **komutları** bölmesinde **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|Genel yazı tipi değiştiğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|Üst araç çubuğunda hareket ettiğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|Düğme olduğunda görünür veya gizli framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|Üst araç çubuğunda boyutunu değiştirir veya konumu ve bu değişiklik neden boyutunu değiştirmek düğmeyi framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|Üst araç çubuğunda, araç ipucu metni güncelleştirdiğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarEditBoxButton::Serialize`|Bu nesne bir arşivden okur veya arşive yazar. (Geçersiz kılmaları [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarEditBoxButton::SetACCData`|Sağlanan doldurur `CAccessibilityData` araç çubuğu düğmesinden erişilebilirlik veri nesnesi. (Geçersiz kılmaları [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContents](#setcontents)|Düğmenin düzenleme denetiminde metin ayarlar.|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|Belirtilen komut kimliği ve söz konusu düğmenin düzenleme denetiminde metni ayarlar Düzenle denetim düğmesine bulur.|
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|Kısayol menüsünün düğmesi ile ilişkili kaynak Kimliğini belirtir.|
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|Uygulamayı düzenleme kutusu düğmeleri düz stil görünümünü belirler.|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetStyle](#setstyle)|Düğmenin stilini belirtir. (Geçersiz kılmaları [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|

## <a name="remarks"></a>Açıklamalar

Araç çubuğuna bir düzenleme kutusu düğmesi eklemek için aşağıdaki adımları izleyin:

1. Üst araç çubuğunda kaynağında düğme için bir işlevsiz kaynak kimliği saklı tutarız.

2. Oluşturmak bir `CMFCToolBarEditBoxButton` nesne.

3. AFX_WM_RESETTOOLBAR iletiyi işleyen ileti işleyicisi işlevsiz düğmesini kullanarak yeni bir birleşik giriş kutusu düğmesi ile değiştirin [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

Daha fazla bilgi için [izlenecek yol: temel denetimler koyma araç'çubukları](../../mfc/walkthrough-putting-controls-on-toolbars.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCToolBarEditBoxButton` sınıfı. Örnek, belirtmek bir kullanıcı düğme özelleştirme sırasında esnetme, kullanıcı düğmeye tıkladığında düğmenin kenarlık görüntüleneceğini belirtmek, metin kutusu denetiminde metni ayarlama Uy içinde düzenleme kutusu düğmeleri düz stil görünümünü belirtmek, nasıl gösterir Uygulama, bir araç çubuğunun stil düzenleme kutusu denetimi belirtin.

[!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

`CMFCToolBarEditBoxButton`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtoolbareditboxbutton.h

##  <a name="canbestretched"></a>  CMFCToolBarEditBoxButton::CanBeStretched

Bir kullanıcı, düğme özelleştirme sırasında esnetme olup olmadığını belirtir.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem, TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, çerçeve sırasında özelleştirme araç çubuğu düğmesi uzatmak kullanıcı izin vermiyor. Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) kullanıcının bir düzenleme kutusu araç çubuğu düğmesi özelleştirme sırasında esnetme sağlayarak.

##  <a name="cmfctoolbareditboxbutton"></a>  CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton

Oluşturur bir [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) nesne.

```
CMFCToolBarEditBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=ES_AUTOHSCROLL,
    int iWidth=0);
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[in] Denetim kimliğini belirtir.

*iImage*<br/>
[in] Bir araç çubuğu görüntüsü sıfır tabanlı dizini belirtir. Görüntüsü bulunan [Cmfctoolbarımages sınıfı](../../mfc/reference/cmfctoolbarimages-class.md) nesnesinin [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md) sınıfı tutar.

*dwStyle*<br/>
[in] Düzenleme denetiminin stilini belirtir.

*iWidth*<br/>
[in] Düzenleme denetiminin piksel cinsinden genişliğini belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu aşağıdaki birleşimi için düzenleme denetiminin stilini ayarlar:

WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL

Denetimin varsayılan genişliğini 150 pikseldir.

##  <a name="copyfrom"></a>  CMFCToolBarEditBoxButton::CopyFrom

Başka bir araç çubuğu düğmesi özelliklerini geçerli düğmeyi kopyalar.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[in] Kopyalanacak kaynak düğmesini başvuru.

### <a name="remarks"></a>Açıklamalar

Bu araç çubuğu düğmesi için başka bir araç çubuğu düğmesini kopyalama için bu yöntemi çağırın. *src* türünde olmalıdır `CMFCToolBarEditBoxButton`.

##  <a name="createedit"></a>  CMFCToolBarEditBoxButton::CreateEdit

Yeni bir düzenleme denetimi düğmesi oluşturur.

```
virtual CEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[in] Düzenleme denetiminin üst penceresine belirtir. NULL olmamalıdır.

*Rect*<br/>
[in] Düzenleme denetiminin boyutunu ve konumunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan düzenleme denetimi için bir işaretçi; Denetim oluşturma ve ek başarısız olursa NULL ise.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CMFCToolBarEditBoxButton` iki adımda nesne. İlk oluşturucusunu çağırın ve ardından arama `CreateEdit`, hangi Windows düzenleme denetimi oluşturur ve ona ekler `CMFCToolBarEditBoxButton` nesne.

##  <a name="getbycmd"></a>  CMFCToolBarEditBoxButton::GetByCmd

İlk alır `CMFCToolBarEditBoxButton` belirtilen komut kimliği olan bir uygulama nesnesi

```
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[in] Komut Kimliği Al düğmesi.

### <a name="return-value"></a>Dönüş Değeri

İlk `CMFCToolBarEditBoxButton` böyle bir nesne varsa, belirtilen komut kimliği ya da NULL olan uygulama nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu paylaşılan yardımcı yöntem gibi yöntemler tarafından kullanılan [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall) ve [CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall) ayarlayın veya ilk düzenleme kutusu araç metnini almak için Belirtilen komut kimliği olan denetim

##  <a name="getcontentsall"></a>  CMFCToolBarEditBoxButton::GetContentsAll

Belirtilen komut kimliği olduğundan ilk düzenleme kutusu araç çubuğu denetimi metnini alır.

```
static CString __stdcall GetContentsAll(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[in] Düğme içeriğinin alınacağı komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

A `CString` belirtilen komut kimliği olduğundan ilk düzenleme kutusu araç çubuğu denetiminin metin içeren nesne

### <a name="remarks"></a>Açıklamalar

Hayır ise bu yöntem boş bir dize döndürür `CMFCToolBarEditBoxButton` nesneler sahip belirtilen komut kimliği.

##  <a name="getcontextmenuid"></a>  CMFCToolBarEditBoxButton::GetContextMenuID

Kısayol menüsünün düğmesi ile ilişkili kaynak Kimliğini alır.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Dönüş Değeri

İlişkili kısayol menüsü düğmesi varsa, düğme veya 0 ile ilişkili kısayol menüsü kaynak kimliği.

### <a name="remarks"></a>Açıklamalar

Framework, kullanıcı düğmeye tıkladığında kısayolunu oluşturmak için kaynak Kimliğini kullanır.

##  <a name="geteditborder"></a>  CMFCToolBarEditBoxButton::GetEditBorder

Düzenleme kutusu düğmesi düzenleme parçası sınırlayıcı dikdörtgenini alır.

```
virtual void GetEditBorder(CRect& rectBorder);
```

### <a name="parameters"></a>Parametreler

*rectBorder*<br/>
[out] Bir başvuru `CRect` dikdörtgen alan nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem istemci koordinatları düzenleme denetiminin sınırlayıcı dikdörtgeni alır. Bu, bir piksel boyutunu her yönde bir dikdörtgen genişletir.

[CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) çevresinde kenarlık çizdiğinde yöntemi çağıran bu yöntem bir `CMFCToolBarEditBoxButton` nesne.

##  <a name="geteditbox"></a>  CMFCToolBarEditBoxButton::GetEditBox

Bir işaretçi döndürür [CEdit sınıfı](../../mfc/reference/cedit-class.md) düğmesini katıştırılmış denetimi.

```
CEdit* GetEditBox() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi [CEdit sınıfı](../../mfc/reference/cedit-class.md) düğmesi içeren denetimi. Bu NULL ise `CEdit` denetim henüz oluşturulmadı.

### <a name="remarks"></a>Açıklamalar

Oluşturduğunuz `CEdit` çağırarak denetim [CMFCToolBarEditBoxButton::CreateEdit](#createedit).

##  <a name="gethwnd"></a>  CMFCToolBarEditBoxButton::GetHwnd

Araç çubuğu düğmesi ile ilişkili olan bir pencere tutucu alır.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Dönüş Değeri

Düğme ile ilişkili pencere tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Bu metot geçersiz kılmaları [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) düzenleme kutusu düğmesi düzenleme denetimi parçası pencere tanıtıcısı döndürerek yöntemi.

##  <a name="getinvalidaterect"></a>  CMFCToolBarEditBoxButton::GetInvalidateRect

Bölge çizilmesini gerekir düğmenin istemci alanının alır.

```
virtual const CRect GetInvalidateRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `CRect` çizilmesini gerekir bölgeyi belirten bir nesne.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu yöntemin genişlettiği [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect), metin etiketi alanının bölgede ekleyerek.

##  <a name="havehotborder"></a>  CMFCToolBarEditBoxButton::HaveHotBorder

Bir kullanıcı düğmeye tıkladığında düğmenin kenarlık görüntülenip görüntülenmeyeceğini belirler.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir düğme seçildiğinde kenarlığını görüntüler olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu yöntemin genişlettiği [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), denetimin görünür olması halinde bir sıfır dışında bir değeri döndürerek.

##  <a name="isflatmode"></a>  CMFCToolBarEditBoxButton::IsFlatMode

Düzenleme kutusu düğmeleri, düz bir stil sahip olup olmadığını belirler.

```
static BOOL __stdcall IsFlatMode();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmeleri düz bir stil varsa sıfır; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, düz bir stil düzenleme kutusu düğmeleri sahiptir. Kullanım [CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode) , uygulamanızın düz stil görünümünü değiştirmek için yöntemi.

##  <a name="notifycommand"></a>  CMFCToolBarEditBoxButton::NotifyCommand

Düğme işler olup olmadığını belirtir [WM_COMMAND](/windows/desktop/menurc/wm-command) ileti.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parametreler

*iNotifyCode*<br/>
[in] Komutu ile ilişkili bir uyarı iletisi.

### <a name="return-value"></a>Dönüş Değeri

WM_COMMAND ileti veya yanlış ileti üst araç tarafından işlenmesi gerektiğini belirtmek için düğmeyi işler TRUE.

### <a name="remarks"></a>Açıklamalar

Göndermek üzere olduğunda framework bu yöntemi çağıran bir [WM_COMMAND](/windows/desktop/menurc/wm-command) üst penceresine ileti.

Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) işleme tarafından [EN_UPDATE](/windows/desktop/Controls/en-update) bildirim. Bu nesne olarak aynı komutu kimlikli her düzenleme kutusu için bu nesne için metin etiketi metin etiketini ayarlar.

##  <a name="onaddtocustomizepage"></a>  CMFCToolBarEditBoxButton::OnAddToCustomizePage

Framework tarafından düğmenin eklendiğinde çağırılır bir **Özelleştir** iletişim kutusu.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) özelliklerini bu nesneninkiyle aynı komutu Kimliğine sahip herhangi bir araç çubuğu düzenleme kutusu denetiminde kopyalayarak. Bu yöntem, bu nesne olarak aynı komutu Kimliğine sahip bir düzenleme kutusu denetimi araç çubuğu yok varsa, hiçbir şey yapmaz.

Hakkında daha fazla bilgi için **Özelleştir** iletişim kutusu, bkz: [CMFCToolBarsCustomizeDialog sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

##  <a name="onchangeparentwnd"></a>  CMFCToolBarEditBoxButton::OnChangeParentWnd

Yeni bir araç çubuğu düğmesi eklendiğinde framework tarafından çağırılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[in] Yeni üst penceresine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu metodu geçersiz kılar ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) iç yeniden tarafından `CEdit` nesne.

##  <a name="onclick"></a>  CMFCToolBarEditBoxButton::OnClick

Kullanıcı fare düğmesine tıkladığında framework tarafından çağırılır.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
[in] Kullanılmayan.

*bDelay*<br/>
[in] Kullanılmayan.

### <a name="return-value"></a>Dönüş Değeri

Düğmenin click iletiyi işler olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu metodu geçersiz kılar ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)) ise sıfır olmayan bir değer döndürerek iç `CEdit` nesne görünür.

##  <a name="onctlcolor"></a>  CMFCToolBarEditBoxButton::OnCtlColor

Üst araç çubuğunda WM_CTLCOLOR iletisi işlediğinde framework tarafından çağırılır.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Düğme görüntüler cihaz bağlamı.

*nCtlColor*<br/>
[in] Kullanılmayan.

### <a name="return-value"></a>Dönüş Değeri

Genel pencere fırçasına tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu metodu geçersiz kılar ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)) genel metin ve arka plan renkleri için sağlanan cihaz bağlamının metin ve arkaplan renklerini sırasıyla ayarlayarak.

Uygulamanız için mevcut olan genel seçenekleri hakkında daha fazla bilgi için bkz. [AFX_GLOBAL_DATA yapısı](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onglobalfontschanged"></a>  CMFCToolBarEditBoxButton::OnGlobalFontsChanged

Genel yazı tipi değiştiğinde framework tarafından çağırılır.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) genel yazı tipini, yazı tipini denetimi değiştirerek.

Uygulamanız için mevcut olan genel seçenekleri hakkında daha fazla bilgi için bkz. [AFX_GLOBAL_DATA yapısı](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onmove"></a>  CMFCToolBarEditBoxButton::OnMove

Üst araç çubuğunda hareket ettiğinde framework tarafından çağırılır.

```
virtual void OnMove();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan sınıf uygulamasını bu metodu geçersiz kılar ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) iç konumunu güncelleştirerek `CEdit` nesnesi

##  <a name="onshow"></a>  CMFCToolBarEditBoxButton::OnShow

Düğme olduğunda görünür veya gizli framework tarafından çağırılır.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bBilgi Göster*<br/>
[in] Düğmenin görünür olup olmadığını belirtir. Bu parametre TRUE ise, düğmeyi görülebilir. Aksi halde düğme görünür değil.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)), düğmeyi görüntüleyerek *bBilgi Göster* true'dur. Aksi takdirde, bu yöntem düğmesi gizlenir.

##  <a name="onsize"></a>  CMFCToolBarEditBoxButton::OnSize

Üst araç çubuğunda boyutunu değiştirir veya konumu ve bu değişiklik neden boyutunu değiştirmek düğmeyi framework tarafından çağırılır.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parametreler

*iSize*<br/>
[in] Yeni piksel cinsinden düğmenin genişliği.

### <a name="remarks"></a>Açıklamalar

Varsayılan sınıf uygulamasını bu metodu geçersiz kılar [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize), boyutunu ve konumunu iç güncelleştirerek `CEdit` nesne.

##  <a name="onupdatetooltip"></a>  CMFCToolBarEditBoxButton::OnUpdateToolTip

Üst araç çubuğunda, araç ipucu metni güncelleştirdiğinde framework tarafından çağırılır.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[in] Kullanılmayan.

*iButtonIndex*<br/>
[in] Kullanılmayan.

*wndToolTip*<br/>
[in] Araç ipucu metnini görüntüleyen denetim.

*str*<br/>
[out] A `CString` güncelleştirilmiş araç ipucunu alan nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Araç İpucu metni yöntemi güncelleştirmeleri olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) görüntüleyerek düğmesi düzenleme bölümü ile ilişkili olan araç ipucu metni. İç `CEdit` nesnedir NULL ya da pencere tanıtıcısı `CEdit` nesneyi varolan pencereye belirlemek değil, bu yöntem, hiçbir şey yapmaz ve false değerini döndürür.

##  <a name="setcontents"></a>  CMFCToolBarEditBoxButton::SetContents

Metin, metin kutusu denetiminde ayarlar.

```
virtual void SetContents(const CString& sContents);
```

### <a name="parameters"></a>Parametreler

*sContents*<br/>
[in] Ayarlanacak yeni metni belirtir.

##  <a name="setcontentsall"></a>  CMFCToolBarEditBoxButton::SetContentsAll

Bulur bir [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) belirtilen komut Kimliğine sahip ve belirtilen metin, metin kutusundaki ayarlar nesnesi.

```
static BOOL SetContentsAll(
    UINT uiCmd,
    const CString& strContents);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[in] Metin değiştirilecek denetim komut Kimliğini belirtir.

*strContents*<br/>
[in] Ayarlanacak yeni metni belirtir.

### <a name="return-value"></a>Dönüş Değeri

Metni ayarlanmadı olursa sıfır dışı; 0 ise `CMFCToolBarEditBoxButton` Denetim belirtilen komut kimliği yok.

##  <a name="setcontextmenuid"></a>  CMFCToolBarEditBoxButton::SetContextMenuID

Kısayol menüsünün düğmesi ile ilişkili kaynak Kimliğini belirtir.

```
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[in] Kısayol menüsünde kaynak kimliği.

### <a name="remarks"></a>Açıklamalar

Framework, kullanıcı araç çubuğu düğmesini tıklattığında kısayolunu oluşturmak için kaynak Kimliğini kullanır.

##  <a name="setflatmode"></a>  CMFCToolBarEditBoxButton::SetFlatMode

Uygulamayı düzenleme kutusu düğmeleri düz stil görünümünü belirler.

```
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```

### <a name="parameters"></a>Parametreler

*bFlat*<br/>
[in] Düzenleme kutusu düğmeleri düz stili. Bu parametre TRUE ise, düz bir stil görünümünü etkinleştirilir; Aksi takdirde düz stil görünümünü devre dışı bırakıldı.

### <a name="remarks"></a>Açıklamalar

Varsayılan düz stil için düzenleme kutusu düğmeleri, TRUE şeklindedir. Kullanım [CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode) , uygulamanızın düz stil görünümünü almak için yöntemi.

##  <a name="setstyle"></a>  CMFCToolBarEditBoxButton::SetStyle

Düzenleme kutusu denetimi araç çubuğu stilini belirtir.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
[in] Ayarlanacak yeni stili.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ayarlar [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) için *nStyle* uygulamayı Özelleştir modunda ve uygulamayı özelleştirme modu (bkz: olmadığındasağlar,ayrıcametinkutusunudevredışıbırakır[ CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) ve [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). Bkz: [ToolBar denetim stilleri](../../mfc/reference/toolbar-control-styles.md) geçerli stili bayrakların listesi için.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton Sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)



