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
ms.openlocfilehash: e67bbb18b6a87edfaa4bc4c410ec28eb613ed51d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841499"
---
# <a name="ckeyboardmanager-class"></a>CKeyboardManager sınıfı

Ana çerçeve penceresi ve alt çerçeve pencereleri için kısayol tuşu tablolarını yönetir.

## <a name="syntax"></a>Syntax

```
class CKeyboardManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|-|-|
|[CKeyboardManager:: CKeyboardManager](#ckeyboardmanager)|Bir `CKeyboardManager` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|-|-|
|[CKeyboardManager:: CleanUp](#cleanup)|Kısayol tuşu tablolarını temizler.|
|[CKeyboardManager:: FindDefaultAccelerator](#finddefaultaccelerator)|Belirtilen komut ve pencere için varsayılan kısayol tuşunu alır.|
|[CKeyboardManager:: ıskeyişlendi](#iskeyhandled)|Bir anahtarın Hızlandırıcı tablosu tarafından işlenip işlenmediğini belirler.|
|[CKeyboardManager:: IsKeyPrintable](#iskeyprintable)|Bir karakterin yazdırılabilir olup olmadığını gösterir.|
|[CKeyboardManager:: IsShowAllAccelerators](#isshowallaccelerators)|Menülerin bir komut için veya yalnızca varsayılan kısayol tuşu için tüm kısayol tuşlarını gösterip göstermediğini belirtir.|
|[CKeyboardManager:: LoadState](#loadstate)|Windows kayıt defterinden kısayol tuşu tablolarını yükler.|
|[CKeyboardManager:: ResetAll](#resetall)|Uygulama kaynağından kısayol tuşu tablolarını yeniden yükler.|
|[CKeyboardManager:: Savemlak](#savestate)|Kısayol tuşu tablolarını Windows kayıt defterine kaydeder.|
|[CKeyboardManager:: ShowAllAccelerators](#showallaccelerators)|Çerçevenin tüm komutlar için kısayol tuşlarını veya her komut için tek bir kısayol tuşunu görüntüleyip görüntülemediğini belirtir. Bu yöntem, yalnızca bir ilişkili kısayol tuşu olan komutları etkilemez.|
|[CKeyboardManager:: TranslateCharToUpper](#translatechartoupper)|Bir karakteri üst kaydına dönüştürür.|
|[CKeyboardManager:: UpdateAccelTable](#updateacceltable)|Kısayol tuşu tablosunu yeni bir kısayol tuşu tablosu ile güncelleştirir.|

## <a name="remarks"></a>Açıklamalar

Bu sınıfın üyeleri, kısayol tuşu tablolarını Windows kayıt defterine kaydedip yükleme, kısa kesme anahtar tablolarını güncelleştirmek için şablon kullanma ve bir komut için bir çerçeve penceresinde varsayılan kısayol tuşunu bulma imkanı sağlar. Ayrıca, `CKeyboardManager` nesnesi kısayol tuşlarının kullanıcıya nasıl görüntülendiğini denetlemenize olanak tanır.

`CKeyboardManager`El ile bir nesne oluşturmamalıdır. Bu, uygulamanızın çerçevesi tarafından otomatik olarak oluşturulur. Ancak, uygulamanızın başlatma işlemi sırasında [CWinAppEx:: InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) ' ı çağırmanız gerekir. Uygulamanıza yönelik klavye Yöneticisi işaretçisi almak için [CWinAppEx:: GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)çağırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir sınıftan bir nesnenin bir işaretçisinin nasıl alınacağını `CKeyboardManager` `CWinAppEx` ve menü komutlarıyla ilişkili tüm kısayol tuşlarının nasıl gösterileceğini gösterir. Bu kod parçacığı, [özel sayfalar örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxkeyboardmanager. h

## <a name="ckeyboardmanagerckeyboardmanager"></a><a name="ckeyboardmanager"></a> CKeyboardManager:: CKeyboardManager

Bir `CKeyboardManager` nesnesi oluşturur.

```
CKeyboardManager();
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, doğrudan oluşturmanız gerekmez `CKeyboardManager` . Varsayılan olarak, çerçeve sizin için bir tane oluşturur. ' A bir işaretçi almak için `CKeyboardManager` , [CWinAppEx:: GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)çağırın. El ile bir tane oluşturursanız, [CWinAppEx:: InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)yöntemiyle onu başlatmalısınız.

## <a name="ckeyboardmanagercleanup"></a><a name="cleanup"></a> CKeyboardManager:: CleanUp

Kaynakları serbest bırakır `CKeyboardManager` ve tüm kısayol tuşu eşlemelerini temizler.

```
static void CleanUp();
```

### <a name="remarks"></a>Açıklamalar

Kısayol tuşları hakkında daha fazla bilgi için bkz. [klavye ve fare özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md).

