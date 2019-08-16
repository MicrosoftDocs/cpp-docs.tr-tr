---
title: Cmdicchild Dwnd sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMDIChildWnd
- AFXWIN/CMDIChildWnd
- AFXWIN/CMDIChildWnd::CMDIChildWnd
- AFXWIN/CMDIChildWnd::Create
- AFXWIN/CMDIChildWnd::GetMDIFrame
- AFXWIN/CMDIChildWnd::MDIActivate
- AFXWIN/CMDIChildWnd::MDIDestroy
- AFXWIN/CMDIChildWnd::MDIMaximize
- AFXWIN/CMDIChildWnd::MDIRestore
- AFXWIN/CMDIChildWnd::SetHandles
helpviewer_keywords:
- CMDIChildWnd [MFC], CMDIChildWnd
- CMDIChildWnd [MFC], Create
- CMDIChildWnd [MFC], GetMDIFrame
- CMDIChildWnd [MFC], MDIActivate
- CMDIChildWnd [MFC], MDIDestroy
- CMDIChildWnd [MFC], MDIMaximize
- CMDIChildWnd [MFC], MDIRestore
- CMDIChildWnd [MFC], SetHandles
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
ms.openlocfilehash: 09a9846cc3d242ef7d812cb31b4dcdd515d5f6ef
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506074"
---
# <a name="cmdichildwnd-class"></a>Cmdicchild Dwnd sınıfı

