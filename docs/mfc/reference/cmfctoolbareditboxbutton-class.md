---
title: CMFCToolBarEditBoxButton Sınıfı
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
ms.openlocfilehash: 52989f7b523bf0ba9a00da350242a968ca0db153
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360481"
---
# <a name="cmfctoolbareditboxbutton-class"></a>CMFCToolBarEditBoxButton Sınıfı

Düzenleme denetimi [(CEdit Class)](../../mfc/reference/cedit-class.md)içeren araç çubuğu düğmesi.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarEditBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](#cmfctoolbareditboxbutton)|Bir `CMFCToolBarEditBoxButton` nesne inşa eder.|
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|Özelleştirme sırasında bir kullanıcının düğmeyi esnetleyip genişletemeyeceğini belirtir. [(Overrides CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesinin özelliklerini geçerli düğmeye kopyalar. [(CMFCToolBarButton geçersiz kılar::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::CreateEdit](#createedit)|Düğmede yeni bir denetim denetimi oluşturur.|
|`CMFCToolBarEditBoxButton::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|Belirtilen komut `CMFCToolBarEditBoxButton` kimliğine sahip uygulamada ilk nesneyi alır.|
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|Belirtilen komut kimliğine sahip ilk düzenleme kutusu araç çubuğu denetiminin metnini alır.|
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|Düğmeyle ilişkili kısayol menüsünün kaynak kimliğini alır.|
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|Edit kutusu düğmesinin bir bölümünün sınırlayıcı dikdörtgenini alır.|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|Düğmeye katıştırılmış bir düğmeyi denetlemedenetimine bir işaretçi döndürür.|
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|Araç çubuğu düğmesiyle ilişkili pencere tutamacını alır. (Geçersiz kılar [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|Yeniden çizilmesi gereken düğmenin istemci alanının bölgesini alır. [(CMFCToolBarButton geçersiz kılar::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|
|`CMFCToolBarEditBoxButton::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|Kullanıcı düğmeyi tıklattığında düğmenin kenarlığı görüntülenip görüntülenmediğini belirler. (Geçersiz kılar [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|Kutu düğmelerinin düz bir stili olup olmadığını belirler.|
|[CMFCToolBarEditBoxButton::Komut Bildir](#notifycommand)|Düğmenin [WM_COMMAND](/windows/win32/menurc/wm-command) iletiyi çalışıp belirtir. [(CMFCToolBarButton geçersiz kılar::Command Command](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|**Özelleştir** iletişim kutusuna düğme eklendiğinde çerçeve tarafından çağrılır. [(CmFCToolBarButton geçersiz kılar::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Belirtilen aygıt bağlamı ve yerleştirme durumu için düğmenin boyutunu hesaplamak için çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|Düğme yeni bir araç çubuğuna takıldığında çerçeve tarafından çağrılır. [(Üstyüklemeler CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCToolBarEditBoxButton::Tıkla](#onclick)|Kullanıcı fare düğmesini tıklattığında çerçeve tarafından çağrılır. [(Overrides CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|Üst araç çubuğu bir WM_CTLCOLOR iletisi işlediğinde çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarEditBoxButton::OnDraw`|Belirtilen stilleri ve seçenekleri kullanarak düğmeyi çizmek için çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|**Özelleştir** iletişim kutusunun **Komutlar** bölmesinde düğmeyi çizmek için çerçeve tarafından çağrılır. [(Overrides CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCToolBarEditBoxButton::OnGlobalFontsDeğiştirildi](#onglobalfontschanged)|Genel yazı tipi değiştiğinde çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|Ana araç çubuğu hareket ettiğinde çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[CMFCToolBarEditBoxButton::Açık Göster](#onshow)|Düğme görünür veya görünmez olduğunda çerçeve tarafından çağrılır. [(CmFCToolBarButton geçersiz kılar::AçıkShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|[CMFCToolBarEditBoxButton::Boyut](#onsize)|Ana araç çubuğu boyutunu veya konumunu değiştirdiğinde ve bu değişiklik düğmenin boyutunu değiştirmesine neden olduğunda çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|Üst araç çubuğu araç ipucu metnini güncelleştirirken çerçeve tarafından çağrılır. [(Overrides CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarEditBoxButton::Serialize`|Bu nesneyi arşivden okur veya arşive yazar. [(CMFCToolBarButton geçersiz kılar::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarEditBoxButton::SetACCData`|Araç çubuğu `CAccessibilityData` düğmesinden sağlanan nesneyi erişilebilirlik verileriyle doldurur. [(CMFCToolBarButton geçersiz kılar::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetContents](#setcontents)|Düğmenin denetiminde metni ayarlar.|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|Belirtilen komut kimliğine sahip denetim düğmesini bulur ve bu düğmenin denetimindeki metni ayarlar.|
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|Düğmeyle ilişkili kısayol menüsünün kaynak kimliğini belirtir.|
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|Uygulamadaki kutu düğmelerinin düz stil görünümünü belirtir.|
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetStyle](#setstyle)|Düğmenin stilini belirtir. [(CMFCToolBarButton geçersiz kılar::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|

## <a name="remarks"></a>Açıklamalar

Araç çubuğuna düzenleme kutusu düğmesi eklemek için aşağıdaki adımları izleyin:

1. Ana araç çubuğu kaynağındaki düğme için sahte bir kaynak kimliği ayırın.

2. Bir `CMFCToolBarEditBoxButton` nesne oluştur.

3. AFX_WM_RESETTOOLBAR iletiyi işleyen ileti işleyicisinde, [CMFCToolBar::ReplaceButton'u](../../mfc/reference/cmfctoolbar-class.md#replacebutton)kullanarak sahte düğmeyi yeni açılan kutu düğmesiyle değiştirin.

Daha fazla bilgi için [Walkthrough: Denetimleri Araç Çubuklarına Koyma'ya](../../mfc/walkthrough-putting-controls-on-toolbars.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemlerin `CMFCToolBarEditBoxButton` nasıl kullanılacağını göstermektedir. Örnek, özelleştirme sırasında bir kullanıcının düğmeyi nasıl uzatabileceğini belirtin, bir kullanıcı düğmeyi tıklattığında düğmenin kenarının görüntüleneceğini belirtin, metin kutusu denetimindeki metni ayarlayın, uygulamadaki düzenleme kutusu düğmelerinin düz stil görünümünü belirtin ve araç çubuğu düzenleme kutusu denetiminin stilini belirtir.

[!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

`CMFCToolBarEditBoxButton`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbareditboxbutton.h

## <a name="cmfctoolbareditboxbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCToolBarEditBoxButton::CanBeStretched

Özelleştirme sırasında bir kullanıcının düğmeyi esnetleyip genişletemeyeceğini belirtir.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, çerçeve kullanıcıözelleştirme sırasında bir araç çubuğu düğmesini germek için izin vermez. Bu yöntem, kullanıcının özelleştirme sırasında düzenleme kutusu araç çubuğunu esnetmesine izin vererek taban sınıf uygulamasını [(CMFCToolBarButton::CanBeStretched)](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)genişletir.

## <a name="cmfctoolbareditboxbuttoncmfctoolbareditboxbutton"></a><a name="cmfctoolbareditboxbutton"></a>CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton

[CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) nesnesi oluşturuyor.

```
CMFCToolBarEditBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=ES_AUTOHSCROLL,
    int iWidth=0);
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[içinde] Denetim kimliğini belirtir.

*ıımage*<br/>
[içinde] Araç çubuğu görüntüsünün sıfır tabanlı dizinini belirtir. Görüntü [CMFCToolBarClass](../../mfc/reference/cmfctoolbarimages-class.md) sınıfının koruduğu [CMFCToolBarImages](../../mfc/reference/cmfctoolbar-class.md) Sınıfı nesnesinde bulunur.

*Dwstyle*<br/>
[içinde] Denetim stilini belirtir.

*iGenişlik*<br/>
[içinde] Denetimin piksellerinde genişliği belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan oluşturucu, denetim stilini aşağıdaki kombinasyona ayarlar:

WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL

Denetimin varsayılan genişliği 150 pikseldir.

## <a name="cmfctoolbareditboxbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCToolBarEditBoxButton::CopyFrom

Başka bir araç çubuğu düğmesinin özelliklerini geçerli düğmeye kopyalar.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[içinde] Kopyalamak için kaynak düğmesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Başka bir araç çubuğu düğmesini bu araç çubuğu düğmesine kopyalamak için bu yöntemi arayın. *src* türünde `CMFCToolBarEditBoxButton`olmalıdır.

## <a name="cmfctoolbareditboxbuttoncreateedit"></a><a name="createedit"></a>CMFCToolBarEditBoxButton::CreateEdit

Düğmede yeni bir denetim denetimi oluşturur.

```
virtual CEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Denetimin üst penceresini belirtir. NULL olmamalıdır.

*Rect*<br/>
[içinde] Edit denetiminin boyutunu ve konumunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan edit denetimi için bir işaretçi; denetimin oluşturulması ve eki başarısız olursa NULL'dur.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CMFCToolBarEditBoxButton` iki adımda inşa ee. Önce oluşturucuyu çağırın, `CreateEdit`sonra Windows edit denetimini oluşturan ve `CMFCToolBarEditBoxButton` nesneye iliştiren , sonra çağırın.

## <a name="cmfctoolbareditboxbuttongetbycmd"></a><a name="getbycmd"></a>CMFCToolBarEditBoxButton::GetByCmd

Belirtilen komut `CMFCToolBarEditBoxButton` kimliğine sahip uygulamada ilk nesneyi alır.

```
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Alınacak düğmenin komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen `CMFCToolBarEditBoxButton` komut kimliğine sahip uygulamada ilk nesne veya böyle bir nesne yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu paylaşılan yardımcı program yöntemi [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall) ve [CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall) ayarlamak veya belirtilen komut kimliğine sahip ilk düzenleme kutusu araç çubuğu denetimi nin metnini almak gibi yöntemlerle kullanılır.

## <a name="cmfctoolbareditboxbuttongetcontentsall"></a><a name="getcontentsall"></a>CMFCToolBarEditBoxButton::GetContentsAll

Belirtilen komut kimliğine sahip ilk düzenleme kutusu araç çubuğu denetiminin metnini alır.

```
static CString __stdcall GetContentsAll(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] İçeriği almak için düğmenin komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen `CString` komut kimliğine sahip ilk düzenleme kutusu araç çubuğu denetiminin metnini içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen komut `CMFCToolBarEditBoxButton` kimliğine sahip olmayan nesneler yoksa boş dizeyi döndürür.

## <a name="cmfctoolbareditboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a>CMFCToolBarEditBoxButton::GetContextMenuID

Düğmeyle ilişkili kısayol menüsünün kaynak kimliğini alır.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmede ilişkili kısayol menüsü yoksa, düğmeyle ilişkili kısayol menüsünün kaynak kimliği veya 0.

### <a name="remarks"></a>Açıklamalar

Çerçeve, kullanıcı düğmeye sağ tıkladığında kısayol menüsünü oluşturmak için kaynak kimliğini kullanır.

## <a name="cmfctoolbareditboxbuttongeteditborder"></a><a name="geteditborder"></a>CMFCToolBarEditBoxButton::GetEditBorder

Edit kutusu düğmesinin bir bölümünün sınırlayıcı dikdörtgenini alır.

```
virtual void GetEditBorder(CRect& rectBorder);
```

### <a name="parameters"></a>Parametreler

*rectBorder*<br/>
[çıkış] Sınırlayıcı dikdörtgeni alan `CRect` nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, istemci koordinatlarında düzen denetiminin sınırlayıcı dikdörtgenini alır. Her yöndeki dikdörtgenin boyutunu bir piksel genişletir.

[CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) yöntemi, bir `CMFCToolBarEditBoxButton` nesnenin kenarlığı çizdiğinde bu yöntemi çağırır.

## <a name="cmfctoolbareditboxbuttongeteditbox"></a><a name="geteditbox"></a>CMFCToolBarEditBoxButton::GetEditBox

Düğmeye katıştırılmış [CEdit Sınıfı](../../mfc/reference/cedit-class.md) denetimine bir işaretçi döndürür.

```
CEdit* GetEditBox() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin içerdiği [CEdit Sınıfı](../../mfc/reference/cedit-class.md) denetimine işaretçi. `CEdit` Denetim henüz oluşturulmadıysa NULL'dur.

### <a name="remarks"></a>Açıklamalar

Denetimi `CEdit` [CMFCToolBarEditBoxButton'ı arayarak oluşturursunuz::CreateEdit](#createedit).

## <a name="cmfctoolbareditboxbuttongethwnd"></a><a name="gethwnd"></a>CMFCToolBarEditBoxButton::GetHwnd

Araç çubuğu düğmesiyle ilişkili pencere tutamacını alır.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmeyle ilişkili pencere tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CMFCToolBarButton geçersiz kılar::Düzenleme](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) kutusu düğmesinin denetim bölümünün pencere tutamacını döndürerek GetHwnd yöntemi.

## <a name="cmfctoolbareditboxbuttongetinvalidaterect"></a><a name="getinvalidaterect"></a>CMFCToolBarEditBoxButton::GetInvalidateRect

Yeniden çizilmesi gereken düğmenin istemci alanının bölgesini alır.

```
virtual const CRect GetInvalidateRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeniden `CRect` çizilmesi gereken bölgeyi belirten bir nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, metin etiketinin alanını bölgeye ekleyerek taban sınıf uygulamasını, [CMFCToolBarButton::GetInvalidateRect'i](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect)genişletir.

## <a name="cmfctoolbareditboxbuttonhavehotborder"></a><a name="havehotborder"></a>CMFCToolBarEditBoxButton::HaveHotBorder

Kullanıcı düğmeyi tıklattığında düğmenin kenarlığı görüntülenip görüntülenmediğini belirler.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir düğme seçildiğinde kenarlığını görüntülerse sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetim görünürise sıfır olmayan bir değer döndürerek taban sınıf uygulaması, [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder)genişletir.

## <a name="cmfctoolbareditboxbuttonisflatmode"></a><a name="isflatmode"></a>CMFCToolBarEditBoxButton::IsFlatMode

Kutu düğmelerinin düz bir stili olup olmadığını belirler.

```
static BOOL __stdcall IsFlatMode();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmelerin düz bir stili varsa sıfıra inme; aksi takdirde, 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, kutu düğmelerini düzenleme nin düz bir stili vardır. [CMFCToolBarEditBoxButton::Uygulamanızın](#setflatmode) düz stil görünümünü değiştirmek için SetFlatMode yöntemini kullanın.

## <a name="cmfctoolbareditboxbuttonnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarEditBoxButton::Komut Bildir

Düğmenin [WM_COMMAND](/windows/win32/menurc/wm-command) iletiyi çalışıp belirtir.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parametreler

*iNotifyCode*<br/>
[içinde] Komutla ilişkili bildirim iletisi.

### <a name="return-value"></a>Dönüş Değeri

Doğru düğme, iletinin ana araç çubuğu tarafından işletilmesi gerektiğini belirtmek için WM_COMMAND iletisini işlerse veya FALSE.

### <a name="remarks"></a>Açıklamalar

Çerçeve, üst pencereye [WM_COMMAND](/windows/win32/menurc/wm-command) iletisi göndermek üzereyken bu yöntemi çağırır.

Bu [yöntem, EN_UPDATE](/windows/win32/Controls/en-update) bildirimini işleyerek taban sınıf uygulamasını [(CMFCToolBarButton::NotifyCommand)](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)genişletir. Bu nesneyle aynı komut kimliğine sahip her bir edit kutusu için metin etiketini bu nesnenin metin etiketine ayarlar.

## <a name="cmfctoolbareditboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarEditBoxButton::OnAddToCustomizePage

**Özelleştir** iletişim kutusuna düğme eklendiğinde çerçeve tarafından çağrılır.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu nesneyle aynı komut kimliğine sahip herhangi bir araç çubuğundaki düzenleme kutusu denetiminden özellikleri kopyalayarak taban sınıf uygulamasını [(CMFCToolBarButton::OnAddToCustomizePage)](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)genişletir. Bu yöntem, hiçbir araç çubuğunda bu nesneyle aynı komut kimliğine sahip bir düzenleme kutusu denetimi varsa hiçbir şey yapmaz.

**Özelleştir** iletişim kutusu hakkında daha fazla bilgi için [CMFCToolBarsCustomizeDialog Class'a](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)bakın.

## <a name="cmfctoolbareditboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarEditBoxButton::OnChangeParentWnd

Düğme yeni bir araç çubuğuna takıldığında çerçeve tarafından çağrılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Yeni üst pencereiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç `CEdit` nesneyi yeniden oluşturarak taban sınıf uygulamasını [(CMFCToolBarButton::OnChangeParentWnd)](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)geçersiz kılar.

## <a name="cmfctoolbareditboxbuttononclick"></a><a name="onclick"></a>CMFCToolBarEditBoxButton::Tıkla

Kullanıcı fare düğmesini tıklattığında çerçeve tarafından çağrılır.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Kullanılma -yan.

*bGecikme*<br/>
[içinde] Kullanılma -yan.

### <a name="return-value"></a>Dönüş Değeri

Düğme tıklama iletisini işlerse sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç `CEdit` nesne görünürse sıfır olmayan bir değer döndürerek taban sınıf uygulamasını [(CMFCToolBarButton::OnClick)](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)geçersiz kılar.

## <a name="cmfctoolbareditboxbuttononctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarEditBoxButton::OnCtlColor

Üst araç çubuğu bir WM_CTLCOLOR iletisi işlediğinde çerçeve tarafından çağrılır.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Düğmeyi görüntüleyen aygıt bağlamı.

*nCtlColor*<br/>
[içinde] Kullanılma -yan.

### <a name="return-value"></a>Dönüş Değeri

Genel pencere fırçasının tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, sağlanan aygıt bağlamının metin ve arka plan renklerini sırasıyla genel metin ve arka plan renklerine ayarlayarak taban sınıf uygulamasını [(CMFCToolBarButton::OnCtlColor)](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)geçersiz kılar.

Uygulamanızda kullanılabilen genel seçenekler hakkında daha fazla bilgi için [AFX_GLOBAL_DATA Yapısı'na](../../mfc/reference/afx-global-data-structure.md)bakın.

## <a name="cmfctoolbareditboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarEditBoxButton::OnGlobalFontsDeğiştirildi

Genel yazı tipi değiştiğinde çerçeve tarafından çağrılır.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetimin yazı tipini genel yazı tipiyle değiştirerek taban sınıf uygulamasını [(CMFCToolBarButton::OnGlobalFontsChanged)](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)genişletir.

Uygulamanızda kullanılabilen genel seçenekler hakkında daha fazla bilgi için [AFX_GLOBAL_DATA Yapısı'na](../../mfc/reference/afx-global-data-structure.md)bakın.

## <a name="cmfctoolbareditboxbuttononmove"></a><a name="onmove"></a>CMFCToolBarEditBoxButton::OnMove

Ana araç çubuğu hareket ettiğinde çerçeve tarafından çağrılır.

```
virtual void OnMove();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç `CEdit` nesnenin konumunu güncelleştirerek varsayılan sınıf uygulamasını [(CMFCToolBarButton::OnMove)](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)geçersiz kılar

## <a name="cmfctoolbareditboxbuttononshow"></a><a name="onshow"></a>CMFCToolBarEditBoxButton::Açık Göster

Düğme görünür veya görünmez olduğunda çerçeve tarafından çağrılır.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bGöster*<br/>
[içinde] Düğmenin görünür olup olmadığını belirtir. Bu parametre TRUE ise, düğme görünür. Aksi takdirde, düğme görünmez.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *bShow* DOĞRU ise düğmeyi görüntüleyerek taban sınıf uygulamasını [(CMFCToolBarButton::OnShow)](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)genişletir. Aksi takdirde, bu yöntem düğmeyi gizler.

## <a name="cmfctoolbareditboxbuttononsize"></a><a name="onsize"></a>CMFCToolBarEditBoxButton::Boyut

Ana araç çubuğu boyutunu veya konumunu değiştirdiğinde ve bu değişiklik düğmenin boyutunu değiştirmesine neden olduğunda çerçeve tarafından çağrılır.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parametreler

*iSize*<br/>
[içinde] Düğmenin yeni genişliği, pikselolarak.

### <a name="remarks"></a>Açıklamalar

Bu yöntem varsayılan sınıf uygulaması geçersiz kılar, [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize), iç `CEdit` nesnenin boyutunu ve konumunu güncelleştirerek.

## <a name="cmfctoolbareditboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarEditBoxButton::OnUpdateToolTip

Üst araç çubuğu araç ipucu metnini güncelleştirirken çerçeve tarafından çağrılır.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Kullanılma -yan.

*iButtonIndex*<br/>
[içinde] Kullanılma -yan.

*wndToolTip*<br/>
[içinde] Araç ipucu metnini görüntüleyen denetim.

*Str*<br/>
[çıkış] Güncelleştirilmiş araç ipucu metnini alan bir `CString` nesne.

### <a name="return-value"></a>Dönüş Değeri

Yöntem araç ipucu metnini güncelleştirirse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, düğmenin düzenleme bölümüyle ilişkili araç ipucu metnini görüntüleyerek taban sınıf uygulamasını [(CMFCToolBarButton::OnUpdateToolTip)](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)genişletir. İç `CEdit` nesne NULL ise veya nesnenin `CEdit` pencere tutamacı varolan bir pencereyi tanımlamazsa, bu yöntem hiçbir şey yapmaz ve FALSE döndürür.

## <a name="cmfctoolbareditboxbuttonsetcontents"></a><a name="setcontents"></a>CMFCToolBarEditBoxButton::SetContents

Metin kutusu denetimindeki metni ayarlar.

```
virtual void SetContents(const CString& sContents);
```

### <a name="parameters"></a>Parametreler

*sContents*<br/>
[içinde] Ayarlanacak yeni metni belirtir.

## <a name="cmfctoolbareditboxbuttonsetcontentsall"></a><a name="setcontentsall"></a>CMFCToolBarEditBoxButton::SetContentsAll

Belirtilen komut kimliğine sahip bir [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) nesnesi bulur ve metin kutusunda belirtilen metni ayarlar.

```
static BOOL SetContentsAll(
    UINT uiCmd,
    const CString& strContents);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Metnin değiştirileceği denetimin komut kimliğini belirtir.

*strContents*<br/>
[içinde] Ayarlanacak yeni metni belirtir.

### <a name="return-value"></a>Dönüş Değeri

Metin ayarlanmışsa sıfır olmayan; Belirtilen komut `CMFCToolBarEditBoxButton` kimliği ile denetim yoksa 0.

## <a name="cmfctoolbareditboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a>CMFCToolBarEditBoxButton::SetContextMenuID

Düğmeyle ilişkili kısayol menüsünün kaynak kimliğini belirtir.

```
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Kısayol menüsünün kaynak kimliği.

### <a name="remarks"></a>Açıklamalar

Kullanıcı araç çubuğu düğmesini sağ tıklattığında kısayol menüsünü oluşturmak için kaynak kimliği kullanır.

## <a name="cmfctoolbareditboxbuttonsetflatmode"></a><a name="setflatmode"></a>CMFCToolBarEditBoxButton::SetFlatMode

Uygulamadaki kutu düğmelerinin düz stil görünümünü belirtir.

```
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```

### <a name="parameters"></a>Parametreler

*bDüz*<br/>
[içinde] Kutu düğmelerini edin için düz stil. Bu parametre TRUE ise, düz stil görünümü etkinleştirilir; aksi takdirde düz stil görünümü devre dışı bırakılır.

### <a name="remarks"></a>Açıklamalar

Kutu düğmelerini edin için varsayılan düz stil TRUE'dur. [CMFCToolBarEditBoxButton::Uygulamanız](#isflatmode) için düz stil görünümünü almak için IsFlatMode yöntemini kullanın.

## <a name="cmfctoolbareditboxbuttonsetstyle"></a><a name="setstyle"></a>CMFCToolBarEditBoxButton::SetStyle

Araç çubuğu düzenleme kutusu denetiminin stilini belirtir.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
[içinde] Ayarı yeni bir stil.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) *nStyle* için de uygulama Özelleştirme modunda olduğunda metin kutusunu devre dışı katıyor ve uygulama Özelleştirme modunda olmadığında bunu sağlar (cmfcToolBar [bakınız::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) ve [CMFCToolBar::IsCustomizeMode).](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) Geçerli stil bayrakları listesi için [Araç Çubuğu Denetim Stilleri'ne](../../mfc/reference/toolbar-control-styles.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton Sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
