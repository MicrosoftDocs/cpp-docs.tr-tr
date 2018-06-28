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
ms.openlocfilehash: 44caf81fd73567e9c206bdfe62869f5fc145fd33
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039114"
---
# <a name="cmfcribboncategory-class"></a>CMFCRibbonCategory sınıfı
`CMFCRibbonCategory` Sınıfı uygulayan bir grubu içeren bir Şerit sekmesi [Şerit paneller](../../mfc/reference/cmfcribbonpanel-class.md).  
  
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
|[CMFCRibbonCategory::AddHidden](#addhidden)|Gizli bir öğesi Şerit kategorisine ekler.|  
|[CMFCRibbonCategory::AddPanel](#addpanel)|Yeni bir panel Şerit kategorisine ekler.|  
|[CMFCRibbonCategory::CopyFrom](#copyfrom)||  
|[CMFCRibbonCategory::FindByData](#findbydata)||  
|[CMFCRibbonCategory::FindByID](#findbyid)||  
|[CMFCRibbonCategory::FindPanelWithElem](#findpanelwithelem)||  
|[CMFCRibbonCategory::GetContextID](#getcontextid)|Şerit kategori bağlam Kimliğini döndürür.|  
|[CMFCRibbonCategory::GetData](#getdata)|Şerit kategoriyle ilişkili kullanıcı tanımlı veri döndürür.|  
|[CMFCRibbonCategory::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonCategory::GetElements](#getelements)||  
|[CMFCRibbonCategory::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonCategory::GetFirstVisibleElement](#getfirstvisibleelement)|Şerit kategorisine ait bir ilk görünür öğesi alın.|  
|[CMFCRibbonCategory::GetFocused](#getfocused)|Odaklanılan öğeyi döndürür.|  
|[CMFCRibbonCategory::GetHighlighted](#gethighlighted)|Vurgulanan öğeyi döndürür.|  
|[CMFCRibbonCategory::GetImageCount](#getimagecount)||  
|[CMFCRibbonCategory::GetImageSize](#getimagesize)||  
|[CMFCRibbonCategory::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonCategory::GetLastVisibleElement](#getlastvisibleelement)|Şerit kategorisine ait bir son görünür öğesi alın|  
|[CMFCRibbonCategory::GetLargeImages](#getlargeimages)|Şerit kategorisini kullanır görüntülerin büyük listesine bir başvuru döndürür.|  
|[CMFCRibbonCategory::GetMaxHeight](#getmaxheight)||  
|[CMFCRibbonCategory::GetName](#getname)||  
|[CMFCRibbonCategory::GetPanel](#getpanel)|Belirtilen dizinde bulunan Şerit paneline bir işaretçi döndürür.|  
|[CMFCRibbonCategory::GetPanelCount](#getpanelcount)|Şerit kategorisinde Şerit paneller sayısını döndürür.|  
|[CMFCRibbonCategory::GetPanelFromPoint](#getpanelfrompoint)||  
|[CMFCRibbonCategory::GetPanelIndex](#getpanelindex)|Belirtilen Şerit paneli dizinini döndürür.|  
|[CMFCRibbonCategory::GetParentButton](#getparentbutton)||  
|[CMFCRibbonCategory::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonCategory::GetParentRibbonBar](#getparentribbonbar)||  
|[CMFCRibbonCategory::GetRect](#getrect)||  
|[CMFCRibbonCategory::GetSmallImages](#getsmallimages)|Kategori kullanan küçük resimlerin listesi bir başvuru döndürür.|  
|[CMFCRibbonCategory::GetTabColor](#gettabcolor)|Şerit kategori sekmesi geçerli rengi döndürür.|  
|[CMFCRibbonCategory::GetTabRect](#gettabrect)||  
|[CMFCRibbonCategory::GetTextTopLine](#gettexttopline)||  
|[CMFCRibbonCategory::GetVisibleElements](#getvisibleelements)|Şerit kategorisine ait tüm görünür öğeleri alın.|  
|[CMFCRibbonCategory::HighlightPanel](#highlightpanel)||  
|[CMFCRibbonCategory::HitTest](#hittest)||  
|[CMFCRibbonCategory::HitTestEx](#hittestex)||  
|[CMFCRibbonCategory::HitTestScrollButtons](#hittestscrollbuttons)||  
|[CMFCRibbonCategory::IsActive](#isactive)||  
|[CMFCRibbonCategory::IsVisible](#isvisible)|Şerit kategori görünür olup olmadığını belirler.|  
|[CMFCRibbonCategory::IsWindows7Look](#iswindows7look)|Üst Şerit Windows 7 stil görünümünü (küçük dikdörtgen uygulama düğmesi) olup olmadığını gösterir|  
|[CMFCRibbonCategory::NotifyControlCommand](#notifycontrolcommand)||  
|[CMFCRibbonCategory::OnCancelMode](#oncancelmode)||  
|[CMFCRibbonCategory::OnDraw](#ondraw)||  
|[CMFCRibbonCategory::OnDrawImage](#ondrawimage)||  
|[CMFCRibbonCategory::OnDrawMenuBorder](#ondrawmenuborder)||  
|[CMFCRibbonCategory::OnKey](#onkey)|Bir kullanıcı bir klavye düğmesine bastığında çerçevesi tarafından çağrılır.|  
|[CMFCRibbonCategory::OnLButtonDown](#onlbuttondown)||  
|[CMFCRibbonCategory::OnLButtonUp](#onlbuttonup)||  
|[CMFCRibbonCategory::OnMouseMove](#onmousemove)||  
|[CMFCRibbonCategory::OnRTLChanged](#onrtlchanged)||  
|[CMFCRibbonCategory::OnScrollHorz](#onscrollhorz)||  
|[CMFCRibbonCategory::OnUpdateCmdUI](#onupdatecmdui)||  
|[CMFCRibbonCategory::RecalcLayout](#recalclayout)||  
|[CMFCRibbonCategory::RemovePanel](#removepanel)||  
|[CMFCRibbonCategory::ReposPanels](#repospanels)||  
|[CMFCRibbonCategory::SetCollapseOrder](#setcollapseorder)|Şerit kategorisinde bulunan Şerit paneller Daralt sırasını tanımlar.|  
|[CMFCRibbonCategory::SetData](#setdata)|Kullanıcı tanımlı veri Şerit kategorisinde depolar.|  
|[CMFCRibbonCategory::SetKeys](#setkeys)|Bir keytip Şerit kategorisine atar.|  
|[CMFCRibbonCategory::SetName](#setname)||  
|[CMFCRibbonCategory::SetTabColor](#settabcolor)|Şerit kategori rengini belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, bir Şerit kategori dolaylı olarak çağırarak oluşturduğunuz [CMFCRibbonBar::AddCategory](../../mfc/reference/cmfcribbonbar-class.md#addcategory), yeni oluşturulan Şerit kategorisine bir işaretçi döndürür. Paneller çağırarak kategoriye eklemek [CMFCRibbonCategory::AddPanel](#addpanel).  
  
 `CMFCRibbonTab` Sınıfı çizer Şerit kategoriler. Öğesinden türetilen [CMFCRibbonBaseElement sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md).  
  
 Aşağıdaki örnek bir Şerit kategorisi oluşturma ve bir panel ekleyin gösterir.  
  
 `// Create a new ribbon category and get a pointer to it`  
  
 `CMFCRibbonCategory* pCategory = m_wndRibbonBar.AddCategory`  
  
 `(_T("&Write"),           // Category name`  
  
 `IDB_WRITE,              // Category small images (16 x 16)`  
  
 `IDB_WRITE_LARGE);   // Category large images (32 x 32)`  
  
 `// Add a panel to the new category`  
  
 `CMFCRibbonPanel* pPanel = pCategory->AddPanel (`  
  
 `_T("Clipboard"),                       // Panel name`  
  
 `m_PanelIcons.ExtractIcon (0));  // Panel icon`  
  
 Aşağıdaki diyagramda bir şekilde RibbonApp örnek uygulamadan giriş kategorinin gösterilmektedir.  
  
 ![CMFCRibbonCategory görüntü](../../mfc/reference/media/cmfcribboncategory.png "cmfcribboncategory")  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCRibbonCategory`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxribboncategory.h  
  
##  <a name="addhidden"></a>  CMFCRibbonCategory::AddHidden  
 Özelleştirme iletişim kutusunda görüntülenen Şerit öğeleri dizisi için belirtilen Şerit öğesi ekler.  
  
```  
void AddHidden(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pElem*  
 Şerit öğesi işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit öğeleri özelleştirme iletişim kutusunda hızlı erişim araç çubuğuna ekleyebileceğiniz komutlardır.  
  
##  <a name="addpanel"></a>  CMFCRibbonCategory::AddPanel  
 Şerit kategori için Şerit paneli oluşturur.  
  
```  
CMFCRibbonPanel* AddPanel(
    LPCTSTR lpszPanelName,  
    HICON hIcon = 0,  
    CRuntimeClass* pRTI = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszPanelName*  
 Yeni Şerit paneli adını işaretçi.  
  
 [in] *hIcon*  
 Yeni Şerit paneli varsayılan simgesi için işleyin.  
  
 [in] *pRTI*  
 Özel Şerit paneli için çalışma zamanı sınıf bilgileri işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa yeni bir Şerit paneli işaretçi; Aksi takdirde `NULL` Masası değil oluşturulduysa.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel Şerit paneli oluşturmak istiyorsanız, kendi çalışma zamanı sınıf bilgileri belirtmelisiniz *pRTI*. Özel Şerit paneli sınıfı öğesinden türetilmelidir `CMFCRibbonPanel` sınıfı.  
  
 Şerit öğeleri görüntülemek için yeterli alan olduğunda Şerit paneli varsayılan simgesi görüntülenir.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `AddPanel` yönteminde `CMFCRibbonCategory` sınıfı.  
  
 [!code-cpp[NVC_MFC_RibbonApp#10](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_1.cpp)]  
  
##  <a name="cmfcribboncategory"></a>  CMFCRibbonCategory::CMFCRibbonCategory  
 Oluşturur ve başlatır bir [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) nesnesi.  
  
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
 [in] *pParenrRibbonBar*  
 Şerit kategorisi üst Şerit çubuğuna işaretçi.  
  
 [in] *lpszName*  
 Şerit kategori adı.  
  
 [in] *uiSmallImagesResID*  
 Şerit kategorisinde Şerit öğeleri tarafından kullanılan küçük resimleri için resim listesi kaynak kimliği.  
  
 [in] *uiLargeImagesResID*  
 Şerit kategorisinde Şerit öğeleri tarafından kullanılan büyük görüntüleri için resim listesi kaynak kimliği.  
  
 [in] *sizeSmallImage*  
 Şerit kategorisinde Şerit öğeleri için küçük resimlerin boyutu varsayılan.  
  
 [in] *sizeLargeImage*  
 Şerit kategorisinde Şerit öğeleri için büyük resimlerin boyutu varsayılan.  
  
##  <a name="copyfrom"></a>  CMFCRibbonCategory::CopyFrom  
 Belirtilen durumunu kopyalar [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) geçerli [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) nesnesi.  
  
```  
virtual void CopyFrom(CMFCRibbonCategory& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *src*  
 Kaynak `CMFCRibbonCategory` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findbydata"></a>  CMFCRibbonCategory::FindByData  
 Belirtilen verilerle ilişkili Şerit öğesi alır.  
  
```  
CMFCRibbonBaseElement* FindByData(
    DWORD_PTR dwData,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwData*  
 Şerit öğesi ile ilişkili veriler.  
  
 [in] *bVisibleOnly*  
 `TRUE` hızlı erişim Şerit öğeleri aramada dahil etmek için; `FALSE` hızlı erişim Şerit öğeleri arama dışlanacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa bir Şerit öğesi işaretçi; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findbyid"></a>  CMFCRibbonCategory::FindByID  
 Belirtilen komut kimlikle ilişkili Şerit öğesi alır.  
  
```  
CMFCRibbonBaseElement* FindByID(
    UINT uiCmdID,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiCmdID*  
 Şerit öğeyle ilişkili komut kimliği.  
  
 [in] *bVisibleOnly*  
 `TRUE` hızlı erişim Şerit öğeleri aramada dahil etmek için; `FALSE` hızlı erişim Şerit öğeleri arama dışlanacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa bir Şerit öğesi işaretçi; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findpanelwithelem"></a>  CMFCRibbonCategory::FindPanelWithElem  
 Belirtilen Şerit öğesi içeren Şerit paneli alır.  
  
```  
CMFCRibbonPanel* FindPanelWithElem(const CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pElement*  
 Şerit öğesi işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa bir Şerit panel işaretçi; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcontextid"></a>  CMFCRibbonCategory::GetContextID  
 Şerit kategori bağlam Kimliğini alır.  
  
```  
UINT GetContextID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit kategori bağlam kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit kategori bağlam Şerit kategori değilse içerik kimliği 0'dır.  
  
##  <a name="getdata"></a>  CMFCRibbonCategory::GetData  
 Şerit kategoriyle ilişkili kullanıcı tanımlı veri alır.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit kategoriyle ilişkili kullanıcı tanımlı bir veri.  
  
##  <a name="getdroppeddown"></a>  CMFCRibbonCategory::GetDroppedDown  
 Şu anda açılır menüsü görüntülenen sahip Şerit öğesi için bir işaretçi alır.  
  
```  
CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa bir Şerit öğesi işaretçi; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getelements"></a>  CMFCRibbonCategory::GetElements  
 Şerit kategorideki tüm Şerit öğeleri alır.  
  
```  
void GetElements(
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parametreler  
 [içinde out] *arElements*  
 Başvuru bir [CArray](../../mfc/reference/carray-class.md) Şerit öğelerinin.  
  
### <a name="remarks"></a>Açıklamalar  
 Hızlı Erişim Araç çubuğu üzerinde kullanılmak üzere tasarlanmış Şerit öğeleri dizideki dahil edilir.  
  
##  <a name="getelementsbyid"></a>  CMFCRibbonCategory::GetElementsByID  
 Belirtilen komut kimliği ile ilişkili tüm Şerit öğeleri alır.  
  
```  
void GetElementsByID(
    UINT uiCmdID,  
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiCmdID*  
 Şerit öğeyle ilişkili komut kimliği.  
  
 [içinde out] *arElements*  
 Başvuru bir [CArray](../../mfc/reference/carray-class.md) Şerit öğelerinin.  
  
### <a name="remarks"></a>Açıklamalar  
 Hızlı Erişim Araç çubuğu üzerinde kullanılmak üzere tasarlanmış Şerit öğeleri dizideki dahil edilir.  
  
##  <a name="getfirstvisibleelement"></a>  CMFCRibbonCategory::GetFirstVisibleElement  
 Şerit kategorisine ait ilk görünür öğesi alır.  
  
```  
CMFCRibbonBaseElement* GetFirstVisibleElement() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi ilk görünür öğesine; olabilir `NULL` kategori görünür tüm öğeleri yoksa.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getfocused"></a>  CMFCRibbonCategory::GetFocused  
 Odaklanılan öğeyi döndürür.  
  
```  
CMFCRibbonBaseElement* GetFocused();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Odaklanmış bir öğe için bir işaretçi veya `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gethighlighted"></a>  CMFCRibbonCategory::GetHighlighted  
 Vurgulanan öğeyi döndürür.  
  
```  
CMFCRibbonBaseElement* GetHighlighted();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Vurgulanan öğe için bir işaretçi veya `NULL` öğe vurgulanmıştır durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getimagecount"></a>  CMFCRibbonCategory::GetImageCount  
 Şerit kategoride bulunan belirtilen görüntü listesinde görüntü sayısını alır.  
  
```  
int GetImageCount(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bIsLargeImage*  
 `TRUE` büyük resim listesi görüntüleri sayısı için; `FALSE` küçük resim listesi görüntülerinde sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen görüntü listesinde görüntüleri sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getimagesize"></a>  CMFCRibbonCategory::GetImageSize  
 Belirtilen görüntü listesinde Şerit kategoride yer alan bir görüntü boyutunu alır.  
  
```  
CSize GetImageSize(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bIsLargeImage*  
 `TRUE` büyük resimlerin boyutu için; `FALSE` küçük resimlerin boyutu için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen görüntü listesinde bir resim boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Alınan boyutu genel görüntü ölçek faktörü içerir.  
  
##  <a name="getitemidslist"></a>  CMFCRibbonCategory::GetItemIDsList  
 Komut kimlikleri için Şerit kategoride yer alan Şerit öğeleri alır.  
  
```  
void GetItemIDsList(
    CList<UINT, UINT>& lstItems,  
    BOOL bHiddenOnly = FALSE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *lstItems*  
 Komut kimlikleri için Şerit kategori Şerit öğeleri listesi.  
  
 [in] *bHiddenOnly*  
 `TRUE` Şerit kategorisinde Şerit paneller görüntülenen Şerit öğeleri dışlamak için; `FALSE` Şerit kategorisinde bulunan tüm Şerit öğeleri dahil etmek için.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getlargeimages"></a>  CMFCRibbonCategory::GetLargeImages  
 Şerit kategoride bulunan büyük görüntüleri listesini alır.  
  
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
 İşaretçi son görünür öğesine; olabilir `NULL` kategori görünür tüm öğeleri yoksa.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getmaxheight"></a>  CMFCRibbonCategory::GetMaxHeight  
 Şerit kategoride yer alan Şerit paneller maksimum yüksekliğini alır.  
  
```  
int GetMaxHeight(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Şerit paneller için cihaz bağlamı işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit kategoride yer alan Şerit paneller en fazla yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit paneller için üst ve alt kenar boşlukları yüksekliğini alınan değeri içerir.  
  
##  <a name="getname"></a>  CMFCRibbonCategory::GetName  
 Şerit kategorisinin adını alır.  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit kategori adı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanel"></a>  CMFCRibbonCategory::GetPanel  
 Belirtilen dizinde bulunan Şerit paneline bir işaretçi döndürür.  
  
```  
CMFCRibbonPanel* GetPanel(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Şerit paneli sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dizinde bulunan Şerit paneli işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özel durum *nIndex* aralık dışında.  
  
##  <a name="getpanelcount"></a>  CMFCRibbonCategory::GetPanelCount  
 Şerit kategorisinde Şerit paneller sayısını döndürür.  
  
```  
int GetPanelCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit paneller Şerit kategorisinde sayısı.  
  
##  <a name="getpanelfrompoint"></a>  CMFCRibbonCategory::GetPanelFromPoint  
 Belirtilen nokta içinde yer alıyorsa bir Şerit panel gösteren bir işaretçi alır.  
  
```  
CMFCRibbonPanel* GetPanelFromPoint(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 X ve y koordinatları işaretçinin penceresinin sol üst köşesindeki göre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa bir Şerit panel işaretçi; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit kategorisinde bulunan Şerit paneller sınanır.  
  
##  <a name="getpanelindex"></a>  CMFCRibbonCategory::GetPanelIndex  
 Belirtilen Şerit paneli sıfır tabanlı dizinini alır.  
  
```  
int GetPanelIndex(const CMFCRibbonPanel* pPanel) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pPanel*  
 Şerit paneli işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa belirtilen Şerit paneli sıfır tabanlı dizini; Aksi takdirde-1.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit kategorisinde bulunan Şerit paneller aranır.  
  
##  <a name="getparentbutton"></a>  CMFCRibbonCategory::GetParentButton  
 Şerit kategorisi üst Şerit öğesi alır.  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üst Şerit öğesi için bir işaretçi döndürür veya `NULL` herhangi bir üst öğe yoksa.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getparentmenubar"></a>  CMFCRibbonCategory::GetParentMenuBar  
 Ana menü çubuğu için bir işaretçi döndüren `CMFCRibbonCategory` nesnesi.  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçeriğini döndürür `m_pParentMenuBar` üye korumalı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getparentribbonbar"></a>  CMFCRibbonCategory::GetParentRibbonBar  
 Şerit kategori için üst Şerit çubuğu alır.  
  
```  
CMFCRibbonBar* GetParentRibbonBar() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi Şerit kategori için üst Şerit çubuğu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrect"></a>  CMFCRibbonCategory::GetRect  
 Şerit kategori için Görüntü dikdörtgen alır.  
  
```  
CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit kategori için Görüntü dikdörtgen.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit kategori için Görüntü dikdörtgen kategori sekmesini içermez.  
  
##  <a name="getsmallimages"></a>  CMFCRibbonCategory::GetSmallImages  
 Şerit kategorisinde bulunan küçük resimler listesini alır.  
  
```  
CMFCToolBarImages& GetSmallImages();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit kategorisinde bulunan küçük resimler listesi.  
  
##  <a name="gettabcolor"></a>  CMFCRibbonCategory::GetTabColor  
 Şerit kategori sekmesi geçerli rengi döndürür.  
  
```  
AFX_RibbonCategoryColor GetTabColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit kategori sekmesi geçerli rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen değer aşağıdaki numaralandırılmış değerlerden biri olabilir:  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
##  <a name="gettabrect"></a>  CMFCRibbonCategory::GetTabRect  
 Şerit kategori sekmesi için Görüntü dikdörtgen alır.  
  
```  
CRect GetTabRect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit kategori sekmesi için Görüntü dikdörtgen.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettexttopline"></a>  CMFCRibbonCategory::GetTextTopLine  
 Büyük resimleri görüntüleme Şerit düğmeleri Şerit kategorisinde metnin dikey konumu alır.  
  
```  
int GetTextTopLine() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Piksel cinsinden büyük resimleri görüntüleme Şerit düğmeleri metnin dikey konumu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getvisibleelements"></a>  CMFCRibbonCategory::GetVisibleElements  
 Şerit kategorisine ait tüm görünür öğeleri alır.  
  
```  
void GetVisibleElements(
    CArray <CMFCRibbonBaseElement*,  
    CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parametreler  
 *arElements*  
 Tüm görünür öğeleri dizisi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="highlightpanel"></a>  CMFCRibbonCategory::HighlightPanel  
 Belirtilen Şerit paneli vurgular.  
  
```  
CMFCRibbonPanel* HighlightPanel(
    CMFCRibbonPanel* pHLPanel,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pHLPanel*  
 İşaretçi vurgulamak için Şerit paneline.  
  
 [in] *noktası*  
 X ve y koordinatları işaretçinin penceresinin sol üst köşesindeki göre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi önceden vurgulanan Şerit paneline; Aksi takdirde `NULL` varsa bu yöntem çağrıldığında hiçbir Şerit paneli vurgulanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit paneli vurgulama hakkında daha fazla bilgi için bkz: [CMFCRibbonPanel::Highlight](../../mfc/reference/cmfcribbonpanel-class.md#highlight).  
  
##  <a name="hittest"></a>  CMFCRibbonCategory::HitTest  
 Belirtilen nokta içinde yer alıyorsa Şerit öğesi için bir işaretçi alır.  
  
```  
CMFCRibbonBaseElement* HitTest(
    CPoint point,  
    BOOL bCheckPanelCaption = FALSE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 X ve y koordinatları penceresinin sol üst köşesindeki göreli fare işaretçisi.  
  
 [in] *bCheckPanelCaption*  
 `TRUE` Şerit Panosu resim yazısı test etmek için; `FALSE` şeridi Bölmesi Başlığı dışlanacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa bir Şerit öğesi işaretçi; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit kategorisinde bulunan Şerit öğeleri sınanır.  
  
##  <a name="hittestex"></a>  CMFCRibbonCategory::HitTestEx  
 Belirtilen nokta içinde yer alıyorsa Şerit öğenin sıfır tabanlı dizinini alır.  
  
```  
int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 X ve y koordinatları penceresinin sol üst köşesindeki göreli fare işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa bir Şerit öğenin sıfır tabanlı dizini; Aksi takdirde-1.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit kategorisinde bulunan Şerit öğeleri sınanır.  
  
##  <a name="hittestscrollbuttons"></a>  CMFCRibbonCategory::HitTestScrollButtons  
 Bir işaretçi bir noktası içinde bir Şerit kategorinin sola veya sağa kaydırma düğmesini kalırsa, bu düğme döndürür.  
  
```  
CMFCRibbonBaseElement* HitTestScrollButtons(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 Test noktası.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa *noktası* ya da sola sınırlayıcı dikdörtgenini veya sağa kaydırma düğmesi Şerit kategorisi içinde kalan, bu düğme için bir işaretçi döndürür veya aksi halde, döndürür `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isactive"></a>  CMFCRibbonCategory::IsActive  
 Şerit kategori Şerit çubuğundaki etkin kategori olup olmadığını gösterir.  
  
```  
BOOL IsActive() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Şerit kategori etkin kategori ise; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkin Şerit kategorisi Şerit panellerini görüntüler.  
  
##  <a name="isvisible"></a>  CMFCRibbonCategory::IsVisible  
 Şerit kategori görünür olup olmadığını gösterir.  
  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Şerit kategori görünür durumdaysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Görünür Şerit kategoriler kategori sekmesini görüntüleyin.  
  
##  <a name="iswindows7look"></a>  CMFCRibbonCategory::IsWindows7Look  
 Üst Şerit Windows 7'yi (küçük dikdörtgen uygulama düğmesi) Ara olup olmadığını gösterir.  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Windows 7'yi arayın üst Şerit varsa, Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="notifycontrolcommand"></a>  CMFCRibbonCategory::NotifyControlCommand  
 Wm_notıfy komutu iletiyi tümüne teslim `CMFCRibbonPanel` öğelerinde `CMFCRibbonCategory` iletinin işlenmiş kadar.  
  
```  
virtual BOOL NotifyControlCommand(
    BOOL bAccelerator,  
    int nNotifyCode,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bAccelerator*  
 `TRUE` Bu komut bir Hızlandırıcı geldiyse veya `FALSE` Aksi takdirde.  
  
 [in] *nNotifyCode*  
 Bildirim kodu.  
  
 [in] *wParam*  
 WPARAM alanı iletisi.  
  
 [in] *lParam*  
 LPARAM alanı iletisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` ileti işleniyorsa veya `FALSE` değilse.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="oncancelmode"></a>  CMFCRibbonCategory::OnCancelMode  
 Tüm iptal modunda çağırır `CMFCRibbonPanel` öğeleri `CMFCRibbonCategory`.  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondraw"></a>  CMFCRibbonCategory::OnDraw  
 Şerit kategori çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Şerit kategorisi için cihaz bağlamı işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawimage"></a>  CMFCRibbonCategory::OnDrawImage  
 Belirtilen görüntü Şerit kategorisine göre çizmek için çerçevesi tarafından çağrılır.  
  
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
 [in] *pDC*  
 Görüntüsü için bir cihaz bağlamı işaretçi.  
  
 [in] *rect*  
 Resmi için dikdörtgen görüntüler.  
  
 [in] *pElement*  
 Resmi içeren Şerit öğesi işaretçisi.  
  
 [in] *bIsLargeImage*  
 `TRUE` görüntü boyutu büyük olduğunda; `FALSE` görüntünün küçük boyutu ise.  
  
 [in] *nImageIndex*  
 Şerit kategoride yer alan görüntü dizi görüntüde sıfır tabanlı dizini.  
  
 [in] *bCenter*  
 `TRUE` Görüntü dikdörtgen görüntüde merkezine; `FALSE` resim görüntüleme dikdörtgenini sol üst köşesindeki çizmek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawmenuborder"></a>  CMFCRibbonCategory::OnDrawMenuBorder  
 Açılan menü kenarlık çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawMenuBorder(
    CDC* pDC,  
    CMFCRibbonPanelMenuBar* pMenuBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bu parametre kullanılmaz.  
  
 [in] *pMenuBar*  
 Bu parametre kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak bu yöntem hiçbir şey yapmaz. Açılan menü kenarlık çizmek için bu yöntemi geçersiz kılın.  
  
##  <a name="onkey"></a>  CMFCRibbonCategory::OnKey  
 Bir kullanıcı bir klavye düğmesine bastığında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Parametreler  
 *NChar*  
 Bir kullanıcı basılı anahtarı sanal anahtar kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onlbuttondown"></a>  CMFCRibbonCategory::OnLButtonDown  
 Belirtilen nokta altında Şerit öğesi kullanıcı sol fare düğmesini bastığında almak için çerçevesi tarafından çağrılır.  
  
```  
virtual CMFCRibbonBaseElement* OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 X ve y koordinatları penceresinin sol üst köşesindeki göreli fare işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa bir Şerit öğesi işaretçi; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onlbuttonup"></a>  CMFCRibbonCategory::OnLButtonUp  
 Kullanıcı sol fare düğmesini serbest bırakır ve işaretçiyi Şerit kategori çerçevesi tarafından çağrılır.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 X ve y koordinatları işaretçinin penceresinin sol üst köşesindeki göre.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onmousemove"></a>  CMFCRibbonCategory::OnMouseMove  
 İşaretçi Şerit kategori görüntüsünü güncelleştirmek için Şerit çubuğunda geldiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnMouseMove(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 X ve y koordinatları işaretçinin penceresinin sol üst köşesindeki göre.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onrtlchanged"></a>  CMFCRibbonCategory::OnRTLChanged  
 Düzen yönü değiştiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bIsRTL*  
 `TRUE` Düzen sağdan sola ise; `FALSE` düzeni soldan sağa ise.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tüm Şerit paneller ve Şerit kategoride yer alan Şerit öğeleri düzenini ayarlar.  
  
##  <a name="onscrollhorz"></a>  CMFCRibbonCategory::OnScrollHorz  
 Yatay yönde Şerit kategori kayar.  
  
```  
virtual BOOL OnScrollHorz(
    BOOL bScrollLeft,  
    int nScrollOffset = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bScrollLeft*  
 `TRUE` sola kaydırma için; `FALSE` sağa doğru kaydırma için.  
  
 [in] *nScrollOffset*  
 Piksel cinsinden kaydırma uzaklığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Şerit kategori yatay yönde taşınsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onupdatecmdui"></a>  CMFCRibbonCategory::OnUpdateCmdUI  
 Çağrıları `OnUpdateCmdUI` her üye işlevi `CMFCRibbonPanel` öğeleri `CMFCRibbonCategory` etkinleştirme veya devre dışı bir kullanıcı arabirimi öğeleri.  
  
```  
virtual void OnUpdateCmdUI(
    CMFCRibbonCmdUI* pCmdUI,  
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pCmdUI*  
 İşaretçi `CMFCRibbonCmdUI` nesne olan kullanıcı arabirimi öğeleri etkinleştirilmesi ve devre dışı olduğunu belirler.  
  
 [in] *pTarget*  
 İşaretçi etkinleştirme veya devre dışı kullanıcı arabirimi öğelerini denetimleri penceresine.  
  
 [in] *bDisableIfNoHndler*  
 `TRUE` kullanıcı arabirimi öğesi hiçbir işleyici varsa devre dışı bırakmak için ileti eşlemesi içinde tanımlanan; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="recalclayout"></a>  CMFCRibbonCategory::RecalcLayout  
 Şerit kategorisine tüm denetimlerin düzenini ayarlar.  
  
```  
virtual void RecalcLayout(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Şerit kategorisi için cihaz bağlamı işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removepanel"></a>  CMFCRibbonCategory::RemovePanel  
 Şerit Masası Şerit kategoriden kaldırır.  
  
```cpp  
BOOL RemovePanel(
    int nIndex,  
    BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Kaldırmak için Denetim Masası dizin sayısı. Çağırılarak alınır [CMFCRibbonCategory::GetPanelIndex](#getpanelindex) yöntemi.  
  
 [in] *bSil*  
 `TRUE` panel nesnesi bellekten silmek için; `FALSE` silmeden panel nesnesi kaldırmak için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
##  <a name="repospanels"></a>  CMFCRibbonCategory::ReposPanels  
 Şerit kategoride yer alan Şerit paneller tüm denetimlerin düzenini ayarlar.  
  
```  
virtual void ReposPanels(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Şerit kategoride yer alan Şerit paneller için cihaz bağlamı işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setcollapseorder"></a>  CMFCRibbonCategory::SetCollapseOrder  
 İçinde Şerit kategorisinin Şerit paneller Daralt sırasını tanımlar.  
  
```  
void SetCollapseOrder(const CArray<int,int>& arCollapseOrder);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *arCollapseOrder*  
 Daraltma sırasını belirtir. Dizi Şerit paneller sıfır tabanlı dizinlerini içeriyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Kitaplık Daralt sırasını tanımlar. Bununla birlikte, Daralt sırası belirten dizinleri listesiyle kategori sağlayarak bu davranışı özelleştirebilirsiniz.  
  
 Kategori Şerit paneli daraltmak olduğunu algıladığında, belirtilen liste sonraki öğe arar. Liste boş olduğu veya yeterli sayıda öğe belirtmediniz, kategori iç algoritmasını kullanır.  
  
 Örneğin, kategori üç Şerit paneller sahiptir ve tüm panelleri tam olarak daraltılmış durumda kadar birkaç kez daraltılabilen. Aşağıdaki Daralt sırasını ayarlayabilirsiniz: 0, 0, 2, 2. Bu durumda, kategori 0 paneli iki kez daraltır, Panosu 2 iki kez. 1 dizininin paneli uncollapsed kalır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `SetCollapseOrder` yönteminde `CMFCRibbonCategory` sınıfı. Örnek Daralt sipariş için bir dizi oluşturma ve Şerit kategorisine Daralt sırayı ayarlamak nasıl gösterir.  
  
 [!code-cpp[NVC_MFC_RibbonApp#13](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_2.cpp)]  
  
##  <a name="setdata"></a>  CMFCRibbonCategory::SetData  
 Şerit kategoriyle ilişkili olduğu kullanıcı tanımlı veri ayarlar.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwData*  
 Kullanıcı tanımlı veri.  
  
##  <a name="setkeys"></a>  CMFCRibbonCategory::SetKeys  
 Bir keytip Şerit kategorisine atar.  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszKeys*  
 Keytip metin.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı Alt veya F10 tuşuna bastığında tuş ipuçlarını görüntülenir.  
  
##  <a name="setname"></a>  CMFCRibbonCategory::SetName  
 Bir ad ve keytip Şerit kategorisine atar.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszName*  
 Ad ve keytip Şerit kategorisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit kategori keytip ayarlamak için keytip karakter arkasından bir satır başı karakteri kaçış sırası append *lpszName*.  
  
##  <a name="settabcolor"></a>  CMFCRibbonCategory::SetTabColor  
 Şerit kategori rengini belirler.  
  
```  
void SetTabColor(AFX_RibbonCategoryColor color);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rengi*  
 Şerit kategori yeni rengini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk aşağıdaki değerlerden biri olabilir:  
  
-   AFX_CategoryColor_None  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CObject Sınıfı](../../mfc/reference/cobject-class.md)
