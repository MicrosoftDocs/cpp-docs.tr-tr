---
title: CContainedWindowT Sınıfı
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
ms.openlocfilehash: cde9c73a195303e57758cb4f27184b5136bdaf14
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327211"
---
# <a name="ccontainedwindowt-class"></a>CContainedWindowT Sınıfı

Bu sınıf başka bir nesne içinde bulunan bir pencere uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>
class CContainedWindowT : public TBase
```

#### <a name="parameters"></a>Parametreler

*TBase*<br/>
Yeni sınıfının taban sınıfı. Varsayılan taban sınıf. `CWindow`

*TwinTraits*<br/>
Pencerenizin stillerini tanımlayan özellikler sınıfı. Varsayılan değer: `CControlWinTraits`.

> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) bir uzmanlık `CContainedWindowT`alanıdır. Taban sınıfı veya özellikleri değiştirmek istiyorsanız, `CContainedWindowT` doğrudan kullanın.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CcontainedWindowT::ccontainedwindowt](#ccontainedwindowt)|Oluşturucu. Hangi ileti eşlerinin içerdiği pencerenin iletilerini işleyecek lerini belirtmek için veri üyelerini başlatılmasını.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CContainedWindowT::Oluştur](#create)|Bir pencere oluşturur.|
|[CContainedWindowT::DefWindowProc](#defwindowproc)|Varsayılan ileti işleme sağlar.|
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|Geçerli iletiyi döndürür.|
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|İçerdiği pencerenin pencere sınıfını kaydeder.|
|[CContainedWindowT::Alt SınıfPenceresi](#subclasswindow)|Alt sınıflar bir pencere.|
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|İçerdiği pencerenin iletilerini işlemek için hangi ileti eşleminin kullanıldığını değiştirir.|
|[CContainedWindowT::Alt Sınıf Penceresi](#unsubclasswindow)|Daha önce alt sınıflanmış bir pencereyi geri yükler.|
|[CContainedWindowT::WindowProc](#windowproc)|(Statik) İçerdiği pencereye gönderilen iletileri işler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|Hangi ileti haritasının içerdiği pencerenin iletilerini işleyecek lerini tanımlar.|
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|Yeni bir pencere sınıfının temel alınacağı varolan bir pencere sınıfının adını belirtir.|
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Pencere sınıfının özgün pencere yordamını işaret eder.|
|[CContainedWindowT::m_pObject](#m_pobject)|İçeren nesneyi işaret eder.|

## <a name="remarks"></a>Açıklamalar

`CContainedWindowT`başka bir nesne içinde bulunan bir pencere uygular. `CContainedWindowT`'S pencere yordamı, iletileri uygun işleyicilere yönlendirmek için içeren nesnede bir ileti eşlemi kullanır. Bir `CContainedWindowT` nesne oluştururken, hangi ileti eşleminin kullanılması gerektiğini belirtirsiniz.

`CContainedWindowT`varolan bir pencere sınıfını üst sınıfa ekleyerek yeni bir pencere oluşturmanıza olanak tanır. Yöntem `Create` ilk olarak varolan bir sınıfa dayalı ancak `CContainedWindowT::WindowProc`kullanan bir pencere sınıfını kaydeder. `Create`sonra bu yeni pencere sınıfına dayalı bir pencere oluşturur. Her örnek `CContainedWindowT` farklı bir pencere sınıfı üst sınıf olabilir.

`CContainedWindowT`pencere alt sınıflandırmayı da destekler. Yöntem `SubclassWindow` nesneye `CContainedWindowT` varolan bir pencere bağlar ve `CContainedWindowT::WindowProc`pencere yordamını . Her örneği `CContainedWindowT` farklı bir pencere alt sınıfolabilir.

> [!NOTE]
> Belirli bir `CContainedWindowT` nesne için, `SubclassWindow`ya da `Create` . Her iki yöntemi de aynı nesne üzerinde çağırmamalısınız.

ATL Project Sihirbazı'ndaki seçeneği **temel alan Ekle denetimini** kullandığınızda, sihirbaz denetimi uygulayan sınıfa otomatik olarak bir `CContainedWindowT` veri üyesi ekler. Aşağıdaki örnek, içerdiği pencerenin nasıl beyan edildiğigöster:

[!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]

[!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]

[!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]

|Daha fazla bilgi|Bkz.|
|--------------------------------|---------|
|Denetim oluşturma|[ATL Öğretici](../../atl/active-template-library-atl-tutorial.md)|
|ATL'de pencereleri kullanma|[ATL Pencere Sınıfları](../../atl/atl-window-classes.md)|
|ATL Proje Sihirbazı|[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)|
|Windows|[Windows](/windows/win32/winmsg/windows) SDK'daki Windows ve sonraki konular|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`TBase`

`CContainedWindowT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="ccontainedwindowtccontainedwindowt"></a><a name="ccontainedwindowt"></a>CcontainedWindowT::ccontainedwindowt

