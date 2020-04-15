---
title: CMFCToolBarComboBoxButton Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddSortedItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::Compare
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CreateEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::DeleteItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::FindItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetByCmd
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetComboBox
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCount
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCountAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSel
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSelAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetEditCtrl
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemData
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataPtrAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetText
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetTextAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsFlatMode
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::RemoveAllItems
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetDropDownHeight
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetFlatMode
helpviewer_keywords:
- CMFCToolBarComboBoxButton [MFC], CMFCToolBarComboBoxButton
- CMFCToolBarComboBoxButton [MFC], AddItem
- CMFCToolBarComboBoxButton [MFC], AddSortedItem
- CMFCToolBarComboBoxButton [MFC], Compare
- CMFCToolBarComboBoxButton [MFC], CreateEdit
- CMFCToolBarComboBoxButton [MFC], DeleteItem
- CMFCToolBarComboBoxButton [MFC], FindItem
- CMFCToolBarComboBoxButton [MFC], GetByCmd
- CMFCToolBarComboBoxButton [MFC], GetComboBox
- CMFCToolBarComboBoxButton [MFC], GetCount
- CMFCToolBarComboBoxButton [MFC], GetCountAll
- CMFCToolBarComboBoxButton [MFC], GetCurSel
- CMFCToolBarComboBoxButton [MFC], GetCurSelAll
- CMFCToolBarComboBoxButton [MFC], GetEditCtrl
- CMFCToolBarComboBoxButton [MFC], GetItem
- CMFCToolBarComboBoxButton [MFC], GetItemAll
- CMFCToolBarComboBoxButton [MFC], GetItemData
- CMFCToolBarComboBoxButton [MFC], GetItemDataAll
- CMFCToolBarComboBoxButton [MFC], GetItemDataPtrAll
- CMFCToolBarComboBoxButton [MFC], GetText
- CMFCToolBarComboBoxButton [MFC], GetTextAll
- CMFCToolBarComboBoxButton [MFC], IsCenterVert
- CMFCToolBarComboBoxButton [MFC], IsFlatMode
- CMFCToolBarComboBoxButton [MFC], RemoveAllItems
- CMFCToolBarComboBoxButton [MFC], SelectItem
- CMFCToolBarComboBoxButton [MFC], SelectItemAll
- CMFCToolBarComboBoxButton [MFC], SetCenterVert
- CMFCToolBarComboBoxButton [MFC], SetDropDownHeight
- CMFCToolBarComboBoxButton [MFC], SetFlatMode
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
ms.openlocfilehash: 0d003bdacf13403ad8dc4be4ec7e6f71ea57d156
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372183"
---
# <a name="cmfctoolbarcomboboxbutton-class"></a>CMFCToolBarComboBoxButton Sınıfı

