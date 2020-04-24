---
title: CPagerCtrl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPagerCtrl
- AFXCMN/CPagerCtrl
- AFXCMN/CPagerCtrl::CPagerCtrl
- AFXCMN/CPagerCtrl::Create
- AFXCMN/CPagerCtrl::CreateEx
- AFXCMN/CPagerCtrl::ForwardMouse
- AFXCMN/CPagerCtrl::GetBkColor
- AFXCMN/CPagerCtrl::GetBorder
- AFXCMN/CPagerCtrl::GetButtonSize
- AFXCMN/CPagerCtrl::GetButtonState
- AFXCMN/CPagerCtrl::GetDropTarget
- AFXCMN/CPagerCtrl::GetScrollPos
- AFXCMN/CPagerCtrl::IsButtonDepressed
- AFXCMN/CPagerCtrl::IsButtonGrayed
- AFXCMN/CPagerCtrl::IsButtonHot
- AFXCMN/CPagerCtrl::IsButtonInvisible
- AFXCMN/CPagerCtrl::IsButtonNormal
- AFXCMN/CPagerCtrl::RecalcSize
- AFXCMN/CPagerCtrl::SetBkColor
- AFXCMN/CPagerCtrl::SetBorder
- AFXCMN/CPagerCtrl::SetButtonSize
- AFXCMN/CPagerCtrl::SetChild
- AFXCMN/CPagerCtrl::SetScrollPos
helpviewer_keywords:
- CPagerCtrl [MFC], CPagerCtrl
- CPagerCtrl [MFC], Create
- CPagerCtrl [MFC], CreateEx
- CPagerCtrl [MFC], ForwardMouse
- CPagerCtrl [MFC], GetBkColor
- CPagerCtrl [MFC], GetBorder
- CPagerCtrl [MFC], GetButtonSize
- CPagerCtrl [MFC], GetButtonState
- CPagerCtrl [MFC], GetDropTarget
- CPagerCtrl [MFC], GetScrollPos
- CPagerCtrl [MFC], IsButtonDepressed
- CPagerCtrl [MFC], IsButtonGrayed
- CPagerCtrl [MFC], IsButtonHot
- CPagerCtrl [MFC], IsButtonInvisible
- CPagerCtrl [MFC], IsButtonNormal
- CPagerCtrl [MFC], RecalcSize
- CPagerCtrl [MFC], SetBkColor
- CPagerCtrl [MFC], SetBorder
- CPagerCtrl [MFC], SetButtonSize
- CPagerCtrl [MFC], SetChild
- CPagerCtrl [MFC], SetScrollPos
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
ms.openlocfilehash: cd27a3acf26abe39831089546df317679f2ecab6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753708"
---
# <a name="cpagerctrl-class"></a>CPagerCtrl Sınıfı

Sınıf, `CPagerCtrl` içerdiği pencereye uymayan bir pencereyi görüntülemek için kaydırabilirsiniz Windows çağrı cihazı denetimini sarar.

## <a name="syntax"></a>Sözdizimi

