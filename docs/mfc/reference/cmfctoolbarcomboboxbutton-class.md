---
description: 'Daha fazla bilgi edinin: CMFCToolBarComboBoxButton sınıfı'
title: CMFCToolBarComboBoxButton sınıfı
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
ms.openlocfilehash: aa28d1b125a5e1baf56a9e6e10812e7e6e56312f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163918"
---
# <a name="cmfctoolbarcomboboxbutton-class"></a>CMFCToolBarComboBoxButton sınıfı

Birleşik giriş kutusu denetimi ( [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)) içeren bir araç çubuğu düğmesi.

## <a name="syntax"></a>Syntax

```
class CMFCToolBarComboBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarComboBoxButton:: CMFCToolBarComboBoxButton](#cmfctoolbarcomboboxbutton)|Bir oluşturur `CMFCToolBarComboBoxButton` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarComboBoxButton:: AddItem](#additem)|Birleşik giriş kutusu listesinin sonuna bir öğe ekler.|
|[CMFCToolBarComboBoxButton:: Addsortedidıtem](#addsorteditem)|Birleşik giriş kutusu listesine bir öğe ekler. Listedeki öğelerin sırası tarafından belirtilir `Compare` .|
|[CMFCToolBarComboBoxButton:: Compare](#compare)|İki öğeyi karşılaştırır. `AddSortedItems`Birleşik giriş kutusu listesine ekleyen öğeleri sıralamak için çağırılır.|
|[CMFCToolBarComboBoxButton:: CreateEdit](#createedit)|Birleşik giriş kutusu düğmesi için yeni bir düzenleme denetimi oluşturur.|
|[CMFCToolBarComboBoxButton::D Eleteıtem](#deleteitem)|Birleşik giriş kutusu listesinden bir öğeyi siler.|
|[CMFCToolBarComboBoxButton:: FindItem](#finditem)|Belirtilen dizeyi içeren öğenin dizinini döndürür.|
|[CMFCToolBarComboBoxButton:: GetByCmd](#getbycmd)|Belirtilen komut KIMLIĞIYLE Birleşik giriş kutusu düğmesine bir işaretçi döndürür.|
|[CMFCToolBarComboBoxButton:: GetComboBox](#getcombobox)|Birleşik giriş kutusu düğmesine eklenmiş olan açılan kutu denetimine bir işaretçi döndürür.|
|[CMFCToolBarComboBoxButton:: GetCount](#getcount)|Birleşik giriş kutusu listesindeki öğe sayısını döndürür.|
|[CMFCToolBarComboBoxButton:: GetCountAll](#getcountall)|Belirtilen komut KIMLIĞINE sahip olan Birleşik giriş kutusu düğmesini bulur. Bu düğmenin Birleşik giriş kutusu listesindeki öğe sayısını döndürür.|
|[CMFCToolBarComboBoxButton:: GetCurSel](#getcursel)|Birleşik giriş kutusu listesindeki seçili öğenin dizinini döndürür.|
|[CMFCToolBarComboBoxButton:: GetCurSelAll](#getcurselall)|Belirtilen komut KIMLIĞINE sahip olan Birleşik giriş kutusu düğmesini bulur ve bu düğmenin Birleşik giriş kutusu listesindeki seçili öğenin dizinini döndürür.|
|[CMFCToolBarComboBoxButton:: GetEditCtrl](#geteditctrl)|Birleşik giriş kutusu düğmesine katıştırılmış düzenleme denetimine bir işaretçi döndürür.|
|[CMFCToolBarComboBoxButton:: GetItem](#getitem)|Birleşik giriş kutusu listesinde belirtilen bir dizinle ilişkili dizeyi döndürür.|
|[CMFCToolBarComboBoxButton:: Getıtemall](#getitemall)|Belirtilen komut KIMLIĞINE sahip olan Birleşik giriş kutusu düğmesini bulur ve bu düğmenin Birleşik giriş kutusu listesindeki bir dizinle ilişkili dizeyi döndürür.|
|[CMFCToolBarComboBoxButton:: GetItemData](#getitemdata)|Birleşik giriş kutusu listesinde belirtilen bir dizinle ilişkili 32 bitlik değeri döndürür.|
|[CMFCToolBarComboBoxButton:: Getıtemdataall](#getitemdataall)|Belirtilen komut KIMLIĞINE sahip olan Birleşik giriş kutusu düğmesini bulur ve bu düğmenin Birleşik giriş kutusu listesindeki bir dizinle ilişkili 32 bitlik değeri döndürür.|
|[CMFCToolBarComboBoxButton:: Getıtemdataptrall](#getitemdataptrall)|Belirtilen komut KIMLIĞINE sahip olan Birleşik giriş kutusu düğmesini bulur. Bu düğmenin Birleşik giriş kutusu listesinde bir dizin ile ilişkilendirilmiş 32 bitlik değeri alır ve bir işaretçi olarak 32 bit değeri döndürür.|
|[CMFCToolBarComboBoxButton:: GetText](#gettext)|Birleşik giriş kutusunun düzenleme denetimindeki metni döndürür.|
|[CMFCToolBarComboBoxButton:: GetTextAll](#gettextall)|Belirtilen komut KIMLIĞINE sahip olan Birleşik giriş kutusu düğmesini bulur ve bu düğmenin düzenleme denetiminden metni döndürür.|
|[CMFCToolBarComboBoxButton:: SCC](#iscentervert)|Uygulamadaki Birleşik giriş kutusu düğmelerinin araç çubuğunun üst ile ortalanmasını veya hizalanıp hizalanmayacağını belirler.|
|[CMFCToolBarComboBoxButton:: ısyataymode](#isflatmode)|Uygulamadaki Birleşik giriş kutusu düğmelerinin düz bir görünüme sahip olup olmadığını belirler.|
|[CMFCToolBarComboBoxButton:: Removeallıtems](#removeallitems)|Tüm öğeleri liste kutusundan kaldırır ve Birleşik giriş kutusunun düzenleme denetimi.|
|[CMFCToolBarComboBoxButton:: SelectItem](#selectitem)|Dizin, 32-bit değeri veya dizeye göre Birleşik giriş kutusunda bir öğe seçer ve seçim hakkında Birleşik giriş kutusu denetimine bildirir.|
|[CMFCToolBarComboBoxButton:: Selectıtemall](#selectitemall)|Belirtilen komut KIMLIĞINE sahip olan Birleşik giriş kutusu düğmesini bulur. `SelectItem`Bu düğmenin Birleşik giriş kutusunda dize, dizin veya 32-bit değerine göre bir öğe seçmek için çağırır.|
|[CMFCToolBarComboBoxButton:: SetCenterVert](#setcentervert)|Uygulamadaki Birleşik giriş kutusu düğmelerinin, araç çubuğunun üst ile dikey mi yoksa hizalı mi olacağını belirtir.|
|[CMFCToolBarComboBoxButton:: SetDropDownHeight](#setdropdownheight)|Açılan liste kutusunun yüksekliğini ayarlar.|
|[CMFCToolBarComboBoxButton:: Setyataymod](#setflatmode)|Uygulamadaki Birleşik giriş kutusu düğmelerinin düz bir görünüme sahip olup olmadığını belirtir.|

## <a name="remarks"></a>Açıklamalar

Bir araç çubuğuna Birleşik giriş kutusu düğmesi eklemek için aşağıdaki adımları izleyin:

1. Ana araç çubuğu kaynağında düğme için bir kukla kaynak KIMLIĞI ayırın.

2. Bir `CMFCToolBarComboBoxButton` nesne oluşturun.

3. AFX_WM_RESETTOOLBAR iletisini işleyen ileti işleyicisinde, [CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)öğesini kullanarak kukla düğmesini Yeni Birleşik giriş kutusu düğmesiyle değiştirin.

Daha fazla bilgi için bkz. [Izlenecek yol: denetimleri araç çubuklarına yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md). Birleşik giriş kutusu araç çubuğu düğmesine bir örnek için bkz. VisualStudioDemo örnek projesi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir `CMFCToolBarComboBoxButton` . Örnek, düzenleme ve Birleşik giriş kutularının nasıl etkinleştirileceğini, uygulamadaki Birleşik giriş kutusu düğmelerinin dikey konumunu ayarlamayı, açılan liste kutusunun yüksekliğini ayarlamayı, uygulamadaki Birleşik giriş kutusu düğmelerinin düz stil görünümünü ayarlamayı ve Birleşik giriş kutusu düğmesinin düzenleme kutusunda metni ayarlamayı gösterir. Bu kod parçacığı, [Visual Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbarcomboboxbutton. h

## <a name="cmfctoolbarcomboboxbuttonadditem"></a><a name="additem"></a> CMFCToolBarComboBoxButton:: AddItem

Liste kutusuna benzersiz bir öğe ekler.

```
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Parametreler

