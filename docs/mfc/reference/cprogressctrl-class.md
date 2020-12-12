---
description: 'Daha fazla bilgi edinin: CProgressCtrl Class'
title: CProgressCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
helpviewer_keywords:
- CProgressCtrl [MFC], CProgressCtrl
- CProgressCtrl [MFC], Create
- CProgressCtrl [MFC], CreateEx
- CProgressCtrl [MFC], GetBarColor
- CProgressCtrl [MFC], GetBkColor
- CProgressCtrl [MFC], GetPos
- CProgressCtrl [MFC], GetRange
- CProgressCtrl [MFC], GetState
- CProgressCtrl [MFC], GetStep
- CProgressCtrl [MFC], OffsetPos
- CProgressCtrl [MFC], SetBarColor
- CProgressCtrl [MFC], SetBkColor
- CProgressCtrl [MFC], SetMarquee
- CProgressCtrl [MFC], SetPos
- CProgressCtrl [MFC], SetRange
- CProgressCtrl [MFC], SetState
- CProgressCtrl [MFC], SetStep
- CProgressCtrl [MFC], StepIt
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
ms.openlocfilehash: f5bd1bcae041d6bd61b715275b232fc5536cba2f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301418"
---
# <a name="cprogressctrl-class"></a>CProgressCtrl sınıfı

