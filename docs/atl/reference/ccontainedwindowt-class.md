---
description: 'Daha fazla bilgi edinin: CContainedWindowT sınıfı'
title: CContainedWindowT sınıfı
ms.date: 11/04/2016
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
ms.openlocfilehash: 68135ec6d8dc43623ec2a827bbe075e24eef8d42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142083"
---
# <a name="ccontainedwindowt-class"></a>CContainedWindowT sınıfı

Bu sınıf, başka bir nesne içinde yer alan bir pencere uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>
class CContainedWindowT : public TBase
```

#### <a name="parameters"></a>Parametreler

*TBase*<br/>
Yeni sınıfınızın temel sınıfı. Varsayılan temel sınıf `CWindow` .

*TWinTraits*<br/>
Pencerenize yönelik stilleri tanımlayan bir nitelikler sınıfı. Varsayılan değer: `CControlWinTraits`.

> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) , öğesinin bir özelleştirmesi `CContainedWindowT` . Temel sınıf veya nitelikleri değiştirmek istiyorsanız, `CContainedWindowT` doğrudan kullanın.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CContainedWindowT:: CContainedWindowT](#ccontainedwindowt)|Oluşturucu. Hangi ileti eşlemesinin içerilen pencerenin iletilerini işleyeceğini belirtmek için veri üyelerini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CContainedWindowT:: Create](#create)|Bir pencere oluşturur.|
|[CContainedWindowT::D efWindowProc](#defwindowproc)|Varsayılan ileti işleme sağlar.|
|[CContainedWindowT:: GetCurrentMessage](#getcurrentmessage)|Geçerli iletiyi döndürür.|
|[CContainedWindowT:: Registerwndsüper sınıfı](#registerwndsuperclass)|İçerilen pencerenin pencere sınıfını kaydeder.|
|[CContainedWindowT:: SubclassWindow](#subclasswindow)|Bir pencerenin alt sınıfları.|
|[CContainedWindowT:: SwitchMessageMap](#switchmessagemap)|İçerilen pencerenin iletilerini işlemek için kullanılan ileti eşlemesini değiştirir.|
|[CContainedWindowT:: UnsubclassWindow](#unsubclasswindow)|Daha önce bir alt sınıflı pencereyi geri yükler.|
|[CContainedWindowT:: WindowProc](#windowproc)|Se İçerilen pencereye gönderilen iletileri işler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CContainedWindowT:: m_dwMsgMapID](#m_dwmsgmapid)|Hangi ileti eşlemesinin içerilen pencerenin iletilerini işleyeceğini belirler.|
|[CContainedWindowT:: m_lpszClassName](#m_lpszclassname)|Yeni bir pencere sınıfının temel alınacağı varolan bir pencere sınıfının adını belirtir.|
|[CContainedWindowT:: m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Pencere sınıfının özgün pencere yordamını işaret eder.|
|[CContainedWindowT:: m_pObject](#m_pobject)|İçeren nesneyi işaret eder.|

## <a name="remarks"></a>Açıklamalar

`CContainedWindowT` başka bir nesne içinde yer alan bir pencere uygular. `CContainedWindowT`uygulamasının pencere yordamı, iletileri uygun işleyicilere yönlendirmek için içeren nesnede bir ileti eşlemesi kullanır. Bir nesne oluştururken `CContainedWindowT` hangi ileti haritasının kullanılması gerektiğini belirtirsiniz.

`CContainedWindowT` Varolan bir pencere sınıfını seçerek yeni bir pencere oluşturmanıza olanak sağlar. `Create`Yöntemi ilk olarak var olan bir sınıfı temel alan, ancak kullanan bir pencere sınıfını kaydeder `CContainedWindowT::WindowProc` . `Create` sonra bu yeni pencere sınıfını temel alan bir pencere oluşturur. Her bir örneği `CContainedWindowT` , farklı bir pencere sınıfını üst sınıfa ekleyebilir.

`CContainedWindowT` Ayrıca Window altsınıflama 'ı destekler. `SubclassWindow`Yöntemi, nesnesine varolan bir pencere iliştirir `CContainedWindowT` ve pencere yordamını olarak değiştirir `CContainedWindowT::WindowProc` . Her bir örneği `CContainedWindowT` farklı bir pencerenin alt sınıfını oluşturabilir.

> [!NOTE]
> Verilen herhangi bir `CContainedWindowT` nesne için ya da veya ' ı çağırın `Create` `SubclassWindow` . Aynı nesne üzerinde her iki yöntemi de çağırmamalıdır.

ATL proje sihirbazında **Denetim tabanlı Ekle** seçeneğini kullandığınızda sihirbaz, `CContainedWindowT` denetimi uygulayan sınıfa otomatik olarak bir veri üyesi ekler. Aşağıdaki örnek, içerilen pencerenin nasıl bildirildiği gösterilmektedir:

[!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]

[!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]

[!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]

|Daha fazla bilgi|Bkz.|
|--------------------------------|---------|
|Denetimler oluşturma|[ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md)|
|ATL 'de Windows kullanma|[ATL pencere sınıfları](../../atl/atl-window-classes.md)|
|ATL Proje Sihirbazı|[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)|
|Windows|Windows SDK [Windows](/windows/win32/winmsg/windows) ve sonraki konular|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`TBase`

`CContainedWindowT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="ccontainedwindowtccontainedwindowt"></a><a name="ccontainedwindowt"></a> CContainedWindowT:: CContainedWindowT

