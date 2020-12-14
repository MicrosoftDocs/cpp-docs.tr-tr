---
description: 'Daha fazla bilgi edinin: Cmdictepdwnd sınıfı'
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
ms.openlocfilehash: 4e9bf936cbb4f07401e8d54c56516f8846f2fc0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336691"
---
# <a name="cmdichildwnd-class"></a>Cmdicchild Dwnd sınıfı

Windows çoklu belge arabirimi (MDI) alt penceresi işlevlerini, pencereyi yönetmek için üyelerle birlikte sağlar.

## <a name="syntax"></a>Syntax

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
|[Cmdictepdwnd:: Create](#create)|Nesnesiyle ilişkili Windows MDI alt penceresini oluşturur `CMDIChildWnd` .|
|[Cmdictepdwnd:: Getmdıframe](#getmdiframe)|MDI istemci penceresinin üst MDI çerçevesini döndürür.|
|[Cmdictepdwnd:: Mdıactivate](#mdiactivate)|Bu MDI alt penceresini etkinleştirir.|
|[Cmdicchild Dwnd:: Mdıdestroy](#mdidestroy)|Bu MDI alt penceresini yok eder.|
|[Cmdictepdwnd:: Mdıdıkapla](#mdimaximize)|Bu MDI alt penceresini en üst düzeye çıkarır.|
|[Cmdicchild Dwnd:: MDIRestore](#mdirestore)|Bu MDI alt penceresini ekranı kaplamış veya en küçük boyuttan geri yükler.|
|[Cmdictepdwnd:: SetHandles](#sethandles)|Menü ve Hızlandırıcı kaynakları için tutamaçları ayarlar.|

## <a name="remarks"></a>Açıklamalar

MDI alt penceresi, bir MDI alt penceresinin, masaüstü yerine bir MDI çerçevesi penceresi içinde görünmesi dışında, bir MDI alt penceresi, tipik bir çerçeve penceresine benzer şekilde görünür. MDI alt penceresi kendi menü çubuğuna sahip değildir, bunun yerine MDI çerçeve penceresinin menüsünü paylaşır. Framework, geçerli etkin MDI alt penceresini göstermek için MDI kare menüsünü otomatik olarak değiştirir.

Uygulamanız için yararlı bir MDI alt penceresi oluşturmak için, öğesinden bir sınıf türetebilirsiniz `CMDIChildWnd` . Uygulamanıza özgü verileri depolamak için türetilmiş sınıfa üye değişkenleri ekleyin. İletileri pencereye yönlendirdiğinde ne olacağını belirtmek için ileti işleyicisi üye işlevlerini ve türetilmiş sınıfta bir ileti eşlemesi uygulayın.

MDI alt penceresi oluşturmak için üç yol vardır:

- Kullanarak doğrudan oluşturun `Create` .

- Kullanarak doğrudan oluşturun `LoadFrame` .

- Bir belge şablonu aracılığıyla dolaylı olarak oluşturun.

Veya çağrısından önce `Create` `LoadFrame` , C++ işlecini kullanarak yığında kare pencere nesnesi oluşturmanız gerekir **`new`** . ' İ çağırmadan önce, `Create` çerçeveye ait simge ve sınıf stillerini ayarlamak Için [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) genel işleviyle bir pencere sınıfı da kaydedebilirsiniz.

`Create`Çerçevenin oluşturma parametrelerini hemen bağımsız değişken olarak geçirmek için üye işlevini kullanın.

`LoadFrame` öğesinden daha az bağımsız değişken gerektirir `Create` ve bunun yerine çerçevenin başlık, simge, Hızlandırıcı tablosu ve menü dahil olmak üzere kaynaklardaki varsayılan değerlerinin çoğunu alır. Tarafından erişilebilmesi için `LoadFrame` , tüm bu kaynakların aynı kaynak kimliğine sahip olması gerekir (örneğin, IDR_MAINFRAME).

Bir `CMDIChildWnd` nesne görünümler ve belgeler içerdiğinde, doğrudan programcı tarafından değil Framework tarafından dolaylı olarak oluşturulur. `CDocTemplate`Nesnesi çerçevenin oluşturulmasını, kapsayan görünümlerin oluşturulmasını ve görünümlerin ilgili belge ile bağlantısını düzenler. Oluşturucunun parametreleri, `CDocTemplate` `CRuntimeClass` içerilen üç sınıfın (belge, çerçeve ve Görünüm) sayısını belirtir. Bir `CRuntimeClass` nesne, Kullanıcı tarafından belirtildiğinde (örneğin, dosya yeni komut veya MDI penceresi yeni komutu kullanılarak) dinamik olarak yeni çerçeveler oluşturmak için çerçevesi tarafından kullanılır.

`CMDIChildWnd`Yukarıdaki RUNTIME_CLASS mekanizmanın doğru çalışması için öğesinden türetilmiş bir çerçeve pencere sınıfı DECLARE_DYNCREATE bildirilmelidir.

`CMDIChildWnd`Sınıfı, varsayılan uygulamasının çoğunu öğesinden devralır `CFrameWnd` . Bu özelliklerin ayrıntılı bir listesi için lütfen [CFrameWnd](../../mfc/reference/cframewnd-class.md) sınıfı açıklamasına bakın. `CMDIChildWnd`Sınıfı aşağıdaki ek özelliklere sahiptir:

- `CMultiDocTemplate`Sınıfıyla birlikte, `CMDIChildWnd` aynı belge şablonundaki birden çok nesne aynı menüyü paylaşır ve Windows sistem kaynaklarını kaydederek aynı menüyü paylaşır.

- Şu anda etkin olan MDI alt pencere menüsü tamamen MDI çerçevesi penceresinin menüsünü değiştirir ve şu anda etkin olan MDI alt penceresinin resim yazısı MDI çerçevesinin pencere yazısına eklenir. MDI çerçevesi penceresiyle birlikte uygulanan MDI alt pencere işlevlerine yönelik daha fazla örnek için bkz `CMDIFrameWnd` . sınıf açıklaması.

**`delete`** Bir çerçeve penceresini yok etmek Için C++ işlecini kullanmayın. Bunun yerine `CWnd::DestroyWindow` kullanın. Uygulamasının `CFrameWnd` uygulanması, `PostNcDestroy` pencere yok edildiğinde C++ nesnesini silecektir. Kullanıcı çerçeve penceresini kapattığında, varsayılan `OnClose` işleyici çağırır `DestroyWindow` .

Hakkında daha fazla bilgi için `CMDIChildWnd` bkz. [çerçeve pencereleri](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cmdichildwndcmdichildwnd"></a><a name="cmdichildwnd"></a> Cmdictepdwnd:: Cmdicchild Dwnd

Bir nesne oluşturmak için çağırın `CMDIChildWnd` .

```
CMDIChildWnd();
```

### <a name="remarks"></a>Açıklamalar

`Create`Görünür pencereyi oluşturmak için çağırın.

### <a name="example"></a>Örnek

  [Cmdictepdwnd:: Create](#create)örneğine bakın.

## <a name="cmdichildwndcreate"></a><a name="create"></a> Cmdictepdwnd:: Create

Bir Windows MDI alt penceresi oluşturmak ve nesneye iliştirmek için bu üye işlevi çağırın `CMDIChildWnd` .

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
Windows sınıfına ( [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısı) ad veren null ile sonlandırılmış bir karakter dizesini işaret eder. Sınıf adı, [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) genel işlevine kayıtlı herhangi bir ad olabilir. Standart için NULL olmalıdır `CMDIChildWnd` .

*lpszWindowName*<br/>
Pencere adını temsil eden, null ile sonlandırılmış bir karakter dizesini işaret eder. Başlık çubuğu için metin olarak kullanılır.

*dwStyle*<br/>
Pencere [stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) özniteliklerini belirtir. WS_CHILD stili gereklidir.

*Rect*<br/>
Pencerenin boyutunu ve konumunu içerir. `rectDefault`Değer, Windows 'un boyut ve yeni konumunu belirlemesine izin verir `CMDIChildWnd` .

*pParentWnd*<br/>
Pencerenin üst öğesini belirtir. NULL ise, ana uygulama penceresi kullanılır.

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısını belirtir. Bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Şu anda etkin olan MDI alt çerçeve penceresi, üst çerçeve penceresinin başlığını belirleyebilir. Bu özellik, alt çerçeve penceresinin FWS_ADDTOTITLE stil bitini kapatarak devre dışı bırakılır.

Framework, bir alt pencere oluşturmak için bir Kullanıcı komutuna yanıt olarak bu üye işlevini çağırır ve Framework, alt pencereyi uygulamaya düzgün şekilde bağlamak için *pContext* parametresini kullanır. `Create`' İ çağırdığınızda, *PCONTEXT* null olabilir.

### <a name="example"></a>Örnek

Örnek 1:

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>Örnek

Örnek 2:

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

## <a name="cmdichildwndgetmdiframe"></a><a name="getmdiframe"></a> Cmdictepdwnd:: Getmdıframe

MDI üst çerçevesini döndürmek için bu işlevi çağırın.

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>Dönüş Değeri

MDI üst çerçeve penceresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Döndürülen çerçeve, ' dan çıkarılan iki üst öğesidir `CMDIChildWnd` ve nesneyi yöneten MDICLIENT türünde pencerenin üst öğesidir `CMDIChildWnd` . [](../../mfc/reference/cwnd-class.md#getparent) `CMDIChildWnd` Nesnenin ımmdıclıent Parent öğesini geçici bir işaretçi olarak döndürmek için GetParent üye işlevini çağırın `CWnd` .

### <a name="example"></a>Örnek

  [Cmdiframewnd:: MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu)örneğine bakın.

## <a name="cmdichildwndmdiactivate"></a><a name="mdiactivate"></a> Cmdictepdwnd:: Mdıactivate

MDI çerçevesi penceresinden bağımsız olarak bir MDI alt penceresini etkinleştirmek için bu üye işlevini çağırın.

```cpp
void MDIActivate();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve etkin hale geldiğinde, en son etkinleştirilen alt pencere de etkinleştirilir.

### <a name="example"></a>Örnek

  [Cmdiframewnd:: GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup)örneğine bakın.

## <a name="cmdichildwndmdidestroy"></a><a name="mdidestroy"></a> Cmdicchild Dwnd:: Mdıdestroy

Bir MDI alt penceresini yok etmek için bu üye işlevini çağırın.

```cpp
void MDIDestroy();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, alt pencerenin başlığını çerçeve penceresinden kaldırır ve alt pencereyi devre dışı bırakır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

## <a name="cmdichildwndmdimaximize"></a><a name="mdimaximize"></a> Cmdictepdwnd:: Mdıdıkapla

MDI alt penceresini en üst düzeye çıkarmak için bu üye işlevi çağırın.

```cpp
void MDIMaximize();
```

### <a name="remarks"></a>Açıklamalar

Bir alt pencere ekranı kapladığında Windows, istemci alanının çerçeve penceresinin istemci alanını doldurmasını sağlamak için bunu yeniden boyutlandırır. Windows, alt pencereyi geri yüklemek veya kapatmak ve alt pencerenin başlığını çerçeve pencere başlığına eklemek için çerçevenin menü çubuğuna alt pencerenin Denetim menüsünü yerleştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

## <a name="cmdichildwndmdirestore"></a><a name="mdirestore"></a> Cmdicchild Dwnd:: MDIRestore

Bir MDI alt penceresini ekranı kaplamış veya küçültülmüş boyuttan geri yüklemek için bu üye işlevi çağırın.

```cpp
void MDIRestore();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

## <a name="cmdichildwndsethandles"></a><a name="sethandles"></a> Cmdictepdwnd:: SetHandles

Menü ve Hızlandırıcı kaynakları için tutamaçları ayarlar.

```cpp
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
[CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd sınıfı](../../mfc/reference/cmdiframewnd-class.md)
