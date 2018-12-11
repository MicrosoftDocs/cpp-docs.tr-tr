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
ms.openlocfilehash: 9d9a2d33f61aa9033bb17c090989b4f08ee82bd7
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178388"
---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd sınıfı

Bir Windows işlevlerini birden çok Belgeli Arabirim (MDI) çerçeve penceresi ve pencereyi yönetmek için üyeleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMDIFrameWnd : public CFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMDIFrameWnd::CMDIFrameWnd](#cmdiframewnd)|Oluşturur bir `CMDIFrameWnd`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMDIFrameWnd::CreateClient](#createclient)|Bunun için bir Windows MDICLIENT penceresi oluşturur `CMDIFrameWnd`. Çağıran `OnCreate` üye işlevini `CWnd`.|
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|Yeni bir alt pencere oluşturur.|
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|Pencere açılır menüsünü döndürür.|
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|Farklı bir MDI alt penceresini etkinleştirir.|
|[CMDIFrameWnd::MDICascade](#mdicascade)|Tüm alt pencereleri art arda biçimde düzenler.|
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|Alt öğe ekranı olup olmadığını belirten bir bayrak yanı sıra etkin MDI alt penceresi, alır.|
|[CMDIFrameWnd::MDIIconArrange](#mdiiconarrange)|Tüm simge durumuna küçültülmüş belge alt pencereleri düzenler.|
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|Bir MDI alt penceresinin en üst düzeye çıkarır.|
|[CMDIFrameWnd::MDINext](#mdinext)|Hemen arkasına şu anda etkin alt pencerenin alt penceresini etkinleştirir ve şu anda etkin alt pencerenin diğer tüm alt öğe pencerelerini yerleştirir.|
|[CMDIFrameWnd::MDIPrev](#mdiprev)|Önceki alt penceresini etkinleştirir ve şu anda etkin alt pencerenin hemen arkasına yerleştirir.|
|[CMDIFrameWnd::MDIRestore](#mdirestore)|Bir MDI alt penceresi simge durumuna küçültülmüş ya da tam ekran boyutunu geri yükler.|
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|Bir MDI çerçeve penceresinin menü, penceresi açılır menüyü veya her ikisi de değiştirir.|
|[CMDIFrameWnd::MDITile](#mditile)|Tüm alt pencereleri döşenmiş bir biçimde düzenler.|

## <a name="remarks"></a>Açıklamalar

Uygulamanız için kullanışlı bir MDI çerçeve penceresinin oluşturmak için öğesinden bir sınıf türetin `CMDIFrameWnd`. Uygulamanıza özgü verileri depolamak için türetilmiş sınıf üye değişkenlerini ekleyin. Türetilen bir sınıfta iletileri penceresine yönlendirilirsiniz olduğunda ne olacağını belirlemek için uygulama ileti işleyicisi üye işlevleri ve bir ileti eşleyin.

Bir MDI çerçeve penceresinin çağırarak oluşturabilirsiniz [Oluştur](../../mfc/reference/cframewnd-class.md#create) veya [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) üye işlevini `CFrameWnd`.

Çağırmadan önce `Create` veya `LoadFrame`, C++ kullanarak yığın çerçeve penceresi nesnede oluşturmalıdır **yeni** işleci. Çağırmadan önce `Create` pencere sınıfı ile de kaydedebilirsiniz [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) simgesi ve sınıf stilleri çerçevesi için ayarlanacak genel işlev.

Kullanım `Create` çerçeve oluşturma parametreleri olarak anında bağımsız değişkenleri geçirmek için üye işlevi.

`LoadFrame` daha az sayıda bağımsız değişken gerektirir `Create`ve bunun yerine varsayılan değerlerine çoğunu çerçevenin başlık, simgesi, Hızlandırıcı tablosu ve menü gibi kaynaklardan alır. Tarafından erişilmek üzere `LoadFrame`, tüm bu kaynaklar aynı kaynak kimliği (örneğin, IDR_MAINFRAME) olması gerekir.

Ancak `MDIFrameWnd` türetilir `CFrameWnd`, bir pencere sınıfını türetilen `CMDIFrameWnd` ile bildirilmesine gerek olmadığı `DECLARE_DYNCREATE`.

`CMDIFrameWnd` Sınıfından devralan varsayılan uygulanması çoğunu `CFrameWnd`. Bu özelliklerin ayrıntılı listesi için başvurmak [CFrameWnd](../../mfc/reference/cframewnd-class.md) açıklaması sınıfı. `CMDIFrameWnd` Sınıfı aşağıdaki ek özelliklere sahiptir:

- Bir MDI çerçeve penceresinin denetim çubukları birlikte yeniden konumlandırma MDICLIENT penceresi yönetir. MSI istemci penceresi doğrudan üst MDI alt çerçeve pencereleri ' dir. Belirtilen WS_HSCROLL ve WS_VSCROLL pencere stilleri bir `CMDIFrameWnd` uygulamak için MSI istemci penceresi kullanıcı MDI istemci alanını (olduğu gibi Windows Program Yöneticisi, örneğin) kaydırma yapabilir, böylece ana çerçeve penceresinin yerine.

- Bir MDI çerçeve penceresinin hiçbir etkin MDI alt penceresine olduğunda menü çubuğu olarak kullanılan bir varsayılan menü sahip. Etkin MDI alt olduğunda MDI çerçeve penceresinin menü çubuğunu MDI alt penceresi menüsü tarafından otomatik olarak değiştirilir.

- Varsa bir MDI çerçeve penceresinin geçerli MDI alt penceresi ile birlikte çalışır. Örneğin, komut iletilerini etkin MDI alt MDI çerçeve penceresinin önce verilmiş.

- Bir MDI çerçeve penceresinin aşağıdaki standart pencere menü komutları için varsayılan işleyicileri vardır:

    - ID_WINDOW_TILE_VERT

    - ID_WINDOW_TILE_HORZ

    - ID_WINDOW_CASCADE

    - ID_WINDOW_ARRANGE

- Bir MDI çerçeve penceresinin de yeni bir çerçeve ve geçerli belge görünümü oluşturan ıd_wındow_new uygulaması vardır. Bir uygulama MDI pencere işleme özelleştirmek için bu varsayılan komut uygulamaları geçersiz kılabilirsiniz.

C++ kullanmayın **Sil** çerçeve penceresini yok etmek için işleci. Bunun yerine `CWnd::DestroyWindow` kullanın. `CFrameWnd` Uygulaması `PostNcDestroy` penceresi kaldırıldığında C++ nesnesi siler. Kullanıcının varsayılan çerçeve penceresi kapattığı zaman `OnClose` işleyici çağırır `DestroyWindow`.

Daha fazla bilgi için `CMDIFrameWnd`, bkz: [çerçeve Windows](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cmdiframewnd"></a>  CMDIFrameWnd::CMDIFrameWnd

Oluşturur bir `CMDIFrameWnd` nesne.

```
CMDIFrameWnd();
```

### <a name="remarks"></a>Açıklamalar

Çağrı `Create` veya `LoadFrame` görünür MDI çerçeve penceresinin oluşturmak için üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

##  <a name="createclient"></a>  CMDIFrameWnd::CreateClient

Yöneten MSI istemci penceresi oluşturur `CMDIChildWnd` nesneleri.

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Parametreler

*lpCreateStruct*<br/>
Uzun bir işaretçi bir [CREATESTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcreatestructa) yapısı.

*pWindowMenu*<br/>
Penceresi açılır menüsünden bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, geçersiz kılarsanız çağrılmalıdır `OnCreate` doğrudan üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

##  <a name="createnewchild"></a>  CMDIFrameWnd::CreateNewChild

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
Çalışma zamanı sınıf oluşturulacak alt pencerenin.

*Nkaynak*<br/>
Alt pencere ile ilgili paylaşılan kaynak kimliği.

*hMenu*<br/>
Alt pencere menüsü.

*hAccel*<br/>
Alt pencerenin Hızlandırıcı.

### <a name="remarks"></a>Açıklamalar

Alt MDI çerçeve penceresinin windows oluşturmak için bu işlevi kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

##  <a name="getwindowmenupopup"></a>  CMDIFrameWnd::GetWindowMenuPopup

Geçerli açılır menüsüne "Penceresinin" (ile MDI pencere yönetimi menü öğelerinin açılan menü) adlı bir tanıtıcı elde etmek için bu üye işlevini çağırın.

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>Parametreler

*hMenuBar*<br/>
Geçerli menü çubuğu.

### <a name="return-value"></a>Dönüş Değeri

Bir pencere açılır menü var; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama ıd_wındow_new ve ıd_wındow_tıle_horz gibi standart pencere menü komutları içeren bir açılır menü arar.

Standart menü komutunu kimlikleri kullanmayan bir pencere menüsü varsa bu üye işlevini geçersiz kılar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

##  <a name="mdiactivate"></a>  CMDIFrameWnd::MDIActivate

Farklı bir MDI alt penceresini etkinleştirir.

```
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>Parametreler

*pWndActivate*<br/>
Etkinleştirilecek MDI alt penceresi işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi gönderir [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) etkinleştirilmekte olan alt pencerenin hem devre dışı bırakılan alt pencere ileti.

Kullanıcı, fare ve klavye kullanarak MDI alt penceresine odak değiştikçe, gönderilen iletinin budur.

> [!NOTE]
>  Bir MDI alt penceresi MDI çerçeve penceresinin bağımsız olarak etkinleştirilir. Çerçeve etkin olduğunda, son etkinleştirildiği alt pencerenin gönderilen bir [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) bir etkin pencere çerçevesi ve başlık çubuğu, ancak bunu çizmek için ileti başka bir WM_MDIACTIVATE iletisi almaz.

### <a name="example"></a>Örnek

Örneğin bakın [CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup).

##  <a name="mdicascade"></a>  CMDIFrameWnd::MDICascade

Tüm MDI alt Pencereleri Basamakla biçimde düzenler.

```
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>Parametreler

*nTür*<br/>
Art arda bayrak belirtir. Yalnızca aşağıdaki bayrağı belirtilebilir: MDITILE_SKIPDISABLED basamaklı gelen devre dışı MDI alt pencereleri engeller.

### <a name="remarks"></a>Açıklamalar

Ürününün ilk sürümünü `MDICascade`, hiçbir parametre olmadan basamaklı devre dışı olanlar da dahil olmak üzere tüm MDI alt pencereleri. Dosyanın ikinci sürümü için MDITILE_SKIPDISABLED belirtirseniz, isteğe bağlı olarak değil devre dışı MDI alt Pencereleri Basamakla yapar. *nTür* parametresi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

##  <a name="mdigetactive"></a>  CMDIFrameWnd::MDIGetActive

Geçerli etkin MDI alt penceresi alt pencerenin ekranı olup olmadığını belirten bir bayrak alır.

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>Parametreler

*pbMaximized*<br/>
Bir işaretçi bir Boole değeri döndürür. Pencere ekranı, dönüşünü TRUE olarak ayarlayın; Aksi durumda FALSE.

### <a name="return-value"></a>Dönüş Değeri

Etkin MDI alt penceresine bir işaretçi.

### <a name="example"></a>Örnek

Örneğin bakın [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

##  <a name="mdiiconarrange"></a>  CMDIFrameWnd::MDIIconArrange

Tüm simge durumuna küçültülmüş belge alt pencereleri düzenler.

```
void MDIIconArrange();
```

### <a name="remarks"></a>Açıklamalar

Değil simge durumuna küçültülmüş bir alt öğe pencerelerini etkilemez.

### <a name="example"></a>Örnek

Örneğin bakın [CMDIFrameWnd::MDICascade](#mdicascade).

##  <a name="mdimaximize"></a>  CMDIFrameWnd::MDIMaximize

Belirtilen MDI alt penceresinin en üst düzeye çıkarır.

```
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Pencerenin en üst düzeye çıkarmak için işaret eder.

### <a name="remarks"></a>Açıklamalar

Windows istemci pencereyi doldurmak, istemci alanını oluşturmak üzere bir alt penceresi büyütüldüğünde göre yeniden boyutlandırır. Kullanıcı geri yükleyin veya alt pencereyi kapatmak için Windows alt pencerenin denetim menüsünden çerçeve menü çubuğuna yerleştirir. Çerçeve pencere başlığı alt pencerenin başlığı da ekler.

Etkin MDI alt penceresi büyütüldüğünde başka bir MDI alt penceresi etkinleştirilmişse, Windows şu anda etkin alt geri yükler ve yeni etkinleştirilen alt pencerenin en üst düzeye çıkarır.

### <a name="example"></a>Örnek

Örneğin bakın [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

##  <a name="mdinext"></a>  CMDIFrameWnd::MDINext

Hemen arkasına şu anda etkin alt pencerenin alt penceresini etkinleştirir ve şu anda etkin alt pencerenin diğer tüm alt öğe pencerelerini yerleştirir.

```
void MDINext();
```

### <a name="remarks"></a>Açıklamalar

Etkin MDI alt penceresi, üye işlevi şu anda etkin alt geri yükler ve yeni etkinleştirilen alt en üst düzeye çıkarır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

##  <a name="mdiprev"></a>  CMDIFrameWnd::MDIPrev

Önceki alt penceresini etkinleştirir ve şu anda etkin alt pencerenin hemen arkasına yerleştirir.

```
void MDIPrev();
```

### <a name="remarks"></a>Açıklamalar

Etkin MDI alt penceresi, üye işlevi şu anda etkin alt geri yükler ve yeni etkinleştirilen alt en üst düzeye çıkarır.

##  <a name="mdirestore"></a>  CMDIFrameWnd::MDIRestore

Bir MDI alt penceresi simge durumuna küçültülmüş ya da tam ekran boyutunu geri yükler.

```
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Geri yükleme penceresi işaret eder.

### <a name="example"></a>Örnek

Örneğin bakın [CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore).

##  <a name="mdisetmenu"></a>  CMDIFrameWnd::MDISetMenu

Bir MDI çerçeve penceresinin menü, penceresi açılır menüyü veya her ikisi de değiştirir.

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Parametreler

*pFrameMenu*<br/>
Yeni bir çerçeve penceresinin menü menüsünü belirtir. NULL ise, menü değiştirilmez.

*pWindowMenu*<br/>
Yeni Pencere menüsü açılır menüsünü belirtir. NULL ise, menü değiştirilmez.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen bu iletiyle çerçeve penceresinin menü işaretçisi. İşaretçi geçici olabilir ve daha sonra kullanmak üzere saklanmalıdır değil.

### <a name="remarks"></a>Açıklamalar

Arama sonra `MDISetMenu`, bir uygulamayı çağırması gerekir [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) üye işlevinin `CWnd` menü çubuğu güncelleştirilecek.

Bu çağrı penceresinde açılan menüsünün yerini MDI alt penceresi menü öğeleri önceki Pencere menüsünden kaldırılır ve yeni penceresi açılır menüsü eklendi.

Bu çağrı MDI çerçeve penceresinin menü değiştirir ve bir MDI alt penceresi, Denetim menüsüne ve geri yükleme denetimleri önceki bir çerçeve Pencere menüsünden kaldırılır ve yeni menüsüne eklenen.

MDI alt pencereleri yönetmek için çerçeveyi kullanırsanız, bu üye işlevini çağırmayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

##  <a name="mditile"></a>  CMDIFrameWnd::MDITile

Tüm alt pencereleri döşenmiş bir biçimde düzenler.

```
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>Parametreler

*nTür*<br/>
Bir döşeme bayrak belirtir. Bu parametre aşağıdaki bayraklar herhangi biri olabilir:

- Tek bir pencerede başka görünecek şekilde MDITILE_HORIZONTAL kutucukları MDI alt pencereleri.

- MDITILE_SKIPDISABLED engeller döşenmiş gelen MDI alt pencereleri devre dışı.

- Tek bir pencerede başka görünecek şekilde MDITILE_VERTICAL kutucukları MDI alt pencereleri.

### <a name="remarks"></a>Açıklamalar

Ürününün ilk sürümünü `MDITile`, parametre olmadan, Windows 3.1 ve sonraki sürümler altında dikey windows kutucukları. Dosyanın ikinci sürümü windows dikey veya yatay olarak bağlı olarak değeri kutucukları *nTür* parametresi.

### <a name="example"></a>Örnek

Örneğin bakın [CMDIFrameWnd::MDICascade](#mdicascade).

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek MDI](../../visual-cpp-samples.md)<br/>
[MFC örnek MDIDOCVW](../../visual-cpp-samples.md)<br/>
[MFC örnek SNAPVW](../../visual-cpp-samples.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CMDIChildWnd Sınıfı](../../mfc/reference/cmdichildwnd-class.md)