Oluşturucu veri üyelerini başlatır.

```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>
'ndaki İçerilen pencerenin temel alınacağı varolan bir pencere sınıfının adı.

*Nesnesini*<br/>
'ndaki İleti eşlemini bildiren kapsayan nesneye yönelik bir işaretçi. Bu nesnenin sınıfının [CMessageMap](../../atl/reference/cmessagemap-class.md)öğesinden türetilmesi gerekir.

*dwMsgMapID*<br/>
'ndaki İçerilen pencerenin iletilerini işleyecek ileti eşlemini tanımlar. Varsayılan değer olan 0, [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile belirtilen varsayılan ileti haritasını belirtir. [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)ile belirtilen alternatif bir ileti eşlemesini kullanmak için pass `msgMapID` .

### <a name="remarks"></a>Açıklamalar

[Oluştur](#create)aracılığıyla yeni bir pencere oluşturmak Istiyorsanız, *lpszClassName* parametresi için varolan bir pencere sınıfının adını geçirmeniz gerekir. Bir örnek için bkz. [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 'a genel bakış.

Üç Oluşturucu vardır:

- Üç bağımsız değişkene sahip Oluşturucu genellikle çağrılan bir oluşturucudur.

- İki bağımsız değişken içeren Oluşturucu, ' den sınıf adını kullanır `TBase::GetWndClassName` .

- Bağımsız değişken içermeyen Oluşturucu, daha sonra bağımsız değişkenleri sağlamak istiyorsanız kullanılır. Daha sonra çağırdığınızda pencere sınıfı adı, ileti eşleme nesnesi ve ileti eşleme KIMLIĞI sağlamalısınız `Create` .

Var olan bir pencerenin [SubclassWindow](#subclasswindow)aracılığıyla alt sınıfını oluşturursanız *lpszClassName* değeri kullanılmaz; Bu nedenle, bu parametre için NULL değeri geçirebilirsiniz.

## <a name="ccontainedwindowtcreate"></a><a name="create"></a> CContainedWindowT:: Create

Mevcut bir sınıfı temel alan ancak [CContainedWindowT:: WindowProc](#windowproc)kullanan bir pencere sınıfını kaydetmek Için [Registerwndsüper](#registerwndsuperclass) sınıfını çağırır.

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>
'ndaki İçerilen pencerenin temel alınacağı varolan bir pencere sınıfının adı.

*Nesnesini*<br/>
'ndaki İleti eşlemini bildiren kapsayan nesneye yönelik bir işaretçi. Bu nesnenin sınıfının [CMessageMap](../../atl/reference/cmessagemap-class.md)öğesinden türetilmesi gerekir.

*dwMsgMapID*<br/>
'ndaki İçerilen pencerenin iletilerini işleyecek ileti eşlemini tanımlar. Varsayılan değer olan 0, [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile belirtilen varsayılan ileti haritasını belirtir. [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)ile belirtilen alternatif bir ileti eşlemesini kullanmak için pass `msgMapID` .

*hWndParent*<br/>
'ndaki Üst veya sahip penceresi için tanıtıcı.

*Rect*<br/>
'ndaki Pencerenin konumunu belirten bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı. , `RECT` İşaretçi veya başvuru ile geçirilebilir.

*szWindowName*<br/>
'ndaki Pencerenin adını belirtir. Varsayılan değer NULL.

*dwStyle*<br/>
'ndaki Pencerenin stili. Varsayılan değer WS_CHILD &#124; WS_VISIBLE. Olası değerlerin bir listesi için Windows SDK, bkz. [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) .

*dwExStyle*<br/>
'ndaki Genişletilmiş pencere stili. Varsayılan değer 0 ' dır, anlamı genişletilmiş bir stil değildir. Olası değerler listesi için Windows SDK [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) bölümüne bakın.

*MenuOrID*<br/>
'ndaki Bir alt pencere için pencere tanımlayıcısı. Üst düzey bir pencere için, pencerenin menü tutamacı. Varsayılan değer **0u**'dir.

*lpCreateParam*<br/>
'ndaki Pencere oluşturma verilerine yönelik bir işaretçi. Tam açıklama için, [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)için son parametrenin açıklamasına bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, yeni oluşturulan pencerenin tanıtıcısı; Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Mevcut pencere sınıfı adı [m_lpszClassName](#m_lpszclassname)kaydedilir. `Create` daha sonra bu yeni sınıfa dayalı bir pencere oluşturur. Yeni oluşturulan pencere, nesnesine otomatik olarak eklenir `CContainedWindowT` .

> [!NOTE]
> `Create`Zaten [SubclassWindow](#subclasswindow)olarak adlandırdıysanız çağırmayın.

> [!NOTE]
> Eğer, *MenuOrID* parametresinin değeri olarak kullanılırsa, bir derleyici hatasından kaçınmak Için 0u (varsayılan değer) olarak belirtilmelidir.

## <a name="ccontainedwindowtdefwindowproc"></a><a name="defwindowproc"></a> CContainedWindowT::D efWindowProc

İleti eşlemesi tarafından işlenmeyen iletileri işlemek için [WindowProc](#windowproc) tarafından çağırılır.

```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*uMsg*<br/>
'ndaki Pencereye gönderilen ileti.

