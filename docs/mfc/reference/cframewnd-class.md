---
title: CFrameWnd sınıfı
ms.date: 11/04/2016
f1_keywords:
- CFrameWnd
- AFXWIN/CFrameWnd
- AFXWIN/CFrameWnd::CFrameWnd
- AFXWIN/CFrameWnd::ActivateFrame
- AFXWIN/CFrameWnd::BeginModalState
- AFXWIN/CFrameWnd::Create
- AFXWIN/CFrameWnd::CreateView
- AFXWIN/CFrameWnd::DockControlBar
- AFXWIN/CFrameWnd::EnableDocking
- AFXWIN/CFrameWnd::EndModalState
- AFXWIN/CFrameWnd::FloatControlBar
- AFXWIN/CFrameWnd::GetActiveDocument
- AFXWIN/CFrameWnd::GetActiveFrame
- AFXWIN/CFrameWnd::GetActiveView
- AFXWIN/CFrameWnd::GetControlBar
- AFXWIN/CFrameWnd::GetDockState
- AFXWIN/CFrameWnd::GetMenuBarState
- AFXWIN/CFrameWnd::GetMenuBarVisibility
- AFXWIN/CFrameWnd::GetMessageBar
- AFXWIN/CFrameWnd::GetMessageString
- AFXWIN/CFrameWnd::GetTitle
- AFXWIN/CFrameWnd::InitialUpdateFrame
- AFXWIN/CFrameWnd::InModalState
- AFXWIN/CFrameWnd::IsTracking
- AFXWIN/CFrameWnd::LoadAccelTable
- AFXWIN/CFrameWnd::LoadBarState
- AFXWIN/CFrameWnd::LoadFrame
- AFXWIN/CFrameWnd::NegotiateBorderSpace
- AFXWIN/CFrameWnd::OnBarCheck
- AFXWIN/CFrameWnd::OnContextHelp
- AFXWIN/CFrameWnd::OnSetPreviewMode
- AFXWIN/CFrameWnd::OnUpdateControlBarMenu
- AFXWIN/CFrameWnd::RecalcLayout
- AFXWIN/CFrameWnd::SaveBarState
- AFXWIN/CFrameWnd::SetActivePreviewView
- AFXWIN/CFrameWnd::SetActiveView
- AFXWIN/CFrameWnd::SetDockState
- AFXWIN/CFrameWnd::SetMenuBarState
- AFXWIN/CFrameWnd::SetMenuBarVisibility
- AFXWIN/CFrameWnd::SetMessageText
- AFXWIN/CFrameWnd::SetProgressBarPosition
- AFXWIN/CFrameWnd::SetProgressBarRange
- AFXWIN/CFrameWnd::SetProgressBarState
- AFXWIN/CFrameWnd::SetTaskbarOverlayIcon
- AFXWIN/CFrameWnd::SetTitle
- AFXWIN/CFrameWnd::ShowControlBar
- AFXWIN/CFrameWnd::ShowOwnedWindows
- AFXWIN/CFrameWnd::OnCreateClient
- AFXWIN/CFrameWnd::OnHideMenuBar
- AFXWIN/CFrameWnd::OnShowMenuBar
- AFXWIN/CFrameWnd::m_bAutoMenuEnable
- AFXWIN/CFrameWnd::rectDefault
helpviewer_keywords:
- CFrameWnd [MFC], CFrameWnd
- CFrameWnd [MFC], ActivateFrame
- CFrameWnd [MFC], BeginModalState
- CFrameWnd [MFC], Create
- CFrameWnd [MFC], CreateView
- CFrameWnd [MFC], DockControlBar
- CFrameWnd [MFC], EnableDocking
- CFrameWnd [MFC], EndModalState
- CFrameWnd [MFC], FloatControlBar
- CFrameWnd [MFC], GetActiveDocument
- CFrameWnd [MFC], GetActiveFrame
- CFrameWnd [MFC], GetActiveView
- CFrameWnd [MFC], GetControlBar
- CFrameWnd [MFC], GetDockState
- CFrameWnd [MFC], GetMenuBarState
- CFrameWnd [MFC], GetMenuBarVisibility
- CFrameWnd [MFC], GetMessageBar
- CFrameWnd [MFC], GetMessageString
- CFrameWnd [MFC], GetTitle
- CFrameWnd [MFC], InitialUpdateFrame
- CFrameWnd [MFC], InModalState
- CFrameWnd [MFC], IsTracking
- CFrameWnd [MFC], LoadAccelTable
- CFrameWnd [MFC], LoadBarState
- CFrameWnd [MFC], LoadFrame
- CFrameWnd [MFC], NegotiateBorderSpace
- CFrameWnd [MFC], OnBarCheck
- CFrameWnd [MFC], OnContextHelp
- CFrameWnd [MFC], OnSetPreviewMode
- CFrameWnd [MFC], OnUpdateControlBarMenu
- CFrameWnd [MFC], RecalcLayout
- CFrameWnd [MFC], SaveBarState
- CFrameWnd [MFC], SetActivePreviewView
- CFrameWnd [MFC], SetActiveView
- CFrameWnd [MFC], SetDockState
- CFrameWnd [MFC], SetMenuBarState
- CFrameWnd [MFC], SetMenuBarVisibility
- CFrameWnd [MFC], SetMessageText
- CFrameWnd [MFC], SetProgressBarPosition
- CFrameWnd [MFC], SetProgressBarRange
- CFrameWnd [MFC], SetProgressBarState
- CFrameWnd [MFC], SetTaskbarOverlayIcon
- CFrameWnd [MFC], SetTitle
- CFrameWnd [MFC], ShowControlBar
- CFrameWnd [MFC], ShowOwnedWindows
- CFrameWnd [MFC], OnCreateClient
- CFrameWnd [MFC], OnHideMenuBar
- CFrameWnd [MFC], OnShowMenuBar
- CFrameWnd [MFC], m_bAutoMenuEnable
- CFrameWnd [MFC], rectDefault
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
ms.openlocfilehash: 5e40f08447d24eed51588b5c2dfa87e289d99eed
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561585"
---
# <a name="cframewnd-class"></a>CFrameWnd sınıfı