*lpszItem*<br/>
'ndaki Liste kutusuna eklenecek öğenin metni.

*dwData*<br/>
'ndaki Liste kutusuna eklenecek öğeyle ilişkili veriler.

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki son öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Liste kutusu stili sıralandığında bu yöntemi kullanmayın.

Öğe metni liste kutusunda zaten varsa, yeni veriler varolan öğeyle birlikte depolanır. Öğe için arama büyük/küçük harfe duyarlıdır.

## <a name="cmfctoolbarcomboboxbuttonaddsorteditem"></a><a name="addsorteditem"></a> CMFCToolBarComboBoxButton:: Addsortedidıtem

[Compare](#compare) yöntemi tarafından tanımlanan sırada liste kutusuna bir öğe ekler.

```
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Parametreler

*lpszItem*<br/>
'ndaki Liste kutusuna eklenecek öğenin metni.

*dwData*<br/>
'ndaki Liste kutusuna eklenecek öğeyle ilişkili veriler.

### <a name="return-value"></a>Dönüş Değeri

Liste kutusuna eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Liste kutusuna belirli bir sırada öğe eklemek için bu işlevi kullanın.

## <a name="cmfctoolbarcomboboxbuttoncanbestretched"></a><a name="canbestretched"></a> CMFCToolBarComboBoxButton:: Canbeesnetilen

Birleşik giriş kutusu düğme boyutunun değişebilir olup olmadığını gösterir.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE değerini döndürür.

## <a name="cmfctoolbarcomboboxbuttoncmfctoolbarcomboboxbutton"></a><a name="cmfctoolbarcomboboxbutton"></a> CMFCToolBarComboBoxButton:: CMFCToolBarComboBoxButton

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) nesnesi oluşturur.

```
CMFCToolBarComboBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=CBS_DROPDOWNLIST,
    int iWidth=0);
