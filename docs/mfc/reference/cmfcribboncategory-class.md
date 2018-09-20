---
title: CMFCRibbonCategory sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory::CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory::AddHidden
- AFXRIBBONCATEGORY/CMFCRibbonCategory::AddPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::CopyFrom
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindByData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindByID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindPanelWithElem
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetContextID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetDroppedDown
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetElements
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetElementsByID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetFirstVisibleElement
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetFocused
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetHighlighted
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetImageCount
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetImageSize
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetItemIDsList
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetLastVisibleElement
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetLargeImages
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetMaxHeight
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetName
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelCount
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelFromPoint
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelIndex
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentButton
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentMenuBar
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentRibbonBar
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetRect
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetSmallImages
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTabColor
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTabRect
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTextTopLine
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetVisibleElements
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HighlightPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTest
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTestEx
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTestScrollButtons
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsActive
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsVisible
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsWindows7Look
- AFXRIBBONCATEGORY/CMFCRibbonCategory::NotifyControlCommand
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnCancelMode
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDraw
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDrawImage
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDrawMenuBorder
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnKey
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnLButtonDown
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnLButtonUp
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnMouseMove
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnRTLChanged
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnScrollHorz
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnUpdateCmdUI
- AFXRIBBONCATEGORY/CMFCRibbonCategory::RecalcLayout
- AFXRIBBONCATEGORY/CMFCRibbonCategory::RemovePanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::ReposPanels
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetCollapseOrder
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetKeys
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetName
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetTabColor
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCategory [MFC], CMFCRibbonCategory
- CMFCRibbonCategory [MFC], AddHidden
- CMFCRibbonCategory [MFC], AddPanel
- CMFCRibbonCategory [MFC], CopyFrom
- CMFCRibbonCategory [MFC], FindByData
- CMFCRibbonCategory [MFC], FindByID
- CMFCRibbonCategory [MFC], FindPanelWithElem
- CMFCRibbonCategory [MFC], GetContextID
- CMFCRibbonCategory [MFC], GetData
- CMFCRibbonCategory [MFC], GetDroppedDown
- CMFCRibbonCategory [MFC], GetElements
- CMFCRibbonCategory [MFC], GetElementsByID
- CMFCRibbonCategory [MFC], GetFirstVisibleElement
- CMFCRibbonCategory [MFC], GetFocused
- CMFCRibbonCategory [MFC], GetHighlighted
- CMFCRibbonCategory [MFC], GetImageCount
- CMFCRibbonCategory [MFC], GetImageSize
- CMFCRibbonCategory [MFC], GetItemIDsList
- CMFCRibbonCategory [MFC], GetLastVisibleElement
- CMFCRibbonCategory [MFC], GetLargeImages
- CMFCRibbonCategory [MFC], GetMaxHeight
- CMFCRibbonCategory [MFC], GetName
- CMFCRibbonCategory [MFC], GetPanel
- CMFCRibbonCategory [MFC], GetPanelCount
- CMFCRibbonCategory [MFC], GetPanelFromPoint
- CMFCRibbonCategory [MFC], GetPanelIndex
- CMFCRibbonCategory [MFC], GetParentButton
- CMFCRibbonCategory [MFC], GetParentMenuBar
- CMFCRibbonCategory [MFC], GetParentRibbonBar
- CMFCRibbonCategory [MFC], GetRect
- CMFCRibbonCategory [MFC], GetSmallImages
- CMFCRibbonCategory [MFC], GetTabColor
- CMFCRibbonCategory [MFC], GetTabRect
- CMFCRibbonCategory [MFC], GetTextTopLine
- CMFCRibbonCategory [MFC], GetVisibleElements
- CMFCRibbonCategory [MFC], HighlightPanel
- CMFCRibbonCategory [MFC], HitTest
- CMFCRibbonCategory [MFC], HitTestEx
- CMFCRibbonCategory [MFC], HitTestScrollButtons
- CMFCRibbonCategory [MFC], IsActive
- CMFCRibbonCategory [MFC], IsVisible
- CMFCRibbonCategory [MFC], IsWindows7Look
- CMFCRibbonCategory [MFC], NotifyControlCommand
- CMFCRibbonCategory [MFC], OnCancelMode
- CMFCRibbonCategory [MFC], OnDraw
- CMFCRibbonCategory [MFC], OnDrawImage
- CMFCRibbonCategory [MFC], OnDrawMenuBorder
- CMFCRibbonCategory [MFC], OnKey
- CMFCRibbonCategory [MFC], OnLButtonDown
- CMFCRibbonCategory [MFC], OnLButtonUp
- CMFCRibbonCategory [MFC], OnMouseMove
- CMFCRibbonCategory [MFC], OnRTLChanged
- CMFCRibbonCategory [MFC], OnScrollHorz
- CMFCRibbonCategory [MFC], OnUpdateCmdUI
- CMFCRibbonCategory [MFC], RecalcLayout
- CMFCRibbonCategory [MFC], RemovePanel
- CMFCRibbonCategory [MFC], ReposPanels
- CMFCRibbonCategory [MFC], SetCollapseOrder
- CMFCRibbonCategory [MFC], SetData
- CMFCRibbonCategory [MFC], SetKeys
- CMFCRibbonCategory [MFC], SetName
- CMFCRibbonCategory [MFC], SetTabColor
ms.assetid: 99ba25b6-d060-4fdd-bfab-3c46c22981bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1cc273274068e65bd5066a149f52d2f7cc39271
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429844"
---
# <a name="cmfcribboncategory-class"></a>CMFCRibbonCategory sınıfı

