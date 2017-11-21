---
title: "CFrameWnd sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6d5766a883c8bec143a7a635a657ba2545d1d612
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cframewnd-class"></a>CFrameWnd sınıfı
Çakışan Windows tek belge arabirimi (SDI) veya pencere yönetmek için üyeleri birlikte açılır çerçeve penceresi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFrameWnd : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFrameWnd::CFrameWnd](#cframewnd)|Oluşturan bir `CFrameWnd` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFrameWnd::ActivateFrame](#activateframe)|Çerçeve kullanıcıya görünür ve kullanılabilir hale getirir.|  
|[CFrameWnd::BeginModalState](#beginmodalstate)|Çerçeve penceresi için kalıcı ayarlar.|  
|[CFrameWnd::Create](#create)|Oluşturma ve ilişkili Windows çerçeve penceresi başlatma için çağrı `CFrameWnd` nesnesi.|  
|[CFrameWnd::CreateView](#createview)|Bir görünüm türetilmedi bir çerçevesinde oluşturur `CView`.|  
|[CFrameWnd::DockControlBar](#dockcontrolbar)|Denetim çubuğu docks.|  
|[CFrameWnd::EnableDocking](#enabledocking)|Yerleşik bir denetim çubuğu sağlar.|  
|[CFrameWnd::EndModalState](#endmodalstate)|Çerçeve pencere kalıcı durumunu sonlandırır. Tüm devre dışı windows etkinleştirir `BeginModalState`.|  
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|Denetim çubuğu kayar.|  
|[CFrameWnd::GetActiveDocument](#getactivedocument)|Etkin döndürür **CDocument** nesnesi.|  
|[CFrameWnd::GetActiveFrame](#getactiveframe)|Etkin döndürür `CFrameWnd` nesnesi.|  
|[CFrameWnd::GetActiveView](#getactiveview)|Etkin döndürür `CView` nesnesi.|  
|[CFrameWnd::GetControlBar](#getcontrolbar)|Denetim çubuğu alır.|  
|[CFrameWnd::GetDockState](#getdockstate)|Bir çerçeve penceresinde dock durumunu alır.|  
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|Geçerli MFC uygulaması menüde görünen durumunu alır.|  
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|Geçerli MFC uygulaması menüde varsayılan davranışını gizli veya görünür olup olmadığını gösterir.|  
|[CFrameWnd::GetMessageBar](#getmessagebar)|Çerçeve penceresi ait çubuğu durum için bir işaretçi döndürür.|  
|[CFrameWnd::GetMessageString](#getmessagestring)|Bir komut kimliğini karşılık gelen iletiyi alır|  
|[CFrameWnd::GetTitle](#gettitle)|İlgili denetim çubuğu başlığını alır.|  
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|Neden `OnInitialUpdate` çağrılacak çerçeve penceresindeki tüm görünümler ait üye işlevi.|  
|[CFrameWnd::InModalState](#inmodalstate)|Çerçeve penceresi kalıcı bir durumda olup olmadığını belirten bir değer döndürür.|  
|[CFrameWnd::IsTracking](#istracking)|Bölümlendirici çubuğu şu anda taşınıyor varsa belirler.|  
|[CFrameWnd::LoadAccelTable](#loadacceltable)|Hızlandırıcı tablosunu yüklemek için çağırın.|  
|[CFrameWnd::LoadBarState](#loadbarstate)|Denetim çubuğu ayarları geri yüklemek için çağırın.|  
|[CFrameWnd::LoadFrame](#loadframe)|Çerçeve penceresi kaynak bilgileri dinamik olarak oluşturmak için çağırın.|  
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|Çerçeve penceresi kenarlık alanı görüşür.|  
|[CFrameWnd::OnBarCheck](#onbarcheck)|Bir eylem belirtilen denetim çubuğunda gerçekleştirildiğinde çağrılır.|  
|[CFrameWnd::OnContextHelp](#oncontexthelp)|SHIFT + F1 Yardımı yerinde öğeleri için işler.|  
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|Uygulamanın ana çerçeve penceresi içine ve dışına Baskı Önizleme modunu ayarlar.|  
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|İlişkili menüyü güncelleştirildiğinde çerçevesi tarafından çağrılır.|  
|[CFrameWnd::RecalcLayout](#recalclayout)|Denetim çubukları yeniden konumlandırır `CFrameWnd` nesnesi.|  
|[CFrameWnd::SaveBarState](#savebarstate)|Denetim çubuğu ayarları kaydetmek için çağırın.|  
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|Belirtilen görünüm zengin önizlemesi için etkin görünüm olarak belirler.|  
|[CFrameWnd::SetActiveView](#setactiveview)|Etkin ayarlar `CView` nesnesi.|  
|[CFrameWnd::SetDockState](#setdockstate)|Ana pencerede çerçeve pencere sabitlemek için çağırın.|  
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|Gizli veya görüntülenen geçerli MFC uygulamasında menüsünün ekran durumunu ayarlar.|  
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|Gizli veya görünür olacak şekilde geçerli MFC uygulamasında menüsünün varsayılan davranışını ayarlar.|  
|[CFrameWnd::SetMessageText](#setmessagetext)|Standart durum çubuğu metni ayarlar.|  
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|Windows 7 ilerleme çubuğu çubuğunda görüntülenen geçerli konumunu ayarlar.|  
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|Windows 7 ilerleme çubuğu çubuğunda görüntülenen aralığını ayarlar.|  
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|Görev çubuğunda görüntülenen İlerleme göstergesi durumunu ve türünü ayarlar.|  
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|Fazla Yüklendi. Uygulama durumu veya kullanıcıya bir bildirim belirtmek üzere bir görev çubuğu düğmesi bir katmana uygulanır.|  
|[CFrameWnd::SetTitle](#settitle)|Başlık ilgili denetim çubuğunun ayarlar.|  
|[CFrameWnd::ShowControlBar](#showcontrolbar)|Denetim çubuğu göstermek için çağırın.|  
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|Alt öğeleri olan tüm windows gösterir `CFrameWnd` nesnesi.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFrameWnd::OnCreateClient](#oncreateclient)|Bir istemci pencere çerçevesi için oluşturur.|  
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|Geçerli MFC uygulaması menüde gizli önce çağrılır.|  
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|Geçerli MFC uygulaması menüde görüntülenmeden önce çağrılır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|Denetimleri otomatik etkinleştirin ve işlevselliği için menü öğelerini devre dışı bırakın.|  
|[CFrameWnd::rectDefault](#rectdefault)|Bu statik geçirmek `CRect` oluştururken, bir parametre olarak bir `CFrameWnd` pencerenin başlangıç boyutunu ve konumunu seçmek izin vermek için nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulamanız için yararlı çerçeve penceresi oluşturmak için öğesinden bir sınıf türetin `CFrameWnd`. Üye değişkenleri, uygulamaya özgü verileri depolamak için türetilmiş bir sınıf ekleyin. Uygulama ileti işleyicisi üye işlevleri ve bir ileti iletileri penceresine yönlendirilirsiniz olduğunda ne olacağını belirlemek için türetilen sınıfta eşleyin.  
  
 Çerçeve penceresi oluşturmak için üç yolu vardır:  
  
-   Doğrudan kullanarak oluşturmak [oluşturma](#create).  
  
-   Doğrudan kullanarak oluşturmak [LoadFrame](#loadframe).  
  
-   Dolaylı bir belge şablonu kullanarak oluşturun.  
  
 Ya da çağırmadan önce **oluşturma** veya `LoadFrame`, C++ kullanarak yığın çerçeve penceresi nesnesinde oluşturmalıdır **yeni** işleci. Çağırmadan önce **oluşturma**, ayrıca, bir pencere sınıfı ile kaydedebilirsiniz [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) çerçeve simgesini ve sınıf stilleri ayarlamak için genel işlevi.  
  
 Kullanım **oluşturma** çerçeve oluşturma parametreleri olarak hemen bağımsız değişkenleri geçirmek için üye işlevi.  
  
 `LoadFrame`daha az sayıda bağımsız değişken gerektirir **oluşturma**ve bunun yerine varsayılan değerlerine çoğunu çerçeve resim yazısı simgesi, Hızlandırıcı tablosu ve menü çeşitli kaynaklardan alır. Tarafından erişilebilir olmasını `LoadFrame`, tüm bu kaynaklar aynı kaynak kimliği olmalıdır (örneğin, **IDR_MAINFRAME**).  
  
 Zaman bir `CFrameWnd` nesnesini içeren görünümleri ve belgeleri, çerçevesiyle yerine doğrudan Programcı tarafından dolaylı olarak oluşturma. `CDocTemplate` Çerçeve oluşturulmasını, içeren görünümler oluşturma ve uygun belge görünümlerine bağlantı nesnesi düzenler. Parametreleri `CDocTemplate` Oluşturucusu belirtin `CRuntimeClass` üç sınıflarını söz konusu (belge, çerçeve ve Görünüm). A `CRuntimeClass` nesnesi çerçevesi tarafından dinamik olarak (örneğin, dosya yeni veya birden çok belge arabirimi (MDI) penceresi yeni komutunu kullanarak) kullanıcı tarafından belirtilen zaman yeni çerçeve oluşturmak için kullanılır.  
  
 Çerçeve pencere sınıfı türetilmiş `CFrameWnd` ile bildirilmelidir `DECLARE_DYNCREATE` yukarıdaki için sırada `RUNTIME_CLASS` düzgün çalışması için bir mekanizma.  
  
 A `CFrameWnd` Windows için tipik bir uygulamada ana penceresinin aşağıdaki işlevleri gerçekleştirmek için varsayılan uygulamaları içerir:  
  
-   A `CFrameWnd` çerçeve penceresi Windows etkin pencereyi veya geçerli giriş odağını bağımsız şu anda etkin bir görünüm izler. Çerçeve etkinleştirildiğinde etkin görünüm çağırarak bildirilir `CView::OnActivateView`.  
  
-   Komut iletileri ve tarafından işlenen dahil olmak üzere, birçok ortak çerçeve bildirim iletilerini `OnSetFocus`, `OnHScroll`, ve `OnVScroll` işlevlerini `CWnd`, tarafından verilmiş bir `CFrameWnd` çerçeve penceresi şu anda etkin görüntülemek için.  
  
-   Şu anda etkin görünüm (veya şu anda etkin MDI alt çerçeve penceresi bir MDI çerçevesi söz konusu olduğunda) çerçeve penceresi resim yazısını belirleyebilirsiniz. Bu özellik kapatma tarafından devre dışı bırakılabilir **fws_addtotıtle** stili bit çerçeve penceresi.  
  
-   A `CFrameWnd` çerçeve penceresi denetim çubukları, görünümler ve çerçeve penceresinin istemci alanı içindeki diğer alt windows konumlandırma yönetir. Çerçeve penceresi de boşta kalma süresi araç ve diğer denetim çubuğu düğmelerini güncelleştirme yapar. A `CFrameWnd` çerçeve penceresi de varsayılan uygulamaları açma ve kapatma araç çubuğu ve durum çubuğu geçiş için komutların vardır.  
  
-   A `CFrameWnd` çerçeve penceresi ana menü çubuğu yönetir. Çerçeve penceresi açılır menü görüntülendiğinde kullanan **UPDATE_COMMAND_UI** hangi menü öğeleri etkin, devre dışı kullanıma veya belirlemek için bir mekanizma. Kullanıcı menü öğesi seçtiğinde, çerçeve penceresi durum çubuğunda komut ileti dizesi ile güncelleştirir.  
  
-   A `CFrameWnd` çerçeve penceresi otomatik olarak klavye Hızlandırıcıları çeviren bir isteğe bağlı Hızlandırıcı tablosu vardır.  
  
-   A `CFrameWnd` çerçeve penceresi kümesiyle bir isteğe bağlı Yardım Kimliğe sahip `LoadFrame` bağlama duyarlı Yardım için kullanılır. Bağlama duyarlı Yardım (SHIFT + F1) ve Baskı Önizleme modlarında gibi yarı kalıcı durumlar ana orchestrator bir çerçeve penceredir.  
  
-   A `CFrameWnd` çerçeve penceresi Dosya Yöneticisi'nden sürüklenen ve çerçeve penceresi bırakılan bir dosya açın. Bir dosya uzantısı kayıtlı ve uygulama ile ilişkilendirilmiş, çerçeve penceresi veya kullanıcı bir veri dosyası Dosya Yöneticisi'nde açar zaman ortaya çıkan dinamik veri değişimi (DDE) açık isteğe yanıt **ShellExecute** Windows işlev çağrılır.  
  
-   Çerçeve penceresi ana uygulama penceresi ise (diğer bir deyişle, `CWinThread::m_pMainWnd`), kullanıcı uygulama kapandığında çerçeve penceresi değiştirilmiş belgeleri kaydetmek için kullanıcıdan (için `OnClose` ve `OnQueryEndSession`).  
  
-   Çerçeve penceresi ana uygulama penceresi, çerçeve penceresi WinHelp çalıştırmak için içerik ise. WINHELP çerçeve pencereyi kapat. EXE bu uygulama için Yardımı için başlatıldı.  
  
 C++ kullanmayın **silmek** işleci bir çerçeve penceresi yok. Bunun yerine `CWnd::DestroyWindow` kullanın. `CFrameWnd` Uyarlamasını `PostNcDestroy` pencere bozulduğunda C++ nesneyi siler. Kullanıcının varsayılan çerçeve penceresi kapattığı zaman `OnClose` işleyici çağıracaktır `DestroyWindow`.  
  
 Daha fazla bilgi için `CFrameWnd`, bkz: [çerçeve pencereleri](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="activateframe"></a>CFrameWnd::ActivateFrame  
 Etkinleştirme ve böylece kullanıcıya görünür ve kullanılabilir durumda çerçeve penceresi geri yüklemek için bu üye işlevini çağırın.  
  
```  
virtual void ActivateFrame(int nCmdShow = -1);
```  
  
### <a name="parameters"></a>Parametreler  
 `nCmdShow`  
 Geçirilecek parametresi belirtir [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow). Varsayılan olarak, çerçeve gösterilen ve doğru şekilde geri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu genellikle bir DDE, OLE veya çerçeve penceresi ya da içeriğini kullanıcıya gösterebilir başka bir olay gibi bir kullanıcı olmayan arabirimi olayından sonra çağrılır.  
  
 Varsayılan Uygulama Çerçevesi etkinleştirir ve Z düzenini üst kısmına beraberinde getirir ve gerekirse, uygulamanın ana çerçeve penceresi için aynı adımları yapar.  
  
 Bu üye işlevi bir çerçeve nasıl etkinleştirileceğini değiştirmek için geçersiz kılar. Örneğin, tam ekran için MDI alt pencereleri zorlayabilirsiniz. Uygun işlevselliği ekleyin, sonra açık bir temel sınıf sürümüyle çağrı `nCmdShow`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]  
  
##  <a name="beginmodalstate"></a>CFrameWnd::BeginModalState  
 Çerçeve penceresi kalıcı yapmak için bu üye işlevini çağırın.  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="cframewnd"></a>CFrameWnd::CFrameWnd  
 Oluşturan bir `CFrameWnd` nesnesi, ancak görünür çerçeve penceresi oluşturmaz.  
  
```  
CFrameWnd();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı **oluşturma** görünür penceresi oluşturulamadı.  
  
##  <a name="create"></a>CFrameWnd::Create  
 Oluşturma ve ilişkili Windows çerçeve penceresi başlatma için çağrı `CFrameWnd` nesnesi.  
  
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
 `lpszClassName`  
 Windows sınıfı adları null olarak sonlandırılan bir karakter dizesine noktaları. Sınıf adı kayıtlı herhangi bir ad olabilir `AfxRegisterWndClass` genel işlevi veya **RegisterClass** Windows işlevi. Varsa **NULL**, önceden tanımlanmış varsayılan kullanır `CFrameWnd` öznitelikleri.  
  
 `lpszWindowName`  
 Pencere adı temsil eden bir null olarak sonlandırılan bir karakter dizesi noktalarına. Başlık çubuğunu metin olarak kullanılır.  
  
 `dwStyle`  
 Pencerenin belirtir [stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) öznitelikleri. Dahil **fws_addtotıtle** penceresinde gösterilen belgenin adını otomatik olarak görüntülenecek başlık çubuğu istiyorsanız stili.  
  
 `rect`  
 Pencere konumunu ve boyutunu belirtir. `rectDefault` Değeri boyutunu ve yeni pencere konumunu belirtmek Windows sağlar.  
  
 `pParentWnd`  
 Bu çerçeve penceresinin üst pencere belirtir. Bu parametre olmalıdır **NULL** en üst düzey çerçeve pencereleri için.  
  
 *lpszMenuName*  
 Pencerenin ile kullanılmak üzere menü kaynağın adını tanımlar. Kullanım **MAKEINTRESOURCE** menü bir dize yerine bir tamsayı kimliği varsa. Bu parametre olabilir **NULL**.  
  
 `dwExStyle`  
 Genişletilmiş pencere belirtir [stili](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) öznitelikleri.  
  
 `pContext`  
 Bir işaretçi belirten bir [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısı. Bu parametre olabilir **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlatma başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CFrameWnd` iki adımda nesne. İlk olarak, yapıları Oluşturucusu çağırma `CFrameWnd` nesnesini genişletin ve ardından arama **oluşturma**, hangi Windows çerçeve penceresi oluşturur ve ona ekler `CFrameWnd` nesnesi. **Oluşturma** pencere sınıfı adı ve pencere adı başlatır ve stil, üst ve ilişkili menü varsayılan değerleri kaydeder.  
  
 Kullanım `LoadFrame` yerine **oluşturma** bağımsız değişkenlerini belirtme yerine bir kaynaktan çerçeve penceresi yüklenemiyor.  
  
##  <a name="createview"></a>CFrameWnd::CreateView  
 Çağrı `CreateView` bir çerçevesinde bir görünüm oluşturmak için.  
  
```  
CWnd* CreateView(
    CCreateContext* pContext,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>Parametreler  
 `pContext`  
 Görünüm ve belge türünü belirtir.  
  
 `nID`  
 Bir görünüm kimliği sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir `CWnd` nesne başarılı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Olmayan "Görünüm" oluşturmak için bu üye fonksiyonu kullanın `CView`-bir çerçevesinde türetilmiş. Çağırdıktan sonra `CreateView`, el ile görünümü etkin olarak ayarlanmış ve görünür olması için ayarlamanız gerekir; bu görevler tarafından otomatik olarak gerçekleştirilmez `CreateView`.  
  
##  <a name="dockcontrolbar"></a>CFrameWnd::DockControlBar  
 Çerçeve penceresi yerleşik bir denetim çubuğu neden olur.  
  
```  
void DockControlBar(
    CControlBar* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBar`  
 Yerleşik için denetim çubuğu noktalarına.  
  
 `nDockBarID`  
 Yerleştirme için dikkate alınması gereken çerçeve penceresi hangi kenarlarına belirler. 0, veya bir veya daha fazla aşağıdakiler olabilir:  
  
- `AFX_IDW_DOCKBAR_TOP`Çerçeve penceresi üst kenarına sabitleyin.  
  
- **AFX_IDW_DOCKBAR_BOTTOM** çerçeve penceresi alt tarafına yerleştir.  
  
- `AFX_IDW_DOCKBAR_LEFT`Çerçeve penceresi sol tarafına sabitleyin.  
  
- `AFX_IDW_DOCKBAR_RIGHT`Çerçeve penceresi sağ tarafındaki sabitleyin.  
  
 0 ise, hedef çerçeve penceresinde yerleştirme için etkin yan denetim çubuğu ına.  
  
 `lpRect`  
 Denetim çubuğu hedef çerçeve penceresi nonclient alanında nereye yerleştirilir ekran koordinatları belirler.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubuğu her ikisi de çağrıları belirtilen çerçeve penceresi yanlarından birine yerleşik [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) ve [CFrameWnd::EnableDocking](#enabledocking). Seçilen yan tarafından belirlenen `nDockBarID`.  
  
##  <a name="enabledocking"></a>CFrameWnd::EnableDocking  
 Bir çerçeve penceresinde Dockable denetim çubukları etkinleştirmek için bu işlevini çağırın.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDockStyle`  
 Çerçeve penceresi hangi kenarlarına siteler için Denetim çubukları yerleştirme olarak hizmet verebilir belirtir. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `CBRS_ALIGN_TOP`İstemci alanının üstünde yerleştirme sağlar.  
  
- `CBRS_ALIGN_BOTTOM`İstemci alanı altındaki yerleştirme sağlar.  
  
- `CBRS_ALIGN_LEFT`İstemci alanını sol tarafta yerleştirme sağlar.  
  
- `CBRS_ALIGN_RIGHT`İstemci alanını sağ tarafta yerleştirme sağlar.  
  
- `CBRS_ALIGN_ANY`Tüm istemci alanını tarafında yerleştirme sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, aşağıdaki sırayla çerçeve penceresi tarafına denetim çubukları yerleştirilir: üst, alt, sol, sağ.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CToolBar::Create](../../mfc/reference/ctoolbar-class.md#create).  
  
##  <a name="endmodalstate"></a>CFrameWnd::EndModalState  
 Çerçeve penceresi kalıcı için kalıcı olmayan değiştirmek için bu üye işlevini çağırın.  
  
```  
virtual void EndModalState();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `EndModalState`tüm devre dışı windows etkinleştirir [BeginModalState](#beginmodalstate).  
  
##  <a name="floatcontrolbar"></a>CFrameWnd::FloatControlBar  
 Çerçeve penceresi yerleştirilmemişse denetim çubuğu neden bu işlevini çağırın.  
  
```  
void FloatControlBar(
    CControlBar* pBar,  
    CPoint point,  
    DWORD dwStyle = CBRS_ALIGN_TOP);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBar`  
 Kaydırılmış için denetim çubuğu noktalarına.  
  
 `point`  
 Denetim çubuğu sol üst köşesine yerleştirileceği konum, ekran koordinatları.  
  
 `dwStyle`  
 Denetim çubuğu kendi yeni çerçeve penceresi içinde yatay veya dikey olarak Hizala belirtir. Aşağıdakilerden herhangi biri olabilir:  
  
- `CBRS_ALIGN_TOP`Denetim çubuğu dikey olarak yönlendirir.  
  
- `CBRS_ALIGN_BOTTOM`Denetim çubuğu dikey olarak yönlendirir.  
  
- `CBRS_ALIGN_LEFT`Denetim çubuğu yatay olarak yönlendirir.  
  
- `CBRS_ALIGN_RIGHT`Denetim çubuğu yatay olarak yönlendirir.  
  
 Stilleri yatay ve dikey yönlendirme belirtme aktarılırsa, araç yatay yönelimli olacaktır.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, bu programın önceki yürütülmesinden ayarlarını geri yüklerken uygulama başlangıcında gerçekleştirilir.  
  
 Denetim çubuğu yerleştirme için kullanılabilir olmayan bir konum üzerinden sürükleme sırasında sol fare düğmesini serbest bırakma bırakma işlemi kullanıcı neden olduğunda bu işlev çerçevesi tarafından çağrılır.  
  
##  <a name="getactivedocument"></a>CFrameWnd::GetActiveDocument  
 Geçerli bir işaretçi elde etmek için bu üye işlevini çağırın **CDocument** geçerli etkin görünüme bağlı.  
  
```  
virtual CDocument* GetActiveDocument();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi [CDocument](../../mfc/reference/cdocument-class.md). Geçerli bir belge ise döndürür **NULL**.  
  
##  <a name="getactiveframe"></a>CFrameWnd::GetActiveFrame  
 Etkin bir işaretçi bir MDI çerçeve penceresi birden çok belge arabirimi (MDI) alt pencere elde etmek için bu üye işlevini çağırın.  
  
```  
virtual CFrameWnd* GetActiveFrame();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etkin MDI alt pencere için bir işaretçi. SDI uygulamasıdır veya etkin belge yok, örtük MDI çerçeve penceresi sahip **bu** işaretçi döndürülecek.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir etkin MDI alt yok veya bir tek belge arabirimi (SDI) örtük uygulamasıdır **bu** işaretçi döndürülür.  
  
##  <a name="getactiveview"></a>CFrameWnd::GetActiveView  
 Bir çerçeve penceresinde bağlı etkin görünüm (varsa) için bir işaretçi elde etmek için bu üye işlevini çağırın ( `CFrameWnd`).  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi [CView](../../mfc/reference/cview-class.md). Geçerli Görünüm ise döndürür **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, döndürür **NULL** bir MDI ana çerçeve penceresi çağrıldığında ( `CMDIFrameWnd`). MDI uygulamada MDI ana çerçeve penceresi kendisiyle ilişkili bir görünüm yok. Bunun yerine, her tek tek alt pencere ( `CMDIChildWnd`) bir veya daha fazla ilişkili görünüme sahiptir. MDI uygulamanın etkin görünümde etkin MDI alt pencere ilk bulma ve ardından o alt pencere için etkin görünüm bulma tarafından alınabilir. Etkin MDI alt pencere işlevini çağırarak bulunabilir `MDIGetActive` veya **GetActiveFrame** aşağıda gösterildiği gibi:  
  
 [!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]  
  
##  <a name="getcontrolbar"></a>CFrameWnd::GetControlBar  
 Çağrı `GetControlBar` kimliğiyle ilişkili denetim çubuğu erişmek için  
  
```  
CControlBar* GetControlBar(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Denetim çubuğu kimliği sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi kimliğiyle ilişkili denetim çubuğu  
  
### <a name="remarks"></a>Açıklamalar  
 `nID` Parametresi başvuruyor geçirilen benzersiz tanımlayıcıya **oluşturma** denetim çubuğu yöntemi. Denetim çubukları hakkında daha fazla bilgi için başlıklı konuya bakın [denetim çubukları](../../mfc/control-bars.md).  
  
 `GetControlBar`denetim çubuğu kayan olduğu ve bu nedenle şu anda bir alt pencere çerçevesinin değil olsa bile döndürür.  
  
##  <a name="getdockstate"></a>CFrameWnd::GetDockState  
 Çerçeve pencere denetim çubukları hakkında durum bilgilerini depolamak için bu üye işlevini çağırın bir `CDockState` nesnesi.  
  
```  
void GetDockState(CDockState& state) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `state`  
 Çerçeve pencere denetim çubukları return üzerine geçerli durumunu içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Ardından içeriğini yazmak `CDockState` depolama kullanmanın `CDockState::SaveState` veya `Serialize`. Daha sonra Denetim çubukları önceki bir duruma geri yüklemek istiyorsanız, durumuyla yük `CDockState::LoadState` veya `Serialize`, ardından çağıran `SetDockState` çerçeve pencere denetim çubukları önceki bir duruma uygulamak için.  
  
##  <a name="getmenubarstate"></a>CFrameWnd::GetMenuBarState  
 Geçerli MFC uygulaması menüde görünen durumunu alır.  
  
```  
virtual DWORD GetMenuBarState();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri aşağıdaki değerlere sahip olabilir:  
  
-   AFX_MBS_VISIBLE (0x01) - menü görünür olur.  
  
-   AFX_MBS_HIDDEN (0x02) - menü gizlenir.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı hatası meydana gelirse, bu yöntem hata ayıklama modunda onaylar ve türetilmiş bir özel durum oluşturur [CException](../../mfc/reference/cexception-class.md) sınıfı.  
  
##  <a name="getmenubarvisibility"></a>CFrameWnd::GetMenuBarVisibility  
 Geçerli MFC uygulaması menüde varsayılan durumu gizli veya görünür olup olmadığını gösterir.  
  
```  
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem aşağıdaki değerlerden birini döndürür:  
  
-   AFX_MBV_KEEPVISIBLE (0x01) - menüsü görüntülenir hiç zamanları ve tarafından varsayılan odağa sahip değil.  
  
-   AFX_MBV_DISPLAYONFOCUS (0x02) - menüsü varsayılan olarak gizlidir. Menü gizli ise, menüsünü görüntüleme ve odağı vermek için ALT tuşuna basın. Menü görüntüleniyorsa, gizlemek için ALT ya da ESC tuşuna basın.  
  
-   AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04) (Bitsel bir birleşimi (veya)) - menüsü varsayılan olarak gizlidir. Menü gizli ise, menüsünü görüntüleyin ve odaklanmak için F10 tuşuna basın. Menü görüntüleniyorsa, açın veya menü odak geçiş yapmak için F10 tuşuna basın. Gizlemek için ALT ya da ESC tuşuna basın kadar menüsü görüntülenir.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı hatası meydana gelirse, bu yöntem hata ayıklama modunda onaylar ve türetilmiş bir özel durum oluşturur [CException](../../mfc/reference/cexception-class.md) sınıfı.  
  
##  <a name="getmessagebar"></a>CFrameWnd::GetMessageBar  
 Durum çubuğu bir işaretçi almak için bu üye işlevini çağırın.  
  
```  
virtual CWnd* GetMessageBar();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durum çubuğu penceresi işaretçi.  
  
##  <a name="getmessagestring"></a>CFrameWnd::GetMessageString  
 Komut kimlikleri için özel dizeleri sağlamak için bu işlevi geçersiz kılar.  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 İstenen iletinin kaynak kimliği.  
  
 `rMessage`  
 `CString`ileti yerleştirmek için nesnesine.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama tarafından belirtilen dize yalnızca yükler `nID` kaynak dosyadan. Güncelleştirme durum çubuğunda ileti dizesi ihtiyacı olduğunda bu işlev çerçevesi tarafından çağrılır.  
  
##  <a name="gettitle"></a>CFrameWnd::GetTitle  
 Pencere nesnesi başlığını alır.  
  
```  
CString GetTitle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) pencere nesnesi geçerli başlığı içeren nesne.  
  
##  <a name="initialupdateframe"></a>CFrameWnd::InitialUpdateFrame  
 Çağrı **IntitialUpdateFrame** ile yeni bir çerçeve oluşturduktan sonra **oluşturma**.  
  
```  
void InitialUpdateFrame(
    CDocument* pDoc,  
    BOOL bMakeVisible);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDoc`  
 Çerçeve penceresi ilişkilendirilen belge noktalarına. Olabilir **NULL**.  
  
 `bMakeVisible`  
 Varsa **doğru**, çerçeve görünür ve etkin olması gerektiğini gösterir. Varsa **yanlış**, hiçbir alt öğeleri görünür yapılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tüm görünümleri almak için bu çerçeve penceresinde neden olan kendi `OnInitialUpdate` çağrıları.  
  
 Ayrıca, yoksa daha önce etkin bir görünüm, çerçeve penceresi birincil görünümünü etkinleştirilir. Birincil görünüm alt kimliğine sahip bir görünümdür **AFX_IDW_PANE_FIRST**. Son olarak, çerçeve penceresi görünür hale gelir, `bMakeVisible` sıfır olmayan bir değer değil. Varsa `bMakeVisible` 0'dır, geçerli odak ve çerçeve penceresi görünür durumunu değişmeden kalır. Framework'ün uygulama ve dosya yeni dosya Aç kullanırken bu işlevi çağırmak gerekli değildir.  
  
##  <a name="inmodalstate"></a>CFrameWnd::InModalState  
 Çerçeve penceresi kalıcı veya geçici olup olmadığını denetlemek için bu üye işlevini çağırın.  
  
```  
BOOL InModalState() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yanıt Evet ise sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="istracking"></a>CFrameWnd::IsTracking  
 Ayırıcı çubuğu penceresinde şu anda taşınıyor varsa belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsTracking() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölme işlemi devam ediyor, sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="loadacceltable"></a>CFrameWnd::LoadAccelTable  
 Belirtilen Hızlandırıcı tablosunu yüklemek için çağırın.  
  
```  
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszResourceName`  
 Hızlandırıcı kaynağın adını tanımlar. Kullanım **MAKEINTRESOURCE** bir tamsayı kimliği ile kaynak tanımladıysanız  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hızlandırıcı tablosu başarıyla yüklendiyse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Aynı anda yalnızca bir tablo yüklenebilir.  
  
 Uygulama sonlandırıldığında kaynaklardan yüklenen Hızlandırıcı tabloları otomatik olarak kurtulurlar.  
  
 Çağırırsanız `LoadFrame` çerçeve penceresi oluşturmak için menü ve simge kaynakları birlikte Hızlandırıcı tablosunu framework yükler ve bir sonraki bu üye işlevi çağrısı sonra gerekli değildir.  
  
##  <a name="loadbarstate"></a>CFrameWnd::LoadBarState  
 Çerçeve penceresi tarafından sahip olunan her denetim çubuğu ayarlarını geri yüklemek için bu işlevini çağırın.  
  
```  
void LoadBarState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszProfileName`  
 Başlatma (INI) dosyası bir bölümünde veya durum bilgilerini depolandığı Windows kayıt defteri anahtarında adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Geri bilgi görünürlük, yatay/dikey hizalama, takma durumunu ve denetim çubuğu konumunu içerir.  
  
 Arama yapmadan önce geri yüklemek istediğiniz ayarları kayıt defterine yazılmalıdır `LoadBarState`. Çağırarak bilgilerini kayıt defterine yazma [CWinApp::SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey). Bilgi çağırarak INI dosyasına yazma [SaveBarState](#savebarstate).  
  
##  <a name="loadframe"></a>CFrameWnd::LoadFrame  
 Çerçeve penceresi kaynak bilgileri dinamik olarak oluşturmak için çağırın.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDResource`  
 Çerçeve penceresi ile ilişkilendirilmiş paylaşılan kaynakları kimliği.  
  
 *dwDefaultStyle*  
 Çerçeve [stili](../../mfc/reference/styles-used-by-mfc.md#window-styles). Dahil **fws_addtotıtle** penceresinde gösterilen belgenin adını otomatik olarak görüntülenecek başlık çubuğu istiyorsanız stili.  
  
 `pParentWnd`  
 Çerçeve üst için bir işaretçi.  
  
 `pContext`  
 Bir işaretçi bir [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısı. Bu parametre olabilir **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CFrameWnd` iki adımda nesne. İlk olarak, yapıları Oluşturucusu çağırma `CFrameWnd` nesnesini genişletin ve ardından arama `LoadFrame`, hangi Windows çerçeve penceresi ve ilişkili kaynakları yükler ve çerçeve penceresi ekler `CFrameWnd` nesnesi. `nIDResource` Parametresi, menü, Hızlandırıcı tablosu, simge ve çerçeve penceresi başlığını dize kaynağını belirtir.  
  
 Kullanım **oluşturma** üye işlevi yerine `LoadFrame` tüm çerçeve pencere oluşturma parametreleri belirtmek istediğinizde.  
  
 Framework çağrıları `LoadFrame` bir belge şablonu nesnesi kullanılarak bir çerçeve penceresinde oluşturduğunda.  
  
 Çerçeve kullanır `pContext` herhangi dahil olmak üzere çerçeve penceresine bağlı nesnelere belirtmek için bağımsız değişken bulunan nesneleri görüntüle. Ayarlayabileceğiniz `pContext` bağımsız değişkeni **NULL** çağırdığınızda `LoadFrame`.  
  
##  <a name="m_bautomenuenable"></a>CFrameWnd::m_bAutoMenuEnable  
 Bu veri üyesi (varsayılan değer olan) etkin olduğunda, menü öğelerini olmayan `ON_UPDATE_COMMAND_UI` veya `ON_COMMAND` işleyicileri otomatik olarak devre dışı bırakılacak kullanıcının bir menüyü çeker olduğunda.  
  
```  
BOOL m_bAutoMenuEnable;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sahip menü öğelerini bir `ON_COMMAND` işleyici ancak hiçbir `ON_UPDATE_COMMAND_UI` işleyici otomatik olarak etkinleştirilir.  
  
 Bu veri üyesi olarak ayarlandığında, menü öğeleri araç çubuğu düğmeleri etkinleştirildiğini aynı şekilde otomatik olarak etkinleştirilir.  
  
> [!NOTE]
> `m_bAutoMenuEnable`üst düzey menü öğeleri üzerinde hiçbir etkisi yoktur.  
  
 Bu veri üyesi geçerli seçime göre isteğe bağlı komutları uyarlamasını basitleştirir ve yazma ihtiyacını azaltır `ON_UPDATE_COMMAND_UI` etkinleştirmek ve menü öğelerini devre dışı bırakmak için işleyiciler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]  
  
##  <a name="negotiateborderspace"></a>CFrameWnd::NegotiateBorderSpace  
 OLE yerinde etkinleştirme sırasında bir çerçeve penceresinde kenarlık alanı anlaşmak üzere bu üye işlevini çağırın.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>Parametreler  
 *nBorderCmd*  
 Aşağıdaki değerlerden birini içeren **enum BorderCmd**:  
  
- **borderGet** = 1  
  
- **borderRequest** = 2  
  
- **borderSet** = 3  
  
 `lpRectBorder`  
 İşaretçi bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) kenarlık koordinatlarını belirtir nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlev **CFrameWnd** OLE kenarlık alanı anlaşma uygulamasıdır.  
  
##  <a name="onbarcheck"></a>CFrameWnd::OnBarCheck  
 Bir eylem belirtilen denetim çubuğunda gerçekleştirildiğinde çağrılır.  
  
```  
afx_msg BOOL OnBarCheck(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Gösterildikten çubuğu denetiminin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim çubuğu varsa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="oncontexthelp"></a>CFrameWnd::OnContextHelp  
 SHIFT + F1 Yardımı yerinde öğeleri için işler.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlama duyarlı Yardım etkinleştirmek için eklemelisiniz bir  
  
 [!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]  
  
 deyimi, `CFrameWnd` sınıfı ileti eşlemesi ve de genellikle SHIFT + bu üye işlevini etkinleştirmek için F1, bir Hızlandırıcı tablosu girişini ekleyin.  
  
 Uygulamanız bir OLE kapsayıcı ise `OnContextHelp` Yardım moduna çerçeve pencere nesnesi içinde bulunan tüm yerinde öğeleri koyar. İmleç değişiklikleri bir ok ve soru işareti ve kullanıcı fare işaretçisini ve iletişim kutusu, pencere, menü veya komut düğmesi seçmek için sol fare düğmesine basın. Bu üye işlevi Windows işlevini çağırır `WinHelp` imleç altındaki Nesne Yardım içeriğine sahip.  
  
##  <a name="oncreateclient"></a>CFrameWnd::OnCreateClient  
 Yürütülmesi sırasında çerçevesi tarafından çağrılır `OnCreate`.  
  
```  
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpcs`  
 Windows için bir işaretçi [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) yapısı.  
  
 `pContext`  
 Bir işaretçi bir [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir zaman bu işlevini çağırın.  
  
 Bu işlev varsayılan uygulamasını oluşturur bir `CView` sağlanan bilgileri nesnesinden `pContext`, mümkün olduğunda.  
  
 Geçirilen değerleri geçersiz kılmak için bu işlevi geçersiz `CCreateContext` nesne veya değiştirmek için çerçeve penceresi ana istemci alanını şekilde denetimlerinde oluşturulur. `CCreateContext` Kılabilirsiniz üyeleri açıklanmıştır [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) sınıfı.  
  
> [!NOTE]
>  Geçirilen değerleri değiştirmeyin `CREATESTRUCT` yapısı. Yalnızca bilgilendirme amaçlı oldukları. İlk pencere dikdörtgeni geçersiz kılmak istiyorsanız, örneğin, geçersiz kılma `CWnd` üye işlevi [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).  
  
##  <a name="onhidemenubar"></a>CFrameWnd::OnHideMenuBar  
 Sistem geçerli MFC uygulaması menü çubuğunda hakkında gizlemek için olduğunda bu işlev çağrılır.  
  
```  
virtual void OnHideMenuBar();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu olay işleyicisi sistem yaklaşık menüsünü gizlemek için olduğunda özel eylemleri gerçekleştirmek uygulamanızı sağlar. Gizli gelen menü önleyemez, ancak, örneğin, menü stili veya durumunu almak için diğer yöntemleri çağırabilirsiniz.  
  
##  <a name="onsetpreviewmode"></a>CFrameWnd::OnSetPreviewMode  
 Uygulamanın ana çerçeve penceresi içine ve dışına Baskı Önizleme modunu ayarlamak için bu üye işlevini çağırın.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parametreler  
 *bPreview*  
 Baskı Önizleme moduna uygulama gerekip gerekmediğini belirtir. Kümesine **TRUE** baskı önizlemede yerleştirmek için **FALSE** Önizlemeyi iptal etmek için.  
  
 `pState`  
 Bir işaretçi bir **CPrintPreviewState** yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama, tüm standart araç çubuklarını devre dışı bırakır ve ana menü ve ana istemci penceresini gizler. Bu, geçici SDI çerçeve pencereleri halinde MDI çerçeve pencereleri kapatır.  
  
 Baskı Önizleme sırasında denetim çubukları ve diğer çerçeve penceresi parçalarının gösterme ve gizleme özelleştirmek için bu üye işlevi geçersiz kılar. Geçersiz kılınan sürüm içinde temel sınıf uygulamasından çağırın.  
  
##  <a name="onshowmenubar"></a>CFrameWnd::OnShowMenuBar  
 Sistem geçerli MFC uygulamasında menü çubuğu hakkında görüntülenecek olduğunda bu işlev çağrılır.  
  
```  
virtual void OnShowMenuBar();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu olay işleyicisi menü görüntülenmek üzere olduğunda özel eylemleri gerçekleştirmek uygulamanızı sağlar. Menü görüntülenmesini önlemek olamaz, ancak, örneğin, menü stili veya durumunu almak için diğer yöntemleri çağırabilirsiniz.  
  
##  <a name="onupdatecontrolbarmenu"></a>CFrameWnd::OnUpdateControlBarMenu  
 İlişkili menüyü güncelleştirildiğinde çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCmdUI`  
 Bir işaretçi bir [Ccmduı](../../mfc/reference/ccmdui-class.md) güncelleştirme komutu oluşturulan menü temsil eden nesne. Güncelleştirme işleyicisi çağrılarını [etkinleştirmek](../../mfc/reference/ccmdui-class.md#enable) üye işlevini `CCmdUI` nesnesi aracılığıyla `pCmdUI` kullanıcı arabirimini güncelleştirmek için.  
  
##  <a name="recalclayout"></a>CFrameWnd::RecalcLayout  
 Standart denetim çubukları açmak veya kapatmak kapatıldığında veya çerçeve penceresi yeniden boyutlandırıldığında çerçevesi tarafından çağrılır.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bNotify`  
 Çerçeve penceresi için etkin yerinde öğesi düzeni değişiklik bildirimi alıp almayacağını belirler. Varsa **TRUE**, öğe, uyarılan aksi **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi varsayılan uygulamasını çağıran `CWnd` üye işlevi `RepositionBars` çerçevesinde de ana istemci penceresi olduğu gibi tüm denetim çubukları yeniden konumlandırmak için (genellikle bir `CView` veya **MDICLIENT**) .  
  
 Çerçeve penceresi düzenini değiştikten sonra görünümünü ve davranışını denetim çubukları denetlemek için bu üye işlevi geçersiz kılar. Örneğin, Denetim çubuklarını aç veya kapat veya başka bir denetim çubuğu eklediğinizde, çağırın.  
  
##  <a name="rectdefault"></a>CFrameWnd::rectDefault  
 Bu statik geçirmek `CRect` pencerenin başlangıç boyutunu ve konumunu seçin izin vermek için bir pencere oluşturma sırasında bir parametre olarak.  
  
```  
static AFX_DATA const CRect rectDefault;  
```  
  
##  <a name="savebarstate"></a>CFrameWnd::SaveBarState  
 Çerçeve penceresi tarafından sahip olunan her denetim çubuğu hakkında bilgi depolamak için bu işlevini çağırın.  
  
```  
void SaveBarState(LPCTSTR lpszProfileName) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszProfileName`  
 Başlatma dosyası bölümünde veya durum bilgilerini depolandığı Windows kayıt defteri anahtarında adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bilgileri kullanarak başlatma dosyayı okuyabilir [LoadBarState](#loadbarstate). Depolanan bilgileri görünürlük, durumu ve denetim çubuğu konumu yerleştirme yatay/dikey yönlendirmesini içerir.  
  
##  <a name="setactivepreviewview"></a>CFrameWnd::SetActivePreviewView  
 Belirtilen görünüm zengin önizlemesi için etkin görünüm olarak belirler.  
  
```  
void SetActivePreviewView(CView* pViewNew);
```  
  
### <a name="parameters"></a>Parametreler  
 `pViewNew`  
 Etkinleştirilecek bir görünüm için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setactiveview"></a>CFrameWnd::SetActiveView  
 Etkin görünüm ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetActiveView(
    CView* pViewNew,  
    BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *pViewNew*  
 Bir işaretçi belirtir bir [CView](../../mfc/reference/cview-class.md) nesnesi veya **NULL** etkin görünüm için.  
  
 `bNotify`  
 Görünüm etkinleştirmesi bildirilmesini olup olmadığını belirtir. Varsa **TRUE**, `OnActivateView` için yeni bir görünümü; denir **yanlış**, bu değildir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir görünüme çerçeve penceresi içinde odak değiştikçe framework bu işlev otomatik olarak çağırır. Açıkça çağırabilir `SetActiveView` odağı belirtilen görünümü değiştirmek için.  
  
##  <a name="setdockstate"></a>CFrameWnd::SetDockState  
 Durum bilgilerini depolanan uygulamak için bu üye işlevini çağırın bir `CDockState` çerçeve pencere denetim çubukları nesnesine.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Parametreler  
 `state`  
 Çerçeve pencere denetim çubukları depolanmış durumu geçerli.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubukları önceki durumunu geri yüklemek için depolanmış durumuyla yükleyebilir `CDockState::LoadState` veya `Serialize`, ardından `SetDockState` çerçeve pencere denetim çubukları uygulamak için. Önceki bir duruma depolanan `CDockState` nesnesi ile`GetDockState`  
  
##  <a name="setmenubarstate"></a>CFrameWnd::SetMenuBarState  
 Gizli veya görüntülenen geçerli MFC uygulamasında menüsünün ekran durumunu ayarlar.  
  
```  
virtual BOOL SetMenuBarState(DWORD nState);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`nState`|Menü gizleyin veya gösterin belirtir. `nState` Parametresi, aşağıdaki değerleri sahip olabilir:<br /><br /> -AFX_MBS_VISIBLE (0x01) - gizli ancak görünür durumdaysa etkisizdir menüsünü görüntüler.<br />-AFX_MBS_HIDDEN (0x02) - gizler menü görünür ancak gizli hiçbir etkisi olmaz.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem menü durumu; başarılı bir şekilde değişirse Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı hatası meydana gelirse, bu yöntem hata ayıklama modunda onaylar ve türetilmiş bir özel durum oluşturur [CException](../../mfc/reference/cexception-class.md) sınıfı.  
  
##  <a name="setmenubarvisibility"></a>CFrameWnd::SetMenuBarVisibility  
 Gizli veya görünür olacak şekilde geçerli MFC uygulamasında menüsünün varsayılan davranışını ayarlar.  
  
```  
virtual void SetMenuBarVisibility(DWORD nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`nStyle`|Menü gizli, varsayılan olarak veya görünür durumda ve odağa sahip olup olmadığını belirtir. `nStyle` Parametresi, aşağıdaki değerleri sahip olabilir:<br /><br /> -AFX_MBV_KEEPVISIBLE (0X01)-<br />     Menü her zaman görüntülenir ve varsayılan olarak odağa sahip değil.<br />-AFX_MBV_DISPLAYONFOCUS (0X02)-<br />     Menü varsayılan olarak gizlidir. Menü gizli ise, menüsünü görüntüleme ve odağı vermek için ALT tuşuna basın. Menü görüntüleniyorsa, menüsünü gizlemek için ALT ya da ESC tuşuna basın.<br />-AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0X04)<br />     (Bitsel bir birleşimi (veya)) - menüsü varsayılan olarak gizlidir. Menü gizli ise, menüsünü görüntüleyin ve odaklanmak için F10 tuşuna basın. Menü görüntüleniyorsa, açın veya menü odak geçiş yapmak için F10 tuşuna basın. Gizlemek için ALT ya da ESC tuşuna basın kadar menüsü görüntülenir.|  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa değerini `nStyle` parametresi geçerli değil, bu yöntem başlatır ve hata ayıklama modu ile onaylar [CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md) yayın modunda. Diğer çalışma zamanı hataları durumunda, bu yöntem hata ayıklama modunda onaylar ve türetilmiş bir özel durum oluşturur [CException](../../mfc/reference/cexception-class.md) sınıfı.  
  
 Bu yöntem için yazılmış uygulamalar menülerde durumunu etkileyen [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] ve daha sonra.  
  
##  <a name="setmessagetext"></a>CFrameWnd::SetMessageText  
 Durum çubuğu bölmesinde bir kimliği 0 olan bir dize yerleştirmek için bu işlevini çağırın.  
  
```  
void SetMessageText(LPCTSTR lpszText);  
void SetMessageText(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszText`  
 Durum çubuğunda yerleştirilecek dizeye noktaları.  
  
 `nID`  
 Durum çubuğunda yerleştirilecek dize kaynak kimliği dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu genellikle soldaki ve en uzun, bölmesinde durum çubuğu olur.  
  
##  <a name="setprogressbarposition"></a>CFrameWnd::SetProgressBarPosition  
 Görev çubuğunda görüntülenen Windows 7 ilerleme çubuğu geçerli konumunu ayarlar.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Parametreler  
 `nProgressPos`  
 Ayarlamak için konumu belirtir. Tarafından belirlenen aralıkta olmalıdır `SetProgressBarRange`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setprogressbarrange"></a>CFrameWnd::SetProgressBarRange  
 Görev çubuğunda görüntülenen Windows 7 ilerleme çubuğu aralığını ayarlar.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>Parametreler  
 `nRangeMin`  
 En az değer.  
  
 `nRangeMax`  
 Üst düzeyde değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setprogressbarstate"></a>CFrameWnd::SetProgressBarState  
 Görev çubuğunda görüntülenen İlerleme göstergesi durumunu ve türünü ayarlar.  
  
```  
void SetProgressBarState(TBPFLAG tbpFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 `tbpFlags`  
 İlerleme düğmesi geçerli durumunu denetlemek bayraklar. Tüm durumları birbirini dışlayan olduğundan bayrakları yalnızca aşağıdakilerden birini belirtin: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settaskbaroverlayicon"></a>CFrameWnd::SetTaskbarOverlayIcon  
 Fazla Yüklendi. Bir katmana görev çubuğu düğmesi için uygulama durumunu belirten veya kullanıcıya bildirmek için geçerlidir.  
  
```  
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,  
    LPCTSTR lpcszDescr);

 
BOOL SetTaskbarOverlayIcon(
    HICON hIcon,  
    LPCTSTR lpcszDescr);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDResource`  
 Simge kaynak katmana kullanılacak Kimliğini belirtir. Açıklama için bkz: `hIcon` Ayrıntılar için.  
  
 `lpcszDescr`  
 Bir alternatif metin sürümü erişilebilirlik amacıyla bir katmana ifade ettiği bilgileri sağlayan bir dize için bir işaretçi.  
  
 `hIcon`  
 Bir katmana kullanılacak bir simge işleci. Bu 16 x 16 piksel 96 nokta / inç (dpi) konumunda ölçme küçük bir simge olması gerekir. Bir katmana simge görev çubuğu düğmesi uygulanırsa, bu varolan katmana değiştirilir. Bu değer `NULL`. Nasıl bir `NULL` değeri işlenir görev çubuğu düğmesini tek bir pencere veya Windows'un bir grubu temsil bağlıdır. Boşaltmak için çağrı yapan uygulamanın sorumluluğundadır `hIcon` zaman artık gerekli.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başarılı olursa; `FALSE` işletim sistemi sürümü Windows 7'den küçükse veya simgesi ayar bir hata meydana gelirse.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settitle"></a>CFrameWnd::SetTitle  
 Başlığı pencere nesnesi olarak ayarlar.  
  
```  
void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszTitle`  
 Pencere nesnesi başlığı içeren bir karakter dizesi için bir işaretçi.  
  
##  <a name="showcontrolbar"></a>CFrameWnd::ShowControlBar  
 Denetim çubuğunu göstermek veya gizlemek için bu üye işlevini çağırın.  
  
```  
void ShowControlBar(
    CControlBar* pBar,  
    BOOL bShow,  
    BOOL bDelay);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBar`  
 Denetim çubuğu gösterileceğini veya gizleneceğini için işaretçi.  
  
 `bShow`  
 Varsa **doğru**, denetim çubuğu gösterilecek olduğunu belirtir. Varsa **yanlış**, denetim çubuğu gizlenecek olduğunu belirtir.  
  
 *bDelay*  
 Varsa **doğru**, denetim çubuğu gösteren gecikme. Varsa **yanlış**, hemen çubuğu denetimi göster.  
  
##  <a name="showownedwindows"></a>CFrameWnd::ShowOwnedWindows  
 Alt öğeleri olan tüm pencereleri göstermek için bu üye işlevini çağırın `CFrameWnd` nesnesi.  
  
```  
void ShowOwnedWindows(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 `bShow`  
 Ait windows gösterileceğini veya gizleneceğini olup olmadığını belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd sınıfı](../../mfc/reference/cmdiframewnd-class.md)   
 [Cmdıchildwnd sınıfı](../../mfc/reference/cmdichildwnd-class.md)   
 [CView sınıfı](../../mfc/reference/cview-class.md)   
 [CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)   
 [CRuntimeClass yapısı](../../mfc/reference/cruntimeclass-structure.md)
