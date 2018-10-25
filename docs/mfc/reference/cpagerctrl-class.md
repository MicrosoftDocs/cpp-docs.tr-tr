---
title: CPagerCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f7dc77eb9afdfcded959abad2199b1d255ffe3e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054273"
---
# <a name="cpagerctrl-class"></a>CPagerCtrl sınıfı

`CPagerCtrl` Sınıfı, kapsayan pencereye uymayan bir kapsanan pencere görünümüne kaydırabilirsiniz Windows sayfalama denetimini sarar.

## <a name="syntax"></a>Sözdizimi

```
class CPagerCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPagerCtrl::CPagerCtrl](#cpagerctrl)|Oluşturur bir `CPagerCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPagerCtrl::Create](#create)|Belirtilen stilleriyle bir çağrı cihazı denetimi oluşturur ve geçerli ekler `CPagerCtrl` nesne.|
|[CPagerCtrl::CreateEx](#createex)|Belirtilen genişletilmiş stilleriyle bir çağrı cihazı denetimi oluşturur ve geçerli ekler `CPagerCtrl` nesne.|
|[CPagerCtrl::ForwardMouse](#forwardmouse)|Etkinleştirir veya devre dışı bırakır, iletme [WM_MOUSEMOVE](/windows/desktop/inputdev/wm-mousemove) geçerli çağrı denetiminde bulunan bir pencere için iletileri.|
|[CPagerCtrl::GetBkColor](#getbkcolor)|Geçerli çağrı cihazı denetimi arka plan rengini alır.|
|[CPagerCtrl::GetBorder](#getborder)|Geçerli çağrı cihazı denetimi kenarlık boyutunu alır.|
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|Geçerli çağrı cihazı denetimi düğmesi boyutunu alır.|
|[CPagerCtrl::GetButtonState](#getbuttonstate)|Geçerli çağrı cihazı denetimi içinde belirtilen düğmenin durumunu alır.|
|[CPagerCtrl::GetDropTarget](#getdroptarget)|Alır [ıdroptarget'ı](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) geçerli çağrı cihazı denetimi için arabirim.|
|[CPagerCtrl::GetScrollPos](#getscrollpos)|Geçerli çağrı cihazı denetimi kaydırma konumunu alır.|
|[CPagerCtrl::IsButtonDepressed](#isbuttondepressed)|Geçerli çağrı cihazı denetimi belirtilen düğmesine içinde olup olmadığını belirten `pressed` durumu.|
|[CPagerCtrl::IsButtonGrayed](#isbuttongrayed)|Geçerli çağrı cihazı denetimi belirtilen düğmesine içinde olup olmadığını belirten `grayed` durumu.|
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|Geçerli çağrı cihazı denetimi belirtilen düğmesine içinde olup olmadığını belirten `hot` durumu.|
|[CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)|Geçerli çağrı cihazı denetimi belirtilen düğmesine içinde olup olmadığını belirten `invisible` durumu.|
|[CPagerCtrl::IsButtonNormal](#isbuttonnormal)|Geçerli çağrı cihazı denetimi belirtilen düğmesine içinde olup olmadığını belirten `normal` durumu.|
|[CPagerCtrl::RecalcSize](#recalcsize)|Kapsanan pencere boyutunu yeniden hesaplar geçerli çağrı cihazı denetimi neden olur.|
|[CPagerCtrl::SetBkColor](#setbkcolor)|Geçerli çağrı cihazı denetimi arka plan rengini ayarlar.|
|[CPagerCtrl::SetBorder](#setborder)|Geçerli çağrı cihazı denetimi kenarlık boyutunu ayarlar.|
|[CPagerCtrl::SetButtonSize](#setbuttonsize)|Geçerli çağrı cihazı denetimi düğmesi boyutunu ayarlar.|
|[CPagerCtrl::SetChild](#setchild)|Kapsanan pencerenin geçerli çağrı cihazı denetimi için ayarlar.|
|[CPagerCtrl::SetScrollPos](#setscrollpos)|Geçerli çağrı cihazı denetimi kaydırma konumunu ayarlar.|

## <a name="remarks"></a>Açıklamalar

Sayfalama denetimi içeren doğrusal ve kapsayan pencereye büyük ve kapsanan pencere görünümüne gidin sağlayan başka bir pencere bir penceredir. Çağrı cihazı denetimi kapsanan pencere kaydırılan, otomatik olarak en uzak, bir aşamaya kaybolur iki kaydırma düğmelerine görüntüler; Aksi takdirde yeniden görünür. Yatay veya dikey olarak kaydırır bir çağrı cihazı denetimi oluşturabilirsiniz.

Örneğin, uygulamanızın tüm öğeleri göstermek için geniş değil bir araç çubuğu varsa, araç için bir çağrı cihazı denetimi atayabilir ve kullanıcıların araç çubuğuna tüm öğelerin erişmeye sağa veya sola kaydırma mümkün olacaktır. Microsoft Internet Explorer sürüm 4.0 (commctrl.dll sürüm 4.71), çağrı cihazı denetimi sunar.

`CPagerCtrl` Sınıfı türetilen [CWnd](../../mfc/reference/cwnd-class.md) sınıfı. Daha fazla bilgi ve çağrı cihazı denetimi çizim için bkz: [çağrı denetimleri](/windows/desktop/Controls/pager-controls).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPagerCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

##  <a name="cpagerctrl"></a>  CPagerCtrl::CPagerCtrl

Oluşturur bir `CPagerCtrl` nesne.

```
CPagerCtrl();
```

### <a name="remarks"></a>Açıklamalar

Kullanım [CPagerCtrl::Create](#create) veya [CPagerCtrl::CreateEx](#createex) yöntemi, sayfalama denetimi oluşturun ve buna eklemek için `CPagerCtrl` nesne.

##  <a name="create"></a>  CPagerCtrl::Create

Belirtilen stilleriyle bir çağrı cihazı denetimi oluşturur ve geçerli ekler `CPagerCtrl` nesne.

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
|*dwStyle*|[in] Bit düzeyinde birleşimi (veya) [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [çağrı cihazı denetimi stilleri](/windows/desktop/Controls/pager-control-styles) denetime uygulanacak.|
|*Rect*|[in] Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları denetiminin boyutunu ve konumunu içeren yapısı.|
|*pParentWnd*|[in] Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) denetiminin üst penceresine olan nesne. Bu parametre NULL olamaz.|
|*nID*|[in] Denetimin kimliği.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Sayfalama denetimi oluşturmak için bildirin bir `CPagerCtrl` değişkeni,'ı çağırın [CPagerCtrl::Create](#create) veya [CPagerCtrl::CreateEx](#createex) değişken yöntemi.

### <a name="example"></a>Örnek

Aşağıdaki örnek, çağrı cihazı denetimi oluşturur, ardından kullanan [CPagerCtrl::SetChild](#setchild) çok uzun bir düğme denetimi, çağrı cihazı denetimi ile ilişkilendirmek için yöntemi. Ardından örnekte [CPagerCtrl::SetButtonSize](#setbuttonsize) yöntemi çağrı denetimin yüksekliği 20 piksel olarak ayarlanacak ve [CPagerCtrl::SetBorder](#setborder) 1 piksel kenarlık kalınlığı ayarlamak için yöntemi.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="createex"></a>  CPagerCtrl::CreateEx

Belirtilen genişletilmiş stilleriyle bir çağrı cihazı denetimi oluşturur ve geçerli ekler `CPagerCtrl` nesne.

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
|*dwExStyle*|[in] Denetimlere uygulanması için genişletilmiş stiller Bitsel bir birleşimi. Daha fazla bilgi için *dwExStyle* parametresinin [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) işlevi.|
|*dwStyle*|[in] Bit düzeyinde birleşimi (veya) [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [çağrı cihazı denetimi stilleri](/windows/desktop/Controls/pager-control-styles) denetime uygulanacak.|
|*Rect*|[in] Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları denetiminin boyutunu ve konumunu içeren yapısı.|
|*pParentWnd*|[in] Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) denetiminin üst penceresine olan nesne. Bu parametre NULL olamaz.|
|*nID*|[in] Denetimin kimliği.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Sayfalama denetimi oluşturmak için bildirin bir `CPagerCtrl` değişkeni,'ı çağırın [CPagerCtrl::Create](#create) veya [CPagerCtrl::CreateEx](#createex) değişken yöntemi.

##  <a name="forwardmouse"></a>  CPagerCtrl::ForwardMouse

Etkinleştirir veya devre dışı bırakır, iletme [WM_MOUSEMOVE](/windows/desktop/inputdev/wm-mousemove) geçerli çağrı denetiminde bulunan bir pencere için iletileri.

```
void ForwardMouse(BOOL bForward);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*bForward*|[in] İletme fare iletileri veya yanlış true değil fare iletileri iletecek şekilde.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_FORWARDMOUSE](/windows/desktop/Controls/pgm-forwardmouse) Windows SDK'da açıklanan ileti.

##  <a name="getborder"></a>  CPagerCtrl::GetBorder

Geçerli çağrı cihazı denetimi kenarlık boyutunu alır.

```
int GetBorder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli sınır boyutunu piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_GETBORDER](/windows/desktop/Controls/pgm-getborder) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki örnekte [CPagerCtrl::GetBorder](#getborder) çağrı Denetimin kenarlık kalınlığı almak için yöntemi.

[!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]

##  <a name="getbkcolor"></a>  CPagerCtrl::GetBkColor

Geçerli çağrı cihazı denetimi arka plan rengini alır.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

A [COLORREF](/windows/desktop/gdi/colorref) değeri geçerli arka plan rengi çağrı cihazı denetimi içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_GETBKCOLOR](/windows/desktop/Controls/pgm-getbkcolor) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki örnekte [CPagerCtrl::SetBkColor](#setbkcolor) kırmızı, çağrı cihazı denetimi arka plan rengini ayarlamak için yöntemi ve [CPagerCtrl::GetBkColor](#getbkcolor) yöntemi değişiklik yapıldığını onaylayın.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

##  <a name="getbuttonsize"></a>  CPagerCtrl::GetButtonSize

Geçerli çağrı cihazı denetimi düğmesi boyutunu alır.

```
int GetButtonSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli düğmesi boyutunu piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_GETBUTTONSIZE](/windows/desktop/Controls/pgm-getbuttonsize) Windows SDK'da açıklanan ileti.

Çağrı cihazı denetimi PGS_HORZ stili varsa, düğme boyutu, sayfa düğmelerini genişliğini belirler. ve çağrı cihazı denetimi PGS_VERT stili varsa, sayfa düğmelerini yüksekliğini düğmesi boyutunu belirler. Daha fazla bilgi için [çağrı cihazı denetimi stilleri](/windows/desktop/Controls/pager-control-styles).

##  <a name="getbuttonstate"></a>  CPagerCtrl::GetButtonState

Geçerli çağrı cihazı denetimi belirtilen kaydırma düğmeye durumunu alır.

```
DWORD GetButtonState(int iButton) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButton*|[in] İçin durumu alınacağı düğmesini gösterir. Çağrı cihazı denetimi stil PGS_HORZ ise PGB_TOPORLEFT PGB_BOTTOMORRIGHT ve sol düğme için sağ düğme için belirtin. Çağrı cihazı denetimi stil PGS_VERT ise PGB_TOPORLEFT PGB_BOTTOMORRIGHT ve üst düğme için alt düğmesini belirtin. Daha fazla bilgi için [çağrı cihazı denetimi stilleri](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen düğmenin durumu *iButton* parametresi. Durum PGF_INVISIBLE, PGF_NORMAL, PGF_GRAYED, PGF_DEPRESSED veya PGF_HOT şeklindedir. Daha fazla bilgi için dönüş değeri bölümüne bakın. [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) ileti.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Windows SDK'da açıklanan ileti.

##  <a name="getdroptarget"></a>  CPagerCtrl::GetDropTarget

Alır [ıdroptarget'ı](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) geçerli çağrı cihazı denetimi için arabirim.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `IDropTarget` geçerli çağrı cihazı denetimi için arabirim.

### <a name="remarks"></a>Açıklamalar

`IDropTarget` bir arabirim uygulamak için uygulamanızda sürükle ve bırak işlemleri destekler.

Bu yöntem gönderir [PGM_GETDROPTARGET](/windows/desktop/Controls/pgm-getdroptarget) Windows SDK'da açıklanan ileti. Bu yöntemi çağıran kişi için arama sorumludur `Release` üyesi [ıdroptarget'ı](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) arabirimi bu arabirim artık gerekli olmadığında.

##  <a name="getscrollpos"></a>  CPagerCtrl::GetScrollPos

Geçerli çağrı cihazı denetimi kaydırma konumunu alır.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kaydırma konumunu piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_GETPOS](/windows/desktop/Controls/pgm-getpos) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki örnekte [CPagerCtrl::GetScrollPos](#getscrollpos) çağrı cihazı denetimi kaydırma konumunu almak için yöntemi. Çağrı cihazı denetimi zaten en soldaki konumu, sıfır olarak kaydırılan değil örnek kullanıyorsa [CPagerCtrl::SetScrollPos](#setscrollpos) sıfır olarak kaydırma konumunu ayarlamak için yöntemi.

[!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]

##  <a name="isbuttondepressed"></a>  CPagerCtrl::IsButtonDepressed

Geçerli çağrı cihazı denetimi belirtilen kaydırma düğmesi basılı durumda olup olmadığını belirtir.

```
BOOL IsButtonDepressed(int iButton) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButton*|[in] İçin durumu alınacağı düğmesini gösterir. Çağrı cihazı denetimi stil PGS_HORZ ise PGB_TOPORLEFT PGB_BOTTOMORRIGHT ve sol düğme için sağ düğme için belirtin. Çağrı cihazı denetimi stil PGS_VERT ise PGB_TOPORLEFT PGB_BOTTOMORRIGHT ve üst düğme için alt düğmesini belirtin. Daha fazla bilgi için [çağrı cihazı denetimi stilleri](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğmesini basılı durumda ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Windows SDK'da açıklanan ileti. Daha sonra döndürülen durum PGF_DEPRESSED olup olmadığını sınar. Daha fazla bilgi için dönüş değeri bölümüne bakın. [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) ileti.

##  <a name="isbuttongrayed"></a>  CPagerCtrl::IsButtonGrayed

Geçerli çağrı cihazı denetimi belirtilen kaydırma düğmesi gri durumda olup olmadığını belirtir.

```
BOOL IsButtonGrayed(int iButton) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButton*|[in] İçin durumu alınacağı düğmesini gösterir. Çağrı cihazı denetimi stil PGS_HORZ ise PGB_TOPORLEFT PGB_BOTTOMORRIGHT ve sol düğme için sağ düğme için belirtin. Çağrı cihazı denetimi stil PGS_VERT ise PGB_TOPORLEFT PGB_BOTTOMORRIGHT ve üst düğme için alt düğmesini belirtin. Daha fazla bilgi için [çağrı cihazı denetimi stilleri](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğmesi gri durumda ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Windows SDK'da açıklanan ileti. Daha sonra döndürülen durum PGF_GRAYED olup olmadığını sınar. Daha fazla bilgi için dönüş değeri bölümüne bakın. [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) ileti.

##  <a name="isbuttonhot"></a>  CPagerCtrl::IsButtonHot

Geçerli çağrı cihazı denetimi belirtilen kaydırma düğmesi etkin durumda olup olmadığını belirtir.

```
BOOL IsButtonHot(int iButton) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButton*|[in] İçin durumu alınacağı düğmesini gösterir. Çağrı cihazı denetimi stil PGS_HORZ ise PGB_TOPORLEFT PGB_BOTTOMORRIGHT ve sol düğme için sağ düğme için belirtin. Çağrı cihazı denetimi stil PGS_VERT ise PGB_TOPORLEFT PGB_BOTTOMORRIGHT ve üst düğme için alt düğmesini belirtin. Daha fazla bilgi için [çağrı cihazı denetimi stilleri](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğmenin sıcak durumunda ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Windows SDK'da açıklanan ileti. Daha sonra döndürülen durum PGF_HOT olup olmadığını sınar. Daha fazla bilgi için dönüş değeri bölümüne bakın. [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) ileti.

##  <a name="isbuttoninvisible"></a>  CPagerCtrl::IsButtonInvisible

Geçerli çağrı cihazı denetimi belirtilen kaydırma düğmesine görünmez durumda olup olmadığını belirtir.

```
BOOL IsButtonInvisible(int iButton) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButton*|[in] İçin durumu alınacağı düğmesini gösterir. Çağrı cihazı denetimi stil PGS_HORZ ise PGB_TOPORLEFT PGB_BOTTOMORRIGHT ve sol düğme için sağ düğme için belirtin. Çağrı cihazı denetimi stil PGS_VERT ise PGB_TOPORLEFT PGB_BOTTOMORRIGHT ve üst düğme için alt düğmesini belirtin. Daha fazla bilgi için [çağrı cihazı denetimi stilleri](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğmenin görünmez durumda ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla düğmeye tıklandığında daha kapsanan pencerenin görünüme yapılamıyor çünkü kapsanan pencerenin en uzak, bir aşamaya kaydırılan olduğunda Windows kaydırma çubuğu belirli bir yönde görünmez hale getirir.

Bu yöntem gönderir [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Windows SDK'da açıklanan ileti. Daha sonra döndürülen durum PGF_INVISIBLE olup olmadığını sınar. Daha fazla bilgi için dönüş değeri bölümüne bakın. [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) ileti.

### <a name="example"></a>Örnek

Aşağıdaki örnekte [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible) yöntemi, sayfalama denetimi sol ve sağ kaydırma düğmelerine görünür olup olmadığını belirlemek için.

[!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]

##  <a name="isbuttonnormal"></a>  CPagerCtrl::IsButtonNormal

Geçerli çağrı cihazı denetimi belirtilen kaydırma düğmesine normal durumda olup olmadığını belirtir.

```
BOOL IsButtonNormal(int iButton) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButton*|[in] İçin durumu alınacağı düğmesini gösterir. Çağrı cihazı denetimi stil PGS_HORZ ise PGB_TOPORLEFT PGB_BOTTOMORRIGHT ve sol düğme için sağ düğme için belirtin. Çağrı cihazı denetimi stil PGS_VERT ise PGB_TOPORLEFT PGB_BOTTOMORRIGHT ve üst düğme için alt düğmesini belirtin. Daha fazla bilgi için [çağrı cihazı denetimi stilleri](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Dönüş Değeri

Belirtilen düğmesi içinde normal durumuna ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Windows SDK'da açıklanan ileti. Daha sonra döndürülen durum PGF_NORMAL olup olmadığını sınar. Daha fazla bilgi için dönüş değeri bölümüne bakın. [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) ileti.

##  <a name="recalcsize"></a>  CPagerCtrl::RecalcSize

Kapsanan pencere boyutunu yeniden hesaplar geçerli çağrı cihazı denetimi neden olur.

```
void RecalcSize();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_RECALCSIZE](/windows/desktop/Controls/pgm-recalcsize) Windows SDK'da açıklanan ileti. Sonuç olarak, çağrı cihazı denetimi gönderir [PGN_CALCSIZE](/windows/desktop/Controls/pgn-calcsize) kapsanan pencerenin kaydırılabilir boyutlarını almak için bildirim.

### <a name="example"></a>Örnek

Aşağıdaki örnekte [CPagerCtrl::RecalcSize](#recalcsize) boyutunu yeniden hesaplar için geçerli çağrı cihazı denetimi istemek için yöntemi.

[!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]

### <a name="example"></a>Örnek

Aşağıdaki örnekte [ileti yansıma](../../mfc/tn062-message-reflection-for-windows-controls.md) hesaplama gerçekleştirmek için denetimin üst iletişim kutusunu göstermek zorunda kalmadan, kendi boyutu yeniden hesaplamak çağrı cihazı denetimi etkinleştirmek için. Örnek türetilen `MyPagerCtrl` gelen sınıfı [CPagerCtrl sınıfı](../../mfc/reference/cpagerctrl-class.md), daha sonra ilişkilendirmek için ileti eşlemesi kullanır [PGN_CALCSIZE](/windows/desktop/Controls/pgn-calcsize) bildirimi `OnCalcsize` bildirim işleyici. Bu örnekte, bildirim işleyici genişlik ve yükseklik çağrı cihazı denetimi sabit değerlerine göre ayarlar.

[!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]

##  <a name="setbkcolor"></a>  CPagerCtrl::SetBkColor

Geçerli çağrı cihazı denetimi arka plan rengini ayarlar.

```
COLORREF SetBkColor(COLORREF clrBk);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*clrBk*|[in] A [COLORREF](/windows/desktop/gdi/colorref) yeni arka plan rengi çağrı cihazı denetimi içeren bir değer.|

### <a name="return-value"></a>Dönüş Değeri

A [COLORREF](/windows/desktop/gdi/colorref) değeri önceki arka plan rengi çağrı cihazı denetimi içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_SETBKCOLOR](/windows/desktop/Controls/pgm-setbkcolor) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki örnekte [CPagerCtrl::SetBkColor](#setbkcolor) kırmızı, çağrı cihazı denetimi arka plan rengini ayarlamak için yöntemi ve [CPagerCtrl::GetBkColor](#getbkcolor) yöntemi değişiklik yapıldığını onaylayın.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

##  <a name="setborder"></a>  CPagerCtrl::SetBorder

Geçerli çağrı cihazı denetimi kenarlık boyutunu ayarlar.

```
int SetBorder(int iBorder);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iBorder*|[in] Yeni sınır boyutunu piksel cinsinden ölçülür. Varsa *iBorder* parametresi negatif ise, sınır boyutu sıfır olarak ayarlanır.|

### <a name="return-value"></a>Dönüş Değeri

Önceki kenarlık boyutunu piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_SETBORDER](/windows/desktop/Controls/pgm-setborder) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki örnek, çağrı cihazı denetimi oluşturur, ardından kullanan [CPagerCtrl::SetChild](#setchild) çok uzun bir düğme denetimi, çağrı cihazı denetimi ile ilişkilendirmek için yöntemi. Ardından örnekte [CPagerCtrl::SetButtonSize](#setbuttonsize) yöntemi çağrı denetimin yüksekliği 20 piksel olarak ayarlanacak ve [CPagerCtrl::SetBorder](#setborder) 1 piksel kenarlık kalınlığı ayarlamak için yöntemi.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setbuttonsize"></a>  CPagerCtrl::SetButtonSize

Geçerli çağrı cihazı denetimi düğmesi boyutunu ayarlar.

```
int SetButtonSize(int iButtonSize);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iButtonSize*|[in] Yeni düğme boyutunu piksel cinsinden ölçülür.|

### <a name="return-value"></a>Dönüş Değeri

Önceki düğmesi boyutunu piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_SETBUTTONSIZE](/windows/desktop/Controls/pgm-setpos) Windows SDK'da açıklanan ileti.

Çağrı cihazı denetimi PGS_HORZ stili varsa, düğme boyutu, sayfa düğmelerini genişliğini belirler. ve çağrı cihazı denetimi PGS_VERT stili varsa, sayfa düğmelerini yüksekliğini düğmesi boyutunu belirler. Varsayılan düğme boyutu üç fourths kaydırma çubuğunun genişliği ve en az düğme boyutu 12 pikseldir. Daha fazla bilgi için [çağrı cihazı denetimi stilleri](/windows/desktop/Controls/pager-control-styles).

### <a name="example"></a>Örnek

Aşağıdaki örnek, çağrı cihazı denetimi oluşturur, ardından kullanan [CPagerCtrl::SetChild](#setchild) çok uzun bir düğme denetimi, çağrı cihazı denetimi ile ilişkilendirmek için yöntemi. Ardından örnekte [CPagerCtrl::SetButtonSize](#setbuttonsize) yöntemi çağrı denetimin yüksekliği 20 piksel olarak ayarlanacak ve [CPagerCtrl::SetBorder](#setborder) 1 piksel kenarlık kalınlığı ayarlamak için yöntemi.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setchild"></a>  CPagerCtrl::SetChild

Kapsanan pencerenin geçerli çağrı cihazı denetimi için ayarlar.

```
void SetChild(HWND hwndChild);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*hwndChild*|[in] Pencereyi dahil edilmek üzere işleyin.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_SETCHILD](/windows/desktop/Controls/pgm-setchild) Windows SDK'da açıklanan ileti.

Bu yöntem, kapsanan pencerenin üst değiştirmez. yalnızca bir pencere tutucu kaydırmayı çağrı cihazı denetimi atar. Çoğu durumda, çağrı cihazı denetimi alt pencere kapsanan pencere olacaktır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, çağrı cihazı denetimi oluşturur, ardından kullanan [CPagerCtrl::SetChild](#setchild) çok uzun bir düğme denetimi, çağrı cihazı denetimi ile ilişkilendirmek için yöntemi. Ardından örnekte [CPagerCtrl::SetButtonSize](#setbuttonsize) yöntemi çağrı denetimin yüksekliği 20 piksel olarak ayarlanacak ve [CPagerCtrl::SetBorder](#setborder) 1 piksel kenarlık kalınlığı ayarlamak için yöntemi.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setscrollpos"></a>  CPagerCtrl::SetScrollPos

Geçerli çağrı cihazı denetimi kaydırma konumunu ayarlar.

```
void SetScrollPos(int iPos);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iPos*|[in] Yeni kaydırma konumunu piksel cinsinden ölçülür.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PGM_SETPOS](/windows/desktop/Controls/pgm-setpos) Windows SDK'da açıklanan ileti.

## <a name="see-also"></a>Ayrıca Bkz.

[CPagerCtrl Sınıfı](../../mfc/reference/cpagerctrl-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sayfa denetimleri](/windows/desktop/Controls/pager-controls)

