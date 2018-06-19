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
ms.openlocfilehash: ddfa4d26ed0a4328714fbd1a921fe7c204ca3752
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377372"
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
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](#cmfctoolbarcomboboxbutton)|Oluşturan bir `CMFCToolBarComboBoxButton`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::AddItem](#additem)|Açılan kutu listesi sonuna bir öğe ekler.|  
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|Birleşik giriş kutusu listesine bir öğe ekler. Listesindeki öğelerin sırasını tarafından belirtilen `Compare`.|  
|[CMFCToolBarComboBoxButton::Compare](#compare)|İki öğeyi karşılaştırır. Adlı sıralamak için bu öğeler `AddSortedItems` birleşik giriş kutusu listesine ekler.|  
|[CMFCToolBarComboBoxButton::CreateEdit](#createedit)|Birleşik giriş kutusu düğmesi için yeni bir düzenleme denetimi oluşturur.|  
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|Birleşik giriş kutusu listesinden bir öğeyi siler.|  
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|Belirtilen dizeyi içeren öğenin dizinini döndürür.|  
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|Birleşik giriş kutusu düğmesi belirtilen komut kimliği ile bir işaretçi döndürür|  
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|Birleşik giriş kutusu düğmesini katıştırılmış birleşik giriş kutusu denetimine işaretçi döndürür.|  
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|Öğe sayısı açılan kutu listesi döndürür.|  
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|Belirtilen komut kimliğe sahip kutusu düğmesi açılan bulur Öğe sayısı açılan bu düğme kutusunu listesini döndürür.|  
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|Seçili öğenin dizini açılan kutu listesi döndürür.|  
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|Birleşik giriş belirtilen komut Kimliğine sahip ve seçilen öğenin dizini açılan kutu listesi o düğmesinin döndürür kutusu düğmesi bulur.|  
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|Birleşik giriş kutusu düğmesini katıştırılmış düzenleme denetimine işaretçi döndürür.|  
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|Birleşik giriş belirtilen dizinde ile ilişkili dize kutu listesi döndürür.|  
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|Birleşik giriş belirtilen komut Kimliğine sahip ve bu düğme, birleşik giriş kutusu listede bir dizinden ile ilişkili bir dize döndürür kutusu düğmesi bulur.|  
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|Birleşik giriş belirtilen dizinde ilişkilendirilmiş 32-bit değeri kutu listesi döndürür.|  
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|Birleşik giriş belirtilen komut Kimliğine sahip ve bu düğme, birleşik giriş kutusu listede bir dizinden ilişkilendirilmiş 32-bit değeri döndüren kutusu düğmesi bulur.|  
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|Belirtilen komut kimliğe sahip kutusu düğmesi açılan bulur Alır 32-bit değeri bu düğmesi ve 32-bit bir işaretçi olarak değeri döndürür birleşik giriş kutusu listede bir dizinden ilişkilendirilmiş.|  
|[CMFCToolBarComboBoxButton::GetText](#gettext)|Birleşik giriş kutusu düzenleme denetiminden metni döndürür.|  
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|Birleşik giriş belirtilen komut Kimliğine sahip ve bu düğme düzenleme denetiminden metni döndüren kutusu düğmesi bulur.|  
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|Birleşik giriş kutusu düğmeleri uygulama ortalanmış veya araç çubuğunun üstündeki hizalı olup olmadığını belirler.|  
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|Birleşik giriş kutusu düğmeleri uygulama düz bir görünümü sahip olup olmadığını belirler.|  
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|Listeden tüm öğeler kutusuna ve birleşik giriş kutusu denetimi Düzenle kaldırır.|  
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|Birleşik giriş kutusu dizini, 32-bit değeri veya dize göre bir öğeyi seçer ve birleşik giriş kutusu denetimi seçimi hakkında bilgilendirir.|  
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|Belirtilen komut kimliğe sahip kutusu düğmesi açılan bulur Çağrıları `SelectItem` dize, dizin veya 32-bit değeri göre bu düğmesinin açılan kutusunda bir öğe seçin.|  
|[CMFCToolBarComboBoxButton::SetCenterVert](#setcentervert)|Birleşik giriş kutusu düğmeleri uygulama dikey ortalanmış veya araç çubuğunun üstündeki hizalanacağını belirtir.|  
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|Aşağı açılan liste kutusunu yüksekliğini ayarlar.|  
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|Birleşik giriş kutusu düğmeleri uygulama düz bir görünümü sahip olup olmadığını belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu düğmesi bir araç çubuğuna eklemek için aşağıdaki adımları izleyin:  
  
 1. Bir kukla kaynağı kimliği üst araç çubuğu kaynak düğmesi için ayrılmış.  
  
 2. Oluşturmak bir `CMFCToolBarComboBoxButton` nesnesi.  
  
 3. İşler ileti işleyicisi'ndeki `AFX_WM_RESETTOOLBAR` iletisi, sahte düğmesini kullanarak yeni birleşik giriş kutusu düğmesi ile değiştirin [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Daha fazla bilgi için bkz: [izlenecek yol: üzerinde denetimler koyma araç'çubukları](../../mfc/walkthrough-putting-controls-on-toolbars.md). Birleşik giriş kutusu araç çubuğu düğmesi bir örneği için örnek proje VisualStudioDemo bakın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCToolBarComboBoxButton` sınıfı. Örnek düzenleme ve birleşik giriş kutularını etkinleştirmek için uygulamada kutusunu düğmeleri açılan dikey konumu ayarlayın, onu bırakıldığında liste kutusu yüksekliğini ayarlayın, uygulamada birleşik giriş kutusu düğmeleri düz stil görünümünü ayarlamak nasıl gösterir ve metin kutusunda düğme açılan düzenleme kutusuna ayarlayın. Bu kod parçacığını parçası olan [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtoolbarcomboboxbutton.h  
  
##  <a name="additem"></a>  CMFCToolBarComboBoxButton::AddItem  
 Liste kutusu için benzersiz bir öğe ekler.  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszItem`  
 Liste kutusu eklemek için öğenin metni.  
  
 [in] `dwData`  
 Liste kutusu eklenecek öğe ile ilişkili veriler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusu son öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, liste kutusunu stili sıralandığında kullanmayın.  
  
 Öğe metnini liste kutusunda ise, yeni verileri var olan öğe depolanır. Öğesi için arama büyük küçük harfe duyarlıdır.  
  
##  <a name="addsorteditem"></a>  CMFCToolBarComboBoxButton::AddSortedItem  
 Liste kutusu tarafından tanımlanan sırada bir öğe ekler [karşılaştırmak](#compare) yöntemi.  
  
```  
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszItem`  
 Liste kutusu eklemek için öğenin metni.  
  
 [in] `dwData`  
 Liste kutusu eklenecek öğe ile ilişkili veriler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusu eklendi öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli bir sırada liste kutusunda öğeler eklemek için bu işlevi kullanın.  
  
##  <a name="canbestretched"></a>  CMFCToolBarComboBoxButton::CanBeStretched  
 Birleşik giriş kutusu düğme boyutu değişip değişemeyeceğini gösterir.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE`.  
  
##  <a name="cmfctoolbarcomboboxbutton"></a>  CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton  
 Oluşturan bir [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) nesnesi.  
  
```  
CMFCToolBarComboBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=CBS_DROPDOWNLIST,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiID`  
 Yeni düğmesini komut kimliği.  
  
 [in] `iImage`  
 Yeni düğmesi ile ilişkilendirilmiş görüntüsü görüntü dizini.  
  
 [in] `dwStyle`  
 Yeni düğmesini stili.  
  
 [in] `iWidth`  
 Yeni düğmesinin piksel cinsinden genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan genişliğini 150 pikseldir.  
  
 Araç çubuğu düğmesi stilleri listesi için bkz: [ToolBar denetim stilleri](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="cleardata"></a>  CMFCToolBarComboBoxButton::ClearData  
 Kullanıcı tanımlı siler veri.  
  
```  
virtual void ClearData();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak bu yöntem hiçbir şey yapmaz. Herhangi bir kullanıcı tarafından tanımlanan veri silmek istiyorsanız bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="compare"></a>  CMFCToolBarComboBoxButton::Compare  
 İki dizeyi karşılaştırır.  
  
```  
virtual int Compare(
    LPCTSTR lpszItem1,  
    LPCTSTR lpszItem2);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszItem1`  
 Karşılaştırılacak ilk dize.  
  
 [in] `lpszItem2`  
 Karşılaştırılacak ikinci dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizeleri büyük küçük harfe duyarlı lexicographic ilişkisi belirten bir değer. Olası değerler aşağıdaki tabloda listelenmektedir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|\<0|İlk dizesi küçük ikinciden.|  
|0|İlk dizesi ikinci eşittir.|  
|>0|İlk dizesi saniyeden daha büyük.|  
  
### <a name="remarks"></a>Açıklamalar  
 Öğeleri liste kutusunda nasıl sıralanacağını değiştirmek için bu yöntemi geçersiz kılın.  
  
 Karşılaştırma büyük/küçük harf duyarlıdır.  
  
 Bu yöntem yalnızca çağrılır [AddSortedItem](#addsorteditem) yöntemi.  
  
##  <a name="copyfrom"></a>  CMFCToolBarComboBoxButton::CopyFrom  
 Belirtilen durumunu kopyalar `CMFCToolBarComboBoxButton` geçerli nesneye.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `src`  
 Kaynak `CMFCToolBarComboBoxButton` nesnesi.  
  
##  <a name="createcombo"></a>  CMFCToolBarComboBoxButton::CreateCombo  
 Birleşik giriş kutusu düğmesi için yeni bir birleşik giriş kutusu oluşturur.  
  
```  
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pWndParent`  
 Düğmenin üst pencere için bir işaretçi.  
  
 [in] `rect`  
 Birleşik giriş kutusu sınırlayıcı dikdörtgenini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa yeni bir birleşik giriş kutusu için bir işaretçi; Aksi takdirde `NULL`.  
  
##  <a name="createedit"></a>  CMFCToolBarComboBoxButton::CreateEdit  
 Birleşik giriş kutusu düğmesi için yeni bir düzenleme kutusu oluşturur.  
  
```  
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pWndParent`  
 Düğmenin üst pencere için bir işaretçi.  
  
 [in] `rect`  
 Yeni düzenleme kutusu sınırlayıcı dikdörtgenini.  
  
 [in] `dwEditStyle`  
 Yeni düzenleme kutusuna denetim stili.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa yeni düzenleme kutusu için bir işaretçi; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu düğmesi için yeni bir düzenleme kutusu oluşturduğunda framework bu yöntemi çağırır. Değiştirmek için bu yöntemi geçersiz kılın nasıl [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md) oluşturulur.  
  
##  <a name="deleteitem"></a>  CMFCToolBarComboBoxButton::DeleteItem  
 Belirtilen öğe liste kutusundan siler.  
  
```  
BOOL DeleteItem(int iIndex);  
BOOL DeleteItem(DWORD_PTR dwData);  
  BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iIndex`  
 Silinecek öğenin sıfır tabanlı dizini.  
  
 [in] `dwData`  
 Silinecek öğe ile ilişkili veriler.  
  
 [in] `lpszText`  
 Silinecek öğe metin. Aynı metnin ile birden çok öğe varsa, ilk öğe silindi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` öğe bulunan ve başarıyla silindi Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="duplicatedata"></a>  CMFCToolBarComboBoxButton::DuplicateData  
 Yinelenen kullanıcı tanımlı veri.  
  
```  
virtual void DuplicateData();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak bu yöntem hiçbir şey yapmaz. Herhangi bir kullanıcı tarafından tanımlanan veri kopyalamak istiyorsanız, bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="enablewindow"></a>  CMFCToolBarComboBoxButton::EnableWindow  
 Etkinleştirir veya düzenleme ve birleşik giriş kutuları devre dışı bırakır.  
  
```  
virtual void EnableWindow(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bEnable`  
 `TRUE` Düzenle ve birleşik giriş kutuları etkinleştirmek için; `FALSE` düzenleme ve birleşik giriş kutuları devre dışı bırakmak için.  
  
### <a name="remarks"></a>Açıklamalar  
 Devre dışı bırakıldığında, denetimleri etkin olamaz ve kullanıcı girişi kabul edemez.  
  
##  <a name="exporttomenubutton"></a>  CMFCToolBarComboBoxButton::ExportToMenuButton  
 Birleşik giriş kutusu düğmesi komutunu kullanarak belirtilen menü uygulama dize tablosundan dizeye kopya kimliği  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] `menuButton`  
 Menü düğmesi başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `TRUE`.  
  
##  <a name="finditem"></a>  CMFCToolBarComboBoxButton::FindItem  
 Belirtilen dizeyi içeren liste kutusunda ilk öğenin dizinini döndürür.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszText`  
 Liste kutusunda Aranacak metin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğenin dizini; veya `CB_ERR` öğenin bulunamaması durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getbycmd"></a>  CMFCToolBarComboBoxButton::GetByCmd  
 Belirtilen komut kimliğe sahip birleşik giriş kutusu düğmesini gösteren bir işaretçi alır  
  
```  
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,  
    BOOL bIsFocus=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiCmd`  
 Birleşik giriş kutusu düğmesi komut kimliği.  
  
 [in] `bIsFocus`  
 `TRUE` Yalnızca arama için düğmeler odaklanmış; `FALSE` tüm düğmeleri aramak için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu düğmesini gösteren bir işaretçi; veya `NULL` düğmesi bulunmazsa.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcombobox"></a>  CMFCToolBarComboBoxButton::GetComboBox  
 Bir işaretçi açılan kutu içinde birleşik giriş kutusu düğmesi döndürür.  
  
```  
CComboBox* GetComboBox() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md) yöntemi, varsa başarılıysa nesne `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcontextmenuid"></a>  CMFCToolBarComboBoxButton::GetContextMenuID  
 Birleşik giriş kutusu düğmesi için kısayol menüsü kaynak kimliği alır.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kısayol menüsü kaynak kimliği  
  
##  <a name="getcount"></a>  CMFCToolBarComboBoxButton::GetCount  
 Liste kutusunda öğe sayısını döndürür.  
  
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
 [in] `uiCmd`  
 Birleşik giriş kutusu düğmesi komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusu öğelerin sayısı; Aksi takdirde `CB_ERR` birleşik giriş kutusu düğmesi bulunmazsa.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcursel"></a>  CMFCToolBarComboBoxButton::GetCurSel  
 Liste kutusunda seçili öğenin dizinini alır.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda seçili öğenin dizini; veya `CB_ERR` öğe seçili değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu sıfır tabanlı dizinidir.  
  
##  <a name="getcurselall"></a>  CMFCToolBarComboBoxButton::GetCurSelAll  
 Belirtilen komut kimliğe sahip kutusu düğmesi bir açılan liste kutusunda seçili öğenin dizinini döndürür  
  
```  
static int GetCurSelAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiCmd`  
 Birleşik giriş kutusu düğmesi komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda seçili öğenin dizini; Aksi takdirde, `CB_ERR` seçili öğe yok veya birleşik giriş kutusu düğmesi bulunamadı.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu sıfır tabanlı dizinidir.  
  
##  <a name="geteditctrl"></a>  CMFCToolBarComboBoxButton::GetEditCtrl  
 Bir işaretçi düzenleme kutusu içinde birleşik giriş kutusu düğmesi döndürür.  
  
```  
virtual CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düzenleme kutusuna yöntemi başarılı olup olmadığını gösteren bir işaretçi; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gethwnd"></a>  CMFCToolBarComboBoxButton::GetHwnd  
 Birleşik giriş kutusu için Pencere işleyicisini döndürür.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir pencere tanıtıcının veya `NULL` birleşik giriş kutusu pencere nesnesi ile ilişkili değilse.  
  
##  <a name="getitem"></a>  CMFCToolBarComboBoxButton::GetItem  
 Liste kutusunda belirtilen dizindeki bir öğesiyle ilişkili dizeyi döndürür.  
  
```  
LPCTSTR GetItem(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iIndex`  
 Liste kutusunda öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeyle ilişkili dize için bir işaretçi; Aksi takdirde `NULL` dizin parametresi geçersiz olması veya dizin parametresi -1'dir ve açılan kutuda seçili öğe yok.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizin parametresi-1, geçerli olarak seçili öğenin dize döndürür.  
  
##  <a name="getitemall"></a>  CMFCToolBarComboBoxButton::GetItemAll  
 Belirtilen komut kimliğe sahip bir birleşik giriş kutusu düğmesi, liste kutusunda belirtilen dizindeki bir öğesiyle ilişkili dizeyi döndürür  
  
```  
static LPCTSTR GetItemAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiCmd`  
 Birleşik giriş kutusu düğmesi komut kimliği.  
  
 [in] `iIndex`  
 Liste kutusunda öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa öğesi'nin dize için bir işaretçi; Aksi takdirde `NULL` dizin geçersiz olduğu, birleşik giriş kutusu düğmesi değilse bulunan veya dizin ise -1 ve açılan kutuda seçili öğe yok.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizin değeri-1, geçerli olarak seçili öğenin dize döndürür.  
  
##  <a name="getitemdata"></a>  CMFCToolBarComboBoxButton::GetItemData  
 Liste kutusunda belirli bir dizindeki bir öğesiyle ilişkili verileri döndürür.  
  
```  
DWORD_PTR GetItemData(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iIndex`  
 Liste kutusunda öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu öğeyle ilişkili veri; veya öğe yoksa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizin parametresi-1 şu anda seçili öğe ile ilişkilendirilen veri döndürür.  
  
##  <a name="getitemdataall"></a>  CMFCToolBarComboBoxButton::GetItemDataAll  
 Belirli bir dizine belirli komut kimliğe sahip bir birleşik giriş kutusu düğmesi, liste kutusunda bir öğesiyle ilişkili verileri döndürür  
  
```  
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiCmd`  
 Birleşik giriş kutusu düğmesi komut kimliği.  
  
 [in] `iIndex`  
 Liste kutusunda öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa öğe ile ilişkilendirilen veri; Aksi halde, belirtilen dizin geçerli değilse, 0 veya birleşik giriş kutusu düğmesi CB_ERR bulunamadı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizin parametresi-1 şu anda seçili öğe ile ilişkilendirilen veri döndürür.  
  
##  <a name="getitemdataptrall"></a>  CMFCToolBarComboBoxButton::GetItemDataPtrAll  
 Belirli bir dizine belirli komut kimliğe sahip bir birleşik giriş kutusu düğmesi, liste kutusunda bir öğesiyle ilişkili verileri döndürür Bu veriler bir işaretçi olarak döndürülür.  
  
```  
static void* GetItemDataPtrAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiCmd`  
 Birleşik giriş kutusu düğmesi komut kimliği.  
  
 [in] `iIndex`  
 Liste kutusunda öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa öğe ile ilişkilendirilen bir işaretçi; bir hata oluşursa, aksi takdirde, -1 veya `NULL` birleşik giriş kutusu düğmesi bulunmazsa.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getprompt"></a>  CMFCToolBarComboBoxButton::GetPrompt  
 İstem Dizesi birleşik giriş kutusu düğmesi döndürür.  
  
```  
virtual CString GetPrompt() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İstem dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu metot şu anda uygulanmadı.  
  
##  <a name="gettext"></a>  CMFCToolBarComboBoxButton::GetText  
 Metin düzenleme kutusu içinde alır.  
  
```  
LPCTSTR GetText() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düzenleme kutusuna metin.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettextall"></a>  CMFCToolBarComboBoxButton::GetTextAll  
 Belirtilen komut kimliğe sahip bir birleşik giriş kutusu düğmesi düzenleme kutusuna metni alır  
  
```  
static LPCTSTR GetTextAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiCmd`  
 Belirli birleşik giriş kutusu düğmesi komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa düzenleme kutusuna metinde; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hasfocus"></a>  CMFCToolBarComboBoxButton::HasFocus  
 Birleşik giriş kutusu odağa sahip olup olmadığını gösterir.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Birleşik giriş kutusu odağa sahip Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem aynı zamanda `TRUE` tüm alt pencere açılan kutunun odağa sahip değilse.  
  
##  <a name="iscentervert"></a>  CMFCToolBarComboBoxButton::IsCenterVert  
 Birleşik giriş kutusu düğmelerini dikey konumu uygulamada döndürür.  
  
```  
static BOOL IsCenterVert();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` düğmeleri ortalanır; `FALSE` düğmeleri en üstünde hizalanır durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isflatmode"></a>  CMFCToolBarComboBoxButton::IsFlatMode  
 Birleşik giriş kutusu düğmelerin düz stil görünümünü uygulamada döndürür.  
  
```  
static BOOL IsFlatMode();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` düğmeleri düz bir stil varsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu düğmeleri için varsayılan düz stili `FALSE.`  
  
##  <a name="isownerof"></a>  CMFCToolBarComboBoxButton::IsOwnerOf  
 Belirtilen tanıtıcı birleşik giriş kutusu düğmesini veya alt öğelerinden ile ilişkili olup olmadığını gösterir.  
  
```  
virtual BOOL IsOwnerOf(HWND hwnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `hwnd`  
 Bir pencere işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Birleşik giriş kutusu düğmesini veya alt öğelerinden assocated işleyicisidir Aksi takdirde `FALSE`.  
  
##  <a name="isribbonbutton"></a>  CMFCToolBarComboBoxButton::IsRibbonButton  
 Birleşik giriş kutusu düğmesi Şerit panelde bulunduğunu gösterir.  
  
```  
BOOL IsRibbonButton() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem her zaman döndürür `FALSE`, birleşik giriş kutusu düğmesi başka bir deyişle, hiçbir zaman bir Şerit panelde görüntülenir.  
  
##  <a name="iswindowvisible"></a>  CMFCToolBarComboBoxButton::IsWindowVisible  
 Görünürlük durumu birleşik giriş kutusu düğmesi döndürür.  
  
```  
virtual BOOL IsWindowVisible();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu düğmesi görünürlük durumu.  
  
##  <a name="notifycommand"></a>  CMFCToolBarComboBoxButton::NotifyCommand  
 Birleşik giriş kutusu düğmesi iletisini işler olup olmadığını gösterir.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iNotifyCode`  
 Komutu ile ilişkili bildirim iletisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu düğmesi olup iletisini işler.  
  
##  <a name="onaddtocustomizepage"></a>  CMFCToolBarComboBoxButton::OnAddToCustomizePage  
 Düğme eklendiğinde çerçevesi tarafından çağrılır **Özelleştir** iletişim kutusu.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
##  <a name="oncalculatesize"></a>  CMFCToolBarComboBoxButton::OnCalculateSize  
 Düğmenin boyutunu hesaplamak için çerçevesi tarafından çağrılır.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Birleşik giriş kutusu düğmesi görüntüler cihaz bağlamı.  
  
 [in] `sizeDefault`  
 Birleşik giriş kutusu düğmesi varsayılan boyutu.  
  
 [in] `bHorz`  
 Üst araç çubuğu yerleştirme durumu. `TRUE` ne zaman araç yerleştirilmiştir yatay ve `FALSE` zaman araç yerleştirilmiştir dikey olarak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `SIZE` birleşik giriş kutusu düğmesi piksel boyutlarını içeren yapısı.  
  
##  <a name="onchangeparentwnd"></a>  CMFCToolBarComboBoxButton::OnChangeParentWnd  
 Birleşik giriş kutusu düğmesi yeni bir araç çubuğu takıldığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pWndParent`  
 Yeni üst araç işaretçi.  
  
##  <a name="onclick"></a>  CMFCToolBarComboBoxButton::OnClick  
 Kullanıcı birleşik giriş kutusu düğmesini tıklattığında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pWnd`  
 Birleşik giriş kutusu düğmesinin üst pencere işaretçi.  
  
 [in] `bDelay`  
 Bir türetilmiş sınıfta kullanılmak üzere ayrılmıştır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem; olay işliyorsa Aksi takdirde `FALSE`.  
  
##  <a name="onctlcolor"></a>  CMFCToolBarComboBoxButton::OnCtlColor  
 Kullanıcı birleşik giriş kutusu düğmesi rengini ayarlamak için üst araç renk değiştirdiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Birleşik giriş kutusu düğmesi görüntüler cihaz bağlamı.  
  
 [in] `nCtlColor`  
 Kullanılmayan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu düğmesi arka boyamak için çerçevesi kullanır fırça işleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem aynı zamanda birleşik giriş kutusu düğmesi metin rengini belirler.  
  
##  <a name="ondraw"></a>  CMFCToolBarComboBoxButton::OnDraw  
 Birleşik giriş kutusu düğmesi belirtilen stilleri ve seçenekleri kullanarak çizmek için çerçevesi tarafından çağrılır.  
  
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
 [in] `Pdc`  
 Düğme görüntüler cihaz bağlamı.  
  
 [in] `rect`  
 Düğmenin sınırlayıcı dikdörtgenini.  
  
 [in] `pImages`  
 Görüntüleri düğmesi ile ilişkili koleksiyonu.  
  
 [in] `bHorz`  
 Üst araç çubuğu yerleştirme durumu. `TRUE` ne zaman araç yerleştirilmiştir yatay ve `FALSE` zaman araç yerleştirilmiştir dikey olarak.  
  
 [in] `bCustomizeMode`  
 Uygulama özelleştirme modunda olup olmadığı.  
  
 [in] `bHighlight`  
 Birleşik giriş kutusu düğmesi vurgulanmış çizin görüntülenmeyeceğini belirtir.  
  
 [in] `bDrawBorder`  
 Birleşik giriş kutusu düğmesi kenarlık ile çizme görüntülenmeyeceğini belirtir.  
  
 [in] `bGrayDisabledButtons`  
 `TRUE` Gölgeli devre dışı düğmeleri çizmek için; `FALSE` devre dışı kullanmak için koleksiyon görüntüler.  
  
##  <a name="ondrawoncustomizelist"></a>  CMFCToolBarComboBoxButton::OnDrawOnCustomizeList  
 Birleşik giriş kutusu düğmesi çizmek için framework tarafından çağrılan **komutları** bölmesinde **Özelleştir** iletişim kutusu.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Birleşik giriş kutusu düğmesi görüntüler cihaz bağlamı.  
  
 [in] `rect`  
 Birleşik giriş kutusu düğmesi sınırlayıcı dikdörtgenini.  
  
 [in] `bSelected`  
 `TRUE` Birleşik giriş kutusu düğmesi seçilirse; Aksi takdirde `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu düğmesinin piksel cinsinden genişliği.  
  
##  <a name="onglobalfontschanged"></a>  CMFCToolBarComboBoxButton::OnGlobalFontsChanged  
 Uygulama yazı tipi değiştiğinde birleşik giriş kutusu düğmesi yazı tipi ayarlamak için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
##  <a name="onmove"></a>  CMFCToolBarComboBoxButton::OnMove  
 Üst araç taşındığında birleşik giriş kutusu düğmesi konumunu değiştirmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnMove();
```  
  
##  <a name="onshow"></a>  CMFCToolBarComboBoxButton::OnShow  
 Birleşik giriş kutusu düğmesi gizli ya da görüntülenen çerçevesi tarafından çağrılır.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bShow`  
 Birleşik giriş kutusu düğmesi görüntülemek veya gizlemek kullanılıp belirtir.  
  
##  <a name="onsize"></a>  CMFCToolBarComboBoxButton::OnSize  
 Üst araç boyutu değiştiğinde birleşik giriş kutusu düğmesi boyutunu değiştirmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iSize`  
 Birleşik giriş kutusu düğmesi yeni genişliği.  
  
##  <a name="onupdatetooltip"></a>  CMFCToolBarComboBoxButton::OnUpdateToolTip  
 Kullanıcı birleşik giriş kutusu düğmesi için araç ipucu değiştirdiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pWndParent`  
 Birleşik giriş kutusu düğmesi için üst pencere işaretçi.  
  
 [in] `iButtonIndex`  
 Birleşik giriş kutusu düğmesi kimliği.  
  
 [in] `wndToolTip`  
 Birleşik giriş kutusu düğmesi ile ilişkilendirmek için araç ipucu.  
  
 [in] `str`  
 Araç İpucu metni.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem; olay işliyorsa Aksi takdirde `FALSE`.  
  
##  <a name="removeallitems"></a>  CMFCToolBarComboBoxButton::RemoveAllItems  
 Tüm öğeleri listesi ve düzenleme kutularından siler.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Listeden tüm öğeler kutu ve bir birleşik giriş kutusu denetimi Düzenle kaldırır.  
  
##  <a name="selectitem"></a>  CMFCToolBarComboBoxButton::SelectItem  
 Bir öğeyi liste kutusunda seçer.  
  
```  
BOOL SelectItem(
    int iIndex,  
    BOOL bNotify=TRUE);  
  
BOOL SelectItem(DWORD_PTR dwData);  
BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iIndex`  
 Liste kutusunda öğenin sıfır tabanlı dizini.  
  
 [in] `bNotify`  
 `TRUE` Birleşik giriş kutusu düğmesi seçimin bildirmek için; Aksi takdirde `FALSE`.  
  
 [in] `dwData`  
 Liste kutusunda bir öğesiyle ilişkili veriler.  
  
 [in] `lpszText`  
 Liste kutusunda bir öğenin metni.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
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
 [in] `uiCmd`  
 Liste kutusu içeren birleşik giriş kutusu düğmesi komut kimliği.  
  
 [in] `iIndex`  
 Liste kutusunda öğenin sıfır tabanlı dizini. -1 değeri liste kutusunda herhangi bir geçerli seçimi kaldırır ve düzenleme kutusuna temizler.  
  
 [in] `dwData`  
 Liste kutusunda bir öğe verileri.  
  
 [in] `lpszText`  
 Liste kutusunda bir öğenin metni.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="serialize"></a>  CMFCToolBarComboBoxButton::Serialize  
 Bu nesne arşivden okur veya arşive yazar.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 [içinde out] `ar`  
 `CArchive` Nesne seri hale getirilemedi.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlarında `CArchive` nesne belirlemek bu yöntem okur veya arşive yazar.  
  
##  <a name="setaccdata"></a>  CMFCToolBarComboBoxButton::SetACCData  
 Belirtilen doldurur `CAccessibilityData` erişilebilirlik verileri birleşik giriş kutusu düğmesini kullanarak nesne.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pParent`  
 Birleşik giriş kutusu düğmesi üst pencere.  
  
 [out] `data`  
 A `CAccessibilityData` erişilebilirlik verileri birleşik giriş kutusu düğmesinden alan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
##  <a name="setcentervert"></a>  CMFCToolBarComboBoxButton::SetCenterVert  
 Birleşik giriş kutusu düğmelerini dikey konumunu uygulamada ayarlar.  
  
```  
static void SetCenterVert(BOOL bCenterVert=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bCenterVert`  
 `TRUE` Birleşik giriş kutusu düğmesi araç çubuğunda merkezine; `FALSE` birleşik giriş kutusu düğmesi araç üstüne hizalamak için.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, birleşik giriş kutusu düğmeleri dön hizalanır.  
  
##  <a name="setcontextmenuid"></a>  CMFCToolBarComboBoxButton::SetContextMenuID  
 Kısayol menüsü kaynak kimliği birleşik giriş kutusu düğmesi ayarlar.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiResID`  
 Kısayol menüsü kaynak kimliği  
  
##  <a name="setdropdownheight"></a>  CMFCToolBarComboBoxButton::SetDropDownHeight  
 Bu bırakıldığında liste kutusu yüksekliğini ayarlar.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nHeight`  
 Liste kutusu piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan yükseklik 150 pikseldir.  
  
##  <a name="setflatmode"></a>  CMFCToolBarComboBoxButton::SetFlatMode  
 Birleşik giriş kutusu düğmelerin düz stil görünümünü uygulamada ayarlar.  
  
```  
static void SetFlatMode(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bFlat`  
 `TRUE` düz stil görünümü için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Birleşik giriş kutusu düğmeleri için varsayılan düz stili `FALSE`.  
  
##  <a name="setstyle"></a>  CMFCToolBarComboBoxButton::SetStyle  
 Belirtilen stili birleşik giriş kutusu düğmesi ayarlar ve değil devre dışıysa denetimi yeniden çizer.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nStyle`  
 Bitsel bir birleşimi (veya) araç çubuğu stilleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Araç çubuğu düğmesi stilleri listesi için bkz: [ToolBar denetim stilleri](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="settext"></a>  CMFCToolBarComboBoxButton::SetText  
 Metin kutusu düğmesi açılan düzenleme kutusuna ayarlar.  
  
```  
void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszText`  
 Metin düzenleme kutusu içeren bir dize işaretçi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)



