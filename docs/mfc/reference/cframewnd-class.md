---
title: CFrameWnd sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 991b8c55c02272613ce329be9a053ff0110f1926
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764881"
---
# <a name="cframewnd-class"></a>CFrameWnd sınıfı
Windows tek Belgeli Arabirim (SDI) çakışan veya açılır çerçeve penceresinde ve pencereyi yönetmek için üye işlevlerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFrameWnd : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFrameWnd::CFrameWnd](#cframewnd)|Oluşturur bir `CFrameWnd` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFrameWnd::ActivateFrame](#activateframe)|Çerçeve kullanıcıya görünür ve kullanılabilir hale getirir.|  
|[CFrameWnd::BeginModalState](#beginmodalstate)|Çerçeve penceresi için kalıcı ayarlar.|  
|[CFrameWnd::Create](#create)|Oluşturma ve başlatma ile ilişkili Windows çerçeve penceresi için çağrı `CFrameWnd` nesne.|  
|[CFrameWnd::CreateView](#createview)|Bir görünümü içinde türünden türetilmediğinden bir çerçeve oluşturur `CView`.|  
|[CFrameWnd::DockControlBar](#dockcontrolbar)|Denetim çubuğu docks.|  
|[CFrameWnd::EnableDocking](#enabledocking)|Yerleştirilemediğinde denetim çubuğu sağlar.|  
|[CFrameWnd::EndModalState](#endmodalstate)|Çerçeve penceresinin kalıcı durum sona erer. Tümünü devre dışı windows `BeginModalState`.|  
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|Denetim çubuğu kayar.|  
|[CFrameWnd::GetActiveDocument](#getactivedocument)|Etkin döndürür `CDocument` nesne.|  
|[CFrameWnd::GetActiveFrame](#getactiveframe)|Etkin döndürür `CFrameWnd` nesne.|  
|[CFrameWnd::GetActiveView](#getactiveview)|Etkin döndürür `CView` nesne.|  
|[CFrameWnd::GetControlBar](#getcontrolbar)|Denetim çubuğu alır.|  
|[CFrameWnd::GetDockState](#getdockstate)|Çerçeve penceresi dock durumunu alır.|  
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|Geçerli bir MFC uygulaması menüde görünen durumunu alır.|  
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|Geçerli bir MFC uygulaması menüde varsayılan davranışını gizli veya görünür olup olmadığını belirtir.|  
|[CFrameWnd::GetMessageBar](#getmessagebar)|Durum çubuğunda çerçeve penceresine ait bir işaretçi döndürür.|  
|[CFrameWnd::GetMessageString](#getmessagestring)|Bir komut kimliğine karşılık gelen iletiyi alır|  
|[CFrameWnd::GetTitle](#gettitle)|İlgili denetim çubuğu başlığını alır.|  
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|Neden `OnInitialUpdate` çağrılacak çerçeve penceresindeki tüm görünümlere ait üye işlevi.|  
|[CFrameWnd::InModalState](#inmodalstate)|Çerçeve penceresi kalıcı bir durumda olup olmadığını belirten bir değer döndürür.|  
|[CFrameWnd::IsTracking](#istracking)|Ayırıcıyı şu anda taşınırken, belirler.|  
|[CFrameWnd::LoadAccelTable](#loadacceltable)|Hızlandırıcı tablosunu yüklenecek çağırın.|  
|[CFrameWnd::LoadBarState](#loadbarstate)|Denetim çubuğu ayarları geri çağırma.|  
|[CFrameWnd::LoadFrame](#loadframe)|Çerçeve penceresi kaynak bilgilerini dinamik olarak oluşturmak için bunu çağırın.|  
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|Çerçeve penceresindeki kenarlık alanı görüşür.|  
|[CFrameWnd::OnBarCheck](#onbarcheck)|Belirtilen denetim çubuğu gerçekleştirilen bir eylem zaman çağrılır.|  
|[CFrameWnd::OnContextHelp](#oncontexthelp)|Yerinde öğeleri için SHIFT + F1 Yardımı işler.|  
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|Uygulamanın ana çerçeve penceresinin içine ve dışına Baskı Önizleme modunu ayarlar.|  
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|İlişkili menü güncelleştirildiğinde framework tarafından çağırılır.|  
|[CFrameWnd::RecalcLayout](#recalclayout)|Denetim çubukları yeniden konumlandırır `CFrameWnd` nesne.|  
|[CFrameWnd::SaveBarState](#savebarstate)|Denetim çubuğu ayarları kaydetmek için çağrılır.|  
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|Belirtilen görünüm Zengin Önizleme için etkin görünüm olarak belirler.|  
|[CFrameWnd::SetActiveView](#setactiveview)|Etkin ayarlar `CView` nesne.|  
|[CFrameWnd::SetDockState](#setdockstate)|Çerçeve penceresi ana penceresinde sabitlemek için çağırın.|  
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|Gizli veya gösterilen geçerli MFC uygulamasındaki menüsünde görünen durumunu ayarlar.|  
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|Gizli veya görünür olması için geçerli MFC uygulamasında menü'nın varsayılan davranışını ayarlar.|  
|[CFrameWnd::SetMessageText](#setmessagetext)|Standart durum çubuğu metninin ayarlar.|  
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|Windows 7 ilerleme çubuğu çubuğunda görüntülenen geçerli konumunu ayarlar.|  
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|Windows 7 ilerleme çubuğu çubuğunda görüntülenen aralığını ayarlar.|  
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|Görev çubuğunda görüntülenen İlerleme göstergesi durumunu ve türünü ayarlar.|  
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|Fazla Yüklendi. Uygulama durumu veya kullanıcıya bir bildirim belirtmek için bir görev çubuğunda düğme için bir katmana uygulanır.|  
|[CFrameWnd::SetTitle](#settitle)|İlgili denetim çubuğu başlığını ayarlar.|  
|[CFrameWnd::ShowControlBar](#showcontrolbar)|Denetim çubuğu gösterecek şekilde çağırın.|  
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|Alt öğeleri olan tüm windows gösterir `CFrameWnd` nesne.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFrameWnd::OnCreateClient](#oncreateclient)|Çerçeve için bir istemci penceresi oluşturur.|  
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|Geçerli bir MFC uygulaması menüde gizli önce çağrılır.|  
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|Geçerli bir MFC uygulaması menüde görüntülemeden önce çağrılır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|Otomatik denetimler etkinleştirin ve menü öğeleri için işlevini devre dışı bırakın.|  
|[CFrameWnd::rectDefault](#rectdefault)|Bu statik geçirmek `CRect` oluştururken bir parametre olarak bir `CFrameWnd` pencerenin başlangıç boyutu ve konumu seçmek Windows izin vermek için nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulamanız için kullanışlı bir çerçeve penceresi oluşturmak için öğesinden bir sınıf türetin `CFrameWnd`. Uygulamanıza özgü verileri depolamak için türetilmiş sınıf üye değişkenlerini ekleyin. Türetilen bir sınıfta iletileri penceresine yönlendirilirsiniz olduğunda ne olacağını belirlemek için uygulama ileti işleyicisi üye işlevleri ve bir ileti eşleyin.  
  
 Çerçeve penceresi oluşturmak için üç yolu vardır:  
  
-   Doğrudan kullanarak oluşturmak [Oluştur](#create).  
  
-   Doğrudan kullanarak oluşturmak [LoadFrame](#loadframe).  
  
-   Dolaylı olarak bir belge şablonu kullanarak oluşturun.  
  
 Ya da çağırmadan önce `Create` veya `LoadFrame`, C++ kullanarak yığın çerçeve pencere nesnesinde oluşturmalıdır **yeni** işleci. Çağırmadan önce `Create`, ayrıca, pencere sınıfı ile kaydedebilirsiniz [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) simgesi ve sınıf stilleri çerçevesi için ayarlanacak genel işlev.  
  
 Kullanım `Create` çerçeve oluşturma parametreleri olarak anında bağımsız değişkenleri geçirmek için üye işlevi.  
  
 `LoadFrame` daha az sayıda bağımsız değişken gerektirir `Create`ve bunun yerine varsayılan değerlerine çoğunu çerçevenin başlık, simgesi, Hızlandırıcı tablosu ve menü gibi kaynaklardan alır. Tarafından erişilebilir olmasını `LoadFrame`, tüm bu kaynaklar aynı kaynak kimliği (örneğin, IDR_MAINFRAME) olması gerekir.  
  
 Olduğunda bir `CFrameWnd` nesne, görünümleri ve belgeleri içerir, bunlar yerine doğrudan programcısı tarafından framework tarafından dolaylı olarak oluşturulur. `CDocTemplate` Çerçeve oluşturulmasını, içeren görünümler oluşturma ve uygun belge görünümleri bağlantı nesnesi düzenler. Parametreleri `CDocTemplate` Oluşturucusu belirtin `CRuntimeClass` üç sınıflarını dahil (belge, çerçeve ve Görünüm). A `CRuntimeClass` nesnesi (örneğin, dosya yeni komutunun veya birden çok belge arabirimi (MDI) penceresi yeni komutunu kullanarak) kullanıcı tarafından belirtilen yeni çerçeve dinamik olarak oluşturmak için framework tarafından kullanılır.  
  
 Öğesinden türetilen bir çerçeve pencere sınıf `CFrameWnd` DECLARE_DYNCREATE ile düzgün çalışması yukarıdaki RUNTIME_CLASS mekanizması için sırada bildirilmesi gerekir.  
  
 A `CFrameWnd` aşağıdaki işlevleri ana pencerenin, Windows için tipik bir uygulamada gerçekleştirmek için varsayılan uygulamaları içerir:  
  
-   A `CFrameWnd` çerçeve penceresinde Windows etkin pencere veya geçerli giriş odağını bağımsız bir etkin görünüm izler. Çerçeve etkinleştirildiğinde, etkin görünüm çağırarak bildirilir `CView::OnActivateView`.  
  
-   Komut iletileri ve tarafından işlenen dahil olmak üzere birçok ortak çerçeve bildirim iletileri `OnSetFocus`, `OnHScroll`, ve `OnVScroll` işlevlerini `CWnd`, tarafından verilmiş bir `CFrameWnd` çerçeve penceresine şu anda etkin.  
  
-   Şu anda etkin görünüm (veya etkin MDI alt çerçeve penceresi bir MDI çerçeve söz konusu olduğunda) çerçeve penceresinin başlığını belirleyebilirsiniz. Çerçeve penceresi fws_addtotıtle stili bit devre dışı bırakarak bu özelliği devre dışı bırakılabilir.  
  
-   A `CFrameWnd` çerçeve penceresi, Denetim çubukları, görünümler ve çerçeve penceresinin istemci alanı içindeki diğer alt pencereleri konumlandırma yönetir. Bir çerçeve penceresi araç çubuğu ve diğer denetim çubuğu düğmeleri boşta kalma süresi güncelleştirme de yapar. A `CFrameWnd` çerçeve penceresi de varsayılan uygulamaları açma ve kapatma araç çubuğu ve durum çubuğu geçiş için komutları vardır.  
  
-   A `CFrameWnd` çerçeve penceresi yöneten ana menü çubuğu. Çerçeve penceresi UPDATE_COMMAND_UI mekanizması açılır menü görüntülendiğinde, hangi menü öğelerini etkin, devre dışı işaretli veya belirlemek için kullanır. Kullanıcı bir menü öğesi seçtiğinde, çerçeve penceresi durum çubuğunun komutun ileti dizesi güncelleştirir.  
  
-   A `CFrameWnd` çerçeve penceresi otomatik olarak klavye Hızlandırıcılar çeviren isteğe bağlı Hızlandırıcı tablosunu sahiptir.  
  
-   A `CFrameWnd` çerçeve penceresi ile ayarlanmış bir isteğe bağlı Yardım Kimliğe sahip `LoadFrame` bağlama duyarlı Yardım için kullanılır. Bağlama duyarlı Yardım (SHIFT + F1) ve Baskı Önizleme modlarında gibi yarı kalıcı durumlar'ın ana orchestrator çerçeve penceresidir.  
  
-   A `CFrameWnd` Dosya Yöneticisi'nden sürüklenebilen ve çerçeve penceresinde bırakılan bir dosyayı çerçeve penceresi açılır. Bir dosya uzantısı kayıtlı ve uygulama ile ilişkili çerçeve penceresi, kullanıcı bir veri dosyası Dosya Yöneticisi'nde açtığında veya oluşur dinamik veri değişimi (DDE) açık isteğine yanıt vermeden `ShellExecute` Windows işlevi çağrılır.  
  
-   Çerçeve penceresi ana uygulama penceresini ise (diğer bir deyişle, `CWinThread::m_pMainWnd`), kullanıcı uygulama kapandığında çerçeve penceresi tüm değiştirilmiş belgeleri kaydetmek için kullanıcıdan (için `OnClose` ve `OnQueryEndSession`).  
  
-   Çerçeve penceresi ana uygulama penceresini ise, çerçeve penceresi WinHelp çalıştırmak için bağlamdır. Çerçeve penceresi kapatma WINHELP kapat. Bu uygulama için Yardım için başlatıldıysa EXE.  
  
 C++ kullanmayın **Sil** çerçeve penceresini yok etmek için işleci. Bunun yerine `CWnd::DestroyWindow` kullanın. `CFrameWnd` Uygulaması `PostNcDestroy` penceresi kaldırıldığında C++ nesnesi siler. Kullanıcının varsayılan çerçeve penceresi kapattığı zaman `OnClose` işleyici çağırır `DestroyWindow`.  
  
 Daha fazla bilgi için `CFrameWnd`, bkz: [çerçeve Windows](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="activateframe"></a>  CFrameWnd::ActivateFrame  
 Etkinleştirme ve böylece kullanıcıya görünür ve kullanılabilir çerçeve penceresi geri yüklemek için bu üye işlevini çağırın.  
  
```  
virtual void ActivateFrame(int nCmdShow = -1);
```  
  
### <a name="parameters"></a>Parametreler  
 *nCmdShow*  
 Geçirilecek parametreyi belirtir [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow). Varsayılan olarak, çerçeve gösterilen ve doğru bir şekilde geri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlev, genellikle DDE, OLE ve çerçeve penceresi ya da içeriğini kullanıcıya gösterebilir başka bir olay gibi bir Kullanıcısız arabirimi olayından sonra çağrılır.  
  
 Varsayılan Uygulama Çerçevesi etkinleştirir ve Z düzenini en üstüne getirir ve gerekirse, uygulamanın ana çerçeve penceresi için aynı adımları yapar.  
  
 Bu üye işlevi bir çerçeve nasıl etkinleştirileceğini değiştirmek için geçersiz kılın. Örneğin, MDI alt pencereleri ekranı için zorlayabilirsiniz. Uygun işlevselliği ekleyin ve ardından açık bir temel sınıf sürümüyle çağrı *nCmdShow*.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]  
  
##  <a name="beginmodalstate"></a>  CFrameWnd::BeginModalState  
 Çerçeve penceresi kalıcı hale getirmek için bu üye işlevini çağırın.  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="cframewnd"></a>  CFrameWnd::CFrameWnd  
 Oluşturur bir `CFrameWnd` nesne, ancak görünür çerçeve penceresi oluşturmaz.  
  
```  
CFrameWnd();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `Create` görünür pencere oluşturmak için.  
  
##  <a name="create"></a>  CFrameWnd::Create  
 Oluşturma ve başlatma ile ilişkili Windows çerçeve penceresi için çağrı `CFrameWnd` nesne.  
  
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
 *lpszClassName*  
 Windows sınıf adları null ile sonlandırılmış dizeye işaret eder. Sınıf adı ile kayıtlı herhangi bir ad olabilir `AfxRegisterWndClass` genel işlev veya `RegisterClass` Windows işlevi. NULL ise, önceden tanımlanmış varsayılan kullanan `CFrameWnd` öznitelikleri.  
  
 *lpszWindowName*  
 Pencere adının temsil eden bir boş sonlandırılmış karakter dizesi işaret eder. Başlık çubuğunu metin olarak kullanılır.  
  
 *dwStyle*  
 Pencerenin belirtir [stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) öznitelikleri. Otomatik olarak penceresinde gösterilen belgenin adını görüntülemek için başlık çubuğu istiyorsanız fws_addtotıtle stili içerir.  
  
 *Rect*  
 Pencerenin konumunu ve boyutunu belirtir. *RectDefault* değer, yeni pencerenin konumunu ve boyutunu belirtmek Windows sağlar.  
  
 *pParentWnd*  
 Bu çerçeve penceresinin üst pencere belirtir. Bu parametre, üst düzey çerçeve pencereleri için NULL olmalıdır.  
  
 *lpszMenuName*  
 Pencere ile kullanılmak üzere menü kaynağı adını tanımlar. Menüden bir dize yerine tamsayı Kimliğine sahip MAKEINTRESOURCE kullanın. Bu parametre NULL olabilir.  
  
 *dwExStyle*  
 Genişletilmiş pencere belirtir [stili](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) öznitelikleri.  
  
 *pContext*  
 Bir işaretçi belirtir bir [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısı. Bu parametre NULL olabilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlatma başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CFrameWnd` iki adımda nesne. İlk olarak, oluşturan Oluşturucu çağırmak `CFrameWnd` nesnesi ve ardından arama `Create`, Windows çerçeve penceresi oluşturur ve ona ekler `CFrameWnd` nesne. `Create` pencere sınıfı adı ve penceresi adı başlatır ve stil, üst ve ilişkili menü varsayılan değerleri kaydeder.  
  
 Kullanım `LoadFrame` yerine `Create` bağımsız değişkenlerini belirtmek yerine, bir kaynaktan çerçeve penceresi yüklenemedi.  
  
##  <a name="createview"></a>  CFrameWnd::CreateView  
 Çağrı `CreateView` bir çerçevesinde bir görünüm oluşturmak için.  
  
```  
CWnd* CreateView(
    CCreateContext* pContext,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>Parametreler  
 *pContext*  
 Görünüm ve belge türünü belirtir.  
  
 *nID*  
 Bir görünüm kimliği sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir `CWnd` nesne başarılı; Aksi takdirde NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Olmayan "görünümler" oluşturmak için bu üye işlevini `CView`-türetilmiş bir çerçeve içinde. Arama sonra `CreateView`, el ile görünümü etkin olarak ayarlanmış ve görünür olması için ayarlamanız gerekir; bu görevler tarafından otomatik olarak gerçekleştirilmez `CreateView`.  
  
##  <a name="dockcontrolbar"></a>  CFrameWnd::DockControlBar  
 Çerçeve penceresi için yerleştirilmiş olması bir denetim çubuğu neden olur.  
  
```  
void DockControlBar(
    CControlBar* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *pBar*  
 Yerleştirilemediğinde denetim çubuğu işaret eder.  
  
 *nDockBarID*  
 Hangi yerleştirme için dikkate alınması gereken çerçeve penceresi taraflı belirler. 0 veya bir veya daha fazla aşağıdakiler olabilir:  
  
- Çerçeve penceresinin üst tarafındaki AFX_IDW_DOCKBAR_TOP yerleştir.  
  
- Çerçeve penceresinin alt tarafındaki AFX_IDW_DOCKBAR_BOTTOM yerleştir.  
  
- Çerçeve penceresinin sol tarafındaki AFX_IDW_DOCKBAR_LEFT yerleştir.  
  
- Çerçeve penceresinin sağ tarafındaki AFX_IDW_DOCKBAR_RIGHT yerleştir.  
  
 0 ise, denetim çubuğu hedef çerçeve penceresinde yerleştirme için etkin bir tarafına sabitlenebilir.  
  
 *lpRect*  
 , Hedef çerçeve penceresinin istemci olmayan alanda denetim çubuğu nereye yerleştirilir ekran koordinatlarında belirler.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubuğu bir çerçeve penceresi hem yapılan çağrıda belirtilen tarafının yerleştirilmiş [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) ve [CFrameWnd::EnableDocking](#enabledocking). Yan seçilen belirlenir *nDockBarID*.  
  
##  <a name="enabledocking"></a>  CFrameWnd::EnableDocking  
 Bir çerçeve penceresinde yerleştirilebilir denetim çubukları etkinleştirmek için bu işlevi çağırın.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwDockStyle*  
 Çerçeve penceresi hangi kenarlarına siteler için Denetim çubukları yerleştirme olarak hizmet verebilen belirtir. Bir veya daha fazlasını olabilir:  
  
- İstemci alanının en üstünde yerleştirme CBRS_ALIGN_TOP sağlar.  
  
- İstemci alanının altındaki yerleştirme CBRS_ALIGN_BOTTOM sağlar.  
  
- CBRS_ALIGN_LEFT istemci alanını sol tarafta yerleştirmeye izin verir.  
  
- CBRS_ALIGN_RIGHT istemci alanının sağ tarafta yerleştirmeye izin verir.  
  
- Cbrs_alıgn_any istemci alanının herhangi bir tarafta yerleştirmeye izin verir.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubukları varsayılan olarak, aşağıdaki sırayla çerçeve penceresinin bir tarafa yerleştirilir: üst, alt, sol, sağ.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CToolBar::Create](../../mfc/reference/ctoolbar-class.md#create).  
  
##  <a name="endmodalstate"></a>  CFrameWnd::EndModalState  
 Çerçeve penceresi kalıcı için geçici değiştirmek için bu üye işlevini çağırın.  
  
```  
virtual void EndModalState();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `EndModalState` Tümünü devre dışı windows [BeginModalState](#beginmodalstate).  
  
##  <a name="floatcontrolbar"></a>  CFrameWnd::FloatControlBar  
 Çerçeve penceresi için yerleştirilmemişse bir denetim çubuğu neden olmak için bu işlevi çağırın.  
  
```  
void FloatControlBar(
    CControlBar* pBar,  
    CPoint point,  
    DWORD dwStyle = CBRS_ALIGN_TOP);
```  
  
### <a name="parameters"></a>Parametreler  
 *pBar*  
 Denetim çubuğu kaydırıldı için işaret eder.  
  
 *Noktası*  
 Denetim çubuğunun sol üst köşesindeki yerleştirileceği konumu, ekran koordinatları.  
  
 *dwStyle*  
 Denetim çubuğu, yeni bir çerçeve penceresi içinde yatay veya dikey olarak Hizala belirtir. Bu, aşağıdakilerden herhangi biri olabilir:  
  
- CBRS_ALIGN_TOP denetim çubuğu dikey olarak yönlendirir.  
  
- CBRS_ALIGN_BOTTOM denetim çubuğu dikey olarak yönlendirir.  
  
- CBRS_ALIGN_LEFT denetim çubuğu yatay olarak yönlendirir.  
  
- CBRS_ALIGN_RIGHT denetim çubuğu yatay olarak yönlendirir.  
  
 Stilleri yatay ve dikey hizalama belirtme geçirilmezse, araç yatay yönlendirilmiş olacaktır.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, bu programın önceki yürütmeyi ayarlarını yüklerken uygulama başlangıcında gerçekleştirilir.  
  
 Kullanıcının sol fare düğmesini serbest bırakma yerleştirme için kullanılabilir olmayan bir konum üzerinden denetim çubuğunu sürüklerken bir bırakma işlemi neden olduğunda bu işlev çerçeve tarafından çağrılır.  
  
##  <a name="getactivedocument"></a>  CFrameWnd::GetActiveDocument  
 Geçerli bir işaretçi alma için bu üye işlevini çağırın `CDocument` geçerli etkin görünüme iliştirilmiş.  
  
```  
virtual CDocument* GetActiveDocument();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi [CDocument](../../mfc/reference/cdocument-class.md). Geçerli belge yok ise NULL döndürür.  
  
##  <a name="getactiveframe"></a>  CFrameWnd::GetActiveFrame  
 Bir MDI çerçeve penceresinin Çok Belgeli Arabirim (MDI) alt penceresi etkin bir işaretçi alma için bu üye işlevini çağırın.  
  
```  
virtual CFrameWnd* GetActiveFrame();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etkin MDI alt penceresine bir işaretçi. Uygulama bir SDI uygulamasıdır veya MDI çerçeve penceresinin, örtük etkin hiçbir belge sahip **bu** işaretçi döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkin MDI alt öğesi yok veya bir tek Belgeli Arabirim (SDI) örtük uygulamasıdır **bu** işaretçi döndürülür.  
  
##  <a name="getactiveview"></a>  CFrameWnd::GetActiveView  
 Çerçeve pencere bağlı etkin görünüm (varsa) bir işaretçi alma için bu üye işlevini çağırın ( `CFrameWnd`).  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi [CView](../../mfc/reference/cview-class.md). Geçerli Görünüm ise NULL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, MDI ana çerçeve penceresi için çağrıldığında NULL döndürür ( `CMDIFrameWnd`). Bir MDI uygulamasında MDI ana çerçeve penceresinin ilişkili bir görünüm yok. Bunun yerine, her ayrı alt penceresi ( `CMDIChildWnd`) bir veya daha fazla ilişkili görünüme sahiptir. Bir MDI uygulamasında etkin görünüm önce etkin MDI alt penceresine bularak ve sonra o alt penceresi etkin bulma elde edilebilir. Etkin MDI alt penceresine işlevi çağrılarak bulunabilir `MDIGetActive` veya `GetActiveFrame` aşağıda gösterildiği gibi:  
  
 [!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]  
  
##  <a name="getcontrolbar"></a>  CFrameWnd::GetControlBar  
 Çağrı `GetControlBar` kimliğiyle ilişkili denetim çubuğu erişim elde etmek için  
  
```  
CControlBar* GetControlBar(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *nID*  
 Denetim çubuğu kimliği sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi kimliğiyle ilişkili denetim çubuğu  
  
### <a name="remarks"></a>Açıklamalar  
 *NID* parametresi için geçirilen benzersiz tanımlayıcısı başvurduğu `Create` yöntemi denetim çubuğu. Denetim çubukları hakkında daha fazla bilgi için başlıklı konuya bakın [denetim çubukları](../../mfc/control-bars.md).  
  
 `GetControlBar` denetim çubuğu kayan olduğu ve bu nedenle şu anda bir alt pencere çerçevesi değil olsa bile döndürür.  
  
##  <a name="getdockstate"></a>  CFrameWnd::GetDockState  
 Çerçeve penceresinin denetim çubuklarını hakkındaki durum bilgilerini depolamak için bu üye işlevi çağrısı bir `CDockState` nesne.  
  
```  
void GetDockState(CDockState& state) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *durumu*  
 Çerçeve penceresinin denetim çubukları iade sırasında geçerli durumunu içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Ardından içeriğini yazabileceğiniz `CDockState` depolama kullanarak `CDockState::SaveState` veya `Serialize`. Daha sonra Denetim çubukları önceki bir duruma geri yüklemek isterseniz durumuyla yük `CDockState::LoadState` veya `Serialize`, ardından çağırın `SetDockState` çerçeve penceresinin denetim çubukları için önceki bir duruma uygulamak için.  
  
##  <a name="getmenubarstate"></a>  CFrameWnd::GetMenuBarState  
 Geçerli bir MFC uygulaması menüde görünen durumunu alır.  
  
```  
virtual DWORD GetMenuBarState();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri, aşağıdaki değerlere sahip olabilir:  
  
-   AFX_MBS_VISIBLE (0x01) - menü görünür.  
  
-   AFX_MBS_HIDDEN (0x02) - menü gizlenir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir çalışma zamanı hatası meydana gelirse, hata ayıklama modunda onaylar ve türetilen özel durum harekete [CException](../../mfc/reference/cexception-class.md) sınıfı.  
  
##  <a name="getmenubarvisibility"></a>  CFrameWnd::GetMenuBarVisibility  
 Geçerli bir MFC uygulaması menüde varsayılan durumu gizli veya görünür olup olmadığını belirtir.  
  
```  
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem aşağıdaki değerlerden birini döndürür:  
  
-   AFX_MBV_KEEPVISIBLE (0x01) - menüsünde görüntülenen tüm süreleri ve tarafından varsayılan odağa sahip değil.  
  
-   AFX_MBV_DISPLAYONFOCUS (0x02) - menüsünde varsayılan olarak gizlidir. Menü gizli ise, menüsünü görüntüleyin ve odaklanmak için ALT tuşuna basın. Menü gösterilirse, gizlemek için ALT ya da ESC tuşuna basın.  
  
-   AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04) (karşılaştırmaya (veya)) - menüsünde varsayılan olarak gizlidir. Menü gizli ise, menüsünü görüntüleyin ve odaklanmak için F10 tuşuna basın. Menü gösterilirse, veya menüyü Kapat odağı değiştirilecek F10 tuşuna basın. Kadar gizlemek için ALT ya da ESC tuşuna basın menüsü görüntülenir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir çalışma zamanı hatası meydana gelirse, hata ayıklama modunda onaylar ve türetilen özel durum harekete [CException](../../mfc/reference/cexception-class.md) sınıfı.  
  
##  <a name="getmessagebar"></a>  CFrameWnd::GetMessageBar  
 Durum çubuğu için bir işaretçi almak için bu üye işlevini çağırın.  
  
```  
virtual CWnd* GetMessageBar();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durum çubuğu pencere işaretçisi.  
  
##  <a name="getmessagestring"></a>  CFrameWnd::GetMessageString  
 Komut kimlikleri için özel dizeleri sağlamak için bu işlevi geçersiz kılar.  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nID*  
 İstenen iletinin kaynak kimliği.  
  
 *rMessage*  
 `CString` ileti yerleştirileceği nesnesine.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama tarafından belirtilen dize yalnızca yükler *nID* kaynak dosyasından. Bu işlev, durum çubuğundaki ileti dizesinin güncellenmesi gerektiğinde framework tarafından çağırılır.  
  
##  <a name="gettitle"></a>  CFrameWnd::GetTitle  
 Pencere nesnesi başlığını alır.  
  
```  
CString GetTitle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) pencere nesnesi geçerli başlığını içeren nesne.  
  
##  <a name="initialupdateframe"></a>  CFrameWnd::InitialUpdateFrame  
 Çağrı `IntitialUpdateFrame` ile yeni bir çerçeve oluşturduktan sonra `Create`.  
  
```  
void InitialUpdateFrame(
    CDocument* pDoc,  
    BOOL bMakeVisible);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDoc*  
 Çerçeve penceresi ilişkilendirilen belge işaret eder. NULL olabilir.  
  
 *bMakeVisible*  
 TRUE ise bir çerçeve görünür ve etkin olması gerektiğini gösterir. FALSE ise, hiçbir alt öğeleri görünür hale getirilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tüm görünümlere almak için bu çerçeve penceresinde neden olur, `OnInitialUpdate` çağırır.  
  
 Ayrıca, yoksa daha önce etkin bir görünüm, çerçeve penceresinin birincil görünüm etkinleştirilir. Birincil görünüm Kimliği'nın AFX_IDW_PANE_FIRST alt ile bir görünümüdür. Son olarak, çerçeve penceresi görünür hale gelir, *bMakeVisible* sıfır değil. Varsa *bMakeVisible* 0 ise, geçerli odak ve çerçeve penceresi görünür durumunu değişmeden kalır. Framework'ün uygulaması dosya yeni ve Dosya Aç kullanırken bu işlevi çağırmak gerekli değildir.  
  
##  <a name="inmodalstate"></a>  CFrameWnd::InModalState  
 Çerçeve penceresi kalıcı veya geçici olup olmadığını denetlemek için bu üye işlevini çağırın.  
  
```  
BOOL InModalState() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yanıt Evet ise sıfır olmayan; Aksi durumda 0.  
  
##  <a name="istracking"></a>  CFrameWnd::IsTracking  
 Ayırıcıyı penceresinde şu anda taşınırken, belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsTracking() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölme işlemi devam ederken olursa sıfır dışı; Aksi durumda 0.  
  
##  <a name="loadacceltable"></a>  CFrameWnd::LoadAccelTable  
 Belirtilen Hızlandırıcı tablosu yüklenecek çağırın.  
  
```  
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszResourceName*  
 Hızlandırıcı kaynak adını tanımlar. Bir tamsayı kimliği ile kaynak belirlenirse MAKEINTRESOURCE kullanın  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hızlandırıcı tablosu başarıyla yüklendi olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kerede yalnızca bir tabloya yüklenebilir.  
  
 Hızlandırıcı tablolarını kaynaklardan yüklenen, uygulama sonlandığında otomatik olarak kurtulurlar.  
  
 Eğer `LoadFrame` çerçeve penceresi oluşturmak için menü ve simge kaynakları birlikte Hızlandırıcı tablosunu framework yükler ve ardından sonraki çağrı bu üye işlevi için gerekli değildir.  
  
##  <a name="loadbarstate"></a>  CFrameWnd::LoadBarState  
 Çerçeve penceresi tarafından sahip olunan her denetim çubuğu ayarları geri yüklemek için bu işlevi çağırın.  
  
```  
void LoadBarState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszProfileName*  
 Başlatma (INI) dosyasının bir bölümünde veya durum bilgilerini depolandığı Windows kayıt defteri anahtarı adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Görünürlük, yatay dikey yönde, yerleştirme durumu ve denetim çubuğu konumu geri bilgileri içerir.  
  
 Çağırmadan önce geri yüklemek istediğiniz ayarları kayıt defterine yazılmalıdır `LoadBarState`. Çağırarak kayıt defterine bilgi yazma [CWinApp::SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey). Çağırarak bilgileri INI dosyaya yazmak [SaveBarState](#savebarstate).  
  
##  <a name="loadframe"></a>  CFrameWnd::LoadFrame  
 Çerçeve penceresi kaynak bilgilerini dinamik olarak oluşturmak için bunu çağırın.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDResource*  
 Çerçeve penceresi ile ilişkilendirilmiş paylaşılan kaynakları kimliği.  
  
 *dwDefaultStyle*  
 Çerçeve [stil](../../mfc/reference/styles-used-by-mfc.md#window-styles). Otomatik olarak penceresinde gösterilen belgenin adını görüntülemek için başlık çubuğu istiyorsanız fws_addtotıtle stili içerir.  
  
 *pParentWnd*  
 Ana çerçeve işaretçisi.  
  
 *pContext*  
 Bir işaretçi bir [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısı. Bu parametre NULL olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CFrameWnd` iki adımda nesne. İlk olarak, oluşturan Oluşturucu çağırmak `CFrameWnd` nesnesi ve ardından arama `LoadFrame`, Windows çerçeve penceresi ve ilişkili kaynakları yükler ve ekler için çerçeve penceresi `CFrameWnd` nesne. *NIDResource* parametresi, menü, Hızlandırıcı tablosu, simge ve çerçeve penceresinin başlığını, dize kaynağını belirtir.  
  
 Kullanım `Create` üye işlevi yerine `LoadFrame` tüm çerçeve penceresinin oluşturma parametreleri belirtmek istediğinizde.  
  
 Framework çağrıları `LoadFrame` bir belge şablonu nesnesi kullanarak bir çerçeve penceresi oluşturduğunda.  
  
 Framework kullanan *pContext* dahil çerçeve penceresine bağlanması nesneleri belirlemek için bağımsız değişken bulunan nesneleri görüntüle. Ayarlayabileceğiniz *pContext* çağırdığınızda NULL bağımsız değişkeni `LoadFrame`.  
  
##  <a name="m_bautomenuenable"></a>  CFrameWnd::m_bAutoMenuEnable  
 Bu veri üyesi (varsayılan değer olan) etkin olduğunda, kullanıcı bir menüyü çeker, on_update_command_uı veya ON_COMMAND işleyicilere sahip değil menü öğelerini otomatik olarak devre dışı bırakılır.  
  
```  
BOOL m_bAutoMenuEnable;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 ON_COMMAND işleyici ancak hiçbir on_update_command_uı işleyicisi menü öğelerini otomatik olarak etkinleştirilecektir.  
  
 Bu veri üyesi olarak ayarlandığında menü öğeleri araç çubuğu düğmeleri etkinleştirildiğini aynı şekilde otomatik olarak etkinleştirilir.  
  
> [!NOTE]
> `m_bAutoMenuEnable` üst düzey menü öğeleri üzerinde etkisi yoktur.  
  
 Bu veri üyesi, isteğe bağlı komut geçerli seçime dayanan uygulama basitleştirir ve menü öğelerini devre dışı bırakma ve etkinleştirme on_update_command_uı işleyicileri yazma ihtiyacını azaltır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]  
  
##  <a name="negotiateborderspace"></a>  CFrameWnd::NegotiateBorderSpace  
 OLE yerinde etkinleştirme sırasında bir çerçeve penceresinde kenarlık alanı anlaşmak üzere bu üye işlevini çağırın.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>Parametreler  
 *nBorderCmd*  
 Aşağıdaki değerlerden birini içeren `enum BorderCmd`:  
  
- `borderGet` = 1  
  
- `borderRequest` = 2  
  
- `borderSet` = 3  
  
 *lpRectBorder*  
 İşaretçi bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesini kenarlık koordinatlarını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi olan `CFrameWnd` OLE kenarlık alanı anlaşma uygulamasıdır.  
  
##  <a name="onbarcheck"></a>  CFrameWnd::OnBarCheck  
 Belirtilen denetim çubuğu gerçekleştirilen bir eylem zaman çağrılır.  
  
```  
afx_msg BOOL OnBarCheck(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *nID*  
 Gösterilen çubuğu denetiminin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim çubuğu varolan olursa sıfır dışı; Aksi durumda 0.  
  
##  <a name="oncontexthelp"></a>  CFrameWnd::OnContextHelp  
 Yerinde öğeleri için SHIFT + F1 Yardımı işler.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlama duyarlı Yardım'ı etkinleştirmek için eklemelisiniz bir  
  
 [!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]  
  
 deyimi, `CFrameWnd` sınıf ileti eşlemesi ve de genellikle üst karakter + bu üye işlevini etkinleştirmek için F1, bir Hızlandırıcı tablosunu giriş ekleme.  
  
 Uygulamanız bir OLE kapsayıcı ise `OnContextHelp` Yardım moduna çerçeve pencere nesnesi içinde yer alan tüm yerinde öğeleri koyar. İmleç değişiklikleri bir ok, soru işareti ve kullanıcının fare işaretçisini ve bir iletişim kutusu, pencere, menü ya da komut düğmesi seçmek için farenin sol düğmesine basın. Bu üye işlevi Windows işlevini çağırır `WinHelp` imleç altındaki Nesne Yardım içeriğine sahip.  
  
##  <a name="oncreateclient"></a>  CFrameWnd::OnCreateClient  
 Framework tarafından yürütülmesi sırasında çağırılır `OnCreate`.  
  
```  
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpcs*  
 Bir Windows işaretçisi [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) yapısı.  
  
 *pContext*  
 Bir işaretçi bir [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir zaman bu işlevi çağırın.  
  
 Bu işlev varsayılan uygulamasını oluşturur bir `CView` sağlanan bilgileri nesneden *pContext*, mümkünse.  
  
 Bu işlev, geçirilen değerleri geçersiz kılmak için geçersiz kılma `CCreateContext` nesne veya değiştirmek için şekilde denetimleri çerçeve penceresinin ana istemci alanında oluşturulur. `CCreateContext` Üyeleri geçersiz kılma açıklanmıştır [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) sınıfı.  
  
> [!NOTE]
>  Geçirilen değerleri değiştirmeyin `CREATESTRUCT` yapısı. Bunlar, yalnızca bilgilendirme amaçlı. Başlangıç penceresi dikdörtgen geçersiz kılmak istiyorsanız, örneğin, geçersiz kılma `CWnd` üye işlevi [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).  
  
##  <a name="onhidemenubar"></a>  CFrameWnd::OnHideMenuBar  
 Sistem geçerli MFC uygulaması menü çubuğundaki hakkında gizlemek için olduğunda bu işlev çağrılır.  
  
```  
virtual void OnHideMenuBar();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu olay işleyicisi, sistem hakkında menüyü Gizle olduğunda özel eylemleri gerçekleştirmek uygulamanızı sağlar. Gizlenmelerini menü engelleyemez. ancak, örneğin, menü stil veya durumunu almak için diğer yöntemleri çağırabilirsiniz.  
  
##  <a name="onsetpreviewmode"></a>  CFrameWnd::OnSetPreviewMode  
 Uygulamanın ana çerçeve penceresinin içine ve dışına Yazdır-Önizle moduna ayarlamak için bu üye işlevini çağırın.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parametreler  
 *bPreview*  
 Uygulama Yazdır-Önizle moduna gerekip gerekmediğini belirtir. Baskı Önizleme, Önizlemeyi iptal etmek için FALSE yerleştirmek için TRUE olarak ayarlayın.  
  
 *pState*  
 Bir işaretçi bir `CPrintPreviewState` yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama, tüm standart araç çubuklarını devre dışı bırakır ve ana menü ve ana istemci penceresini gizler. Bu, geçici SDI çerçeve pencereleri MDI çerçeve pencereleri kapatır.  
  
 Baskı Önizleme sırasında denetim çubuklarını ve diğer çerçeve penceresi parçalarının gösterme ve gizleme özelleştirmek için bu üye işlevini geçersiz kılar. Geçersiz kılınan sürüm içinde temel sınıf uygulamasından çağırın.  
  
##  <a name="onshowmenubar"></a>  CFrameWnd::OnShowMenuBar  
 Sistem menü çubuğu hakkında geçerli bir MFC uygulamasında görüntülenecek olduğunda bu işlev çağrılır.  
  
```  
virtual void OnShowMenuBar();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu olay işleyicisi menü gösterilmek üzereyken özel eylemleri gerçekleştirmek uygulamanızı sağlar. Menüde görüntülenmesini önlemesini olamaz, ancak örneğin, menü stil veya durumunu almak için diğer yöntemler çağırabilirsiniz.  
  
##  <a name="onupdatecontrolbarmenu"></a>  CFrameWnd::OnUpdateControlBarMenu  
 İlişkili menü güncelleştirildiğinde framework tarafından çağırılır.  
  
```  
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parametreler  
 *pCmdUI*  
 Bir işaretçi bir [Ccmduı](../../mfc/reference/ccmdui-class.md) güncelleştirme komut oluşturulan menü temsil eden nesne. Güncelleştirme işleyicisi çağrılarını [etkinleştirme](../../mfc/reference/ccmdui-class.md#enable) üye işlevinin `CCmdUI` nesnesi aracılığıyla *pCmdUI* kullanıcı arabirimini güncelleştirmek için.  
  
##  <a name="recalclayout"></a>  CFrameWnd::RecalcLayout  
 Standart denetim çubukları, açılıp kapatıldığında veya çerçeve penceresi yeniden boyutlandırıldığında framework tarafından çağırılır.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bNotify*  
 Çerçeve penceresi için etkin yerinde öğeyi Düzen değişiklik bildirimi alıp almayacağını belirler. TRUE ise öğe bildirilir; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevini varsayılan uygulamasını çağırır `CWnd` üye işlevi `RepositionBars` çerçevesinde de ana istemci pencereyi olduğu gibi tüm denetim çubukları yeniden konumlandırmak için (genellikle bir `CView` veya MDICLIENT).  
  
 Çerçeve penceresi düzenini değiştirildikten sonra Denetim çubukları davranışını ve görünümünü kontrol etmek için bu üye işlevini geçersiz kılar. Örneğin, Denetim çubukları Aç veya kapat veya başka bir denetim çubuğu eklediğinizde, çağırın.  
  
##  <a name="rectdefault"></a>  CFrameWnd::rectDefault  
 Bu statik geçirmek `CRect` pencerenin başlangıç boyutu ve konumu seçmek Windows izin vermek için bir pencere oluşturma sırasında bir parametre olarak.  
  
```  
static AFX_DATA const CRect rectDefault;  
```  
  
##  <a name="savebarstate"></a>  CFrameWnd::SaveBarState  
 Çerçeve penceresi tarafından sahip olunan her denetim çubuğu hakkında bilgi depolamak için bu işlevi çağırın.  
  
```  
void SaveBarState(LPCTSTR lpszProfileName) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszProfileName*  
 Bir bölümde bir başlatma dosyası veya bir durum bilgilerini depolandığı Windows kayıt defteri anahtarı adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bilgileri kullanarak başlatma dosyası okunabilir [LoadBarState](#loadbarstate). Görünürlük durumu ve denetim çubuğu konumunu yerleştirme yatay dikey yönde, depolanan bilgileri içerir.  
  
##  <a name="setactivepreviewview"></a>  CFrameWnd::SetActivePreviewView  
 Belirtilen görünüm Zengin Önizleme için etkin görünüm olarak belirler.  
  
```  
void SetActivePreviewView(CView* pViewNew);
```  
  
### <a name="parameters"></a>Parametreler  
 *pViewNew*  
 Etkinleştirilecek bir görünüm için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setactiveview"></a>  CFrameWnd::SetActiveView  
 Etkin görünüm ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetActiveView(
    CView* pViewNew,  
    BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *pViewNew*  
 Bir işaretçi belirtir bir [CView](../../mfc/reference/cview-class.md) nesne ya da etkin görünüm için NULL.  
  
 *bNotify*  
 Görünüm etkinleştirme bildirilmesi için olup olmadığını belirtir. TRUE ise `OnActivateView` için yeni bir görünümü; yanlış değilse çağrılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir görünüme çerçeve penceresi içinde odak değiştikçe framework otomatik olarak bu işlevi çağıracaktır. Açıkça çağırabilirsiniz `SetActiveView` odağı belirtilen görünümünü değiştirmek için.  
  
##  <a name="setdockstate"></a>  CFrameWnd::SetDockState  
 Saklanan durum bilgilerini uygulamak için bu üye işlevi çağrısı bir `CDockState` çerçeve penceresinin denetim çubukları için nesne.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Parametreler  
 *durumu*  
 Depolanmış durumu çerçeve penceresinin denetim çubukları için geçerlidir.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubukları önceki durumunu geri yüklemek için depolanan durumuyla yükleyebilir `CDockState::LoadState` veya `Serialize`, ardından `SetDockState` çerçeve penceresinin denetim çubukları için uygulanacak. Önceki bir duruma depolanan `CDockState` nesnesi ile `GetDockState`  
  
##  <a name="setmenubarstate"></a>  CFrameWnd::SetMenuBarState  
 Gizli veya gösterilen geçerli MFC uygulamasındaki menüsünde görünen durumunu ayarlar.  
  
```  
virtual BOOL SetMenuBarState(DWORD nState);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] *nDurum*|Görüntüleme veya gizleme menüyü belirtir. *NDurum* parametresi, aşağıdaki değerleri içerebilir:<br /><br /> -AFX_MBS_VISIBLE (0x01) - gizlenir ancak görünür durumdaysa etkisizdir durumunda menü görüntüler.<br />-AFX_MBS_HIDDEN (0x02) - menüsünün görünür ancak gizli ise, hiçbir etkisi olmaz gizler.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarıyla menü değişerek TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir çalışma zamanı hatası meydana gelirse, hata ayıklama modunda onaylar ve türetilen özel durum harekete [CException](../../mfc/reference/cexception-class.md) sınıfı.  
  
##  <a name="setmenubarvisibility"></a>  CFrameWnd::SetMenuBarVisibility  
 Gizli veya görünür olması için geçerli MFC uygulamasında menü'nın varsayılan davranışını ayarlar.  
  
```  
virtual void SetMenuBarVisibility(DWORD nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] *nStyle*|Menü gizli, varsayılan olarak görünür ve odağa sahip olup olmadığını belirtir. *NStyle* parametresi, aşağıdaki değerleri içerebilir:<br /><br /> -AFX_MBV_KEEPVISIBLE (0X01)-<br />     Menü, her zaman görüntülenir ve varsayılan olarak, odak noktası yok.<br />-AFX_MBV_DISPLAYONFOCUS (0X02)-<br />     Menü, varsayılan olarak gizlidir. Menü gizli ise, menüsünü görüntüleyin ve odaklanmak için ALT tuşuna basın. Menü gösterilirse, menüyü Gizle için ALT ya da ESC tuşuna basın.<br />-AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04)<br />     (karşılaştırmaya (veya)) - menüsünde varsayılan olarak gizlidir. Menü gizli ise, menüsünü görüntüleyin ve odaklanmak için F10 tuşuna basın. Menü gösterilirse, veya menüyü Kapat odağı değiştirilecek F10 tuşuna basın. Kadar gizlemek için ALT ya da ESC tuşuna basın menüsü görüntülenir.|  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa değerini *nStyle* parametresi geçerli değil, bu yöntem başlatır ve hata ayıklama modu ile onaylar [Cınvalidargexception](../../mfc/reference/cinvalidargexception-class.md) yayın modunda. Diğer çalışma zamanı hataları durumunda, bu yöntemi hata ayıklama modunda onaylar ve türetilen özel durum harekete [CException](../../mfc/reference/cexception-class.md) sınıfı.  
  
 Bu yöntem, Windows Vista ve üzeri için yazılmış uygulamalar menülerde durumunu etkiler.  
  
##  <a name="setmessagetext"></a>  CFrameWnd::SetMessageText  
 0 Kimliğine sahip durum çubuğu bölmesinde bir dizeyi yerleştirmek için bu işlevi çağırın.  
  
```  
void SetMessageText(LPCTSTR lpszText);  
void SetMessageText(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszText*  
 Durum çubuğunda yerleştirilecek dizesine işaret eder.  
  
 *nID*  
 Durum çubuğunda yerleştirilecek dize kaynak kimliği dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu genellikle en soldaki ve uzun, durum çubuğu bölmesidir.  
  
##  <a name="setprogressbarposition"></a>  CFrameWnd::SetProgressBarPosition  
 Görev çubuğunda görüntülenen Windows 7 ilerleme çubuğu geçerli konumunu ayarlar.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Parametreler  
 *nProgressPos*  
 Ayarlanacak konumunu belirtir. Belirlenen aralıkta olmalıdır `SetProgressBarRange`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setprogressbarrange"></a>  CFrameWnd::SetProgressBarRange  
 Görev çubuğunda görüntülenen Windows 7 ilerleme çubuğu aralığı ayarlar.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>Parametreler  
 *nRangeMin*  
 Minimum değer.  
  
 *nRangeMax*  
 Düzeyde değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setprogressbarstate"></a>  CFrameWnd::SetProgressBarState  
 Görev çubuğunda görüntülenen İlerleme göstergesi durumunu ve türünü ayarlar.  
  
```  
void SetProgressBarState(TBPFLAG tbpFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 *tbpFlags*  
 İlerleme düğmesi geçerli durumunu denetleyen bayraklar. Tüm durumları birbirini dışlayan olduğundan bayraklar yalnızca aşağıdakilerden birini belirtin: TBPF_NOPROGRESS TBPF_INDETERMINATE, TBPF_NORMAL TBPF_ERROR, TBPF_PAUSED.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settaskbaroverlayicon"></a>  CFrameWnd::SetTaskbarOverlayIcon  
 Fazla Yüklendi. Bir katmana görev çubuğu düğmesi için uygulama durumunu göstermek için veya kullanıcıya bildirmek için geçerlidir.  
  
```  
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,  
    LPCTSTR lpcszDescr);

 
BOOL SetTaskbarOverlayIcon(
    HICON hIcon,  
    LPCTSTR lpcszDescr);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDResource*  
 Bir kaplama olarak kullanmak için kaynak kimliği, bir simge belirtir. Açıklama için bkz: *hIcon* Ayrıntılar için.  
  
 *lpcszDescr*  
 Bir alternatif metin sürümünü erişilebilmesi için katmana ifade bilgileri sağlayan bir dize işaretçisi.  
  
 *hIcon*  
 Bir kaplama olarak kullanılacak bir simge tanıtıcı. Bu, 16 x 16 piksel 96 nokta / inç (dpi), ölçme, küçük bir simge olması gerekir. Bir katmana simge görev çubuğu düğme uygulanırsa, bu varolan bir katmana değiştirilir. Bu değer NULL olabilir. Bir NULL değer nasıl ele alındığını görev çubuğu düğmesini tek bir pencere veya Windows'un bir grubu temsil bağlıdır. Ücretsiz arama uygulamanın sorumluluğundadır *hIcon* ne zaman, artık gerekli.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa TRUE; İşletim sistemi sürümü Windows 7'den küçükse veya simgeyi ayarlamak bir hata oluşursa FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settitle"></a>  CFrameWnd::SetTitle  
 Pencere nesnesi başlığını ayarlar.  
  
```  
void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszTitle*  
 Pencere nesnesi başlığını içeren bir karakter dizesine bir işaretçi.  
  
##  <a name="showcontrolbar"></a>  CFrameWnd::ShowControlBar  
 Denetim çubuğunu gizlemek veya göstermek için bu üye işlevini çağırın.  
  
```  
void ShowControlBar(
    CControlBar* pBar,  
    BOOL bShow,  
    BOOL bDelay);
```  
  
### <a name="parameters"></a>Parametreler  
 *pBar*  
 Denetim çubuğu, gösterilen veya gizli için işaretçi.  
  
 *bBilgi Göster*  
 TRUE ise gösterilecek denetim çubuğu olduğunu belirtir. FALSE ise, denetim çubuğu gizli olduğunu belirtir.  
  
 *bDelay*  
 TRUE ise denetim çubuğunu gösteren gecikme. FALSE ise, hemen çubuğu denetimini gösterir.  
  
##  <a name="showownedwindows"></a>  CFrameWnd::ShowOwnedWindows  
 Alt öğeleri olan tüm windows göstermek için bu üye işlevi çağrısı `CFrameWnd` nesne.  
  
```  
void ShowOwnedWindows(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 *bBilgi Göster*  
 Şirkete ait windows gösterilen veya gizli olup olmadığını belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd sınıfı](../../mfc/reference/cmdiframewnd-class.md)   
 [Cmdıchildwnd sınıfı](../../mfc/reference/cmdichildwnd-class.md)   
 [CView sınıfı](../../mfc/reference/cview-class.md)   
 [CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)   
 [CRuntimeClass Yapısı](../../mfc/reference/cruntimeclass-structure.md)
