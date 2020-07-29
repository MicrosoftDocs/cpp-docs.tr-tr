---
title: CMDIFrameWnd sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMDIFrameWnd
- AFXWIN/CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CreateClient
- AFXWIN/CMDIFrameWnd::CreateNewChild
- AFXWIN/CMDIFrameWnd::GetWindowMenuPopup
- AFXWIN/CMDIFrameWnd::MDIActivate
- AFXWIN/CMDIFrameWnd::MDICascade
- AFXWIN/CMDIFrameWnd::MDIGetActive
- AFXWIN/CMDIFrameWnd::MDIIconArrange
- AFXWIN/CMDIFrameWnd::MDIMaximize
- AFXWIN/CMDIFrameWnd::MDINext
- AFXWIN/CMDIFrameWnd::MDIPrev
- AFXWIN/CMDIFrameWnd::MDIRestore
- AFXWIN/CMDIFrameWnd::MDISetMenu
- AFXWIN/CMDIFrameWnd::MDITile
helpviewer_keywords:
- CMDIFrameWnd [MFC], CMDIFrameWnd
- CMDIFrameWnd [MFC], CreateClient
- CMDIFrameWnd [MFC], CreateNewChild
- CMDIFrameWnd [MFC], GetWindowMenuPopup
- CMDIFrameWnd [MFC], MDIActivate
- CMDIFrameWnd [MFC], MDICascade
- CMDIFrameWnd [MFC], MDIGetActive
- CMDIFrameWnd [MFC], MDIIconArrange
- CMDIFrameWnd [MFC], MDIMaximize
- CMDIFrameWnd [MFC], MDINext
- CMDIFrameWnd [MFC], MDIPrev
- CMDIFrameWnd [MFC], MDIRestore
- CMDIFrameWnd [MFC], MDISetMenu
- CMDIFrameWnd [MFC], MDITile
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
ms.openlocfilehash: 321ad0364257d7c20d54f9fdc884073381117c6f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222959"
---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd sınıfı

