---
title: "CContextMenuManager sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::AddMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuById
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuByName
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuNames
- AFXCONTEXTMENUMANAGER/CContextMenuManager::LoadState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ResetState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SaveState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SetDontCloseActiveMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ShowPopupMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::TrackPopupMenu
dev_langs: C++
helpviewer_keywords:
- CContextMenuManager [MFC], CContextMenuManager
- CContextMenuManager [MFC], AddMenu
- CContextMenuManager [MFC], GetMenuById
- CContextMenuManager [MFC], GetMenuByName
- CContextMenuManager [MFC], GetMenuNames
- CContextMenuManager [MFC], LoadState
- CContextMenuManager [MFC], ResetState
- CContextMenuManager [MFC], SaveState
- CContextMenuManager [MFC], SetDontCloseActiveMenu
- CContextMenuManager [MFC], ShowPopupMenu
- CContextMenuManager [MFC], TrackPopupMenu
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ceed1a7127d86ced1c68d92269a6b1a55f41991f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager sınıfı
`CContextMenuManager` Nesnesi olarak da bilinen bağlam menülerini kısayol menüleri yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CContextMenuManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|Oluşturan bir `CContextMenuManager` nesnesi.|  
|`CContextMenuManager::~CContextMenuManager`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CContextMenuManager::AddMenu](#addmenu)|Yeni bir kısayol menü ekler.|  
|[CContextMenuManager::GetMenuById](#getmenubyid)|Sağlanan kaynak kimliği ile ilişkili menüsüne bir işleyici döner|  
|[CContextMenuManager::GetMenuByName](#getmenubyname)|Bir tanıtıcı sağlanan menü adıyla eşleşen menüsüne döndürür.|  
|[CContextMenuManager::GetMenuNames](#getmenunames)|Menü adları listesini döndürür.|  
|[CContextMenuManager::LoadState](#loadstate)|Kısayol menüleri Windows kayıt defterinde depolanan yükler.|  
|[CContextMenuManager::ResetState](#resetstate)|Kısayol menüleri bağlam menüsü Yöneticisi'nden temizler.|  
|[CContextMenuManager::SaveState](#savestate)|Kısayol menüleri Windows kayıt defterine kaydeder.|  
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|Denetimleri olup olmadığını `CContextMenuManager` yeni bir kısayol menü göstermediğinde etkin kısayol menüsünü kapatır.|  
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|Belirtilen kısayol menüsünü görüntüler.|  
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|Belirtilen kısayol menüsünü görüntüler. Seçili menü komutu dizinini döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CContextMenuManager`kısayol menüleri yönetir ve tutarlı bir görünüm sahip olmanızı sağlar.  
  
 Değil oluşturmalısınız bir `CContextMenuManager` el ile nesne. Uygulamanızı çerçevesini oluşturur `CContextMenuManager` nesnesi. Ancak, çağırmalıdır [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) uygulamanızı ne zaman başlatılır. Bağlam Yöneticisi başlatma sonrasında yöntemi kullanın [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) uygulamanız için İçerik Yöneticisi bir işaretçi elde edilir.  
  
 Kısayol menüleri çalışma zamanında çağırarak oluşturabileceğiniz `AddMenu`. İlk alıcı kullanıcı girişi olmadan menüsünü göster istiyorsanız, çağrı `ShowPopupMenu`. `TrackPopupMenu`bir menüsü oluşturabilir ve kullanıcı girişi için bekleyin istediğinizde kullanılır. `TrackPopupMenu`Kullanıcı hiçbir şey seçmeden çıkıldı seçili komutu ya da 0 dizinini döndürür.  
  
 `CContextMenuManager` Kaydedebilir ve durumuna Windows kayıt defterini geri yükleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir menüye eklemek gösterilmiştir bir `CContextMenuManager` nesne ve etkin açılır menü değil nasıl kapatılacağını zaman `CContextMenuManager` nesne yeni bir açılır menü görüntüler. Bu kod parçacığını parçası olan [özel sayfaları örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CContextMenuManager`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcontextmenumanager.h  
  
##  <a name="addmenu"></a>CContextMenuManager::AddMenu  
 Yeni bir kısayol menüsü ekler [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
BOOL AddMenu(
    UINT uiMenuNameResId,  
    UINT uiMenuResId);

 
BOOL AddMenu(
    LPCTSTR lpszName,  
    UINT uiMenuResId);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiMenuNameResId`  
 Yeni menü adını içeren bir dize için bir kaynak kimliği.  
  
 [in]`uiMenuResId`  
 Menü kaynak kimliği  
  
 [in]`lpszName`  
 Yeni menü adını içeren dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır olmayan; yöntem başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem başarısız olursa `uiMenuResId` geçersiz veya aynı ada sahip başka bir menü zaten kullanılmadığını `CContextMenuManager`.  
  
##  <a name="ccontextmenumanager"></a>CContextMenuManager::CContextMenuManager  
 Oluşturan bir [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) nesnesi.  
  
```  
CContextMenuManager();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çoğu durumda, değil oluşturmalısınız bir `CContextMenuManager` el ile. Uygulamanızı çerçevesini oluşturur `CContextMenuManager` nesnesi. Çağırmalısınız [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) , uygulamanızın başlatma sırasında. İçerik Yöneticisi bir işaretçi almak için arama [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager).  
  
##  <a name="getmenubyid"></a>CContextMenuManager::GetMenuById  
 Belirtilen kaynak kimliği ile ilişkili menüsüne bir işleyici döner  
  
```  
HMENU GetMenuById(UINT nMenuResId) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nMenuResId`  
 Menü kaynak kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlişkili menü için bir tanıtıcı veya `NULL` menü bulunmazsa.  
  
##  <a name="getmenubyname"></a>CContextMenuManager::GetMenuByName  
 Belirli bir menüsüne bir işleyici döner.  
  
```  
HMENU GetMenuByName(
    LPCTSTR lpszName,  
    UINT* puiOrigResID = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszName`  
 Almak üzere menü adını içeren dize.  
  
 [out]`puiOrigResID`  
 Bir işaretçi bir `UINT`. Bu parametre, belirtilen menü kaynak Kimliğini içerir bulundu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir tanıtıcı tarafından belirtilen adla eşleşen menüsüne `lpszName`. `NULL`adlı hiçbir menüsü olup olmadığını `lpszName`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem eşleşen bir menü bulursa `lpszName`, `GetMenuByName` parametresinde menüsü kaynak kimliği depolar `puiOrigResID`.  
  
##  <a name="getmenunames"></a>CContextMenuManager::GetMenuNames  
 Eklenen menü adları listesini döndürür [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
void GetMenuNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`listOfNames`  
 Bir başvuru bir [CStringList](../../mfc/reference/cstringlist-class.md) parametresi. Bu yöntem, bu parametre için menü adları listesi yazar.  
  
##  <a name="loadstate"></a>CContextMenuManager::LoadState  
 İle ilişkili bilgileri yükler [CContextMenuManager sınıfı](../../mfc/reference/ccontextmenumanager-class.md) Windows kayıt defterinden.  
  
```  
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszProfileName`  
 Bir kayıt defteri anahtarı göreli yolunu içeren bir dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `lpszProfileName` Parametresi bir kayıt defteri girdisi mutlak yolu değil. Uygulamanız için varsayılan kayıt defteri anahtarı sonuna eklenen göreli bir yol değil. Almak veya varsayılan kayıt defteri anahtarını ayarlamak için yöntemleri kullanın [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) ve [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) sırasıyla.  
  
 Yöntem kullanmak [CContextMenuManager::SaveState](#savestate) kısayol menülerini kayıt defterine kaydetmek için.  
  
##  <a name="resetstate"></a>CContextMenuManager::ResetState  
 Kısayol menüleri ile ilişkili tüm öğeleri temizler [CContextMenuManager sınıfı](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
virtual BOOL ResetState();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yöntem başarılı olursa; `FALSE` bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem açılır menüler temizler ve bunları kaldırır `CContextMenuManager`.  
  
##  <a name="savestate"></a>CContextMenuManager::SaveState  
 İle ilişkili bilgileri kaydeder [CContextMenuManager sınıfı](../../mfc/reference/ccontextmenumanager-class.md) Windows kayıt.  
  
```  
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszProfileName`  
 Bir kayıt defteri anahtarı göreli yolunu içeren bir dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `lpszProfileName` Parametresi bir kayıt defteri girdisi mutlak yolu değil. Uygulamanız için varsayılan kayıt defteri anahtarı sonuna eklenen göreli bir yol değil. Almak veya varsayılan kayıt defteri anahtarını ayarlamak için yöntemleri kullanın [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) ve [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) sırasıyla.  
  
 Yöntem kullanmak [CContextMenuManager::LoadState](#loadstate) kayıt defterinden kısayol menülerini yüklenemiyor.  
  
##  <a name="setdontcloseactivemenu"></a>CContextMenuManager::SetDontCloseActiveMenu  
 Denetimleri olup olmadığını [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) yeni bir açılır menü görüntülediğinde etkin açılır menü kapatır.  
  
```  
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bSet`  
 Etkin açılır menü kapatmak sorulmayacağını denetler Boole parametresi. Değerini `TRUE` etkin açılır menü kapalı gösterir. `FALSE`Etkin açılır menü kapalı olduğunu gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `CContextMenuManager` etkin açılır menü kapatır.  
  
##  <a name="showpopupmenu"></a>CContextMenuManager::ShowPopupMenu  
 Belirtilen kısayol menüsünü görüntüler.  
  
```  
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bOwnMessage = FALSE,  
    BOOL bRightAlign = FALSE);

 
virtual CMFCPopupMenu* ShowPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bOwnMessage = FALSE,  
    BOOL bAutoDestroy = TRUE,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiMenuResId`  
 Bu yöntem görüntüler menüsü kaynak kimliği.  
  
 [in]`x`  
 İstemci koordinatları kısayol menüsünde için uzaklık yatay.  
  
 [in]`y`  
 İstemci koordinatları kısayol menüsünde için dikey uzaklık  
  
 [in]`pWndOwner`  
 Kısayol menüsünün üst pencere için bir işaretçi.  
  
 [in]`bOwnMessage`  
 İletilerin nasıl yönlendirileceğini gösterir Boole parametresi. Varsa `bOwnMessage` olan `FALSE`, standart MFC yönlendirme kullanılır. Aksi takdirde `pWndOwner` iletilerini alır.  
  
 [in]`hmenuPopup`  
 Bu yöntem görüntüler menü işleci.  
  
 [in]`bAutoDestroy`  
 Menü otomatik olarak yok olup olmadığını gösteren bir Boolean parametresiyle.  
  
 [in]`bRightAlign`  
 Menü öğeleri nasıl hizalandığını belirten bir Boolean parametresiyle. Varsa `bRightAlign` olan `TRUE`, sağa hizalı sağdan sola okuma sırası için menü kalır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk yöntemi aşırı yüklemesini yöntemi menü başarıyla gösteriyorsa sıfır olmayan döndürür; Aksi takdirde 0. İkinci yöntemi aşırı yüklemesini gösteren bir işaretçi döndürür [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) kısayol menüsünü görüntüler varsa doğru; tersi durumda `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yöntemi benzer [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) içeren bir kısayol menüsünü yöntemlerin her ikisi de görüntüler. Ancak, `TrackPopupMenu` seçili menü komutu dizinini döndürür.  
  
 Varsa parametresi `bAutoDestroy` olan `FALSE`, el ile devralınan çağırmalısınız `DestroyMenu` bellek kaynakları serbest bırakmak için yöntemi. Varsayılan uygulaması `ShowPopupMenu` parametresi kullanmaz `bAutoDestroy`. Gelecekte kullanım için veya türetilmiş özel sınıflar için sağlanan `CContextMenuManager` sınıfı.  
  
##  <a name="trackpopupmenu"></a>CContextMenuManager::TrackPopupMenu  
 Belirtilen kısayol menüsünü görüntüler ve seçili kısayol menü komutu dizinini döndürür.  
  
```  
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`hmenuPopup`  
 Bu yöntem görüntüler kısayol menüsü işleyicisi.  
  
 [in]`x`  
 İstemci koordinatları kısayol menüsünde için uzaklık yatay.  
  
 [in]`y`  
 İstemci koordinatları kısayol menüsünde için uzaklık dikey.  
  
 [in]`pWndOwner`  
 Kısayol menüsünün üst pencere için bir işaretçi.  
  
 [in]`bRightAlign`  
 Menü öğeleri nasıl hizalandığını belirten bir Boolean parametresiyle. Varsa `bRightAlign` olan `TRUE`, sağa hizalı sağdan sola okuma sırası için menü kalır. Varsa `bRightAlign` olan `FALSE`, sola hizalı soldan sağa okuma sırası için menü kalır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcının seçtiği komut menü komut kimliği; Kullanıcı kısayol menüsünü menü komutu seçmeden kapatırsa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir kısayol menüsünü görüntülemek için kalıcı bir çağrı işlev görür. Kullanıcı kısayol menüsünü kapatır veya bir komut seçer kadar uygulama kodu aşağıdaki satırda olmaya devam etmez. Bir kısayol menüsü görüntülemek için kullanabileceğiniz alternatif bir yöntem [CContextMenuManager::ShowPopupMenu](#showpopupmenu). Bu yöntem, kalıcı bir çağrı değil ve seçili komut Kimliğini döndürmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)