Açılan kutu denetimi [(CComboBox Class)](../../mfc/reference/ccombobox-class.md)içeren bir araç çubuğu düğmesi.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarComboBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](#cmfctoolbarcomboboxbutton)|Bir `CMFCToolBarComboBoxButton`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarComboBoxButton::Öğe Ekle](#additem)|Açılan kutu listesinin sonuna bir öğe ekler.|
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|Açılan kutu listesine bir öğe ekler. Listedeki maddelerin sırası `Compare`.|
|[CMFCToolBarComboBoxButton::Karşılaştır](#compare)|İki öğeyi karşılaştırır. Açılan kutu listesine ekleyen `AddSortedItems` öğeleri sıralamak için çağrılır.|
|[CMFCToolBarComboBoxButton:CreateEdit](#createedit)|Açılan kutu düğmesi için yeni bir denetim denetimi oluşturur.|
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|Bir öğeyi açılan kutu listesinden siler.|
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|Belirtilen dizeiçeren maddenin dizinini döndürür.|
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|Belirtilen bir komut kimliğiyle bir işaretçiyi açılan kutu düğmesine döndürür.|
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|Bir işaretçiyi açılan kutu düğmesine katıştırılmış açılan kutu denetimine döndürür.|
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|Açılan kutu listesindeki öğe sayısını verir.|
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|Belirtilen komut kimliğine sahip açılan kutu düğmesini bulur. Bu düğmenin açılan kutu listesindeki öğelerin sayısını verir.|
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|Açılan kutu listesinde seçili öğenin dizinini döndürür.|
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|Belirtilen komut kimliğine sahip açılan kutu düğmesini bulur ve bu düğmenin açılan kutusu listesinde seçili öğenin dizinini döndürür.|
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|Açılan kutu düğmesine katıştırılmış bir işaretçiyi denetime döndürür.|
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|Açılan kutu listesinde belirtilen dizinle ilişkili dizeyi döndürür.|
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|Belirtilen komut kimliğine sahip açılan kutu düğmesini bulur ve bu düğmenin açılan kutusu listesinde dizinle ilişkili dizeyi döndürür.|
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|Açılan kutu listesinde belirtilen dizinle ilişkili 32 bit değerini döndürür.|
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|Belirtilen komut kimliğine sahip açılan kutu düğmesini bulur ve bu düğmenin açılan kutusu listesinde dizinle ilişkili 32 bit değerini döndürür.|
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|Belirtilen komut kimliğine sahip açılan kutu düğmesini bulur. Bu düğmenin açılan kutu listesinde bir dizinle ilişkili 32 bit değerini alır ve 32 bit değerini işaretçi olarak döndürür.|
|[CMFCToolBarComboBoxButton::GetText](#gettext)|Açılan kutunun denetiminden metni döndürür.|
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|Belirtilen komut kimliğine sahip açılan kutu düğmesini bulur ve metni bu düğmenin denetiminden döndürür.|
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|Uygulamadaki açılan kutu düğmelerinin ortalanmış mı yoksa araç çubuğunun üst kısmıyla hizalanmış mı olduğunu belirler.|
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|Uygulamadaki açılan kutu düğmelerinin düz bir görünüme sahip olup olmadığını belirler.|
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|Liste kutusundaki tüm öğeleri kaldırır ve açılan kutunun denetimini edin.|
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|Açılan kutudaki bir öğeyi dizinine, 32 bit değerine veya dizesine göre seçer ve açılan kutu denetimini seçim hakkında bildirir.|
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|Belirtilen komut kimliğine sahip açılan kutu düğmesini bulur. Dize, dizin veya 32 bit değerine göre o düğmenin açılan kutusundabir öğeseçmek için çağrıda bulunur. `SelectItem`|
|[CMFCToolBarComboBoxButton:SetCenterVert](#setcentervert)|Uygulamadaki açılan kutu düğmelerinin dikey olarak ortalanıp ortalanmayacağını veya araç çubuğunun üst kısmıyla hizalanıp hizalanmayacağını belirtir.|
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|Açılır liste kutusunun yüksekliğini ayarlar.|
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|Uygulamadaki açılan kutu düğmelerinin düz bir görünüme sahip olup olmadığını belirtir.|

## <a name="remarks"></a>Açıklamalar

Araç çubuğuna açılan kutu düğmesi eklemek için aşağıdaki adımları izleyin:

1. Ana araç çubuğu kaynağındaki düğme için sahte bir kaynak kimliği ayırın.

2. Bir `CMFCToolBarComboBoxButton` nesne oluştur.

3. AFX_WM_RESETTOOLBAR iletiyi işleyen ileti işleyicisinde, [CMFCToolBar::ReplaceButton'u](../../mfc/reference/cmfctoolbar-class.md#replacebutton)kullanarak sahte düğmeyi yeni açılan kutu düğmesiyle değiştirin.

Daha fazla bilgi için [Walkthrough: Denetimleri Araç Çubuklarına Koyma'ya](../../mfc/walkthrough-putting-controls-on-toolbars.md)bakın. Açılan kutu araç çubuğu düğmesi örneği için VisualStudioDemo örnek projesine bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemlerin `CMFCToolBarComboBoxButton` nasıl kullanılacağını göstermektedir. Örnek, edit ve açılan kutuların nasıl etkinleştirilen, uygulamada açılan kutu düğmelerinin dikey konumunu ayarlamayı, bırakıldığında liste kutusunun yüksekliğini ayarlamayı, uygulamadaki açılan kutu düğmelerinin düz stil görünümünü nasıl ayarlayacaklarını ve metni açılan kutu düğmesinin düzenlenmiş kutusunda nasıl ayarlayacaklarını gösterir. Bu kod snippet [Visual Studio Demo örnek](../../overview/visual-cpp-samples.md)parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[Cmfctoolbarcomboboxbutton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtoolbarcomboboxbutton.h

## <a name="cmfctoolbarcomboboxbuttonadditem"></a><a name="additem"></a>CMFCToolBarComboBoxButton::Öğe Ekle

Liste kutusuna benzersiz bir öğe ekler.

```
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Parametreler

*lpszItem*<br/>
[içinde] Liste kutusuna eklenecek öğenin metni.

*Dwdata*<br/>
[içinde] Liste kutusuna eklenecek öğeyle ilişkili veriler.

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki son öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Liste kutusu stili sıralandığında bu yöntemi kullanmayın.

Öğe metni zaten liste kutusundaysa, yeni veriler varolan öğeyle birlikte depolanır. Öğenin aranması büyük/küçük harf duyarlıdır.

## <a name="cmfctoolbarcomboboxbuttonaddsorteditem"></a><a name="addsorteditem"></a>CMFCToolBarComboBoxButton::AddSortedItem

[Karşılaştırma](#compare) yöntemiyle tanımlanan sırada liste kutusuna bir öğe ekler.

```
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Parametreler

*lpszItem*<br/>
[içinde] Liste kutusuna eklenecek öğenin metni.

*Dwdata*<br/>
[içinde] Liste kutusuna eklenecek öğeyle ilişkili veriler.

### <a name="return-value"></a>Dönüş Değeri

Liste kutusuna eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Belirli bir sırada liste kutusuna öğeleri eklemek için bu işlevi kullanın.

## <a name="cmfctoolbarcomboboxbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCToolBarComboBoxButton::CanBeStretched

Açılan kutu düğme boyutunun değişip değişemeyeceğini gösterir.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE döndürür.

## <a name="cmfctoolbarcomboboxbuttoncmfctoolbarcomboboxbutton"></a><a name="cmfctoolbarcomboboxbutton"></a>CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) nesnesi oluşturuyor.

```
CMFCToolBarComboBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=CBS_DROPDOWNLIST,
    int iWidth=0);
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[içinde] Yeni düğmenin komut kimliği.

*ıımage*<br/>
[içinde] Yeni düğmeyle ilişkili görüntünün görüntü dizini.

*Dwstyle*<br/>
[içinde] Yeni düğmenin stili.

*iGenişlik*<br/>
[içinde] Yeni düğmenin piksel genişliği.

### <a name="remarks"></a>Açıklamalar

Varsayılan genişlik 150 pikseldir.

Araç çubuğu düğme stilleri listesi için [ToolBar Control Styles'a](../../mfc/reference/toolbar-control-styles.md) bakın

## <a name="cmfctoolbarcomboboxbuttoncleardata"></a><a name="cleardata"></a>CMFCToolBarComboBoxButton::ClearData

Kullanıcı tanımlı verileri siler.

```
virtual void ClearData();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem hiçbir şey yapmaz. Kullanıcı tanımlı verileri silmek istiyorsanız, türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctoolbarcomboboxbuttoncompare"></a><a name="compare"></a>CMFCToolBarComboBoxButton::Karşılaştır

İki dizeyi karşılaştırır.

```
virtual int Compare(
    LPCTSTR lpszItem1,
    LPCTSTR lpszItem2);
```

### <a name="parameters"></a>Parametreler

*lpszItem1*<br/>
[içinde] Karşılaştırılacak ilk dize.

*lpszItem2*<br/>
[içinde] Karşılaştırılacak ikinci dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeleri arasındaki büyük/küçük harf duyarlı lexicographic ilişkisini gösteren bir değer. Aşağıdaki tabloda olası değerler listelenebilmektedir:

|Değer|Açıklama|
|-----------|-----------------|
|\<0|İlk dize ikinciden daha azdır.|
|0|İlk dize ikinciye eşittir.|
|>0|İlk dize ikincisinden daha büyüktür.|

### <a name="remarks"></a>Açıklamalar

Öğelerin liste kutusunda nasıl sıralandığını değiştirmek için bu yöntemi geçersiz kılın.

Karşılaştırma büyük/küçük harf duyarlıdır.

Bu yöntem yalnızca [AddSortedItem](#addsorteditem) yönteminden çağrılır.

## <a name="cmfctoolbarcomboboxbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCToolBarComboBoxButton::CopyFrom

Geçerli nesneye belirtilen `CMFCToolBarComboBoxButton` durumu kopyalar.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[içinde] Kaynak `CMFCToolBarComboBoxButton` nesne.

## <a name="cmfctoolbarcomboboxbuttoncreatecombo"></a><a name="createcombo"></a>CMFCToolBarComboBoxButton::CreateCombo

Açılan kutu düğmesi için yeni bir açılan kutu oluşturur.

```
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Düğmenin ana penceresine bir işaretçi.

*Rect*<br/>
[içinde] Açılan kutunun sınırlayıcı dikdörtgeni.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa, yeni açılan kutuya işaretçi; aksi takdirde, NULL.

## <a name="cmfctoolbarcomboboxbuttoncreateedit"></a><a name="createedit"></a>CMFCToolBarComboBoxButton:CreateEdit

Açılan kutu düğmesi için yeni bir edit kutusu oluşturur.

```
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Düğmenin ana penceresine bir işaretçi.

*Rect*<br/>
[içinde] Yeni düzeltme kutusunun sınırlayıcı dikdörtgeni.

*dwEditStyle*<br/>
[içinde] Yeni edit kutusunun denetim stili.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa, yeni edit kutusuna işaretçi; aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Çerçeve, açılan kutu düğmesi için yeni bir edit kutusu oluşturduğunda bu yöntemi çağırır. [CMFCToolBarComboBoxEdit'in](../../mfc/reference/cmfctoolbarcomboboxedit-class.md) nasıl oluşturulduğunu değiştirmek için bu yöntemi geçersiz kılın.

## <a name="cmfctoolbarcomboboxbuttondeleteitem"></a><a name="deleteitem"></a>CMFCToolBarComboBoxButton::DeleteItem

Liste kutusundan belirtilen bir öğeyi siler.

```
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);
BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Silinecek öğenin sıfır tabanlı dizin.

*Dwdata*<br/>
[içinde] Silinecek öğeyle ilişkili veriler.

*lpszMetin*<br/>
[içinde] Silinecek öğenin metni. Aynı metne sahip birden çok öğe varsa, ilk öğe silinir.

### <a name="return-value"></a>Dönüş Değeri

Öğe bulunurve başarıyla silinmişse TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttonduplicatedata"></a><a name="duplicatedata"></a>CMFCToolBarComboBoxButton::DuplicateData

Kullanıcı tanımlı verileri yineler.

```
virtual void DuplicateData();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem hiçbir şey yapmaz. Kullanıcı tanımlı verileri kopyalamak istiyorsanız, türemiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctoolbarcomboboxbuttonenablewindow"></a><a name="enablewindow"></a>CMFCToolBarComboBoxButton::Etkinleştirme Penceresi

Edit ve açılan kutuları etkinleştirir veya devre dışı kılabilir.

```
virtual void EnableWindow(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] TRUE ve açılan kutuları etkinleştirmek için; Edit ve açılan kutuları devre dışı kalmak için YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Devre dışı bırakıldığında, denetimler etkin hale gelemez ve kullanıcı girişini kabul edemez.

## <a name="cmfctoolbarcomboboxbuttonexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCToolBarComboBoxButton::ExportToMenuButton

Açılan kutu düğme komut uytu kimliği kullanarak uygulama dize tablosundan belirtilen menüye bir dize kopyalar.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parametreler

*menüDüğme*<br/>
[çıkış] Menü düğmesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE.

## <a name="cmfctoolbarcomboboxbuttonfinditem"></a><a name="finditem"></a>CMFCToolBarComboBoxButton::FindItem

Liste kutusunda belirtilen dizeyi içeren ilk öğenin dizinini döndürür.

```
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
[içinde] Liste kutusunda aranacak metin.

### <a name="return-value"></a>Dönüş Değeri

Maddenin dizini; veya öğe bulunamazsa CB_ERR.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongetbycmd"></a><a name="getbycmd"></a>CMFCToolBarComboBoxButton::GetByCmd

Belirli bir komut kimliğine sahip açılan kutu düğmesine bir işaretçi alır.

```
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,
    BOOL bIsFocus=FALSE);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Açılan kutu düğmesinin komut kimliği.

*bIsFocus*<br/>
[içinde] True sadece odaklanmış düğmeleri aramak için; TÜM düğmeleri aramak için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Açılan kutu düğmesine işaretçi; veya düğme bulunamazsa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongetcombobox"></a><a name="getcombobox"></a>CMFCToolBarComboBoxButton::GetComboBox

Açılan kutu düğmesindeki açılan kutuya bir işaretçi döndürür.

```
CComboBox* GetComboBox() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa [CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md) nesnesine bir işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a>CMFCToolBarComboBoxButton::GetContextMenuID

Açılan kutu düğmesi için kısayol menü kaynak kimliğini alır.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Dönüş Değeri

Kısayol menüsü kaynak kimliği.

## <a name="cmfctoolbarcomboboxbuttongetcount"></a><a name="getcount"></a>CMFCToolBarComboBoxButton::GetCount

Liste kutusundaki öğe sayısını döndürür.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongetcountall"></a><a name="getcountall"></a>CMFCToolBarComboBoxButton::GetCountAll

Belirtilen komut kimliğine sahip açılan kutu düğmesinin liste kutusundaki öğe sayısını alır.

```
static int GetCountAll(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Açılan kutu düğmesinin komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki öğe sayısı; aksi takdirde, açılan kutu düğmesi bulunmazsa CB_ERR.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongetcursel"></a><a name="getcursel"></a>CMFCToolBarComboBoxButton::GetCurSel

Liste kutusunda şu anda seçili öğenin dizinini alır.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusunda şu anda seçili öğenin dizin; veya öğe seçili değilse CB_ERR.

### <a name="remarks"></a>Açıklamalar

Liste kutusu dizini sıfır tabanlıdır.

## <a name="cmfctoolbarcomboboxbuttongetcurselall"></a><a name="getcurselall"></a>CMFCToolBarComboBoxButton::GetCurSelAll

Belirtilen komut kimliğine sahip açılan kutu düğmesinin liste kutusunda şu anda seçili öğenin dizinini verir.

```
static int GetCurSelAll(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Açılan kutu düğmesinin komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Liste kutusunda şu anda seçili öğenin dizin; aksi takdirde, CB_ERR öğe seçili değilse veya açılan kutu düğmesi bulunmazsa.

### <a name="remarks"></a>Açıklamalar

Liste kutusu dizini sıfır tabanlıdır.

## <a name="cmfctoolbarcomboboxbuttongeteditctrl"></a><a name="geteditctrl"></a>CMFCToolBarComboBoxButton::GetEditCtrl

Açılan kutu düğmesindeki bir işaretçiyi kutudaki edit kutusuna döndürür.

```
virtual CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı ysa, kutuyu işaretçisi; aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongethwnd"></a><a name="gethwnd"></a>CMFCToolBarComboBoxButton::GetHwnd

Açılan kutu için pencere tutamacını döndürür.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Dönüş Değeri

Açılan kutu bir pencere nesnesi ile ilişkili değilse pencere tutamacı veya NULL.

## <a name="cmfctoolbarcomboboxbuttongetitem"></a><a name="getitem"></a>CMFCToolBarComboBoxButton::GetItem

Liste kutusunda belirtilen bir dizinde bir öğeyle ilişkili dizeyi döndürür.

```
LPCTSTR GetItem(int iIndex=-1) const;
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Liste kutusundaki bir öğenin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Öğeyle ilişkili dize için bir işaretçi; aksi takdirde, dizin parametresi geçersizse veya dizin parametresi -1 ise ve açılan kutuda seçili öğe yoksa NULL.

### <a name="remarks"></a>Açıklamalar

-1 dizin parametresi, şu anda seçili olan öğenin dizesini döndürür.

## <a name="cmfctoolbarcomboboxbuttongetitemall"></a><a name="getitemall"></a>CMFCToolBarComboBoxButton::GetItemAll

Belirtilen komut kimliğine sahip açılan kutu düğmesinin liste kutusunda belirtilen bir dizindeki bir öğeyle ilişkili dizeyi döndürür.

```
static LPCTSTR GetItemAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Açılan kutu düğmesinin komut kimliği.

*ıındex*<br/>
[içinde] Liste kutusundaki bir öğenin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa öğenin dizesine bir işaretçi; aksi takdirde, dizin geçersizse, bir açılan kutu düğmesi bulunmazsa veya dizin -1 ise ve açılan kutuda seçili öğe yoksa NULL olur.

### <a name="remarks"></a>Açıklamalar

-1 dizin değeri, şu anda seçili olan öğenin dizesini döndürür.

## <a name="cmfctoolbarcomboboxbuttongetitemdata"></a><a name="getitemdata"></a>CMFCToolBarComboBoxButton::GetItemData

Liste kutusundabelirli bir dizinde bir maddeile ilişkili verileri döndürür.

```
DWORD_PTR GetItemData(int iIndex=-1) const;
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Liste kutusundaki bir öğenin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Maddeyle ilişkili veriler; veya öğe yoksa 0.

### <a name="remarks"></a>Açıklamalar

-1 dizin parametresi, şu anda seçili öğeyle ilişkili verileri döndürür.

## <a name="cmfctoolbarcomboboxbuttongetitemdataall"></a><a name="getitemdataall"></a>CMFCToolBarComboBoxButton::GetItemDataAll

Belirli bir komut kimliğine sahip açılan kutu düğmesinin liste kutusunda belirli bir dizindeki bir maddeyle ilişkili verileri döndürür.

```
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Açılan kutu düğmesinin komut kimliği.

*ıındex*<br/>
[içinde] Liste kutusundaki bir öğenin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa maddeyle ilişkili veriler; aksi takdirde, belirtilen dizin geçerli değilse 0 veya açılan kutu düğmesi bulunmazsa CB_ERR.

### <a name="remarks"></a>Açıklamalar

-1 dizin parametresi, şu anda seçili öğeyle ilişkili verileri döndürür.

## <a name="cmfctoolbarcomboboxbuttongetitemdataptrall"></a><a name="getitemdataptrall"></a>CMFCToolBarComboBoxButton::GetItemDataPtrAll

Belirli bir komut kimliğine sahip açılan kutu düğmesinin liste kutusunda belirli bir dizindeki bir maddeyle ilişkili verileri döndürür. Bu veriler işaretçi olarak döndürülür.

```
static void* GetItemDataPtrAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Açılan kutu düğmesinin komut kimliği.

*ıındex*<br/>
[içinde] Liste kutusundaki bir öğenin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa maddeyle ilişkili bir işaretçi; aksi takdirde, bir hata oluşursa -1 veya açılan kutu düğmesi bulunamazsa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongetprompt"></a><a name="getprompt"></a>CMFCToolBarComboBoxButton::GetPrompt

Açılan kutu düğmesi için istem dizesini döndürür.

```
virtual CString GetPrompt() const;
```

### <a name="return-value"></a>Dönüş Değeri

İstem dizesi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem şu anda uygulanmaz.

## <a name="cmfctoolbarcomboboxbuttongettext"></a><a name="gettext"></a>CMFCToolBarComboBoxButton::GetText

Metni edit kutusunu alır.

```
LPCTSTR GetText() const;
```

### <a name="return-value"></a>Dönüş Değeri

Edit kutusundaki metin.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongettextall"></a><a name="gettextall"></a>CMFCToolBarComboBoxButton::GetTextAll

Metni, belirli bir komut kimliğine sahip açılan kutu düğmesinin edit kutusuna alır.

```
static LPCTSTR GetTextAll(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Belirli bir açılan kutu düğmesinin komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı ysa, edit kutusundaki metin; aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttonhasfocus"></a><a name="hasfocus"></a>CMFCToolBarComboBoxButton::HasFocus

Açılan kutunun şu anda odak noktası olup olmadığını gösterir.

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Combo kutusu şu anda odak varsa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Açılan kutunun herhangi bir alt penceresi şu anda odak varsa bu yöntem de TRUE döndürür.

## <a name="cmfctoolbarcomboboxbuttoniscentervert"></a><a name="iscentervert"></a>CMFCToolBarComboBoxButton::IsCenterVert

Uygulamadaki açılan kutu düğmelerinin dikey konumunu döndürür.

```
static BOOL IsCenterVert();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmeler ortalanmışsa DOĞRU; Düğmeler en üstte hizalanmışsa YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttonisflatmode"></a><a name="isflatmode"></a>CMFCToolBarComboBoxButton::IsFlatMode

Uygulamada açılan kutu düğmelerinin düz stil görünümünü verir.

```
static BOOL IsFlatMode();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmelerin düz bir stili varsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Açılan kutu düğmeleri için varsayılan düz stil FALSE'dır.

## <a name="cmfctoolbarcomboboxbuttonisownerof"></a><a name="isownerof"></a>CMFCToolBarComboBoxButton::IsOwnerOf

Belirtilen tanıtıcının açılan kutu düğmesiyle mi yoksa çocuklarından biriyle mi ilişkili olduğunu gösterir.

```
virtual BOOL IsOwnerOf(HWND hwnd);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
[içinde] Pencere sapı.

### <a name="return-value"></a>Dönüş Değeri

Tutamaç açılan kutu düğmesi veya çocuklarından biri ile uyumlu ysa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cmfctoolbarcomboboxbuttonisribbonbutton"></a><a name="isribbonbutton"></a>CMFCToolBarComboBoxButton::IsRibbonButton

Açılan kutu düğmesinin şerit panelinde bulunup olmadığını gösterir.

```
BOOL IsRibbonButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem her zaman FALSE döndürür, bu da açılan kutu düğmesinin hiçbir zaman şerit panelinde görüntülenmediği anlamına gelir.

## <a name="cmfctoolbarcomboboxbuttoniswindowvisible"></a><a name="iswindowvisible"></a>CMFCToolBarComboBoxButton::IsWindowVisible

Açılan kutu düğmesinin görünürlük durumunu verir.

```
virtual BOOL IsWindowVisible();
```

### <a name="return-value"></a>Dönüş Değeri

Açılan kutu düğmesinin görünürlük durumu.

## <a name="cmfctoolbarcomboboxbuttonnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarComboBoxButton::Komut Bildir

Açılan kutu düğmesinin iletiyi çalışıp İşlemdiğini gösterir.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parametreler

*iNotifyCode*<br/>
[içinde] Komutla ilişkili bildirim iletisi.

### <a name="return-value"></a>Dönüş Değeri

Açılan kutu düğmesinin iletiyi işleyip İşlemip İşlemediği.

## <a name="cmfctoolbarcomboboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarComboBoxButton::OnAddToCustomizePage

Düğme **Özelleştir** iletişim kutusuna eklendiğinde çerçeve tarafından çağrılır.

```
virtual void OnAddToCustomizePage();
```

## <a name="cmfctoolbarcomboboxbuttononcalculatesize"></a><a name="oncalculatesize"></a>CMFCToolBarComboBoxButton::OnCalculateSize

Düğmenin boyutunu hesaplamak için çerçeve tarafından çağrılır.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Açılan kutu düğmesini görüntüleyen aygıt bağlamı.

*boyutVarsayılan*<br/>
[içinde] Açılan kutu düğmesinin varsayılan boyutu.

*bHorz*<br/>
[içinde] Ana araç çubuğunun dock durumu. Araç çubuğu yatay olarak kenetlendiğinde DOĞRU ve araç çubuğu dikey olarak kenetlendiğinde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Açılan `SIZE` kutu düğmesinin boyutlarını içeren bir yapı, pikseller halinde.

## <a name="cmfctoolbarcomboboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarComboBoxButton::OnChangeParentWnd

Açılan kutu düğmesi yeni bir araç çubuğuna takıldığında çerçeve tarafından çağrılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Yeni üst araç çubuğunu işaretçi.

## <a name="cmfctoolbarcomboboxbuttononclick"></a><a name="onclick"></a>CMFCToolBarComboBoxButton::Tıkla

Kullanıcı açılan kutu düğmesini tıklattığında çerçeve tarafından çağrılır.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Açılan kutu düğmesinin üst penceresine işaretçi.

*bGecikme*<br/>
[içinde] Türemiş bir sınıfta kullanılmak üzere ayrılmıştır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem olayı işlerse DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cmfctoolbarcomboboxbuttononctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarComboBoxButton::OnCtlColor

Kullanıcı, açılan kutu düğmesi rengini ayarlamak için ana araç çubuğu rengini değiştirdiğinde çerçeve tarafından çağrılır.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Açılan kutu düğmesini görüntüleyen aygıt bağlamı.

*nCtlColor*<br/>
[içinde] Kullanılma -yan.

### <a name="return-value"></a>Dönüş Değeri

Çerçevenin açılan kutu düğmesinin arka planını boyamak için kullandığı fırçayı işaretleyin.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ayrıca açılan kutu düğmesi metin rengini de ayarlar.

## <a name="cmfctoolbarcomboboxbuttonondraw"></a><a name="ondraw"></a>CMFCToolBarComboBoxButton::OnDraw

Belirtilen stilleri ve seçenekleri kullanarak açılan kutu düğmesini çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Düğmeyi görüntüleyen aygıt bağlamı.

*Rect*<br/>
[içinde] Düğmenin sınırlayıcı dikdörtgeni.

*pImages*<br/>
[içinde] Düğmeyle ilişkili görüntülerin toplanması.

*bHorz*<br/>
[içinde] Ana araç çubuğunun dock durumu. Araç çubuğu yatay olarak kenetlendiğinde DOĞRU ve araç çubuğu dikey olarak kenetlendiğinde FALSE.

*bCustomizeMode*<br/>
[içinde] Uygulamaözelleştirme modunda olup olmadığı.

*bVurgu*<br/>
[içinde] Açılan kutu düğmesini çizmek için olup olmadığı vurgulanır.

*bDrawBorder*<br/>
[içinde] Bir kenarlık ile açılan kutu düğmesini çizmek ister.

*bGrayDisabledButtons*<br/>
[içinde] Gölgeli devre dışı bırakılan düğmeleri çizmek için TRUE; Devre dışı bırakılmış görüntüler koleksiyonunu kullanmak için FALSE.

## <a name="cmfctoolbarcomboboxbuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFCToolBarComboBoxButton::OnDrawOnCustomizeList

**Özelleştir** iletişim kutusunun **Komutlar** bölmesinde açılan kutu düğmesini çizmek için çerçeve tarafından çağrılır.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Açılan kutu düğmesini görüntüleyen aygıt bağlamı.

*Rect*<br/>
[içinde] Açılan kutu düğmesinin sınırlayıcı dikdörtgeni.

*bSelected*<br/>
[içinde] Açılan kutu düğmesi seçilirse TRUE; aksi takdirde, YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Açılan kutu düğmesinin piksel genişliği.

## <a name="cmfctoolbarcomboboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarComboBoxButton::OnGlobalFontsDeğiştirildi

Uygulama yazı tipi değiştiğinde açılan kutu düğmesi yazı tipini ayarlamak için çerçeve tarafından çağrılır.

```
virtual void OnGlobalFontsChanged();
```

## <a name="cmfctoolbarcomboboxbuttononmove"></a><a name="onmove"></a>CMFCToolBarComboBoxButton::OnMove

Ana araç çubuğu hareket ettiğinde açılan kutu düğmesinin konumunu değiştirmek için çerçeve tarafından çağrılır.

```
virtual void OnMove();
```

## <a name="cmfctoolbarcomboboxbuttononshow"></a><a name="onshow"></a>CMFCToolBarComboBoxButton::AçıkGöster

Açılan kutu düğmesi gizlendiğinde veya görüntülendiğinde çerçeve tarafından çağrılır.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bGöster*<br/>
[içinde] Açılan kutu düğmesini gizlemek veya görüntülemek ister.

## <a name="cmfctoolbarcomboboxbuttononsize"></a><a name="onsize"></a>CMFCToolBarComboBoxButton::Boyut

Ana araç çubuğu boyutunu değiştirdiğinde açılan kutu düğmesinin boyutunu değiştirmek için çerçeve tarafından çağrılır.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parametreler

*iSize*<br/>
[içinde] Açılan kutu düğmesinin yeni genişliği.

## <a name="cmfctoolbarcomboboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarComboBoxButton::OnUpdateToolTip

Kullanıcı açılan kutu düğmesi için araç ipucunu değiştirdiğinde çerçeve tarafından çağrılır.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Açılan kutu düğmesi için ana pencereyi işaretleyin.

*iButtonIndex*<br/>
[içinde] Açılan kutu düğmesinin kimliği.

*wndToolTip*<br/>
[içinde] Açılan kutu düğmesiyle ilişkilendirilen araç ucu.

*Str*<br/>
[içinde] Araç ipucu metni.

### <a name="return-value"></a>Dönüş Değeri

Yöntem olayı işlerse DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cmfctoolbarcomboboxbuttonremoveallitems"></a><a name="removeallitems"></a>CMFCToolBarComboBoxButton::RemoveAllItems

Listeden tüm öğeleri siler ve kutuları düzenle.

```
void RemoveAllItems();
```

### <a name="remarks"></a>Açıklamalar

Liste kutusundaki tüm öğeleri kaldırır ve açılan kutunun denetimini denetler.

## <a name="cmfctoolbarcomboboxbuttonselectitem"></a><a name="selectitem"></a>CMFCToolBarComboBoxButton::SelectItem

Liste kutusundabir öğe seçer.

```
BOOL SelectItem(
    int iIndex,
    BOOL bNotify=TRUE);

BOOL SelectItem(DWORD_PTR dwData);
BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Liste kutusundaki bir öğenin sıfır tabanlı dizin.

*bNotify*<br/>
[içinde] DOĞRU seçim açılan kutu düğmesini bildirmek için; aksi takdirde YANLIŞ.

*Dwdata*<br/>
[içinde] Liste kutusundaki bir öğeyle ilişkili veriler.

*lpszMetin*<br/>
[içinde] Liste kutusundaki bir öğenin metni.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olsaydı DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttonselectitemall"></a><a name="selectitemall"></a>CMFCToolBarComboBoxButton::SelectItemAll

Belirli bir komut kimliğine sahip açılan kutu düğmesinin liste kutusunda bir öğe seçer.

```
static BOOL SelectItemAll(
    UINT uiCmd,
    int iIndex);

static BOOL SelectItemAll(
    UINT uiCmd,
    DWORD_PTR dwData);

static BOOL SelectItemAll(
    UINT uiCmd,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Liste kutusunu içeren açılan kutu düğmesinin komut kimliği.

*ıındex*<br/>
[içinde] Liste kutusundaki öğenin sıfır tabanlı dizin. -1 değeri liste kutusundaki geçerli seçimi kaldırır ve denetim kutusunu temizler.

*Dwdata*<br/>
[içinde] Liste kutusundaki bir öğenin verileri.

*lpszMetin*<br/>
[içinde] Liste kutusundaki bir öğenin metni.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olsaydı DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttonserialize"></a><a name="serialize"></a>CMFCToolBarComboBoxButton::Serialize

Bu nesneyi arşivden okur veya arşive yazar.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
[içinde, dışarı] Serihale `CArchive` getirmek için nesne.

### <a name="remarks"></a>Açıklamalar

Nesnedeki `CArchive` ayarlar, bu yöntemin arşivi okuyup okumayacağını veya yazıp yazmayacağını belirler.

## <a name="cmfctoolbarcomboboxbuttonsetaccdata"></a><a name="setaccdata"></a>CMFCToolBarComboBoxButton::SetACCData

Açılan kutu `CAccessibilityData` düğmesinden erişilebilirlik verilerini kullanarak belirtilen nesneyi doldurur.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
[içinde] Açılan kutu düğmesinin ana penceresi.

*Veri*<br/>
[çıkış] Açılan `CAccessibilityData` kutu düğmesinden erişilebilirlik verilerini alan bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olsaydı DOĞRU; aksi takdirde YANLIŞ.

## <a name="cmfctoolbarcomboboxbuttonsetcentervert"></a><a name="setcentervert"></a>CMFCToolBarComboBoxButton:SetCenterVert

Uygulamadaki açılan kutu düğmelerinin dikey konumunu ayarlar.

```
static void SetCenterVert(BOOL bCenterVert=TRUE);
```

### <a name="parameters"></a>Parametreler

*bCenterVert*<br/>
[içinde] Araç çubuğundaki açılan kutu düğmesini ortalamak için TRUE; Combo box düğmesini araç çubuğunun üst bölümüne hizalamak için FALSE.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, açılan kutu düğmeleri en üste hizalanır.

## <a name="cmfctoolbarcomboboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a>CMFCToolBarComboBoxButton::SetContextMenuID

Açılan kutu düğmesi için kısayol menü kaynak kimliğini ayarlar.

```
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>Parametreler

*uiResID*<br/>
[içinde] Kısayol menüsü kaynak kimliği.

## <a name="cmfctoolbarcomboboxbuttonsetdropdownheight"></a><a name="setdropdownheight"></a>CMFCToolBarComboBoxButton::SetDropDownHeight

Liste kutusunun yüksekliğini aşağı bırakıldığında ayarlar.

```
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>Parametreler

*Nheight*<br/>
[içinde] Liste kutusunun yüksekliği, piksel olarak.

### <a name="remarks"></a>Açıklamalar

Varsayılan yükseklik 150 pikseldir.

## <a name="cmfctoolbarcomboboxbuttonsetflatmode"></a><a name="setflatmode"></a>CMFCToolBarComboBoxButton::SetFlatMode

Uygulamada açılan kutu düğmelerinin düz stil görünümünü ayarlar.

```
static void SetFlatMode(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>Parametreler

*bDüz*<br/>
[içinde] Düz bir stil görünümü için DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Açılan kutu düğmeleri için varsayılan düz stil FALSE'dır.

## <a name="cmfctoolbarcomboboxbuttonsetstyle"></a><a name="setstyle"></a>CMFCToolBarComboBoxButton::SetStyle

Açılan kutu düğmesi için belirtilen stili ayarlar ve devre dışı bırakılmazsa denetimi yeniden çizer.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
[içinde] Araç çubuğu stillerinin bitwise kombinasyonu (VEYA).

### <a name="remarks"></a>Açıklamalar

Araç çubuğu düğme stilleri listesi için [ToolBar Control Styles'a](../../mfc/reference/toolbar-control-styles.md) bakın

## <a name="cmfctoolbarcomboboxbuttonsettext"></a><a name="settext"></a>CMFCToolBarComboBoxButton::SetText

Metni açılan kutu düğmesinin edit kutusunda ayarlar.

```
void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
[içinde] Edit kutusu için metin içeren bir dize işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton Sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
