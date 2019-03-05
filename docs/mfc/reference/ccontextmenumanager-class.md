---
title: CContextMenuManager sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 594b78fd36dcb1ff92c63867688c38eac7520eba
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304345"
---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager sınıfı

`CContextMenuManager` Nesnesi bağlam menüleri olarak da bilinen kısayol menülerini yönetir.

## <a name="syntax"></a>Sözdizimi

```
class CContextMenuManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|Oluşturur bir `CContextMenuManager` nesne.|
|`CContextMenuManager::~CContextMenuManager`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CContextMenuManager::AddMenu](#addmenu)|Yeni bir kısayol menüsü ekler.|
|[CContextMenuManager::GetMenuById](#getmenubyid)|Sağlanan kaynak kimliği ile ilişkili menüsüne bir tanıtıcı döndürür.|
|[CContextMenuManager::GetMenuByName](#getmenubyname)|Sağlanan menü adıyla eşleşen menüsüne bir tanıtıcı döndürür.|
|[CContextMenuManager::GetMenuNames](#getmenunames)|Menü adları listesini döndürür.|
|[CContextMenuManager::LoadState](#loadstate)|Windows kayıt defterinde depolanan kısayol menüleri yükler.|
|[CContextMenuManager::ResetState](#resetstate)|Kısayol menüleri bağlam menüsü Yöneticisi'nden temizler.|
|[CContextMenuManager::SaveState](#savestate)|Kısayol menüleri Windows kayıt defterine kaydeder.|
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|Denetimleri olmadığını `CContextMenuManager` etkin kısayol menüsünü kapatır, yeni bir kısayol menüsünü gösterir.|
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|Belirtilen kısayol menüsünü görüntüler.|
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|Belirtilen kısayol menüsünü görüntüler. Seçili bir menü komutunu dizinini döndürür.|

## <a name="remarks"></a>Açıklamalar

`CContextMenuManager` kısayol menülerini yönetir ve bunların tutarlı bir görünüm sahip olduğunuzdan emin olun.

Oluşturacağınız değil bir `CContextMenuManager` el ile nesne. Uygulama Framework'ü oluşturur `CContextMenuManager` nesne. Ancak, çağırmalıdır [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) uygulamanızın ne zaman başlatılır. Bağlam Yöneticisi başlatma sonrasında yöntemi kullanmak [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) uygulamanız için İçerik Yöneticisi'ni işaretçisi elde edilir.

Çalışma zamanında kısayol menüleri çağırarak oluşturabilirsiniz `AddMenu`. Alan ilk kullanıcı girişi olmadan menü göstermek istiyorsanız, çağrı `ShowPopupMenu`. `TrackPopupMenu` menü oluşturmak ve kullanıcı girişini bekleme istediğinizde kullanılır. `TrackPopupMenu` Kullanıcı hiçbir şey seçmeden çıkıldı seçili komutu ya da 0 dizinini döndürür.

`CContextMenuManager` Kaydedebilir ve durumunu Windows kayıt defterine yükleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir menü eklemek gösterilmiştir bir `CContextMenuManager` nesne ve nasıl etkin açılır menüyü Kapat değil, `CContextMenuManager` nesne yeni bir açılır menü görüntüler. Bu kod parçacığı parçasıdır [özel sayfaları örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CContextMenuManager`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcontextmenumanager.h

##  <a name="addmenu"></a>  CContextMenuManager::AddMenu

Yeni bir kısayol menüsüne ekler [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).

```
BOOL AddMenu(
    UINT uiMenuNameResId,
    UINT uiMenuResId);

BOOL AddMenu(
    LPCTSTR lpszName,
    UINT uiMenuResId);
```

### <a name="parameters"></a>Parametreler

*uiMenuNameResId*<br/>
[in] Yeni menü adını içeren bir dize için bir kaynak kimliği.

*uiMenuResId*<br/>
[in] Menü kaynak kimliği

*lpszName*<br/>
[in] Yeni menü adını içeren bir dize.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; yöntem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, başarısız *uiMenuResId* geçersiz veya aynı ada sahip başka bir menü zaten yer alıyorsa `CContextMenuManager`.

##  <a name="ccontextmenumanager"></a>  CContextMenuManager::CContextMenuManager