```

### <a name="parameters"></a>Parametreler

*Uııd*<br/>
'ndaki Yeni düğmenin komut KIMLIĞI.

*IImage*<br/>
'ndaki Yeni düğmeyle ilişkili görüntünün görüntü dizini.

*dwStyle*<br/>
'ndaki Yeni düğmenin stili.

*ıwidth*<br/>
'ndaki Yeni düğmenin piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

Varsayılan genişlik 150 pikseldir.

Araç çubuğu düğmesi stillerinin listesi için bkz. [ToolBar denetim stilleri](../../mfc/reference/toolbar-control-styles.md)

## <a name="cmfctoolbarcomboboxbuttoncleardata"></a><a name="cleardata"></a> CMFCToolBarComboBoxButton:: ClearData

Kullanıcı tanımlı verileri siler.

```
virtual void ClearData();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem hiçbir şey yapmaz. Kullanıcı tanımlı herhangi bir veriyi silmek istiyorsanız türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctoolbarcomboboxbuttoncompare"></a><a name="compare"></a> CMFCToolBarComboBoxButton:: Compare

İki dizeyi karşılaştırır.

```
virtual int Compare(
    LPCTSTR lpszItem1,
    LPCTSTR lpszItem2);
```

### <a name="parameters"></a>Parametreler

*lpszItem1*<br/>
'ndaki Karşılaştırılacak ilk dize.

*lpszItem2*<br/>
'ndaki Karşılaştırılacak ikinci dize.

### <a name="return-value"></a>Dönüş Değeri

Dizeler arasındaki büyük/küçük harfe duyarlı lexicographic ilişkisini gösteren bir değer. Aşağıdaki tabloda olası değerler listelenmiştir:

|Değer|Açıklama|
|-----------|-----------------|
|\<0|İlk dize ikinciden daha küçüktür.|
|0|İlk dize ikincisine eşittir.|
|>0|İlk dize ikinciden büyük.|

### <a name="remarks"></a>Açıklamalar

Öğelerin liste kutusunda nasıl sıralanacağını değiştirmek için bu yöntemi geçersiz kılın.

Karşılaştırma büyük/küçük harfe duyarlıdır.

Bu yöntem yalnızca [Addsortedidıtem](#addsorteditem) yönteminden çağırılır.

## <a name="cmfctoolbarcomboboxbuttoncopyfrom"></a><a name="copyfrom"></a> CMFCToolBarComboBoxButton:: CopyFrom

Belirtilen durumunu `CMFCToolBarComboBoxButton` geçerli nesneye kopyalar.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
'ndaki Kaynak `CMFCToolBarComboBoxButton` nesne.

## <a name="cmfctoolbarcomboboxbuttoncreatecombo"></a><a name="createcombo"></a> CMFCToolBarComboBoxButton:: CreateCombo

Birleşik giriş kutusu düğmesi için yeni bir Birleşik giriş kutusu oluşturur.

```
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Düğmenin üst penceresine yönelik bir işaretçi.

*Rect*<br/>
'ndaki Birleşik giriş kutusunun sınırlayıcı dikdörtgeni.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa yeni Birleşik giriş kutusu işaretçisi. Aksi takdirde, NULL.

## <a name="cmfctoolbarcomboboxbuttoncreateedit"></a><a name="createedit"></a> CMFCToolBarComboBoxButton:: CreateEdit

Birleşik giriş kutusu düğmesi için yeni bir düzenleme kutusu oluşturur.

```
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Düğmenin üst penceresine yönelik bir işaretçi.

*Rect*<br/>
'ndaki Yeni düzenleme kutusunun sınırlayıcı dikdörtgeni.

*dwEditStyle*<br/>
'ndaki Yeni düzenleme kutusunun denetim stili.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa yeni düzenleme kutusu işaretçisi; Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Çerçeve, Birleşik giriş kutusu düğmesi için yeni bir düzenleme kutusu oluşturduğunda bu yöntemi çağırır. [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md) 'in nasıl oluşturulduğunu değiştirmek için bu yöntemi geçersiz kılın.

## <a name="cmfctoolbarcomboboxbuttondeleteitem"></a><a name="deleteitem"></a> CMFCToolBarComboBoxButton::D Eleteıtem

Liste kutusundan belirtilen bir öğeyi siler.

```
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);
BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Silinecek öğenin sıfır tabanlı dizini.

*dwData*<br/>
'ndaki Silinecek öğeyle ilişkili veriler.

*lpszText*<br/>
'ndaki Silinecek öğenin metni. Aynı metne sahip birden fazla öğe varsa, ilk öğe silinir.

### <a name="return-value"></a>Dönüş Değeri

Öğe bulunuyorsa ve başarıyla silinmişse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttonduplicatedata"></a><a name="duplicatedata"></a> CMFCToolBarComboBoxButton: Upereptedata:D

Kullanıcı tanımlı verileri çoğaltır.

```
virtual void DuplicateData();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem hiçbir şey yapmaz. Kullanıcı tanımlı herhangi bir veriyi kopyalamak istiyorsanız türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctoolbarcomboboxbuttonenablewindow"></a><a name="enablewindow"></a> CMFCToolBarComboBoxButton:: EnableWindow

Düzenleme ve Birleşik giriş kutularını etkinleştirilir veya devre dışı bırakır.

```
virtual void EnableWindow(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Düzenleme ve Birleşik giriş kutularını etkinleştirmek için TRUE; Düzenleme ve Birleşik giriş kutularını devre dışı bırakmak için FALSE.

### <a name="remarks"></a>Açıklamalar

Devre dışı bırakıldığında, denetimler etkin hale gelir ve Kullanıcı girişini kabul edemez.

## <a name="cmfctoolbarcomboboxbuttonexporttomenubutton"></a><a name="exporttomenubutton"></a> CMFCToolBarComboBoxButton:: Exporttomenubtan

Uygulama dizesi tablosundan bir dizeyi, Birleşik giriş kutusu düğmesi komut KIMLIĞI ' ni kullanarak belirtilen menüye kopyalar.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parametreler

*menuButton*<br/>
dışı Bir menü düğmesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE.

## <a name="cmfctoolbarcomboboxbuttonfinditem"></a><a name="finditem"></a> CMFCToolBarComboBoxButton:: FindItem

Liste kutusundaki, belirtilen dizeyi içeren ilk öğenin dizinini döndürür.

```
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
'ndaki Liste kutusunda Aranacak metin.

### <a name="return-value"></a>Dönüş Değeri

Öğenin dizini; ya da öğe bulunmazsa CB_ERR.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongetbycmd"></a><a name="getbycmd"></a> CMFCToolBarComboBoxButton:: GetByCmd

Belirtilen komut KIMLIĞINE sahip olan Birleşik giriş kutusu düğmesine bir işaretçi alır.

```
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,
    BOOL bIsFocus=FALSE);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Birleşik giriş kutusu düğmesinin komut KIMLIĞI.

*bIsFocus*<br/>
'ndaki Yalnızca odaklanmış düğmeleri aramak için TRUE; Tüm düğmeleri aramak için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusu düğmesi işaretçisi; ya da düğme bulunamazsa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongetcombobox"></a><a name="getcombobox"></a> CMFCToolBarComboBoxButton:: GetComboBox

Birleşik giriş kutusu düğmesinde Birleşik giriş kutusuna bir işaretçi döndürür.

```
CComboBox* GetComboBox() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md) nesnesine yönelik bir işaretçi; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a> CMFCToolBarComboBoxButton:: GetContextMenuID

