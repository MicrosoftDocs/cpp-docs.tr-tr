---
title: CMFCToolBarComboBoxButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ffb17f8f38e83399ec32b792338f818cc06215dc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703787"
---
# <a name="cmfctoolbarcomboboxbutton-class"></a>CMFCToolBarComboBoxButton sınıfı
Birleşik giriş kutusu denetimi içeren bir araç çubuğu düğmesi ( [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCToolBarComboBoxButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](#cmfctoolbarcomboboxbutton)|Oluşturur bir `CMFCToolBarComboBoxButton`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::AddItem](#additem)|Açılan kutu listesi sonuna bir öğe ekler.|  
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|Birleşik giriş kutusu listesine bir öğe ekler. Listedeki öğeler tarafından belirtilen `Compare`.|  
|[CMFCToolBarComboBoxButton::Compare](#compare)|İki öğe karşılaştırır. Adlı sıralamak için bu öğeler `AddSortedItems` birleşik giriş kutusu listesine ekler.|  
|[CMFCToolBarComboBoxButton::CreateEdit](#createedit)|Yeni bir düzenleme denetimi için birleşik giriş kutusu düğmesi oluşturur.|  
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|Birleşik giriş kutusu listeden bir öğeyi siler.|  
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|Belirtilen dizeyi içeren öğenin dizinini döndürür.|  
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|Belirtilen komut kimliği ile birleşik giriş kutusu düğmesi için bir işaretçi döndürür.|  
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|Birleşik giriş kutusu düğmesi içinde gömülü birleşik giriş kutusu denetimi için bir işaretçi döndürür.|  
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|Öğe sayısı birleşik giriş kutusu liste döndürür.|  
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|Birleşik giriş kutusu düğmesi, belirtilen komut kimliğe sahip bulur Öğe sayısı birleşik giriş kutusu liste söz konusu düğmenin döndürür.|  
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|Seçili öğenin dizinini birleşik giriş kutusu liste döndürür.|  
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|Birleşik giriş, belirtilen komut kimliği olan ve seçilen öğenin dizini içinde açılan kutusu listesi söz konusu düğmenin döndürür kutusu düğmesi bulur.|  
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|Birleşik giriş kutusu düğmesi içinde gömülü düzenleme denetimi için bir işaretçi döndürür.|  
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|Belirtilen bir birleşik giriş dizini ile ilişkili dizeyi kutusu listesi döndürür.|  
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|Birleşik giriş belirtilen komut kimliği ve söz konusu düğmenin açılan kutu listesi dizini ile ilişkili dizeyi döndüren kutusu düğmesi bulur.|  
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|Belirtilen bir birleşik giriş dizini ile ilişkili 32-bit değeri kutusu listesi döndürür.|  
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|Birleşik giriş belirtilen komut kimliği vardır ve bu düğmeyi birleşik giriş kutusu listesinde bir dizini ile ilişkili 32-bit değeri döndüren kutusu düğmesi bulur.|  
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|Birleşik giriş kutusu düğmesi, belirtilen komut kimliğe sahip bulur Alır 32-bit değeri açılan kutu listesi bu düğme ve 32-bit değeri bir işaretçi döndürür bir dizinde ilişkili.|  
|[CMFCToolBarComboBoxButton::GetText](#gettext)|Birleşik giriş kutusu düzenleme denetiminden metni döndürür.|  
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|Birleşik giriş belirtilen komut kimliği ve söz konusu düğmenin düzenleme denetiminden metni döndüren kutusu düğmesi bulur.|  
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|Birleşik giriş kutusu düğmeleri uygulama ortalanmış veya araç üstüne hizalanmış belirler.|  
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|Birleşik giriş kutusu düğmeleri uygulama düz görünüm sahip olup olmadığını belirler.|  
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|Listeden tüm öğeler kutu ve birleşik giriş kutusu denetimi Düzenle kaldırır.|  
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|Birleşik giriş kutusunda, dizin, 32-bit değeri veya dize göre bir öğe seçer ve Kombo kutusu denetiminin seçim hakkında bilgilendirir.|  
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|Birleşik giriş kutusu düğmesi, belirtilen komut kimliğe sahip bulur Çağrıları `SelectItem` birleşik giriş kutusundaki söz konusu düğmenin kendi dize, dizin veya 32-bit değere göre bir öğe seçin.|  
|[CMFCToolBarComboBoxButton::SetCenterVert](#setcentervert)|Birleşik giriş kutusu düğmeleri uygulama dikey ortalanmış veya araç üstüne hizalanmış belirtir.|  
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|Aşağı açılan liste kutusunun yüksekliğini belirler.|  
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|Birleşik giriş kutusu düğmeleri uygulama düz görünüm sahip olup olmadığını belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu düğmesi için araç çubuğu eklemek için bu adımları izleyin:  
  
 1. Üst araç çubuğunda kaynağında düğme için bir işlevsiz kaynak kimliği saklı tutarız.  
  
 2. Oluşturmak bir `CMFCToolBarComboBoxButton` nesne.  
  
 3. AFX_WM_RESETTOOLBAR iletiyi işleyen ileti işleyicisi işlevsiz düğmesini kullanarak yeni bir birleşik giriş kutusu düğmesi ile değiştirin [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Daha fazla bilgi için [izlenecek yol: temel denetimler koyma araç'çubukları](../../mfc/walkthrough-putting-controls-on-toolbars.md). Örneği bir birleşik giriş kutusu araç çubuğu düğmesi için örnek proje VisualStudioDemo bakın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCToolBarComboBoxButton` sınıfı. Örnek düzenleme ve birleşik giriş kutularını etkinleştirmek, dikey konumu birleşik giriş kutusu düğmeleri uygulamada ayarlayın, bırakıldığında, liste kutusunun yüksekliğini ayarlama, birleşik giriş kutusu düğmeleri düz stil görünümünü uygulamada ayarlamak nasıl gösterir , metin düzenleme kutusuna birleşik giriş kutusu düğmesi ayarlayın. Bu kod parçacığı parçasıdır [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtoolbarcomboboxbutton.h  
  
##  <a name="additem"></a>  CMFCToolBarComboBoxButton::AddItem  
 Liste kutusuna benzersiz bir öğe ekler.  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Parametreler  
*lpszItem*<br/>
[in] Liste kutusuna eklenecek öğe metni.  
  
*dwData*<br/>
[in] Liste kutusuna eklenecek öğe ile ilişkili veriler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda son öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu stili sıralandığında, bu yöntemi kullanmayın.  
  
 Öğe metin liste kutusunda ise, yeni verileri var olan öğeyle depolanır. Öğe için arama büyük/küçük harfe duyarlıdır.  
  
##  <a name="addsorteditem"></a>  CMFCToolBarComboBoxButton::AddSortedItem  
 Bir öğe tarafından tanımlanan sırayla liste kutusuna ekler [karşılaştırma](#compare) yöntemi.  
  
```  
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Parametreler  
*lpszItem*<br/>
[in] Liste kutusuna eklenecek öğe metni.  
  
*dwData*<br/>
[in] Liste kutusuna eklenecek öğe ile ilişkili veriler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusuna eklenen öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli bir sırayla liste kutusu öğeleri eklemek için bu işlevi kullanın.  
  
##  <a name="canbestretched"></a>  CMFCToolBarComboBoxButton::CanBeStretched  
 Birleşik giriş kutusu düğme boyutu değiştirip değiştiremeyeceğini belirtir.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE değerini döndürür.  
  
##  <a name="cmfctoolbarcomboboxbutton"></a>  CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton  
 Oluşturur bir [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) nesne.  
  
```  
CMFCToolBarComboBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=CBS_DROPDOWNLIST,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>Parametreler  
*uiID*<br/>
[in] Yeni düğmesini komut kimliği.  
  
*iImage*<br/>
[in] Yeni düğmesi ile ilişkili görüntünün görüntü dizini.  
  
*dwStyle*<br/>
[in] Yeni düğmesini stili.  
  
*iWidth*<br/>
[in] Yeni düğmesini piksel cinsinden genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan genişliğini 150 pikseldir.  
  
 Araç çubuğu düğmesi stilleri bir listesi için bkz. [ToolBar denetim stilleri](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="cleardata"></a>  CMFCToolBarComboBoxButton::ClearData  
 Verileri kullanıcı tanımlı siler.  
  
```  
virtual void ClearData();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntemi hiçbir şey yapmaz. Kullanıcı tanımlı tüm verileri silmek isterseniz türetilen bir sınıfta bu yöntemi yok sayın.  
  
##  <a name="compare"></a>  CMFCToolBarComboBoxButton::Compare  
 İki dizeyi karşılaştırır.  
  
```  
virtual int Compare(
    LPCTSTR lpszItem1,  
    LPCTSTR lpszItem2);
```  
  
### <a name="parameters"></a>Parametreler  
*lpszItem1*<br/>
[in] Karşılaştırılacak ilk dize.  
  
*lpszItem2*<br/>
[in] Karşılaştırılacak ikinci dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizeler büyük/küçük harfe lexicographic ilişkisi belirten bir değer. Olası değerler aşağıdaki tabloda listelenmektedir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|\<0|İlk dize küçük ikinciden.|  
|0|Birinci dize ikinci eşittir.|  
|>0|İlk dize ikinciden büyükse.|  
  
### <a name="remarks"></a>Açıklamalar  
 Öğeleri liste kutusunda nasıl sıralanacağını değiştirmek için bu yöntemi yok sayın.  
  
 Karşılaştırma büyük/küçük harf duyarlıdır.  
  
 Bu yöntem yalnızca çağrılır [AddSortedItem](#addsorteditem) yöntemi.  
  
##  <a name="copyfrom"></a>  CMFCToolBarComboBoxButton::CopyFrom  
 Belirtilen durumunu kopyalar `CMFCToolBarComboBoxButton` geçerli nesneye.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parametreler  
*src*<br/>
[in] Kaynak `CMFCToolBarComboBoxButton` nesne.  
  
##  <a name="createcombo"></a>  CMFCToolBarComboBoxButton::CreateCombo  
 Birleşik giriş kutusu düğmesi için yeni bir birleşik giriş kutusu oluşturur.  
  
```  
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
*pWndParent*<br/>
[in] Düğmenin üst penceresine bir işaretçi.  
  
*Rect*<br/>
[in] Birleşik giriş kutusu sınırlayıcı dikdörtgenini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa yeni bir birleşik giriş kutusu için bir işaretçi; Aksi takdirde NULL.  
  
##  <a name="createedit"></a>  CMFCToolBarComboBoxButton::CreateEdit  
 Yeni bir düzenleme kutusu için birleşik giriş kutusu düğmesi oluşturur.  
  
```  
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>Parametreler  
*pWndParent*<br/>
[in] Düğmenin üst penceresine bir işaretçi.  
  
*Rect*<br/>
[in] Yeni düzenleme kutusu sınırlayıcı dikdörtgenini.  
  
*dwEditStyle*<br/>
[in] Yeni düzenleme kutusu denetim stili.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa yeni bir düzenleme kutusu için bir işaretçi; Aksi takdirde NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu düğmesi için yeni bir düzenleme kutusuna oluşturduğunda framework bu yöntemi çağırır. Değiştirmek için bu yöntemi yok sayın nasıl [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md) oluşturulur.  
  
##  <a name="deleteitem"></a>  CMFCToolBarComboBoxButton::DeleteItem  
 Belirtilen öğe liste kutusundan siler.  
  
```  
BOOL DeleteItem(int iIndex);  
BOOL DeleteItem(DWORD_PTR dwData);  
  BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
*İIndex*<br/>
[in] Silinecek öğenin sıfır tabanlı dizini.  
  
*dwData*<br/>
[in] Silinecek öğe ile ilişkili veriler.  
  
*lpszText*<br/>
[in] Silinecek öğenin metni. Aynı metni birden çok öğe varsa, ilk öğe silindi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe bulunan ve başarıyla silindi gerekiyorsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="duplicatedata"></a>  CMFCToolBarComboBoxButton::DuplicateData  
 Yinelenen kullanıcı tanımlı veri.  
  
```  
virtual void DuplicateData();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntemi hiçbir şey yapmaz. Herhangi bir kullanıcı tanımlı veri kopyalamak isterseniz türetilen bir sınıfta bu yöntemi yok sayın.  
  
##  <a name="enablewindow"></a>  CMFCToolBarComboBoxButton::EnableWindow  
 Etkinleştirir veya düzenleme ve birleşik giriş kutuları devre dışı bırakır.  
  
```  
virtual void EnableWindow(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
*bSistemlerde*<br/>
[in] Düzenle ve birleşik giriş kutularını etkinleştirmek için TRUE; Düzenle ve birleşik giriş kutuları devre dışı bırakmak için FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Devre dışı bırakıldığında denetimler etkin olamaz ve kullanıcı girişi kabul edemez.  
  
##  <a name="exporttomenubutton"></a>  CMFCToolBarComboBoxButton::ExportToMenuButton  
 Kopya uygulama dize tablosunda bir dizeden belirtilen menüsüne komut birleşik giriş kutusu düğmesini kullanarak kimliği  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Parametreler  
*MenuButton*<br/>
[out] Menü düğmesine başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman TRUE.  
  
##  <a name="finditem"></a>  CMFCToolBarComboBoxButton::FindItem  
 Belirtilen dizeyi içeren liste kutusunda ilk öğenin dizinini döndürür.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>Parametreler  
*lpszText*<br/>
[in] Liste kutusunda aramak istediğiniz metin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğenin dizini; veya öğenin bulunamaması durumunda CB_ERR.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getbycmd"></a>  CMFCToolBarComboBoxButton::GetByCmd  
 Belirtilen komut kimliği olan birleşik giriş kutusu düğmesi için bir işaretçi alır  
  
```  
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,  
    BOOL bIsFocus=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
*uiCmd*<br/>
[in] Birleşik giriş kutusu düğmesi komut kimliği.  
  
*bIsFocus*<br/>
[in] Yalnızca arama için true, düğmeler odaklanmış; Tüm düğmeleri aramak için FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu düğmesi için bir işaretçi; ya da düğme bulunamazsa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcombobox"></a>  CMFCToolBarComboBoxButton::GetComboBox  
 Bir işaretçi açılan kutu içinde birleşik giriş kutusu düğmesi döndürür.  
  
```  
CComboBox* GetComboBox() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md) yöntemi başarılı olup olmadığını nesne; Aksi takdirde NULL.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcontextmenuid"></a>  CMFCToolBarComboBoxButton::GetContextMenuID  
 Birleşik giriş kutusu düğmesi için kısayol menüsü kaynak Kimliğini alır.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kısayol menüsünde kaynak kimliği  
  
##  <a name="getcount"></a>  CMFCToolBarComboBoxButton::GetCount  
 Liste kutusundan öğe sayısını döndürür.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcountall"></a>  CMFCToolBarComboBoxButton::GetCountAll  
 Belirtilen komut kimliğe sahip bir birleşik giriş kutusu düğmesi liste kutusunda öğe sayısını alır  
  
```  
static int GetCountAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parametreler  
*uiCmd*<br/>
[in] Birleşik giriş kutusu düğmesi komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda öğe sayısı; Aksi halde düğme birleşik giriş kutusu CB_ERR bulunamadı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcursel"></a>  CMFCToolBarComboBoxButton::GetCurSel  
 Liste kutusunda seçili öğenin dizinini alır.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda seçili öğenin dizinini; veya hiçbir öğe seçili değilse CB_ERR.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu dizin sıfır tabanlıdır.  
  
##  <a name="getcurselall"></a>  CMFCToolBarComboBoxButton::GetCurSelAll  
 Seçili öğenin dizinini bir açılan liste kutusunda belirtilen komut kimliği olan kutusu düğmesi döndürür.  
  
```  
static int GetCurSelAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parametreler  
*uiCmd*<br/>
[in] Birleşik giriş kutusu düğmesi komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda seçili öğenin dizinini; Aksi takdirde, hiçbir öğe seçili değilse CB_ERR veya birleşik giriş kutusu düğmesi bulunamadı.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu dizin sıfır tabanlıdır.  
  
##  <a name="geteditctrl"></a>  CMFCToolBarComboBoxButton::GetEditCtrl  
 Bir işaretçi için düzenleme kutusu içinde birleşik giriş kutusu düğmesi döndürür.  
  
```  
virtual CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa düzenleme kutusu için bir işaretçi; Aksi takdirde NULL.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gethwnd"></a>  CMFCToolBarComboBoxButton::GetHwnd  
 Birleşik giriş kutusu için Pencere işleyicisi döndürür.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencere tanıtıcısı veya birleşik giriş kutusu bir pencere nesnesi ile ilişkili değilse NULL.  
  
##  <a name="getitem"></a>  CMFCToolBarComboBoxButton::GetItem  
 Belirtilen bir dizinden liste kutusunda bir öğe ile ilişkili dizeyi döndürür.  
  
```  
LPCTSTR GetItem(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Parametreler  
*İIndex*<br/>
[in] Liste kutusunda bir öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesiyle ilişkili dize için bir işaretçi; Aksi takdirde dizin parametresi geçersiz olduğunda ya da dizin parametresi -1'dir ve birleşik giriş kutusunda seçili öğe yok yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda seçili olan öğenin dize dizin parametresi-1 döndürür.  
  
##  <a name="getitemall"></a>  CMFCToolBarComboBoxButton::GetItemAll  
 Belirtilen komut kimliğe sahip bir birleşik giriş kutusu düğmesi, liste kutusunda belirtilen bir dizinden bir öğe ile ilişkili dizeyi döndürür  
  
```  
static LPCTSTR GetItemAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Parametreler  
*uiCmd*<br/>
[in] Birleşik giriş kutusu düğmesi komut kimliği.  
  
*İIndex*<br/>
[in] Liste kutusunda bir öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, öğenin dizeye bir işaretçi; Aksi takdirde NULL dizini geçersiz bir birleşik giriş kutusu düğmesi bulunamadı, ya da dizin -1 ve birleşik giriş kutusunda seçili öğe yok.  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda seçili olan öğe dizisi bir dizin değeri-1 döndürür.  
  
##  <a name="getitemdata"></a>  CMFCToolBarComboBoxButton::GetItemData  
 Belirli bir dizinini liste kutusunda bir öğe ile ilişkili verilerini döndürür.  
  
```  
DWORD_PTR GetItemData(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Parametreler  
*İIndex*<br/>
[in] Liste kutusunda bir öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeyle ilişkili verileri; ya da öğe yoksa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda seçili öğeyle ilişkili verileri dizin parametresi-1 döndürür.  
  
##  <a name="getitemdataall"></a>  CMFCToolBarComboBoxButton::GetItemDataAll  
 Belirli bir dizinin belirli komut kimliğe sahip bir birleşik giriş kutusu düğmesi, liste kutusunda bir öğe ile ilişkili verileri döndürür  
  
```  
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Parametreler  
*uiCmd*<br/>
[in] Birleşik giriş kutusu düğmesi komut kimliği.  
  
*İIndex*<br/>
[in] Liste kutusunda bir öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa öğeye ilişkilendirilmiş veri; Aksi takdirde, belirtilen dizinde geçerli değilse, 0 veya birleşik giriş kutusu düğmesi CB_ERR bulunamadı.  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda seçili öğeyle ilişkili verileri dizin parametresi-1 döndürür.  
  
##  <a name="getitemdataptrall"></a>  CMFCToolBarComboBoxButton::GetItemDataPtrAll  
 Belirli bir dizinin belirli komut kimliğe sahip bir birleşik giriş kutusu düğmesi, liste kutusunda bir öğe ile ilişkili verileri döndürür Bu veriler, bir işaretçi olarak döndürülür.  
  
```  
static void* GetItemDataPtrAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Parametreler  
*uiCmd*<br/>
[in] Birleşik giriş kutusu düğmesi komut kimliği.  
  
*İIndex*<br/>
[in] Liste kutusunda bir öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa öğeye ilişkilendirilmiş bir işaretçi; Aksi takdirde,-1 ise bir hata oluşur ya da düğme birleşik giriş kutusu yoksa NULL bulunamadı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getprompt"></a>  CMFCToolBarComboBoxButton::GetPrompt  
 İstem Dizesi birleşik giriş kutusu düğmesi döndürür.  
  
```  
virtual CString GetPrompt() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İstem dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem henüz uygulanmadı.  
  
##  <a name="gettext"></a>  CMFCToolBarComboBoxButton::GetText  
 Metin düzenleme kutusu içinde alır.  
  
```  
LPCTSTR GetText() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düzenleme kutusuna metin.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettextall"></a>  CMFCToolBarComboBoxButton::GetTextAll  
 Belirtilen komut kimliğe sahip bir birleşik giriş kutusu düğmesi düzenleme kutusuna metin alır  
  
```  
static LPCTSTR GetTextAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parametreler  
*uiCmd*<br/>
[in] Belirli bir birleşik giriş kutusu düğmesi komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa düzenleme kutusuna metin; Aksi takdirde NULL.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hasfocus"></a>  CMFCToolBarComboBoxButton::HasFocus  
 Birleşik giriş kutusu odağa sahip olup olmadığını gösterir.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu şu anda odağı varsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusunun herhangi bir alt pencere odağı varsa, bu yöntem ayrıca TRUE döndürür.  
  
##  <a name="iscentervert"></a>  CMFCToolBarComboBoxButton::IsCenterVert  
 Birleşik giriş kutusu düğmeleri dikey konumu uygulamaya döndürür.  
  
```  
static BOOL IsCenterVert();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmeleri ortalanır TRUE; Düğmeleri üstünde hizalanır FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isflatmode"></a>  CMFCToolBarComboBoxButton::IsFlatMode  
 Birleşik giriş kutusu düğmeleri düz stil görünümünü uygulamada döndürür.  
  
```  
static BOOL IsFlatMode();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmeleri düz bir stil varsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu düğmeleri varsayılan düz stilini FALSE olur.  
  
##  <a name="isownerof"></a>  CMFCToolBarComboBoxButton::IsOwnerOf  
 Belirtilen tutamaç birleşik giriş kutusu düğmesi veya alt öğelerinden biri ile ilişkili olup olmadığını belirtir.  
  
```  
virtual BOOL IsOwnerOf(HWND hwnd);
```  
  
### <a name="parameters"></a>Parametreler  
*HWND*<br/>
[in] Bir pencere tutucu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tutamaç birleşik giriş kutusu düğmesi veya alt öğelerinden birine assocated ise TRUE; Aksi takdirde FALSE.  
  
##  <a name="isribbonbutton"></a>  CMFCToolBarComboBoxButton::IsRibbonButton  
 Bir Şerit panel üzerine birleşik giriş kutusu düğmesi bulunduğunu gösterir.  
  
```  
BOOL IsRibbonButton() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem her zaman yanlış, yani bir Şerit panel üzerine birleşik giriş kutusu düğmesi hiçbir zaman görüntülenen döndürür.  
  
##  <a name="iswindowvisible"></a>  CMFCToolBarComboBoxButton::IsWindowVisible  
 Görünürlük durumu birleşik giriş kutusu düğmesi döndürür.  
  
```  
virtual BOOL IsWindowVisible();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu düğmesi görünürlük durumu.  
  
##  <a name="notifycommand"></a>  CMFCToolBarComboBoxButton::NotifyCommand  
 Birleşik giriş kutusu düğmesi iletiyi işler olup olmadığını gösterir.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Parametreler  
*iNotifyCode*<br/>
[in] Komutu ile ilişkili bir uyarı iletisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olup birleşik giriş kutusu düğmesi iletiyi işler.  
  
##  <a name="onaddtocustomizepage"></a>  CMFCToolBarComboBoxButton::OnAddToCustomizePage  
 Framework tarafından düğmenin eklendiğinde çağırılır **Özelleştir** iletişim kutusu.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
##  <a name="oncalculatesize"></a>  CMFCToolBarComboBoxButton::OnCalculateSize  
 Düğmenin boyutunu hesaplamak için framework tarafından çağırılır.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
*pDC*<br/>
[in] Birleşik giriş kutusu düğmesi görüntüler cihaz bağlamı.  
  
*sizeDefault*<br/>
[in] Birleşik giriş kutusu düğmesi varsayılan boyutu.  
  
*bHorz*<br/>
[in] Üst araç çubuğu yerleştirme durumu. Araç dikey yerleştirildiğinde araç yatay ve yanlış yerleştirildiğini olduğunda TRUE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `SIZE` birleşik giriş kutusu düğmesi piksel cinsinden boyutunu içeren yapısı.  
  
##  <a name="onchangeparentwnd"></a>  CMFCToolBarComboBoxButton::OnChangeParentWnd  
 Birleşik giriş kutusu düğmesi, yeni bir araç çubuğuna eklendiğinde, framework tarafından çağırılır.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parametreler  
*pWndParent*<br/>
[in] Yeni üst araç işaretçisi.  
  
##  <a name="onclick"></a>  CMFCToolBarComboBoxButton::OnClick  
 Kullanıcı birleşik giriş kutusu düğmesine tıkladığında framework tarafından çağırılır.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
*pWnd*<br/>
[in] Birleşik giriş kutusu düğmesi ana pencerenin işaretçisi.  
  
*bDelay*<br/>
[in] Türetilen bir sınıfta kullanılmak üzere ayrılmıştır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem olayı işleyen TRUE; Aksi takdirde FALSE.  
  
##  <a name="onctlcolor"></a>  CMFCToolBarComboBoxButton::OnCtlColor  
 Kullanıcı birleşik giriş kutusu düğme rengi ayarlamak için üst araç çubuğu rengi değiştiğinde framework tarafından çağırılır.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Parametreler  
*pDC*<br/>
[in] Birleşik giriş kutusu düğmesi görüntüler cihaz bağlamı.  
  
*nCtlColor*<br/>
[in] Kullanılmayan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu düğmenin arka plan boyama için framework kullanan fırçaya işleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ayrıca Birleşik giriş kutusu düğmesi metnin rengini ayarlar.  
  
##  <a name="ondraw"></a>  CMFCToolBarComboBoxButton::OnDraw  
 Birleşik giriş kutusu düğmesi belirtilen stillerini ve seçeneklerini kullanarak çizilmesi gerektiğinde framework tarafından çağırılır.  
  
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
*PDC*<br/>
[in] Düğme görüntüler cihaz bağlamı.  
  
*Rect*<br/>
[in] Dikdörtgen düğmesi.  
  
*pImages*<br/>
[in] Görüntüleri düğmesi ile ilişkili olan koleksiyonu.  
  
*bHorz*<br/>
[in] Üst araç çubuğu yerleştirme durumu. Araç dikey yerleştirildiğinde araç yatay ve yanlış yerleştirildiğini olduğunda TRUE.  
  
*bCustomizeMode*<br/>
[in] Uygulamayı özelleştirme modunda olup olmadığı.  
  
*bHighlight*<br/>
[in] Birleşik giriş kutusu düğmesi çizileceğini belirtir.  
  
*bDrawBorder*<br/>
[in] Birleşik giriş kutusu düğmesi ile kenarlık çizmek belirtir.  
  
*bGrayDisabledButtons*<br/>
[in] Çizim true devre dışı düğmeleri gölgeli; Devre dışı görüntüleri koleksiyon kullanmak için FALSE.  
  
##  <a name="ondrawoncustomizelist"></a>  CMFCToolBarComboBoxButton::OnDrawOnCustomizeList  
 Birleşik giriş kutusu düğmesi çizim için framework tarafından çağırılır **komutları** bölmesinde **Özelleştir** iletişim kutusu.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parametreler  
*pDC*<br/>
[in] Birleşik giriş kutusu düğmesi görüntüler cihaz bağlamı.  
  
*Rect*<br/>
[in] Birleşik giriş kutusu düğmesi sınırlayıcı dikdörtgenini.  
  
*bSelected*<br/>
[in] Birleşik giriş kutusu düğmesi seçili ise TRUE; Aksi takdirde FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu düğmesi piksel cinsinden genişliği.  
  
##  <a name="onglobalfontschanged"></a>  CMFCToolBarComboBoxButton::OnGlobalFontsChanged  
 Uygulama yazı tipi değiştiğinde birleşik giriş kutusu düğmesi yazı tipi ayarlamak için framework tarafından çağırılır.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
##  <a name="onmove"></a>  CMFCToolBarComboBoxButton::OnMove  
 Üst araç çubuğunda hareket ettiğinde birleşik giriş kutusu düğmesi konumunu değiştirmek için framework tarafından çağırılır.  
  
```  
virtual void OnMove();
```  
  
##  <a name="onshow"></a>  CMFCToolBarComboBoxButton::OnShow  
 Birleşik giriş kutusu düğmesi gizli veya gösterilen framework tarafından çağırılır.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
*bBilgi Göster*<br/>
[in] Birleşik giriş kutusu düğmesi görüntülemek veya gizlemek belirtir.  
  
##  <a name="onsize"></a>  CMFCToolBarComboBoxButton::OnSize  
 Üst araç çubuğunda boyutu değiştiğinde birleşik giriş kutusu düğmesi boyutunu değiştirmek için framework tarafından çağırılır.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Parametreler  
*iSize*<br/>
[in] Birleşik giriş kutusu düğmesi yeni genişliği.  
  
##  <a name="onupdatetooltip"></a>  CMFCToolBarComboBoxButton::OnUpdateToolTip  
 Kullanıcı birleşik giriş kutusu düğmesi için araç ipucu değiştiğinde framework tarafından çağırılır.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Parametreler  
*pWndParent*<br/>
[in] Birleşik giriş kutusu düğmesi için ana pencere işaretçisi.  
  
*iButtonIndex*<br/>
[in] Birleşik giriş kutusu düğmesi kimliği.  
  
*wndToolTip*<br/>
[in] Birleşik giriş kutusu düğmesi ile ilişkilendirmek için araç ipucu.  
  
*str*<br/>
[in] Araç İpucu metni.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem olayı işleyen TRUE; Aksi takdirde FALSE.  
  
##  <a name="removeallitems"></a>  CMFCToolBarComboBoxButton::RemoveAllItems  
 Liste ve Düzenle kutularında tüm öğelerini siler.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Listeden tüm öğeler kutu ve bir birleşik giriş kutusu denetimi Düzenle kaldırır.  
  
##  <a name="selectitem"></a>  CMFCToolBarComboBoxButton::SelectItem  
 Liste kutusunda bir öğe seçer.  
  
```  
BOOL SelectItem(
    int iIndex,  
    BOOL bNotify=TRUE);  
  
BOOL SelectItem(DWORD_PTR dwData);  
BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
*İIndex*<br/>
[in] Liste kutusunda bir öğenin sıfır tabanlı dizini.  
  
*bNotify*<br/>
[in] Birleşik giriş kutusu düğmesi seçimin bildirmek için TRUE; Aksi durumda FALSE.  
  
*dwData*<br/>
[in] Liste kutusunda bir öğe ile ilişkili veriler.  
  
*lpszText*<br/>
[in] Liste kutusunda bir öğenin metni.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olduysa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="selectitemall"></a>  CMFCToolBarComboBoxButton::SelectItemAll  
 Belirtilen komut kimliğe sahip bir birleşik giriş kutusu düğmesi liste kutusunda bir öğe seçer  
  
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
[in] Liste kutusunu içeren birleşik giriş kutusu düğmesi komut kimliği.  
  
*İIndex*<br/>
[in] Liste kutusunda öğenin sıfır tabanlı dizini. -1 değeri, geçerli herhangi bir seçimi liste kutusundan kaldırır ve düzenleme kutusuna temizler.  
  
*dwData*<br/>
[in] Liste kutusunda bir öğe verileri.  
  
*lpszText*<br/>
[in] Liste kutusunda bir öğenin metni.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olduysa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="serialize"></a>  CMFCToolBarComboBoxButton::Serialize  
 Bu nesne bir arşivden okur veya arşive yazar.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
*ar*<br/>
[out içinde] `CArchive` Nesneyi serileştirmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlarında `CArchive` nesne, bu yöntem okur veya yazar arşive belirleyin.  
  
##  <a name="setaccdata"></a>  CMFCToolBarComboBoxButton::SetACCData  
 Belirtilen doldurur `CAccessibilityData` erişilebilirlik verileri birleşik giriş kutusu düğmesi kullanarak nesne.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parametreler  
*pParent*<br/>
[in] Birleşik giriş kutusu düğmenin üst pencere.  
  
*Veri*<br/>
[out] A `CAccessibilityData` birleşik giriş kutusu düğmesinden erişilebilirlik veri alan nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olduysa TRUE; Aksi durumda FALSE.  
  
##  <a name="setcentervert"></a>  CMFCToolBarComboBoxButton::SetCenterVert  
 Birleşik giriş kutusu düğmeleri dikey konumu, uygulamanın ayarlar.  
  
```  
static void SetCenterVert(BOOL bCenterVert=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
*bCenterVert*<br/>
[in] Araç çubuğunda birleşik giriş kutusu düğmesi ortalamak için TRUE; Birleşik giriş kutusu düğmesi araç çubuğunun üst hizalamak için FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, birleşik giriş kutusu düğmeleri dön hizalanır.  
  
##  <a name="setcontextmenuid"></a>  CMFCToolBarComboBoxButton::SetContextMenuID  
 Kısayol menüsünde kaynak kimliği için birleşik giriş kutusu düğmesi ayarlar.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Parametreler  
*uiResID*<br/>
[in] Kısayol menüsünde kaynak kimliği  
  
##  <a name="setdropdownheight"></a>  CMFCToolBarComboBoxButton::SetDropDownHeight  
 Liste kutusunun yüksekliğini, bırakılan ayarlar.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>Parametreler  
*nHeight*<br/>
[in] Liste kutusu piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan yükseklik 150 pikseldir.  
  
##  <a name="setflatmode"></a>  CMFCToolBarComboBoxButton::SetFlatMode  
 Birleşik giriş kutusu düğmeleri düz stil görünümünü uygulamada ayarlar.  
  
```  
static void SetFlatMode(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
*bFlat*<br/>
[in] Düz stil görünümü için TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu düğmeleri varsayılan düz stilini FALSE olur.  
  
##  <a name="setstyle"></a>  CMFCToolBarComboBoxButton::SetStyle  
 Belirtilen stili birleşik giriş kutusu düğmesi ayarlar ve devre dışı değildir, bu denetimi yeniden çizer.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
*nStyle*<br/>
[in] Bitsel bir birleşimi (veya) toolbar stilleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Araç çubuğu düğmesi stilleri bir listesi için bkz. [ToolBar denetim stilleri](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="settext"></a>  CMFCToolBarComboBoxButton::SetText  
 Metin düzenleme kutusuna birleşik giriş kutusu düğmesi ayarlar.  
  
```  
void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
*lpszText*<br/>
[in] Düzenleme kutusu metni içeren bir dize işaretçisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)