Oluşturur bir [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) nesne.

```
CContextMenuManager();
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, değil oluşturmalısınız bir `CContextMenuManager` el ile. Uygulama Framework'ü oluşturur `CContextMenuManager` nesne. Çağırmalısınız [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) , uygulamanızın başlatma sırasında. Bağlam Yöneticisi için bir işaretçi alma çağrısı [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager).

##  <a name="getmenubyid"></a>  CContextMenuManager::GetMenuById

Belirtilen kaynak kimliği ile ilişkili menüsüne bir tanıtıcı döndürür.

```
HMENU GetMenuById(UINT nMenuResId) const;
```

### <a name="parameters"></a>Parametreler

*nMenuResId*<br/>
[in] Menü kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

İlişkili menüsüne bir tanıtıcı veya `NULL` menü bulunamaması durumunda.

##  <a name="getmenubyname"></a>  CContextMenuManager::GetMenuByName

Belirli bir menüsüne bir tanıtıcı döndürür.

```
HMENU GetMenuByName(
    LPCTSTR lpszName,
    UINT* puiOrigResID = NULL) const;
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
[in] Alınacak menünün adını içeren bir dize.

*puiOrigResID*<br/>
[out] Bir birim için bir işaretçi. Bu parametre, belirtilen menüsünde, kaynak Kimliğini içerir bulunamadı.

### <a name="return-value"></a>Dönüş Değeri

Bir tanıtıcı tarafından belirtilen adla eşleşen menüsüne *lpszName*. Menü yok adlı yoksa NULL *lpszName*.

### <a name="remarks"></a>Açıklamalar

Bu yöntem eşleşen bir menü bulursa *lpszName*, `GetMenuByName` parametreyi menüsü kaynak Kimliğini depolar *puiOrigResID*.

##  <a name="getmenunames"></a>  CContextMenuManager::GetMenuNames

Eklenen menü adları listesini döndürür [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).

```
void GetMenuNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Parametreler

*listOfNames*<br/>
[out] Bir başvuru bir [CStringList](../../mfc/reference/cstringlist-class.md) parametresi. Bu yöntem, bu parametre için menü adları listesi yazar.

##  <a name="loadstate"></a>  CContextMenuManager::LoadState

İle ilişkili bilgileri yükler [CContextMenuManager sınıfı](../../mfc/reference/ccontextmenumanager-class.md) Windows kayıt defterinden.

```
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Bir kayıt defteri anahtarının göreli yolu içeren bir dize.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

*LpszProfileName* parametresi bir kayıt defteri girdisi için mutlak yol değil. Uygulamanız için varsayılan kayıt defteri anahtarı sonuna eklenen bir göreli yoludur. Alma veya varsayılan kayıt defteri anahtarı ayarlama için yöntemleri kullanın. [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) ve [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) sırasıyla.

