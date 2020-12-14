---
description: 'Daha fazla bilgi edinin: CPagerCtrl sınıfı'
title: CPagerCtrl sınıfı
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
ms.openlocfilehash: ba01d07ebd6d638a1d505d555e44e9562e4bd27b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345231"
---
# <a name="cpagerctrl-class"></a>CPagerCtrl sınıfı

`CPagerCtrl`Sınıfı Windows sayfalayıcı denetimini sarmalanmış ve kapsayan pencereye uymayan bir içerilen pencereyi görüntülemeye kaydırabilen.

## <a name="syntax"></a>Syntax

```
class CPagerCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPagerCtrl:: CPagerCtrl](#cpagerctrl)|Bir `CPagerCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPagerCtrl:: Create](#create)|Belirtilen stillerle bir sayfalayıcı denetimi oluşturur ve geçerli `CPagerCtrl` nesneye ekler.|
|[CPagerCtrl:: CreateEx](#createex)|Belirtilen genişletilmiş stillerle bir sayfalayıcı denetimi oluşturur ve geçerli `CPagerCtrl` nesneye ekler.|
|[CPagerCtrl:: ForwardMouse](#forwardmouse)|Geçerli sayfalayıcı denetiminde yer alan pencereye [WM_MOUSEMOVE](/windows/win32/inputdev/wm-mousemove) iletilerini iletmeyi sağlar veya devre dışı bırakır.|
|[CPagerCtrl:: GetBkColor](#getbkcolor)|Geçerli sayfalayıcı denetiminin arka plan rengini alır.|
|[CPagerCtrl:: GetBorder](#getborder)|Geçerli sayfalayıcı denetiminin kenarlık boyutunu alır.|
|[CPagerCtrl:: GetButtonSize](#getbuttonsize)|Geçerli sayfalayıcı denetiminin düğme boyutunu alır.|
|[CPagerCtrl:: GetButtonState](#getbuttonstate)|Geçerli sayfalayıcı denetimindeki belirtilen düğmenin durumunu alır.|
|[CPagerCtrl:: GetDropTarget](#getdroptarget)|Geçerli sayfalayıcı denetimi için [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) arabirimini alır.|
|[CPagerCtrl:: GetScrollPos](#getscrollpos)|Geçerli sayfalayıcı denetiminin kaydırma konumunu alır.|
|[CPagerCtrl:: Isbuttondepınat](#isbuttondepressed)|Geçerli sayfalayıcı denetiminin belirtilen düğmesinin durumunda olup olmadığını gösterir `pressed` .|
|[CPagerCtrl:: Isbuttongridir](#isbuttongrayed)|Geçerli sayfalayıcı denetiminin belirtilen düğmesinin durumunda olup olmadığını gösterir `grayed` .|
|[CPagerCtrl:: IsButtonHot](#isbuttonhot)|Geçerli sayfalayıcı denetiminin belirtilen düğmesinin durumunda olup olmadığını gösterir `hot` .|
|[CPagerCtrl:: Isbuttongörünmez](#isbuttoninvisible)|Geçerli sayfalayıcı denetiminin belirtilen düğmesinin durumunda olup olmadığını gösterir `invisible` .|
|[CPagerCtrl:: IsButtonNormal](#isbuttonnormal)|Geçerli sayfalayıcı denetiminin belirtilen düğmesinin durumunda olup olmadığını gösterir `normal` .|
|[CPagerCtrl:: yeniden hesaplama](#recalcsize)|Geçerli sayfalayıcı denetiminin içerilen pencerenin boyutunu yeniden hesaplamasını sağlar.|
|[CPagerCtrl:: SetBkColor](#setbkcolor)|Geçerli sayfalayıcı denetiminin arka plan rengini ayarlar.|
|[CPagerCtrl:: SetBorder](#setborder)|Geçerli sayfalayıcı denetiminin kenarlık boyutunu ayarlar.|
|[CPagerCtrl:: SetButtonSize](#setbuttonsize)|Geçerli sayfalayıcı denetiminin düğme boyutunu ayarlar.|
|[CPagerCtrl:: SetChild](#setchild)|Geçerli sayfalayıcı denetimi için içerilen pencereyi ayarlar.|
|[CPagerCtrl:: SetScrollPos](#setscrollpos)|Geçerli sayfalayıcı denetiminin kaydırma konumunu ayarlar.|

## <a name="remarks"></a>Açıklamalar

Sayfalayıcı denetimi, kapsayan pencere ile doğrusal ve daha büyük bir pencere içeren ve içerilen pencereyi görünüme kaydırabilmenizi sağlayan bir penceredir. Sayfalayıcı denetimi, içerilen pencere en uzak kapsamına kaydırıldığında otomatik olarak kaybolan iki kaydırma düğmesini görüntüler ve aksi takdirde yeniden görüntülenir. Yatay veya dikey olarak kaydırma yapan bir sayfalayıcı denetimi oluşturabilirsiniz.

Örneğin, uygulamanızın tüm öğelerini göstermek için yeterince geniş olmayan bir araç çubuğu varsa, araç çubuğunu bir sayfalayıcı denetimine atayabilirsiniz ve kullanıcılar araç çubuğunu sola veya sağa kaydırabilecektir ve öğelerin tümüne erişin. Microsoft Internet Explorer sürüm 4,0 (commctrl.dll sürüm 4,71) sayfalayıcı denetimini tanıtır.

`CPagerCtrl`Sınıfı, [CWnd](../../mfc/reference/cwnd-class.md) sınıfından türetilir. Daha fazla bilgi ve çağrı denetimi çizimi için bkz. [sayfalayıcı denetimleri](/windows/win32/Controls/pager-controls).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPagerCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

## <a name="cpagerctrlcpagerctrl"></a><a name="cpagerctrl"></a> CPagerCtrl:: CPagerCtrl

Bir `CPagerCtrl` nesnesi oluşturur.

```
CPagerCtrl();
```

### <a name="remarks"></a>Açıklamalar

Bir sayfalayıcı denetimi oluşturmak ve nesneye iliştirmek için [CPagerCtrl:: Create](#create) veya [CPagerCtrl:: CreateEx](#createex) metodunu kullanın `CPagerCtrl` .

## <a name="cpagerctrlcreate"></a><a name="create"></a> CPagerCtrl:: Create

Belirtilen stillerle bir sayfalayıcı denetimi oluşturur ve geçerli `CPagerCtrl` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*\
'ndaki Denetime uygulanacak [pencere stillerinin](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [sayfalayıcı denetim stillerinin](/windows/win32/Controls/pager-control-styles) BIT düzeyinde birleşimi (veya).

*Rect*\
'ndaki İstemci koordinatlarındaki denetimin konumunu ve boyutunu içeren bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*\
'ndaki Denetimin üst penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine yönelik bir işaretçi. Bu parametre NULL olamaz.

*NID*\
'ndaki Denetimin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bir sayfalayıcı denetimi oluşturmak için bir değişken bildirin `CPagerCtrl` , ardından Bu değişkende [CPagerCtrl:: Create](#create) veya [CPagerCtrl:: CreateEx](#createex) metodunu çağırın.

### <a name="example"></a>Örnek

Aşağıdaki örnek bir sayfalayıcı denetimi oluşturur ve sonra çok uzun bir düğme denetimini sayfalayıcı denetimiyle ilişkilendirmek için [CPagerCtrl:: SetChild](#setchild) yöntemini kullanır. Örnek daha sonra [CPagerCtrl:: SetButtonSize](#setbuttonsize) yöntemini kullanarak sayfalayıcı denetiminin yüksekliğini 20 piksel, sonra da kenarlık kalınlığını 1 piksel olarak ayarlamak Için [CPagerCtrl:: SetBorder](#setborder) yöntemini kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlcreateex"></a><a name="createex"></a> CPagerCtrl:: CreateEx

Belirtilen genişletilmiş stillerle bir sayfalayıcı denetimi oluşturur ve geçerli `CPagerCtrl` nesneye ekler.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*\
'ndaki Denetime uygulanacak genişletilmiş stillerin bit düzeyinde birleşimi. Daha fazla bilgi için bkz. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) Işlevinin *dwExStyle* parametresi.

*dwStyle*\
'ndaki Denetime uygulanacak [pencere stillerinin](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [sayfalayıcı denetim stillerinin](/windows/win32/Controls/pager-control-styles) BIT düzeyinde birleşimi (veya).

*Rect*\
'ndaki İstemci koordinatlarındaki denetimin konumunu ve boyutunu içeren bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*\
'ndaki Denetimin üst penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine yönelik bir işaretçi. Bu parametre NULL olamaz.

*NID*\
'ndaki Denetimin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bir sayfalayıcı denetimi oluşturmak için bir değişken bildirin `CPagerCtrl` , ardından Bu değişkende [CPagerCtrl:: Create](#create) veya [CPagerCtrl:: CreateEx](#createex) metodunu çağırın.

## <a name="cpagerctrlforwardmouse"></a><a name="forwardmouse"></a> CPagerCtrl:: ForwardMouse

Geçerli sayfalayıcı denetiminde yer alan pencereye [WM_MOUSEMOVE](/windows/win32/inputdev/wm-mousemove) iletilerini iletmeyi sağlar veya devre dışı bırakır.

```cpp
void ForwardMouse(BOOL bForward);
```

### <a name="parameters"></a>Parametreler

*Bilet*\
'ndaki Fare iletilerini iletmek için TRUE, fare iletilerini iletmeyen FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_FORWARDMOUSE](/windows/win32/Controls/pgm-forwardmouse) iletisini gönderir.

## <a name="cpagerctrlgetborder"></a><a name="getborder"></a> CPagerCtrl:: GetBorder

Geçerli sayfalayıcı denetiminin kenarlık boyutunu alır.

```
int GetBorder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Piksel cinsinden ölçülen geçerli kenarlık boyutu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_GETBORDER](/windows/win32/Controls/pgm-getborder) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sayfalayıcı denetiminin kenarlığının kalınlığını almak için [CPagerCtrl:: GetBorder](#getborder) metodunu kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]

## <a name="cpagerctrlgetbkcolor"></a><a name="getbkcolor"></a> CPagerCtrl:: GetBkColor

Geçerli sayfalayıcı denetiminin arka plan rengini alır.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sayfalayıcı denetiminin geçerli arka plan rengini içeren bir [colorref](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_GETBKCOLOR](/windows/win32/Controls/pgm-getbkcolor) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki örnek [CPagerCtrl:: SetBkColor](#setbkcolor) metodunu kullanarak sayfalayıcı denetiminin arka plan rengini kırmızı olarak, [CPagerCtrl:: GetBkColor](#getbkcolor) yöntemini ise değişikliğin yapıldığını onaylayın.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

## <a name="cpagerctrlgetbuttonsize"></a><a name="getbuttonsize"></a> CPagerCtrl:: GetButtonSize

Geçerli sayfalayıcı denetiminin düğme boyutunu alır.

```
int GetButtonSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Piksel cinsinden ölçülen geçerli düğme boyutu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_GETBUTTONSIZE](/windows/win32/Controls/pgm-getbuttonsize) iletisini gönderir.

Sayfalayıcı denetiminin PGS_HORZ stili varsa, düğme boyutu sayfalayıcı düğmelerinin genişliğini belirler ve sayfalayıcı denetiminin PGS_VERT stili varsa, düğme boyutu sayfalayıcı düğmelerinin yüksekliğini belirler. Daha fazla bilgi için bkz. [sayfalayıcı denetim stilleri](/windows/win32/Controls/pager-control-styles).

## <a name="cpagerctrlgetbuttonstate"></a><a name="getbuttonstate"></a> CPagerCtrl:: GetButtonState

Geçerli sayfalayıcı denetimindeki belirtilen kaydırma düğmesinin durumunu alır.

```
DWORD GetButtonState(int iButton) const;
```

### <a name="parameters"></a>Parametreler

*IButton*\
'ndaki Durumun alındığı düğmeyi gösterir. Sayfalayıcı denetim stili PGS_HORZ, sol düğme için PGB_TOPORLEFT ve sağ düğme için PGB_BOTTOMORRIGHT belirtin. Sayfalayıcı denetim stili PGS_VERT, en üstteki düğme için PGB_TOPORLEFT ve alt düğme için PGB_BOTTOMORRIGHT belirtin. Daha fazla bilgi için bkz. [sayfalayıcı denetim stilleri](/windows/win32/Controls/pager-control-styles).

### <a name="return-value"></a>Dönüş Değeri

*IButton* parametresi tarafından belirtilen düğmenin durumu. Durum PGF_INVISIBLE, PGF_NORMAL, PGF_GRAYED, PGF_DEPRESSED veya PGF_HOT. Daha fazla bilgi için [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) Iletisinin dönüş değeri bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisini gönderir.

## <a name="cpagerctrlgetdroptarget"></a><a name="getdroptarget"></a> CPagerCtrl:: GetDropTarget

Geçerli sayfalayıcı denetimi için [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) arabirimini alır.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Dönüş Değeri

`IDropTarget`Geçerli sayfalayıcı denetimi için arabirim işaretçisi.

### <a name="remarks"></a>Açıklamalar

`IDropTarget` , uygulamanızda sürükle ve bırak işlemlerini desteklemek için uyguladığınız arabirimlerden biridir.

Bu yöntem, Windows SDK açıklanan [PGM_GETDROPTARGET](/windows/win32/Controls/pgm-getdroptarget) iletisini gönderir. Bu yöntemin çağıranı, `Release` arabirime artık gerek kalmadığında [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) arabiriminin üyesini çağırmaktan sorumludur.

## <a name="cpagerctrlgetscrollpos"></a><a name="getscrollpos"></a> CPagerCtrl:: GetScrollPos

Geçerli sayfalayıcı denetiminin kaydırma konumunu alır.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Piksel cinsinden ölçülen geçerli kaydırma konumu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_GETPOS](/windows/win32/Controls/pgm-getpos) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sayfalayıcı denetiminin geçerli kaydırma konumunu almak için [CPagerCtrl:: GetScrollPos](#getscrollpos) metodunu kullanır. Sayfalayıcı denetimi zaten sıfıra kaydırılmaz, en soldaki konum, örnek, kaydırma konumunu sıfıra ayarlamak için [CPagerCtrl:: SetScrollPos](#setscrollpos) metodunu kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]

## <a name="cpagerctrlisbuttondepressed"></a><a name="isbuttondepressed"></a> CPagerCtrl:: Isbuttondepınat

Geçerli sayfalayıcı denetiminin belirtilen kaydırma düğmesinin basılı durumda olup olmadığını gösterir.

```
BOOL IsButtonDepressed(int iButton) const;
```

### <a name="parameters"></a>Parametreler

*IButton*\
'ndaki Durumun alındığı düğmeyi gösterir. Sayfalayıcı denetim stili PGS_HORZ, sol düğme için PGB_TOPORLEFT ve sağ düğme için PGB_BOTTOMORRIGHT belirtin. Sayfalayıcı denetim stili PGS_VERT, en üstteki düğme için PGB_TOPORLEFT ve alt düğme için PGB_BOTTOMORRIGHT belirtin. Daha fazla bilgi için bkz. [sayfalayıcı denetim stilleri](/windows/win32/Controls/pager-control-styles).

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğme basılı durumdaysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisini gönderir. Ardından, döndürülen durumun PGF_DEPRESSED olup olmadığını sınar. Daha fazla bilgi için [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) Iletisinin dönüş değeri bölümüne bakın.

## <a name="cpagerctrlisbuttongrayed"></a><a name="isbuttongrayed"></a> CPagerCtrl:: Isbuttongridir

Geçerli sayfalayıcı denetiminin belirtilen kaydırma düğmesinin gri durumunda olup olmadığını gösterir.

```
BOOL IsButtonGrayed(int iButton) const;
```

### <a name="parameters"></a>Parametreler

*IButton*\
'ndaki Durumun alındığı düğmeyi gösterir. Sayfalayıcı denetim stili PGS_HORZ, sol düğme için PGB_TOPORLEFT ve sağ düğme için PGB_BOTTOMORRIGHT belirtin. Sayfalayıcı denetim stili PGS_VERT, en üstteki düğme için PGB_TOPORLEFT ve alt düğme için PGB_BOTTOMORRIGHT belirtin. Daha fazla bilgi için bkz. [sayfalayıcı denetim stilleri](/windows/win32/Controls/pager-control-styles).

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğme gri durumdaysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisini gönderir. Ardından, döndürülen durumun PGF_GRAYED olup olmadığını sınar. Daha fazla bilgi için [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) Iletisinin dönüş değeri bölümüne bakın.

## <a name="cpagerctrlisbuttonhot"></a><a name="isbuttonhot"></a> CPagerCtrl:: IsButtonHot

Geçerli sayfalayıcı denetiminin belirtilen kaydırma düğmesinin etkin durumda olup olmadığını gösterir.

```
BOOL IsButtonHot(int iButton) const;
```

### <a name="parameters"></a>Parametreler

*IButton*\
'ndaki Durumun alındığı düğmeyi gösterir. Sayfalayıcı denetim stili PGS_HORZ, sol düğme için PGB_TOPORLEFT ve sağ düğme için PGB_BOTTOMORRIGHT belirtin. Sayfalayıcı denetim stili PGS_VERT, en üstteki düğme için PGB_TOPORLEFT ve alt düğme için PGB_BOTTOMORRIGHT belirtin. Daha fazla bilgi için bkz. [sayfalayıcı denetim stilleri](/windows/win32/Controls/pager-control-styles).

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğme etkin durumdaysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisini gönderir. Ardından, döndürülen durumun PGF_HOT olup olmadığını sınar. Daha fazla bilgi için [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) Iletisinin dönüş değeri bölümüne bakın.

## <a name="cpagerctrlisbuttoninvisible"></a><a name="isbuttoninvisible"></a> CPagerCtrl:: Isbuttongörünmez

Geçerli sayfalayıcı denetiminin belirtilen kaydırma düğmesinin görünmez durumda olup olmadığını gösterir.

```
BOOL IsButtonInvisible(int iButton) const;
```

### <a name="parameters"></a>Parametreler

*IButton*\
'ndaki Durumun alındığı düğmeyi gösterir. Sayfalayıcı denetim stili PGS_HORZ, sol düğme için PGB_TOPORLEFT ve sağ düğme için PGB_BOTTOMORRIGHT belirtin. Sayfalayıcı denetim stili PGS_VERT, en üstteki düğme için PGB_TOPORLEFT ve alt düğme için PGB_BOTTOMORRIGHT belirtin. Daha fazla bilgi için bkz. [sayfalayıcı denetim stilleri](/windows/win32/Controls/pager-control-styles).

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğme görünmez durumdaysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Pencereler, içerilen pencere daha fazla pencerenin görünüme daha fazlasını getiremediği için, bulunan pencerenin en üst kapsamına kaydırıldığında, kaydırma düğmesini belirli bir yönde görünmez hale getirir.

Bu yöntem, Windows SDK açıklanan [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisini gönderir. Ardından, döndürülen durumun PGF_INVISIBLE olup olmadığını sınar. Daha fazla bilgi için [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) Iletisinin dönüş değeri bölümüne bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sayfalayıcı denetiminin sol ve sağ kaydırma düğmelerinin görünür olup olmadığını anlamak için [CPagerCtrl:: Isbuttongörünmeyen](#isbuttoninvisible) yöntemini kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]

## <a name="cpagerctrlisbuttonnormal"></a><a name="isbuttonnormal"></a> CPagerCtrl:: IsButtonNormal

Geçerli sayfalayıcı denetiminin belirtilen kaydırma düğmesinin normal durumda olup olmadığını gösterir.

```
BOOL IsButtonNormal(int iButton) const;
```

### <a name="parameters"></a>Parametreler

*IButton*\
'ndaki Durumun alındığı düğmeyi gösterir. Sayfalayıcı denetim stili PGS_HORZ, sol düğme için PGB_TOPORLEFT ve sağ düğme için PGB_BOTTOMORRIGHT belirtin. Sayfalayıcı denetim stili PGS_VERT, en üstteki düğme için PGB_TOPORLEFT ve alt düğme için PGB_BOTTOMORRIGHT belirtin. Daha fazla bilgi için bkz. [sayfalayıcı denetim stilleri](/windows/win32/Controls/pager-control-styles).

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğme normal durumdaysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) iletisini gönderir. Ardından, döndürülen durumun PGF_NORMAL olup olmadığını sınar. Daha fazla bilgi için [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) Iletisinin dönüş değeri bölümüne bakın.

## <a name="cpagerctrlrecalcsize"></a><a name="recalcsize"></a> CPagerCtrl:: yeniden hesaplama

Geçerli sayfalayıcı denetiminin içerilen pencerenin boyutunu yeniden hesaplamasını sağlar.

```cpp
void RecalcSize();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_RECALCSIZE](/windows/win32/Controls/pgm-recalcsize) iletisini gönderir. Sonuç olarak, sayfalayıcı denetimi içerilen pencerenin kaydırılabilir boyutlarını almak için [PGN_CALCSIZE](/windows/win32/Controls/pgn-calcsize) bildirimi gönderir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, boyutunu yeniden hesaplamak için geçerli sayfalayıcı denetimini istemek üzere [CPagerCtrl:: yeniden hesaplama CSize](#recalcsize) yöntemini kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]

### <a name="example"></a>Örnek

Aşağıdaki örnek, denetimin üst iletişim kutusunun hesaplamayı gerçekleştirmesini gerektirmek yerine sayfalayıcı denetiminin kendi boyutunu yeniden hesaplamasını sağlamak için [ileti yansımasını](../../mfc/tn062-message-reflection-for-windows-controls.md) kullanır. Örnek, `MyPagerCtrl` [CPagerCtrl sınıfından](../../mfc/reference/cpagerctrl-class.md)sınıfını türeten sonra bildirim işleyicisiyle [PGN_CALCSIZE](/windows/win32/Controls/pgn-calcsize) bildirimi ilişkilendirmek için bir ileti eşlemesi kullanır `OnCalcsize` . Bu örnekte, bildirim işleyicisi sayfalayıcı denetiminin genişlik ve yüksekliğini sabit değerler olarak ayarlar.

[!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]

## <a name="cpagerctrlsetbkcolor"></a><a name="setbkcolor"></a> CPagerCtrl:: SetBkColor

Geçerli sayfalayıcı denetiminin arka plan rengini ayarlar.

```
COLORREF SetBkColor(COLORREF clrBk);
```

### <a name="parameters"></a>Parametreler

*clrBk*\
'ndaki Sayfalayıcı denetiminin yeni arka plan rengini içeren bir [colorref](/windows/win32/gdi/colorref) değeri.

### <a name="return-value"></a>Dönüş Değeri

Sayfalayıcı denetiminin önceki arka plan rengini içeren bir [colorref](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_SETBKCOLOR](/windows/win32/Controls/pgm-setbkcolor) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki örnek [CPagerCtrl:: SetBkColor](#setbkcolor) metodunu kullanarak sayfalayıcı denetiminin arka plan rengini kırmızı olarak, [CPagerCtrl:: GetBkColor](#getbkcolor) yöntemini ise değişikliğin yapıldığını onaylayın.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

## <a name="cpagerctrlsetborder"></a><a name="setborder"></a> CPagerCtrl:: SetBorder

Geçerli sayfalayıcı denetiminin kenarlık boyutunu ayarlar.

```
int SetBorder(int iBorder);
```

### <a name="parameters"></a>Parametreler

*ıborder*\
'ndaki Piksel cinsinden ölçülen yeni kenarlık boyutu. *Iborder* parametresi negatifse, kenarlık boyutu sıfır olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Önceki kenarlık boyutu piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_SETBORDER](/windows/win32/Controls/pgm-setborder) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki örnek bir sayfalayıcı denetimi oluşturur ve sonra çok uzun bir düğme denetimini sayfalayıcı denetimiyle ilişkilendirmek için [CPagerCtrl:: SetChild](#setchild) yöntemini kullanır. Örnek daha sonra [CPagerCtrl:: SetButtonSize](#setbuttonsize) yöntemini kullanarak sayfalayıcı denetiminin yüksekliğini 20 piksel, sonra da kenarlık kalınlığını 1 piksel olarak ayarlamak Için [CPagerCtrl:: SetBorder](#setborder) yöntemini kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetbuttonsize"></a><a name="setbuttonsize"></a> CPagerCtrl:: SetButtonSize

Geçerli sayfalayıcı denetiminin düğme boyutunu ayarlar.

```
int SetButtonSize(int iButtonSize);
```

### <a name="parameters"></a>Parametreler

*ıbuttonsize*\
'ndaki Piksel cinsinden ölçülen yeni düğme boyutu.

### <a name="return-value"></a>Dönüş Değeri

Önceki düğme boyutu piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_SETBUTTONSIZE](/windows/win32/Controls/pgm-setpos) iletisini gönderir.

Sayfalayıcı denetiminin PGS_HORZ stili varsa, düğme boyutu sayfalayıcı düğmelerinin genişliğini belirler ve sayfalayıcı denetiminin PGS_VERT stili varsa, düğme boyutu sayfalayıcı düğmelerinin yüksekliğini belirler. Varsayılan düğme boyutu, kaydırma çubuğunun genişliğinin üç onudur ve minimum düğme boyutu 12 pikselden oluşur. Daha fazla bilgi için bkz. [sayfalayıcı denetim stilleri](/windows/win32/Controls/pager-control-styles).

### <a name="example"></a>Örnek

Aşağıdaki örnek bir sayfalayıcı denetimi oluşturur ve sonra çok uzun bir düğme denetimini sayfalayıcı denetimiyle ilişkilendirmek için [CPagerCtrl:: SetChild](#setchild) yöntemini kullanır. Örnek daha sonra [CPagerCtrl:: SetButtonSize](#setbuttonsize) yöntemini kullanarak sayfalayıcı denetiminin yüksekliğini 20 piksel, sonra da kenarlık kalınlığını 1 piksel olarak ayarlamak Için [CPagerCtrl:: SetBorder](#setborder) yöntemini kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetchild"></a><a name="setchild"></a> CPagerCtrl:: SetChild

Geçerli sayfalayıcı denetimi için içerilen pencereyi ayarlar.

```cpp
void SetChild(HWND hwndChild);
```

### <a name="parameters"></a>Parametreler

*hwndChild*\
'ndaki Dahil edilecek pencere için tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_SETCHILD](/windows/win32/Controls/pgm-setchild) iletisini gönderir.

Bu yöntem, içerilen pencerenin üst öğesini değiştirmez; yalnızca kaydırma için sayfalayıcı denetimine bir pencere tutamacı atar. Çoğu durumda, içerilen pencere sayfalayıcı denetiminin bir alt penceresi olacaktır.

### <a name="example"></a>Örnek

Aşağıdaki örnek bir sayfalayıcı denetimi oluşturur ve sonra çok uzun bir düğme denetimini sayfalayıcı denetimiyle ilişkilendirmek için [CPagerCtrl:: SetChild](#setchild) yöntemini kullanır. Örnek daha sonra [CPagerCtrl:: SetButtonSize](#setbuttonsize) yöntemini kullanarak sayfalayıcı denetiminin yüksekliğini 20 piksel, sonra da kenarlık kalınlığını 1 piksel olarak ayarlamak Için [CPagerCtrl:: SetBorder](#setborder) yöntemini kullanır.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetscrollpos"></a><a name="setscrollpos"></a> CPagerCtrl:: SetScrollPos

Geçerli sayfalayıcı denetiminin kaydırma konumunu ayarlar.

```cpp
void SetScrollPos(int iPos);
```

### <a name="parameters"></a>Parametreler

*IPOS*\
'ndaki Piksel cinsinden ölçülen yeni kaydırma konumu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PGM_SETPOS](/windows/win32/Controls/pgm-setpos) iletisini gönderir.

## <a name="see-also"></a>Ayrıca bkz.

[CPagerCtrl sınıfı](../../mfc/reference/cpagerctrl-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sayfalayıcı denetimleri](/windows/win32/Controls/pager-controls)