*wParam*<br/>
'ndaki İletiye özgü ek bilgiler.

*lParam*<br/>
'ndaki İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

İleti işlemenin sonucu.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `DefWindowProc` ileti bilgilerini [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)belirtilen pencere yordamına göndermek Için [CallWindowProc](/windows/win32/api/winuser/nf-winuser-callwindowprocw) Win32 işlevini çağırır.

## <a name="ccontainedwindowtgetcurrentmessage"></a><a name="getcurrentmessage"></a> CContainedWindowT:: GetCurrentMessage

Geçerli iletiyi () döndürür `m_pCurrentMsg` .

```
const _ATL_MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Dönüş Değeri

Yapıda paketlenmiş geçerli ileti `MSG` .

## <a name="ccontainedwindowtm_dwmsgmapid"></a><a name="m_dwmsgmapid"></a> CContainedWindowT:: m_dwMsgMapID

İçerilen pencere için kullanılmakta olan ileti eşlemesinin tanımlayıcısını tutar.

```
DWORD m_dwMsgMapID;
```

### <a name="remarks"></a>Açıklamalar

Bu ileti eşlemesi kapsayan nesnede bildirilmelidir.

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile belirtilen varsayılan ileti eşlemesi her zaman sıfır tarafından tanımlanır. [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)ile belirtilen alternatif bir ileti eşlemesi tarafından tanımlanır `msgMapID` .

`m_dwMsgMapID` İlk olarak Oluşturucu tarafından başlatılır ve [SwitchMessageMap](#switchmessagemap)çağırarak değiştirilebilir. Bir örnek için bkz. [CContainedWindowT genel bakış](../../atl/reference/ccontainedwindowt-class.md).

## <a name="ccontainedwindowtm_lpszclassname"></a><a name="m_lpszclassname"></a> CContainedWindowT:: m_lpszClassName

Varolan bir pencere sınıfının adını belirtir.

```
LPTSTR m_lpszClassName;
```

### <a name="remarks"></a>Açıklamalar

Bir pencere [oluşturduğunuzda, bu](#create) var olan sınıfa dayalı ancak [CContainedWindowT:: WindowProc](#windowproc)kullanan yeni bir pencere sınıfı kaydettirir.

`m_lpszClassName` , Oluşturucu tarafından başlatılır. Bir örnek için bkz. [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) genel bakış.

## <a name="ccontainedwindowtm_pfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a> CContainedWindowT:: m_pfnSuperWindowProc

İçerilen pencere alt sınıflandır, `m_pfnSuperWindowProc` pencere sınıfının orijinal pencere yordamına işaret eder.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Açıklamalar

İçerilen pencere, mevcut bir sınıfı değiştiren bir pencere sınıfını temel alıyorsa, var olan `m_pfnSuperWindowProc` pencere sınıfının pencere yordamını işaret eder.

[DefWindowProc](#defwindowproc) yöntemi ' de kaydedilen pencere yordamına ileti bilgilerini gönderir `m_pfnSuperWindowProc` .

## <a name="ccontainedwindowtm_pobject"></a><a name="m_pobject"></a> CContainedWindowT:: m_pObject

Nesneyi içeren nesnesine işaret eder `CContainedWindowT` .

```
CMessageMap* m_pObject;
```

### <a name="remarks"></a>Açıklamalar

Sınıfı [CMessageMap](../../atl/reference/cmessagemap-class.md)'ten türetmelidir bu kapsayıcı, içerilen pencere tarafından kullanılan ileti eşlemesini bildirir.

`m_pObject` , Oluşturucu tarafından başlatılır. Bir örnek için bkz. [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) genel bakış.

## <a name="ccontainedwindowtregisterwndsuperclass"></a><a name="registerwndsuperclass"></a> CContainedWindowT:: Registerwndsüper sınıfı

İçerilen pencerenin Window sınıfını kaydetmek için [Create](#create) tarafından çağırılır.

```
ATOM RegisterWndSuperClass();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, kayıtlı pencere sınıfını benzersiz bir şekilde tanımlayan bir atom; Aksi takdirde, sıfır.