Bu yöntemi kullanmak [CContextMenuManager::SaveState](#savestate) kısayol menülerini kayıt defterine kaydetmek için.

##  <a name="resetstate"></a>  CContextMenuManager::ResetState

Tüm öğeleri ile ilişkili kısayol menülerinde temizler [CContextMenuManager sınıfı](../../mfc/reference/ccontextmenumanager-class.md).

```
virtual BOOL ResetState();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Bir hata oluştuğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, açılır menüler temizler ve bunları kaldırır `CContextMenuManager`.

##  <a name="savestate"></a>  CContextMenuManager::SaveState

İle ilişkili bilgileri kaydeder [CContextMenuManager sınıfı](../../mfc/reference/ccontextmenumanager-class.md) Windows kayıt defterine.

```
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Bir kayıt defteri anahtarının göreli yolu içeren bir dize.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

*LpszProfileName* parametresi bir kayıt defteri girdisi için mutlak yol değil. Uygulamanız için varsayılan kayıt defteri anahtarı sonuna eklenen bir göreli yoludur. Alma veya varsayılan kayıt defteri anahtarı ayarlama için yöntemleri kullanın. [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) ve [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) sırasıyla.

Bu yöntemi kullanmak [CContextMenuManager::LoadState](#loadstate) kısayol menülerini kayıt defterinden yüklenemedi.

##  <a name="setdontcloseactivemenu"></a>  CContextMenuManager::SetDontCloseActiveMenu

Denetimleri olmadığını [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) etkin açılır menüsünden Yeni bir açılır menü görüntülendiğinde kapatır.

```
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parametreler

*bInternet*<br/>
[in] Etkin açılır menüyü Kapat verilip verilmeyeceğini denetler bir Boole parametresi. Etkin açılır menü kapalı TRUE değerini gösterir. FALSE, etkin bir açılan menü kapalı olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CContextMenuManager` etkin açılır menü kapatır.

##  <a name="showpopupmenu"></a>  CContextMenuManager::ShowPopupMenu

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

*uiMenuResId*<br/>
[in] Bu yöntem görüntüler menüsü kaynak kimliği.

*x*<br/>
[in] İstemci koordinatları kısayol menüsünde için uzaklık yatay.

*Y*<br/>
[in] İstemci koordinatları kısayol menüsünde dikey kaydırma uzaklığı

*pWndOwner*<br/>
[in] Kısayol menüsünün üst penceresine bir işaretçi.

*bOwnMessage*<br/>
[in] İletilerin nasıl yönlendirileceğini gösteren bir Boole parametresi. Varsa *bOwnMessage* FALSE, standart MFC olan Yönlendirme kullanılır. Aksi takdirde, *pWndOwner* iletileri alır.

*hmenuPopup*<br/>
[in] Bu yöntem görüntülenecek menü tanıtıcısı.

*bAutoDestroy*<br/>
[in] Menü otomatik olarak edileceği olup olmadığını gösteren bir Boole parametresi.

*bRightAlign*<br/>
[in] Menü öğelerinin nasıl hizalandığını gösteren bir Boole parametresi. Varsa *bRightAlign* TRUE ise sağa hizalı sağdan sola okuma düzeni için menü.

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem aşırı yükleme yöntemi başarıyla menü gösterir, sıfır döndürür; Aksi durumda 0. İkinci yöntem aşırı yüklemesi için bir işaretçi döndürür [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) kısayol menü görüntüler doğru; Aksi takdirde NULL varsa.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yöntem benzer [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) içeren iki yöntem de bir kısayol menüsünü görüntüleme. Ancak, `TrackPopupMenu` seçili menü komutunu dizinini döndürür.

Parametre *bAutoDestroy* yanlış, el ile devralınan çağırmalıdır `DestroyMenu` bellek kaynakları serbest bırakmak için yöntemi. Varsayılan uygulaması `ShowPopupMenu` parametresini kullanmıyor *bAutoDestroy*. Öğesinden türetilen özel sınıflar veya gelecekte kullanım için sağlanan `CContextMenuManager` sınıfı.

##  <a name="trackpopupmenu"></a>  CContextMenuManager::TrackPopupMenu

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

*hmenuPopup*<br/>
[in] Bu yöntem görüntüler kısayol menüsünü tanıtıcısı.

*x*<br/>
[in] İstemci koordinatları kısayol menüsünde için uzaklık yatay.

*Y*<br/>
[in] Dikey istemci koordinatları kısayol menüsünde için uzaklık.

*pWndOwner*<br/>
[in] Kısayol menüsünün üst penceresine bir işaretçi.

*bRightAlign*<br/>
[in] Menü öğelerinin nasıl hizalandığını gösteren bir Boole parametresi. Varsa *bRightAlign* TRUE ise sağa hizalı sağdan sola okuma düzeni için menü. Varsa *bRightAlign* yanlış, sağdan sola okuma düzeni için sola hizalanmış menüsü.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı komut menü komut kimliği; 0 kullanıcı kısayol menüsünü menü komutunu seçmeden kapatır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir kısayol menüsünü görüntülemek için kalıcı bir çağrı işlev görür. Kullanıcı kısayol menüsünü kapatır veya komut seçtiğinde kadar uygulama aşağıdaki kod satırında devam etmeyecek. Bir kısayol menüsünü görüntülemek için kullanabileceğiniz alternatif bir yöntem [CContextMenuManager::ShowPopupMenu](#showpopupmenu). Bu yöntem, kalıcı bir çağrı değildir ve seçili komut Kimliğini döndürmez.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)