Windows ortak ilerleme çubuğu denetiminin işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CProgressCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CProgressCtrl:: CProgressCtrl](#cprogressctrl)|Bir `CProgressCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CProgressCtrl:: Create](#create)|İlerleme çubuğu denetimi oluşturur ve bir `CProgressCtrl` nesneye ekler.|
|[CProgressCtrl:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir ilerleme denetimi oluşturur ve bunu bir `CProgressCtrl` nesneye ekler.|
|[CProgressCtrl:: GetBarColor](#getbarcolor)|Geçerli ilerleme çubuğu denetimi için ilerleme göstergesi çubuğunun rengini alır.|
|[CProgressCtrl:: GetBkColor](#getbkcolor)|Geçerli ilerleme çubuğunun arka plan rengini alır.|
|[CProgressCtrl:: GetPos](#getpos)|İlerleme çubuğunun geçerli konumunu alır.|
|[CProgressCtrl:: GetRange](#getrange)|İlerleme çubuğu denetimi aralığının alt ve üst sınırlarını alır.|
|[CProgressCtrl:: GetState](#getstate)|Geçerli ilerleme çubuğu denetiminin durumunu alır.|
|[CProgressCtrl:: GetStep](#getstep)|Geçerli ilerleme çubuğu denetiminin ilerleme çubuğu için adım artışı alır.|
|[CProgressCtrl:: OffsetPos](#offsetpos)|İlerleme çubuğu denetiminin geçerli konumunu belirtilen artışla ilerletir ve çubuğu yeni konumu yansıtacak şekilde yeniden çizer.|
|[CProgressCtrl:: SetBarColor](#setbarcolor)|Geçerli ilerleme çubuğu denetimindeki ilerleme göstergesi çubuğunun rengini ayarlar.|
|[CProgressCtrl:: SetBkColor](#setbkcolor)|İlerleme çubuğu için arka plan rengini ayarlar.|
|[CProgressCtrl:: Setafkümesi](#setmarquee)|Geçerli ilerleme çubuğu denetimi için seçim çerçevesi modunu açar veya kapatır.|
|[CProgressCtrl:: SetPos](#setpos)|İlerleme çubuğu denetimi için geçerli konumu ayarlar ve çubuğu yeni konumu yansıtacak şekilde yeniden çizer.|
|[CProgressCtrl:: SetRange](#setrange)|İlerleme çubuğu denetimi için minimum ve maksimum aralıkları ayarlar ve çubuğu yeni aralıkları yansıtacak şekilde yeniden çizer.|
|[CProgressCtrl:: SetState](#setstate)|Geçerli ilerleme çubuğu denetiminin durumunu ayarlar.|
|[CProgressCtrl:: SetStep](#setstep)|İlerleme çubuğu denetiminin adım artışını belirtir.|
|[CProgressCtrl:: StepIt](#stepit)|, Adım artışı (bkz. [SetStep](#setstep)) ile bir ilerleme çubuğu denetiminin geçerli konumunu ilerletir ve çubuğu yeni konumu yansıtacak şekilde yeniden çizer.|

## <a name="remarks"></a>Açıklamalar

İlerleme çubuğu denetimi, uygulamanın uzun bir işlemin ilerlemesini göstermek için kullanabileceği bir penceredir. İşlem ilerledikçe sistem vurgu rengi ile soldan sağa, yavaş doldurulmuş bir dikdörtgenden oluşur.

İlerleme çubuğu denetimi bir aralığa ve geçerli konuma sahiptir. Aralık işlemin toplam süresini temsil eder ve geçerli konum uygulamanın işlemi tamamlamaya yönelik yaptığı ilerlemeyi temsil eder. Pencere yordamı, vurgu rengiyle doldurulacak ilerleme çubuğunun yüzdesini belirleyebilmek için aralığı ve geçerli konumu kullanır. Aralık ve geçerli konum değerleri işaretli tamsayılar olarak ifade edildiğinden, olası geçerli konum aralığı değeri-2.147.483.648 ile 2.147.483.647 arasında olur.

Kullanma hakkında daha fazla bilgi için `CProgressCtrl` bkz. [denetimler](../../mfc/controls-mfc.md) ve [CProgressCtrl kullanma](../../mfc/using-cprogressctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CProgressCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

## <a name="cprogressctrlcprogressctrl"></a><a name="cprogressctrl"></a> CProgressCtrl:: CProgressCtrl

Bir `CProgressCtrl` nesnesi oluşturur.

```
CProgressCtrl();
```

### <a name="remarks"></a>Açıklamalar

Nesnesi oluşturulduktan sonra `CProgressCtrl` `CProgressCtrl::Create` ilerleme çubuğu denetimini oluşturmak için çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]

## <a name="cprogressctrlcreate"></a><a name="create"></a> CProgressCtrl:: Create

İlerleme çubuğu denetimi oluşturur ve bir `CProgressCtrl` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
İlerleme çubuğu denetiminin stilini belirtir. Aşağıdaki ilerleme çubuğu denetim stillerine ek olarak, Windows SDK [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) 'ta açıklanan Window stylesof birleşimini uygulayın:

- PBS_VERTICAL ilerleme bilgilerini dikey ve yukarıdan aşağıya görüntüler. Bu bayrak olmadan, ilerleme çubuğu denetimi yatay olarak soldan sağa görüntülenir.

- PBS_SMOOTH, ilerleme çubuğu denetiminde aşamalı, düzgün doldurma gösterir. Bu bayrak olmadan denetim bloklarla doldurulur.

*Rect*<br/>
İlerleme çubuğu denetiminin boyutunu ve konumunu belirtir. Bu, bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir. Denetimin bir alt pencere olması gerektiğinden, belirtilen koordinatlar *pParentWnd*'nin istemci alanına göre belirlenir.

*pParentWnd*<br/>
İlerleme çubuğu denetiminin üst penceresini (genellikle a) belirtir `CDialog` . NULL olmaması gerekir.

*NID*<br/>
İlerleme çubuğu denetiminin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

`CProgressCtrl`Nesne başarıyla OLUŞTURULDUYSA true; aksi takdırde false.

### <a name="remarks"></a>Açıklamalar

`CProgressCtrl`İki adımda bir nesne oluşturursunuz. İlk olarak, nesnesini oluşturan oluşturucuyu çağırın `CProgressCtrl` ve sonra `Create` ilerleme çubuğu denetimini oluşturan çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]

## <a name="cprogressctrlcreateex"></a><a name="createex"></a> CProgressCtrl:: CreateEx

Bir denetim (alt pencere) oluşturur ve `CProgressCtrl` nesneyle ilişkilendirir.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Oluşturulmakta olan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerinin listesi için, Windows SDK için bkz. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) Için *dwExStyle* parametresi.

*dwStyle*<br/>
İlerleme çubuğu denetiminin stilini belirtir. Windows SDK [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) 'ta açıklanan pencere stillerinin herhangi bir birleşimini uygulayın.

*Rect*<br/>
*PParentWnd* istemci koordinatları içinde oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencerenin işaretçisi.

*NID*<br/>
Denetimin alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CreateEx`Windows genişletilmiş stil ön yüzü **ws_ex_** tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için [Create](#create) yerine kullanın.

## <a name="cprogressctrlgetbarcolor"></a><a name="getbarcolor"></a> CProgressCtrl:: GetBarColor

Geçerli ilerleme çubuğu denetimi için ilerleme göstergesi çubuğunun rengini alır.

```
COLORREF GetBarColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli ilerleme çubuğunun [colorref](/windows/win32/gdi/colorref) değeri olarak temsil edilen rengi veya ilerleme göstergesi çubuk rengi varsayılan renkse CLR_DEFAULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PBM_GETBARCOLOR](/windows/win32/Controls/pbm-getbarcolor) iletisini gönderir.

## <a name="cprogressctrlgetbkcolor"></a><a name="getbkcolor"></a> CProgressCtrl:: GetBkColor

Geçerli ilerleme çubuğunun arka plan rengini alır.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli ilerleme çubuğunun [colorref](/windows/win32/gdi/colorref) değeri olarak temsil edilen arka plan rengi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PBM_GETBKCOLOR](/windows/win32/Controls/pbm-getbkcolor) iletisini gönderir.

## <a name="cprogressctrlgetpos"></a><a name="getpos"></a> CProgressCtrl:: GetPos

İlerleme çubuğunun geçerli konumunu alır.

```
int GetPos();
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu denetiminin konumu.

### <a name="remarks"></a>Açıklamalar

İlerleme çubuğu denetiminin konumu ekranda fiziksel konum değildir, bunun yerine [SetRange](#setrange)içinde belirtilen üst ve alt Aralık arasında olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]

## <a name="cprogressctrlgetrange"></a><a name="getrange"></a> CProgressCtrl:: GetRange

İlerleme çubuğu denetiminin geçerli alt ve üst sınırlarını veya aralığını alır.

```cpp
void GetRange(
    int& nLower,
    int& nUpper);
```

### <a name="parameters"></a>Parametreler

*nLower*<br/>
İlerleme çubuğu denetiminin alt sınırını alan bir tamsayıya yönelik başvuru.

*nUpper*<br/>
İlerleme çubuğu denetiminin üst sınırını alan bir tamsayıya yönelik başvuru.

### <a name="remarks"></a>Açıklamalar

Bu işlev, alt ve üst limitlerin değerlerini sırasıyla *nLower* ve *nUpper* tarafından başvurulan tamsayılara kopyalar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]

## <a name="cprogressctrlgetstate"></a><a name="getstate"></a> CProgressCtrl:: GetState

Geçerli ilerleme çubuğu denetiminin durumunu alır.

```
int GetState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu değerlerden biri olan geçerli ilerleme çubuğu denetiminin durumu:

|Değer|Durum|
|-----------|-----------|
|PBST_NORMAL|Sürüyor|
|PBST_ERROR|Hata|
|PBST_PAUSED|Duraklatıldı|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PBM_GETSTATE](/windows/win32/Controls/pbm-getstate) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_progressCtrl` ilerleme çubuğu denetimine programlı bir şekilde erişmek için kullanılan değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli ilerleme çubuğu denetiminin durumunu alır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]

## <a name="cprogressctrlgetstep"></a><a name="getstep"></a> CProgressCtrl:: GetStep

Geçerli ilerleme çubuğu denetiminin ilerleme çubuğu için adım artışı alır.

```
int GetStep() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğunun adım artışı.

### <a name="remarks"></a>Açıklamalar

Adım artışı, [CProgressCtrl:: Stepa](#stepit) çağrısının ilerleme çubuğunun geçerli konumunu artırdığı tutardır.

Bu yöntem, Windows SDK açıklanan [PBM_GETSTEP](/windows/win32/Controls/pbm-getstep) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_progressCtrl` ilerleme çubuğu denetimine programlı bir şekilde erişmek için kullanılan değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli ilerleme çubuğu denetiminin adım artışını alır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]

## <a name="cprogressctrloffsetpos"></a><a name="offsetpos"></a> CProgressCtrl:: OffsetPos

İlerleme çubuğu denetiminin geçerli konumunu *nPos* tarafından belirtilen artışla ilerletir ve çubuğu yeni konumu yansıtacak şekilde yeniden çizer.

```
int OffsetPos(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Konumun ilerleme miktarı.

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu denetiminin önceki konumu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]

## <a name="cprogressctrlsetbarcolor"></a><a name="setbarcolor"></a> CProgressCtrl:: SetBarColor

Geçerli ilerleme çubuğu denetimindeki ilerleme göstergesi çubuğunun rengini ayarlar.

```
COLORREF SetBarColor(COLORREF clrBar);
```

### <a name="parameters"></a>Parametreler

*clrBar*\
'ndaki İlerleme göstergesi çubuğunun yeni rengini belirten [colorref](/windows/win32/gdi/colorref) değeri. İlerleme çubuğunun varsayılan rengini kullanmasını sağlamak için CLR_DEFAULT belirtin.

### <a name="return-value"></a>Dönüş Değeri

İlerleme göstergesi çubuğunun, [colorref](/windows/win32/gdi/colorref) değeri olarak temsil edilen önceki rengi veya ilerleme göstergesi çubuğunun rengi varsayılan renk ise CLR_DEFAULT.

### <a name="remarks"></a>Açıklamalar

`SetBarColor`Yöntemi, yalnızca bir Windows Vista [teması](/windows/win32/Controls/visual-styles-overview) etkin değilse ilerleme çubuğu rengini ayarlar.

Bu yöntem, Windows SDK açıklanan [PBM_SETBARCOLOR](/windows/win32/Controls/pbm-setbarcolor) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_progressCtrl` ilerleme çubuğu denetimine programlı bir şekilde erişmek için kullanılan değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, ilerleme çubuğunun rengini kırmızı, yeşil, mavi veya varsayılan olarak değiştirir.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]

## <a name="cprogressctrlsetbkcolor"></a><a name="setbkcolor"></a> CProgressCtrl:: SetBkColor

İlerleme çubuğu için arka plan rengini ayarlar.

```
COLORREF SetBkColor(COLORREF clrNew);
```

### <a name="parameters"></a>Parametreler

*clrNew*<br/>
Yeni arka plan rengini belirten COLORREF değeri. İlerleme çubuğu için varsayılan arka plan rengini kullanmak üzere CLR_DEFAULT değerini belirtin.

### <a name="return-value"></a>Dönüş Değeri

Önceki arka plan rengini gösteren [colorref](/windows/win32/gdi/colorref) değeri veya arka plan rengi varsayılan renk ise CLR_DEFAULT.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]

## <a name="cprogressctrlsetmarquee"></a><a name="setmarquee"></a> CProgressCtrl:: Setafkümesi

Geçerli ilerleme çubuğu denetimi için seçim çerçevesi modunu açar veya kapatır.

```
BOOL SetMarquee(
    BOOL fMarqueeMode,
    int nInterval);
```

### <a name="parameters"></a>Parametreler

*fMarqueeMode*\
'ndaki Kayan yazı modunu açmak için TRUE, kayan yazı modunu kapatmak için FALSE.

*nAralık*\
'ndaki Kayan yazı animasyonunun güncelleştirmeleri arasındaki milisaniye cinsinden süre.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Kayan yazı modu açık olduğunda, ilerleme çubuğu canlandırılır ve bir sinemalı seçim çerçevesiyle bir oturum gibi kayar.

Bu yöntem, Windows SDK açıklanan [PBM_SETMARQUEE](/windows/win32/Controls/pbm-setmarquee) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_progressCtrl` ilerleme çubuğu denetimine programlı bir şekilde erişmek için kullanılan değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği başlar ve kayan yazı animasyonunu sonlandırır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]

## <a name="cprogressctrlsetpos"></a><a name="setpos"></a> CProgressCtrl:: SetPos

İlerleme çubuğu denetiminin geçerli konumunu *nPos* tarafından belirtilen şekilde ayarlar ve çubuğu yeni konumu yansıtacak şekilde yeniden çizer.

```
int SetPos(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
İlerleme çubuğu denetiminin yeni konumu.

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu denetiminin önceki konumu.

### <a name="remarks"></a>Açıklamalar

İlerleme çubuğu denetiminin konumu ekranda fiziksel konum değildir, bunun yerine [SetRange](#setrange)içinde belirtilen üst ve alt Aralık arasında olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]

## <a name="cprogressctrlsetrange"></a><a name="setrange"></a> CProgressCtrl:: SetRange

İlerleme çubuğu denetiminin aralığının üst ve alt sınırlarını ayarlar ve çubuğu yeni aralıkları yansıtacak şekilde yeniden çizer.

```cpp
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Parametreler

*nLower*<br/>
Aralığın alt sınırını belirtir (varsayılan sıfırdır).

*nUpper*<br/>
Aralığın üst sınırını belirtir (varsayılan değer 100 ' dir).

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `SetRange32` ilerleme denetimi için 32 bitlik aralığı ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]

## <a name="cprogressctrlsetstate"></a><a name="setstate"></a> CProgressCtrl:: SetState

Geçerli ilerleme çubuğu denetiminin durumunu ayarlar.

```
int SetState(int iState);
```

### <a name="parameters"></a>Parametreler

*iState*\
'ndaki İlerleme çubuğunu ayarlanacak durum. Aşağıdaki değerlerden birini kullanın:

- `PBST_NORMAL` -Devam ediyor
- `PBST_ERROR` -Hata
- `PBST_PAUSED` -Duraklatıldı

### <a name="return-value"></a>Dönüş Değeri

Geçerli ilerleme çubuğu denetiminin önceki durumu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [PBM_SETSTATE](/windows/win32/Controls/pbm-setstate) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_progressCtrl` ilerleme çubuğu denetimine programlı bir şekilde erişmek için kullanılan değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli ilerleme çubuğu denetiminin durumunu duraklatılmış veya devam ediyor olarak ayarlar.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]

## <a name="cprogressctrlsetstep"></a><a name="setstep"></a> CProgressCtrl:: SetStep

İlerleme çubuğu denetiminin adım artışını belirtir.

```
int SetStep(int nStep);
```

### <a name="parameters"></a>Parametreler

*nStep*<br/>
Yeni adım artışı.

### <a name="return-value"></a>Dönüş Değeri

Önceki adım artışı.

### <a name="remarks"></a>Açıklamalar

Adım artışı, bir çağrının `CProgressCtrl::StepIt` ilerleme çubuğunun geçerli konumunu arttığı tutardır.

Varsayılan adım artışı 10 ' dur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]

## <a name="cprogressctrlstepit"></a><a name="stepit"></a> CProgressCtrl:: StepIt

Adım artışı tarafından ilerleme çubuğu denetiminin geçerli konumunu ilerletir ve çubuğu yeni konumu yansıtacak şekilde yeniden çizer.

```
int StepIt();
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu denetiminin önceki konumu.

### <a name="remarks"></a>Açıklamalar

Adım artışı `CProgressCtrl::SetStep` üye işlevi tarafından ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