### <a name="remarks"></a>Açıklamalar

Bu pencere sınıfı, var olan bir sınıfa dayalıdır, ancak [CContainedWindowT:: WindowProc](#windowproc)kullanır. Mevcut pencere sınıfının adı ve pencere yordamı sırasıyla [m_lpszClassName](#m_lpszclassname) ve [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)kaydedilir.

## <a name="ccontainedwindowtsubclasswindow"></a><a name="subclasswindow"></a> CContainedWindowT:: SubclassWindow

*HWND* tarafından tanımlanan pencerenin alt sınıfları ve `CContainedWindowT` nesneye iliştirir.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki Alt sınıflandırılacak pencerenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Pencere başarıyla alt sınıflandırdıysanız doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Alt sınıflı pencere artık [CContainedWindowT:: WindowProc](#windowproc)kullanır. Özgün pencere yordamı [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)kaydedilir.

> [!NOTE]
> `SubclassWindow`Zaten [Oluştur](#create)olarak adlandırdıysanız çağırmayın.

## <a name="ccontainedwindowtswitchmessagemap"></a><a name="switchmessagemap"></a> CContainedWindowT:: SwitchMessageMap

İçerilen pencerenin iletilerini işlemek için kullanılacak ileti eşlemesini değiştirir.

```cpp
void SwitchMessageMap(DWORD dwMsgMapID);
```

### <a name="parameters"></a>Parametreler

*dwMsgMapID*<br/>
'ndaki İleti eşleme tanımlayıcısı. [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile belirtilen varsayılan ileti eşlemesini kullanmak için sıfır geçirin. [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)ile belirtilen alternatif bir ileti eşlemesini kullanmak için pass `msgMapID` .

### <a name="remarks"></a>Açıklamalar

İleti eşlemesi kapsayan nesnede tanımlanmalıdır.

İlk olarak oluşturucuda ileti eşleme tanımlayıcısını belirtirsiniz.

## <a name="ccontainedwindowtunsubclasswindow"></a><a name="unsubclasswindow"></a> CContainedWindowT:: UnsubclassWindow

Nesnenin alt sınıf penceresini ayırır `CContainedWindowT` ve [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)kaydedilir ve özgün pencere yordamını geri yükler.

```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```

### <a name="parameters"></a>Parametreler

*Bzorla*<br/>
'ndaki Bu nesnenin pencere yordamı Şu anda etkin olmasa bile özgün pencere yordamını geri yüklemeye zorlamak için TRUE olarak ayarlayın `CContainedWindowT` . *Bzorlamalı* değeri false olarak ayarlandıysa ve bu nesnenin pencere yordamı `CContainedWindowT` Şu anda etkin değilse, özgün pencere yordamı geri yüklenmez.

### <a name="return-value"></a>Dönüş Değeri

Pencerenin daha önce alt sınıflandırılacak olan işleyici. *Bzorlamalı* değeri false olarak ayarlandıysa ve bu nesnenin pencere yordamı `CContainedWindowT` Şu anda ETKIN değilse, null değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca pencere yok edileceği orijinal pencere yordamını geri yüklemek istiyorsanız kullanın. Aksi halde pencere yok edildiğinde [WindowProc](#windowproc) bunu otomatik olarak olur.

## <a name="ccontainedwindowtwindowproc"></a><a name="windowproc"></a> CContainedWindowT:: WindowProc

Bu statik yöntem pencere yordamını uygular.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki Pencerenin tutamacı.

*uMsg*<br/>
'ndaki Pencereye gönderilen ileti.

*wParam*<br/>
'ndaki İletiye özgü ek bilgiler.

*lParam*<br/>
'ndaki İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

İleti işlemenin sonucu.

### <a name="remarks"></a>Açıklamalar

`WindowProc` iletileri [m_dwMsgMapID](#m_dwmsgmapid)tarafından tanımlanan ileti eşlemesine yönlendirir. Gerekirse, `WindowProc` ek ileti işleme Için [DefWindowProc](#defwindowproc) çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[CWindow sınıfı](../../atl/reference/cwindow-class.md)<br/>
[CWindowImpl sınıfı](../../atl/reference/cwindowimpl-class.md)<br/>
[CMessageMap sınıfı](../../atl/reference/cmessagemap-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