```
class CPagerCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPagerCtrl::CPagerCtrl](#cpagerctrl)|Bir `CPagerCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPagerCtrl::Oluştur](#create)|Belirtilen stilleri içeren bir çağrı cihazı denetimi oluşturur `CPagerCtrl` ve geçerli nesneye bağlar.|
|[CPagerCtrl::CreateEx](#createex)|Belirtilen genişletilmiş stilleri içeren bir çağrı cihazı denetimi oluşturur `CPagerCtrl` ve geçerli nesneye bağlar.|
|[CPagerCtrl::İleri Fare](#forwardmouse)|[İletileri](/windows/win32/inputdev/wm-mousemove) geçerli çağrı cihazı denetiminde bulunan pencereye WM_MOUSEMOVE iletmeyi etkinleştirer veya devre dışı kılabilir.|
|[CPagerCtrl::GetBkColor](#getbkcolor)|Geçerli çağrı cihazı denetiminin arka plan rengini alır.|
|[CPagerCtrl::GetBorder](#getborder)|Geçerli çağrı cihazı denetiminin kenarlık boyutunu alır.|
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|Geçerli çağrı cihazı denetiminin düğme boyutunu alır.|
|[CPagerCtrl::GetButtonState](#getbuttonstate)|Geçerli çağrı cihazı denetiminde belirtilen düğmenin durumunu alır.|
|[CPagerCtrl::GetDropTarget](#getdroptarget)|Geçerli çağrı cihazı denetimi için [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) arabirimini alır.|
|[CPagerCtrl::GetScrollPos](#getscrollpos)|Geçerli çağrı cihazı denetiminin kaydırma konumunu alır.|
|[CPagerCtrl::IsButtonDepressed](#isbuttondepressed)|Geçerli çağrı cihazı denetiminin belirtilen düğmesinin `pressed` durumda olup olmadığını gösterir.|
|[CPagerCtrl::IsButtonGrayed](#isbuttongrayed)|Geçerli çağrı cihazı denetiminin belirtilen düğmesinin `grayed` durumda olup olmadığını gösterir.|
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|Geçerli çağrı cihazı denetiminin belirtilen düğmesinin `hot` durumda olup olmadığını gösterir.|
|[CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)|Geçerli çağrı cihazı denetiminin belirtilen düğmesinin `invisible` durumda olup olmadığını gösterir.|
|[CPagerCtrl::IsButtonNormal](#isbuttonnormal)|Geçerli çağrı cihazı denetiminin belirtilen düğmesinin `normal` durumda olup olmadığını gösterir.|
|[CPagerCtrl::RecalcSize](#recalcsize)|Geçerli çağrı cihazı denetiminin, içerdiği pencerenin boyutunu yeniden hesaplamasına neden olur.|
|[CPagerCtrl::SetBkColor](#setbkcolor)|Geçerli çağrı cihazı denetiminin arka plan rengini ayarlar.|
|[CPagerCtrl::SetBorder](#setborder)|Geçerli çağrı cihazı denetiminin kenarlık boyutunu ayarlar.|
|[CPagerCtrl::SetButtonSize](#setbuttonsize)|Geçerli çağrı cihazı denetiminin düğme boyutunu ayarlar.|
|[CPagerCtrl::SetChild](#setchild)|Geçerli çağrı cihazı denetimi için içerdiği pencereyi ayarlar.|
|[CPagerCtrl::SetScrollPos](#setscrollpos)|Geçerli çağrı cihazı denetiminin kaydırma konumunu ayarlar.|

## <a name="remarks"></a>Açıklamalar

Çağrı cihazı denetimi, doğrusal ve içerdiği pencereden daha büyük başka bir pencere içeren ve içerdiği pencereyi görünüme kaydırmanızı sağlayan bir penceredir. Çağrı cihazı denetimi, içerdiği pencere en uzak ölçüde kaydırıldığında otomatik olarak kaybolan iki kaydırma düğmesi görüntüler ve aksi takdirde yeniden görünür. Yatay veya dikey olarak kaydırılabilen bir çağrı cihazı denetimi oluşturabilirsiniz.

Örneğin, uygulamanızda tüm öğelerini gösterecek kadar geniş olmayan bir araç çubuğu varsa, araç çubuğunu bir çağrı cihazı denetimine atayabilirsiniz ve kullanıcılar tüm öğelere erişmek için araç çubuğunu sola veya sağa kaydırabilir. Microsoft Internet Explorer Sürüm 4.0 (commctrl.dll sürüm 4.71) çağrı cihazı denetimini sunar.

Sınıf `CPagerCtrl` [CWnd](../../mfc/reference/cwnd-class.md) sınıfından türetilmiştir. Daha fazla bilgi ve çağrı cihazı denetiminin bir örneği için [Çağrı Cihazı Denetimleri](/windows/win32/Controls/pager-controls)bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CPagerCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="cpagerctrlcpagerctrl"></a><a name="cpagerctrl"></a>CPagerCtrl::CPagerCtrl

Bir `CPagerCtrl` nesne inşa eder.

```
CPagerCtrl();
```

### <a name="remarks"></a>Açıklamalar

Çağrı cihazı denetimi oluşturmak ve nesneye takmak için [CPagerCtrl::Create](#create) veya [CPagerCtrl::CreateEx](#createex) yöntemini `CPagerCtrl` kullanın.

## <a name="cpagerctrlcreate"></a><a name="create"></a>CPagerCtrl::Oluştur

Belirtilen stilleri içeren bir çağrı cihazı denetimi oluşturur `CPagerCtrl` ve geçerli nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Dwstyle*|[içinde] Denetime uygulanacak [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [çağrı cihazı denetim stillerinin](/windows/win32/Controls/pager-control-styles) bitwise kombinasyonu (VEYA).|
|*Rect*|[içinde] İstemci koordinatlarında denetimin konumunu ve boyutunu içeren bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.|
|*pParentWnd*|[içinde] Denetimin ana penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine işaretçi. Bu parametre NULL olamaz.|
|*Nıd*|[içinde] Kontrol kimliği.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Çağrı cihazı denetimi oluşturmak için `CPagerCtrl` bir değişken bildirin ve ardından [CPagerCtrl'yi arayın::Bu](#create) değişkende CreateEx yöntemini oluşturun [veya CPagerCtrl::CreateEx](#createex) yöntemini oluşturun.

### <a name="example"></a>Örnek

Aşağıdaki örnek bir çağrı cihazı denetimi oluşturur, ardından çağrı cihazı denetimi ile çok uzun bir düğme denetimini ilişkilendirmek için [CPagerCtrl::SetChild](#setchild) yöntemini kullanır. Örnek daha sonra çağrı cihazı denetiminin yüksekliğini 20 piksele ayarlamak için [CPagerCtrl::SetButtonSize](#setbuttonsize) yöntemini kullanır ve kenarlık kalınlığını 1 piksele ayarlamak için [CPagerCtrl::SetBorder](#setborder) yöntemi.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlcreateex"></a><a name="createex"></a>CPagerCtrl::CreateEx

Belirtilen genişletilmiş stilleri içeren bir çağrı cihazı denetimi oluşturur `CPagerCtrl` ve geçerli nesneye bağlar.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*dwExStyle*|[içinde] Denetime uygulanacak genişletilmiş stillerin bitwise kombinasyonu. Daha fazla bilgi için [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) işlevinin *dwExStyle* parametresini görün.|
|*Dwstyle*|[içinde] Denetime uygulanacak [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [çağrı cihazı denetim stillerinin](/windows/win32/Controls/pager-control-styles) bitwise kombinasyonu (VEYA).|
|*Rect*|[içinde] İstemci koordinatlarında denetimin konumunu ve boyutunu içeren bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.|
|*pParentWnd*|[içinde] Denetimin ana penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine işaretçi. Bu parametre NULL olamaz.|
|*Nıd*|[içinde] Kontrol kimliği.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Çağrı cihazı denetimi oluşturmak için `CPagerCtrl` bir değişken bildirin ve ardından [CPagerCtrl'yi arayın::Bu](#create) değişkende CreateEx yöntemini oluşturun [veya CPagerCtrl::CreateEx](#createex) yöntemini oluşturun.

## <a name="cpagerctrlforwardmouse"></a><a name="forwardmouse"></a>CPagerCtrl::İleri Fare

[İletileri](/windows/win32/inputdev/wm-mousemove) geçerli çağrı cihazı denetiminde bulunan pencereye WM_MOUSEMOVE iletmeyi etkinleştirer veya devre dışı kılabilir.

```cpp
void ForwardMouse(BOOL bForward);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*bForward*|[içinde] Fare iletilerini iletmek için TRUE veya fare iletilerini iletmemek için FALSE.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_FORWARDMOUSE](/windows/win32/Controls/pgm-forwardmouse) iletisini gönderir.

## <a name="cpagerctrlgetborder"></a><a name="getborder"></a>CPagerCtrl::GetBorder

Geçerli çağrı cihazı denetiminin kenarlık boyutunu alır.

```
int GetBorder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kenarlık boyutu, piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_GETBORDER](/windows/win32/Controls/pgm-getborder) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, çağrı cihazı denetiminin kenarlığı kalınlığını almak için [CPagerCtrl::GetBorder](#getborder) yöntemi kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]

## <a name="cpagerctrlgetbkcolor"></a><a name="getbkcolor"></a>CPagerCtrl::GetBkColor

Geçerli çağrı cihazı denetiminin arka plan rengini alır.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çağrı cihazı denetiminin geçerli arka plan rengini içeren bir [COLORREF](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_GETBKCOLOR](/windows/win32/Controls/pgm-getbkcolor) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, çağrı cihazı denetiminin arka plan rengini kırmızıya ayarlamak için [CPagerCtrl::SetBkColor](#setbkcolor) yöntemi ve değişikliğin yapıldığını doğrulamak için [CPagerKColor](#getbkcolor) yöntemi kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

## <a name="cpagerctrlgetbuttonsize"></a><a name="getbuttonsize"></a>CPagerCtrl::GetButtonSize

Geçerli çağrı cihazı denetiminin düğme boyutunu alır.

```
int GetButtonSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli düğme boyutu, piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_GETBUTTONSIZE](/windows/win32/Controls/pgm-getbuttonsize) iletigönderir.

Çağrı cihazı denetimi PGS_HORZ stiline sahipse, düğme boyutu çağrı cihazı düğmelerinin genişliğini belirler ve çağrı cihazı denetimi PGS_VERT stiline sahipse, düğme boyutu çağrı cihazı düğmelerinin yüksekliğini belirler. Daha fazla bilgi için [Çağrı Cihazı Denetim Stilleri'ne](/windows/win32/Controls/pager-control-styles)bakın.

## <a name="cpagerctrlgetbuttonstate"></a><a name="getbuttonstate"></a>CPagerCtrl::GetButtonState

Geçerli çağrı cihazı denetiminde belirtilen kaydırma düğmesinin durumunu alır.

```
DWORD GetButtonState(int iButton) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButton*|[içinde] Durum alınacağı düğmeyi gösterir. Çağrı cihazı denetim stili PGS_HORZ, sol düğme için PGB_TOPORLEFT belirtin ve sağ düğme için PGB_BOTTOMORRIGHT. Çağrı cihazı denetim stili PGS_VERT ise, üst düğme için PGB_TOPORLEFT belirtin ve alt düğme için PGB_BOTTOMORRIGHT. Daha fazla bilgi için [Çağrı Cihazı Denetim Stilleri'ne](/windows/win32/Controls/pager-control-styles)bakın.|

### <a name="return-value"></a>Dönüş Değeri

*iButton* parametresi tarafından belirtilen düğmenin durumu. Devlet ya PGF_INVISIBLE, PGF_NORMAL, PGF_GRAYED, PGF_DEPRESSED, ya da PGF_HOT. Daha fazla bilgi için [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisinin İade Değeri bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisini gönderir.

## <a name="cpagerctrlgetdroptarget"></a><a name="getdroptarget"></a>CPagerCtrl::GetDropTarget

Geçerli çağrı cihazı denetimi için [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) arabirimini alır.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli çağrı `IDropTarget` cihazı denetimi için arabirime işaretçi.

### <a name="remarks"></a>Açıklamalar

`IDropTarget`uygulamanızda sürükle ve bırak işlemlerini desteklemek için uyguladığınız arabirimlerden biridir.

Bu yöntem, Windows SDK'da açıklanan [PGM_GETDROPTARGET](/windows/win32/Controls/pgm-getdroptarget) iletisini gönderir. Bu yöntemin arayan arabirimi `Release` artık gerekli olduğunda [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) arabiriminin üyesini aramak için sorumludur.

## <a name="cpagerctrlgetscrollpos"></a><a name="getscrollpos"></a>CPagerCtrl::GetScrollPos

Geçerli çağrı cihazı denetiminin kaydırma konumunu alır.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kaydırma konumu, piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_GETPOS](/windows/win32/Controls/pgm-getpos) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, çağrı cihazı denetiminin geçerli kaydırma konumunu almak için [CPagerCtrl::GetScrollPos](#getscrollpos) yöntemi ni kullanır. Çağrı cihazı denetimi zaten sıfıra, en sol konuma kaydırılmazsa, örnek kaydırma konumunu sıfıra ayarlamak için [CPagerCtrl::SetScrollPos](#setscrollpos) yöntemini kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]

## <a name="cpagerctrlisbuttondepressed"></a><a name="isbuttondepressed"></a>CPagerCtrl::IsButtonDepressed

Geçerli çağrı cihazı denetiminin belirtilen kaydırma düğmesinin basılı durumda olup olmadığını gösterir.

```
BOOL IsButtonDepressed(int iButton) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButton*|[içinde] Durum alınacağı düğmeyi gösterir. Çağrı cihazı denetim stili PGS_HORZ, sol düğme için PGB_TOPORLEFT belirtin ve sağ düğme için PGB_BOTTOMORRIGHT. Çağrı cihazı denetim stili PGS_VERT ise, üst düğme için PGB_TOPORLEFT belirtin ve alt düğme için PGB_BOTTOMORRIGHT. Daha fazla bilgi için [Çağrı Cihazı Denetim Stilleri'ne](/windows/win32/Controls/pager-control-styles)bakın.|

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğme basılı durumdaysa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisini gönderir. Daha sonra döndürülen durum PGF_DEPRESSED olup olmadığını test edin. Daha fazla bilgi için [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisinin İade Değeri bölümüne bakın.

## <a name="cpagerctrlisbuttongrayed"></a><a name="isbuttongrayed"></a>CPagerCtrl::IsButtonGrayed

Geçerli çağrı cihazı denetiminin belirtilen kaydırma düğmesinin gri durumda olup olmadığını gösterir.

```
BOOL IsButtonGrayed(int iButton) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButton*|[içinde] Durum alınacağı düğmeyi gösterir. Çağrı cihazı denetim stili PGS_HORZ, sol düğme için PGB_TOPORLEFT belirtin ve sağ düğme için PGB_BOTTOMORRIGHT. Çağrı cihazı denetim stili PGS_VERT ise, üst düğme için PGB_TOPORLEFT belirtin ve alt düğme için PGB_BOTTOMORRIGHT. Daha fazla bilgi için [Çağrı Cihazı Denetim Stilleri'ne](/windows/win32/Controls/pager-control-styles)bakın.|

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğme gri durumdaysa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisini gönderir. Daha sonra döndürülen durum PGF_GRAYED olup olmadığını test edin. Daha fazla bilgi için [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisinin İade Değeri bölümüne bakın.

## <a name="cpagerctrlisbuttonhot"></a><a name="isbuttonhot"></a>CPagerCtrl::IsButtonHot

Geçerli çağrı cihazı denetiminin belirtilen kaydırma düğmesinin sıcak durumda olup olmadığını gösterir.

```
BOOL IsButtonHot(int iButton) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButton*|[içinde] Durum alınacağı düğmeyi gösterir. Çağrı cihazı denetim stili PGS_HORZ, sol düğme için PGB_TOPORLEFT belirtin ve sağ düğme için PGB_BOTTOMORRIGHT. Çağrı cihazı denetim stili PGS_VERT ise, üst düğme için PGB_TOPORLEFT belirtin ve alt düğme için PGB_BOTTOMORRIGHT. Daha fazla bilgi için [Çağrı Cihazı Denetim Stilleri'ne](/windows/win32/Controls/pager-control-styles)bakın.|

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğme sıcak durumdaysa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisini gönderir. Daha sonra döndürülen durumu PGF_HOT olup olmadığını test edin. Daha fazla bilgi için [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisinin İade Değeri bölümüne bakın.

## <a name="cpagerctrlisbuttoninvisible"></a><a name="isbuttoninvisible"></a>CPagerCtrl::IsButtonInvisible

Geçerli çağrı cihazı denetiminin belirtilen kaydırma düğmesinin görünmez durumda olup olmadığını gösterir.

```
BOOL IsButtonInvisible(int iButton) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButton*|[içinde] Durum alınacağı düğmeyi gösterir. Çağrı cihazı denetim stili PGS_HORZ, sol düğme için PGB_TOPORLEFT belirtin ve sağ düğme için PGB_BOTTOMORRIGHT. Çağrı cihazı denetim stili PGS_VERT ise, üst düğme için PGB_TOPORLEFT belirtin ve alt düğme için PGB_BOTTOMORRIGHT. Daha fazla bilgi için [Çağrı Cihazı Denetim Stilleri'ne](/windows/win32/Controls/pager-control-styles)bakın.|

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğme görünmez durumdaysa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Windows, içerdiği pencere en uzak ölçüde kaydırıldığında belirli bir yöndeki kaydırma düğmesini görünmez kılar, çünkü düğmeyi tıklatmak içerdiği pencereden daha fazlasını görüntüleyemez.

Bu yöntem, Windows SDK'da açıklanan [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisini gönderir. Daha sonra döndürülen durum PGF_INVISIBLE olup olmadığını test edin. Daha fazla bilgi için [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisinin İade Değeri bölümüne bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, çağrı cihazı denetiminin sol ve sağ kaydırma düğmelerinin görünür olup olmadığını belirlemek için [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible) yöntemi ni kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]

## <a name="cpagerctrlisbuttonnormal"></a><a name="isbuttonnormal"></a>CPagerCtrl::IsButtonNormal

Geçerli çağrı cihazı denetiminin belirtilen kaydırma düğmesinin normal durumda olup olmadığını gösterir.

```
BOOL IsButtonNormal(int iButton) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButton*|[içinde] Durum alınacağı düğmeyi gösterir. Çağrı cihazı denetim stili PGS_HORZ, sol düğme için PGB_TOPORLEFT belirtin ve sağ düğme için PGB_BOTTOMORRIGHT. Çağrı cihazı denetim stili PGS_VERT ise, üst düğme için PGB_TOPORLEFT belirtin ve alt düğme için PGB_BOTTOMORRIGHT. Daha fazla bilgi için [Çağrı Cihazı Denetim Stilleri'ne](/windows/win32/Controls/pager-control-styles)bakın.|

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğme normal durumdaysa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisini gönderir. Daha sonra döndürülen durum PGF_NORMAL olup olmadığını test edin. Daha fazla bilgi için [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisinin İade Değeri bölümüne bakın.

## <a name="cpagerctrlrecalcsize"></a><a name="recalcsize"></a>CPagerCtrl::RecalcSize

Geçerli çağrı cihazı denetiminin, içerdiği pencerenin boyutunu yeniden hesaplamasına neden olur.

```cpp
void RecalcSize();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_RECALCSIZE](/windows/win32/Controls/pgm-recalcsize) iletisini gönderir. Sonuç olarak, çağrı cihazı denetimi, içerdiği pencerenin kaydırılabilir boyutlarını elde etmek için [PGN_CALCSIZE](/windows/win32/Controls/pgn-calcsize) bildirimi gönderir.

### <a name="example"></a>Örnek

Aşağıdaki örnekte [CPagerCtrl::RecalcSize](#recalcsize) yöntemini kullanır ve boyutunu yeniden hesaplamak için geçerli çağrı cihazı denetimini istemeyi sağlar.

[!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]

### <a name="example"></a>Örnek

Aşağıdaki örnekte, hesaplamayı gerçekleştirmek için denetimin üst iletişim kutusunu gerektirmek yerine çağrı cihazı denetiminin kendi boyutunu yeniden hesaplamasını sağlamak için [ileti yansıması](../../mfc/tn062-message-reflection-for-windows-controls.md) kullanılır. Örnek, `MyPagerCtrl` sınıfı [CPagerCtrl sınıfından](../../mfc/reference/cpagerctrl-class.md)türetir, ardından [PGN_CALCSIZE](/windows/win32/Controls/pgn-calcsize) `OnCalcsize` bildirimini bildirim işleyicisiyle ilişkilendirmek için bir ileti eşlemi kullanır. Bu örnekte, bildirim işleyicisi çağrı cihazı denetiminin genişliğini ve yüksekliğini sabit değerlere ayarlar.

[!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]

## <a name="cpagerctrlsetbkcolor"></a><a name="setbkcolor"></a>CPagerCtrl::SetBkColor

Geçerli çağrı cihazı denetiminin arka plan rengini ayarlar.

```
COLORREF SetBkColor(COLORREF clrBk);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*clrBk*|[içinde] Çağrı cihazı denetiminin yeni arka plan rengini içeren bir [COLORREF](/windows/win32/gdi/colorref) değeri.|

### <a name="return-value"></a>Dönüş Değeri

Çağrı cihazı denetiminin önceki arka plan rengini içeren bir [COLORREF](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_SETBKCOLOR](/windows/win32/Controls/pgm-setbkcolor) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, çağrı cihazı denetiminin arka plan rengini kırmızıya ayarlamak için [CPagerCtrl::SetBkColor](#setbkcolor) yöntemi ve değişikliğin yapıldığını doğrulamak için [CPagerKColor](#getbkcolor) yöntemi kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

## <a name="cpagerctrlsetborder"></a><a name="setborder"></a>CPagerCtrl::SetBorder

Geçerli çağrı cihazı denetiminin kenarlık boyutunu ayarlar.

```
int SetBorder(int iBorder);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iBorder*|[içinde] Yeni kenarlık boyutu, piksel cinsinden ölçülür. *iBorder* parametresi negatifse, kenarlık boyutu sıfıra ayarlanır.|

### <a name="return-value"></a>Dönüş Değeri

Önceki kenarlık boyutu, piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_SETBORDER](/windows/win32/Controls/pgm-setborder) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki örnek bir çağrı cihazı denetimi oluşturur, ardından çağrı cihazı denetimi ile çok uzun bir düğme denetimini ilişkilendirmek için [CPagerCtrl::SetChild](#setchild) yöntemini kullanır. Örnek daha sonra çağrı cihazı denetiminin yüksekliğini 20 piksele ayarlamak için [CPagerCtrl::SetButtonSize](#setbuttonsize) yöntemini kullanır ve kenarlık kalınlığını 1 piksele ayarlamak için [CPagerCtrl::SetBorder](#setborder) yöntemi.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetbuttonsize"></a><a name="setbuttonsize"></a>CPagerCtrl::SetButtonSize

Geçerli çağrı cihazı denetiminin düğme boyutunu ayarlar.

```
int SetButtonSize(int iButtonSize);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButtonSize*|[içinde] Piksel cinsinden ölçülen yeni düğme boyutu.|

### <a name="return-value"></a>Dönüş Değeri

Önceki düğme boyutu, piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_SETBUTTONSIZE](/windows/win32/Controls/pgm-setpos) iletisini gönderir.

Çağrı cihazı denetimi PGS_HORZ stiline sahipse, düğme boyutu çağrı cihazı düğmelerinin genişliğini belirler ve çağrı cihazı denetimi PGS_VERT stiline sahipse, düğme boyutu çağrı cihazı düğmelerinin yüksekliğini belirler. Varsayılan düğme boyutu kaydırma çubuğunun genişliğinin dörtte üçüdür ve minimum düğme boyutu 12 pikseldir. Daha fazla bilgi için [Çağrı Cihazı Denetim Stilleri'ne](/windows/win32/Controls/pager-control-styles)bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek bir çağrı cihazı denetimi oluşturur, ardından çağrı cihazı denetimi ile çok uzun bir düğme denetimini ilişkilendirmek için [CPagerCtrl::SetChild](#setchild) yöntemini kullanır. Örnek daha sonra çağrı cihazı denetiminin yüksekliğini 20 piksele ayarlamak için [CPagerCtrl::SetButtonSize](#setbuttonsize) yöntemini kullanır ve kenarlık kalınlığını 1 piksele ayarlamak için [CPagerCtrl::SetBorder](#setborder) yöntemi.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetchild"></a><a name="setchild"></a>CPagerCtrl::SetChild

Geçerli çağrı cihazı denetimi için içerdiği pencereyi ayarlar.

```cpp
void SetChild(HWND hwndChild);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*hwndÇocuk*|[içinde] Kontrol edilecek pencereye sapla.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_SETCHILD](/windows/win32/Controls/pgm-setchild) iletisini gönderir.

Bu yöntem, içerdiği pencerenin üst öğesini değiştirmez; yalnızca kaydırma için çağrı cihazı denetimine bir pencere tutamacı atar. Çoğu durumda, içerdiği pencere çağrı cihazı denetiminin alt penceresi olacaktır.

### <a name="example"></a>Örnek

Aşağıdaki örnek bir çağrı cihazı denetimi oluşturur, ardından çağrı cihazı denetimi ile çok uzun bir düğme denetimini ilişkilendirmek için [CPagerCtrl::SetChild](#setchild) yöntemini kullanır. Örnek daha sonra çağrı cihazı denetiminin yüksekliğini 20 piksele ayarlamak için [CPagerCtrl::SetButtonSize](#setbuttonsize) yöntemini kullanır ve kenarlık kalınlığını 1 piksele ayarlamak için [CPagerCtrl::SetBorder](#setborder) yöntemi.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetscrollpos"></a><a name="setscrollpos"></a>CPagerCtrl::SetScrollPos

Geçerli çağrı cihazı denetiminin kaydırma konumunu ayarlar.

```cpp
void SetScrollPos(int iPos);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iPos*|[içinde] Piksel cinsinden ölçülen yeni kaydırma konumu.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PGM_SETPOS](/windows/win32/Controls/pgm-setpos) iletisini gönderir.

## <a name="see-also"></a>Ayrıca bkz.

[CPagerCtrl Sınıfı](../../mfc/reference/cpagerctrl-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Çağrı Cihazı Denetimleri](/windows/win32/Controls/pager-controls)
