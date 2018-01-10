---
title: "CKeyboardManager sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "33"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7547887b4ad34ecbbea32516eaf76b6f4d1ab25d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ckeyboardmanager-class"></a>CKeyboardManager sınıfı
Kısayol tuş tablolar alt çerçeve pencereleri ve ana çerçeve penceresi için yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CKeyboardManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Oluşturan bir `CKeyboardManager` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CKeyboardManager::CleanUp](#cleanup)|Kısayol tuş tablolarını temizler.|  
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Belirtilen komut ve pencere için varsayılan kısayol tuşu alır.|  
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Bir anahtar Hızlandırıcı tablosu tarafından işlenip işlenmediğini belirler.|  
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Bir karakter yazdırılabilir olup olmadığını gösterir.|  
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Menüleri tüm kısayol tuşları için bir komut veya yalnızca varsayılan kısayol tuşu Göster olup olmadığını gösterir.|  
|[CKeyboardManager::LoadState](#loadstate)|Kısayol tuş tabloları Windows kayıt defterinden yükler.|  
|[CKeyboardManager::ResetAll](#resetall)|Uygulama kaynağı kısayol anahtar tablolardan yeniden yükler.|  
|[CKeyboardManager::SaveState](#savestate)|Kısayol tuş tabloları Windows kayıt defterine kaydeder.|  
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Framework tüm komutlar için tüm kısayol tuşları ya da her komut için tek bir kısayol tuşu görüntülenip görüntülenmeyeceğini belirtir. Bu yöntem yalnızca bir ilişkili kısayol tuşu sahip komutları etkilemez.|  
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|Bir karakter üst kasaya dönüştürür.|  
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Kısayol anahtar tablosunda yeni bir kısayol anahtar tablosu ile güncelleştirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf üyeleri, kaydetme ve kısayol Windows kayıt defteri anahtarı tablolara yüklemek, kısa kesme anahtar tabloları güncelleştirmek için bir şablon kullanın etkinleştirin ve varsayılan kısayol tuşu komutu için bir çerçeve penceresinde bulun. Ayrıca, `CKeyboardManager` nesne kısayol tuşları kullanıcıya görüntülenme biçimini denetlemenize olanak tanır.  
  
 Değil oluşturmalısınız bir `CKeyboardManager` el ile nesne. Uygulamanızı çerçevesi tarafından otomatik olarak yeniden oluşturulur. Ancak, çağırmalıdır [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) , uygulamanızın başlatma işlemi sırasında. Uygulamanız için klavye Yöneticisi bir işaretçi almak için arama [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir işaretçi almak nasıl gösteren bir `CKeyboardManager` nesnesinin bir `CWinAppEx` sınıfı ve menü komutlarını ile ilişkili tüm kısayol tuşları göstermek nasıl. Bu kod parçacığını parçası olan [özel sayfaları örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxkeyboardmanager.h  
  
##  <a name="ckeyboardmanager"></a>CKeyboardManager::CKeyboardManager  
 Oluşturan bir `CKeyboardManager` nesnesi.  
  
```  
CKeyboardManager();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çoğu durumda, oluşturmanız gerekmez bir `CKeyboardManager` doğrudan. Varsayılan olarak, sizin için bir çerçeve oluşturur. Bir işaretçi almak için `CKeyboardManager`, çağrı [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). Biri el ile oluşturursanız, yöntemiyle başlatmalıdır [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).  
  
##  <a name="cleanup"></a>CKeyboardManager::CleanUp  
 Serbest bırakma `CKeyboardManager` kaynakları ve tüm kısayol tuş eşlemeleri temizler.  
  
```  
static void CleanUp();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kısayol tuşları hakkında daha fazla bilgi için bkz: [klavye ve fare özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md).  
  
 Framework otomatik uygulama çıkış sırasında çağırır çünkü uygulamanız çıktığında bu işlevi çağırmak gerekmez.  
  
##  <a name="finddefaultaccelerator"></a>CKeyboardManager::FindDefaultAccelerator  
 Belirtilen komut ve pencere için varsayılan kısayol tuşu alır.  
  
```  
static BOOL FindDefaultAccelerator(
    UINT uiCmd,  
    CString& str,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiCmd`  
 Komut kimliği.  
  
 [out]`str`  
 Bir başvuru bir `CString` nesnesi.  
  
 [in]`pWndFrame`  
 Çerçeve penceresi için bir işaretçi.  
  
 [in]`bIsDefaultFrame`  
 Çerçeve penceresi varsayılan çerçeve penceresi olup olmadığını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kısayol bulunursa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından belirtilen komut arar `uiCmd` ve varsayılan kısayol tuşu alır. Yöntemi bu kısayol tuşu ile ilişkili dizeyi alır ve değerine yazar sonra `str` parametresi.  
  
##  <a name="iskeyhandled"></a>CKeyboardManager::IsKeyHandled  
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
|[in]`nKey`|Denetlenecek anahtarı.|  
|[in]`fVirt`|Kısayol tuşu davranışını belirtir. Olası değerler listesi için bkz: [HIZLANDIRMA yapısı](http://msdn.microsoft.com/library/windows/desktop/ms646340).|  
|[in]`pWndFrame`|Çerçeve penceresi. Bu yöntem, bir kısayol tuşu Bu çerçevede işlenip işlenmediğini belirler.|  
|[in]`bIsDefaultFrame`|Gösteren bir Boolean parametresiyle olup olmadığını `pWndFrame` varsayılan çerçeve penceresi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`kısayol tuşu işleniyorsa. `FALSE`anahtar işlenmiyor veya gerekiyorsa `pWndFrame` olan `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Giriş parametreleri Hızlandırıcı tablosunda her iki giriş eşleşmelidir `nKey` ve `fVirt` bir kısayol tuşu içinde işlenir olup olmadığını belirlemek için `pWndFrame`.  
  
##  <a name="iskeyprintable"></a>CKeyboardManager::IsKeyPrintable  
 Bir karakter yazdırılabilir olup olmadığını gösterir.  
  
```  
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`nChar`|Bu yöntem denetler karakter.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan karakter yazdırılabilir ise sıfır değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem çağrısı başarısız olur [GetKeyboardState](http://msdn.microsoft.com/library/windows/desktop/ms646299) başarısız olur.  
  
##  <a name="isshowallaccelerators"></a>CKeyboardManager::IsShowAllAccelerators  
 Menüleri menü komutları ile ilişkili tüm kısayol tuşları veya yalnızca varsayılan kısayol tuşları görüntüleme olup olmadığını gösterir.  
  
```  
static BOOL IsShowAllAccelerators();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulama menü komutları tüm kısayol tuşları listeleniyorsa sıfır olmayan; 0 uygulama yalnızca varsayılan kısayol tuşları görüntüler.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama menü komutlarını menü çubuğunda kısayol tuşları listeler. İşlevini [CKeyboardManager::ShowAllAccelerators](#showallaccelerators) denetlemek için mi uygulama listeler tüm kısayol tuşları veya yalnızca varsayılan kısayol tuşları.  
  
##  <a name="loadstate"></a>CKeyboardManager::LoadState  
 Kısayol tuş tabloları Windows kayıt defterinden yükler.  
  
```  
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszProfileName`  
 Kayıt defteri yolunu burada `CKeyboardManager` verileri kaydedilir.  
  
 [in]`pDefaultFrame`  
 Varsayılan pencere olarak kullanmak için bir çerçeve penceresi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durum Aksi halde başarıyla yüklenmedi veya 0 ise, sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `lpszProfileName` parametresi `NULL`, bu yöntem varsayılan kayıt defteri konumu denetler `CKeyboardManager` veri. Varsayılan kayıt defteri konumu tarafından belirtilen [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md). Verileri önceden yöntemiyle yazılmalıdır [CKeyboardManager::SaveState](#savestate).  
  
 Varsayılan pencere belirtmezseniz, uygulamanızın ana çerçeve penceresi kullanılır.  
  
##  <a name="resetall"></a>CKeyboardManager::ResetAll  
 Uygulama kaynağı kısayol anahtar tablolardan yeniden yükler.  
  
```  
void ResetAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev depolanan kısayolları temizler `CKeyboardManager` örneği. Ardından klavye Yöneticisi'nden Uygulama kaynağı durumunu yeniden yükleyecektir.  
  
##  <a name="savestate"></a>CKeyboardManager::SaveState  
 Kısayol tuş tabloları Windows kayıt defterine kaydeder.  
  
```  
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszProfileName`  
 Kaydetmek için kayıt defteri yolu `CKeyboardManager` durumu.  
  
 [in]`pDefaultFrame`  
 Varsayılan pencere olur bir çerçeve penceresi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Klavye Yöneticisi durumu başarıyla kaydettiyseniz sıfır olmayan ya da aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `lpszProfileName` parametresi `NULL`, bu yöntem yazacak `CKeyboardManager` tarafından belirtilen varsayılan konuma durum [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md). Bir konum belirtirseniz, daha sonra yöntemini kullanarak verileri yükleyebilir [CKeyboardManager::LoadState](#loadstate).  
  
 Varsayılan pencere belirtmezseniz, ana çerçeve penceresi varsayılan pencere olarak kullanılır.  
  
##  <a name="showallaccelerators"></a>CKeyboardManager::ShowAllAccelerators  
 Menü komutları ile ilişkili tüm kısayol tuşları gösterir.  
  
```  
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,  
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bShowAll`  
 Varsa `true`, tüm kısayol tuşları görüntülenir. Varsa `false`, yalnızca ilk kısayol tuşu görüntülenir.  
  
 [in]`lpszDelimiter`  
 Kısayol tuşları arasında eklemek için bir dize. Bir kısayol tuşu görüntülenen yalnızca bu sınırlayıcı bir etkisi yoktur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir komut ile ilişkili birden fazla kısayol tuşu varsa, varsayılan olarak, yalnızca ilk kısayol tuşu gösterilir. Bu işlev, tüm komutları ile ilişkili tüm kısayol tuşlarının listesini sağlar.  
  
 Kısayol tuşları, menü çubuğundaki komutu yanındaki listelenir. Tüm kısayol tuşları görüntüleniyorsa, dize tarafından sağlanan `lpszDelimiter` tek tek kısayol tuşları ayırın.  
  
##  <a name="translatechartoupper"></a>CKeyboardManager::TranslateCharToUpper  
 Bir karakter üst kasaya dönüştürür.  
  
```  
static UINT TranslateCharToUpper(const UINT nChar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nChar`  
 Dönüştürülecek karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Giriş parametresinin üst kaydıdır karakter.  
  
##  <a name="updateacceltable"></a>CKeyboardManager::UpdateAccelTable  
 Kısayol anahtar tablosunda yeni bir kısayol anahtar tablosu ile güncelleştirir.  
  
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
 [in]`pTemplate`  
 Belge şablonu için bir işaretçi.  
  
 [in]`lpAccel`  
 Yeni kısayol tuşu gösteren bir işaretçi.  
  
 [in]`nSize`  
 Yeni bir kısayol tablo boyutu.  
  
 [in]`pDefaultFrame`  
 Varsayılan çerçeve penceresi için bir işaretçi.  
  
 [in]`hAccelNew`  
 Yeni bir kısayol tablo için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Birkaç çerçeve pencere nesneleri için yeni kısayol anahtarlarla varolan kısayol tabloyu değiştirmek için bu işlevi kullanın. İşlevi bir belge şablonu verilen belgedeki şablona bağlı tüm çerçeve pencere nesneleri erişim sağlamak için bir parametre olarak alır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)   
 [Klavye ve Fare Özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md)



