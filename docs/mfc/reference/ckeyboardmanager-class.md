---
title: CKeyboardManager sınıfı
ms.date: 11/04/2016
f1_keywords:
- CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CleanUp
- AFXKEYBOARDMANAGER/CKeyboardManager::FindDefaultAccelerator
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyHandled
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyPrintable
- AFXKEYBOARDMANAGER/CKeyboardManager::IsShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::LoadState
- AFXKEYBOARDMANAGER/CKeyboardManager::ResetAll
- AFXKEYBOARDMANAGER/CKeyboardManager::SaveState
- AFXKEYBOARDMANAGER/CKeyboardManager::ShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::TranslateCharToUpper
- AFXKEYBOARDMANAGER/CKeyboardManager::UpdateAccelTable
helpviewer_keywords:
- CKeyboardManager [MFC], CKeyboardManager
- CKeyboardManager [MFC], CleanUp
- CKeyboardManager [MFC], FindDefaultAccelerator
- CKeyboardManager [MFC], IsKeyHandled
- CKeyboardManager [MFC], IsKeyPrintable
- CKeyboardManager [MFC], IsShowAllAccelerators
- CKeyboardManager [MFC], LoadState
- CKeyboardManager [MFC], ResetAll
- CKeyboardManager [MFC], SaveState
- CKeyboardManager [MFC], ShowAllAccelerators
- CKeyboardManager [MFC], TranslateCharToUpper
- CKeyboardManager [MFC], UpdateAccelTable
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
ms.openlocfilehash: 3360a28d50f64546837cc5ef35dcfc761b4fb0f5
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779813"
---
# <a name="ckeyboardmanager-class"></a>CKeyboardManager sınıfı

Ana çerçeve penceresi ve alt çerçeve pencereleri için kısayol tuşu tablolarını yönetir.

## <a name="syntax"></a>Sözdizimi

```
class CKeyboardManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Ad|Açıklama|
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Oluşturur bir `CKeyboardManager` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CKeyboardManager::CleanUp](#cleanup)|Kısayol tuşu tablolarını temizler.|
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Belirtilen komut ve pencere için varsayılan kısayol tuşu alır.|
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Bir anahtar tarafından Hızlandırıcı tablosu işlenip işlenmediğini belirler.|
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Yazdırılabilir bir karakter olup olmadığını gösterir.|
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Menü komutu için tüm kısayol tuşlarının veya yalnızca varsayılan kısayol tuşu gösterip göstermediği belirtir.|
|[CKeyboardManager::LoadState](#loadstate)|Windows kayıt defterinden kısayol tuşu tablolarını yükler.|
|[CKeyboardManager::ResetAll](#resetall)|Uygulama kaynağından kısayol tuşu tablolarını yeniden yükler.|
|[CKeyboardManager::SaveState](#savestate)|Kısayol tuşu tablolarını Windows kayıt defterine kaydeder.|
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Framework tüm komutlar için tüm kısayol tuşlarının veya tek bir kısayol tuşuna her komut için görüntülenip görüntülenmeyeceğini belirtir. Bu yöntem yalnızca bir ilişkili bir kısayol tuşuna sahip komutları etkilemez.|
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|Kendi üst kasaya bir karakteri dönüştürür.|
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Bir kısayol anahtar tablosu ile yeni bir kısayol anahtar tablosunu güncelleştirir.|

## <a name="remarks"></a>Açıklamalar

Bu sınıfın üyeleri kaydedin ve Windows kayıt defterine kısayol tuşu tablolarını yük kısayol tuşu tablolarını güncelleştirmek için bir şablon kullanmak etkinleştirmeniz ve bir çerçeve penceresinde bir komutun varsayılan kısayol tuşu bulun. Ayrıca, `CKeyboardManager` nesne kısayol tuşları kullanıcıya nasıl görüntüleneceğini denetlemenizi sağlar.

Oluşturacağınız değil bir `CKeyboardManager` el ile nesne. Uygulamanızın framework tarafından otomatik olarak yeniden oluşturulur. Ancak, çağırmalıdır [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) , uygulamanızın başlatma işlemi sırasında. Bir işaretçi, uygulamanız için klavye Manager'a almak için arama [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir işaretçi almak gösterilmiştir bir `CKeyboardManager` nesnesinden bir `CWinAppEx` sınıfı ve menü komutları ile ilişkili tüm kısayol tuşlarının gösterme. Bu kod parçacığı parçasıdır [özel sayfaları örnek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxkeyboardmanager.h

##  <a name="ckeyboardmanager"></a>  CKeyboardManager::CKeyboardManager

Oluşturur bir `CKeyboardManager` nesne.

```
CKeyboardManager();
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, oluşturma gerekmez bir `CKeyboardManager` doğrudan. Varsayılan olarak, framework sizin için oluşturur. Bir işaretçi almaya `CKeyboardManager`, çağrı [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). Bir el ile oluşturursanız yöntemi ile başlatması gerekir [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).

