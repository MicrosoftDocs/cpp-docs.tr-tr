---
title: CContextMenuManager Sınıfı
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
ms.openlocfilehash: c676355ebf44d6cc02bfa66ac870757627ae5a58
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754811"
---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager Sınıfı

Nesne, `CContextMenuManager` bağlam menüleri olarak da bilinen kısayol menülerini yönetir.

## <a name="syntax"></a>Sözdizimi

```
class CContextMenuManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|Bir `CContextMenuManager` nesne inşa eder.|
|`CContextMenuManager::~CContextMenuManager`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CContextMenuManager::AddMenu](#addmenu)|Yeni bir kısayol menüsü ekler.|
|[CcontextMenuManager::GetMenuById](#getmenubyid)|Sağlanan kaynak kimliğiyle ilişkili menüye bir tanıtıcı döndürür.|
|[CcontextMenuManager::GetMenuByName](#getmenubyname)|Sağlanan menü adı yla eşleşen bir tanıtıcıyı menüye döndürür.|
|[CContextMenuManager::GetMenuNames](#getmenunames)|Menü adlarının listesini verir.|
|[CContextMenuManager::LoadState](#loadstate)|Windows kayıt defterinde depolanan kısayol menülerini yükler.|
|[CContextMenuManager::ResetState](#resetstate)|Bağlam menüsü yöneticisinden kısayol menülerini temizler.|
|[CContextMenuManager::SaveState](#savestate)|Kısayol menülerini Windows kayıt defterine kaydeder.|
|[CContextMenuManager::SetDontCloseActiveMenü](#setdontcloseactivemenu)|Etkin kısayol menüsü yeni bir kısayol menüsü gösterdiğinde `CContextMenuManager` kapanıp kapanmadığını denetler.|
|[CContextMenuManager::ShowPopupMenü](#showpopupmenu)|Belirtilen kısayol menüsünü görüntüler.|
|[CContextMenuManager::TrackPopUpMenu](#trackpopupmenu)|Belirtilen kısayol menüsünü görüntüler. Seçili menü komutunun dizinini döndürür.|

## <a name="remarks"></a>Açıklamalar

`CContextMenuManager`kısayol menülerini yönetir ve tutarlı bir görünüme sahip olmasını sağlar.

Bir `CContextMenuManager` nesneyi el ile oluşturmamalısınız. Uygulamanızın çerçevesi nesneyi `CContextMenuManager` oluşturur. Ancak, uygulamanız başolarak [başlattığında CWinAppEx::InitContextMenuManager'ı](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) aramalısınız. Bağlam yöneticisinin başlatılmasından sonra, uygulamanız için bağlam yöneticisine bir işaretçi almak için [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) yöntemini kullanın.

Runtime'da kısayol menüleri `AddMenu`oluşturabilirsiniz. Menüyü önce kullanıcı girişi almadan göstermek istiyorsanız, `ShowPopupMenu`'yi arayın. `TrackPopupMenu`bir menü oluşturmak ve kullanıcı girişi için beklemek istediğinizde kullanılır. `TrackPopupMenu`kullanıcı hiçbir şey seçmeden çıkarsa seçili komutun dizinini veya 0'ı döndürür.

Ayrıca, `CContextMenuManager` durumunu Windows kayıt defterine kaydedebilir ve yükleyebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CContextMenuManager` nesneye menü nasıl ekleyeceğinive `CContextMenuManager` nesne yeni bir açılır menü görüntülediğinde etkin açılır menüyü nasıl kapatılmayı gösterir. Bu kod parçacığı Özel Sayfalar [örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CContextMenuManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcontextmenumanager.h

## <a name="ccontextmenumanageraddmenu"></a><a name="addmenu"></a>CContextMenuManager::AddMenu

[CContextMenuManager'a](../../mfc/reference/ccontextmenumanager-class.md)yeni bir kısayol menüsü ekler.

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
[içinde] Yeni menünün adını içeren bir dize için kaynak kimliği.

*uiMenuResId*<br/>
[içinde] Menü kaynak kimliği.

*Lpszname*<br/>
[içinde] Yeni menünün adını içeren bir dize.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa sıfırolmayan; Yöntem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

*UiMenuResId geçersizse* veya aynı ada sahip başka bir menü `CContextMenuManager`zaten .

## <a name="ccontextmenumanagerccontextmenumanager"></a><a name="ccontextmenumanager"></a>CContextMenuManager::CContextMenuManager

[Bir CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) nesnesi oluşturuyor.

```
CContextMenuManager();
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, el ile `CContextMenuManager` oluşturmamalısınız. Uygulamanızın çerçevesi nesneyi `CContextMenuManager` oluşturur. Uygulamanızın başlatılması sırasında [CWinAppEx::InitContextMenuManager'ı](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) aramalısınız. Bağlam yöneticisine bir işaretçi almak için [CWinAppEx::GetContextMenuManager'ı](../../mfc/reference/cwinappex-class.md#getcontextmenumanager)arayın.

## <a name="ccontextmenumanagergetmenubyid"></a><a name="getmenubyid"></a>CcontextMenuManager::GetMenuById

Belirli bir kaynak kimliğiyle ilişkili menüye bir tanıtıcı döndürür.

```
HMENU GetMenuById(UINT nMenuResId) const;
```

### <a name="parameters"></a>Parametreler

*nMenuResId*<br/>
[içinde] Menünün kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

İlişkili menüye `NULL` veya menü bulunamazsa bir tanıtıcı.

## <a name="ccontextmenumanagergetmenubyname"></a><a name="getmenubyname"></a>CcontextMenuManager::GetMenuByName

Bir tanıtıcıyı belirli bir menüye döndürür.

```
HMENU GetMenuByName(
    LPCTSTR lpszName,
    UINT* puiOrigResID = NULL) const;
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
[içinde] Alınacak menünün adını içeren bir dize.

*puiOrigResID*<br/>
[çıkış] UINT için bir işaretçi. Bu parametre, bulunursa belirtilen menünün kaynak kimliğini içerir.

### <a name="return-value"></a>Dönüş Değeri

*LpszName*tarafından belirtilen adla eşleşen menüye bir tutamaç. *LPSzName*adlı bir menü yoksa NULL .

### <a name="remarks"></a>Açıklamalar

Bu yöntem *lpszName*eşleşen bir `GetMenuByName` menü bulursa, parametre *puiOrigResID*menü kaynak kimliği depolar.

## <a name="ccontextmenumanagergetmenunames"></a><a name="getmenunames"></a>CContextMenuManager::GetMenuNames

[CContextMenuManager'a](../../mfc/reference/ccontextmenumanager-class.md)eklenen menü adlarının listesini verir.

```cpp
void GetMenuNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Parametreler

*listOfNames*<br/>
[çıkış] [CStringList](../../mfc/reference/cstringlist-class.md) parametresine başvuru. Bu yöntem, menü adlarının listesini bu parametreye yazar.

## <a name="ccontextmenumanagerloadstate"></a><a name="loadstate"></a>CContextMenuManager::LoadState

Windows kayıt defterinden [CContextMenuManager Sınıfıile](../../mfc/reference/ccontextmenumanager-class.md) ilişkili bilgileri yükler.

```
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Kayıt defteri anahtarının göreli yolunu içeren dize.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*lpszProfileName* parametresi, kayıt defteri girişi için mutlak yol değildir. Uygulamanız için varsayılan kayıt defteri anahtarının sonuna eklenen göreli bir yoldur. Varsayılan kayıt defteri anahtarını almak veya ayarlamak için [sırasıyla CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) ve [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) yöntemlerini kullanın.

Kısayol menülerini kayıt defterine kaydetmek için [CContextMenuManager::SaveState](#savestate) yöntemini kullanın.

## <a name="ccontextmenumanagerresetstate"></a><a name="resetstate"></a>CContextMenuManager::ResetState

[CContextMenuManager Sınıfı](../../mfc/reference/ccontextmenumanager-class.md)ile ilişkili kısayol menülerinden tüm öğeleri temizler.

```
virtual BOOL ResetState();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa DOĞRU; Bir hata oluşursa YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem açılır menüleri temizler ve `CContextMenuManager`'den kaldırır.

## <a name="ccontextmenumanagersavestate"></a><a name="savestate"></a>CContextMenuManager::SaveState

[CContextMenuManager Sınıfıile](../../mfc/reference/ccontextmenumanager-class.md) ilişkili bilgileri Windows kayıt defterine kaydeder.

```
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Kayıt defteri anahtarının göreli yolunu içeren dize.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*lpszProfileName* parametresi, kayıt defteri girişi için mutlak yol değildir. Uygulamanız için varsayılan kayıt defteri anahtarının sonuna eklenen göreli bir yoldur. Varsayılan kayıt defteri anahtarını almak veya ayarlamak için [sırasıyla CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) ve [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) yöntemlerini kullanın.

Kısayol menülerini kayıt defterinden yüklemek için [CContextMenuManager::LoadState](#loadstate) yöntemini kullanın.

## <a name="ccontextmenumanagersetdontcloseactivemenu"></a><a name="setdontcloseactivemenu"></a>CContextMenuManager::SetDontCloseActiveMenü

[CContextMenuManager'ın](../../mfc/reference/ccontextmenumanager-class.md) yeni bir açılır menü görüntülediğinde etkin açılır menüyü kapatıp kapatmadığını denetler.

```cpp
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSet*<br/>
[içinde] Etkin açılır menüyü kapatıp kapatmamayı kontrol eden bir Boolean parametresi. TRUE değeri, etkin açılır menü kapalı olmadığını gösterir. FALSE, etkin açılır menü kapalı olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CContextMenuManager` etkin açılır menü kapanır.

## <a name="ccontextmenumanagershowpopupmenu"></a><a name="showpopupmenu"></a>CContextMenuManager::ShowPopupMenü

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
[içinde] Bu yöntemin görüntüleneeceği menünün kaynak kimliği.

*X*<br/>
[içinde] İstemci koordinatlarında kısayol menüsü için yatay ofset.

*Y*<br/>
[içinde] İstemci koordinatlarında kısayol menüsü için dikey ofset

*pWndSahibi*<br/>
[içinde] Kısayol menüsünün üst penceresine işaretçi.

*bOwnMessage*<br/>
[içinde] İletilerin nasıl yönlendirildiğini gösteren bir Boolean parametresi. *bOwnMessage* FALSE ise standart MFC yönlendirmesi kullanılır. Aksi takdirde, *pWndOwner* iletileri alır.

*hmenuPopup*<br/>
[içinde] Bu yöntemin görüntüleneeceği menünün tutamacı.

*bAutoDestroy*<br/>
[içinde] Menünün otomatik olarak yok edilip edilmeyeceğini gösteren bir Boolean parametresi.

*bRightAlign*<br/>
[içinde] Menü öğelerinin nasıl hizalandığını gösteren bir Boolean parametresi. *bRightAlign* TRUE ise, menü sağdan sola okuma sırası için sağ hizalanır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem menüyü başarıyla gösteriyorsa, ilk yöntem aşırı yük sıfırsız döndürür; aksi takdirde 0. Kısayol menüsü doğru görüntüleniyorsa, ikinci yöntem aşırı yükleme bir işaretçiyi [CMFCPopUpMenu'ye](../../mfc/reference/cmfcpopupmenu-class.md) döndürür; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, her iki yöntemin de bir kısayol menüsü nüsergilemesi için [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) yöntemine benzer. Ancak, `TrackPopupMenu` seçili menü komutunun dizinini döndürür.

*bAutoDestroy* parametresi FALSE ise, bellek kaynaklarını serbest `DestroyMenu` bırakmak için devralınan yöntemi el ile aramanız gerekir. Varsayılan uygulama `ShowPopupMenu` *parametre bAutoDestroy*kullanmaz. İleride kullanılmak üzere veya `CContextMenuManager` sınıftan türetilen özel sınıflar için sağlanır.

## <a name="ccontextmenumanagertrackpopupmenu"></a><a name="trackpopupmenu"></a>CContextMenuManager::TrackPopUpMenu

Belirtilen kısayol menüsünü görüntüler ve seçili kısayol menüsü komutunun dizinini döndürür.

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
[içinde] Bu yöntemin görüntülenebilen kısayol menüsünün tutamacı.

*X*<br/>
[içinde] İstemci koordinatlarında kısayol menüsü için yatay ofset.

*Y*<br/>
[içinde] İstemci koordinatlarında kısayol menüsü için dikey ofset.

*pWndSahibi*<br/>
[içinde] Kısayol menüsünün üst penceresine işaretçi.

*bRightAlign*<br/>
[içinde] Menü öğelerinin nasıl hizalandığına dair boolean parametresi. *bRightAlign* TRUE ise, menü sağdan sola okuma sırası için sağ hizalanır. *bRightAlign* FALSE ise, menü soldan sağa okuma sırası için sola hizalanır.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcının seçtiği komutun menü komut kimliği; Kullanıcı bir menü komutu seçmeden kısayol menüsünü kapatırsa 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kısayol menüsünü görüntülemek için modal bir çağrı işlevi görür. Kullanıcı kısayol menüsünü kapatana veya bir komut seçene kadar uygulama kod da aşağıdaki satıra devam etmez. Bir kısayol menüsünü görüntülemek için kullanabileceğiniz alternatif bir yöntem [CContextMenuManager::ShowPopupMenu](#showpopupmenu). Bu yöntem bir modal arama değildir ve seçili komutun kimliğini döndürmez.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)
