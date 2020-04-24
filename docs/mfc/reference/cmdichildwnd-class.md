---
title: CMDIChildWnd Sınıfı
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
ms.openlocfilehash: a547a21b96d035f507e749aeb19f891175498d5d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754569"
---
# <a name="cmdichildwnd-class"></a>CMDIChildWnd Sınıfı

Pencereyi yönetmek için üyelerle birlikte bir Windows birden çok belge arabirimi (MDI) alt penceresiişlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMDIChildWnd : public CFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|Bir `CMDIChildWnd` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMDIChildWnd::Oluştur](#create)|Nesneyle ilişkili Windows MDI alt `CMDIChildWnd` penceresini oluşturur.|
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|MDI istemci penceresinin üst MDI çerçevesini döndürür.|
|[CMDIChildWnd::MDIActivate](#mdiactivate)|Bu MDI alt pencereyi etkinleştirir.|
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|Bu MDI alt pencereyi yok eder.|
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|Bu MDI alt pencereyi en üst düzeye çıkarır.|
|[CMDIChildWnd::MDIRestore](#mdirestore)|Bu MDI alt pencereyi en üst düzeye veya en aza indirilmiş boyuttan geri yükler.|
|[CMDIChildWnd::SetHandles](#sethandles)|Menü ve hızlandırıcı kaynakları için tutamaçları ayarlar.|

## <a name="remarks"></a>Açıklamalar

MDI alt penceresi, MDI alt penceresinin masaüstünde değil, MDI çerçeve penceresinin içinde görünmesi dışında, tipik bir çerçeve penceresine çok benzer. MDI alt penceresinin kendi menü çubuğu yoktur, ancak bunun yerine MDI çerçeve penceresinin menüsünü paylaşır. Çerçeve, şu anda etkin olan MDI alt penceresini temsil edecek şekilde MDI çerçeve menüsünü otomatik olarak değiştirir.

Uygulamanız için yararlı bir MDI alt penceresi oluşturmak `CMDIChildWnd`için, 'den bir sınıf türetin. Uygulamanıza özgü verileri depolamak için türemiş sınıfa üye değişkenler ekleyin. İletiler pencereye yönlendirildiğinde ne olacağını belirtmek için ileti işleyicisi üye işlevlerini ve türetilmiş sınıfta bir ileti eşlemi uygulayın.

Bir MDI alt penceresi oluşturmanın üç yolu vardır:

- Doğrudan kullanarak `Create`inşa edin.

- Doğrudan kullanarak `LoadFrame`inşa edin.

- Dolaylı olarak bir belge şablonu aracılığıyla oluşturmak.

Çağırmadan `Create` önce `LoadFrame`veya , C++ **yeni** işleci kullanarak yığın üzerinde çerçeve-pencere nesnesi oluşturmanız gerekir. Aramadan `Create` önce, çerçeveiçin simge yi ve sınıf stillerini ayarlamak için [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) global işlevine sahip bir pencere sınıfı da kaydedebilirsiniz.

Çerçevenin `Create` oluşturma parametrelerini hemen bağımsız değişken olarak geçirmek için üye işlevi kullanın.

`LoadFrame`daha `Create`az bağımsız değişken gerektirir ve bunun yerine çerçevenin resim yazısı, simge, hızlandırıcı tablosu ve menü dahil olmak üzere kaynaklardan varsayılan değerlerinin çoğunu alır. Bu kaynaklartarafından `LoadFrame`erişilebilmek için tüm kaynakların aynı kaynak kimliğine sahip olması gerekir (örneğin, IDR_MAINFRAME).

Bir `CMDIChildWnd` nesne görünümler ve belgeler içeriyorsa, doğrudan programcı tarafından değil, dolaylı olarak çerçeve tarafından oluşturulur. Nesne `CDocTemplate` çerçevenin oluşturulmasını, içeren görünümlerin oluşturulmasını ve görünümlerin uygun belgeye bağlantısını yönetir. `CDocTemplate` Oluşturucunun `CRuntimeClass` parametreleri ilgili üç sınıfın (belge, çerçeve ve görünüm) Bir `CRuntimeClass` nesne, kullanıcı tarafından belirtildiğinde dinamik olarak yeni çerçeveler oluşturmak için çerçeve tarafından kullanılır (örneğin, Yeni Dosya komutu veya MDI Penceresi Yeni komutu kullanılarak).

Yukarıdaki RUNTIME_CLASS mekanizmasının `CMDIChildWnd` doğru çalışabilmesi için, türetilen bir çerçeve penceresi sınıfının DECLARE_DYNCREATE ile birlikte bildirilmesi gerekir.

Sınıf, `CMDIChildWnd` varsayılan uygulamasının `CFrameWnd`çoğunu . Bu özelliklerin ayrıntılı bir listesi için lütfen [CFrameWnd](../../mfc/reference/cframewnd-class.md) sınıfı açıklamasına bakın. Sınıfın `CMDIChildWnd` aşağıdaki ek özellikleri vardır:

- `CMultiDocTemplate` Sınıfla birlikte, aynı `CMDIChildWnd` belge şablonundan birden çok nesne aynı menüyü paylaşarak Windows sistem kaynaklarını kaydeder.

- Şu anda etkin olan MDI alt pencere menüsü tamamen MDI çerçeve penceresinin menüsünün yerini alır ve şu anda etkin olan MDI alt penceresinin alt yazısı MDI çerçeve penceresinin alt yazısına eklenir. MDI çerçeve penceresi ile birlikte uygulanan MDI alt pencere işlevlerinin diğer `CMDIFrameWnd` örnekleri için sınıf açıklamasına bakın.

Çerçeve penceresini yok etmek için C++ **silme** işleci kullanmayın. Bunun yerine `CWnd::DestroyWindow` kullanın. Pencere `CFrameWnd` yok `PostNcDestroy` edildiğinde C++ nesnesi siler. Kullanıcı çerçeve penceresini kapattığında, `OnClose` varsayılan işleyici `DestroyWindow`.

Daha fazla `CMDIChildWnd`bilgi için [Bkz. Çerçeve Windows.](../../mfc/frame-windows.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cmdichildwndcmdichildwnd"></a><a name="cmdichildwnd"></a>CMDIChildWnd::CMDIChildWnd

Bir `CMDIChildWnd` nesne oluşturmak için arayın.

```
CMDIChildWnd();
```

### <a name="remarks"></a>Açıklamalar

Görünür `Create` pencereyi oluşturmak için arayın.

### <a name="example"></a>Örnek

  [CMDIChildWnd](#create)için örneğe bakın:Oluştur .

## <a name="cmdichildwndcreate"></a><a name="create"></a>CMDIChildWnd::Oluştur

Windows MDI alt penceresi oluşturmak ve `CMDIChildWnd` nesneye eklemek için bu üye işlevi arayın.

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
Windows sınıfını [(WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısı) isimleyen null-sonlandırılan karakter dizesini işaret eder. Sınıf [adı, AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) global işlevine kayıtlı herhangi bir ad olabilir. Bir standart `CMDIChildWnd`için NULL olmalıdır.

*lpszWindowName*<br/>
Pencere adını temsil eden null-sonlandırılan karakter dizesini gösterir. Başlık çubuğu için metin olarak kullanılır.

*Dwstyle*<br/>
Pencere [stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) özniteliklerini belirtir. WS_CHILD stili gereklidir.

*Rect*<br/>
Pencerenin boyutunu ve konumunu içerir. Değer, Windows'un `rectDefault` yeni `CMDIChildWnd`nin boyutunu ve konumunu belirtmesine olanak tanır.

*pParentWnd*<br/>
Pencerenin üst öğesini belirtir. NULL ise, ana uygulama penceresi kullanılır.

*Pcontext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısını belirtir. Bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Şu anda etkin olan MDI alt çerçeve penceresi, üst çerçeve penceresinin alt yazısını belirleyebilir. Bu özellik, alt çerçeve penceresinin FWS_ADDTOTITLE stil bitini kapatarak devre dışı bırakılır.

Çerçeve, bir alt pencere oluşturmak için bir kullanıcı komutuna yanıt olarak bu üye işlevi çağırır ve çerçeve alt pencereyi uygulamaya düzgün bağlamak için *pContext* parametresini kullanır. `Create`Aradiğinizde, *pContext* NULL olabilir.

### <a name="example"></a>Örnek

Örnek 1:

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>Örnek

Örnek 2:

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

## <a name="cmdichildwndgetmdiframe"></a><a name="getmdiframe"></a>CMDIChildWnd::GetMDIFrame

MDI üst çerçevesini döndürmek için bu işlevi arayın.

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>Dönüş Değeri

MDI üst çerçeve penceresiiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Döndürülen çerçeve iki ebeveyn `CMDIChildWnd` kaldırıldı ve `CMDIChildWnd` nesneyi yöneten MDICLIENT türü penceresinin üst. Nesnenin hemen MDICLIENT `CMDIChildWnd` üst öğesini geçici `CWnd` işaretçi olarak döndürmek için [GetParent](../../mfc/reference/cwnd-class.md#getparent) üye işlevini arayın.

### <a name="example"></a>Örnek

  CMDIFrameWnd için örneğe [bakın::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).

## <a name="cmdichildwndmdiactivate"></a><a name="mdiactivate"></a>CMDIChildWnd::MDIActivate

MDI çerçeve penceresinden bağımsız olarak bir MDI alt penceresi etkinleştirmek için bu üye işlevi arayın.

```cpp
void MDIActivate();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve etkin hale geldiğinde, en son etkinleştirilen alt pencere de etkinleştirilir.

### <a name="example"></a>Örnek

  CMDIFrameWnd için örneğe [bakın:GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).

## <a name="cmdichildwndmdidestroy"></a><a name="mdidestroy"></a>CMDIChildWnd::MDIDestroy

Bir MDI alt penceresini yok etmek için bu üye işlevi arayın.

```cpp
void MDIDestroy();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, alt pencerenin başlığını çerçeve penceresinden kaldırır ve alt pencereyi devre dışı bırakır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

## <a name="cmdichildwndmdimaximize"></a><a name="mdimaximize"></a>CMDIChildWnd::MDIMaximize

Bir MDI alt penceresini en üst düzeye çıkarmak için bu üye işlevini arayın.

```cpp
void MDIMaximize();
```

### <a name="remarks"></a>Açıklamalar

Alt pencere en üst düzeye çıktığında, Windows istemci alanı çerçeve penceresinin istemci alanını doldurmak için yeniden boyutlandırılır. Windows, kullanıcının alt pencereyi geri yükleyebilmeleri veya kapatabilmesi için alt pencerenin Denetim menüsünü çerçevenin menü çubuğuna yerleştirir ve alt pencerenin başlığını çerçeve penceresi başlığına ekler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

## <a name="cmdichildwndmdirestore"></a><a name="mdirestore"></a>CMDIChildWnd::MDIRestore

MDI alt penceresini maksimize edilmiş veya en aza indirilmiş boyuttan geri yüklemek için bu üye işlevi arayın.

```cpp
void MDIRestore();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

## <a name="cmdichildwndsethandles"></a><a name="sethandles"></a>CMDIChildWnd::SetHandles

Menü ve hızlandırıcı kaynakları için tutamaçları ayarlar.

```cpp
void SetHandles(
    HMENU hMenu,
    HACCEL hAccel);
```

### <a name="parameters"></a>Parametreler

*Hmenu*<br/>
Menü kaynağının tutamacı.

*hAccel*<br/>
Hızlandırıcı kaynağının tutamacı.

### <a name="remarks"></a>Açıklamalar

MDI alt pencere nesnesi tarafından kullanılan menü ve hızlandırıcı kaynaklarını ayarlamak için bu işlevi arayın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd Sınıfı](../../mfc/reference/cmdiframewnd-class.md)
