---
title: CMDIFrameWnd Sınıfı
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
ms.openlocfilehash: a6e68f6368a7b45e0a566a7d2d12f23a9cd62b12
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370055"
---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd Sınıfı

Pencereyi yönetmek için üyelerle birlikte Bir Windows birden çok belge arabirimi (MDI) çerçeve penceresiişlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMDIFrameWnd : public CFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMDIFrameWnd::CMDIFrameWnd](#cmdiframewnd)|Bir `CMDIFrameWnd`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMDIFrameWnd::CreateClient](#createclient)|Bunun `CMDIFrameWnd`için bir Windows MDICLIENT penceresi oluşturur. `OnCreate` Üye işlevi tarafından `CWnd`çağrılır.|
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|Yeni bir alt pencere oluşturur.|
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|Pencere açılır menüsünü döndürür.|
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|Farklı bir MDI alt penceresi etkinleştirir.|
|[CMDIFrameWnd::MDICascade](#mdicascade)|Tüm alt pencereleri basamaklı bir biçimde düzenler.|
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|Şu anda etkin olan MDI alt penceresini ve çocuğun en üst düzeye çıkarılıp çıkarılmadığını belirten bir bayrak la birlikte alır.|
|[CMDIFrameWnd::MDIIconDüzenleme](#mdiiconarrange)|Simge durumuna küçültülmüş tüm belge alt pencerelerini düzenler.|
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|MDI alt pencereyi en üst düzeye çıkarır.|
|[CMDIFrameWnd::MDINext](#mdinext)|Şu anda etkin olan alt pencerenin hemen arkasındaki alt pencereyi etkinleştirir ve şu anda etkin olan alt pencereyi diğer tüm alt pencerelerinin arkasına yerleştirir.|
|[CMDIFrameWnd::MDIPrev](#mdiprev)|Önceki alt pencereyi etkinleştirir ve şu anda etkin olan alt pencereyi hemen arkasına yerleştirir.|
|[CMDIFrameWnd::MDIRestore](#mdirestore)|MDI alt pencereyi en üst düzeye veya en aza indirilmiş boyuttan geri yükler.|
|[CMDIFrameWnd::MDISetMenü](#mdisetmenu)|MDI çerçeve penceresinin menüsünü, Pencere açılır menüsünü veya her ikisini birden değiştirir.|
|[CMDIFrameWnd::MDITile](#mditile)|Tüm alt pencereleri karo biçiminde düzenler.|

## <a name="remarks"></a>Açıklamalar

Uygulamanız için kullanışlı bir MDI çerçeve penceresi oluşturmak `CMDIFrameWnd`için bir sınıf türetin. Uygulamanıza özgü verileri depolamak için türemiş sınıfa üye değişkenler ekleyin. İletiler pencereye yönlendirildiğinde ne olacağını belirtmek için ileti işleyicisi üye işlevlerini ve türetilmiş sınıfta bir ileti eşlemi uygulayın.

'nin Create veya [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) üye işlevini arayarak bir MDI çerçeve penceresi oluşturabilirsiniz. [Create](../../mfc/reference/cframewnd-class.md#create) `CFrameWnd`

Çağırmadan `Create` önce `LoadFrame`veya , C++ **yeni** işleci kullanarak yığın üzerinde çerçeve penceresi nesnesi oluşturmanız gerekir. Aramadan `Create` önce, çerçeveiçin simge yi ve sınıf stillerini ayarlamak için [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) global işlevine sahip bir pencere sınıfı da kaydedebilirsiniz.

Çerçevenin `Create` oluşturma parametrelerini hemen bağımsız değişken olarak geçirmek için üye işlevi kullanın.

`LoadFrame`daha `Create`az bağımsız değişken gerektirir ve bunun yerine çerçevenin resim yazısı, simge, hızlandırıcı tablosu ve menü dahil olmak üzere kaynaklardan varsayılan değerlerinin çoğunu alır. Erişilebilmek için `LoadFrame`tüm bu kaynakların aynı kaynak kimliğine sahip olması gerekir (örneğin, IDR_MAINFRAME).

`MDIFrameWnd` Türetilmiş `CFrameWnd`olsa da, gerekten `CMDIFrameWnd` türetilen bir `DECLARE_DYNCREATE`çerçeve penceresi sınıfı ile bildirilmeyecek.

Sınıf, `CMDIFrameWnd` varsayılan uygulamasının `CFrameWnd`çoğunu . Bu özelliklerin ayrıntılı bir listesi için [CFrameWnd](../../mfc/reference/cframewnd-class.md) sınıf açıklamasına bakın. Sınıfın `CMDIFrameWnd` aşağıdaki ek özellikleri vardır:

- MDI çerçeve penceresi, MDICLIENT penceresini yönetir ve denetim çubuklarıyla birlikte yeniden konumlandırılır. MDI istemci penceresi, MDI alt çerçeve pencerelerinin doğrudan üst öğesidir. Kullanıcının MDI istemci alanını `CMDIFrameWnd` kaydırabilmesi için ana çerçeve penceresi yerine MDI istemci penceresine uygulanan WS_HSCROLL ve WS_VSCROLL pencere stilleri (örneğin Windows Program Yöneticisi'nde olduğu gibi).

- MDI çerçeve penceresi, etkin MDI alt penceresi olmadığında menü çubuğu olarak kullanılan varsayılan bir menüye sahip olur. Etkin bir MDI alt öğesi olduğunda, MDI çerçeve penceresinin menü çubuğu otomatik olarak MDI alt pencere menüsüyle değiştirilir.

- Varsa, Bir MDI çerçeve penceresi geçerli MDI alt penceresi ile birlikte çalışır. Örneğin, komut iletileri MDI çerçeve penceresinden önce şu anda etkin olan MDI alt çocuğuna devredilir.

- MDI çerçeve penceresi, aşağıdaki standart Pencere menüsü komutları için varsayılan işleyicileri vardır:

  - ID_WINDOW_TILE_VERT

  - ID_WINDOW_TILE_HORZ

  - ID_WINDOW_CASCADE

  - ID_WINDOW_ARRANGE

- MDI çerçeve penceresi, geçerli belgede yeni bir çerçeve ve görünüm oluşturan ID_WINDOW_NEW uygulamasına da sahiptir. Bir uygulama, MDI pencere işleme özelleştirmek için bu varsayılan komut uygulamalarını geçersiz kılabilir.

Çerçeve penceresini yok etmek için C++ **silme** işleci kullanmayın. Bunun yerine `CWnd::DestroyWindow` kullanın. Pencere `CFrameWnd` yok `PostNcDestroy` edildiğinde C++ nesnesi siler. Kullanıcı çerçeve penceresini kapattığında, `OnClose` varsayılan işleyici `DestroyWindow`.

Daha fazla `CMDIFrameWnd`bilgi için [Bkz. Çerçeve Windows.](../../mfc/frame-windows.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cmdiframewndcmdiframewnd"></a><a name="cmdiframewnd"></a>CMDIFrameWnd::CMDIFrameWnd

Bir `CMDIFrameWnd` nesne inşa eder.

```
CMDIFrameWnd();
```

### <a name="remarks"></a>Açıklamalar

Görünür `Create` MDI çerçeve penceresi oluşturmak için veya `LoadFrame` üye işlevini arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

## <a name="cmdiframewndcreateclient"></a><a name="createclient"></a>CMDIFrameWnd::CreateClient

`CMDIChildWnd` Nesneleri yöneten MDI istemci penceresi oluşturur.

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Parametreler

*lpCreateStruct*<br/>
[CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) yapısıiçin uzun bir işaretçi.

*pWindowMenu*<br/>
Pencere açılır menüsüne bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`OnCreate` Üye işlevi doğrudan geçersiz kılarsanız, bu üye işlev çağrılmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

## <a name="cmdiframewndcreatenewchild"></a><a name="createnewchild"></a>CMDIFrameWnd::CreateNewChild

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
Alt pencereyle ilişkili paylaşılan kaynakların kimliği.

*Hmenu*<br/>
Alt pencerenin menüsü.

*hAccel*<br/>
Çocuk penceresinin hızlandırıcısı.

### <a name="remarks"></a>Açıklamalar

MDI çerçeve penceresinin alt pencerelerini oluşturmak için bu işlevi kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

## <a name="cmdiframewndgetwindowmenupopup"></a><a name="getwindowmenupopup"></a>CMDIFrameWnd::GetWindowMenuPopup

"Pencere" (MDI pencere yönetimi için menü öğeleri içeren açılır menü) adlı geçerli açılır menü için bir tanıtıcı elde etmek için bu üye işlevi arayın.

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>Parametreler

*hMenuBar*<br/>
Geçerli menü çubuğu.

### <a name="return-value"></a>Dönüş Değeri

Varsa Pencere açılır menüsü; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, ID_WINDOW_NEW ve ID_WINDOW_TILE_HORZ gibi standart Pencere menüsü komutlarını içeren bir açılır menü arar.

Standart menü komut iI'lerini kullanmayan bir Pencere menüsü varsa bu üye işlevi geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

## <a name="cmdiframewndmdiactivate"></a><a name="mdiactivate"></a>CMDIFrameWnd::MDIActivate

Farklı bir MDI alt penceresi etkinleştirir.

```
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>Parametreler

*pWndEtkinleştir*<br/>
Etkinleştirilecek MDI alt penceresine işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, hem etkinleştirilmekte olan alt pencereye hem de alt pencerenin devre dışı bırakılmasına [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) ileti gönderir.

Bu, kullanıcı fareyi veya klavyeyi kullanarak odağı Bir MDI alt penceresine değiştirirse gönderilen iletinin aynıdır.

> [!NOTE]
> MDI alt penceresi, MDI çerçeve penceresinden bağımsız olarak etkinleştirilir. Çerçeve etkin hale geldiğinde, en son etkinleştirilen alt pencere, etkin bir pencere çerçevesi ve resim yazısı çubuğu çizmek için [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) iletisi gönderilir, ancak başka bir WM_MDIACTIVATE iletisi almaz.

### <a name="example"></a>Örnek

CMDIFrameWnd için örneğe [bakın:GetWindowMenuPopup](#getwindowmenupopup).

## <a name="cmdiframewndmdicascade"></a><a name="mdicascade"></a>CMDIFrameWnd::MDICascade

Tüm MDI alt pencerelerini basamaklı bir biçimde düzenler.

```
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>Parametreler

*nTipi*<br/>
Basamaklı bir bayrak belirtir. Yalnızca aşağıdaki bayrak belirtilebilir: MDITILE_SKIPDISABLED, devre dışı bırakılan MDI alt pencerelerinin basamaklanmasını önler.

### <a name="remarks"></a>Açıklamalar

Hiçbir parametre `MDICascade`olmadan, ilk sürümü, devre dışı olanlar da dahil olmak üzere tüm MDI alt pencereleri basamaklı. *nType* parametresi için MDITILE_SKIPDISABLED belirtirseniz, ikinci sürüm isteğe bağlı olarak devre dışı bırakılmış MDI alt pencerelerini basamaklamaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

## <a name="cmdiframewndmdigetactive"></a><a name="mdigetactive"></a>CMDIFrameWnd::MDIGetActive

Geçerli etkin MDI alt penceresini ve alt pencerenin en üst düzeye çıkarılıp çıkarılmadığını belirten bir bayrak alır.

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>Parametreler

*pbMaximized*<br/>
BOOL iade değeri için bir işaretçi. Pencere en üst düzeye çıkarsa dönüşte TRUE olarak ayarlayın; aksi takdirde YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Etkin MDI alt penceresiiçin bir işaretçi.

### <a name="example"></a>Örnek

[CMDIChildWnd örneğine bakın::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

## <a name="cmdiframewndmdiiconarrange"></a><a name="mdiiconarrange"></a>CMDIFrameWnd::MDIIconDüzenleme

Simge durumuna küçültülmüş tüm belge alt pencerelerini düzenler.

```
void MDIIconArrange();
```

### <a name="remarks"></a>Açıklamalar

En aza indirgenmeyen alt pencereleri etkilemez.

### <a name="example"></a>Örnek

CMDIFrameWnd için örneğe [bakın::MDICascade](#mdicascade).

## <a name="cmdiframewndmdimaximize"></a><a name="mdimaximize"></a>CMDIFrameWnd::MDIMaximize

Belirtilen MDI alt penceresini en üst düzeye çıkarır.

```
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
En üst düzeye çıkarmak için pencereye işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Alt pencere en üst düzeye çıktığında, Windows istemci alanı istemci penceresini doldurmak yapmak için yeniden boyutlandırılır. Windows, kullanıcının alt pencereyi geri yükleyebilmeleri veya kapatabilmesi için alt pencerenin Denetim menüsünü çerçevenin menü çubuğuna yerleştirir. Ayrıca, çerçeve penceresi başlığına alt pencerenin başlığını da ekler.

Şu anda etkin olan MDI alt penceresi en üst düzeye çıktığında başka bir MDI alt penceresi etkinleştirilirse, Windows şu anda etkin olan alt pencereyi geri yükler ve yeni etkinleştirilen alt pencereyi en üst düzeye çıkarır.

### <a name="example"></a>Örnek

[CMDIChildWnd örneğine bakın::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

## <a name="cmdiframewndmdinext"></a><a name="mdinext"></a>CMDIFrameWnd::MDINext

Şu anda etkin olan alt pencerenin hemen arkasındaki alt pencereyi etkinleştirir ve şu anda etkin olan alt pencereyi diğer tüm alt pencerelerinin arkasına yerleştirir.

```
void MDINext();
```

### <a name="remarks"></a>Açıklamalar

Şu anda etkin olan MDI alt penceresi en üst düzeye çıkarsa, üye işlev şu anda etkin olan alt çocuğu geri yükler ve yeni etkinleştirilen alt alanı en üst düzeye çıkarır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

## <a name="cmdiframewndmdiprev"></a><a name="mdiprev"></a>CMDIFrameWnd::MDIPrev

Önceki alt pencereyi etkinleştirir ve şu anda etkin olan alt pencereyi hemen arkasına yerleştirir.

```
void MDIPrev();
```

### <a name="remarks"></a>Açıklamalar

Şu anda etkin olan MDI alt penceresi en üst düzeye çıkarsa, üye işlev şu anda etkin olan alt çocuğu geri yükler ve yeni etkinleştirilen alt alanı en üst düzeye çıkarır.

## <a name="cmdiframewndmdirestore"></a><a name="mdirestore"></a>CMDIFrameWnd::MDIRestore

MDI alt pencereyi en üst düzeye veya en aza indirilmiş boyuttan geri yükler.

```
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Geri yükleme penceresine işaret ediyor.

### <a name="example"></a>Örnek

CMDIChildWnd için örneğe [bakın::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore).

## <a name="cmdiframewndmdisetmenu"></a><a name="mdisetmenu"></a>CMDIFrameWnd::MDISetMenü

MDI çerçeve penceresinin menüsünü, Pencere açılır menüsünü veya her ikisini birden değiştirir.

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Parametreler

*pFrameMenu*<br/>
Yeni çerçeve penceresi menüsünün menüsünü belirtir. NULL ise, menü değiştirilmez.

*pWindowMenu*<br/>
Yeni Pencere açılır menüsünün menüsünü belirtir. NULL ise, menü değiştirilmez.

### <a name="return-value"></a>Dönüş Değeri

Çerçeve penceresi menüsünün işaretçisi bu iletiyle değiştirilir. İşaretçi geçici olabilir ve daha sonra kullanılmak üzere depolanmamalıdır.

### <a name="remarks"></a>Açıklamalar

Aradıktan `MDISetMenu`sonra, bir uygulama menü çubuğunu `CWnd` güncelleştirmek için [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) üye işlevini aramalıdır.

Bu arama Pencere açılır menüsünün yerini alırsa, MDI alt pencere menüsü öğeleri önceki Pencere menüsünden kaldırılır ve yeni Pencere açılır menüsüne eklenir.

Bir MDI alt penceresi en üst düzeye çıkarılırsa ve bu çağrı MDI çerçeve penceresi menüsünün yerini alırsa, Denetim menüsü ve geri yükleme denetimleri önceki çerçeve penceresi menüsünden kaldırılır ve yeni menüye eklenir.

MDI alt pencerelerinizi yönetmek için çerçeveyi kullanıyorsanız bu üye işlevini aramayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

## <a name="cmdiframewndmditile"></a><a name="mditile"></a>CMDIFrameWnd::MDITile

Tüm alt pencereleri karo biçiminde düzenler.

```
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>Parametreler

*nTipi*<br/>
Döşeme bayrağını belirtir. Bu parametre aşağıdaki bayraklardan biri olabilir:

- MDITILE_HORIZONTAL, bir pencerenin diğerinin üzerinde görünmesi için MDI alt pencerelerini kutular.

- MDITILE_SKIPDISABLED Devre dışı bırakılan MDI alt pencerelerinin döşenmesini önler.

- MDITILE_VERTICAL Kutucuklar MDI alt pencereleri böylece bir pencere diğerinin yanında görünür.

### <a name="remarks"></a>Açıklamalar

Parametreler olmadan, `MDITile`windows sürümleri 3.1 ve sonraki altında dikey olarak kutucuklar ilk sürümü. İkinci sürüm, *nType* parametresinin değerine bağlı olarak pencereleri dikey veya yatay olarak kutular.

### <a name="example"></a>Örnek

CMDIFrameWnd için örneğe [bakın::MDICascade](#mdicascade).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CMDIChildWnd Sınıfı](../../mfc/reference/cmdichildwnd-class.md)
