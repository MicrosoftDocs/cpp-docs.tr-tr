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
ms.openlocfilehash: c8a51a33c69b09d0ecd61520b5f1c9ff18c290a0
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78868996"
---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager sınıfı

`CContextMenuManager` nesnesi, bağlam menüleri olarak da bilinen kısayol menülerini yönetir.

## <a name="syntax"></a>Sözdizimi

```
class CContextMenuManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CContextMenuManager:: CContextMenuManager](#ccontextmenumanager)|`CContextMenuManager` nesnesi oluşturur.|
|`CContextMenuManager::~CContextMenuManager`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CContextMenuManager:: MenüEkle](#addmenu)|Yeni bir kısayol menüsü ekler.|
|[CContextMenuManager:: Getmenubyıd](#getmenubyid)|Belirtilen kaynak KIMLIĞIYLE ilişkili menüye bir tanıtıcı döndürür.|
|[CContextMenuManager:: GetMenuByName](#getmenubyname)|Menüye, belirtilen menü adıyla eşleşen bir tanıtıcı döndürür.|
|[CContextMenuManager:: GetMenuNames](#getmenunames)|Menü adları listesini döndürür.|
|[CContextMenuManager:: LoadState](#loadstate)|Windows kayıt defterinde depolanan kısayol menülerini yükler.|
|[CContextMenuManager:: ResetState](#resetstate)|Kısayol menülerini bağlam menüsü yöneticisinden temizler.|
|[CContextMenuManager:: Savemlak](#savestate)|Kısayol menülerini Windows kayıt defterine kaydeder.|
|[CContextMenuManager:: SetDontCloseActiveMenu](#setdontcloseactivemenu)|Yeni bir kısayol menüsü gösterdiğinde `CContextMenuManager` etkin kısayol menüsünü kapatıp kapatmadığını denetler.|
|[CContextMenuManager:: ShowPopupMenu](#showpopupmenu)|Belirtilen kısayol menüsünü görüntüler.|
|[CContextMenuManager:: TrackPopupMenu](#trackpopupmenu)|Belirtilen kısayol menüsünü görüntüler. Seçilen menü komutunun dizinini döndürür.|

## <a name="remarks"></a>Açıklamalar

`CContextMenuManager`, kısayol menülerini yönetir ve tutarlı bir görünüme sahip olduklarından emin olur.

`CContextMenuManager` nesnesini el ile oluşturmamalıdır. Uygulamanızın çerçevesi `CContextMenuManager` nesnesini oluşturur. Bununla birlikte, uygulamanız başlatıldığında [CWinAppEx:: InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) öğesini çağırmanız gerekir. Bağlam yöneticisini başlattıktan sonra, uygulamanızın bağlam Yöneticisi için bir işaretçi almak üzere [CWinAppEx:: GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) metodunu kullanın.

`AddMenu`çağırarak çalışma zamanında kısayol menüleri oluşturabilirsiniz. Menüyü önce Kullanıcı girişi almadan göstermek istiyorsanız `ShowPopupMenu`çağırın. `TrackPopupMenu`, bir menü oluşturmak ve Kullanıcı girişini beklemek istediğinizde kullanılır. `TrackPopupMenu` seçili komutun dizinini veya kullanıcının hiçbir şeyi seçmeden çıkış yapsa 0 döndürür.

`CContextMenuManager` Ayrıca, durumunu Windows kayıt defterine kaydedip yükleyebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CContextMenuManager` nesnesine bir menünün nasıl ekleneceğini ve `CContextMenuManager` nesnesi yeni bir açılır menü görüntülediğinde etkin açılır menünün nasıl kapanacağını göstermektedir. Bu kod parçacığı, [özel sayfalar örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CContextMenuManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcontextmenumanager. h

##  <a name="addmenu"></a>CContextMenuManager:: MenüEkle

[CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)öğesine yeni bir kısayol menüsü ekler.

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
'ndaki Yeni menünün adını içeren bir dize için kaynak KIMLIĞI.

*Uııd*<br/>
'ndaki Menü kaynak KIMLIĞI.

*lpszName*<br/>
'ndaki Yeni menünün adını içeren bir dize.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Yöntem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

*Uıımtrresd* geçersiz ise veya aynı ada sahip başka bir menü `CContextMenuManager`zaten varsa, bu yöntem başarısız olur.

##  <a name="ccontextmenumanager"></a>CContextMenuManager:: CContextMenuManager

[CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) nesnesi oluşturur.

```
CContextMenuManager();
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda `CContextMenuManager` el ile oluşturmamalıdır. Uygulamanızın çerçevesi `CContextMenuManager` nesnesini oluşturur. Uygulamanızın başlatılması sırasında [CWinAppEx:: InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) öğesini çağırmanız gerekir. Bağlam yöneticisine bir işaretçi almak için, [CWinAppEx:: GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager)çağırın.

##  <a name="getmenubyid"></a>CContextMenuManager:: Getmenubyıd

Verilen bir kaynak KIMLIĞIYLE ilişkili menüye bir tanıtıcı döndürür.

```
HMENU GetMenuById(UINT nMenuResId) const;
```

### <a name="parameters"></a>Parametreler

*Nmenuresd*<br/>
'ndaki Menünün kaynak KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Menü bulunmazsa ilişkili menüye yönelik bir tanıtıcı veya `NULL`.

##  <a name="getmenubyname"></a>CContextMenuManager:: GetMenuByName

Belirli bir menüye bir tanıtıcı döndürür.

```
HMENU GetMenuByName(
    LPCTSTR lpszName,
    UINT* puiOrigResID = NULL) const;
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
'ndaki Alınacak menünün adını içeren bir dize.

*puiOrigResID*<br/>
dışı Bir UINT işaretçisi. Bu parametre, bulunursa, belirtilen menünün kaynak KIMLIĞINI içerir.

### <a name="return-value"></a>Dönüş Değeri

Menü için *lpszName*tarafından belirtilen adla eşleşen bir tanıtıcı. *LpszName*adlı bir menü yoksa null.

### <a name="remarks"></a>Açıklamalar

Bu yöntemde *lpszName*ile eşleşen bir menü bulunursa `GetMenuByName`, menü kaynak kimliğini *puiOrigResID*parametresinde depolar.

##  <a name="getmenunames"></a>CContextMenuManager:: GetMenuNames

[CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)öğesine eklenen menü adlarının listesini döndürür.

```
void GetMenuNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Parametreler

*Lıfnames*<br/>
dışı [CStringList](../../mfc/reference/cstringlist-class.md) parametresine bir başvuru. Bu yöntem, menü adlarının listesini bu parametreye yazar.

##  <a name="loadstate"></a>CContextMenuManager:: LoadState

[CContextMenuManager sınıfıyla](../../mfc/reference/ccontextmenumanager-class.md) Ilişkili bilgileri Windows kayıt defterinden yükler.

```
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Bir kayıt defteri anahtarının göreli yolunu içeren bir dize.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*LpszProfileName* parametresi bir kayıt defteri girişi için mutlak yol değil. Bu, uygulamanız için varsayılan kayıt defteri anahtarının sonuna eklenen göreli bir yoldur. Varsayılan kayıt defteri anahtarını almak veya ayarlamak için sırasıyla [CWinAppEx:: GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) ve [CWinAppEx:: SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) yöntemlerini kullanın.

Kısayol menülerini kayıt defterine kaydetmek için [CContextMenuManager:: savthe](#savestate) metodunu kullanın.

##  <a name="resetstate"></a>CContextMenuManager:: ResetState

[CContextMenuManager sınıfıyla](../../mfc/reference/ccontextmenumanager-class.md)ilişkili kısayol menülerinden tüm öğeleri temizler.

```
virtual BOOL ResetState();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Bir hata oluşursa FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem açılır menüleri temizler ve `CContextMenuManager`kaldırır.

##  <a name="savestate"></a>CContextMenuManager:: Savemlak

[CContextMenuManager sınıfıyla](../../mfc/reference/ccontextmenumanager-class.md) Ilişkili bilgileri Windows kayıt defterine kaydeder.

```
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Bir kayıt defteri anahtarının göreli yolunu içeren bir dize.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*LpszProfileName* parametresi bir kayıt defteri girişi için mutlak yol değil. Bu, uygulamanız için varsayılan kayıt defteri anahtarının sonuna eklenen göreli bir yoldur. Varsayılan kayıt defteri anahtarını almak veya ayarlamak için sırasıyla [CWinAppEx:: GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) ve [CWinAppEx:: SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) yöntemlerini kullanın.

Kayıt defterinden kısayol menülerini yüklemek için [CContextMenuManager:: LoadState](#loadstate) metodunu kullanın.

##  <a name="setdontcloseactivemenu"></a>CContextMenuManager:: SetDontCloseActiveMenu

[CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) 'ın yeni bir açılır menü görüntülediğinde etkin açılır menüyü kapatmayacağını denetler.

```
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSet*<br/>
'ndaki Etkin açılır menünün kapatılıp kapanmayacağını denetleyen Boolean bir parametre. TRUE değeri, etkin açılır menünün kapanmadığını gösterir. FALSE, etkin açılır menünün kapalı olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak `CContextMenuManager`, etkin açılır menüyü kapatır.

##  <a name="showpopupmenu"></a>CContextMenuManager:: ShowPopupMenu

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

*Uııd*<br/>
'ndaki Bu yöntemin görüntüleyeceği menünün kaynak KIMLIĞI.

*sayı*<br/>
'ndaki İstemci koordinatlarındaki kısayol menüsünün yatay boşluğu.

*Iz*<br/>
'ndaki İstemci koordinatlarındaki kısayol menüsünün dikey boşluğu

*pWndOwner*<br/>
'ndaki Kısayol menüsünün üst penceresine yönelik bir işaretçi.

*Bowniletisi*<br/>
'ndaki İletilerin nasıl yönlendirildiğini gösteren bir Boolean parametresi. *BOwnMessage* false Ise standart MFC yönlendirme kullanılır. Aksi takdirde, *pWndOwner* iletileri alır.

*hmenuPopup*<br/>
'ndaki Bu yöntemin görüntüleyeceği menünün tutamacı.

*bAutoDestroy*<br/>
'ndaki Menünün otomatik olarak yok edilemeyeceğini belirten bir Boole parametresi.

*Parlak*<br/>
'ndaki Menü öğelerinin nasıl hizalandığını gösteren bir Boolean parametresi. *Parlaklık* değeri true ise, menü sağdan sola okuma düzeni için sağa hizalanır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem menüyü başarıyla gösteriyorsa, ilk yöntem aşırı yüklemesi sıfır dışında bir değer döndürür; Aksi takdirde 0. İkinci yöntem aşırı yüklemesi, kısayol menüsü doğru şekilde görüntüleniyorsa [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) için bir işaretçi döndürür; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, her iki yöntemde de bir kısayol menüsü görüntüleyen [CContextMenuManager:: TrackPopupMenu](#trackpopupmenu) yöntemine benzer. Ancak, `TrackPopupMenu` seçili menü komutunun dizinini döndürür.

*BAutoDestroy* parametresi false ise, bellek kaynaklarını serbest bırakmak için devralınan `DestroyMenu` yöntemini el ile çağırmanız gerekir. `ShowPopupMenu` varsayılan uygulanması, *bAutoDestroy*parametresini kullanmaz. Bu, gelecekte kullanılmak üzere veya `CContextMenuManager` sınıfından türetilmiş özel sınıflar için sağlanır.

##  <a name="trackpopupmenu"></a>CContextMenuManager:: TrackPopupMenu

Belirtilen kısayol menüsünü görüntüler ve seçilen kısayol menü komutunun dizinini döndürür.

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
'ndaki Bu yöntemin görüntülediği kısayol menüsünün tutamacı.

*sayı*<br/>
'ndaki İstemci koordinatlarındaki kısayol menüsünün yatay boşluğu.

*Iz*<br/>
'ndaki İstemci koordinatlarındaki kısayol menüsünün dikey boşluğu.

*pWndOwner*<br/>
'ndaki Kısayol menüsünün üst penceresine yönelik bir işaretçi.

*Parlak*<br/>
'ndaki Menü öğelerinin nasıl hizalandığını gösteren bir Boolean parametresi. *Parlaklık* değeri true ise, menü sağdan sola okuma düzeni için sağa hizalanır. *Parlaklık* değeri false ise, menü sola doğru okuma düzeni için sola hizalanır.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcının seçtiği komutun menü komut KIMLIĞI; Kullanıcı kısayol menüsünü bir menü komutu seçmeden kapatırsa 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir kısayol menüsünü göstermek için kalıcı bir çağrı olarak çalışır. Kullanıcı, kısayol menüsünü kapatana veya bir komut seçinceye kadar kodda aşağıdaki satıra devam etmez. Bir kısayol menüsünü göstermek için kullanabileceğiniz alternatif bir yöntem [CContextMenuManager:: ShowPopupMenu](#showpopupmenu)olur. Bu yöntem, kalıcı bir çağrı değildir ve seçili komutun KIMLIĞINI döndürmez.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)
