---
title: CFrameWnd Sınıfı
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
ms.openlocfilehash: 3bb93420b39be5d6fb9a6691cec8300fdccb0e73
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754983"
---
# <a name="cframewnd-class"></a>CFrameWnd Sınıfı

Pencereyi yönetmek için üyelerle birlikte üst üste binen veya açılır çerçeve penceresi olan Bir Windows tek belge arabiriminin (SDI) işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFrameWnd : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFrameWnd::CFrameWnd](#cframewnd)|Bir `CFrameWnd` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFrameWnd::Etkinleştirme Çerçevesi](#activateframe)|Çerçeveyi görünür ve kullanıcı tarafından kullanılabilir hale getirir.|
|[CFrameWnd::BeginModalState](#beginmodalstate)|Çerçeve penceresini modal olarak ayarlar.|
|[CFrameWnd::Oluştur](#create)|`CFrameWnd` Nesneyle ilişkili Windows çerçeve penceresi oluşturmak ve başlatmayı arayın.|
|[CFrameWnd::CreateView](#createview)|`CView`Türetilen olmayan bir çerçeve içinde bir görünüm oluşturur.|
|[CFrameWnd::DockControlBar](#dockcontrolbar)|Bir kontrol çubuğuna yanaşıyor.|
|[CFrameWnd::Etkinleştirme Docking](#enabledocking)|Bir denetim çubuğunun kenetlenmesini sağlar.|
|[CFrameWnd::EndModalState](#endmodalstate)|Çerçeve penceresinin modal durumunu sona erdirer. Tüm pencereleri devre dışı `BeginModalState`bırakmanızı sağlar.|
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|Bir kontrol çubuğu yüzer.|
|[CFrameWnd::GetActiveDocument](#getactivedocument)|Etkin nesneyi döndürür. `CDocument`|
|[CFrameWnd::GetActiveFrame](#getactiveframe)|Etkin nesneyi döndürür. `CFrameWnd`|
|[CFrameWnd::GetActiveView](#getactiveview)|Etkin nesneyi döndürür. `CView`|
|[CFrameWnd::GetControlBar](#getcontrolbar)|Denetim çubuğunu alır.|
|[CFrameWnd::GetDockState](#getdockstate)|Çerçeve penceresinin dock durumunu alır.|
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|Geçerli MFC uygulamasında menünün görüntü durumunu alır.|
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|Geçerli MFC uygulamasındaki menünün varsayılan davranışının gizli veya görünür olup olmadığını gösterir.|
|[CFrameWnd::GetMessageBar](#getmessagebar)|Çerçeve penceresine ait durum çubuğuna bir işaretçi döndürür.|
|[CFrameWnd::GetMessageString](#getmessagestring)|Komut kimliğine karşılık gelen iletiyi alır.|
|[CFrameWnd::GetTitle](#gettitle)|İlgili denetim çubuğunun başlığını alır.|
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|Çerçeve `OnInitialUpdate` penceresindeki tüm görünümlere ait üye işlevin çağrılmasını neden olur.|
|[CFrameWnd::InModalState](#inmodalstate)|Çerçeve penceresinin modal durumda olup olmadığını belirten bir değer döndürür.|
|[CFrameWnd::IsTracking](#istracking)|Splitter çubuğunun şu anda taşınıp taşınmayanlarını belirler.|
|[CFrameWnd::LoadAccelTable](#loadacceltable)|Hızlandırıcı tablosunu yüklemek için arayın.|
|[CFrameWnd::LoadBarState](#loadbarstate)|Denetim çubuğu ayarlarını geri yüklemek için arayın.|
|[CFrameWnd::LoadFrame](#loadframe)|Kaynak bilgilerinden dinamik olarak bir çerçeve penceresi oluşturmak için arayın.|
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|Çerçeve penceresinde kenarlık alanını görüşür.|
|[CFrameWnd::OnBarCheck](#onbarcheck)|Belirtilen denetim çubuğunda bir eylem yapıldığında çağrılır.|
|[CFrameWnd::OnContextHelp](#oncontexthelp)|Yerinde öğeler için SHIFT+F1 Yardım'ı işler.|
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|Uygulamanın ana çerçeve penceresini yazdırma önizleme moduna ve dışına ayarlar.|
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|İlişkili menü güncelleştirildiğinde çerçeve tarafından çağrılır.|
|[CFrameWnd::RecalcLayout](#recalclayout)|`CFrameWnd` Nesnenin denetim çubuklarını yeniden konumlandırın.|
|[CFrameWnd::SaveBarState](#savebarstate)|Denetim çubuğu ayarlarını kaydetmek için arayın.|
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|Belirtilen görünümü Zengin Önizleme için etkin görünüm olarak belirtir.|
|[CFrameWnd::SetActiveView](#setactiveview)|Etkin `CView` nesneyi ayarlar.|
|[CFrameWnd::SetDockState](#setdockstate)|Ana penceredeki çerçeve penceresini yerleştirmeyi arayın.|
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|Geçerli MFC uygulamasındaki menünün ekran durumunu gizli veya görüntülenecek şekilde ayarlar.|
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|Geçerli MFC uygulamasındaki menünün varsayılan davranışını gizli veya görünür olarak ayarlar.|
|[CFrameWnd::SetMessageText](#setmessagetext)|Standart durum çubuğunun metnini ayarlar.|
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|Görev çubuğunda görüntülenen Windows 7 ilerleme çubuğu için geçerli konumu ayarlar.|
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|Görev çubuğunda görüntülenen Windows 7 ilerleme çubuğu aralığını ayarlar.|
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|Görev çubuğu düğmesinde görüntülenen ilerleme göstergesinin türünü ve durumunu ayarlar.|
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|Fazla Yüklendi. Uygulama durumunu veya kullanıcıya bir bildirim belirtmek için görev çubuğuna bir bindirme uygular.|
|[CFrameWnd::SetTitle](#settitle)|İlgili denetim çubuğunun başlığını ayarlar.|
|[CFrameWnd::ShowControlBar](#showcontrolbar)|Kontrol çubuğunu göstermek için arayın.|
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|Nesnenin torunları olan tüm `CFrameWnd` pencereleri gösterir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFrameWnd::OnCreateClient](#oncreateclient)|Çerçeve için bir istemci penceresi oluşturur.|
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|Geçerli MFC uygulamasındaki menü gizlenmeden önce çağrılır.|
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|Geçerli MFC uygulamasındaki menü görüntülenmeden önce çağrılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|Menü öğeleri için otomatik etkinleştirme ve işlevselliği devre dışı kullanabilirsiniz.|
|[CFrameWnd::rectVarsayılan](#rectdefault)|Windows'un `CRect` pencerenin başlangıç boyutunu `CFrameWnd` ve konumunu seçmesine izin verecek bir nesne oluştururken bu paraziti parametre olarak geçirin.|

## <a name="remarks"></a>Açıklamalar

Uygulamanız için kullanışlı bir çerçeve penceresi oluşturmak `CFrameWnd`için, 'den bir sınıf türetin. Uygulamanıza özgü verileri depolamak için türemiş sınıfa üye değişkenler ekleyin. İletiler pencereye yönlendirildiğinde ne olacağını belirtmek için ileti işleyicisi üye işlevlerini ve türetilmiş sınıfta bir ileti eşlemi uygulayın.

Çerçeve penceresi oluşturmanın üç yolu vardır:

- [Doğrudan Oluştur](#create)kullanarak oluşturun.

- [LoadFrame](#loadframe)kullanarak doğrudan oluşturabilirsiniz.

- Dolaylı olarak bir belge şablonu kullanarak oluşturmak.

Birini `Create` aramadan `LoadFrame`önce , C++ **yeni** işleci kullanarak yığın üzerinde çerçeve penceresi nesnesini oluşturmanız gerekir. Aramadan `Create`önce, çerçeve için simge ve sınıf stillerini ayarlamak için [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) global işlevine bir pencere sınıfı da kaydedebilirsiniz.

Çerçevenin `Create` oluşturma parametrelerini hemen bağımsız değişken olarak geçirmek için üye işlevi kullanın.

`LoadFrame`daha `Create`az bağımsız değişken gerektirir ve bunun yerine çerçevenin resim yazısı, simge, hızlandırıcı tablosu ve menü dahil olmak üzere kaynaklardan varsayılan değerlerinin çoğunu alır. Bu kaynaklartarafından `LoadFrame`erişilebilmek için tüm kaynakların aynı kaynak kimliğine sahip olması gerekir (örneğin, IDR_MAINFRAME).

Bir `CFrameWnd` nesne görünümler ve belgeler içeriyorsa, doğrudan programcı tarafından değil, dolaylı olarak çerçeve tarafından oluşturulur. Nesne `CDocTemplate` çerçevenin oluşturulmasını, içeren görünümlerin oluşturulmasını ve görünümlerin uygun belgeye bağlantısını yönetir. `CDocTemplate` Oluşturucunun `CRuntimeClass` parametreleri ilgili üç sınıfın (belge, çerçeve ve görünüm) Bir `CRuntimeClass` nesne, kullanıcı tarafından belirtildiğinde dinamik olarak yeni çerçeveler oluşturmak için çerçeve tarafından kullanılır (örneğin, Yeni Dosya komutu veya birden çok belge arabirimi (MDI) Penceresi Yeni komutu kullanılarak).

Yukarıdaki RUNTIME_CLASS mekanizmasının `CFrameWnd` doğru çalışabilmesi için, türetilen bir çerçeve penceresi sınıfının DECLARE_DYNCREATE ile birlikte bildirilmesi gerekir.

A, `CFrameWnd` Windows için tipik bir uygulamada ana pencerenin aşağıdaki işlevlerini gerçekleştirmek için varsayılan uygulamaları içerir:

- Çerçeve `CFrameWnd` penceresi, Windows etkin penceresinden veya geçerli giriş odağından bağımsız olarak şu anda etkin olan görünümü izler. Çerçeve yeniden etkinleştirildiğinde, etkin görünüm ' i `CView::OnActivateView`arayarak bildirilir.

- Komut iletileri ve birçok ortak çerçeve bildirim iletileri, `OnSetFocus` `OnHScroll`bu `OnVScroll` tarafından `CWnd`işlenen de dahil `CFrameWnd` olmak üzere , , ve işlevleri , şu anda etkin görünümüne bir çerçeve penceresi tarafından devredilir.

- Şu anda etkin görünüm (veya bir MDI çerçevesi durumunda şu anda etkin MDI alt çerçeve penceresi) çerçeve penceresinin alt yazısını belirleyebilir. Bu özellik, çerçeve penceresinin FWS_ADDTOTITLE stil bitini kapatarak devre dışı bırakılabilir.

- Çerçeve `CFrameWnd` penceresi, çerçeve penceresinin istemci alanı içindeki denetim çubuklarının, görünümlerin ve diğer alt pencerelerin konumlandırılmasını yönetir. Çerçeve penceresi, araç çubuğunun ve diğer denetim çubuğu düğmelerinin boşta zaman güncellenmesini de yapar. Çerçeve `CFrameWnd` penceresi, araç çubuğu ve durum çubuğunda ve dışında başka bir yerde veya dışında ggling için varsayılan komutuygulamaları da vardır.

- Çerçeve `CFrameWnd` penceresi ana menü çubuğunu yönetir. Açılır menü görüntülendiğinde, çerçeve penceresi hangi menü öğelerinin etkinleştirilmesi, devre dışı edilmesi veya denetlenmesi gerektiğini belirlemek için UPDATE_COMMAND_UI mekanizmasını kullanır. Kullanıcı bir menü öğesi seçtiğinde, çerçeve penceresi durum çubuğunu bu komutun ileti dizesiyle güncelleştirir.

- `CFrameWnd` Çerçeve penceresinde klavye hızlandırıcılarını otomatik olarak çeviren isteğe bağlı bir hızlandırıcı tablosu vardır.

- Çerçeve `CFrameWnd` penceresinde, içeriğe duyarlı `LoadFrame` yardım için kullanılan isteğe bağlı bir yardım kimliği kümesi vardır. Çerçeve penceresi, bağlama duyarlı yardım (SHIFT+F1) ve yazdırma-önizleme modları gibi yarı modal durumların ana orkestratörüdür.

- Çerçeve `CFrameWnd` penceresi, Dosya Yöneticisi'nden sürüklenen ve çerçeve penceresine bırakılan bir dosyayı açar. Bir dosya uzantısı kaydedilir ve uygulamayla ilişkilendirilirse, çerçeve penceresi, kullanıcı Dosya Yöneticisi'nde bir veri dosyası açtığında veya `ShellExecute` Windows işlevi çağrıldığında oluşan dinamik veri alışverişi (DDE) açık isteğine yanıt verir.

- Çerçeve penceresi ana uygulama penceresiise (diğer `CWinThread::m_pMainWnd`bir şekilde), kullanıcı uygulamayı kapattığında, çerçeve penceresi kullanıcıdan değiştirilen `OnClose` belgeleri `OnQueryEndSession`kaydetmesini ister (için ve).

- Çerçeve penceresi ana uygulama penceresiise, çerçeve penceresi WinHelp'i çalıştırmak için bağlamdır. Çerçeve penceresini kapatmak WINHELP'i kapatır. EXE bu uygulama için yardım için başlatıldı.

Çerçeve penceresini yok etmek için C++ **silme** işleci kullanmayın. Bunun yerine `CWnd::DestroyWindow` kullanın. Pencere `CFrameWnd` yok `PostNcDestroy` edildiğinde C++ nesnesi siler. Kullanıcı çerçeve penceresini kapattığında, `OnClose` varsayılan işleyici `DestroyWindow`.

Daha fazla `CFrameWnd`bilgi için [Bkz. Çerçeve Windows.](../../mfc/frame-windows.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cframewndactivateframe"></a><a name="activateframe"></a>CFrameWnd::Etkinleştirme Çerçevesi

Çerçeve penceresini kullanıcıtarafından görünür ve kullanılabilir olacak şekilde etkinleştirmek ve geri yüklemek için bu üye işlevini arayın.

```
virtual void ActivateFrame(int nCmdShow = -1);
```

### <a name="parameters"></a>Parametreler

*nCmdShow*<br/>
CWnd geçmek için parametre [belirtir::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow). Varsayılan olarak, çerçeve gösterilir ve doğru şekilde geri yüklenir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev genellikle dde, OLE veya çerçeve penceresini veya içeriğini kullanıcıya gösterebilecek başka bir olay gibi kullanıcı dışı bir arabirim olayından sonra çağrılır.

Varsayılan uygulama çerçeveyi etkinleştirir ve Z sırasının en üstüne getirir ve gerekirse uygulamanın ana çerçeve penceresi için aynı adımları yürütür.

Çerçevenin etkinleştirilme şeklini değiştirmek için bu üye işlevi geçersiz kılın. Örneğin, MDI alt pencerelerini en üst düzeye çıkarmaya zorlayabilirsiniz. Uygun işlevselliği ekleyin, ardından taban sınıf sürümünü açık bir *nCmdShow*ile arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]

## <a name="cframewndbeginmodalstate"></a><a name="beginmodalstate"></a>CFrameWnd::BeginModalState

Bir çerçeve penceresi modal yapmak için bu üye işlevi arayın.

```
virtual void BeginModalState();
```

## <a name="cframewndcframewnd"></a><a name="cframewnd"></a>CFrameWnd::CFrameWnd

Bir `CFrameWnd` nesne oluşturur, ancak görünür çerçeve penceresi oluşturmaz.

```
CFrameWnd();
```

### <a name="remarks"></a>Açıklamalar

Görünür `Create` pencereyi oluşturmak için arayın.

## <a name="cframewndcreate"></a><a name="create"></a>CFrameWnd::Oluştur

`CFrameWnd` Nesneyle ilişkili Windows çerçeve penceresi oluşturmak ve başlatmayı arayın.

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
Windows sınıfını isimleyen geçersiz sonlandırılmış karakter dizesini işaret edin. Sınıf `AfxRegisterWndClass` adı, genel işlevveya `RegisterClass` Windows işlevine kayıtlı herhangi bir ad olabilir. NULL ise, önceden tanımlanmış `CFrameWnd` varsayılan öznitelikleri kullanır.

*lpszWindowName*<br/>
Pencere adını temsil eden null-sonlandırılan karakter dizesini gösterir. Başlık çubuğu için metin olarak kullanılır.

*Dwstyle*<br/>
Pencere [stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) özniteliklerini belirtir. Başlık çubuğunun pencerede temsil edilen belgenin adını otomatik olarak görüntülemesini istiyorsanız FWS_ADDTOTITLE stilini ekleyin.

*Rect*<br/>
Pencerenin boyutunu ve konumunu belirtir. *rectDefault* değeri, Windows'un yeni pencerenin boyutunu ve konumunu belirtmesine olanak tanır.

*pParentWnd*<br/>
Bu çerçeve penceresinin ana penceresini belirtir. Bu parametre üst düzey çerçeve pencereleri için NULL olmalıdır.

*lpszMenuName*<br/>
Pencereyle birlikte kullanılacak menü kaynağının adını tanımlar. Menüde dize yerine tamsayı kimliği varsa MAKEINTRESOURCE'ı kullanın. Bu parametre NULL olabilir.

*dwExStyle*<br/>
Pencere genişletilmiş [stil](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) özniteliklerini belirtir.

*Pcontext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısıiçin bir işaretçi belirtir. Bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir `CFrameWnd` nesneyi iki adımda oluştur. İlk olarak, `CFrameWnd` nesneyi oluşturan oluşturucuyu çağırın `Create`ve ardından Windows çerçeve penceresini oluşturan `CFrameWnd` ve nesneye iliştiren ", " çağırın. `Create`pencerenin sınıf adını ve pencere adını aparat eder ve stili, üst öğesi ve ilişkili menüsü için varsayılan değerleri kaydeder.

Bağımsız değişkenlerini belirtmek yerine çerçeve penceresini kaynaktan yüklemek yerine kullanın. `LoadFrame` `Create`

## <a name="cframewndcreateview"></a><a name="createview"></a>CFrameWnd::CreateView

Çerçeve `CreateView` içinde görünüm oluşturmak için arayın.

```
CWnd* CreateView(
    CCreateContext* pContext,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>Parametreler

*Pcontext*<br/>
Görünüm ve belge türünü belirtir.

*Nıd*<br/>
Görünümün kimlik numarası.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CWnd` nesneye işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bir çerçeve içinde türetilmiş olmayan `CView`"görünümler" oluşturmak için bu üye işlevi kullanın. Aradıktan `CreateView`sonra, görünümü el ile etkin olarak ayarlamalı ve görünür olacak şekilde ayarlamanız gerekir; bu görevler otomatik olarak `CreateView`.

## <a name="cframewnddockcontrolbar"></a><a name="dockcontrolbar"></a>CFrameWnd::DockControlBar

Denetim çubuğunun çerçeve penceresine sabitlenebedilmesine neden olur.

```cpp
void DockControlBar(
    CControlBar* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
Kenetlenecek kontrol çubuğunu işaret edin.

*nDockBarID*<br/>
Yerleştirme için çerçeve penceresinin hangi taraflarını göz önünde bulundurması gerektiğini belirler. 0 veya aşağıdakilerden biri veya daha fazlası olabilir:

- AFX_IDW_DOCKBAR_TOP Çerçeve penceresinin üst tarafına dock.

- AFX_IDW_DOCKBAR_BOTTOM Çerçeve penceresinin alt tarafına sabitle.

- AFX_IDW_DOCKBAR_LEFT Çerçeve penceresinin sol tarafına dock.

- AFX_IDW_DOCKBAR_RIGHT Çerçeve penceresinin sağ tarafına sabitle.

0 ise, kontrol çubuğu hedef çerçeve penceresine yerleştirme için etkin olan herhangi bir tarafa sabitlenebilir.

*Lprect*<br/>
Ekran koordinatlarında, kontrol çubuğunun hedef çerçeve penceresinin istemci olmayan alanına nerede kenetleneceğini belirler.

### <a name="remarks"></a>Açıklamalar

Denetim çubuğu, hem [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) hem de [CFrameWnd::EnableDocking'e](#enabledocking)yapılan aramalarda belirtilen çerçeve penceresinin kenarlarından birine sabitlenir. Seçilen yan *nDockBarID*tarafından belirlenir.

## <a name="cframewndenabledocking"></a><a name="enabledocking"></a>CFrameWnd::Etkinleştirme Docking

Çerçeve penceresinde takılabilir denetim çubuklarını etkinleştirmek için bu işlevi çağırın.

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parametreler

*dwDockStyle*<br/>
Çerçeve penceresinin hangi taraflarının denetim çubukları için yerleştirme siteleri olarak hizmet edebileceğini belirtir. Aşağıdakilerden biri veya birkaçı olabilir:

- CBRS_ALIGN_TOP İstemci alanının üst kısmında kenetlenme sağlar.

- CBRS_ALIGN_BOTTOM İstemci alanının altına kenetlenmeyi sağlar.

- CBRS_ALIGN_LEFT İstemci alanının sol tarafına kenetlenmeyi sağlar.

- CBRS_ALIGN_RIGHT İstemci alanının sağ tarafına kenetlenmeyi sağlar.

- CBRS_ALIGN_ANY İstemci alanının herhangi bir tarafına kenetlenmeyi sağlar.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, denetim çubukları aşağıdaki sırada çerçeve penceresinin bir tarafına sabitlenir: üst, alt, sol, sağ.

### <a name="example"></a>Örnek

  CToolBar örneğine [bakın:Oluştur](../../mfc/reference/ctoolbar-class.md#create).

## <a name="cframewndendmodalstate"></a><a name="endmodalstate"></a>CFrameWnd::EndModalState

Bir çerçeve penceresini modal'dan modeless'a değiştirmek için bu üye işlevini arayın.

```
virtual void EndModalState();
```

### <a name="remarks"></a>Açıklamalar

`EndModalState`[BeginModalState](#beginmodalstate)tarafından devre dışı bırakılan tüm pencereleri etkinleştirir.

## <a name="cframewndfloatcontrolbar"></a><a name="floatcontrolbar"></a>CFrameWnd::FloatControlBar

Bir denetim çubuğunun çerçeve penceresine sabitlenmemesi için bu işlevi çağırın.

```cpp
void FloatControlBar(
    CControlBar* pBar,
    CPoint point,
    DWORD dwStyle = CBRS_ALIGN_TOP);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
Yüzdürilecek kontrol çubuğuna işaret edin.

*Nokta*<br/>
Kontrol çubuğunun sol üst köşesinin yerleştirileceği ekran koordinatlarında konum.

*Dwstyle*<br/>
Denetim çubuğunu yeni çerçeve penceresi içinde yatay mı yoksa dikey olarak mı hizalayacağını belirtir. Aşağıdakilerden herhangi biri olabilir:

- CBRS_ALIGN_TOP Kontrol çubuğunu dikey olarak yönlendirir.

- CBRS_ALIGN_BOTTOM Kontrol çubuğunu dikey olarak yönlendirir.

- CBRS_ALIGN_LEFT Kontrol çubuğunu yatay olarak yönlendirir.

- CBRS_ALIGN_RIGHT Yönler kontrol çubuğu yatay.

Hem yatay hem de dikey yönlendirmeyi belirten stiller geçilirse, araç çubuğu yatay olarak yönlendirilir.

### <a name="remarks"></a>Açıklamalar

Genellikle, program önceki yürütme ayarları geri olduğunda bu uygulama başlangıç yapılır.

Bu işlev, kullanıcı sol fare düğmesini bırakarak bir bırakma işlemine neden olduğunda, denetim çubuğunu yerleştirme için kullanılamayan bir konumun üzerine sürüklerek çerçeve tarafından çağrılır.

## <a name="cframewndgetactivedocument"></a><a name="getactivedocument"></a>CFrameWnd::GetActiveDocument

Geçerli etkin görünüme bağlı akımiçin `CDocument` bir işaretçi almak için bu üye işlevi arayın.

```
virtual CDocument* GetActiveDocument();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli [CDocument](../../mfc/reference/cdocument-class.md)için bir işaretçi . Geçerli bir belge yoksa NULL döndürür.

## <a name="cframewndgetactiveframe"></a><a name="getactiveframe"></a>CFrameWnd::GetActiveFrame

MDI çerçeve penceresinin etkin çoklu belge arabirimi (MDI) alt penceresine işaretçi almak için bu üye işlevi arayın.

```
virtual CFrameWnd* GetActiveFrame();
```

### <a name="return-value"></a>Dönüş Değeri

Etkin MDI alt penceresiiçin bir işaretçi. Uygulama bir SDI uygulamasıysa veya MDI çerçeve penceresi etkin bir belgeye sahip değilse, **örtük bu** işaretçi döndürülür.

### <a name="remarks"></a>Açıklamalar

Etkin Bir MDI alt alanı yoksa veya uygulama tek bir belge arabirimi (SDI) ise, **örtük bu** işaretçi döndürülür.

## <a name="cframewndgetactiveview"></a><a name="getactiveview"></a>CFrameWnd::GetActiveView

Bir çerçeve penceresine bağlı etkin görünüm (varsa) için bir işaretçi `CFrameWnd`almak için bu üye işlevi arayın ( ).

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli [CView](../../mfc/reference/cview-class.md)için bir işaretçi . Geçerli görünüm yoksa NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, MDI ana çerçeve penceresi `CMDIFrameWnd`için çağrıldığında NULL döndürür ( ). Bir MDI uygulamasında, MDI ana çerçeve penceresi ile ilişkili bir görünüm yok. Bunun yerine, her `CMDIChildWnd`bir alt pencere ( ) bir veya daha fazla ilişkili görünümleri vardır. Bir MDI uygulamasındaki etkin görünüm, önce etkin MDI alt penceresi nin bulunması ve ardından bu alt pencerenin etkin görünümünü niçin bularak elde edilebilir. Etkin MDI alt penceresi işlevi `MDIGetActive` arayarak `GetActiveFrame` veya aşağıdaki lerde gösterildiği gibi bulunabilir:

[!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]

## <a name="cframewndgetcontrolbar"></a><a name="getcontrolbar"></a>CFrameWnd::GetControlBar

Kimlikle ilişkili denetim çubuğuna erişmek için arayın. `GetControlBar`

```
CControlBar* GetControlBar(UINT nID);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Kontrol çubuğunun kimlik numarası.

### <a name="return-value"></a>Dönüş Değeri

Kimlikle ilişkili denetim çubuğuna işaretçi.

### <a name="remarks"></a>Açıklamalar

*nID* parametresi, denetim `Create` çubuğunun yöntemine geçirilen benzersiz tanımlayıcıyı ifade eder. Denetim çubukları hakkında daha fazla bilgi için Denetim [Çubukları](../../mfc/control-bars.md)başlıklı konuya bakın.

`GetControlBar`yüzer ve bu nedenle şu anda çerçevenin bir alt penceresi olmasa bile denetim çubuğu döndürecektir.

## <a name="cframewndgetdockstate"></a><a name="getdockstate"></a>CFrameWnd::GetDockState

Çerçeve penceresinin denetim çubukları hakkındaki durum bilgilerini bir `CDockState` nesnede depolamak için bu üye işlevi arayın.

```cpp
void GetDockState(CDockState& state) const;
```

### <a name="parameters"></a>Parametreler

*durum*<br/>
Döndükten sonra çerçeve penceresinin denetim çubuklarının geçerli durumunu içerir.

### <a name="remarks"></a>Açıklamalar

Daha sonra kullanarak depolama `CDockState` `CDockState::SaveState` ya da `Serialize`içeriğini yazabilirsiniz. Daha sonra denetim çubuklarını önceki bir duruma geri yüklemek `CDockState::LoadState` `Serialize`istiyorsanız, `SetDockState` durumu yükleyin veya , önceki durumu çerçeve penceresinin denetim çubuklarına uygulamak için arayın.

## <a name="cframewndgetmenubarstate"></a><a name="getmenubarstate"></a>CFrameWnd::GetMenuBarState

Geçerli MFC uygulamasında menünün görüntü durumunu alır.

```
virtual DWORD GetMenuBarState();
```

### <a name="return-value"></a>Dönüş Değeri

İade değeri aşağıdaki değerlere sahip olabilir:

- AFX_MBS_VISIBLE (0x01) - Menü görünür.

- AFX_MBS_HIDDEN (0x02) - Menü gizlidir.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı hatası oluşursa, bu yöntem Hata Ayıklama modunda öne çıkar ve [CException](../../mfc/reference/cexception-class.md) sınıfından türetilen bir özel durum ortaya çıkarır.

## <a name="cframewndgetmenubarvisibility"></a><a name="getmenubarvisibility"></a>CFrameWnd::GetMenuBarVisibility

Geçerli MFC uygulamasındaki menünün varsayılan durumunun gizli mi yoksa görünür mü olduğunu gösterir.

```
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem aşağıdaki değerlerden birini döndürür:

- AFX_MBV_KEEPVISIBLE (0x01) - Menü her zaman görüntülenir ve varsayılan olarak odak noktası yoktur.

- AFX_MBV_DISPLAYONFOCUS (0x02) - Menü varsayılan olarak gizlidir. Menü gizliyse, menüyü görüntülemek ve odağı vermek için ALT tuşuna basın. Menü görüntüleniyorsa, gizlemek için ALT veya ESC tuşuna basın.

- AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04) (bitwise kombinasyonu (VEYA)) - Menü varsayılan olarak gizlidir. Menü gizliyse, menüyü görüntülemek ve odağı vermek için F10 tuşuna basın. Menü görüntülenirse, menüdeki veya menüden odağı kaydırmak için F10 tuşuna basın. Menü, gizlemek için ALT veya ESC tuşuna basana kadar görüntülenir.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı hatası oluşursa, bu yöntem Hata Ayıklama modunda öne çıkar ve [CException](../../mfc/reference/cexception-class.md) sınıfından türetilen bir özel durum ortaya çıkarır.

## <a name="cframewndgetmessagebar"></a><a name="getmessagebar"></a>CFrameWnd::GetMessageBar

Durum çubuğuna bir işaretçi almak için bu üye işlevi arayın.

```
virtual CWnd* GetMessageBar();
```

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu penceresine işaretçi.

## <a name="cframewndgetmessagestring"></a><a name="getmessagestring"></a>CFrameWnd::GetMessageString

Komut iÞleri iÞlisi için özel dizeli ler sağlamak için bu işlevi geçersiz kıntır.

```
virtual void GetMessageString(
    UINT nID,
    CString& rMessage) const;
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
İstenilen iletinin kaynak kimliği.

*rMessage*<br/>
`CString`iletiyi yerleştirmek için nesne.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, kaynak dosyasından *nID* tarafından belirtilen dizeyi yükler. Durum çubuğundaki ileti dizesinin güncelleştirilmesi gerektiğinde, bu işlev çerçeve tarafından çağrılır.

## <a name="cframewndgettitle"></a><a name="gettitle"></a>CFrameWnd::GetTitle

Pencere nesnesinin başlığını alır.

```
CString GetTitle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pencere nesnesinin geçerli başlığını içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

## <a name="cframewndinitialupdateframe"></a><a name="initialupdateframe"></a>CFrameWnd::InitialUpdateFrame

Yeni `IntitialUpdateFrame` bir çerçeve oluşturduktan sonra `Create`arayın.

```cpp
void InitialUpdateFrame(
    CDocument* pDoc,
    BOOL bMakeVisible);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Çerçeve penceresinin ilişkili olduğu belgeyi işaret ediyor. NULL olabilir.

*bMakeVisible*<br/>
TRUE ise, çerçevenin görünür ve etkin hale gelmesi gerektiğini gösterir. FALSE ise, hiçbir torunları görünür hale getirilir.

### <a name="remarks"></a>Açıklamalar

Bu, bu çerçeve penceresindeki tüm `OnInitialUpdate` görünümlerinin çağrılarını almasına neden olur.

Ayrıca, daha önce etkin bir görünüm yoksa, çerçeve penceresinin birincil görünümü etkin hale getirilir. Birincil görünüm, AFX_IDW_PANE_FIRST çocuk kimliğine sahip bir görünümdür. Son olarak, *bMakeVisible* sıfır değilse çerçeve penceresi görünür hale getirilir. *bMakeVisible* 0 ise, çerçeve penceresinin geçerli odak ve görünür durumu değişmeden kalır. Dosya Yeni ve Dosya Aç'ın çerçevesinin uygulamasını kullanırken bu işlevi aramak gerekli değildir.

## <a name="cframewndinmodalstate"></a><a name="inmodalstate"></a>CFrameWnd::InModalState

Çerçeve penceresinin modal veya modeless olup olmadığını kontrol etmek için bu üye işlevi arayın.

```
BOOL InModalState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız ise evet; aksi takdirde 0.

## <a name="cframewndistracking"></a><a name="istracking"></a>CFrameWnd::IsTracking

Penceredeki ayırıcı çubuğunun şu anda taşınıp taşınmamakta olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsTracking() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir ayırıcı işlemi devam ediyorsa sıfır olmayan; aksi takdirde 0.

## <a name="cframewndloadacceltable"></a><a name="loadacceltable"></a>CFrameWnd::LoadAccelTable

Belirtilen hızlandırıcı tablosunu yüklemek için arayın.

```
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Hızlandırıcı kaynağının adını tanımlar. Kaynak bir sonda kimliğiyle tanımlanırsa MAKEINTRESOURCE'ı kullanın.

### <a name="return-value"></a>Dönüş Değeri

Hızlandırıcı tablosu başarıyla yüklenmişse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Aynı anda yalnızca bir tablo yüklenebilir.

Kaynaklardan yüklenen hızlandırıcı tabloları, uygulama sona erdiğinde otomatik olarak serbest bırakılır.

Çerçeve penceresi `LoadFrame` oluşturmak için ararsanız, çerçeve menü ve simge kaynakları ile birlikte bir hızlandırıcı tablo yükler ve bu üye işlevi için sonraki bir çağrı sonra gereksizdir.

## <a name="cframewndloadbarstate"></a><a name="loadbarstate"></a>CFrameWnd::LoadBarState

Çerçeve penceresine ait her denetim çubuğunun ayarlarını geri yüklemek için bu işlevi arayın.

```cpp
void LoadBarState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
Başlatma (INI) dosyasındaki bir bölümün veya durum bilgilerinin depolandığı Windows kayıt defterindeki bir anahtarın adı.

### <a name="remarks"></a>Açıklamalar

Geri yüklenen bilgiler görünürlük, yatay/dikey yönlendirme, yerleştirme durumu ve kontrol çubuğu konumunu içerir.

Geri yüklemek istediğiniz ayarlar, aramadan `LoadBarState`önce kayıt defterine yazılmalıdır. [CWinApp::SetRegistryKey'i](../../mfc/reference/cwinapp-class.md#setregistrykey)arayarak bilgileri kayıt defterine yazın. [SaveBarState'i](#savebarstate)arayarak bilgileri INI dosyasına yazın.

## <a name="cframewndloadframe"></a><a name="loadframe"></a>CFrameWnd::LoadFrame

Kaynak bilgilerinden dinamik olarak bir çerçeve penceresi oluşturmak için arayın.

```
virtual BOOL LoadFrame(
    UINT nIDResource,
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,
    CWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parametreler

*nIDKaynak*<br/>
Çerçeve penceresiile ilişkili paylaşılan kaynakların kimliği.

*dwDefaultStyle*<br/>
Çerçevenin [stili.](../../mfc/reference/styles-used-by-mfc.md#window-styles) Başlık çubuğunun pencerede temsil edilen belgenin adını otomatik olarak görüntülemesini istiyorsanız FWS_ADDTOTITLE stilini ekleyin.

*pParentWnd*<br/>
Çerçevenin üst öğesiiçin bir işaretçi.

*Pcontext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısıiçin bir işaretçi. Bu parametre NULL olabilir.

### <a name="remarks"></a>Açıklamalar

Bir `CFrameWnd` nesneyi iki adımda oluştur. İlk olarak, `CFrameWnd` nesneyi oluşturan oluşturucuyu çağırın `LoadFrame`ve ardından Windows çerçeve penceresini ve ilişkili kaynakları `CFrameWnd` yükleyen ve çerçeve penceresini nesneye ekleyen " çağırın. *nIDResource* parametresi, çerçeve penceresi için başlığın menü, hızlandırıcı tablosu, simgesi ve dize kaynağını belirtir.

Çerçeve `Create` penceresinin oluşturma `LoadFrame` parametrelerinin tümlerini belirtmek istediğinizde yerine üye işlevi kullanın.

Çerçeve, `LoadFrame` belge şablonu nesnesini kullanarak bir çerçeve penceresi oluşturduğunda çağırır.

Çerçeve, içerdiği görünüm nesneleri de dahil olmak üzere çerçeve penceresine bağlanacak nesneleri belirtmek için *pContext* bağımsız değişkenini kullanır. 'yi aradiğinizde `LoadFrame` *pContext* bağımsız değişkenini NULL olarak ayarlayabilirsiniz.

## <a name="cframewndm_bautomenuenable"></a><a name="m_bautomenuenable"></a>CFrameWnd::m_bAutoMenuEnable

Bu veri üyesi etkinleştirildiğinde (varsayılan olan), kullanıcı bir menü aşağı çektiğinde ON_UPDATE_COMMAND_UI veya ON_COMMAND işleyicileri olmayan menü öğeleri otomatik olarak devre dışı bırakılır.

```
BOOL m_bAutoMenuEnable;
```

### <a name="remarks"></a>Açıklamalar

ON_COMMAND işleyicisi olan ancak ON_UPDATE_COMMAND_UI işleyicisi olmayan menü öğeleri otomatik olarak etkinleştirilir.

Bu veri üyesi ayarlandığında, menü öğeleri araç çubuğu düğmelerinin etkin olduğu şekilde otomatik olarak etkinleştirilir.

> [!NOTE]
> `m_bAutoMenuEnable`üst düzey menü öğeleri üzerinde hiçbir etkisi yoktur.

Bu veri üyesi, geçerli seçimi temel alarak isteğe bağlı komutların uygulanmasını kolaylaştırır ve menü öğelerini etkinleştirmek ve devre dışı bırakmak için ON_UPDATE_COMMAND_UI işleyicileri yazma gereksinimini azaltır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]

## <a name="cframewndnegotiateborderspace"></a><a name="negotiateborderspace"></a>CFrameWnd::NegotiateBorderSpace

OLE inplace etkinleştirme sırasında bir çerçeve penceresinde kenarlık alanı müzakere etmek için bu üye işlevi arayın.

```
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,
    LPRECT lpRectBorder);
```

### <a name="parameters"></a>Parametreler

*nBorderCmd*<br/>
Aşağıdaki değerlerden birini `enum BorderCmd`içerir:

- `borderGet`= 1 olarak

- `borderRequest`= 2

- `borderSet`= 3

*lpRectBorder*<br/>
Bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına veya kenarlığın koordinatlarını belirten bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işlecemez.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev `CFrameWnd` OLE sınır alanı müzakeresinin uygulanmasıdır.

## <a name="cframewndonbarcheck"></a><a name="onbarcheck"></a>CFrameWnd::OnBarCheck

Belirtilen denetim çubuğunda bir eylem yapıldığında çağrılır.

```
afx_msg BOOL OnBarCheck(UINT nID);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Denetim çubuğunun kimliği gösteriliyor.

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu varsa sıfırolmayan; aksi takdirde 0.

## <a name="cframewndoncontexthelp"></a><a name="oncontexthelp"></a>CFrameWnd::OnContextHelp

Yerinde öğeler için SHIFT+F1 Yardım'ı işler.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Açıklamalar

İçeriğe duyarlı yardımı etkinleştirmek için,

[!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]

sınıf ileti `CFrameWnd` eşleme ve ayrıca bu üye işlevi etkinleştirmek için bir hızlandırıcı tablo girişi ( genellikle SHIFT +F1) ekleyin.

Uygulamanız bir OLE Kapsayıcısıysa, `OnContextHelp` çerçeve penceresi nesnesi içinde bulunan tüm yerinde öğeleri Yardım moduna koyar. İmleç bir ok ve soru işaretine dönüşür ve kullanıcı daha sonra fare işaretçisini taşıyabilir ve iletişim kutusu, pencere, menü veya komut düğmesini seçmek için sol fare düğmesine basabilir. Bu üye işlev, `WinHelp` imlecin altındaki nesnenin Yardım bağlamıyla Windows işlevini çağırır.

## <a name="cframewndoncreateclient"></a><a name="oncreateclient"></a>CFrameWnd::OnCreateClient

Yürütme sırasında çerçeve tarafından `OnCreate`çağrılan .

```
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,
    CCreateContext* pContext);
```

### <a name="parameters"></a>Parametreler

*lpcs*<br/>
Windows [CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) yapısıiçin bir işaretçi.

*Pcontext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısıiçin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi asla arama.

Bu işlevin varsayılan uygulaması, `CView` mümkünse *pContext'da*sağlanan bilgilerden bir nesne oluşturur.

`CCreateContext` Nesnede geçirilen değerleri geçersiz kılmak veya çerçeve penceresinin ana istemci alanında yol denetimlerini değiştirmek için bu işlevi geçersiz kılın. Geçersiz `CCreateContext` kılabileceğiniz üyeler [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) sınıfında açıklanmıştır.

> [!NOTE]
> Yapıda geçirilen değerleri `CREATESTRUCT` değiştirmeyin. Bunlar yalnızca bilgilendirme amaçlıdır. Örneğin, ilk pencere dikdörtgenini geçersiz kılmak istiyorsanız, `CWnd` [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow)üye işlevini geçersiz kılın.

## <a name="cframewndonhidemenubar"></a><a name="onhidemenubar"></a>CFrameWnd::OnHideMenuBar

Sistem geçerli MFC uygulamasında menü çubuğunu gizlemek üzereyken bu işlev çağrılır.

```
virtual void OnHideMenuBar();
```

### <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi, sistem menüyü gizlemek üzereyken uygulamanızın özel eylemler gerçekleştirmesini sağlar. Menünün gizlenmesini engelleyemezsiniz, ancak örneğin menü stilini veya durumu almak için diğer yöntemleri arayabilirsiniz.

## <a name="cframewndonsetpreviewmode"></a><a name="onsetpreviewmode"></a>CFrameWnd::OnSetPreviewMode

Uygulamanın ana çerçeve penceresini yazdırma önizleme moduna girip çıkmak için bu üye işlevini arayın.

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>Parametreler

*bÖnizleme*<br/>
Uygulamayı yazdırma önizleme moduna yerleştirip yerleştirmeyini belirtir. Yazdırma önizlemesine yerleştirilecek TRUE, önizleme modunu iptal etmek için FALSE olarak ayarlayın.

*pDevlet*<br/>
Bir yapıiçin `CPrintPreviewState` bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama tüm standart araç çubuklarını devre dışı kalır ve ana menüyü ve ana istemci penceresini gizler. Bu, MDI çerçeve pencerelerini geçici SDI çerçeve pencerelerine dönüştürür.

Yazdırma önizlemesi sırasında denetim çubuklarının ve diğer çerçeve pencere parçalarının gizlenme ve gösterilmesini özelleştirmek için bu üye işlevi geçersiz kılın. Geçersiz kılınan sürümden taban sınıf uygulamasını çağırın.

## <a name="cframewndonshowmenubar"></a><a name="onshowmenubar"></a>CFrameWnd::OnShowMenuBar

Sistem geçerli MFC uygulamasında menü çubuğunu görüntülemek üzereyken bu işlev çağrılır.

```
virtual void OnShowMenuBar();
```

### <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi, menü görüntülenmek üzereyken uygulamanızın özel eylemler gerçekleştirmesini sağlar. Menünün görüntülenmesini engelleyemezsiniz, ancak örneğin menü stilini veya durumu almak için diğer yöntemleri arayabilirsiniz.

## <a name="cframewndonupdatecontrolbarmenu"></a><a name="onupdatecontrolbarmenu"></a>CFrameWnd::OnUpdateControlBarMenu

İlişkili menü güncelleştirildiğinde çerçeve tarafından çağrılır.

```
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Güncelleştirme komutunu oluşturan menüyü temsil eden [ccmdUI](../../mfc/reference/ccmdui-class.md) nesnesine işaretçi. Güncelleştirme işleyicisi, kullanıcı arabirimini güncelleştirmek için *pCmdUI* aracılığıyla nesnenin `CCmdUI` [Üye](../../mfc/reference/ccmdui-class.md#enable) İşleyiş etkinleştir işlevini çağırır.

## <a name="cframewndrecalclayout"></a><a name="recalclayout"></a>CFrameWnd::RecalcLayout

Standart denetim çubukları üzerinde veya kapalı veya çerçeve penceresi yeniden boyutlandırılır zaman çerçeve tarafından çağrılır.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parametreler

*bNotify*<br/>
Çerçeve penceresi için etkin yerinde öğenin düzen değişikliği bildirimini alıp almadığını belirler. DOĞRUysa, öğe bildirilir; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin varsayılan `CWnd` uygulaması, `RepositionBars` çerçevedeki ve ana istemci penceresindeki (genellikle bir `CView` veya MDICLIENT) tüm denetim çubuklarını yeniden konumlandırmak için üye işlevi çağırır.

Çerçeve penceresinin düzeni değiştikten sonra denetim çubuklarının görünümünü ve davranışını denetlemek için bu üye işlevi geçersiz kılın. Örneğin, denetim çubuklarını açtığınızda veya kapattığınızda veya başka bir denetim çubuğu eklediğinizde arayın.

## <a name="cframewndrectdefault"></a><a name="rectdefault"></a>CFrameWnd::rectVarsayılan

Windows'un `CRect` pencerenin başlangıç boyutunu ve konumunu seçmesine izin vermek için bir pencere oluştururken bu paraziti parametre olarak geçirin.

```
static AFX_DATA const CRect rectDefault;
```

## <a name="cframewndsavebarstate"></a><a name="savebarstate"></a>CFrameWnd::SaveBarState

Çerçeve penceresine ait her denetim çubuğu yla ilgili bilgileri depolamak için bu işlevi arayın.

```cpp
void SaveBarState(LPCTSTR lpszProfileName) const;
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
Başlatma dosyasındaki bir bölümün veya durum bilgilerinin depolandığı Windows kayıt defterindeki bir anahtarın adı.

### <a name="remarks"></a>Açıklamalar

Bu bilgiler [LoadBarState](#loadbarstate)kullanarak başlatma dosyasından okunabilir. Depolanan bilgiler görünürlük, yatay/dikey yönlendirme, yerleştirme durumu ve kontrol çubuğu konumunu içerir.

## <a name="cframewndsetactivepreviewview"></a><a name="setactivepreviewview"></a>CFrameWnd::SetActivePreviewView

Belirtilen görünümü Zengin Önizleme için etkin görünüm olarak belirtir.

```cpp
void SetActivePreviewView(CView* pViewNew);
```

### <a name="parameters"></a>Parametreler

*pViewNew*<br/>
Etkinleştirilecek bir görünüm için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cframewndsetactiveview"></a><a name="setactiveview"></a>CFrameWnd::SetActiveView

Etkin görünümü ayarlamak için bu üye işlevi arayın.

```cpp
void SetActiveView(
    CView* pViewNew,
    BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parametreler

*pViewNew*<br/>
Etkin bir görünüm için bir [CView](../../mfc/reference/cview-class.md) nesnesine işaretçi veya NULL belirtir.

*bNotify*<br/>
Görünümün etkinleştirmeden haberdar edilip edilmeyeceğini belirtir. TRUE ise, `OnActivateView` yeni görünüm için çağrılır; FALSE ise, öyle değildir.

### <a name="remarks"></a>Açıklamalar

Kullanıcı odağı çerçeve penceresi içindeki bir görünüme değiştirdiğinde çerçeve bu işlevi otomatik olarak çağırır. Odağı belirtilen görünüme değiştirmek için açıkça arayabilirsiniz. `SetActiveView`

## <a name="cframewndsetdockstate"></a><a name="setdockstate"></a>CFrameWnd::SetDockState

`CDockState` Bir nesnede depolanan durum bilgilerini çerçeve penceresinin denetim çubuklarına uygulamak için bu üye işlevi arayın.

```cpp
void SetDockState(const CDockState& state);
```

### <a name="parameters"></a>Parametreler

*durum*<br/>
Depolanan durumu çerçeve penceresinin denetim çubuklarına uygulayın.

### <a name="remarks"></a>Açıklamalar

Denetim çubuklarının önceki durumunu geri yüklemek için, depolanan `CDockState::LoadState` `Serialize`durumu yükleyebilir veya çerçeve penceresinin denetim çubuklarına uygulamak için kullanabilirsiniz. `SetDockState` Önceki durum `CDockState` ile nesnede depolanır`GetDockState`

## <a name="cframewndsetmenubarstate"></a><a name="setmenubarstate"></a>CFrameWnd::SetMenuBarState

Geçerli MFC uygulamasındaki menünün ekran durumunu gizli veya görüntülenecek şekilde ayarlar.

```
virtual BOOL SetMenuBarState(DWORD nState);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Nstate*|[içinde] Menüyü görüntülemek veya gizlemek için belirtir. *nState* parametresi aşağıdaki değerlere sahip olabilir:<br /><br />- AFX_MBS_VISIBLE (0x01) - Menü gizliyse görüntülenir, ancak görünürse hiçbir etkisi yoktur.<br />- AFX_MBS_HIDDEN (0x02) - Görünürse menüyü gizler, ancak gizliyse hiçbir etkisi yoktur.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem menü durumunu başarıyla değiştirirse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı hatası oluşursa, bu yöntem Hata Ayıklama modunda öne çıkar ve [CException](../../mfc/reference/cexception-class.md) sınıfından türetilen bir özel durum ortaya çıkarır.

## <a name="cframewndsetmenubarvisibility"></a><a name="setmenubarvisibility"></a>CFrameWnd::SetMenuBarVisibility

Geçerli MFC uygulamasındaki menünün varsayılan davranışını gizli veya görünür olarak ayarlar.

```
virtual void SetMenuBarVisibility(DWORD nStyle);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*nStyle*|[içinde] Menünün varsayılan olarak gizli olup olmadığını veya görünür olup olmadığını ve odağı olup olmadığını belirtir. *nStyle* parametresi aşağıdaki değerlere sahip olabilir:<br /><br />- AFX_MBV_KEEPVISIBLE (0x01) -<br />     Menü her zaman görüntülenir ve varsayılan olarak odak noktası yoktur.<br />- AFX_MBV_DISPLAYONFOCUS (0x02) -<br />     Menü varsayılan olarak gizlenir. Menü gizliyse, menüyü görüntülemek ve odağı vermek için ALT tuşuna basın. Menü görüntüleniyorsa, menüyü gizlemek için ALT veya ESC tuşuna basın.<br />- AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04)<br />     (bitwise kombinasyonu (VEYA)) - Menü varsayılan olarak gizlidir. Menü gizliyse, menüyü görüntülemek ve odağı vermek için F10 tuşuna basın. Menü görüntülenirse, menüdeki veya menüden odağı kaydırmak için F10 tuşuna basın. Menü, gizlemek için ALT veya ESC tuşuna basana kadar görüntülenir.|

### <a name="remarks"></a>Açıklamalar

*nStyle* parametresinin değeri geçerli değilse, bu yöntem Hata Ayıklama modunda ileri sürülür ve Sürüm modunda [CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md) yükseltir. Diğer çalışma zamanı hataları durumunda, bu yöntem Hata Ayıklama modunda ileri sürüler ve [CException](../../mfc/reference/cexception-class.md) sınıfından türetilen bir özel durum yükseltir.

Bu yöntem, Windows Vista ve daha sonra için yazılmış uygulamalarda menülerin durumunu etkiler.

## <a name="cframewndsetmessagetext"></a><a name="setmessagetext"></a>CFrameWnd::SetMessageText

0 kimliği olan durum çubuğu bölmesine bir dize yerleştirmek için bu işlevi arayın.

```cpp
void SetMessageText(LPCTSTR lpszText);
void SetMessageText(UINT nID);
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
Durum çubuğuna yerleştirilecek dizeyi işaret edin.

*Nıd*<br/>
Durum çubuğuna yerleştirilecek dize dize kaynak kimliği.

### <a name="remarks"></a>Açıklamalar

Bu genellikle durum çubuğunun en sol ve en uzun bölmesidir.

## <a name="cframewndsetprogressbarposition"></a><a name="setprogressbarposition"></a>CFrameWnd::SetProgressBarPosition

Görev çubuğunda görüntülenen Windows 7 ilerleme çubuğunun geçerli konumunu ayarlar.

```cpp
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>Parametreler

*nProgressPos*<br/>
Ayarlanacak konumu belirtir. Tarafından belirlenen aralıkta `SetProgressBarRange`olmalıdır.

### <a name="remarks"></a>Açıklamalar

## <a name="cframewndsetprogressbarrange"></a><a name="setprogressbarrange"></a>CFrameWnd::SetProgressBarRange

Görev çubuğunda görüntülenen Windows 7 ilerleme çubuğunun aralığını ayarlar.

```cpp
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>Parametreler

*nRangeMin*<br/>
Minimum değer.

*nRangeMax*<br/>
Maksimal değer.

### <a name="remarks"></a>Açıklamalar

## <a name="cframewndsetprogressbarstate"></a><a name="setprogressbarstate"></a>CFrameWnd::SetProgressBarState

Görev çubuğu düğmesinde görüntülenen ilerleme göstergesinin türünü ve durumunu ayarlar.

```cpp
void SetProgressBarState(TBPFLAG tbpFlags);
```

### <a name="parameters"></a>Parametreler

*tbpBayraklar*<br/>
İlerleme düğmesinin geçerli durumunu denetleyen bayraklar. Tüm devletler birbirini dışladığı için aşağıdaki bayraklardan yalnızca birini belirtin: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.

### <a name="remarks"></a>Açıklamalar

## <a name="cframewndsettaskbaroverlayicon"></a><a name="settaskbaroverlayicon"></a>CFrameWnd::SetTaskbarOverlayIcon

Fazla Yüklendi. Uygulama durumunu belirtmek veya kullanıcıyı bilgilendirmek için görev çubuğuna bir bindirme uygular.

```
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,
    LPCTSTR lpcszDescr);

BOOL SetTaskbarOverlayIcon(
    HICON hIcon,
    LPCTSTR lpcszDescr);
```

### <a name="parameters"></a>Parametreler

*nIDKaynak*<br/>
Bindirme olarak kullanılacak bir simgenin Kaynak Kimliğini belirtir. Ayrıntılar için *hIcon* açıklamasına bakın.

*lpcszDescr*<br/>
Erişilebilirlik amacıyla bindirme tarafından iletilen bilgilerin alt metin sürümünü sağlayan bir dize işaretçisi.

*Hıcon*<br/>
Bindirme olarak kullanılacak bir simgenin tutamacı. Bu küçük bir simge olmalı, inç başına 96 nokta (dpi) 16x16 piksel ölçme. Görev çubuğu düğmesine zaten bir bindirme simgesi uygulanmışsa, varolan bindirme değiştirilir. Bu değer NULL olabilir. NULL değerinin nasıl işleneceğiniz, görev çubuğu düğmesinin tek bir pencereyi mi yoksa bir pencere grubunu mu temsil etmediğine bağlıdır. Artık ihtiyaç duyulmadığında *hIcon'u* serbest hale getirmek arama uygulamasının sorumluluğundadır.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; İşletim sistemi sürümü Windows 7'den küçükse veya simgeyi ayarlayarak bir hata oluşuyorsa FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cframewndsettitle"></a><a name="settitle"></a>CFrameWnd::SetTitle

Pencere nesnesinin başlığını ayarlar.

```cpp
void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Parametreler

*lpszTitle*<br/>
Pencere nesnesinin başlığını içeren bir karakter dizesine işaretçi.

## <a name="cframewndshowcontrolbar"></a><a name="showcontrolbar"></a>CFrameWnd::ShowControlBar

Denetim çubuğunu göstermek veya gizlemek için bu üye işlevini arayın.

```cpp
void ShowControlBar(
    CControlBar* pBar,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
Gösterilecek veya gizlenmek üzere denetim çubuğuna işaretçi.

*bGöster*<br/>
TRUE ise, denetim çubuğunun gösterilen olduğunu belirtir. FALSE ise, denetim çubuğunun gizleneceğini belirtir.

*bGecikme*<br/>
TRUE ise, denetim çubuğunu göstermeyi geciktirin. FALSE ise, denetim çubuğunu hemen gösterin.

## <a name="cframewndshowownedwindows"></a><a name="showownedwindows"></a>CFrameWnd::ShowOwnedWindows

Nesnenin `CFrameWnd` torunları olan tüm pencereleri göstermek için bu üye işlevi arayın.

```cpp
void ShowOwnedWindows(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bGöster*<br/>
Sahip olunan pencerelerin gösterileceğini veya gizleneceğini belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd Sınıfı](../../mfc/reference/cmdiframewnd-class.md)<br/>
[CMDIChildWnd Sınıfı](../../mfc/reference/cmdichildwnd-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CRuntimeClass Yapısı](../../mfc/reference/cruntimeclass-structure.md)