Windows çoklu belge arabirimi (MDI) alt penceresi işlevlerini, pencereyi yönetmek için üyelerle birlikte sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMDIChildWnd : public CFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cmdictepdwnd:: Cmdicchild Dwnd](#cmdichildwnd)|Bir `CMDIChildWnd` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cmdictepdwnd:: Create](#create)|`CMDIChildWnd` Nesnesiyle ilişkili Windows MDI alt penceresini oluşturur.|
|[Cmdictepdwnd:: Getmdıframe](#getmdiframe)|MDI istemci penceresinin üst MDI çerçevesini döndürür.|
|[Cmdictepdwnd:: Mdıactivate](#mdiactivate)|Bu MDI alt penceresini etkinleştirir.|
|[Cmdicchild Dwnd:: Mdıdestroy](#mdidestroy)|Bu MDI alt penceresini yok eder.|
|[Cmdictepdwnd:: Mdıdıkapla](#mdimaximize)|Bu MDI alt penceresini en üst düzeye çıkarır.|
|[Cmdicchild Dwnd:: MDIRestore](#mdirestore)|Bu MDI alt penceresini ekranı kaplamış veya en küçük boyuttan geri yükler.|
|[Cmdictepdwnd:: SetHandles](#sethandles)|Menü ve Hızlandırıcı kaynakları için tutamaçları ayarlar.|

## <a name="remarks"></a>Açıklamalar

MDI alt penceresi, bir MDI alt penceresinin, masaüstü yerine bir MDI çerçevesi penceresi içinde görünmesi dışında, bir MDI alt penceresi, tipik bir çerçeve penceresine benzer şekilde görünür. MDI alt penceresi kendi menü çubuğuna sahip değildir, bunun yerine MDI çerçeve penceresinin menüsünü paylaşır. Framework, geçerli etkin MDI alt penceresini göstermek için MDI kare menüsünü otomatik olarak değiştirir.

Uygulamanız için yararlı bir MDI alt penceresi oluşturmak için, öğesinden `CMDIChildWnd`bir sınıf türetebilirsiniz. Uygulamanıza özgü verileri depolamak için türetilmiş sınıfa üye değişkenleri ekleyin. İletileri pencereye yönlendirdiğinde ne olacağını belirtmek için ileti işleyicisi üye işlevlerini ve türetilmiş sınıfta bir ileti eşlemesi uygulayın.

MDI alt penceresi oluşturmak için üç yol vardır:

- Kullanarak `Create`doğrudan oluşturun.

- Kullanarak `LoadFrame`doğrudan oluşturun.

- Bir belge şablonu aracılığıyla dolaylı olarak oluşturun.

`Create` C++ Veya öğesini`LoadFrame`çağırmadan önce, **New** işlecini kullanarak yığında çerçeve pencere nesnesi oluşturmanız gerekir. ' İ `Create` çağırmadan önce, çerçeveye ait simge ve sınıf stillerini ayarlamak için [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) genel işleviyle bir pencere sınıfı da kaydedebilirsiniz.

Çerçevenin oluşturma parametrelerini hemen bağımsız değişken olarak geçirmek için üyeişlevinikullanın.`Create`

`LoadFrame`öğesinden `Create`daha az bağımsız değişken gerektirir ve bunun yerine çerçevenin başlık, simge, Hızlandırıcı tablosu ve menü dahil olmak üzere kaynaklardaki varsayılan değerlerinin çoğunu alır. Tarafından `LoadFrame`erişilebilmesi için, tüm bu kaynakların aynı kaynak kimliğine sahip olması gerekir (örneğin, IDR_MAINFRAME).

Bir `CMDIChildWnd` nesne görünümler ve belgeler içerdiğinde, doğrudan programcı tarafından değil Framework tarafından dolaylı olarak oluşturulur. `CDocTemplate` Nesnesi çerçevenin oluşturulmasını, kapsayan görünümlerin oluşturulmasını ve görünümlerin ilgili belge ile bağlantısını düzenler. `CDocTemplate` Oluşturucunun parametreleri, içerilen üç sınıfın ( `CRuntimeClass` belge, çerçeve ve Görünüm) sayısını belirtir. Bir `CRuntimeClass` nesne, Kullanıcı tarafından belirtildiğinde (örneğin, dosya yeni komut veya MDI penceresi yeni komutu kullanılarak) dinamik olarak yeni çerçeveler oluşturmak için çerçevesi tarafından kullanılır.

Yukarıdaki RUNTIME_CLASS mekanizmasının düzgün çalışması için öğesinden `CMDIChildWnd` türetilmiş bir çerçeve pencere sınıfı DECLARE_DYNCREATE ile bildirilmelidir.

Sınıfı `CMDIChildWnd` , varsayılan uygulamasının çoğunu öğesinden `CFrameWnd`devralır. Bu özelliklerin ayrıntılı bir listesi için lütfen [CFrameWnd](../../mfc/reference/cframewnd-class.md) sınıfı açıklamasına bakın. `CMDIChildWnd` Sınıfı aşağıdaki ek özelliklere sahiptir:

- `CMultiDocTemplate` Sınıfıyla birlikte, aynı belge şablonundaki birden `CMDIChildWnd` çok nesne aynı menüyü paylaşır ve Windows sistem kaynaklarını kaydederek aynı menüyü paylaşır.

- Şu anda etkin olan MDI alt pencere menüsü tamamen MDI çerçevesi penceresinin menüsünü değiştirir ve şu anda etkin olan MDI alt penceresinin resim yazısı MDI çerçevesinin pencere yazısına eklenir. MDI çerçevesi penceresiyle birlikte uygulanan MDI alt pencere işlevlerine yönelik daha fazla örnek için bkz `CMDIFrameWnd` . sınıf açıklaması.

Bir çerçeve penceresini yok C++ etmek için **Delete** işlecini kullanmayın. Bunun yerine `CWnd::DestroyWindow` kullanın. Uygulamasının `CFrameWnd` C++ uygulanması ,pencereyokedildiğindenesneyisiler.`PostNcDestroy` Kullanıcı çerçeve penceresini kapattığında, varsayılan `OnClose` işleyici çağırır. `DestroyWindow`

Hakkında `CMDIChildWnd`daha fazla bilgi için bkz. [çerçeve pencereleri](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="cmdichildwnd"></a>Cmdictepdwnd:: Cmdicchild Dwnd

Bir `CMDIChildWnd` nesne oluşturmak için çağırın.

```
CMDIChildWnd();
```

### <a name="remarks"></a>Açıklamalar

Görünür `Create` pencereyi oluşturmak için çağırın.

### <a name="example"></a>Örnek

  [Cmdictepdwnd:: Create](#create)örneğine bakın.

##  <a name="create"></a>Cmdictepdwnd:: Create

Bir Windows MDI alt penceresi oluşturmak ve `CMDIChildWnd` nesneye iliştirmek için bu üye işlevi çağırın.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_OVERLAPPEDWINDOW,
    const RECT& rect = rectDefault,
    CMDIFrameWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>
Windows sınıfına ( [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısı) ad veren null ile sonlandırılmış bir karakter dizesini işaret eder. Sınıf adı, [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) genel işlevine kayıtlı herhangi bir ad olabilir. Standart `CMDIChildWnd`için null olmalıdır.

*lpszWindowName*<br/>
Pencere adını temsil eden, null ile sonlandırılmış bir karakter dizesini işaret eder. Başlık çubuğu için metin olarak kullanılır.

*dwStyle*<br/>
Pencere [stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) özniteliklerini belirtir. WS_CHILD stili gereklidir.

*Rect*<br/>
Pencerenin boyutunu ve konumunu içerir. Değer `rectDefault` , Windows 'un boyut ve yeni `CMDIChildWnd`konumunu belirlemesine izin verir.

*pParentWnd*<br/>
Pencerenin üst öğesini belirtir. NULL ise, ana uygulama penceresi kullanılır.

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısını belirtir. Bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Şu anda etkin olan MDI alt çerçeve penceresi, üst çerçeve penceresinin başlığını belirleyebilir. Bu özellik, alt çerçeve penceresinin FWS_ADDTOTITLE stil bitini kapatarak devre dışı bırakılır.

Framework, bir alt pencere oluşturmak için bir Kullanıcı komutuna yanıt olarak bu üye işlevini çağırır ve Framework, alt pencereyi uygulamaya düzgün şekilde bağlamak için *pContext* parametresini kullanır. ' İ çağırdığınızda `Create`, *pContext* null olabilir.

### <a name="example"></a>Örnek

Örnek 1:

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>Örnek

Örnek 2:

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

##  <a name="getmdiframe"></a>Cmdictepdwnd:: Getmdıframe

MDI üst çerçevesini döndürmek için bu işlevi çağırın.

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>Dönüş Değeri

MDI üst çerçeve penceresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Döndürülen çerçeve, `CMDIChildWnd` ' dan çıkarılan iki üst öğesidir ve `CMDIChildWnd` nesneyi yöneten MDICLIENT türünde pencerenin üst öğesidir. `CMDIChildWnd` Nesnenin ımmdıclıent Parent öğesini geçici `CWnd` bir işaretçi olarak döndürmek için [GetParent](../../mfc/reference/cwnd-class.md#getparent) üye işlevini çağırın.

### <a name="example"></a>Örnek

  [Cmdiframewnd:: MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu)örneğine bakın.

##  <a name="mdiactivate"></a>Cmdictepdwnd:: Mdıactivate

MDI çerçevesi penceresinden bağımsız olarak bir MDI alt penceresini etkinleştirmek için bu üye işlevini çağırın.

```
void MDIActivate();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve etkin hale geldiğinde, en son etkinleştirilen alt pencere de etkinleştirilir.

### <a name="example"></a>Örnek

  [Cmdiframewnd:: GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup)örneğine bakın.

##  <a name="mdidestroy"></a>Cmdicchild Dwnd:: Mdıdestroy

Bir MDI alt penceresini yok etmek için bu üye işlevini çağırın.

```
void MDIDestroy();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, alt pencerenin başlığını çerçeve penceresinden kaldırır ve alt pencereyi devre dışı bırakır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

##  <a name="mdimaximize"></a>Cmdictepdwnd:: Mdıdıkapla

MDI alt penceresini en üst düzeye çıkarmak için bu üye işlevi çağırın.

```
void MDIMaximize();
```

### <a name="remarks"></a>Açıklamalar

Bir alt pencere ekranı kapladığında Windows, istemci alanının çerçeve penceresinin istemci alanını doldurmasını sağlamak için bunu yeniden boyutlandırır. Windows, alt pencereyi geri yüklemek veya kapatmak ve alt pencerenin başlığını çerçeve pencere başlığına eklemek için çerçevenin menü çubuğuna alt pencerenin Denetim menüsünü yerleştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

##  <a name="mdirestore"></a>Cmdicchild Dwnd:: MDIRestore

Bir MDI alt penceresini ekranı kaplamış veya küçültülmüş boyuttan geri yüklemek için bu üye işlevi çağırın.

```
void MDIRestore();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

##  <a name="sethandles"></a>Cmdictepdwnd:: SetHandles

Menü ve Hızlandırıcı kaynakları için tutamaçları ayarlar.

```
void SetHandles(
    HMENU hMenu,
    HACCEL hAccel);
```

### <a name="parameters"></a>Parametreler

*hMenu*<br/>
Bir menü kaynağının tanıtıcısı.

*hAccel*<br/>
Hızlandırıcı kaynağının tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

MDI alt pencere nesnesi tarafından kullanılan menü ve Hızlandırıcı kaynaklarını ayarlamak için bu işlevi çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek MDıDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd Sınıfı](../../mfc/reference/cmdiframewnd-class.md)