Uygulama çıkış sırasında çerçeve tarafından otomatik olarak çağrılamadığından, uygulamanız çıkarken bu işlevi çağırmanız gerekmez.

## <a name="ckeyboardmanagerfinddefaultaccelerator"></a><a name="finddefaultaccelerator"></a> CKeyboardManager:: FindDefaultAccelerator

Belirtilen komut ve pencere için varsayılan kısayol tuşunu alır.

```
static BOOL FindDefaultAccelerator(
    UINT uiCmd,
    CString& str,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Komut KIMLIĞI.

*üstbilgisine*<br/>
dışı Bir `CString` nesneye başvuru.

*pWndFrame*<br/>
'ndaki Çerçeve penceresi işaretçisi.

*bIsDefaultFrame*<br/>
'ndaki Çerçeve penceresinin varsayılan çerçeve penceresi olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Kısayol bulunursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *Uııcmd* tarafından belirtilen komutu arar ve varsayılan kısayol tuşunu alır. Sonra yöntemi bu kısayol tuşuyla ilişkili dizeyi alır ve değeri *Str* parametresine yazar.

## <a name="ckeyboardmanageriskeyhandled"></a><a name="iskeyhandled"></a> CKeyboardManager:: ıskeyişlendi

Belirtilen anahtarın [CKeyboardManager sınıfı](../../mfc/reference/ckeyboardmanager-class.md)tarafından işlenip işlenmediğini belirler.

```
static BOOL __stdcall IsKeyHandled(
    WORD nKey,
    BYTE fVirt,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>Parametreler

*nAnahtar*\
'ndaki Denetlenecek anahtar.

*fVirt*\
'ndaki Kısayol tuşunun davranışını belirtir. Olası değerler listesi için bkz. [Accel yapısı](/windows/win32/api/winuser/ns-winuser-accel).

*pWndFrame*\
'ndaki Bir çerçeve penceresi. Bu yöntem, bu çerçevede bir kısayol tuşunun işlenmiş olup olmadığını belirler.

*bIsDefaultFrame*\
'ndaki *PWndFrame* 'in varsayılan çerçeve penceresi olup olmadığını gösteren bir Boole parametresi.

### <a name="return-value"></a>Dönüş Değeri

Kısayol tuşu işlenirse TRUE. Anahtar işlenmezse veya *pWndFrame* null ise false.

### <a name="remarks"></a>Açıklamalar

Giriş parametrelerinin, *pWndFrame*'de bir kısayol tuşunun işlendiğini anlamak Için hem *nKey* hem de *fVirt* için Hızlandırıcı tablosundaki girişle eşleşmesi gerekir.

## <a name="ckeyboardmanageriskeyprintable"></a><a name="iskeyprintable"></a> CKeyboardManager:: IsKeyPrintable

Bir karakterin yazdırılabilir olup olmadığını gösterir.

```
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```

### <a name="parameters"></a>Parametreler

*nChar*\
'ndaki Bu yöntemin denetlediği karakter.

### <a name="return-value"></a>Dönüş Değeri

Karakter basışuysa sıfır dışında, değilse sıfırdır.

### <a name="remarks"></a>Açıklamalar

[GetKeyboardState](/windows/win32/api/winuser/nf-winuser-getkeyboardstate) çağrısı başarısız olursa bu yöntem başarısız olur.

## <a name="ckeyboardmanagerisshowallaccelerators"></a><a name="isshowallaccelerators"></a> CKeyboardManager:: IsShowAllAccelerators

Menülerin menü komutlarıyla veya yalnızca varsayılan kısayol tuşlarıyla ilişkili tüm kısayol tuşlarını gösterip göstermediğini belirtir.

```
static BOOL IsShowAllAccelerators();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama menü komutlarının tüm kısayol tuşlarını listelemese sıfır dışında; uygulama yalnızca varsayılan kısayol tuşlarını görüntülerse 0.

### <a name="remarks"></a>Açıklamalar

Uygulama menü çubuğundaki menü komutlarının kısayol tuşlarını listeler. Uygulamanın tüm kısayol tuşlarını mı yoksa yalnızca varsayılan kısayol tuşlarını mı listeetmediğini denetlemek için [CKeyboardManager:: ShowAllAccelerators](#showallaccelerators) işlevini kullanın.

## <a name="ckeyboardmanagerloadstate"></a><a name="loadstate"></a> CKeyboardManager:: LoadState

Windows kayıt defterinden kısayol tuşu tablolarını yükler.

```
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Verilerin kaydedildiği kayıt defteri yolu `CKeyboardManager` .

*pDefaultFrame*<br/>
'ndaki Bir çerçeve penceresinin varsayılan pencere olarak kullanılacak bir işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Durum başarıyla yüklenmişse veya 0 değilse sıfır dışında.

### <a name="remarks"></a>Açıklamalar

*LpszProfileName* parametresi null ise, bu yöntem veriler için varsayılan kayıt defteri konumunu denetler `CKeyboardManager` . Varsayılan kayıt defteri konumu [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)tarafından belirtilir. Verilerin daha önce [CKeyboardManager:: Savi](#savestate)yöntemiyle yazılması gerekir.

Varsayılan bir pencere belirtmezseniz, uygulamanızın ana çerçeve penceresi kullanılacaktır.

## <a name="ckeyboardmanagerresetall"></a><a name="resetall"></a> CKeyboardManager:: ResetAll

Uygulama kaynağından kısayol tuşu tablolarını yeniden yükler.

```cpp
void ResetAll();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, örnekte depolanan kısayolları temizler `CKeyboardManager` . Ardından, klavye yöneticisinin durumunu uygulama kaynağından yeniden yükler.

## <a name="ckeyboardmanagersavestate"></a><a name="savestate"></a> CKeyboardManager:: Savemlak

Kısayol tuşu tablolarını Windows kayıt defterine kaydeder.

```
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Durumu kaydetmek için kayıt defteri yolu `CKeyboardManager` .

*pDefaultFrame*<br/>
'ndaki Bir çerçeve penceresinin varsayılan pencere haline gelen bir işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Klavye Yöneticisi durumu başarıyla kaydedildiyse veya 0 değilse sıfır dışında.

### <a name="remarks"></a>Açıklamalar

*LpszProfileName* parametresi null ise, bu yöntem `CKeyboardManager` durumu [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)tarafından belirtilen varsayılan konuma yazar. Bir konum belirtirseniz, verileri daha sonra [CKeyboardManager:: LoadState](#loadstate)metodunu kullanarak yükleyebilirsiniz.

Varsayılan bir pencere belirtmezseniz, ana çerçeve penceresi varsayılan pencere olarak kullanılacaktır.

## <a name="ckeyboardmanagershowallaccelerators"></a><a name="showallaccelerators"></a> CKeyboardManager:: ShowAllAccelerators

Menü komutlarıyla ilişkili tüm kısayol tuşlarını gösterir.

```
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```

### <a name="parameters"></a>Parametreler

*bShowAll*<br/>
'ndaki TRUE ise, tüm kısayol tuşları görüntülenir. YANLıŞSA, yalnızca ilk kısayol tuşu görüntülenir.

*lpszDelimiter*<br/>
'ndaki Kısayol tuşları arasına eklenecek dize. Yalnızca bir kısayol tuşu görüntüleniyorsa, bu sınırlayıcıda hiçbir etkisi yoktur.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir komutta ilişkili birden fazla kısayol tuşu varsa, yalnızca ilk kısayol tuşu gösterilir. Bu işlev, tüm komutlarla ilişkili tüm kısayol tuşlarını listelemenize olanak sağlar.

Kısayol tuşları, menü çubuğundaki komutun yanında listelenecektir. Tüm kısayol tuşları görüntüleniyorsa, *lpszDelimiter* tarafından belirtilen dize ayrı kısayol tuşlarını ayırır.

## <a name="ckeyboardmanagertranslatechartoupper"></a><a name="translatechartoupper"></a> CKeyboardManager:: TranslateCharToUpper

Bir karakteri üst kaydına dönüştürür.

```
static UINT TranslateCharToUpper(const UINT nChar);
```

### <a name="parameters"></a>Parametreler

*nChar*<br/>
'ndaki Dönüştürülecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Giriş parametresinin üst kayıt olan karakter.

## <a name="ckeyboardmanagerupdateacceltable"></a><a name="updateacceltable"></a> CKeyboardManager:: UpdateAccelTable

Kısayol tuşu tablosunu yeni bir kısayol tuşu tablosu ile güncelleştirir.

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
'ndaki Belge şablonuna yönelik bir işaretçi.

*lpAccel*<br/>
'ndaki Yeni kısayol tuşuna yönelik bir işaretçi.

*nSize*<br/>
'ndaki Yeni kısayol tablosunun boyutu.

*pDefaultFrame*<br/>
'ndaki Varsayılan çerçeve penceresine yönelik bir işaretçi.

*Hacsenew*<br/>
'ndaki Yeni kısayol tablosuna yönelik bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Mevcut kısayol tablosunu çeşitli çerçeve penceresi nesneleri için yeni kısayol tuşlarıyla değiştirmek için bu işlevi kullanın. İşlevi, belirtilen belge şablonuna bağlı tüm çerçeve pencere nesnelerine erişim sağlamak için bir parametre olarak bir belge şablonu alır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)<br/>
[CWinAppEx:: InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)<br/>
[Klavye ve fare özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md)