`CMFCRibbonCategory` Sınıfı bir dizi içeren bir Şerit sekmesi uygular [Şerit panel](../../mfc/reference/cmfcribbonpanel-class.md).

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonCategory : public CObject
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonCategory::CMFCRibbonCategory](#cmfcribboncategory)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonCategory::AddHidden](#addhidden)|Hidden öğesi Şerit kategorisine ekler.|
|[CMFCRibbonCategory::AddPanel](#addpanel)|Yeni bir panel Şerit kategorisine ekler.|
|[CMFCRibbonCategory::CopyFrom](#copyfrom)||
|[CMFCRibbonCategory::FindByData](#findbydata)||
|[CMFCRibbonCategory::FindByID](#findbyid)||
|[CMFCRibbonCategory::FindPanelWithElem](#findpanelwithelem)||
|[CMFCRibbonCategory::GetContextID](#getcontextid)|Şerit kategorisi bağlam Kimliğini döndürür.|
|[CMFCRibbonCategory::GetData](#getdata)|Şerit kategorisi ile ilişkili kullanıcı tanımlı veri döndürür.|
|[CMFCRibbonCategory::GetDroppedDown](#getdroppeddown)||
|[CMFCRibbonCategory::GetElements](#getelements)||
|[CMFCRibbonCategory::GetElementsByID](#getelementsbyid)||
|[CMFCRibbonCategory::GetFirstVisibleElement](#getfirstvisibleelement)|Şerit kategorisine ait görünen bir ilk öğesi alın.|
|[CMFCRibbonCategory::GetFocused](#getfocused)|Odaklanan öğeyi döndürür.|
|[CMFCRibbonCategory::GetHighlighted](#gethighlighted)|Vurgulanan öğeyi döndürür.|
|[CMFCRibbonCategory::GetImageCount](#getimagecount)||
|[CMFCRibbonCategory::GetImageSize](#getimagesize)||
|[CMFCRibbonCategory::GetItemIDsList](#getitemidslist)||
|[CMFCRibbonCategory::GetLastVisibleElement](#getlastvisibleelement)|Şerit kategorisine ait son görünür bir öğe alın|
|[CMFCRibbonCategory::GetLargeImages](#getlargeimages)|Şerit kategorisi kullanan büyük görüntü listesini bir başvuru döndürür.|
|[CMFCRibbonCategory::GetMaxHeight](#getmaxheight)||
|[CMFCRibbonCategory::GetName](#getname)||
|[CMFCRibbonCategory::GetPanel](#getpanel)|Belirtilen dizinde bulunan Şerit paneline bir işaretçi döndürür.|
|[CMFCRibbonCategory::GetPanelCount](#getpanelcount)|Şerit paneli Şerit kategorisi döndürür.|
|[CMFCRibbonCategory::GetPanelFromPoint](#getpanelfrompoint)||
|[CMFCRibbonCategory::GetPanelIndex](#getpanelindex)|Belirtilen Şerit paneline dizinini döndürür.|
|[CMFCRibbonCategory::GetParentButton](#getparentbutton)||
|[CMFCRibbonCategory::GetParentMenuBar](#getparentmenubar)||
|[CMFCRibbonCategory::GetParentRibbonBar](#getparentribbonbar)||
|[CMFCRibbonCategory::GetRect](#getrect)||
|[CMFCRibbonCategory::GetSmallImages](#getsmallimages)|Kategori kullanan küçük resimler listesine bir başvuru döndürür.|
|[CMFCRibbonCategory::GetTabColor](#gettabcolor)|Şerit kategorisi sekmesinde geçerli rengi döndürür.|
|[CMFCRibbonCategory::GetTabRect](#gettabrect)||
|[CMFCRibbonCategory::GetTextTopLine](#gettexttopline)||
|[CMFCRibbonCategory::GetVisibleElements](#getvisibleelements)|Şerit kategorisine ait tüm görünür öğeleri alın.|
|[CMFCRibbonCategory::HighlightPanel](#highlightpanel)||
|[CMFCRibbonCategory::HitTest](#hittest)||
|[CMFCRibbonCategory::HitTestEx](#hittestex)||
|[CMFCRibbonCategory::HitTestScrollButtons](#hittestscrollbuttons)||
|[CMFCRibbonCategory::IsActive](#isactive)||
|[CMFCRibbonCategory::IsVisible](#isvisible)|Şerit kategorisi görünür olup olmadığını belirler.|
|[CMFCRibbonCategory::IsWindows7Look](#iswindows7look)|Üst Şerit Windows 7 stil görünümünü (küçük bir dikdörtgen uygulama düğme) olup olmadığını gösterir|
|[CMFCRibbonCategory::NotifyControlCommand](#notifycontrolcommand)||
|[CMFCRibbonCategory::OnCancelMode](#oncancelmode)||
|[CMFCRibbonCategory::OnDraw](#ondraw)||
|[CMFCRibbonCategory::OnDrawImage](#ondrawimage)||
|[CMFCRibbonCategory::OnDrawMenuBorder](#ondrawmenuborder)||
|[CMFCRibbonCategory::OnKey](#onkey)|Bir kullanıcı bir klavye düğmesine bastığında framework tarafından çağırılır.|
|[CMFCRibbonCategory::OnLButtonDown](#onlbuttondown)||
|[CMFCRibbonCategory::OnLButtonUp](#onlbuttonup)||
|[CMFCRibbonCategory::OnMouseMove](#onmousemove)||
|[CMFCRibbonCategory::OnRTLChanged](#onrtlchanged)||
|[CMFCRibbonCategory::OnScrollHorz](#onscrollhorz)||
|[CMFCRibbonCategory::OnUpdateCmdUI](#onupdatecmdui)||
|[CMFCRibbonCategory::RecalcLayout](#recalclayout)||
|[CMFCRibbonCategory::RemovePanel](#removepanel)||
|[CMFCRibbonCategory::ReposPanels](#repospanels)||
|[CMFCRibbonCategory::SetCollapseOrder](#setcollapseorder)|Şerit kategorisinde bulunan Şerit paneli Daralt sırasını tanımlar.|
|[CMFCRibbonCategory::SetData](#setdata)|Kullanıcı tanımlı veri Şerit kategorisi içinde depolar.|
|[CMFCRibbonCategory::SetKeys](#setkeys)|Bir keytip Şerit kategorisine atar.|
|[CMFCRibbonCategory::SetName](#setname)||
|[CMFCRibbonCategory::SetTabColor](#settabcolor)|Şerit kategorisi rengini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Genellikle, bir Şerit kategorisi dolaylı olarak çağırarak oluşturduğunuz [CMFCRibbonBar::AddCategory](../../mfc/reference/cmfcribbonbar-class.md#addcategory), yeni oluşturulan Şerit kategorisi için bir işaretçi döndürür. Çağırarak kategorisine panel ekleme [CMFCRibbonCategory::AddPanel](#addpanel).

`CMFCRibbonTab` Sınıfı Şerit kategorisi çizer. Öğesinden türetilen [CMFCRibbonBaseElement sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md).

Aşağıdaki örnek, bir Şerit kategorisi oluşturmak ve bir panel eklemek gösterilmiştir.

```cpp
// Create a new ribbon category and get a pointer to it`
CMFCRibbonCategory* pCategory = m_wndRibbonBar.AddCategory
    (_T("&Write"),           // Category name
    IDB_WRITE,               // Category small images (16 x 16)
    IDB_WRITE_LARGE);        // Category large images (32 x 32)

// Add a panel to the new category
CMFCRibbonPanel* pPanel = pCategory->AddPanel (
    _T("Clipboard"),                // Panel name
    m_PanelIcons.ExtractIcon (0));  // Panel icon
```

Aşağıdaki diyagramda bir şekil RibbonApp örnek uygulamadan ana kategorinin gösterilmektedir.

![CMFCRibbonCategory görüntü](../../mfc/reference/media/cmfcribboncategory.png "cmfcribboncategory")

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMFCRibbonCategory`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxribboncategory.h

##  <a name="addhidden"></a>  CMFCRibbonCategory::AddHidden

Özelleştirme iletişim kutusunda görüntülenen bir Şerit öğeleri dizisi için belirtilen Şerit öğesi ekler.

```
void AddHidden(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>Parametreler

*pElem*<br/>
[in] Bir Şerit öğesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Şerit öğeleri özelleştirme iletişim kutusunda hızlı erişim araç çubuğuna eklediğiniz komutlar şunlardır:

##  <a name="addpanel"></a>  CMFCRibbonCategory::AddPanel

Bir Şerit paneli Şerit kategorisi oluşturur.

```
CMFCRibbonPanel* AddPanel(
    LPCTSTR lpszPanelName,
    HICON hIcon = 0,
    CRuntimeClass* pRTI = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszPanelName*<br/>
[in] Yeni Şerit panelin adına yönelik işaretçi.

*hIcon*<br/>
[in] İçin yeni bir Şerit panel varsayılan simgeyi işleyin.

*pRTI*<br/>
[in] Bir Şerit panel için çalışma zamanı sınıf bilgileri işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa yeni bir Şerit panel işaretçi; panel oluşturulmadı, bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Bir Şerit paneli oluşturmak istiyorsanız, kendi çalışma zamanı sınıf bilgileri belirtmelisiniz *pRTI*. Özel Şerit paneli sınıfı nesnesinden türetilmesi `CMFCRibbonPanel` sınıfı.

Şerit öğeleri görüntülemek için yeterli alan olmadığında Şerit paneline varsayılan simgesi görüntülenir.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `AddPanel` yönteminde `CMFCRibbonCategory` sınıfı.

[!code-cpp[NVC_MFC_RibbonApp#10](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_1.cpp)]

##  <a name="cmfcribboncategory"></a>  CMFCRibbonCategory::CMFCRibbonCategory

Oluşturur ve başlatır bir [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) nesne.

```
CMFCRibbonCategory(
    CMFCRibbonBar* pParenrRibbonBar,
    LPCTSTR lpszName,
    UINT uiSmallImagesResID,
    UINT uiLargeImagesResID,
    CSize sizeSmallImage = CSize(16,
    16),
    CSize sizeLargeImage = CSize(32,
    32));
```

### <a name="parameters"></a>Parametreler

*pParenrRibbonBar*<br/>
[in] Üst Şerit çubuğuna Şerit kategorisi için işaretçi.

*lpszName*<br/>
[in] Şerit kategorisi adı.

*uiSmallImagesResID*<br/>
[in] Şerit kategorideki Şerit öğeleri tarafından kullanılan küçük resimler için resim listesi kaynak kimliği.

*uiLargeImagesResID*<br/>
[in] Şerit kategorideki Şerit öğeleri tarafından kullanılan büyük resimler için resim listesi kaynak kimliği.

*sizeSmallImage*<br/>
[in] Şerit kategorideki Şerit öğeleri için küçük resimlerin boyutunu varsayılan.

*sizeLargeImage*<br/>
[in] Varsayılan olarak büyük resimler için Şerit kategorideki Şerit öğeleri boyutu.

##  <a name="copyfrom"></a>  CMFCRibbonCategory::CopyFrom

Belirtilen durumunu kopyalar [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) geçerli [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) nesne.

```
virtual void CopyFrom(CMFCRibbonCategory& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[in] Kaynak `CMFCRibbonCategory` nesne.

### <a name="remarks"></a>Açıklamalar

##  <a name="findbydata"></a>  CMFCRibbonCategory::FindByData

Belirtilen verilerle ilişkili Şerit öğesi alır.

```
CMFCRibbonBaseElement* FindByData(
    DWORD_PTR dwData,
    BOOL bVisibleOnly = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*dwData*<br/>
[in] Bir Şerit öğesi ile ilişkili veriler.

*bVisibleOnly*<br/>
[in] Hızlı erişim Şerit öğeleri aramaya dahil edilmesi için TRUE; Arama hızlı erişim Şerit öğeleri hariç tutmak için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa bir Şerit öğesi için işaretçi; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

##  <a name="findbyid"></a>  CMFCRibbonCategory::FindByID

Belirtilen komut kimliğiyle ilişkilendirilen Şerit öğesi alır.

```
CMFCRibbonBaseElement* FindByID(
    UINT uiCmdID,
    BOOL bVisibleOnly = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*uiCmdID*<br/>
[in] Bir Şerit öğesi ile ilişkili komut kimliği.

*bVisibleOnly*<br/>
[in] Hızlı erişim Şerit öğeleri aramaya dahil edilmesi için TRUE; Arama hızlı erişim Şerit öğeleri hariç tutmak için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa bir Şerit öğesi için işaretçi; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

##  <a name="findpanelwithelem"></a>  CMFCRibbonCategory::FindPanelWithElem

Belirtilen Şerit öğesi içeren bir Şerit panel alır.

```
CMFCRibbonPanel* FindPanelWithElem(const CMFCRibbonBaseElement* pElement);
```

### <a name="parameters"></a>Parametreler

*pElement*<br/>
[in] Bir Şerit öğesi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa bir Şerit paneli işaretçi; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

##  <a name="getcontextid"></a>  CMFCRibbonCategory::GetContextID

Şerit kategorisi bağlam Kimliğini alır.

```
UINT GetContextID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit kategorisi kimliği bağlam.

### <a name="remarks"></a>Açıklamalar

Şerit kategorisi bir bağlam Şerit kategorisi değilse içerik kimliği 0'dır.

##  <a name="getdata"></a>  CMFCRibbonCategory::GetData

Şerit kategorisi ile ilişkili kullanıcı tanımlı veri alır.

```
DWORD_PTR GetData() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit kategorisi ile ilişkili kullanıcı tanımlı veri.

##  <a name="getdroppeddown"></a>  CMFCRibbonCategory::GetDroppedDown

Şu anda görüntülenen, açılır menü içeren bir Şerit öğesi için bir işaretçi alır.

```
CMFCRibbonBaseElement* GetDroppedDown();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa bir Şerit öğesi için işaretçi; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

##  <a name="getelements"></a>  CMFCRibbonCategory::GetElements

Şerit kategorisi tüm Şerit öğeleri alır.

```
void GetElements(
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```

### <a name="parameters"></a>Parametreler

*arElements*<br/>
[out içinde] Başvuru bir [CArray](../../mfc/reference/carray-class.md) Şerit öğeleri.

### <a name="remarks"></a>Açıklamalar

Hızlı Erişim Araç çubuğu üzerinde kullanılmak üzere tasarlanmış bir Şerit öğeleri, dizide dahil edilir.

##  <a name="getelementsbyid"></a>  CMFCRibbonCategory::GetElementsByID

Belirtilen komut kimliği ile ilişkili olan tüm Şerit öğeleri alır.

```
void GetElementsByID(
    UINT uiCmdID,
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```

### <a name="parameters"></a>Parametreler

*uiCmdID*<br/>
[in] Bir Şerit öğesi ile ilişkili komut kimliği.

*arElements*<br/>
[out içinde] Başvuru bir [CArray](../../mfc/reference/carray-class.md) Şerit öğeleri.

### <a name="remarks"></a>Açıklamalar

Hızlı Erişim Araç çubuğu üzerinde kullanılmak üzere tasarlanmış bir Şerit öğeleri, dizide dahil edilir.

##  <a name="getfirstvisibleelement"></a>  CMFCRibbonCategory::GetFirstVisibleElement

Şerit kategorisine ait ilk görünür öğeyi alır.

```
CMFCRibbonBaseElement* GetFirstVisibleElement() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görünür ilk öğesinin işaretçisi; Kategori görünür olan herhangi bir öğe yoksa NULL olabilir.

### <a name="remarks"></a>Açıklamalar

##  <a name="getfocused"></a>  CMFCRibbonCategory::GetFocused

Odaklanan öğeyi döndürür.

```
CMFCRibbonBaseElement* GetFocused();
```

### <a name="return-value"></a>Dönüş Değeri

Odaklanan öğeyi veya NULL bir işaretçi.

### <a name="remarks"></a>Açıklamalar

##  <a name="gethighlighted"></a>  CMFCRibbonCategory::GetHighlighted

Vurgulanan öğeyi döndürür.

```
CMFCRibbonBaseElement* GetHighlighted();
```

### <a name="return-value"></a>Dönüş Değeri

Vurgulanan öğe veya öğe vurgulanır, NULL bir işaretçi.

### <a name="remarks"></a>Açıklamalar

##  <a name="getimagecount"></a>  CMFCRibbonCategory::GetImageCount

Şerit kategoride bulunan belirtilen görüntü listesinden görüntü sayısını alır.

```
int GetImageCount(BOOL bIsLargeImage) const;
```

### <a name="parameters"></a>Parametreler

*bIsLargeImage*<br/>
[in] Büyük görüntü listesinden görüntü sayısı için TRUE; Küçük görüntü listesinin görüntüleri sayısı için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen görüntü listesinden görüntü sayısı.

### <a name="remarks"></a>Açıklamalar

##  <a name="getimagesize"></a>  CMFCRibbonCategory::GetImageSize

Belirtilen görüntü listesinde Şerit kategorisinde yer alan bir görüntü boyutunu alır.

```
CSize GetImageSize(BOOL bIsLargeImage) const;
```

### <a name="parameters"></a>Parametreler

*bIsLargeImage*<br/>
[in] Büyük resimler boyutu için TRUE; Küçük resimlerin boyutunu için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen görüntü listesinden görüntü boyutu.

### <a name="remarks"></a>Açıklamalar

Alınan boyutu genel görüntü ölçek faktörü içerir.

##  <a name="getitemidslist"></a>  CMFCRibbonCategory::GetItemIDsList

Komut kimlikleri için Şerit öğeleri Şerit kategorisinde yer alır.

```
void GetItemIDsList(
    CList<UINT, UINT>& lstItems,
    BOOL bHiddenOnly = FALSE) const;
```

### <a name="parameters"></a>Parametreler

*lstItems*<br/>
[out] Komut kimlikleri için Şerit kategorideki Şerit öğeleri listesi.

*bHiddenOnly*<br/>
[in] Şerit paneli Şerit kategorisi içinde görüntülenen bir Şerit öğeleri dışlamak için TRUE; Tüm Şerit öğeleri Şerit kategorisine eklemek için FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="getlargeimages"></a>  CMFCRibbonCategory::GetLargeImages

Şerit kategoride bulunan büyük görüntü listesini alır.

```
CMFCToolBarImages& GetLargeImages();
```

### <a name="return-value"></a>Dönüş Değeri

Şerit kategoride bulunan büyük görüntüleri listesi.

##  <a name="getlastvisibleelement"></a>  CMFCRibbonCategory::GetLastVisibleElement

Şerit kategorisine ait son görünür öğeyi alır.

```
CMFCRibbonBaseElement* GetLastVisibleElement() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görünür son öğesinin işaretçisi; Kategori görünür olan herhangi bir öğe yoksa NULL olabilir.

### <a name="remarks"></a>Açıklamalar

##  <a name="getmaxheight"></a>  CMFCRibbonCategory::GetMaxHeight

Şerit kategoride bulunan Şerit paneli maksimum yüksekliğini alır.

```
int GetMaxHeight(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı Şerit paneli için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Şerit kategoride bulunan Şerit paneli maksimum yüksekliği.

### <a name="remarks"></a>Açıklamalar

Şerit paneli için üst ve alt kenar boşlukları yüksekliğini alınan değeri içerir.

##  <a name="getname"></a>  CMFCRibbonCategory::GetName

Şerit kategorisinin adını alır.

```
LPCTSTR GetName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit kategorisi adı.

### <a name="remarks"></a>Açıklamalar

##  <a name="getpanel"></a>  CMFCRibbonCategory::GetPanel

Belirtilen dizinde bulunan Şerit paneline bir işaretçi döndürür.

```
CMFCRibbonPanel* GetPanel(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
[in] Bir Şerit paneli sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizinde bulunan Şerit paneline işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir özel durum *nIndex* je mimo rozsah.

##  <a name="getpanelcount"></a>  CMFCRibbonCategory::GetPanelCount

Şerit paneli Şerit kategorisi döndürür.

```
int GetPanelCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit paneli Şerit kategorisinde sayısı.

##  <a name="getpanelfrompoint"></a>  CMFCRibbonCategory::GetPanelFromPoint

Belirtilen nokta içinde yer alıyorsa, Şerit paneline bir işaretçi alır.

```
CMFCRibbonPanel* GetPanelFromPoint(CPoint point) const;
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] X ve y koordinatları penceresinin sol üst köşesindeki göre işaretçinin.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa bir Şerit paneli işaretçi; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Şerit kategorisinde bulunan Şerit paneli test edilmez.

##  <a name="getpanelindex"></a>  CMFCRibbonCategory::GetPanelIndex

Belirtilen Şerit paneline sıfır tabanlı dizinini alır.

```
int GetPanelIndex(const CMFCRibbonPanel* pPanel) const;
```

### <a name="parameters"></a>Parametreler

*pPanel*<br/>
[in] Bir Şerit paneli işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bir Şerit panel yöntem başarılı olursa sıfır tabanlı dizini; Aksi takdirde-1.

### <a name="remarks"></a>Açıklamalar

Şerit kategorisinde bulunan Şerit paneli aranır.

##  <a name="getparentbutton"></a>  CMFCRibbonCategory::GetParentButton

Şerit kategorisinin üst Şerit öğesi alır.

```
CMFCRibbonBaseElement* GetParentButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir üst öğe yoksa üst Şerit öğesi veya NULL bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="getparentmenubar"></a>  CMFCRibbonCategory::GetParentMenuBar

Üst menü çubuğu için bir işaretçi döndürür `CMFCRibbonCategory` nesne.

```
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçeriğini döndürür `m_pParentMenuBar` üye korumalı.

### <a name="remarks"></a>Açıklamalar

##  <a name="getparentribbonbar"></a>  CMFCRibbonCategory::GetParentRibbonBar

Üst Şerit çubuğuna Şerit kategorisi için alır.

```
CMFCRibbonBar* GetParentRibbonBar() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üst Şerit çubuğuna Şerit kategorisi için işaretçi.

### <a name="remarks"></a>Açıklamalar

##  <a name="getrect"></a>  CMFCRibbonCategory::GetRect

Şerit kategorisi için görünen dikdörtgen alır.

```
CRect GetRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit kategorisi için görünen dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Şerit kategorisi için görünen dikdörtgen kategori sekmesini içermez.

##  <a name="getsmallimages"></a>  CMFCRibbonCategory::GetSmallImages

Şerit kategoride bulunan küçük görüntü listesini alır.

```
CMFCToolBarImages& GetSmallImages();
```

### <a name="return-value"></a>Dönüş Değeri

Şerit kategorisinde bulunan küçük resimler listesi.

##  <a name="gettabcolor"></a>  CMFCRibbonCategory::GetTabColor

Şerit kategorisi sekmesinde geçerli rengi döndürür.

```
AFX_RibbonCategoryColor GetTabColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit kategorisi sekmesinde geçerli rengi.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer, aşağıdaki numaralandırılmış değerlerden biri olabilir:

- AFX_CategoryColor_Red

- AFX_CategoryColor_Orange

- AFX_CategoryColor_Yellow

- AFX_CategoryColor_Green

- AFX_CategoryColor_Blue

- AFX_CategoryColor_Indigo

- AFX_CategoryColor_Violet

##  <a name="gettabrect"></a>  CMFCRibbonCategory::GetTabRect

Şerit kategorisi sekmesi için görünen dikdörtgen alır.

```
CRect GetTabRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit kategorisi sekmesi için görünen dikdörtgen.

### <a name="remarks"></a>Açıklamalar

##  <a name="gettexttopline"></a>  CMFCRibbonCategory::GetTextTopLine

Büyük resimler görüntüleyen Şerit kategorisi Şerit düğmeleri metnin dikey konumu alır.

```
int GetTextTopLine() const;
```

### <a name="return-value"></a>Dönüş Değeri

Piksel cinsinden büyük resimler görüntüleyen Şerit düğmeleri metnin dikey konumu.

### <a name="remarks"></a>Açıklamalar

##  <a name="getvisibleelements"></a>  CMFCRibbonCategory::GetVisibleElements

Şerit kategorisine ait tüm görünür öğeleri alır.

```
void GetVisibleElements(
    CArray <CMFCRibbonBaseElement*,
    CMFCRibbonBaseElement*>& arElements);
```

### <a name="parameters"></a>Parametreler

*arElements*<br/>
Tüm görünür öğeleri dizisi.

### <a name="remarks"></a>Açıklamalar

##  <a name="highlightpanel"></a>  CMFCRibbonCategory::HighlightPanel

Belirtilen Şerit paneline vurgular.

```
CMFCRibbonPanel* HighlightPanel(
    CMFCRibbonPanel* pHLPanel,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pHLPanel*<br/>
[in] Şerit paneline vurgulamak için işaretçi.

*Noktası*<br/>
[in] X ve y koordinatları penceresinin sol üst köşesindeki göre işaretçinin.

### <a name="return-value"></a>Dönüş Değeri

Daha önce vurgulanan Şerit paneline işaretçi; Bu yöntem çağrıldığında hiçbir Şerit paneline vurgulanır, bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Bir Şerit paneli vurgulama hakkında daha fazla bilgi için bkz. [CMFCRibbonPanel::Highlight](../../mfc/reference/cmfcribbonpanel-class.md#highlight).

##  <a name="hittest"></a>  CMFCRibbonCategory::HitTest

Belirtilen nokta içinde yer alıyorsa, Şerit öğesi için bir işaretçi alır.

```
CMFCRibbonBaseElement* HitTest(
    CPoint point,
    BOOL bCheckPanelCaption = FALSE) const;
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] X ve y koordinatları penceresinin sol üst köşesindeki göre fare işaretçisi.

*bCheckPanelCaption*<br/>
[in] Şerit paneli resim yazısı test etmek için TRUE; Şerit paneli açıklamalı alt yazı hariç tutmak için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa bir Şerit öğesi için işaretçi; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Şerit kategorisinde bulunan Şerit öğeleri test edilmez.

##  <a name="hittestex"></a>  CMFCRibbonCategory::HitTestEx

Belirtilen nokta içinde yer alıyorsa, Şerit öğenin sıfır tabanlı dizinini alır.

```
int HitTestEx(CPoint point) const;
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] X ve y koordinatları penceresinin sol üst köşesindeki göre fare işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa bir Şerit öğenin sıfır tabanlı dizini; Aksi takdirde-1.

### <a name="remarks"></a>Açıklamalar

Şerit kategorisinde bulunan Şerit öğeleri test edilmez.

##  <a name="hittestscrollbuttons"></a>  CMFCRibbonCategory::HitTestScrollButtons

Bir Şerit kategorinin sola veya sağa kaydırma düğmesi içinde bir noktaya denk gelirse, bu düğme için bir işaretçi döndürür.

```
CMFCRibbonBaseElement* HitTestScrollButtons(CPoint point) const;
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] Test noktası.

### <a name="return-value"></a>Dönüş Değeri

Varsa *noktası* ya da sol sınırlayıcı dikdörtgenini veya Şerit kategorisi sağa kaydırma düğmesi içinde kalan, bu düğme için bir işaretçi döndürür veya aksi takdirde, NULL döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="isactive"></a>  CMFCRibbonCategory::IsActive

Şerit kategorisi etkin kategori Şerit çubuğu olup olmadığını belirtir.

```
BOOL IsActive() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit kategorisi etkin kategori ise TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Etkin Şerit kategorisi, Şerit paneli görüntüler.

##  <a name="isvisible"></a>  CMFCRibbonCategory::IsVisible

Şerit kategorisi görülüp görülemeyeceğini gösterir.

```
BOOL IsVisible() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit kategorisi görünür ise TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Görülebilir Şerit kategorisi kategori sekmesini görüntüleyin.

##  <a name="iswindows7look"></a>  CMFCRibbonCategory::IsWindows7Look

Üst Şerit Windows 7 (küçük bir dikdörtgen uygulama düğmesi) olup olmadığını gösterir.

```
BOOL IsWindows7Look() const;
```

### <a name="return-value"></a>Dönüş Değeri

Windows 7'yi arayın üst Şerit varsa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="notifycontrolcommand"></a>  CMFCRibbonCategory::NotifyControlCommand

Wm_notıfy komut ileti tümünü sunar `CMFCRibbonPanel` öğelerinde `CMFCRibbonCategory` kadar ileti ele alınır.

```
virtual BOOL NotifyControlCommand(
    BOOL bAccelerator,
    int nNotifyCode,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*bAccelerator*<br/>
[in] Eğer bu komutu bir Hızlandırıcı veya yanlış, aksi takdirde kaynağı.

*nNotifyCode*<br/>
[in] Uyarı kodu.

*wParam*<br/>
[in] İletinin WPARAM alan.

*lParam*<br/>
[in] İletinin LPARAM alan.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenmiş TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="oncancelmode"></a>  CMFCRibbonCategory::OnCancelMode

Tüm iptal modunda çağırır `CMFCRibbonPanel` öğelerini `CMFCRibbonCategory`.

```
virtual void OnCancelMode();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="ondraw"></a>  CMFCRibbonCategory::OnDraw

Şerit kategorisi çizmek için framework tarafından çağırılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Şerit kategorisi için bir cihaz bağlamı işaretçisi.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondrawimage"></a>  CMFCRibbonCategory::OnDrawImage

Belirtilen görüntü Şerit kategorisine göre çizilmesi gerektiğinde framework tarafından çağırılır.

```
virtual BOOL OnDrawImage(
    CDC* pDC,
    CRect rect,
    CMFCRibbonBaseElement* pElement,
    BOOL bIsLargeImage,
    BOOL nImageIndex,
    BOOL bCenter);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı görüntüsü için işaretçi.

*Rect*<br/>
[in] Resmi için dikdörtgen görüntüler.

*pElement*<br/>
[in] Görüntü içeren Şerit öğesinin işaretçisi.

*bIsLargeImage*<br/>
[in] Görüntü boyutu büyük olduğunda TRUE; Görüntü boyutunun küçük ise FALSE.

*nImageIndex*<br/>
[in] Görüntünün görüntü dizideki Şerit kategoride bulunan sıfır tabanlı dizini.

*bCenter*<br/>
[in] Görüntünün görüntü dikdörtgenin içindeki merkezi için TRUE; Görüntünün görüntü dikdörtgenin sol üst köşesinde bulunan çizmek için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondrawmenuborder"></a>  CMFCRibbonCategory::OnDrawMenuBorder

Bir açılan menü kenarlık çizmek için framework tarafından çağırılır.

```
virtual void OnDrawMenuBorder(
    CDC* pDC,
    CMFCRibbonPanelMenuBar* pMenuBar);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bu parametre kullanılmaz.

*pMenuBar*<br/>
[in] Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntemi hiçbir şey yapmaz. Bir açılan menü kenarlık çizmek için bu yöntemi yok sayın.

##  <a name="onkey"></a>  CMFCRibbonCategory::OnKey

Bir kullanıcı bir klavye düğmesine bastığında framework tarafından çağırılır.

```
virtual BOOL OnKey(UINT nChar);
```

### <a name="parameters"></a>Parametreler

*nChar*<br/>
Bir kullanıcı basılı anahtarı sanal anahtar kodu.

### <a name="remarks"></a>Açıklamalar

##  <a name="onlbuttondown"></a>  CMFCRibbonCategory::OnLButtonDown

Kullanıcının sol fare düğmesine bastığında Şerit öğesi belirtilen nokta altında almak için framework tarafından çağırılır.

```
virtual CMFCRibbonBaseElement* OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] X ve y koordinatları penceresinin sol üst köşesindeki göre fare işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa bir Şerit öğesi için işaretçi; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

##  <a name="onlbuttonup"></a>  CMFCRibbonCategory::OnLButtonUp

Kullanıcının sol fare düğmesini serbest bırakır ve Şerit kategorisi işaretçisi framework tarafından çağırılır.

```
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] X ve y koordinatları penceresinin sol üst köşesindeki göre işaretçinin.

### <a name="remarks"></a>Açıklamalar

##  <a name="onmousemove"></a>  CMFCRibbonCategory::OnMouseMove

Şerit kategorisi görüntüsünü güncelleştirmek için Şerit çubuğundaki işaretçiyi hareket ettirdiğinde framework tarafından çağırılır.

```
virtual void OnMouseMove(CPoint point);
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] X ve y koordinatları penceresinin sol üst köşesindeki göre işaretçinin.

### <a name="remarks"></a>Açıklamalar

##  <a name="onrtlchanged"></a>  CMFCRibbonCategory::OnRTLChanged

Düzen yönü değiştiğinde framework tarafından çağırılır.

```
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>Parametreler

*bIsRTL*<br/>
[in] Sağdan sola düzen ise TRUE; Soldan sağa düzen ise FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tüm Şerit paneli ve Şerit kategoride bulunan Şerit öğeleri düzenini ayarlar.

##  <a name="onscrollhorz"></a>  CMFCRibbonCategory::OnScrollHorz

Yatay yönde Şerit kategorisi kaydırır.

```
virtual BOOL OnScrollHorz(
    BOOL bScrollLeft,
    int nScrollOffset = 0);
```

### <a name="parameters"></a>Parametreler

*bScrollLeft*<br/>
[in] Sola kaydırma yapmak için TRUE; Sağa kaydırma için FALSE.

*nScrollOffset*<br/>
[in] Piksel cinsinden kaydırma uzaklığı.

### <a name="return-value"></a>Dönüş Değeri

Şerit kategorisi bir yatay yönde taşıdıysanız TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="onupdatecmdui"></a>  CMFCRibbonCategory::OnUpdateCmdUI

Çağrıları `OnUpdateCmdUI` üye işlevi her birinde `CMFCRibbonPanel` öğelerini `CMFCRibbonCategory` etkinleştirme veya devre dışı bir kullanıcı arabirimi öğeleri.

```
virtual void OnUpdateCmdUI(
    CMFCRibbonCmdUI* pCmdUI,
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
[in] İşaretçi `CMFCRibbonCmdUI` nesnesini kullanıcı arabirimi öğeleri olan etkin olmasını ve devre dışı olduğunu belirler.

*pTarget*<br/>
[in] Etkinleştirme veya devre dışı kullanıcı arabirimi öğelerini denetleyen pencere işaretçisi.

*bDisableIfNoHndler*<br/>
[in] İşleyici yok ileti eşlemesi içinde tanımlanmışsa, kullanıcı arabirimi öğesi devre dışı bırakmak için TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="recalclayout"></a>  CMFCRibbonCategory::RecalcLayout

Şerit kategorisi tüm denetimlere düzenini ayarlar.

```
virtual void RecalcLayout(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Şerit kategorisi için bir cihaz bağlamı işaretçisi.

### <a name="remarks"></a>Açıklamalar

##  <a name="removepanel"></a>  CMFCRibbonCategory::RemovePanel

Bir Şerit paneli Şerit kategorisi kaldırır.

```cpp
BOOL RemovePanel(
    int nIndex,
    BOOL bDelete = TRUE);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
[in] Dizin numarasını panel kaldırmak için. Çağırılarak [CMFCRibbonCategory::GetPanelIndex](#getpanelindex) yöntemi.

*bSil*<br/>
[in] Bellekten panelinde nesneyi silmek için TRUE; YANLIŞ panel nesnesi silmeden kaldırmak için.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa TRUE; Aksi takdirde FALSE.

##  <a name="repospanels"></a>  CMFCRibbonCategory::ReposPanels

Tüm denetimlere Şerit kategorisinde bulunan Şerit panel düzenini ayarlar.

```
virtual void ReposPanels(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı Şerit kategoride bulunan Şerit paneli için işaretçi.

### <a name="remarks"></a>Açıklamalar

##  <a name="setcollapseorder"></a>  CMFCRibbonCategory::SetCollapseOrder

İçinde Şerit kategorisi Şerit paneli Daralt sırasını tanımlar.

```
void SetCollapseOrder(const CArray<int,int>& arCollapseOrder);
```

### <a name="parameters"></a>Parametreler

*arCollapseOrder*<br/>
[in] Daralt sırasını belirtir. Dizinin sıfır tabanlı dizin, Şerit panel içerir.

### <a name="remarks"></a>Açıklamalar

Kitaplık Daralt sırasını tanımlar. Ancak, Kategori Daralt sırayı belirten dizinleri listesiyle sağlayarak bu davranışı özelleştirebilirsiniz.

Kategori bir Şerit paneli Daralt sahip olduğunu algıladığında, sonraki öğeyi belirtilen listede arar. Liste boş olduğu ya da yeterli sayıda öğe belirtilmemiş kategori iç algoritması kullanır.

Örneğin, kategori, üç Şerit paneli sahiptir ve tüm panellerini tam olarak daraltılmış durumda oluncaya kadar birkaç kez daraltılabilirler. Aşağıdaki Daralt sırasını ayarlayabilirsiniz: 0, 0, 2, 2. Bu durumda, iki kez kategori panelini 0 daraltır, panel 2 iki kez. Dizini 1 olan paneli uncollapsed kalır.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `SetCollapseOrder` yönteminde `CMFCRibbonCategory` sınıfı. Örnek, Şerit kategorisine Daralt sırasını ayarlama ve Daralt sırası için bir dizi oluşturmak nasıl gösterir.

[!code-cpp[NVC_MFC_RibbonApp#13](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_2.cpp)]

##  <a name="setdata"></a>  CMFCRibbonCategory::SetData

Şerit kategorisi ile ilişkilendirilecek kullanıcı tanımlı veri ayarlar.

```
void SetData(DWORD_PTR dwData);
```

### <a name="parameters"></a>Parametreler

*dwData*<br/>
[in] Kullanıcı tanımlı veri.

##  <a name="setkeys"></a>  CMFCRibbonCategory::SetKeys

Bir keytip Şerit kategorisine atar.

```
void SetKeys(LPCTSTR lpszKeys);
```

### <a name="parameters"></a>Parametreler

*lpszKeys*<br/>
[in] Tuş ipucunu metin.

### <a name="remarks"></a>Açıklamalar

Kullanıcı Alt tuşunu veya F10 tuşuna bastığında Keytips görüntülenir.

##  <a name="setname"></a>  CMFCRibbonCategory::SetName

Bir ad ve tuş ipucunu Şerit kategorisine atar.

```
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
[in] Tuş ipucunu Şerit kategorisi ve adı.

### <a name="remarks"></a>Açıklamalar

Şerit kategorisi için tuş ipucunu belirlemek için tuş ipucunu karakterle arkasından bir yeni satır kaçış dizisini ekleme *lpszName*.

##  <a name="settabcolor"></a>  CMFCRibbonCategory::SetTabColor

Şerit kategorisi rengini ayarlar.

```
void SetTabColor(AFX_RibbonCategoryColor color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
[in] Şerit kategorisi yeni rengini belirtir.

### <a name="remarks"></a>Açıklamalar

Renk aşağıdaki değerlerden biri olabilir:

- AFX_CategoryColor_None

- AFX_CategoryColor_Red

- AFX_CategoryColor_Orange

- AFX_CategoryColor_Yellow

- AFX_CategoryColor_Green

- AFX_CategoryColor_Blue

- AFX_CategoryColor_Indigo

- AFX_CategoryColor_Violet

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)