##  <a name="cleanup"></a>  CKeyboardManager::CleanUp

Serbest bırakma `CKeyboardManager` kaynakları ve tüm kısayol anahtar eşlemelerinin temizler.

```
static void CleanUp();
```

### <a name="remarks"></a>Açıklamalar

Kısayol tuşları hakkında daha fazla bilgi için bkz: [klavye ve fare özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md).

Çerçeve bunu otomatik olarak uygulama kapatma sırasında çağırdığı uygulamanız çıkış yaptığında bu işlevi çağırın gerekmez.

##  <a name="finddefaultaccelerator"></a>  CKeyboardManager::FindDefaultAccelerator

Belirtilen komut ve pencere için varsayılan kısayol tuşu alır.

```
static BOOL FindDefaultAccelerator(
    UINT uiCmd,
    CString& str,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[in] Komut kimliği.

*str*<br/>
[out] Bir başvuru bir `CString` nesne.

*pWndFrame*<br/>
[in] Çerçeve penceresi için bir işaretçi.

*bIsDefaultFrame*<br/>
[in] Çerçeve penceresi varsayılan çerçeve penceresi olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Kısayol bulunursa sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından belirtilen komut arar *uiCmd* ve varsayılan kısayol tuşu alır. Yöntemi, bu kısayol tuşu ile ilişkili dizeyi alır ve değerine yazar *str* parametresi.

##  <a name="iskeyhandled"></a>  CKeyboardManager::IsKeyHandled

Belirtilen anahtarı tarafından işlenip işlenmediğini belirler [CKeyboardManager sınıfı](../../mfc/reference/ckeyboardmanager-class.md).

```
static BOOL __stdcall IsKeyHandled(
    WORD nKey,
    BYTE fVirt,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*nKey*|[in] Denetlenecek anahtarı.|
|*fVirt*|[in] Kısayol tuşu davranışını belirtir. Olası değerler listesi için bkz. [HIZLANDIRMA yapısı](/windows/desktop/api/winuser/ns-winuser-tagaccel).|
|*pWndFrame*|[in] Çerçeve penceresi. Bu yöntem, bir kısayol tuşu bu çerçeveye işlenip işlenmediğini belirler.|
|*bIsDefaultFrame*|[in] Belirten bir Boole parametresi olmadığını *pWndFrame* varsayılan çerçeve penceresidir.|

### <a name="return-value"></a>Dönüş Değeri

Kısayol tuşu işlenen TRUE. FALSE anahtar işlenmezse ya da *pWndFrame* null.

### <a name="remarks"></a>Açıklamalar

Giriş parametreleri giriş Hızlandırıcı tablosunda hem eşleşmelidir *nKey* ve *fVirt* bir kısayol tuşu içinde işlenir olup olmadığını belirlemek için *pWndFrame*.

##  <a name="iskeyprintable"></a>  CKeyboardManager::IsKeyPrintable

Yazdırılabilir bir karakter olup olmadığını gösterir.

```
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*nChar*|[in] Bu yöntem denetleyen karakter.|

### <a name="return-value"></a>Dönüş Değeri

Sıfır dışında yazdırılabilir bir karakterse, değilse sıfır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem çağrısı başarısız olur [GetKeyboardState](/windows/desktop/api/winuser/nf-winuser-getkeyboardstate) başarısız olur.

##  <a name="isshowallaccelerators"></a>  CKeyboardManager::IsShowAllAccelerators

Menü komutlarını ile ilişkili tüm kısayol tuşlarının veya yalnızca varsayılan kısayol tuşlarını gösterip göstermediği belirtir.

```
static BOOL IsShowAllAccelerators();
```

### <a name="return-value"></a>Dönüş Değeri

Menü komutları için tüm kısayol tuşlarının uygulama listeler olursa sıfır dışı; 0 uygulama yalnızca varsayılan kısayol tuşları görüntüler.

### <a name="remarks"></a>Açıklamalar

Uygulama, menü komutlarını menü çubuğunda kısayol tuşları listeler. İşlevini [CKeyboardManager::ShowAllAccelerators](#showallaccelerators) denetlemek için mi uygulama listeler tüm kısayol tuşlarının veya yalnızca varsayılan kısayol tuşları.

##  <a name="loadstate"></a>  CKeyboardManager::LoadState

Windows kayıt defterinden kısayol tuşu tablolarını yükler.

```
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Kayıt defteri yolu burada `CKeyboardManager` verileri kaydedilir.

*pDefaultFrame*<br/>
[in] Varsayılan pencere olarak kullanılacak bir çerçeve penceresi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Durum, aksi takdirde başarıyla yüklendi ya da 0 olursa sıfır dışı.

### <a name="remarks"></a>Açıklamalar

Varsa *lpszProfileName* parametre NULL ise, bu yöntem varsayılan kayıt defteri konumunu denetler `CKeyboardManager` veri. Varsayılan kayıt defteri konumu tarafından belirtilen [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md). Verileri önceden yöntemiyle yazılmalıdır [CKeyboardManager::SaveState](#savestate).

Varsayılan pencere belirtmezseniz, uygulamanızın ana çerçeve penceresi kullanılır.

##  <a name="resetall"></a>  CKeyboardManager::ResetAll

Uygulama kaynağından kısayol tuşu tablolarını yeniden yükler.

```
void ResetAll();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev depolanan kısayolları temizler `CKeyboardManager` örneği. Ardından Uygulama kaynağı klavye Manager'dan durumunu yeniden yükler.

##  <a name="savestate"></a>  CKeyboardManager::SaveState

Kısayol tuşu tablolarını Windows kayıt defterine kaydeder.

```
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Kaydetmek için kayıt defteri yolu `CKeyboardManager` durumu.

*pDefaultFrame*<br/>
[in] Varsayılan pencere olur bir çerçeve penceresi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Klavye manager durumu başarıyla kaydedildi olursa sıfır dışı ya da aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsa *lpszProfileName* parametresi NULL olduğundan, bu yöntem yazacak `CKeyboardManager` durum tarafından belirtilen varsayılan konuma [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md). Bir konum belirtirseniz, verileri daha sonra yöntem kullanarak yükleyebilir [CKeyboardManager::LoadState](#loadstate).

Varsayılan pencere belirtmezseniz, ana çerçeve penceresinin varsayılan penceresi olarak kullanılır.

##  <a name="showallaccelerators"></a>  CKeyboardManager::ShowAllAccelerators

Menü komutları ile ilişkili tüm kısayol tuşlarının gösterir.

```
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```

### <a name="parameters"></a>Parametreler

*bShowAll*<br/>
[in] TRUE ise tüm kısayol tuşlarının görüntülenir. FALSE ise, yalnızca ilk kısayol tuşu görüntülenir.

*lpszDelimiter*<br/>
[in] Kısayol tuşları arasında eklemek için bir dize. Bir kısayol tuşu görüntülenir, yalnızca bu sınırlayıcı bir etkisi yoktur.

### <a name="remarks"></a>Açıklamalar

Bir komut ile ilişkili birden fazla kısayol tuşu varsa, varsayılan olarak, yalnızca ilk kısayol tuşu gösterilir. Bu işlev tüm komutları ile ilişkili tüm kısayol tuşlarının listelemenize olanak sağlar.

Kısayol tuşları, menü çubuğundaki komutu yanındaki listelenir. Tüm kısayol tuşlarının görüntüleniyorsa, dize sağlanan *lpszDelimiter* tek kısayol tuşları ayrılır.

##  <a name="translatechartoupper"></a>  CKeyboardManager::TranslateCharToUpper

Kendi üst kasaya bir karakteri dönüştürür.

```
static UINT TranslateCharToUpper(const UINT nChar);
```

### <a name="parameters"></a>Parametreler

*nChar*<br/>
[in] Dönüştürülecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Giriş parametresinin üst kaydıdır karakter.

##  <a name="updateacceltable"></a>  CKeyboardManager::UpdateAccelTable

Bir kısayol anahtar tablosu ile yeni bir kısayol anahtar tablosunu güncelleştirir.

```
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,
    LPACCEL lpAccel,
    int nSize,
    CFrameWnd* pDefaultFrame = NULL);

BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,
    HACCEL hAccelNew,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Parametreler

*pTemplate*<br/>
[in] Bir belge şablonu için bir işaretçi.

*lpAccel*<br/>
[in] Yeni kısayol tuşu işaretçisi.

*nSize*<br/>
[in] Yeni kısayol tablo boyutu.

*pDefaultFrame*<br/>
[in] Varsayılan çerçeve penceresi için bir işaretçi.

*hAccelNew*<br/>
[in] Yeni kısayol tablo için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Mevcut kısayol tablo çeşitli çerçeve pencere nesneleri için yeni kısayol tuşlarını değiştirmek için bu işlevi kullanın. İşlev bir belge şablonu belirli bir belge şablonuna bağlı tüm çerçeve penceresi nesnelere erişim elde etmek için bir parametre olarak alır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)<br/>
[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)<br/>
[Klavye ve Fare Özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md)