Oluşturucu veri üyelerini başlatılmasını ister.

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
[içinde] İçerdiği pencerenin temel alınacağı varolan bir pencere sınıfının adı.

*Pobject*<br/>
[içinde] İleti eşlesini bildiren içeren nesneye işaretçi. Bu nesnenin sınıfı [CMessageMap](../../atl/reference/cmessagemap-class.md)türemelisiniz.

*dwMsgMapID*<br/>
[içinde] İçerdiği pencerenin iletilerini işleyecek ileti eşlemi tanımlar. Varsayılan değer olan 0, [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile bildirilen varsayılan ileti eşleğini belirtir. [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)ile bildirilen alternatif bir ileti `msgMapID`haritası kullanmak için , geç .

### <a name="remarks"></a>Açıklamalar

[Oluştur](#create)üzerinden yeni bir pencere oluşturmak istiyorsanız, *lpszClassName* parametresi için varolan bir pencere sınıfının adını geçirmeniz gerekir. Örneğin, [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) genel görünümüne bakın.

Üç yapıcı vardır:

- Üç bağımsız değişkenli yapıcı genellikle denir.

- İki bağımsız değişkenli oluşturucu sınıf `TBase::GetWndClassName`adını kullanır.

- Bağımsız değişkenleri daha sonra sağlamak istiyorsanız, bağımsız değişkenleri olmayan oluşturucu kullanılır. Daha sonra aradığınızda `Create`pencere sınıf adını, ileti eşlemi nesnesini ve ileti eşlemi kimliğini sağlamanız gerekir.

Varolan bir pencereyi [Alt ClassWindow'dan](#subclasswindow)alt sınıfa çıkarırsanız, *lpszClassName* değeri kullanılmaz; bu nedenle, bu parametre için NULL geçirebilirsiniz.

## <a name="ccontainedwindowtcreate"></a><a name="create"></a>CContainedWindowT::Oluştur

Varolan bir sınıfa dayalı bir pencere sınıfı kaydetmek için [RegisterWndSuperclass](#registerwndsuperclass) çağırır ama [CContainedWindowT kullanır::WindowProc](#windowproc).

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
[içinde] İçerdiği pencerenin temel alınacağı varolan bir pencere sınıfının adı.

*Pobject*<br/>
[içinde] İleti eşlesini bildiren içeren nesneye işaretçi. Bu nesnenin sınıfı [CMessageMap](../../atl/reference/cmessagemap-class.md)türemelisiniz.

*dwMsgMapID*<br/>
[içinde] İçerdiği pencerenin iletilerini işleyecek ileti eşlemi tanımlar. Varsayılan değer olan 0, [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile bildirilen varsayılan ileti eşleğini belirtir. [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)ile bildirilen alternatif bir ileti `msgMapID`haritası kullanmak için , geç .

*hWndParent*<br/>
[içinde] Üst veya sahip penceresine tanıtıcı.

*Rect*<br/>
[içinde] Pencerenin konumunu belirten bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısı. İşaretçi `RECT` veya başvuru ile geçirilebilir.

*szWindowName*<br/>
[içinde] Pencerenin adını belirtir. Varsayılan değer NULL'dur.

*Dwstyle*<br/>
[içinde] Pencerenin stili. Varsayılan değer WS_CHILD &#124; WS_VISIBLE. Olası değerlerin listesi için Windows SDK'daki [Create Window'a](/windows/win32/api/winuser/nf-winuser-createwindoww) bakın.

*dwExStyle*<br/>
[içinde] Genişletilmiş pencere stili. Varsayılan değer 0'dır, yani genişletilmiş stil yoktur. Olası değerlerin listesi için Windows SDK'daki [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) bölümüne bakın.

*MenuOrID*<br/>
[içinde] Bir alt pencere için, pencere tanımlayıcısı. Üst düzey bir pencere için, pencere için bir menü tutamacı. Varsayılan değer **0U'dur.**

*lpCreateParam*<br/>
[içinde] Pencere oluşturma verileri için bir işaretçi. Tam bir açıklama için [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)için son parametrenin açıklamasına bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, yeni oluşturulan pencerenin tutamacı; aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Varolan pencere sınıfı adı [m_lpszClassName](#m_lpszclassname)kaydedilir. `Create`sonra bu yeni sınıfa dayalı bir pencere oluşturur. Yeni oluşturulan pencere nesneye `CContainedWindowT` otomatik olarak eklenir.

> [!NOTE]
> `Create` [SubclassWindow'u](#subclasswindow)zaten aradıysanız aramayın.

> [!NOTE]
> *MenuOrID* parametresi için değer olarak 0 kullanılırsa, derleyici hatasını önlemek için 0U (varsayılan değer) olarak belirtilmelidir.

## <a name="ccontainedwindowtdefwindowproc"></a><a name="defwindowproc"></a>CContainedWindowT::DefWindowProc

İleti haritası tarafından işlenmemiş iletileri işlemek için [WindowProc](#windowproc) tarafından çağrılır.

```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*uMsg*<br/>
[içinde] Pencereye gönderilen ileti.

*Wparam*<br/>
[içinde] İletiye özgü ek bilgiler.

*Lparam*<br/>
[içinde] İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

İleti işleme sonucu.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `DefWindowProc` [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)belirtilen pencere yordamına ileti bilgilerini göndermek için [CallWindowProc](/windows/win32/api/winuser/nf-winuser-callwindowprocw) Win32 işlevini çağırır.

## <a name="ccontainedwindowtgetcurrentmessage"></a><a name="getcurrentmessage"></a>CContainedWindowT::GetCurrentMessage

Geçerli iletiyi`m_pCurrentMsg`döndürür ( ).

```
const _ATL_MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli ileti, `MSG` yapıda paketlenmiş.

## <a name="ccontainedwindowtm_dwmsgmapid"></a><a name="m_dwmsgmapid"></a>CContainedWindowT::m_dwMsgMapID

İçerdiği pencere için şu anda kullanılmakta olan ileti haritasının tanımlayıcısını tutar.

```
DWORD m_dwMsgMapID;
```

### <a name="remarks"></a>Açıklamalar

Bu ileti eşlemi içeren nesnede bildirilmelidir.

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile bildirilen varsayılan ileti eşlemi her zaman sıfırla tanımlanır. [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)ile bildirilen alternatif bir ileti `msgMapID`haritası tanımlanır.

`m_dwMsgMapID`ilk olarak oluşturucu tarafından başharfe çevrilir ve [SwitchMessageMap'i](#switchmessagemap)arayarak değiştirilebilir. Örneğin, [CContainedWindowT Genel Bakış'a](../../atl/reference/ccontainedwindowt-class.md)bakın.

## <a name="ccontainedwindowtm_lpszclassname"></a><a name="m_lpszclassname"></a>CContainedWindowT::m_lpszClassName

Varolan bir pencere sınıfının adını belirtir.

```
LPTSTR m_lpszClassName;
```

### <a name="remarks"></a>Açıklamalar

Bir pencere oluşturduğunuzda, [Create](#create) bu varolan sınıfa dayalı yeni bir pencere sınıfı kaydeder ancak [CContainedWindowT kullanır::WindowProc](#windowproc).

`m_lpszClassName`oluşturucu tarafından başharfe çevrilir. Örneğin, [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) genel görünümüne bakın.

## <a name="ccontainedwindowtm_pfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a>CContainedWindowT::m_pfnSuperWindowProc

İçerdiği pencere alt sınıfa aitse, `m_pfnSuperWindowProc` pencere sınıfının özgün pencere yordamını işaret edin.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Açıklamalar

İçerdiği pencere üst sınıfa sahipse, yani varolan bir sınıfı `m_pfnSuperWindowProc` değiştiren bir pencere sınıfına dayanır, varolan pencere sınıfının pencere yordamını işaret eder.

[DefWindowProc](#defwindowproc) yöntemi kaydedilen pencere yordamına `m_pfnSuperWindowProc`ileti bilgileri gönderir.

## <a name="ccontainedwindowtm_pobject"></a><a name="m_pobject"></a>CContainedWindowT::m_pObject

Nesneyi içeren nesneyi işaret eder. `CContainedWindowT`

```
CMessageMap* m_pObject;
```

### <a name="remarks"></a>Açıklamalar

Sınıfı [CMessageMap'ten](../../atl/reference/cmessagemap-class.md)türemesi gereken bu kapsayıcı, içerdiği pencere tarafından kullanılan ileti eşlemi bildirir.

`m_pObject`oluşturucu tarafından başharfe çevrilir. Örneğin, [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) genel görünümüne bakın.

## <a name="ccontainedwindowtregisterwndsuperclass"></a><a name="registerwndsuperclass"></a>CContainedWindowT::RegisterWndSuperclass

İçerdiği pencerenin pencere sınıfını kaydetmek için [Create](#create) tarafından çağrıldı.

```
ATOM RegisterWndSuperClass();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, kayıtlı olan pencere sınıfını benzersiz olarak tanımlayan bir atom; aksi takdirde, sıfır.

### <a name="remarks"></a>Açıklamalar

Bu pencere sınıfı varolan bir sınıfa dayanır, ancak [CContainedWindowT kullanır::WindowProc](#windowproc). Varolan pencere sınıfının adı ve pencere yordamı sırasıyla [m_lpszClassName](#m_lpszclassname) ve [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)kaydedilir.

## <a name="ccontainedwindowtsubclasswindow"></a><a name="subclasswindow"></a>CContainedWindowT::Alt SınıfPenceresi

*HWnd* tarafından tanımlanan pencereyi alt sınıflar `CContainedWindowT` ve nesneye bağlar.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
[içinde] Pencerenin tutamacı alt sınıflandı.

### <a name="return-value"></a>Dönüş Değeri

Pencere başarıyla alt sınıflanmışsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Alt sınıflı pencere artık [CContainedWindowT kullanır::WindowProc](#windowproc). Özgün pencere yordamı [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)kaydedilir.

> [!NOTE]
> Oluştur'u `SubclassWindow` zaten aradıysanız [Create](#create)aramayın.

## <a name="ccontainedwindowtswitchmessagemap"></a><a name="switchmessagemap"></a>CContainedWindowT::SwitchMessageMap

İçerdiği pencerenin iletilerini işlemek için hangi ileti eşleminin kullanılacağını değiştirir.

```
void SwitchMessageMap(DWORD dwMsgMapID);
```

### <a name="parameters"></a>Parametreler

*dwMsgMapID*<br/>
[içinde] İleti eşlemi tanımlayıcısı. [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile bildirilen varsayılan ileti eşlemi kullanmak için sıfırı geç. [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)ile bildirilen alternatif bir ileti `msgMapID`haritası kullanmak için , geç .

### <a name="remarks"></a>Açıklamalar

İleti eşlemi içeren nesnede tanımlanmalıdır.

Başlangıçta oluşturucuda ileti eşlemi tanımlayıcısını belirtirsiniz.

## <a name="ccontainedwindowtunsubclasswindow"></a><a name="unsubclasswindow"></a>CContainedWindowT::Alt Sınıf Penceresi

Alt sınıflanmış pencereyi `CContainedWindowT` nesneden ayırır ve [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)kaydedilen özgün pencere yordamını geri yükler.

```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```

### <a name="parameters"></a>Parametreler

*bKuvvet*<br/>
[içinde] Bu `CContainedWindowT` nesnenin pencere yordamı şu anda etkin olmasa bile özgün pencere yordamını geri yüklenecek zorlamak için TRUE olarak ayarlayın. *bForce* FALSE olarak ayarlanmışsa ve `CContainedWindowT` bu nesnenin pencere yordamı şu anda etkin değilse, özgün pencere yordamı geri yüklenmez.

### <a name="return-value"></a>Dönüş Değeri

Pencerenin tutamacı daha önce alt sınıflanmış. *bForce* FALSE olarak ayarlanmışsa ve `CContainedWindowT` bu nesnenin pencere yordamı şu anda etkin değilse NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca pencere yok edilmeden önce özgün pencere yordamını geri yüklemek istiyorsanız kullanın. Aksi takdirde, [WindowProc](#windowproc) pencere yok edildiğinde bunu otomatik olarak yapar.

## <a name="ccontainedwindowtwindowproc"></a><a name="windowproc"></a>CContainedWindowT::WindowProc

Bu statik yöntem pencere yordamını uygular.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
[içinde] Pencerenin sapı.

*uMsg*<br/>
[içinde] Pencereye gönderilen ileti.

*Wparam*<br/>
[içinde] İletiye özgü ek bilgiler.

*Lparam*<br/>
[içinde] İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

İleti işleme sonucu.

### <a name="remarks"></a>Açıklamalar

`WindowProc`İletileri [m_dwMsgMapID](#m_dwmsgmapid)tarafından tanımlanan ileti haritasına yönlendirir. Gerekirse, `WindowProc` ek ileti işleme için [DefWindowProc'u](#defwindowproc) arar.

## <a name="see-also"></a>Ayrıca bkz.

[CWindow Sınıfı](../../atl/reference/cwindow-class.md)<br/>
[CWindowImpl Sınıfı](../../atl/reference/cwindowimpl-class.md)<br/>
[CMessageMap Sınıfı](../../atl/reference/cmessagemap-class.md)<br/>
[Begın_msg_map](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
