---
title: CKeyboardManager Sınıfı
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
ms.openlocfilehash: a8053ab33a2b49eb2c447cdaa1cb2b9e356bc696
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754919"
---
# <a name="ckeyboardmanager-class"></a>CKeyboardManager Sınıfı

Ana çerçeve penceresi ve alt çerçeve pencereleri için kısayol anahtar tablolarını yönetir.

## <a name="syntax"></a>Sözdizimi

```
class CKeyboardManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Bir `CKeyboardManager` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CKeyboardManager::Temizleme](#cleanup)|Kısayol anahtar tablolarını temizler.|
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Belirtilen komut ve pencere için varsayılan kısayol tuşunu alır.|
|[CKeyboardManager::Anahtar Ele](#iskeyhandled)|Bir anahtarın hızlandırıcı tablosu tarafından işlenip işlenmediğini belirler.|
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Bir karakterin yazdırılabilir olup olmadığını gösterir.|
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Menülerin bir komut için tüm kısayol anahtarlarını mı yoksa yalnızca varsayılan kısayol anahtarını mı gösterdiğini gösterir.|
|[CKeyboardManager::LoadState](#loadstate)|Kısayol anahtar tablolarını Windows kayıt defterinden yükler.|
|[CKeyboardManager::Tümleri Sıfırla](#resetall)|Kısayol anahtar tablolarını uygulama kaynağından yeniden yükler.|
|[CKeyboardManager::SaveState](#savestate)|Kısayol anahtar tablolarını Windows kayıt defterine kaydeder.|
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Çerçevenin tüm komutlar için tüm kısayol anahtarlarını mı yoksa her komut için tek bir kısayol tuşu mu görüntülediğini belirtir. Bu yöntem, yalnızca bir ilişkili kısayol anahtarı olan komutları etkilemez.|
|[CKeyboardManager::Translatechartoupper](#translatechartoupper)|Bir karakteri üst kaydına dönüştürür.|
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Kısayol anahtar tablosunu yeni bir kısayol anahtar tablosuyla güncelleştirir.|

## <a name="remarks"></a>Açıklamalar

Bu sınıfın üyeleri, kısayol anahtar tablolarını Windows kayıt defterine kaydetmenize ve yüklemenize, kısa yol anahtar tablolarını güncelleştirmek için şablon kullanmanıza ve çerçeve penceresindeki komut için varsayılan kısayol anahtarını bulmanıza olanak tanır. Buna ek `CKeyboardManager` olarak, nesne kısayol tuşlarının kullanıcıya nasıl görüntüleneceğini denetlemenize olanak tanır.

Bir `CKeyboardManager` nesneyi el ile oluşturmamalısınız. Uygulamanızın çerçevesi tarafından otomatik olarak oluşturulur. Ancak, uygulamanızın başlatma işlemi sırasında [CWinAppEx::InitKeyboardManager'ı](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) aramalısınız. Uygulamanız için klavye yöneticisine bir işaretçi almak için [CWinAppEx'i arayın::GetKeyboardManager.](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CKeyboardManager` `CWinAppEx` sınıftan bir nesneye işaretçi nasıl alındığını ve menü komutlarıyla ilişkili tüm kısayol tuşlarının nasıl gösterilebildiğini gösterir. Bu kod parçacığı Özel Sayfalar [örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ckeyboardmanager](../../mfc/reference/ckeyboardmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxkeyboardmanager.h

## <a name="ckeyboardmanagerckeyboardmanager"></a><a name="ckeyboardmanager"></a>CKeyboardManager::CKeyboardManager

Bir `CKeyboardManager` nesne inşa eder.

```
CKeyboardManager();
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, doğrudan bir `CKeyboardManager` oluşturmak zorunda değildir. Varsayılan olarak, çerçeve sizin için bir tane oluşturur. Bir işaretçi almak `CKeyboardManager` [için, CWinAppEx'i arayın::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). Eğer el ile bir oluşturmak yoksa, yöntem CWinAppEx ile başlatılması [gerekir::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).

## <a name="ckeyboardmanagercleanup"></a><a name="cleanup"></a>CKeyboardManager::Temizleme

`CKeyboardManager` Kaynakları boşaltTıran ve tüm kısayol anahtar eşlemelerini temizler.

```
static void CleanUp();
```

### <a name="remarks"></a>Açıklamalar

Kısayol tuşları hakkında daha fazla bilgi için [Klavye ve Fare Özelleştirme'ye](../../mfc/keyboard-and-mouse-customization.md)bakın.

Uygulama çıkışında çerçeve otomatik olarak aradığından, uygulamanız çıktığında bu işlevi aramanız gerekmez.

## <a name="ckeyboardmanagerfinddefaultaccelerator"></a><a name="finddefaultaccelerator"></a>CKeyboardManager::FindDefaultAccelerator

Belirtilen komut ve pencere için varsayılan kısayol tuşunu alır.

```
static BOOL FindDefaultAccelerator(
    UINT uiCmd,
    CString& str,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Komut kimliği.

*Str*<br/>
[çıkış] Bir `CString` nesneye başvuru.

*pWndFrame*<br/>
[içinde] Çerçeve penceresiiçin bir işaretçi.

*bIsDefaultFrame*<br/>
[içinde] Çerçeve penceresinin varsayılan çerçeve penceresi olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Kısayol bulunursa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem *uiCmd* tarafından belirtilen komutu arar ve varsayılan kısayol anahtarını alır. Daha sonra yöntem bu kısayol tuşu ile ilişkili dize alır ve *str* parametre değeri yazar.

## <a name="ckeyboardmanageriskeyhandled"></a><a name="iskeyhandled"></a>CKeyboardManager::Anahtar Ele

Belirtilen anahtarın [CKeyboardManager Sınıfı](../../mfc/reference/ckeyboardmanager-class.md)tarafından işlenip işlenmediğini belirler.

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
|*nAnahtar*|[içinde] Kontrol etmek için anahtar.|
|*fVirt*|[içinde] Kısayol anahtarının davranışını belirtir. Olası değerlerin listesi için [ACCEL Yapısı'na](/windows/win32/api/winuser/ns-winuser-accel)bakın.|
|*pWndFrame*|[içinde] Çerçeve penceresi. Bu yöntem, bu çerçevede bir kısayol anahtarının işlenip işlenmeyeceğini belirler.|
|*bIsDefaultFrame*|[içinde] *pWndFrame* varsayılan çerçeve penceresi olup olmadığını gösteren bir Boolean parametresi.|

### <a name="return-value"></a>Dönüş Değeri

Kısayol tuşu işlenirse DOĞRU. Anahtar işlenmezse veya *pWndFrame* NULL ise YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Giriş *parametreleri, pWndFrame'de*bir kısayol anahtarının işlenip işlenmediğini belirlemek için hem *nKey* hem de *fVirt* için hızlandırıcı tablosundaki girişle eşleşmelidir.

## <a name="ckeyboardmanageriskeyprintable"></a><a name="iskeyprintable"></a>CKeyboardManager::IsKeyPrintable

Bir karakterin yazdırılabilir olup olmadığını gösterir.

```
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*Nchar*|[içinde] Bu yöntemin denetledığı karakter.|

### <a name="return-value"></a>Dönüş Değeri

Karakter yazdırılabilirse sıfır, yazdırılamazsa sıfır.

### <a name="remarks"></a>Açıklamalar

[GetKeyboardState](/windows/win32/api/winuser/nf-winuser-getkeyboardstate) için bir çağrı başarısız olursa bu yöntem başarısız olur.

## <a name="ckeyboardmanagerisshowallaccelerators"></a><a name="isshowallaccelerators"></a>CKeyboardManager::IsShowAllAccelerators

Menülerin menü komutlarıyla ilişkili tüm kısayol tuşlarını mı yoksa yalnızca varsayılan kısayol tuşlarını mı gösterdiğini gösterir.

```
static BOOL IsShowAllAccelerators();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama menü komutları için tüm kısayol tuşlarını listelerse sıfır olmayan; Uygulama yalnızca varsayılan kısayol tuşlarını görüntülerse 0.

### <a name="remarks"></a>Açıklamalar

Uygulama, menü çubuğundaki menü komutları için kısayol tuşlarını listeler. Uygulamanın tüm kısayol tuşlarını mı yoksa yalnızca varsayılan kısayol tuşlarını mı listelediğini denetlemek için [CKeyboardManager::ShowAllAccelerators](#showallaccelerators) işlevini kullanın.

## <a name="ckeyboardmanagerloadstate"></a><a name="loadstate"></a>CKeyboardManager::LoadState

Kısayol anahtar tablolarını Windows kayıt defterinden yükler.

```
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Verilerin kaydedildiği `CKeyboardManager` kayıt defteri yolu.

*pDefaultFrame*<br/>
[içinde] Varsayılan pencere olarak kullanmak üzere çerçeve penceresine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Nonzero devlet başarıyla yüklenmişse veya 0 aksi takdirde.

### <a name="remarks"></a>Açıklamalar

*lpszProfileName* parametresi NULL ise, bu yöntem veri `CKeyboardManager` için varsayılan kayıt defteri konumunu denetler. Varsayılan kayıt defteri konumu [CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)tarafından belirtilir. Veriler daha önce CKeyboardManager yöntemi ile [yazılmalıdır::SaveState](#savestate).

Varsayılan pencere belirtmezseniz, uygulamanızın ana çerçeve penceresi kullanılır.

## <a name="ckeyboardmanagerresetall"></a><a name="resetall"></a>CKeyboardManager::Tümleri Sıfırla

Kısayol anahtar tablolarını uygulama kaynağından yeniden yükler.

```cpp
void ResetAll();
```

### <a name="remarks"></a>Açıklamalar

Bu `CKeyboardManager` işlev, örnekte depolanan kısayolları temizler. Daha sonra klavye yöneticisinin durumunu uygulama kaynağından yeniden yükler.

## <a name="ckeyboardmanagersavestate"></a><a name="savestate"></a>CKeyboardManager::SaveState

Kısayol anahtar tablolarını Windows kayıt defterine kaydeder.

```
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] `CKeyboardManager` Devleti kurtarmak için kayıt yolu.

*pDefaultFrame*<br/>
[içinde] Varsayılan pencere haline gelen bir çerçeve penceresi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Klavye yöneticisi durumu başarıyla kaydedildiyse sıfır veya 0 aksi takdirde.

### <a name="remarks"></a>Açıklamalar

*lpszProfileName* parametresi NULL ise, bu `CKeyboardManager` yöntem durumu [CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)tarafından belirtilen varsayılan konuma yazar. Bir konum belirtirseniz, verileri daha sonra [CKeyboardManager::LoadState](#loadstate)yöntemini kullanarak yükleyebilirsiniz.

Varsayılan pencere belirtmezseniz, ana çerçeve penceresi varsayılan pencere olarak kullanılır.

## <a name="ckeyboardmanagershowallaccelerators"></a><a name="showallaccelerators"></a>CKeyboardManager::ShowAllAccelerators

Menü komutlarıyla ilişkili tüm kısayol tuşlarını gösterir.

```
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```

### <a name="parameters"></a>Parametreler

*bShowAll*<br/>
[içinde] TRUE ise, tüm kısayol anahtarları görüntülenir. FALSE ise, yalnızca ilk kısayol tuşu görüntülenir.

*lpszDelimiter*<br/>
[içinde] Kısayol tuşları arasına eklenecek bir dize. Yalnızca bir kısayol tuşu görüntülenirse, bu sınır distiricinin hiçbir etkisi yoktur.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir komutun ilişkili birden fazla kısayol anahtarı varsa, yalnızca ilk kısayol tuşu gösterilir. Bu işlev, tüm komutlarla ilişkili tüm kısayol tuşlarını listeletmenizi sağlar.

Kısayol tuşları menü çubuğundaki komutun yanında listelenir. Tüm kısayol tuşları *görüntülenirse, lpszDelimiter* tarafından sağlanan dize tek tek kısayol tuşlarını ayırır.

## <a name="ckeyboardmanagertranslatechartoupper"></a><a name="translatechartoupper"></a>CKeyboardManager::Translatechartoupper

Bir karakteri üst kaydına dönüştürür.

```
static UINT TranslateCharToUpper(const UINT nChar);
```

### <a name="parameters"></a>Parametreler

*Nchar*<br/>
[içinde] Dönüştürülecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Giriş parametresinin üst kaydı olan karakter.

## <a name="ckeyboardmanagerupdateacceltable"></a><a name="updateacceltable"></a>CKeyboardManager::UpdateAccelTable

Kısayol anahtar tablosunu yeni bir kısayol anahtar tablosuyla güncelleştirir.

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
[içinde] Belge şablonuna işaretçi.

*lpAccel*<br/>
[içinde] Yeni kısayol anahtarıiçin bir işaretçi.

*nSize*<br/>
[içinde] Yeni kısayol tablosunun boyutu.

*pDefaultFrame*<br/>
[içinde] Varsayılan çerçeve penceresi için bir işaretçi.

*hAccelYeni*<br/>
[içinde] Yeni kısayol tablosuna bir tutamaç.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varolan kısayol tablosunu birkaç çerçeve penceresi nesnesi için yeni kısayol anahtarlarıyla değiştirmek için bu işlevi kullanın. İşlev, verilen belge şablonuna bağlı tüm çerçeve penceresi nesnelerine erişmek için parametre olarak bir belge şablonu alır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)<br/>
[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)<br/>
[Klavye ve Fare Özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md)