Windows çoklu belge arabirimi (MDI) çerçeve penceresi işlevlerini, pencereyi yönetmek için üyelerle birlikte sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMDIFrameWnd : public CFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMDIFrameWnd:: CMDIFrameWnd](#cmdiframewnd)|Bir oluşturur `CMDIFrameWnd` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMDIFrameWnd:: CreateClient](#createclient)|Bunun için bir Windows MDıCLıENT penceresi oluşturur `CMDIFrameWnd` . `OnCreate`Öğesinin üye işlevi tarafından çağırılır `CWnd` .|
|[CMDIFrameWnd:: CreateNewChild](#createnewchild)|Yeni bir alt pencere oluşturur.|
|[CMDIFrameWnd:: GetWindowMenuPopup](#getwindowmenupopup)|Pencere açılır menüsünü döndürür.|
|[CMDIFrameWnd:: Mdıactivate](#mdiactivate)|Farklı bir MDI alt penceresini etkinleştirir.|
|[CMDIFrameWnd:: MDICascade](#mdicascade)|Tüm alt pencereleri basamaklı bir biçimde düzenler.|
|[CMDIFrameWnd:: MDIGetActive](#mdigetactive)|Şu anda etkin olan MDI alt penceresini, alt öğenin ekranı kapladığını belirten bir bayrağıyla birlikte alır.|
|[CMDIFrameWnd:: MDIIconArrange](#mdiiconarrange)|Tüm küçültülmüş belge alt pencerelerini düzenler.|
|[CMDIFrameWnd:: Mdıkapla](#mdimaximize)|MDI alt penceresini en üst düzeye çıkarır.|
|[CMDIFrameWnd:: Mdınext](#mdinext)|Şu anda etkin olan alt pencerenin arkasındaki alt pencereyi etkinleştirir ve o anda etkin olan alt pencereyi diğer tüm alt pencerelerin arkasına koyar.|
|[CMDIFrameWnd:: Mdıöncekini](#mdiprev)|Önceki alt pencereyi etkinleştirir ve o anda etkin olan alt pencereyi hemen arkasına koyar.|
|[CMDIFrameWnd:: MDIRestore](#mdirestore)|Bir MDI alt penceresini ekranı kaplamış veya küçültülmüş boyuttan geri yükler.|
|[CMDIFrameWnd:: MDISetMenu](#mdisetmenu)|Bir MDI çerçevesi penceresi, pencere açılır menüsü veya her ikisi için de bir menü koyar.|
|[CMDIFrameWnd:: MDITile](#mditile)|Tüm alt pencereleri döşeli bir biçimde düzenler.|

## <a name="remarks"></a>Açıklamalar

Uygulamanız için yararlı bir MDI çerçevesi penceresi oluşturmak için, öğesinden bir sınıf türetebilirsiniz `CMDIFrameWnd` . Uygulamanıza özgü verileri depolamak için türetilmiş sınıfa üye değişkenleri ekleyin. İletileri pencereye yönlendirdiğinde ne olacağını belirtmek için ileti işleyicisi üye işlevlerini ve türetilmiş sınıfta bir ileti eşlemesi uygulayın.

[Create](../../mfc/reference/cframewnd-class.md#create) veya [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) üye işlevini çağırarak bir MDI çerçevesi penceresi oluşturabilirsiniz `CFrameWnd` .

Veya çağrısından önce `Create` `LoadFrame` , C++ işlecini kullanarak yığın üzerinde çerçeve pencere nesnesi oluşturmanız gerekir **`new`** . ' İ çağırmadan önce, `Create` çerçeveye ait simge ve sınıf stillerini ayarlamak Için [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) genel işleviyle bir pencere sınıfı da kaydedebilirsiniz.

`Create`Çerçevenin oluşturma parametrelerini hemen bağımsız değişken olarak geçirmek için üye işlevini kullanın.

`LoadFrame`öğesinden daha az bağımsız değişken gerektirir `Create` ve bunun yerine çerçevenin başlık, simge, Hızlandırıcı tablosu ve menü dahil olmak üzere kaynaklardaki varsayılan değerlerinin çoğunu alır. Tarafından erişilebilmesi için `LoadFrame` , tüm bu kaynakların aynı kaynak kimliğine sahip olması gerekir (örneğin, IDR_MAINFRAME).

`MDIFrameWnd`, Öğesinden türetilse `CFrameWnd` , öğesinden türetilmiş bir çerçeve penceresi sınıfının `CMDIFrameWnd` ile bildirilmesine gerek yoktur `DECLARE_DYNCREATE` .

`CMDIFrameWnd`Sınıfı, varsayılan uygulamasının çoğunu öğesinden devralır `CFrameWnd` . Bu özelliklerin ayrıntılı bir listesi için [CFrameWnd](../../mfc/reference/cframewnd-class.md) sınıfı açıklamasına bakın. `CMDIFrameWnd`Sınıfı aşağıdaki ek özelliklere sahiptir:

- Bir MDI çerçevesi penceresi MDıCLıENT penceresini yönetir ve denetim çubuklarıyla birlikte yeniden konumlandırın. MDI istemci penceresi MDI alt çerçeve pencerelerinin doğrudan üst öğesidir. `CMDIFrameWnd`Kullanıcının MDI istemci alanını (örneğin, Windows Program Yöneticisi 'nde olduğu gibi) kaydırabilmesi için ana çerçeve penceresi yerıne MDI istemci penceresinde belirtilen WS_HSCROLL ve ws_vscroll pencere stilleri.

- Bir MDI çerçevesi penceresi, etkin bir MDI alt penceresi olmadığında menü çubuğu olarak kullanılan varsayılan bir menünün sahibidir. Etkin bir MDI alt öğesi olduğunda, MDI çerçevesi penceresinin menü çubuğu otomatik olarak MDI alt pencere menüsüyle değiştirilmiştir.

- Bir MDI çerçevesi penceresi, varsa geçerli MDI alt penceresiyle birlikte çalışıyor. Örnek olarak, komut iletileri MDI çerçevesi penceresinden önce Şu anda etkin olan MDI alt öğesine atanır.

- Aşağıdaki standart pencere menü komutları için bir MDI çerçeve penceresinin varsayılan işleyicileri vardır:

  - ID_WINDOW_TILE_VERT

  - ID_WINDOW_TILE_HORZ

  - ID_WINDOW_CASCADE

  - ID_WINDOW_ARRANGE

- Bir MDI çerçevesi penceresi ayrıca geçerli belgede yeni bir çerçeve ve görünüm oluşturan ID_WINDOW_NEW bir uygulamasına sahiptir. Bir uygulama, MDI pencere işlemesini özelleştirmek için bu varsayılan komut uygulamalarını geçersiz kılabilir.

**`delete`** Bir çerçeve penceresini yok etmek Için C++ işlecini kullanmayın. Bunun yerine `CWnd::DestroyWindow` kullanın. Uygulamasının `CFrameWnd` uygulanması, `PostNcDestroy` pencere yok edildiğinde C++ nesnesini silecektir. Kullanıcı çerçeve penceresini kapattığında, varsayılan `OnClose` işleyici çağırır `DestroyWindow` .

Hakkında daha fazla bilgi için `CMDIFrameWnd` bkz. [çerçeve pencereleri](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cmdiframewndcmdiframewnd"></a><a name="cmdiframewnd"></a>CMDIFrameWnd:: CMDIFrameWnd

Bir `CMDIFrameWnd` nesnesi oluşturur.

```
CMDIFrameWnd();
```

### <a name="remarks"></a>Açıklamalar

`Create` `LoadFrame` Görünür MDI çerçevesi penceresini oluşturmak için veya üye işlevini çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

## <a name="cmdiframewndcreateclient"></a><a name="createclient"></a>CMDIFrameWnd:: CreateClient

Nesneleri yöneten MDI istemci penceresini oluşturur `CMDIChildWnd` .

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Parametreler

*lpCreateStruct*<br/>
[CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) yapısına yönelik uzun bir işaretçi.

*pWindowMenu*<br/>
Pencere açılır menüsüne yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Üye işlevini doğrudan geçersiz kılarsınız, bu üye işlev çağrılmalıdır `OnCreate` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

## <a name="cmdiframewndcreatenewchild"></a><a name="createnewchild"></a>CMDIFrameWnd:: CreateNewChild

Yeni bir alt pencere oluşturur.

```
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,
    UINT nResource,
    HMENU hMenu = NULL,
    HACCEL hAccel = NULL);
```

### <a name="parameters"></a>Parametreler

*pClass*<br/>
Oluşturulacak alt pencerenin çalışma zamanı sınıfı.

*nKaynak*<br/>
Alt pencereyle ilişkili paylaşılan kaynakların KIMLIĞI.

*hMenu*<br/>
Alt pencere menüsü.

*hAccel*<br/>
Alt pencerenin Hızlandırıcısı.

### <a name="remarks"></a>Açıklamalar

MDI çerçeve penceresinin alt pencerelerini oluşturmak için bu işlevi kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

## <a name="cmdiframewndgetwindowmenupopup"></a><a name="getwindowmenupopup"></a>CMDIFrameWnd:: GetWindowMenuPopup

"Pencere" adlı geçerli açılır menüye (MDI pencere yönetimi için menü öğeleri içeren açılır menü) bir tanıtıcı almak için bu üye işlevi çağırın.

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>Parametreler

*hMenuBar*<br/>
Geçerli menü çubuğu.

### <a name="return-value"></a>Dönüş Değeri

Varsa pencere açılır menüsü; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, ID_WINDOW_NEW ve ID_WINDOW_TILE_HORZ gibi standart pencere menüsü komutlarını içeren bir açılır menü arar.

Standart Menü komut kimliklerini kullanmayan bir pencere menüsü varsa, bu üye işlevi geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

## <a name="cmdiframewndmdiactivate"></a><a name="mdiactivate"></a>CMDIFrameWnd:: Mdıactivate

Farklı bir MDI alt penceresini etkinleştirir.

```cpp
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>Parametreler

*Pwndacetkinleştir*<br/>
Etkinleştirilecek MDI alt penceresine işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) iletisini hem etkinleştirilen alt pencereye hem de alt pencere devre dışı bırakılmakta olan alt pencereye gönderir.

Bu, Kullanıcı fare veya klavyeyi kullanarak odağı bir MDI alt penceresine değiştirdiğinde gönderilen iletidir.

> [!NOTE]
> MDI alt penceresi MDI çerçevesi penceresinden bağımsız olarak etkinleştirilir. Çerçeve etkin hale geldiğinde, en son etkinleştirilen alt pencere, etkin pencere çerçevesi ve başlık çubuğu çizmek için [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) bir ileti gönderilir, ancak başka bir WM_MDIACTIVATE iletisi almaz.

### <a name="example"></a>Örnek

[Cmdiframewnd:: GetWindowMenuPopup](#getwindowmenupopup)örneğine bakın.

## <a name="cmdiframewndmdicascade"></a><a name="mdicascade"></a>CMDIFrameWnd:: MDICascade

Tüm MDI alt pencerelerini basamaklı biçimde yerleştirir.

```cpp
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>Parametreler

*nTür*<br/>
Cascade bayrağını belirtir. Yalnızca şu bayrak belirtilebilir: devre dışı bırakılan MDI alt pencerelerinin basamaklı olmasını önleyen MDITILE_SKIPDISABLED.

### <a name="remarks"></a>Açıklamalar

' Nin ilk sürümü, `MDICascade` parametresiz, tüm MDI alt pencereleri, yani devre dışı olanlar dahil. İkinci sürüm, *nType* parametresi için MDITILE_SKIPDISABLED belirtirseniz, isteğe bağlı olarak devre dışı MDI alt pencerelerini basamaklandırmaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

## <a name="cmdiframewndmdigetactive"></a><a name="mdigetactive"></a>CMDIFrameWnd:: MDIGetActive

Geçerli etkin MDI alt penceresini, alt pencerenin ekranı kapladığını belirten bir bayrağıyla birlikte alır.

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>Parametreler

*Pbkaplaması*<br/>
BOOL dönüş değerine yönelik bir işaretçi. Pencere ekranı kapladıysanız, return üzerinde TRUE olarak ayarlayın; Aksi halde yanlış.

### <a name="return-value"></a>Dönüş Değeri

Etkin MDI alt penceresine yönelik bir işaretçi.

### <a name="example"></a>Örnek

[Cmdictepdwnd:: Mdıkapla](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)örneğine bakın.

## <a name="cmdiframewndmdiiconarrange"></a><a name="mdiiconarrange"></a>CMDIFrameWnd:: MDIIconArrange

Tüm küçültülmüş belge alt pencerelerini düzenler.

```cpp
void MDIIconArrange();
```

### <a name="remarks"></a>Açıklamalar

Simge durumuna küçültülmüş alt pencereleri etkilemez.

### <a name="example"></a>Örnek

[Cmdiframewnd:: MDICascade](#mdicascade)örneğine bakın.

## <a name="cmdiframewndmdimaximize"></a><a name="mdimaximize"></a>CMDIFrameWnd:: Mdıkapla

Belirtilen MDI alt penceresini en üst düzeye çıkarır.

```cpp
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
En üst düzeye çıkarmak için pencereyi işaret eder.

### <a name="remarks"></a>Açıklamalar

Bir alt pencere ekranı kapladığında Windows, istemci alanının istemci penceresini doldurmasını sağlamak için bunu yeniden boyutlandırır. Windows, alt pencereyi geri yüklemek veya kapatmak için çerçevenin menü çubuğuna alt pencerenin Denetim menüsünü koyar. Ayrıca, alt pencerenin başlığını çerçeve pencere başlığına ekler.

Şu anda etkin olan MDI alt penceresi ekranı kapladıktan sonra başka bir MDI alt penceresi etkinleştirildiyse, Windows etkin olan alt pencereyi geri yükler ve yeni etkinleştirilen alt pencereyi en üst düzeye çıkarır.

### <a name="example"></a>Örnek

[Cmdictepdwnd:: Mdıkapla](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)örneğine bakın.

## <a name="cmdiframewndmdinext"></a><a name="mdinext"></a>CMDIFrameWnd:: Mdınext

Şu anda etkin olan alt pencerenin arkasındaki alt pencereyi etkinleştirir ve o anda etkin olan alt pencereyi diğer tüm alt pencerelerin arkasına koyar.

```cpp
void MDINext();
```

### <a name="remarks"></a>Açıklamalar

Şu anda etkin olan MDI alt penceresi ekranı kapladıysanız üye işlevi şu anda etkin olan alt öğesi geri yükler ve yeni etkinleştirilen alt öğesini en üst düzeye çıkarır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

## <a name="cmdiframewndmdiprev"></a><a name="mdiprev"></a>CMDIFrameWnd:: Mdıöncekini

Önceki alt pencereyi etkinleştirir ve o anda etkin olan alt pencereyi hemen arkasına koyar.

```cpp
void MDIPrev();
```

### <a name="remarks"></a>Açıklamalar

Şu anda etkin olan MDI alt penceresi ekranı kapladıysanız üye işlevi şu anda etkin olan alt öğesi geri yükler ve yeni etkinleştirilen alt öğesini en üst düzeye çıkarır.

## <a name="cmdiframewndmdirestore"></a><a name="mdirestore"></a>CMDIFrameWnd:: MDIRestore

Bir MDI alt penceresini ekranı kaplamış veya küçültülmüş boyuttan geri yükler.

```cpp
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Geri yüklenecek pencereyi işaret eder.

### <a name="example"></a>Örnek

[Cmdictepdwnd:: MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore)örneğine bakın.

## <a name="cmdiframewndmdisetmenu"></a><a name="mdisetmenu"></a>CMDIFrameWnd:: MDISetMenu

Bir MDI çerçevesi penceresi, pencere açılır menüsü veya her ikisi için de bir menü koyar.

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Parametreler

*pFrameMenu*<br/>
Yeni çerçeve pencere menüsünün menüsünü belirtir. NULL ise, menü değiştirilmez.

*pWindowMenu*<br/>
Yeni pencere açılır menüsünün menüsünü belirtir. NULL ise, menü değiştirilmez.

### <a name="return-value"></a>Dönüş Değeri

Bu iletiyle değiştirilmiş olan çerçeve pencere menüsüne yönelik bir işaretçi. İşaretçi geçici olabilir ve daha sonra kullanılmak üzere depolanmamalıdır.

### <a name="remarks"></a>Açıklamalar

Çağrıldıktan sonra `MDISetMenu` bir uygulamanın, menü çubuğunu güncelleştirmek Için [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) üye işlevini çağırması gerekir `CWnd` .

Bu çağrı pencere açılır menüsünün yerini alırsa, MDI alt pencere menü öğeleri önceki pencere menüsünden kaldırılır ve yeni pencere açılır menüsüne eklenir.

Bir MDI alt penceresi ekranı kaplamışsa ve bu çağrı MDI çerçevesi-pencere menüsünün yerini alırsa, Denetim menüsü ve geri yükleme denetimleri önceki kare pencere menüsünden kaldırılır ve yeni menüye eklenir.

MDI alt pencerelerini yönetmek için çerçevesini kullanıyorsanız bu üye işlevini çağırmayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

## <a name="cmdiframewndmditile"></a><a name="mditile"></a>CMDIFrameWnd:: MDITile

Tüm alt pencereleri döşeli bir biçimde düzenler.

```cpp
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>Parametreler

*nTür*<br/>
Döşeme bayrağını belirtir. Bu parametre aşağıdaki bayraklardan herhangi biri olabilir:

- MDITILE_HORIZONTAL kutucuklar MDI alt pencereleri, bir pencerenin diğerinin üzerinde görünmesini sağlamak için.

- MDITILE_SKIPDISABLED, devre dışı MDI alt pencerelerinin döşeli olmasını önler.

- MDITILE_VERTICAL, bir pencerenin diğerinin yanında görünmesi için MDI alt pencereleri ' ni döşer.

### <a name="remarks"></a>Açıklamalar

İlk sürümü `MDITile` , parametresiz, windows 3,1 ve üzeri Windows sürümleri altındaki pencereleri dikey olarak döşer. İkinci sürüm, *nType* parametresinin değerine bağlı olarak Windows 'u dikey veya yatay olarak döşer.

### <a name="example"></a>Örnek

[Cmdiframewnd:: MDICascade](#mdicascade)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek MDıDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Cmdicchild Dwnd sınıfı](../../mfc/reference/cmdichildwnd-class.md)