Birleşik giriş kutusu düğmesi için kısayol menüsü kaynak KIMLIĞINI alır.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Dönüş Değeri

Kısayol menüsü kaynak KIMLIĞI.

## <a name="cmfctoolbarcomboboxbuttongetcount"></a><a name="getcount"></a> CMFCToolBarComboBoxButton:: GetCount

Liste kutusundaki öğe sayısını döndürür.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongetcountall"></a><a name="getcountall"></a> CMFCToolBarComboBoxButton:: GetCountAll

Belirtilen komut KIMLIĞINE sahip bir açılan kutu düğmesinin liste kutusunda bulunan öğe sayısını alır.

```
static int GetCountAll(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Birleşik giriş kutusu düğmesinin komut KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki öğelerin sayısı; Aksi takdirde, Birleşik giriş kutusu düğmesi bulunmazsa CB_ERR.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongetcursel"></a><a name="getcursel"></a> CMFCToolBarComboBoxButton:: GetCurSel

Liste kutusunda şu anda seçili olan öğenin dizinini alır.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusunda şu anda seçili olan öğenin dizini; veya seçili öğe yoksa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Liste kutusu dizini sıfır tabanlıdır.

## <a name="cmfctoolbarcomboboxbuttongetcurselall"></a><a name="getcurselall"></a> CMFCToolBarComboBoxButton:: GetCurSelAll

Belirtilen komut KIMLIĞINE sahip bir açılan kutu düğmesinin liste kutusunda şu anda seçili olan öğenin dizinini döndürür.

```
static int GetCurSelAll(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Birleşik giriş kutusu düğmesinin komut KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Liste kutusunda şu anda seçili olan öğenin dizini; Aksi takdirde, hiçbir öğe seçilmezse veya bir Birleşik giriş kutusu düğmesi bulunmazsa CB_ERR.

### <a name="remarks"></a>Açıklamalar

Liste kutusu dizini sıfır tabanlıdır.

## <a name="cmfctoolbarcomboboxbuttongeteditctrl"></a><a name="geteditctrl"></a> CMFCToolBarComboBoxButton:: GetEditCtrl

Birleşik giriş kutusu düğmesinde düzenleme kutusuna bir işaretçi döndürür.

```
virtual CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa düzenleme kutusu işaretçisi. Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongethwnd"></a><a name="gethwnd"></a> CMFCToolBarComboBoxButton:: GetHwnd

Birleşik giriş kutusu için pencere tanıtıcısını döndürür.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Dönüş Değeri

Pencere tutamacı veya Birleşik giriş kutusu bir pencere nesnesiyle ilişkilendirilmediği takdirde NULL.

## <a name="cmfctoolbarcomboboxbuttongetitem"></a><a name="getitem"></a> CMFCToolBarComboBoxButton:: GetItem

Liste kutusunda belirtilen dizindeki bir öğeyle ilişkili dizeyi döndürür.

```
LPCTSTR GetItem(int iIndex=-1) const;
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Liste kutusunda bir öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Öğeyle ilişkili dizeye yönelik bir işaretçi; Aksi takdirde, Index parametresi geçersizse veya Index parametresi-1 ise ve Birleşik giriş kutusunda seçili öğe yoksa NULL olur.

### <a name="remarks"></a>Açıklamalar

-1 ' in bir dizin parametresi, şu anda seçili olan öğenin dizesini döndürür.

## <a name="cmfctoolbarcomboboxbuttongetitemall"></a><a name="getitemall"></a> CMFCToolBarComboBoxButton:: Getıtemall

Belirtilen bir komut KIMLIĞINE sahip bir açılan kutu düğmesinin liste kutusunda belirtilen dizindeki bir öğeyle ilişkili dizeyi döndürür.

```
static LPCTSTR GetItemAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Birleşik giriş kutusu düğmesinin komut KIMLIĞI.

*IIndex*<br/>
'ndaki Liste kutusundaki bir öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa öğenin dize işaretçisi. Aksi takdirde, dizin geçersiz ise, Birleşik giriş kutusu düğmesi bulunmaz veya dizin-1 ise ve Birleşik giriş kutusunda seçili öğe yoksa, NULL olur.

### <a name="remarks"></a>Açıklamalar

-1 ' in bir dizin değeri, şu anda seçili olan öğenin dizesini döndürür.

## <a name="cmfctoolbarcomboboxbuttongetitemdata"></a><a name="getitemdata"></a> CMFCToolBarComboBoxButton:: GetItemData

Liste kutusunda belirli bir dizindeki bir öğeyle ilişkili verileri döndürür.

```
DWORD_PTR GetItemData(int iIndex=-1) const;
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Liste kutusundaki bir öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Öğeyle ilişkili veriler; ya da öğe yoksa 0.

### <a name="remarks"></a>Açıklamalar

-1 Dizin parametresi, şu anda seçili olan öğeyle ilişkili verileri döndürür.

## <a name="cmfctoolbarcomboboxbuttongetitemdataall"></a><a name="getitemdataall"></a> CMFCToolBarComboBoxButton:: Getıtemdataall

Belirli bir komut KIMLIĞI olan Birleşik giriş kutusu düğmesinin liste kutusunda belirli bir dizindeki bir öğeyle ilişkili verileri döndürür.

```
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Birleşik giriş kutusu düğmesinin komut KIMLIĞI.

*IIndex*<br/>
'ndaki Liste kutusundaki bir öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa öğeyle ilişkili veriler; Aksi takdirde, belirtilen dizin geçerli değilse 0 veya Birleşik giriş kutusu düğmesi bulunmazsa CB_ERR.

### <a name="remarks"></a>Açıklamalar

-1 Dizin parametresi, şu anda seçili olan öğeyle ilişkili verileri döndürür.

## <a name="cmfctoolbarcomboboxbuttongetitemdataptrall"></a><a name="getitemdataptrall"></a> CMFCToolBarComboBoxButton:: Getıtemdataptrall

Belirli bir komut KIMLIĞI olan Birleşik giriş kutusu düğmesinin liste kutusunda belirli bir dizindeki bir öğeyle ilişkili verileri döndürür. Bu veriler bir işaretçi olarak döndürülür.

```
static void* GetItemDataPtrAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Birleşik giriş kutusu düğmesinin komut KIMLIĞI.

*IIndex*<br/>
'ndaki Liste kutusundaki bir öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa öğeyle ilişkili bir işaretçi; Aksi takdirde, bir hata oluşursa-1 veya Birleşik giriş kutusu düğmesi bulunmazsa NULL değeri boş olur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongetprompt"></a><a name="getprompt"></a> CMFCToolBarComboBoxButton:: GetPrompt

Birleşik giriş kutusu düğmesi için istem dizesini döndürür.

```
virtual CString GetPrompt() const;
```

### <a name="return-value"></a>Dönüş Değeri

İstem dizesi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem şu anda uygulanmadı.

## <a name="cmfctoolbarcomboboxbuttongettext"></a><a name="gettext"></a> CMFCToolBarComboBoxButton:: GetText

Düzenleme kutusunda metni alır.

```
LPCTSTR GetText() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düzenleme kutusundaki metin.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttongettextall"></a><a name="gettextall"></a> CMFCToolBarComboBoxButton:: GetTextAll

Belirtilen komut KIMLIĞINE sahip bir açılan kutu düğmesinin düzenleme kutusunda bulunan metni alır.

```
static LPCTSTR GetTextAll(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Belirli bir açılan kutu düğmesinin komut KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa düzenleme kutusundaki metin; Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttonhasfocus"></a><a name="hasfocus"></a> CMFCToolBarComboBoxButton:: HasFocus

Birleşik giriş kutusunun odağa sahip olup olmadığını gösterir.

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusunda şu anda odak varsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem aynı zamanda Birleşik giriş kutusunun herhangi bir alt penceresinde odağa sahipse TRUE değerini döndürür.

## <a name="cmfctoolbarcomboboxbuttoniscentervert"></a><a name="iscentervert"></a> CMFCToolBarComboBoxButton:: SCC

Uygulamadaki Birleşik giriş kutusu düğmelerinin dikey konumunu döndürür.

```
static BOOL IsCenterVert();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmeler ortalandıysanız doğru; Düğmeler en üste hizalanmışsa FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttonisflatmode"></a><a name="isflatmode"></a> CMFCToolBarComboBoxButton:: ısyataymode

Uygulamadaki Birleşik giriş kutusu düğmelerinin düz stil görünümünü döndürür.

```
static BOOL IsFlatMode();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmelerin düz bir stili varsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Birleşik giriş kutusu düğmelerinin varsayılan düz stili FALSE şeklindedir.

## <a name="cmfctoolbarcomboboxbuttonisownerof"></a><a name="isownerof"></a> CMFCToolBarComboBoxButton:: IsOwnerOf

Belirtilen tanıtıcının Birleşik giriş kutusu düğmesiyle mi yoksa alt öğelerinden biri ile mi ilişkili olduğunu gösterir.

```
virtual BOOL IsOwnerOf(HWND hwnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki Bir pencere tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Tanıtıcı, Birleşik giriş kutusu düğmesi veya alt öğelerinden biri ile asılanalıyorsa TRUE. Aksi takdirde, FALSE.

## <a name="cmfctoolbarcomboboxbuttonisribbonbutton"></a><a name="isribbonbutton"></a> CMFCToolBarComboBoxButton:: ısribbonbutton

Birleşik giriş kutusu düğmesinin bir şerit panelinde bulunup bulunmadığını gösterir.

```
BOOL IsRibbonButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem her zaman FALSE değerini döndürür; bu, Birleşik giriş kutusu düğmesinin bir şerit panelinde hiçbir zaman gösterilmediği anlamına gelir.

## <a name="cmfctoolbarcomboboxbuttoniswindowvisible"></a><a name="iswindowvisible"></a> CMFCToolBarComboBoxButton:: IsWindowVisible

Birleşik giriş kutusu düğmesinin görünürlük durumunu döndürür.

```
virtual BOOL IsWindowVisible();
```

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusu düğmesinin görünürlük durumu.

## <a name="cmfctoolbarcomboboxbuttonnotifycommand"></a><a name="notifycommand"></a> CMFCToolBarComboBoxButton:: NotifyCommand

Birleşik giriş kutusu düğmesinin iletiyi işlemesinin gerekip gerekmediğini gösterir.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parametreler

*iNotifyCode*<br/>
'ndaki Komutuyla ilişkili bildirim iletisi.

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusu düğmesinin iletiyi işleme olup olmadığı.

## <a name="cmfctoolbarcomboboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a> CMFCToolBarComboBoxButton:: OnAddToCustomizePage

Düğme **Özelleştirme** iletişim kutusuna eklendiğinde Framework tarafından çağırılır.

```
virtual void OnAddToCustomizePage();
```

## <a name="cmfctoolbarcomboboxbuttononcalculatesize"></a><a name="oncalculatesize"></a> CMFCToolBarComboBoxButton:: OnCalculateSize

Düğmenin boyutunu hesaplamak için Framework tarafından çağırılır.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Birleşik giriş kutusu düğmesini görüntüleyen cihaz bağlamı.

*sizeDefault*<br/>
'ndaki Birleşik giriş kutusu düğmesinin varsayılan boyutu.

*bHorz*<br/>
'ndaki Üst araç çubuğunun yerleştirme durumu. Araç çubuğu yatay olarak yerleştirildiğinde TRUE, araç çubuğu dikey olarak yerleştirildiğinde FALSE.

### <a name="return-value"></a>Dönüş Değeri

`SIZE`Birleşik giriş kutusu düğmesinin piksel cinsinden boyutlarını içeren bir yapı.

## <a name="cmfctoolbarcomboboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a> CMFCToolBarComboBoxButton:: OnChangeParentWnd

Birleşik giriş kutusu düğmesi yeni bir araç çubuğuna eklendiğinde Framework tarafından çağırılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Yeni üst araç çubuğuna işaretçi.

## <a name="cmfctoolbarcomboboxbuttononclick"></a><a name="onclick"></a> CMFCToolBarComboBoxButton:: OnClick

Kullanıcı açılan kutu düğmesine tıkladığında Framework tarafından çağırılır.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Birleşik giriş kutusu düğmesinin ana penceresine yönelik işaretçi.

*bDelay*<br/>
'ndaki Türetilmiş bir sınıfta kullanılmak üzere ayrılmıştır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem olayı işlediğinde doğru; Aksi takdirde, FALSE.

## <a name="cmfctoolbarcomboboxbuttononctlcolor"></a><a name="onctlcolor"></a> CMFCToolBarComboBoxButton:: OnCtlColor

Kullanıcı ana araç çubuğu rengini değiştirdiğinde, Birleşik giriş kutusu düğme rengini ayarlamak için Framework tarafından çağırılır.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Birleşik giriş kutusu düğmesini görüntüleyen cihaz bağlamı.

*nCtlColor*<br/>
'ndaki Kullanılmayan.

### <a name="return-value"></a>Dönüş Değeri

Çerçevenin Birleşik giriş kutusu düğmesinin arka planını boyamak için kullandığı fırçaya işleyin.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Birleşik giriş kutusu düğmesi metin rengini de ayarlar.

## <a name="cmfctoolbarcomboboxbuttonondraw"></a><a name="ondraw"></a> CMFCToolBarComboBoxButton:: OnDraw

Belirtilen stilleri ve seçenekleri kullanarak Birleşik giriş kutusu düğmesini çizmek için Framework tarafından çağırılır.

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

*Kökündeki*<br/>
'ndaki Düğmeyi görüntüleyen cihaz bağlamı.

*Rect*<br/>
'ndaki Düğmenin sınırlayıcı dikdörtgeni.

*Pımages*<br/>
'ndaki Düğmeyle ilişkili görüntülerin koleksiyonu.

*bHorz*<br/>
'ndaki Üst araç çubuğunun yerleştirme durumu. Araç çubuğu yatay olarak yerleştirildiğinde TRUE, araç çubuğu dikey olarak yerleştirildiğinde FALSE.

*bCustomizeMode*<br/>
'ndaki Uygulamanın özelleştirme modunda olup olmadığı.

*bHighlight*<br/>
'ndaki Birleşik giriş kutusu düğmesinin vurgulanıp çizmeyeceğini belirtir.

*bDrawBorder*<br/>
'ndaki Birleşik giriş kutusu düğmesinin bir kenarlıkla çizilmesi gerekip gerekmediğini belirtir.

*Bgride Disabledbutton*<br/>
'ndaki Gölgeli devre dışı düğmeler çizmek için TRUE; Devre dışı bırakılan görüntüler koleksiyonunu kullanmak için FALSE.

## <a name="cmfctoolbarcomboboxbuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a> CMFCToolBarComboBoxButton:: OnDrawOnCustomizeList

**Özelleştirme** Iletişim kutusunun **Komutlar** bölmesindeki Birleşik giriş kutusu düğmesini çizmek için Framework tarafından çağırılır.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Birleşik giriş kutusu düğmesini görüntüleyen cihaz bağlamı.

*Rect*<br/>
'ndaki Birleşik giriş kutusu düğmesinin sınırlayıcı dikdörtgeni.

*bSelected*<br/>
'ndaki Birleşik giriş kutusu düğmesi seçilmişse doğru; Aksi takdirde, FALSE.

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusu düğmesinin piksel cinsinden genişliği.

## <a name="cmfctoolbarcomboboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a> CMFCToolBarComboBoxButton:: OnGlobalFontsChanged

Uygulama yazı tipi değiştiğinde Birleşik giriş kutusu düğme yazı tipini ayarlamak için Framework tarafından çağırılır.

```
virtual void OnGlobalFontsChanged();
```

## <a name="cmfctoolbarcomboboxbuttononmove"></a><a name="onmove"></a> CMFCToolBarComboBoxButton:: OnMove

Ana araç çubuğu taşırken Birleşik giriş kutusu düğmesinin konumunu değiştirmek için Framework tarafından çağırılır.

```
virtual void OnMove();
```

## <a name="cmfctoolbarcomboboxbuttononshow"></a><a name="onshow"></a> CMFCToolBarComboBoxButton:: OnShow

Birleşik giriş kutusu düğmesi gizlendiği veya görüntülenirken Framework tarafından çağırılır.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
'ndaki Birleşik giriş kutusu düğmesinin gizlenmesi veya görüntülenip gösterilmesi.

## <a name="cmfctoolbarcomboboxbuttononsize"></a><a name="onsize"></a> CMFCToolBarComboBoxButton:: OnSize

Ana araç çubuğu boyutunu değiştirdiğinde Birleşik giriş kutusu düğmesinin boyutunu değiştirmek için Framework tarafından çağırılır.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parametreler

*iSize*<br/>
'ndaki Birleşik giriş kutusu düğmesinin yeni genişliği.

## <a name="cmfctoolbarcomboboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a> CMFCToolBarComboBoxButton:: OnUpdateToolTip

Kullanıcı, Birleşik giriş kutusu düğmesi için araç ipucunu değiştirdiğinde Framework tarafından çağırılır.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Birleşik giriş kutusu düğmesi için üst pencerenin işaretçisi.

*ıbuttonındex*<br/>
'ndaki Birleşik giriş kutusu düğmesinin KIMLIĞI.

*wndToolTip*<br/>
'ndaki Birleşik giriş kutusu düğmesiyle ilişkilendirilecek araç ipucu.

*üstbilgisine*<br/>
'ndaki Araç ipucu metni.

### <a name="return-value"></a>Dönüş Değeri

Yöntem olayı işlediğinde doğru; Aksi takdirde, FALSE.

## <a name="cmfctoolbarcomboboxbuttonremoveallitems"></a><a name="removeallitems"></a> CMFCToolBarComboBoxButton:: Removeallıtems

Liste ve düzenleme kutularından tüm öğeleri siler.

```cpp
void RemoveAllItems();
```

### <a name="remarks"></a>Açıklamalar

Tüm öğeleri liste kutusundan kaldırır ve Birleşik giriş kutusunun denetimini düzenleyebilir.

## <a name="cmfctoolbarcomboboxbuttonselectitem"></a><a name="selectitem"></a> CMFCToolBarComboBoxButton:: SelectItem

Liste kutusunda bir öğe seçer.

```
BOOL SelectItem(
    int iIndex,
    BOOL bNotify=TRUE);

BOOL SelectItem(DWORD_PTR dwData);
BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Liste kutusundaki bir öğenin sıfır tabanlı dizini.

*bNotify*<br/>
'ndaki Seçimin Birleşik giriş kutusu düğmesine bildirmek için TRUE; Aksi halde yanlış.

*dwData*<br/>
'ndaki Liste kutusundaki bir öğeyle ilişkili veriler.

*lpszText*<br/>
'ndaki Liste kutusundaki bir öğenin metni.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttonselectitemall"></a><a name="selectitemall"></a> CMFCToolBarComboBoxButton:: Selectıtemall

Belirtilen komut KIMLIĞINE sahip bir açılan kutu düğmesinin liste kutusunda bir öğe seçer.

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

*Uımd*<br/>
'ndaki Liste kutusunu içeren Birleşik giriş kutusu düğmesinin komut KIMLIĞI.

*IIndex*<br/>
'ndaki Liste kutusunda öğenin sıfır tabanlı dizini. -1 değeri, liste kutusunda geçerli olan seçimi kaldırır ve düzenleme kutusunu temizler.

*dwData*<br/>
'ndaki Liste kutusundaki bir öğenin verileri.

*lpszText*<br/>
'ndaki Liste kutusundaki bir öğenin metni.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctoolbarcomboboxbuttonserialize"></a><a name="serialize"></a> CMFCToolBarComboBoxButton:: Serialize

Bu nesneyi bir arşivden okur veya bir arşive yazar.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
[in, out] `CArchive` Seri hale getirilecek nesne.

### <a name="remarks"></a>Açıklamalar

Nesnesindeki ayarlar, `CArchive` Bu yöntemin Arşivi okuyup okumadığını veya yazmayacağını belirtir.

## <a name="cmfctoolbarcomboboxbuttonsetaccdata"></a><a name="setaccdata"></a> CMFCToolBarComboBoxButton:: SetACCData

Belirtilen nesneyi, `CAccessibilityData` açılan kutu düğmesinden erişilebilirlik verilerini kullanarak doldurur.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
'ndaki Birleşik giriş kutusu düğmesinin ana penceresi.

*data*<br/>
dışı `CAccessibilityData` Birleşik giriş kutusu düğmesinden erişilebilirlik verilerini alan nesne.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa doğru; Aksi halde yanlış.

## <a name="cmfctoolbarcomboboxbuttonsetcentervert"></a><a name="setcentervert"></a> CMFCToolBarComboBoxButton:: SetCenterVert

Uygulamadaki açılan kutu düğmelerinin dikey konumunu ayarlar.

```
static void SetCenterVert(BOOL bCenterVert=TRUE);
```

### <a name="parameters"></a>Parametreler

*bCenterVert*<br/>
'ndaki Araç çubuğundaki Birleşik giriş kutusu düğmesini ortalamak için TRUE; Birleşik giriş kutusu düğmesini araç çubuğunun en üstüne hizalamak için FALSE.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, Birleşik giriş kutusu düğmeleri en üste hizalanır.

## <a name="cmfctoolbarcomboboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a> CMFCToolBarComboBoxButton:: SetContextMenuID

Birleşik giriş kutusu düğmesi için kısayol menüsü kaynak KIMLIĞINI ayarlar.

```cpp
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>Parametreler

*Uırestıd*<br/>
'ndaki Kısayol menüsü kaynak KIMLIĞI.

## <a name="cmfctoolbarcomboboxbuttonsetdropdownheight"></a><a name="setdropdownheight"></a> CMFCToolBarComboBoxButton:: SetDropDownHeight

Aşağı bırakıldığında liste kutusunun yüksekliğini ayarlar.

```cpp
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>Parametreler

*nHeight*<br/>
'ndaki Liste kutusunun piksel cinsinden yüksekliği.

### <a name="remarks"></a>Açıklamalar

Varsayılan yükseklik 150 pikseldir.

## <a name="cmfctoolbarcomboboxbuttonsetflatmode"></a><a name="setflatmode"></a> CMFCToolBarComboBoxButton:: Setyataymod

Uygulamadaki Birleşik giriş kutusu düğmelerinin düz stil görünümünü ayarlar.

```
static void SetFlatMode(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>Parametreler

*bFlat*<br/>
'ndaki Düz stil görünümü için TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Birleşik giriş kutusu düğmelerinin varsayılan düz stili FALSE şeklindedir.

## <a name="cmfctoolbarcomboboxbuttonsetstyle"></a><a name="setstyle"></a> CMFCToolBarComboBoxButton:: SetStyle

Birleşik giriş kutusu düğmesi için belirtilen stili ayarlar ve devre dışı bırakılmayan denetimi yeniden çizer.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
'ndaki Araç çubuğu stillerinin bit tabanlı birleşimi (veya).

### <a name="remarks"></a>Açıklamalar

Araç çubuğu düğmesi stillerinin listesi için bkz. [ToolBar denetim stilleri](../../mfc/reference/toolbar-control-styles.md)

## <a name="cmfctoolbarcomboboxbuttonsettext"></a><a name="settext"></a> CMFCToolBarComboBoxButton:: SetText

Birleşik giriş kutusu düğmesinin düzenleme kutusunda metni ayarlar.

```cpp
void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
'ndaki Düzenleme kutusu için metni içeren bir dize işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[İzlenecek yol: araç çubuklarına denetimler yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