Windows tek belge arabirimi (SDI) örtüşen veya açılan çerçeve penceresinin, pencereyi yönetmek için üyelerle birlikte işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CFrameWnd : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFrameWnd:: CFrameWnd](#cframewnd)|Bir `CFrameWnd` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFrameWnd:: ActivateFrame](#activateframe)|Çerçeveyi görünür ve Kullanıcı tarafından kullanılabilir hale getirir.|
|[CFrameWnd:: BeginModalState](#beginmodalstate)|Çerçeve penceresini kalıcı olarak ayarlar.|
|[CFrameWnd:: Create](#create)|Nesnesiyle ilişkili Windows çerçeve penceresini oluşturmak ve başlatmak için çağırın `CFrameWnd` .|
|[CFrameWnd:: CreateView](#createview)|Bir çerçeve içinde türetilmeyen bir görünüm oluşturur `CView` .|
|[CFrameWnd::D ockControlBar](#dockcontrolbar)|Denetim çubuğunu kontrol edin.|
|[CFrameWnd:: EnableDocking](#enabledocking)|Denetim çubuğunun yerleştirilmiş olmasını sağlar.|
|[CFrameWnd:: EndModalState](#endmodalstate)|Çerçeve penceresinin kalıcı durumunu sonlandırır. Tarafından devre dışı bırakılan tüm pencereleri izin vermez `BeginModalState` .|
|[CFrameWnd:: FloatControlBar](#floatcontrolbar)|Bir denetim çubuğunu float.|
|[CFrameWnd:: GetActiveDocument](#getactivedocument)|Etkin nesneyi döndürür `CDocument` .|
|[CFrameWnd:: GetActiveFrame](#getactiveframe)|Etkin nesneyi döndürür `CFrameWnd` .|
|[CFrameWnd:: GetActiveView](#getactiveview)|Etkin nesneyi döndürür `CView` .|
|[CFrameWnd:: GetControlBar](#getcontrolbar)|Denetim çubuğunu alır.|
|[CFrameWnd:: GetDockState](#getdockstate)|Bir çerçeve penceresinin yerleştirme durumunu alır.|
|[CFrameWnd:: GetMenuBarState](#getmenubarstate)|Geçerli MFC uygulamasındaki menünün görüntüleme durumunu alır.|
|[CFrameWnd:: GetMenuBarVisibility](#getmenubarvisibility)|Geçerli MFC uygulamasındaki menünün varsayılan davranışının gizli ya da görünür olup olmadığını gösterir.|
|[CFrameWnd:: GetMessageBar](#getmessagebar)|Çerçeve penceresine ait olan durum çubuğuna bir işaretçi döndürür.|
|[CFrameWnd:: GetMessageString](#getmessagestring)|Komut KIMLIĞINE karşılık gelen iletiyi alır.|
|[CFrameWnd:: GetTitle](#gettitle)|İlgili denetim çubuğunun başlığını alır.|
|[CFrameWnd:: ınitialupdateframe](#initialupdateframe)|`OnInitialUpdate`Çerçeve penceresindeki tüm görünümlere ait üye işlevinin çağrılmasına neden olur.|
|[CFrameWnd:: InModalState](#inmodalstate)|Bir çerçeve penceresinin kalıcı durumda olup olmadığını gösteren bir değer döndürür.|
|[CFrameWnd:: IsTracking](#istracking)|Ayırıcı çubuğun Şu anda taşınıp taşınmadığını belirler.|
|[CFrameWnd:: LoadAccelTable](#loadacceltable)|Hızlandırıcı tablosu yükleme çağrısı.|
|[CFrameWnd:: LoadBarState](#loadbarstate)|Denetim çubuğu ayarlarını geri yükleme çağrısı.|
|[CFrameWnd:: LoadFrame](#loadframe)|Kaynak bilgilerden dinamik olarak bir çerçeve penceresi oluşturmak için çağırın.|
|[CFrameWnd:: NegotiateBorderSpace](#negotiateborderspace)|Çerçeve penceresinde kenarlık alanı üzerinde anlaşır.|
|[CFrameWnd:: OnBarCheck](#onbarcheck)|Belirtilen denetim çubuğunda bir eylem yapıldığında çağırılır.|
|[CFrameWnd:: OnContextHelp](#oncontexthelp)|Yerinde öğeler için SHIFT + F1 yardımını işler.|
|[CFrameWnd:: Onsetönizleme modu](#onsetpreviewmode)|Uygulamanın ana çerçeve penceresini baskı önizleme modundan ve dışına ayarlar.|
|[CFrameWnd:: OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|İlişkili menü güncelleştirildiği zaman Framework tarafından çağırılır.|
|[CFrameWnd:: RecalcLayout](#recalclayout)|Nesnenin denetim çubuklarını konumlandırır `CFrameWnd` .|
|[CFrameWnd:: SaveBarState](#savebarstate)|Denetim çubuğu ayarlarını kaydetme çağrısı.|
|[CFrameWnd:: Setactiveönizleme görünümü](#setactivepreviewview)|Belirtilen görünümü zengin önizleme için etkin görünüm olarak belirler.|
|[CFrameWnd:: SetActiveView](#setactiveview)|Etkin nesneyi ayarlar `CView` .|
|[CFrameWnd:: SetDockState](#setdockstate)|Ana pencereye çerçeve penceresini yerleştirmek için çağırın.|
|[CFrameWnd:: SetMenuBarState](#setmenubarstate)|Geçerli MFC uygulamasındaki menünün görüntüleme durumunu gizli veya görüntülenir olarak ayarlar.|
|[CFrameWnd:: SetMenuBarVisibility](#setmenubarvisibility)|Geçerli MFC uygulamasındaki menünün varsayılan davranışını gizli ya da görünür olacak şekilde ayarlar.|
|[CFrameWnd:: SetMessageText](#setmessagetext)|Standart durum çubuğunun metnini ayarlar.|
|[CFrameWnd:: SetProgressBarPosition](#setprogressbarposition)|Görev çubuğunda görüntülenmek üzere Windows 7 ilerleme çubuğunun geçerli konumunu ayarlar.|
|[CFrameWnd:: SetProgressBarRange](#setprogressbarrange)|Görev çubuğunda görüntülenmek üzere Windows 7 ilerleme çubuğu aralığını ayarlar.|
|[CFrameWnd:: SetProgressBarState](#setprogressbarstate)|Bir görev çubuğu düğmesinde görünen ilerleme göstergesinin türünü ve durumunu ayarlar.|
|[CFrameWnd:: Settaskbaroverlayıcon](#settaskbaroverlayicon)|Fazla Yüklendi. Uygulama durumunu veya kullanıcıya yönelik bir bildirimi göstermek için bir görev çubuğu düğmesine bir kaplama uygular.|
|[CFrameWnd:: SetTitle](#settitle)|İlgili denetim çubuğunun başlığını ayarlar.|
|[CFrameWnd:: ShowControlBar](#showcontrolbar)|Denetim çubuğunu göstermek için çağırın.|
|[CFrameWnd:: ShowOwnedWindows](#showownedwindows)|Nesnenin alt öğesi olan tüm pencereleri gösterir `CFrameWnd` .|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFrameWnd:: OnCreateClient](#oncreateclient)|Çerçeve için bir istemci penceresi oluşturur.|
|[CFrameWnd:: OnHideMenuBar](#onhidemenubar)|Geçerli MFC uygulamasındaki menü gizlenmadan önce çağırılır.|
|[CFrameWnd:: OnShowMenuBar](#onshowmenubar)|Geçerli MFC uygulamasındaki menü görüntülenmeden önce çağırılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFrameWnd:: m_bAutoMenuEnable](#m_bautomenuenable)|Menü öğeleri için otomatik etkinleştirme ve devre dışı bırakma işlevlerini denetler.|
|[CFrameWnd:: rectDefault](#rectdefault)|`CRect` `CFrameWnd` Windows 'un ilk boyutunu ve konumunu seçmesini sağlamak için bir nesne oluştururken bu statik olarak bir parametre olarak geçirin.|

## <a name="remarks"></a>Açıklamalar

Uygulamanız için kullanışlı bir çerçeve penceresi oluşturmak için, öğesinden bir sınıf türetebilirsiniz `CFrameWnd` . Uygulamanıza özgü verileri depolamak için türetilmiş sınıfa üye değişkenleri ekleyin. İletileri pencereye yönlendirdiğinde ne olacağını belirtmek için ileti işleyicisi üye işlevlerini ve türetilmiş sınıfta bir ileti eşlemesi uygulayın.

Çerçeve penceresi oluşturmak için üç yol vardır:

- Oluşturmayı kullanarak doğrudan [oluşturun](#create).

- [LoadFrame](#loadframe)kullanarak doğrudan oluşturun.

- Bir belge şablonu kullanarak dolaylı olarak oluşturun.

Ya da çağrısından önce `Create` `LoadFrame` , C++ işlecini kullanarak yığında kare pencere nesnesi oluşturmanız gerekir **`new`** . `Create`' İ çağırmadan önce, çerçeveye ait simge ve sınıf stillerini ayarlamak Için [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) genel işleviyle bir pencere sınıfı kaydedebilirsiniz.

`Create`Çerçevenin oluşturma parametrelerini hemen bağımsız değişken olarak geçirmek için üye işlevini kullanın.

`LoadFrame` öğesinden daha az bağımsız değişken gerektirir `Create` ve bunun yerine çerçevenin başlık, simge, Hızlandırıcı tablosu ve menü dahil olmak üzere kaynaklardaki varsayılan değerlerinin çoğunu alır. Tarafından erişilebilmesi için `LoadFrame` , tüm bu kaynakların aynı kaynak kimliğine sahip olması gerekir (örneğin, IDR_MAINFRAME).

Bir `CFrameWnd` nesne görünümler ve belgeler içerdiğinde, doğrudan programcı tarafından değil Framework tarafından dolaylı olarak oluşturulur. `CDocTemplate`Nesnesi çerçevenin oluşturulmasını, kapsayan görünümlerin oluşturulmasını ve görünümlerin ilgili belge ile bağlantısını düzenler. Oluşturucunun parametreleri, `CDocTemplate` `CRuntimeClass` içerilen üç sınıfın (belge, çerçeve ve Görünüm) sayısını belirtir. Bir `CRuntimeClass` nesne, Kullanıcı tarafından belirtildiğinde (örneğin, dosya yeni komut veya birden çok belge arabirimi (MDI) pencereyi yeni komut), yeni çerçeveleri dinamik olarak oluşturmak için çerçevesi tarafından kullanılır.

`CFrameWnd`Yukarıdaki RUNTIME_CLASS mekanizmanın doğru çalışması için öğesinden türetilmiş bir çerçeve pencere sınıfı DECLARE_DYNCREATE bildirilmelidir.

`CFrameWnd`, Windows için tipik bir uygulamada bir ana pencerenin aşağıdaki işlevlerini gerçekleştirmek üzere varsayılan uygulamaları içerir:

- Bir `CFrameWnd` çerçeve penceresi, Windows etkin penceresinden veya geçerli giriş odağından bağımsız olan şu anda etkin olan görünümü izler. Çerçeve yeniden etkinleştirildiğinde, etkin görünüme çağırarak bildirim gönderilir `CView::OnActivateView` .

- Komut iletileri ve,, ve işlevleri tarafından işlenenler dahil olmak üzere birçok yaygın çerçeve bildirimi iletisi, `OnSetFocus` `OnHScroll` `OnVScroll` `CWnd` `CFrameWnd` Şu anda etkin olan görünüm için bir çerçeve penceresi tarafından temsil edilir.

- Şu anda etkin olan görünüm (ya da bir MDI çerçevesi durumunda etkin olan MDI alt çerçeve penceresi), çerçeve penceresinin açıklamalı alt yazısını tespit edebilir. Bu özellik, çerçeve penceresinin FWS_ADDTOTITLE stil bitini kapatarak devre dışı bırakılabilir.

- Çerçeve penceresi, `CFrameWnd` çerçeve penceresinin istemci alanının içindeki denetim çubuklarının, görünümlerin ve diğer alt pencerelerin konumlandırılmasını yönetir. Çerçeve penceresi ayrıca araç çubuğunun ve diğer denetim çubuğu düğmelerinin boşta zamanlı güncelleştirilmesini de yapar. `CFrameWnd`Çerçeve penceresi ayrıca araç çubuğu ve durum çubuğu üzerinde geçiş yapmak ve kapatmak için varsayılan komut uygulamalarına sahiptir.

- Bir `CFrameWnd` çerçeve penceresi, ana menü çubuğunu yönetir. Bir açılır menü görüntülendiğinde, çerçeve penceresi hangi menü öğelerinin etkinleştirileceğini, devre dışı bırakılacağını veya denetleneceğini öğrenmek için UPDATE_COMMAND_UI mekanizmasını kullanır. Kullanıcı bir menü öğesi seçtiğinde, çerçeve penceresi durum çubuğunu ilgili komutun ileti dizesiyle güncelleştirir.

- Bir `CFrameWnd` çerçeve penceresi, klavye hızlandırıcılarını otomatik olarak çeviren isteğe bağlı bir Hızlandırıcı tablosuna sahiptir.

- `CFrameWnd`Çerçeve penceresinde, `LoadFrame` bağlama duyarlı yardım için kullanılan isteğe bağlı BIR Yardım kimliği kümesi vardır. Çerçeve penceresi, bağlama duyarlı Yardım (SHIFT + F1) ve baskı önizleme modları gibi semimodal durumlarının ana Orchestrator.

- Bir `CFrameWnd` çerçeve penceresi dosya yöneticisinden sürüklenen ve çerçeve penceresinde bırakılan bir dosyayı açar. Bir dosya uzantısı kayıtlı ve uygulamayla ilişkiliyse, çerçeve penceresi Kullanıcı dosya yöneticisinde bir veri dosyası açtığında veya Windows işlevi çağrıldığında gerçekleşen dinamik veri değişimi (DDE) açık isteğine yanıt verir `ShellExecute` .

- Çerçeve penceresi ana uygulama penceresuyorsa (yani `CWinThread::m_pMainWnd` ), Kullanıcı uygulamayı kapattığında çerçeve penceresi kullanıcıdan değiştirilen tüm belgeleri kaydetmesini ister ( `OnClose` ve için `OnQueryEndSession` ).

- Çerçeve penceresi ana uygulama penceresuyorsa, çerçeve penceresi WinHelp 'yi çalıştırmaya yönelik bağlamdır. Çerçeve penceresinin kapatılması, bu uygulama için yardım başlatıldığında WINHELP.EXE kapanır.

**`delete`** Bir çerçeve penceresini yok etmek Için C++ işlecini kullanmayın. Bunun yerine `CWnd::DestroyWindow` kullanın. Uygulamasının `CFrameWnd` uygulanması, `PostNcDestroy` pencere yok edildiğinde C++ nesnesini silecektir. Kullanıcı çerçeve penceresini kapattığında, varsayılan `OnClose` işleyici çağırır `DestroyWindow` .

Hakkında daha fazla bilgi için `CFrameWnd` bkz. [çerçeve pencereleri](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cframewndactivateframe"></a><a name="activateframe"></a> CFrameWnd:: ActivateFrame

Görünür ve Kullanıcı tarafından kullanılabilir olması için çerçeve penceresini etkinleştirmek ve geri yüklemek için bu üye işlevi çağırın.

```
virtual void ActivateFrame(int nCmdShow = -1);
```

### <a name="parameters"></a>Parametreler

*nCmdShow*<br/>
[CWnd:: ShowWindow](../../mfc/reference/cwnd-class.md#showwindow)'a geçirilecek parametreyi belirtir. Varsayılan olarak, çerçeve gösterilir ve doğru şekilde geri yüklenir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev genellikle bir DDE, OLE veya bir kullanıcı arabirimi gibi bir kullanıcı arabirimi olayından sonra, çerçeve penceresini veya içeriğini kullanıcıya gösteremeyen başka bir olay olarak çağrılır.

Varsayılan uygulama çerçeveyi etkinleştirir ve Z düzeninin en üstüne getirir ve gerekirse uygulamanın ana çerçeve penceresi için aynı adımları gerçekleştirir.

Çerçevenin nasıl etkinleştirildiğini değiştirmek için bu üye işlevini geçersiz kılın. Örneğin, MDI alt pencerelerini ekranı kaplayacak şekilde zorlayabilirsiniz. Uygun işlevi ekleyin ve ardından bir açık *nCmdShow*ile temel sınıf sürümünü çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]

## <a name="cframewndbeginmodalstate"></a><a name="beginmodalstate"></a> CFrameWnd:: BeginModalState

Bir çerçeve penceresini kalıcı hale getirmek için bu üye işlevini çağırın.

```
virtual void BeginModalState();
```

## <a name="cframewndcframewnd"></a><a name="cframewnd"></a> CFrameWnd:: CFrameWnd

Bir `CFrameWnd` nesne oluşturur, ancak görünür çerçeve penceresini oluşturmaz.

```
CFrameWnd();
```

### <a name="remarks"></a>Açıklamalar

`Create`Görünür pencereyi oluşturmak için çağırın.

## <a name="cframewndcreate"></a><a name="create"></a> CFrameWnd:: Create

Nesnesiyle ilişkili Windows çerçeve penceresini oluşturmak ve başlatmak için çağırın `CFrameWnd` .

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle = WS_OVERLAPPEDWINDOW,
    const RECT& rect = rectDefault,
    CWnd* pParentWnd = NULL,
    LPCTSTR lpszMenuName = NULL,
    DWORD dwExStyle = 0,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>
Windows sınıfına ad veren null ile sonlandırılmış bir karakter dizesini işaret eder. Sınıf adı, `AfxRegisterWndClass` genel işlev veya Windows işlevi ile kaydedilmiş herhangi bir ad olabilir `RegisterClass` . NULL ise, önceden tanımlanmış varsayılan `CFrameWnd` öznitelikleri kullanır.

*lpszWindowName*<br/>
Pencere adını temsil eden, null ile sonlandırılmış bir karakter dizesini işaret eder. Başlık çubuğu için metin olarak kullanılır.

*dwStyle*<br/>
Pencere [stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) özniteliklerini belirtir. Başlık çubuğunun pencerede temsil edilen belge adını otomatik olarak görüntülemesini istiyorsanız FWS_ADDTOTITLE stilini ekleyin.

*Rect*<br/>
Pencerenin boyutunu ve konumunu belirtir. *RectDefault* değeri Windows 'un yeni pencerenin boyutunu ve konumunu belirlemesine izin verir.

*pParentWnd*<br/>
Bu çerçeve penceresinin üst penceresini belirtir. Bu parametre, üst düzey çerçeve pencereleri için NULL olmalıdır.

*lpszMenuName*<br/>
Pencereyle birlikte kullanılacak menü kaynağının adını tanımlar. Menüdeki bir dize yerine bir tamsayı KIMLIĞI varsa, MAKEINTRESOURCE kullanın. Bu parametre NULL olabilir.

*dwExStyle*<br/>
Pencere genişletilmiş [Stil](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) özniteliklerini belirtir.

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısına yönelik bir işaretçi belirtir. Bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CFrameWnd`İki adımda bir nesne oluşturun. İlk olarak, nesnesini oluşturan oluşturucuyu çağırın `CFrameWnd` ve sonra `Create` Windows çerçeve penceresini oluşturan ve bunu nesnesine ekleyen çağırın `CFrameWnd` . `Create` pencerenin sınıf adını ve pencere adını başlatır ve stili, üst ve ilişkili menüsü için varsayılan değerleri kaydeder.

`LoadFrame` `Create` Çerçeve penceresini, bağımsız değişkenlerini belirtmek yerine bir kaynaktan yüklemek yerine kullanın.

## <a name="cframewndcreateview"></a><a name="createview"></a> CFrameWnd:: CreateView

`CreateView`Çerçeve içinde bir görünüm oluşturmak için çağırın.

```
CWnd* CreateView(
    CCreateContext* pContext,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
Görünüm ve belge türünü belirtir.

*NID*<br/>
Bir görünümün KIMLIK numarası.

### <a name="return-value"></a>Dönüş Değeri

`CWnd`Başarılı olursa nesne işaretçisi; aksi takdırde null.

### <a name="remarks"></a>Açıklamalar

Bir çerçeve içinde türetilmeyen "görünümler" oluşturmak için bu üye işlevini kullanın `CView` . Çağrıldıktan sonra `CreateView` , görünümü el ile etkin olarak ayarlamanız ve görünür olacak şekilde ayarlamanız gerekir; bu görevler tarafından otomatik olarak gerçekleştirilmez `CreateView` .

## <a name="cframewnddockcontrolbar"></a><a name="dockcontrolbar"></a> CFrameWnd::D ockControlBar

Bir denetim çubuğunun çerçeve penceresine yerleştirilmesine neden olur.

```cpp
void DockControlBar(
    CControlBar* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
Yerleşik olacak denetim çubuğunu işaret eder.

*nDockBarID*<br/>
Çerçeve penceresinin hangi yüzlerini sabitleme için dikkate verileceğini belirler. 0 veya aşağıdakilerden biri veya daha fazlası olabilir:

- AFX_IDW_DOCKBAR_TOP çerçeve penceresinin üst tarafına yerleştir.

- AFX_IDW_DOCKBAR_BOTTOM çerçeve penceresinin alt tarafına yerleştir.

- AFX_IDW_DOCKBAR_LEFT çerçeve penceresinin sol tarafına yerleştirin.

- AFX_IDW_DOCKBAR_RIGHT çerçeve penceresinin sağ tarafına yerleştirin.

0 ise, denetim çubuğu hedef çerçeve penceresinde yerleştirme için etkin olan herhangi bir tarafa sabitlenebilir.

*lpRect*<br/>
Denetim çubuğunun hedef çerçeve penceresinin istemci olmayan alanına yerleştirilme ekran koordinatlarını belirler.

### <a name="remarks"></a>Açıklamalar

Denetim çubuğu, hem [CControlBar:: EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) hem de [CFrameWnd:: EnableDocking](#enabledocking)çağrılarında belirtilen çerçeve penceresinin kenarlarından birine yerleştirilir. Seçilen kenar *nDockBarID*tarafından belirlenir.

## <a name="cframewndenabledocking"></a><a name="enabledocking"></a> CFrameWnd:: EnableDocking

Bir çerçeve penceresinde yerleştirilebilir denetim çubuklarını etkinleştirmek için bu işlevi çağırın.

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parametreler

*dwDockStyle*<br/>
Çerçeve penceresinin hangi yüzlerini denetim çubukları için yerleştirme siteleri olarak barındırabileceği belirtir. Aşağıdakilerden biri veya birkaçı olabilir:

- CBRS_ALIGN_TOP, istemci alanının en üstünde yerleştirme yapılmasına Izin verir.

- CBRS_ALIGN_BOTTOM, istemci alanının en altında yerleştirmeyi sağlar.

- CBRS_ALIGN_LEFT istemci alanının sol tarafında yerleştirme yapılmasına Izin verir.

- CBRS_ALIGN_RIGHT istemci alanının sağ tarafında yerleştirme yapılmasına Izin verir.

- CBRS_ALIGN_ANY istemci alanının herhangi bir tarafında yerleştirme yapılmasına Izin verir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, denetim çubukları çerçeve penceresinin bir tarafına şu sırada yerleştirilir: üst, alt, sol, sağ.

### <a name="example"></a>Örnek

  [CToolBar:: Create](../../mfc/reference/ctoolbar-class.md#create)örneğine bakın.

## <a name="cframewndendmodalstate"></a><a name="endmodalstate"></a> CFrameWnd:: EndModalState

Bir çerçeve penceresini kalıcı durumundan kalıcı olarak değiştirmek için bu üye işlevi çağırın.

```
virtual void EndModalState();
```

### <a name="remarks"></a>Açıklamalar

`EndModalState`[BeginModalState](#beginmodalstate)tarafından devre dışı bırakılan tüm pencereleri etkin bir şekilde sunar.

## <a name="cframewndfloatcontrolbar"></a><a name="floatcontrolbar"></a> CFrameWnd:: FloatControlBar

Bir denetim çubuğunun çerçeve penceresine yerleştirilmemesine neden olmak için bu işlevi çağırın.

```cpp
void FloatControlBar(
    CControlBar* pBar,
    CPoint point,
    DWORD dwStyle = CBRS_ALIGN_TOP);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
Kaydırılan denetim çubuğunu işaret eder.

*seçeneğinin*<br/>
Denetim çubuğunun sol üst köşesinin yerleştirileceği, ekran koordinatlarına göre konumu.

*dwStyle*<br/>
Denetim çubuğunun yeni çerçeve penceresinde yatay veya dikey olarak hizalanıp hizalanmayacağını belirtir. Aşağıdakilerden biri olabilir:

- CBRS_ALIGN_TOP denetim çubuğunu dikey olarak yönlendirir.

- CBRS_ALIGN_BOTTOM denetim çubuğunu dikey olarak yönlendirir.

- CBRS_ALIGN_LEFT, Denetim çubuğunu yatay olarak yönlendirir.

- CBRS_ALIGN_RIGHT, Denetim çubuğunu yatay olarak yönlendirir.

Stiller hem yatay hem de Dikey yönlendirmeyi belirttiyse, araç çubuğu yatay olarak dağıtılır.

### <a name="remarks"></a>Açıklamalar

Genellikle, bu, program önceki yürütmeden ayarları geri yüklerken uygulama başlangıcında yapılır.

Bu işlev, Kullanıcı, Denetim çubuğunu yerleştirme için kullanılamayan bir konum üzerine sürüklerken sol fare düğmesini serbest bırakarak bir bırakma işlemine neden olduğunda, Framework tarafından çağrılır.

## <a name="cframewndgetactivedocument"></a><a name="getactivedocument"></a> CFrameWnd:: GetActiveDocument

Geçerli etkin görünüme iliştirilmiş geçerli bir işaretçi almak için bu üye işlevini çağırın `CDocument` .

```
virtual CDocument* GetActiveDocument();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli [CDocument](../../mfc/reference/cdocument-class.md)işaretçisi. Geçerli belge yoksa, NULL değerini döndürür.

## <a name="cframewndgetactiveframe"></a><a name="getactiveframe"></a> CFrameWnd:: GetActiveFrame

Bir MDI çerçeve penceresinin etkin birden çok belge arabirimi (MDI) alt penceresine bir işaretçi almak için bu üye işlevini çağırın.

```
virtual CFrameWnd* GetActiveFrame();
```

### <a name="return-value"></a>Dönüş Değeri

Etkin MDI alt penceresine yönelik bir işaretçi. Uygulama bir SDI uygulaması veya MDI çerçeve penceresinde etkin bir belge yoksa örtük **`this`** işaretçi döndürülür.

### <a name="remarks"></a>Açıklamalar

Etkin bir MDI alt öğesi yoksa veya uygulama tek bir belge arabirimi (SDI) ise örtük **`this`** işaretçi döndürülür.

## <a name="cframewndgetactiveview"></a><a name="getactiveview"></a> CFrameWnd:: GetActiveView

Bir çerçeve penceresine () iliştirilmiş etkin görünüm (varsa) için bir işaretçi almak üzere bu üye işlevini çağırın `CFrameWnd` .

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli [CView](../../mfc/reference/cview-class.md)işaretçisi. Geçerli görünüm yoksa, NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir MDI ana kare penceresi () için çağrıldığında NULL değerini döndürür `CMDIFrameWnd` . MDI uygulamasında MDI ana çerçeve penceresinde onunla ilişkili bir görünüm yoktur. Bunun yerine, her bir alt pencerenin ( `CMDIChildWnd` ) bir veya daha fazla ilişkili görünümü vardır. MDI uygulamasındaki etkin görünüm, önce etkin MDI alt penceresi eklenerek ve ardından o alt pencere için etkin görünüm bulunurken elde edilebilir. Etkin MDI alt penceresi, işlevi çağırarak `MDIGetActive` veya `GetActiveFrame` aşağıdaki şekilde gösterildiği gibi bulunabilir:

[!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]

## <a name="cframewndgetcontrolbar"></a><a name="getcontrolbar"></a> CFrameWnd:: GetControlBar

`GetControlBar`Kimlik ile ilişkili denetim çubuğuna erişim kazanmak için çağırın.

```
CControlBar* GetControlBar(UINT nID);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Bir denetim çubuğunun KIMLIK numarası.

### <a name="return-value"></a>Dönüş Değeri

KIMLIK ile ilişkili denetim çubuğuna yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*NID* parametresi, denetim çubuğunun yöntemine geçirilen benzersiz tanımlayıcıyı ifade eder `Create` . Denetim çubukları hakkında daha fazla bilgi için [Denetim çubukları](../../mfc/control-bars.md)başlıklı konuya bakın.

`GetControlBar` , kayan olsa bile denetim çubuğunu döndürür ve bu nedenle şu anda çerçevenin alt penceresi değildir.

## <a name="cframewndgetdockstate"></a><a name="getdockstate"></a> CFrameWnd:: GetDockState

Bir nesnedeki çerçeve penceresinin denetim çubukları hakkında durum bilgilerini depolamak için bu üye işlevi çağırın `CDockState` .

```cpp
void GetDockState(CDockState& state) const;
```

### <a name="parameters"></a>Parametreler

*state*<br/>
Dönüş sırasında çerçeve penceresinin denetim çubuklarının geçerli durumunu içerir.

### <a name="remarks"></a>Açıklamalar

Daha sonra, `CDockState` veya kullanarak depolama alanına içeriğini yazabilirsiniz `CDockState::SaveState` `Serialize` . Daha sonra Denetim çubuklarını önceki bir duruma geri yüklemek istiyorsanız, durumu veya ile yükleyin ve `CDockState::LoadState` `Serialize` ardından `SetDockState` önceki durumu çerçeve penceresinin denetim çubuklarına uygulamak için çağırın.

## <a name="cframewndgetmenubarstate"></a><a name="getmenubarstate"></a> CFrameWnd:: GetMenuBarState

Geçerli MFC uygulamasındaki menünün görüntüleme durumunu alır.

```
virtual DWORD GetMenuBarState();
```

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri aşağıdaki değerlere sahip olabilir:

- AFX_MBS_VISIBLE (0x01)-menü görünür.

- AFX_MBS_HIDDEN (0x02)-menü gizlenir.

### <a name="remarks"></a>Açıklamalar

Bir çalışma zamanı hatası oluşursa, bu yöntem hata ayıklama modunda onaylar ve [CException](../../mfc/reference/cexception-class.md) sınıfından türetilmiş bir özel durum oluşturur.

## <a name="cframewndgetmenubarvisibility"></a><a name="getmenubarvisibility"></a> CFrameWnd:: GetMenuBarVisibility

Geçerli MFC uygulamasındaki menünün varsayılan durumunun gizli veya görünür olup olmadığını gösterir.

```
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem aşağıdaki değerlerden birini döndürür:

- AFX_MBV_KEEPVISIBLE (0x01)-menü her zaman görüntülenir ve varsayılan olarak odağa sahip değildir.

- AFX_MBV_DISPLAYONFOCUS (0x02)-menü varsayılan olarak gizlidir. Menü gizliyse, menüyü göstermek ve odağı vermek için ALT tuşuna basın. Menü görüntüleniyorsa, gizlemek için ALT veya ESC tuşuna basın.

- AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04) (bit düzeyinde birleşim (veya))-menü varsayılan olarak gizlidir. Menü gizliyse, menüyü göstermek ve odağı vermek için F10 tuşuna basın. Menü görüntüleniyorsa, odağı açıp kapatmak için F10 tuşuna basın. Menü, ALT veya ESC tuşuna basarak gizleyecek şekilde görüntülenir.

### <a name="remarks"></a>Açıklamalar

Bir çalışma zamanı hatası oluşursa, bu yöntem hata ayıklama modunda onaylar ve [CException](../../mfc/reference/cexception-class.md) sınıfından türetilmiş bir özel durum oluşturur.

## <a name="cframewndgetmessagebar"></a><a name="getmessagebar"></a> CFrameWnd:: GetMessageBar

Durum çubuğuna bir işaretçi almak için bu üye işlevi çağırın.

```
virtual CWnd* GetMessageBar();
```

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu penceresine yönelik işaretçi.

## <a name="cframewndgetmessagestring"></a><a name="getmessagestring"></a> CFrameWnd:: GetMessageString

Komut kimlikleri için özel dizeler sağlamak üzere bu işlevi geçersiz kılın.

```
virtual void GetMessageString(
    UINT nID,
    CString& rMessage) const;
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
İstenen iletinin kaynak KIMLIĞI.

*rMessage*<br/>
`CString` iletinin yerleştirileceği nesne.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, yalnızca *NID* tarafından belirtilen dizeyi kaynak dosyasından yükler. Bu işlev, durum çubuğundaki ileti dizesinin güncelleştirilmesi gerektiğinde Framework tarafından çağırılır.

## <a name="cframewndgettitle"></a><a name="gettitle"></a> CFrameWnd:: GetTitle

Pencere nesnesinin başlığını alır.

```
CString GetTitle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pencere nesnesinin geçerli başlığını içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

## <a name="cframewndinitialupdateframe"></a><a name="initialupdateframe"></a> CFrameWnd:: ınitialupdateframe

`IntitialUpdateFrame`İle yeni bir çerçeve oluşturduktan sonra çağırın `Create` .

```cpp
void InitialUpdateFrame(
    CDocument* pDoc,
    BOOL bMakeVisible);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Çerçeve penceresinin ilişkilendirildiği belgeyi işaret eder. NULL olabilir.

*bMakeVisible*<br/>
DOĞRU ise, çerçevenin görünür ve etkin hale gelmesi gerektiğini gösterir. YANLıŞSA, hiçbir alt öğe görünür hale getirilmez.

### <a name="remarks"></a>Açıklamalar

Bu, bu çerçeve penceresindeki tüm görünümlerin aramalarını almasına neden olur `OnInitialUpdate` .

Ayrıca, daha önce etkin bir görünüm yoksa, çerçeve penceresinin birincil görünümü etkin hale getirilir. Birincil görünüm, AFX_IDW_PANE_FIRST alt KIMLIĞI olan bir görünümüdür. Son olarak, *bMakeVisible* sıfır değilse çerçeve penceresi görünür hale getirilir. *BMakeVisible* 0 ise, çerçeve penceresinin geçerli odağı ve görünür durumu değişmeden kalır. Framework 'ün yeni dosya ve dosya açma uygulamasının uygulanması kullanılırken bu işlevi çağırmak gerekli değildir.

## <a name="cframewndinmodalstate"></a><a name="inmodalstate"></a> CFrameWnd:: InModalState

Bir çerçeve penceresinin kalıcı veya kalıcı olup olmadığını denetlemek için bu üye işlevi çağırın.

```
BOOL InModalState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Evet ise sıfır dışı; Aksi takdirde 0.

## <a name="cframewndistracking"></a><a name="istracking"></a> CFrameWnd:: IsTracking

Penceredeki Bölümlendirici çubuğunun Şu anda taşınıp taşınmadığını öğrenmek için bu üye işlevi çağırın.

```
BOOL IsTracking() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir Splitter işlemi devam ediyorsa sıfır dışı; Aksi takdirde 0.

## <a name="cframewndloadacceltable"></a><a name="loadacceltable"></a> CFrameWnd:: LoadAccelTable

Belirtilen Hızlandırıcı tablosunu yüklemek için çağırın.

```
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Hızlandırıcı kaynağının adını tanımlar. Kaynak bir tamsayı KIMLIĞIYLE tanımlanmışsa MAKEINTRESOURCE kullanın.

### <a name="return-value"></a>Dönüş Değeri

Hızlandırıcı tablosu başarıyla yüklenmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Tek seferde yalnızca bir tablo yüklenebilir.

Kaynaklardan yüklenen Hızlandırıcı tabloları, uygulama sonlandırıldığında otomatik olarak serbest bırakılır.

`LoadFrame`Çerçeve penceresini oluşturmak için çağrı yaparsanız çerçeve, menü ve simge kaynaklarıyla birlikte bir Hızlandırıcı tablosu yükler ve bu üye işlevine yönelik sonraki bir çağrı gereksizdir.

## <a name="cframewndloadbarstate"></a><a name="loadbarstate"></a> CFrameWnd:: LoadBarState

Çerçeve penceresine ait olan her bir denetim çubuğunun ayarlarını geri yüklemek için bu işlevi çağırın.

```cpp
void LoadBarState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
Başlatma (INI) dosyasındaki bir bölümün adı veya Windows kayıt defteri 'nde durum bilgilerinin depolandığı bir anahtar.

### <a name="remarks"></a>Açıklamalar

Geri yüklenen bilgiler görünürlük, yatay/dikey yön, yerleştirme durumu ve denetim çubuğu konumunu içerir.

Geri yüklemek istediğiniz ayarların, çağrısından önce kayıt defterine yazılması gerekir `LoadBarState` . Bu bilgileri, [CWinApp:: SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey)çağırarak kayıt defterine yazın. [SaveBarState](#savebarstate)' i ÇAĞıRARAK bilgileri INI dosyasına yazın.

## <a name="cframewndloadframe"></a><a name="loadframe"></a> CFrameWnd:: LoadFrame

Kaynak bilgilerden dinamik olarak bir çerçeve penceresi oluşturmak için çağırın.

```
virtual BOOL LoadFrame(
    UINT nIDResource,
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,
    CWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parametreler

*nIDResource*<br/>
Çerçeve penceresiyle ilişkili paylaşılan kaynakların KIMLIĞI.

*dwDefaultStyle*<br/>
Çerçevenin [stili](../../mfc/reference/styles-used-by-mfc.md#window-styles). Başlık çubuğunun pencerede temsil edilen belge adını otomatik olarak görüntülemesini istiyorsanız FWS_ADDTOTITLE stilini ekleyin.

*pParentWnd*<br/>
Çerçevenin üst öğesi için bir işaretçi.

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısına yönelik bir işaretçi. Bu parametre NULL olabilir.

### <a name="remarks"></a>Açıklamalar

`CFrameWnd`İki adımda bir nesne oluşturun. İlk olarak, nesnesini oluşturan oluşturucuyu çağırın `CFrameWnd` ve ardından `LoadFrame` Windows çerçeve penceresini ve ilişkili kaynakları yükleyen ve çerçeveye çerçeve penceresi ekleyen çağırın `CFrameWnd` . *Nidresource* parametresi menü, Hızlandırıcı tablosu, simgesini ve çerçeve penceresi için başlığın dize kaynağını belirtir.

`Create` `LoadFrame` Çerçeve penceresinin oluşturulma parametrelerini belirtmek istediğiniz zaman yerine Member işlevini kullanın.

Framework `LoadFrame` bir belge şablonu nesnesi kullanarak bir çerçeve penceresi oluşturduğunda çağırır.

Framework, içerilen görünüm nesneleri dahil olmak üzere çerçeve penceresine bağlanacak nesneleri belirtmek için *pContext* bağımsız değişkenini kullanır. ' İ çağırdığınızda *pContext* BAĞıMSıZ değişkenini null olarak ayarlayabilirsiniz `LoadFrame` .

## <a name="cframewndm_bautomenuenable"></a><a name="m_bautomenuenable"></a> CFrameWnd:: m_bAutoMenuEnable

Bu veri üyesi etkinleştirildiğinde (varsayılan olarak), ON_UPDATE_COMMAND_UI veya ON_COMMAND işleyicileri olmayan menü öğeleri Kullanıcı bir menü seçtiğinde otomatik olarak devre dışı bırakılır.

```
BOOL m_bAutoMenuEnable;
```

### <a name="remarks"></a>Açıklamalar

ON_COMMAND işleyicisi olan ancak ON_UPDATE_COMMAND_UI işleyicisi olan menü öğeleri otomatik olarak etkinleştirilmez.

Bu veri üyesi ayarlandığında, menü öğeleri araç çubuğu düğmelerinin etkinleştirildiği şekilde otomatik olarak etkinleştirilir.

> [!NOTE]
> `m_bAutoMenuEnable` üst düzey menü öğeleri üzerinde hiçbir etkisi yoktur.

Bu veri üyesi, geçerli seçime bağlı olarak isteğe bağlı komutların uygulanmasını basitleştirir ve menü öğelerini etkinleştirmek ve devre dışı bırakmak için ON_UPDATE_COMMAND_UI işleyicileri yazma ihtiyacını azaltır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]

## <a name="cframewndnegotiateborderspace"></a><a name="negotiateborderspace"></a> CFrameWnd:: NegotiateBorderSpace

OLE yerinde etkinleştirme sırasında bir çerçeve penceresinde kenarlık alanı üzerinde anlaşmak için bu üye işlevini çağırın.

```
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,
    LPRECT lpRectBorder);
```

### <a name="parameters"></a>Parametreler

*nBorderCmd*<br/>
Aşağıdaki değerlerden birini içerir `enum BorderCmd` :

- `borderGet` = 1

- `borderRequest` = 2

- `borderSet` = 3

*lpRectBorder*<br/>
Kenarlığın koordinatlarını belirten bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, `CFrameWnd` OLE sınır alanı anlaşmasının uygulamasıdır.

## <a name="cframewndonbarcheck"></a><a name="onbarcheck"></a> CFrameWnd:: OnBarCheck

Belirtilen denetim çubuğunda bir eylem yapıldığında çağırılır.

```
afx_msg BOOL OnBarCheck(UINT nID);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Gösterilen denetim çubuğunun KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu varsa sıfır dışı; Aksi takdirde 0.

## <a name="cframewndoncontexthelp"></a><a name="oncontexthelp"></a> CFrameWnd:: OnContextHelp

Yerinde öğeler için SHIFT + F1 yardımını işler.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Açıklamalar

Bağlama duyarlı yardımı etkinleştirmek için bir

[!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]

`CFrameWnd`sınıfınıza yönelik bildirim ve ayrıca, bu üye işlevi etkinleştirmek için genellıkle SHIFT + F1 şeklinde bir kısayol tablosu girişi ekleyin.

Uygulamanız bir OLE kapsayıcısıdır, `OnContextHelp` çerçeve penceresi nesnesinin içindeki tüm yerinde öğeleri yardım moduna geçirir. İmleç ok ve soru işaretine dönüşür ve Kullanıcı daha sonra fare işaretçisini taşıyabilir ve bir iletişim kutusu, pencere, menü ya da komut düğmesi seçmek için sol fare düğmesine basabilir. Bu üye işlevi, `WinHelp` imleç altındaki nesnenin yardım bağlamı Ile Windows işlevini çağırır.

## <a name="cframewndoncreateclient"></a><a name="oncreateclient"></a> CFrameWnd:: OnCreateClient

Yürütmesi sırasında Framework tarafından çağırılır `OnCreate` .

```
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,
    CCreateContext* pContext);
```

### <a name="parameters"></a>Parametreler

*lpcs*<br/>
Windows [CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) yapısına yönelik bir işaretçi.

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi hiçbir şekilde çağırmayın.

Bu işlevin varsayılan uygulanması `CView` , mümkünse *pContext*'te belirtilen bilgilerden bir nesne oluşturur.

Nesneye geçirilen değerleri geçersiz kılmak `CCreateContext` veya çerçeve penceresinin ana istemci alanındaki denetimleri değiştirmek için bu işlevi geçersiz kılın. `CCreateContext`Geçersiz kılabileceğiniz Üyeler [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) sınıfında açıklanmıştır.

> [!NOTE]
> Yapıda geçirilen değerleri değiştirme `CREATESTRUCT` . Bunlar yalnızca bilgilendirme amaçlıdır. Örneğin, ilk pencere dikdörtgenini geçersiz kılmak istiyorsanız, `CWnd` üye işlevi önceden [Reatewindow](../../mfc/reference/cwnd-class.md#precreatewindow)' u geçersiz kılın.

## <a name="cframewndonhidemenubar"></a><a name="onhidemenubar"></a> CFrameWnd:: OnHideMenuBar

Bu işlev, sistem geçerli MFC uygulamasındaki menü çubuğunu gizlemek üzereyken çağrılır.

```
virtual void OnHideMenuBar();
```

### <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi, sistem menüyü gizlemek üzere olduğunda uygulamanızın özel eylemler gerçekleştirmesini sağlar. Menünün gizli olmasını engellenemez, ancak örneğin, menü stilini veya durumunu almak için diğer yöntemleri çağırabilirsiniz.

## <a name="cframewndonsetpreviewmode"></a><a name="onsetpreviewmode"></a> CFrameWnd:: Onsetönizleme modu

Bu üye işlevini, uygulamanın ana çerçeve penceresini yazdırma önizleme modundan ve dışına ayarlamak için çağırın.

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>Parametreler

*bPreview*<br/>
Uygulamanın baskı önizleme modunda yerleştirip yerleştirmeyeceğini belirtir. Baskı önizlemede yerleştirmek için TRUE, Önizleme modunu iptal etmek için FALSE olarak ayarlayın.

*pState*<br/>
Bir yapıya yönelik işaretçi `CPrintPreviewState` .

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama tüm standart araç çubuklarını devre dışı bırakır ve ana menüyü ve ana istemci penceresini gizler. Bu, MDI çerçeve pencerelerini geçici SDI çerçeve pencereleri olarak açar.

Yazdırma önizlemesi sırasında denetim çubuklarının ve diğer çerçeve pencere bölümlerinin gizlenme ve gösterilmesini özelleştirmek için bu üye işlevi geçersiz kılın. Geçersiz kılınan sürüm içinden temel sınıf uygulamasını çağırın.

## <a name="cframewndonshowmenubar"></a><a name="onshowmenubar"></a> CFrameWnd:: OnShowMenuBar

Bu işlev, sistem geçerli MFC uygulamasında menü çubuğunu göstermek üzereyken çağrılır.

```
virtual void OnShowMenuBar();
```

### <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi, bir menü görüntülenmek üzere olduğunda uygulamanızın özel eylemler gerçekleştirmesini sağlar. Menünün görüntülenmesini engellenemez, ancak örneğin, menü stilini veya durumunu almak için diğer yöntemleri çağırabilirsiniz.

## <a name="cframewndonupdatecontrolbarmenu"></a><a name="onupdatecontrolbarmenu"></a> CFrameWnd:: OnUpdateControlBarMenu

İlişkili menü güncelleştirildiği zaman Framework tarafından çağırılır.

```
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Update komutunu oluşturan menüyü temsil eden [CCmdUI](../../mfc/reference/ccmdui-class.md) nesnesine yönelik bir işaretçi. Güncelleştirme işleyicisi, [Enable](../../mfc/reference/ccmdui-class.md#enable) `CCmdUI` Kullanıcı arabirimini güncelleştirmek için nesnesinin *pCmdUI* aracılığıyla üye etkinleştirme işlevini çağırır.

## <a name="cframewndrecalclayout"></a><a name="recalclayout"></a> CFrameWnd:: RecalcLayout

Standart denetim çubukları açık veya kapalı olduğunda ya da çerçeve penceresi yeniden boyutlandırılırken Framework tarafından çağırılır.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parametreler

*bNotify*<br/>
Çerçeve penceresi için etkin yerinde öğenin düzen değişikliği bildirimini alıp almayacağını belirler. TRUE ise, öğe bilgilendirilir; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin varsayılan uygulanması, `CWnd` `RepositionBars` çerçeve içindeki tüm denetim çubuklarının yanı sıra ana istemci penceresinde (genellikle a veya MDICLIENT) yeniden konumlandırmak için üye işlevini çağırır `CView` .

Çerçeve penceresinin düzeni değiştirildikten sonra Denetim çubuklarının görünümünü ve davranışını denetlemek için bu üye işlevini geçersiz kılın. Örneğin, denetim çubuklarını açıp kapattığınızda veya başka bir denetim çubuğu eklediğinizde bunu çağırın.

## <a name="cframewndrectdefault"></a><a name="rectdefault"></a> CFrameWnd:: rectDefault

Pencerenin `CRect` ilk boyutunu ve konumunu seçmesini sağlamak için bir pencere oluştururken bu statik parametreyi parametre olarak geçirin.

```
static AFX_DATA const CRect rectDefault;
```

## <a name="cframewndsavebarstate"></a><a name="savebarstate"></a> CFrameWnd:: SaveBarState

Çerçeve penceresine ait olan her denetim çubuğu hakkındaki bilgileri depolamak için bu işlevi çağırın.

```cpp
void SaveBarState(LPCTSTR lpszProfileName) const;
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
Başlangıç dosyasındaki bir bölümün adı veya Windows kayıt defteri 'nde durum bilgilerinin depolandığı bir anahtar.

### <a name="remarks"></a>Açıklamalar

Bu bilgiler, başlatma dosyasından [LoadBarState](#loadbarstate)kullanılarak okunabilir. Depolanan bilgiler görünürlük, yatay/dikey yön, yerleştirme durumu ve denetim çubuğu konumunu içerir.

## <a name="cframewndsetactivepreviewview"></a><a name="setactivepreviewview"></a> CFrameWnd:: Setactiveönizleme görünümü

Belirtilen görünümü zengin önizleme için etkin görünüm olarak belirler.

```cpp
void SetActivePreviewView(CView* pViewNew);
```

### <a name="parameters"></a>Parametreler

*pViewNew*<br/>
Etkinleştirilecek bir görünümün işaretçisi.

### <a name="remarks"></a>Açıklamalar

## <a name="cframewndsetactiveview"></a><a name="setactiveview"></a> CFrameWnd:: SetActiveView

Etkin görünümü ayarlamak için bu üye işlevini çağırın.

```cpp
void SetActiveView(
    CView* pViewNew,
    BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parametreler

*pViewNew*<br/>
Bir [CView](../../mfc/reference/cview-class.md) nesnesine yönelik bir işaretçi ya da etkin görünüm olmadan null değerini belirtir.

*bNotify*<br/>
Görünümün etkinleştirme için bildirim uygulanıp bildirilmeyeceğini belirtir. TRUE ise `OnActivateView` Yeni görünüm için çağırılır; yanlışsa, değildir.

### <a name="remarks"></a>Açıklamalar

Kullanıcı odağı çerçeve penceresi içindeki bir görünüme değiştirdiğinde Framework bu işlevi otomatik olarak çağırır. `SetActiveView`Odağı belirtilen görünüme dönüştürmek için açıkça çağrı yapabilirsiniz.

## <a name="cframewndsetdockstate"></a><a name="setdockstate"></a> CFrameWnd:: SetDockState

Bir nesne içinde depolanan durum bilgilerini `CDockState` çerçeve penceresinin denetim çubuklarına uygulamak için bu üye işlevini çağırın.

```cpp
void SetDockState(const CDockState& state);
```

### <a name="parameters"></a>Parametreler

*state*<br/>
Depolanan durumu çerçeve penceresinin denetim çubuklarına uygulayın.

### <a name="remarks"></a>Açıklamalar

Denetim çubuklarının önceki bir durumunu geri yüklemek için, saklı durumu veya ile yükleyebilir `CDockState::LoadState` `Serialize` , ardından `SetDockState` bunu çerçeve penceresinin denetim çubuklarına uygulamak için kullanabilirsiniz. Önceki durum, `CDockState` ile nesnesinde depolanır `GetDockState`

## <a name="cframewndsetmenubarstate"></a><a name="setmenubarstate"></a> CFrameWnd:: SetMenuBarState

Geçerli MFC uygulamasındaki menünün görüntüleme durumunu gizli veya görüntülenir olarak ayarlar.

```
virtual BOOL SetMenuBarState(DWORD nState);
```

### <a name="parameters"></a>Parametreler

*nDurum*\
'ndaki Menünün görüntülenip görüntülenmeyeceğini veya gizlenmeyeceğini belirtir. *NState* parametresi aşağıdaki değerlere sahip olabilir:

- `AFX_MBS_VISIBLE` (0x01)-menü gizliyse menüyü görüntüler, ancak görünür durumdaysa hiçbir etkiye sahip olmaz.
- `AFX_MBS_HIDDEN` (0x02)-görünür durumdaysa menüyü gizler, ancak gizliyse hiçbir etkisi olmaz.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem menü durumunu başarıyla değiştirirse TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bir çalışma zamanı hatası oluşursa, bu yöntem hata ayıklama modunda onaylar ve [CException](../../mfc/reference/cexception-class.md) sınıfından türetilmiş bir özel durum oluşturur.

## <a name="cframewndsetmenubarvisibility"></a><a name="setmenubarvisibility"></a> CFrameWnd:: SetMenuBarVisibility

Geçerli MFC uygulamasındaki menünün varsayılan davranışını gizli ya da görünür olacak şekilde ayarlar.

```
virtual void SetMenuBarVisibility(DWORD nStyle);
```

### <a name="parameters"></a>Parametreler

*nStyle*\
'ndaki Menünün varsayılan olarak gizli olup olmadığını veya görünür olduğunu ve odağa sahip olduğunu belirtir. *NStyle* parametresi aşağıdaki değerlere sahip olabilir:

- `AFX_MBV_KEEPVISIBLE` (0x01)-menü her zaman görüntülenir ve varsayılan olarak odağa sahip değildir.

- `AFX_MBV_DISPLAYONFOCUS` (0x02)-menü varsayılan olarak gizlidir. Menü gizliyse, menüyü göstermek ve odağı vermek için ALT tuşuna basın. Menü görüntüleniyorsa menüyü gizlemek için ALT veya ESC tuşuna basın.

- `AFX_MBV_DISPLAYONFOCUS` (0x02) &#124; `AFX_MBV_DISPLAYONF10` (0x04) (bit düzeyinde birleşim (veya))-menü varsayılan olarak gizlidir. Menü gizliyse, menüyü göstermek ve odağı vermek için F10 tuşuna basın. Menü görüntüleniyorsa, odağı açıp kapatmak için F10 tuşuna basın. Menü, ALT veya ESC tuşuna basarak gizleyecek şekilde görüntülenir.

### <a name="remarks"></a>Açıklamalar

*NStyle* parametresinin değeri geçerli değilse, bu yöntem hata ayıklama modunda onay verir ve bırakma modunda [Cinvalidargexception](../../mfc/reference/cinvalidargexception-class.md) 'ı başlatır. Diğer çalışma zamanı hataları söz konusu olduğunda, bu yöntem hata ayıklama modunda onay verir ve [CException](../../mfc/reference/cexception-class.md) sınıfından türetilmiş bir özel durum oluşturur.

Bu yöntem, Windows Vista ve üzeri için yazılmış uygulamalardaki menülerin durumunu etkiler.

## <a name="cframewndsetmessagetext"></a><a name="setmessagetext"></a> CFrameWnd:: SetMessageText

KIMLIĞI 0 olan durum çubuğu bölmesine bir dize yerleştirmek için bu işlevi çağırın.

```cpp
void SetMessageText(LPCTSTR lpszText);
void SetMessageText(UINT nID);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
Durum çubuğuna yerleştirilecek dizeyi işaret eder.

*NID*<br/>
Durum çubuğuna yerleştirilecek dizenin dize kaynak KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu genellikle durum çubuğunun en sol ve en uzun bölmesidir.

## <a name="cframewndsetprogressbarposition"></a><a name="setprogressbarposition"></a> CFrameWnd:: SetProgressBarPosition

Görev çubuğunda görüntülenmek üzere Windows 7 ilerleme çubuğunun geçerli konumunu ayarlar.

```cpp
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>Parametreler

*nProgressPos*<br/>
Ayarlanacak konumu belirtir. Tarafından ayarlanan Aralık dahilinde olmalıdır `SetProgressBarRange` .

### <a name="remarks"></a>Açıklamalar

## <a name="cframewndsetprogressbarrange"></a><a name="setprogressbarrange"></a> CFrameWnd:: SetProgressBarRange

Görev çubuğunda görüntülenmek üzere Windows 7 ilerleme çubuğunun aralığını ayarlar.

```cpp
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>Parametreler

*nRangeMin*<br/>
En küçük değer.

*nRangeMax*<br/>
Maxhayvan değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cframewndsetprogressbarstate"></a><a name="setprogressbarstate"></a> CFrameWnd:: SetProgressBarState

Bir görev çubuğu düğmesinde görünen ilerleme göstergesinin türünü ve durumunu ayarlar.

```cpp
void SetProgressBarState(TBPFLAG tbpFlags);
```

### <a name="parameters"></a>Parametreler

*tbpFlags*<br/>
İlerleme düğmesinin geçerli durumunu denetleyen bayraklar. Tüm durumlar birbirini dışlamalı olduğundan aşağıdaki bayraklardan yalnızca birini belirtin: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.

### <a name="remarks"></a>Açıklamalar

## <a name="cframewndsettaskbaroverlayicon"></a><a name="settaskbaroverlayicon"></a> CFrameWnd:: Settaskbaroverlayıcon

Fazla Yüklendi. Uygulama durumunu göstermek veya kullanıcıya bildirimde bulunan bir görev çubuğu düğmesine bir kaplama uygular.

```
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,
    LPCTSTR lpcszDescr);

BOOL SetTaskbarOverlayIcon(
    HICON hIcon,
    LPCTSTR lpcszDescr);
```

### <a name="parameters"></a>Parametreler

*nIDResource*<br/>
Kaplama olarak kullanılacak simgenin kaynak KIMLIĞINI belirtir. Ayrıntılar için bkz. *HICON* için açıklama.

*lpcszDescr*<br/>
Erişilebilirlik amacıyla, yer kaplayan bilgilerin alt metin sürümünü sağlayan bir dize işaretçisi.

*HICON*<br/>
Kaplama olarak kullanılacak simgenin tutamacı. Bu küçük bir simge olmalıdır, %96 nokta/inç (dpi) üzerinde 16x16 piksel ölçme. Bir kaplama simgesi zaten görev çubuğu düğmesine uygulanmışsa, varolan bir kaplama değiştirilmiştir. Bu değer NULL olabilir. NULL değerin nasıl işlendiği, görev çubuğu düğmesinin tek bir pencereyi mi yoksa bir pencere grubunu mı temsil ettiğini bağlıdır. Artık gerekli olmadığında, çağıran uygulamanın *HICON* ücretsiz olarak kullanıldığı sorumluluğudur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; İşletim sistemi sürümü Windows 7 ' den küçükse veya simgeyi ayarlarken bir hata oluşursa FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cframewndsettitle"></a><a name="settitle"></a> CFrameWnd:: SetTitle

Pencere nesnesinin başlığını ayarlar.

```cpp
void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Parametreler

*lpszTitle*<br/>
Pencere nesnesinin başlığını içeren bir karakter dizesinin işaretçisi.

## <a name="cframewndshowcontrolbar"></a><a name="showcontrolbar"></a> CFrameWnd:: ShowControlBar

Denetim çubuğunu göstermek veya gizlemek için bu üye işlevini çağırın.

```cpp
void ShowControlBar(
    CControlBar* pBar,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
Görüntülenecek veya gizlenecek denetim çubuğunun işaretçisi.

*bShow*<br/>
DOĞRU ise, denetim çubuğunun gösterildiğini belirtir. YANLıŞSA, denetim çubuğunun gizlendiğini belirtir.

*bDelay*<br/>
DOĞRU ise, Denetim çubuğunu gösteren gecikme. YANLıŞSA, Denetim çubuğunu hemen gösterin.

## <a name="cframewndshowownedwindows"></a><a name="showownedwindows"></a> CFrameWnd:: ShowOwnedWindows

Nesnenin alt öğesi olan tüm pencereleri göstermek için bu üye işlevi çağırın `CFrameWnd` .

```cpp
void ShowOwnedWindows(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
Sahip olunan pencerelerin gösterilip gösterilmeyeceğini veya gizlenmeyeceğini belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd sınıfı](../../mfc/reference/cmdiframewnd-class.md)<br/>
[Cmdicchild Dwnd sınıfı](../../mfc/reference/cmdichildwnd-class.md)<br/>
[CView sınıfı](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CRuntimeClass yapısı](../../mfc/reference/cruntimeclass-structure.md)
