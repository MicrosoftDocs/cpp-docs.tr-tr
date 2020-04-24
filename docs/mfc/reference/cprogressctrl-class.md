---
title: CProgressCtrl Sınıfı
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
ms.openlocfilehash: c9e94e334318b32efcf8c9de681a78349ab12151
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751128"
---
# <a name="cprogressctrl-class"></a>CProgressCtrl Sınıfı

Windows ortak ilerleme çubuğu denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CProgressCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|Bir `CProgressCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CProgressCtrl::Oluştur](#create)|İlerleme çubuğu denetimi oluşturur ve nesneye `CProgressCtrl` bağlar.|
|[CProgressCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile bir ilerleme denetimi oluşturur `CProgressCtrl` ve bir nesneye bağlar.|
|[CProgressCtrl::GetBarColor](#getbarcolor)|Geçerli ilerleme çubuğu denetimi için ilerleme göstergesi çubuğunun rengini alır.|
|[CProgressCtrl::GetBkColor](#getbkcolor)|Geçerli ilerleme çubuğunun arka plan rengini alır.|
|[CProgressCtrl::GetPos](#getpos)|İlerleme çubuğunun geçerli konumunu alır.|
|[CProgressCtrl::GetRange](#getrange)|İlerleme çubuğu denetimi aralığının alt ve üst sınırlarını alır.|
|[CProgressCtrl::GetState](#getstate)|Geçerli ilerleme çubuğu denetiminin durumunu alır.|
|[CProgressCtrl::GetStep](#getstep)|Geçerli ilerleme çubuğu denetiminin ilerleme çubuğu için adım artışını alır.|
|[CProgressCtrl::OfsetPos](#offsetpos)|İlerleme çubuğu denetiminin geçerli konumunu belirli bir artışla ilerletin ve çubuğu yeni konumu yansıtacak şekilde yeniden çizer.|
|[CProgressCtrl::SetBarColor](#setbarcolor)|Geçerli ilerleme çubuğu denetiminde ilerleme göstergesi çubuğunun rengini ayarlar.|
|[CProgressCtrl::SetBkColor](#setbkcolor)|İlerleme çubuğunun arka plan rengini ayarlar.|
|[CProgressCtrl::SetMarquee](#setmarquee)|Geçerli ilerleme çubuğu denetimi için seçim çerçevesi modunu açar veya kapatır.|
|[CProgressCtrl::SetPos](#setpos)|İlerleme çubuğu denetimi için geçerli konumu ayarlar ve çubuğu yeni konumu yansıtacak şekilde yeniden çizer.|
|[CProgressCtrl::SetAralığı](#setrange)|İlerleme çubuğu denetimi için minimum ve maksimum aralıkları ayarlar ve çubuğu yeni aralıkları yansıtacak şekilde yeniden çizer.|
|[CProgressCtrl::SetState](#setstate)|Geçerli ilerleme çubuğu denetiminin durumunu ayarlar.|
|[CProgressCtrl::SetStep](#setstep)|İlerleme çubuğu denetimi için adım artışını belirtir.|
|[CProgressCtrl::AdımIt](#stepit)|İlerleme çubuğu denetimi için geçerli konumu adım adım adımla ilerletin [(Bkz. SetStep)](#setstep)ve yeni konumu yansıtacak şekilde çubuğu yeniden çizer.|

## <a name="remarks"></a>Açıklamalar

İlerleme çubuğu denetimi, bir uygulamanın uzun bir işlemin ilerlemesini belirtmek için kullanabileceği bir penceredir. Yavaş yavaş doldurulan bir dikdörtgen oluşur, soldan sağa, sistem bir işlem ilerledikçe renk vurgulamak ile.

İlerleme çubuğu denetiminin bir aralığı ve geçerli konumu vardır. Aralık işlemin toplam süresini ve geçerli konum uygulamanın işlemi tamamlama yolunda kaydettiği ilerlemeyi temsil eder. Pencere yordamı, vurgu rengiyle doldurmak için ilerleme çubuğunun yüzdesini belirlemek için aralığı ve geçerli konumu kullanır. Aralık ve geçerli konum değerleri imzalı tümsavar olarak ifade edildiklerinden, geçerli konum değerlerinin olası aralığı -2,147,483,648 ile 2,147,483,647 dahil.

Kullanma `CProgressCtrl`hakkında daha fazla bilgi [Using CProgressCtrl](../../mfc/using-cprogressctrl.md)için, [bkz.](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CProgressCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="cprogressctrlcprogressctrl"></a><a name="cprogressctrl"></a>CProgressCtrl::CProgressCtrl

Bir `CProgressCtrl` nesne inşa eder.

```
CProgressCtrl();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi `CProgressCtrl` oluşturduktan sonra, ilerleme çubuğu denetimini oluşturmak için arayın. `CProgressCtrl::Create`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]

## <a name="cprogressctrlcreate"></a><a name="create"></a>CProgressCtrl::Oluştur

İlerleme çubuğu denetimi oluşturur ve nesneye `CProgressCtrl` bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
İlerleme çubuğu denetiminin stilini belirtir. Windows SDK'da [CreateWindow'da](/windows/win32/api/winuser/nf-winuser-createwindoww) açıklanan pencere stillerinin herhangi bir birleşimini, aşağıdaki ilerleme çubuğu denetim stillerine ek olarak denetime uygulayın:

- PBS_VERTICAL İlerleme bilgilerini dikey olarak, yukarıdan aşağıya görüntüler. Bu bayrak olmadan, ilerleme çubuğu denetimi yatay olarak, soldan sağa görüntülenir.

- PBS_SMOOTH İlerleme çubuğu kontrolünde kademeli ve düzgün doldurma görüntüler. Bu bayrak olmadan, denetim bloklarla doldurulur.

*Rect*<br/>
İlerleme çubuğu denetiminin boyutunu ve konumunu belirtir. Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir. Denetim bir alt pencere olması gerektiğinden, belirtilen koordinatlar *pParentWnd*istemci alanına görelidir.

*pParentWnd*<br/>
İlerleme çubuğu denetiminin üst penceresini belirtir, `CDialog`genellikle bir . NULL olmamalıdır.

*Nıd*<br/>
İlerleme çubuğu denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulursa `CProgressCtrl` DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CProgressCtrl` iki adımda inşa ee. Önce, `CProgressCtrl` nesneyi oluşturan oluşturucuyu çağırın, `Create`sonra da ilerleme çubuğu denetimini oluşturan , çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]

## <a name="cprogressctrlcreateex"></a><a name="createex"></a>CProgressCtrl::CreateEx

Denetim (alt pencere) oluşturur ve `CProgressCtrl` nesneyle ilişkilendirir.

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
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerilistesi için Windows SDK'daki [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) için *dwExStyle* parametreye bakın.

*Dwstyle*<br/>
İlerleme çubuğu denetiminin stilini belirtir. Windows SDK'da [CreateWindow'da](/windows/win32/api/winuser/nf-winuser-createwindoww) açıklanan pencere stillerinin herhangi bir birleşimini uygulayın.

*Rect*<br/>
*PParentWnd*istemci koordinatlarında oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencereye işaretçi.

*Nıd*<br/>
Denetimin alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Windows `CreateEx` genişletilmiş stil önsöz **WS_EX_** tarafından belirtilen genişletilmiş Windows stilleri uygulamak için [Oluştur](#create) yerine kullanın.

## <a name="cprogressctrlgetbarcolor"></a><a name="getbarcolor"></a>CProgressCtrl::GetBarColor

Geçerli ilerleme çubuğu denetimi için ilerleme göstergesi çubuğunun rengini alır.

```
COLORREF GetBarColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

[COLORREF](/windows/win32/gdi/colorref) değeri olarak temsil edilen geçerli ilerleme çubuğunun rengi veya ilerleme göstergesi çubuğu rengi varsayılan renkse CLR_DEFAULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PBM_GETBARCOLOR](/windows/win32/Controls/pbm-getbarcolor) iletisini gönderir.

## <a name="cprogressctrlgetbkcolor"></a><a name="getbkcolor"></a>CProgressCtrl::GetBkColor

Geçerli ilerleme çubuğunun arka plan rengini alır.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

[COLORREF](/windows/win32/gdi/colorref) değeri olarak temsil edilen geçerli ilerleme çubuğunun arka plan rengi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PBM_GETBKCOLOR](/windows/win32/Controls/pbm-getbkcolor) iletisini gönderir.

## <a name="cprogressctrlgetpos"></a><a name="getpos"></a>CProgressCtrl::GetPos

İlerleme çubuğunun geçerli konumunu alır.

```
int GetPos();
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu denetiminin konumu.

### <a name="remarks"></a>Açıklamalar

İlerleme çubuğu denetiminin konumu ekrandaki fiziksel konum değil, [SetRange'de](#setrange)belirtilen üst ve alt aralık arasındadır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]

## <a name="cprogressctrlgetrange"></a><a name="getrange"></a>CProgressCtrl::GetRange

İlerleme çubuğu denetiminin geçerli alt ve üst sınırlarını veya aralığını alır.

```cpp
void GetRange(
    int& nLower,
    int& nUpper);
```

### <a name="parameters"></a>Parametreler

*nLower*<br/>
İlerleme çubuğu denetiminin alt sınırını alan bir tamsayıya başvuru.

*nUpper*<br/>
İlerleme çubuğu denetiminin üst sınırını alan bir tamsayıya başvuru.

### <a name="remarks"></a>Açıklamalar

Bu işlev, sırasıyla *nLower* ve *nUpper*tarafından başvurulan tamsayılara alt ve üst sınırların değerlerini kopyalar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]

## <a name="cprogressctrlgetstate"></a><a name="getstate"></a>CProgressCtrl::GetState

Geçerli ilerleme çubuğu denetiminin durumunu alır.

```
int GetState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri olan geçerli ilerleme çubuğu denetiminin durumu:

|Değer|Durum|
|-----------|-----------|
|PBST_NORMAL|Devam ediyor|
|PBST_ERROR|Hata|
|PBST_PAUSED|Duraklatıldı|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PBM_GETSTATE](/windows/win32/Controls/pbm-getstate) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_progressCtrl`ilerleme çubuğu denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli ilerleme çubuğu denetiminin durumunu alır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]

## <a name="cprogressctrlgetstep"></a><a name="getstep"></a>CProgressCtrl::GetStep

Geçerli ilerleme çubuğu denetiminin ilerleme çubuğu için adım artışını alır.

```
int GetStep() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğunun adım artış.

### <a name="remarks"></a>Açıklamalar

Adım artış miktarı olan CProgressCtrl için bir [çağrı::StepIt](#stepit) ilerleme çubuğunun geçerli konumunu artırır.

Bu yöntem, Windows SDK'da açıklanan [PBM_GETSTEP](/windows/win32/Controls/pbm-getstep) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_progressCtrl`ilerleme çubuğu denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli ilerleme çubuğu denetiminin adım artışını alır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]

## <a name="cprogressctrloffsetpos"></a><a name="offsetpos"></a>CProgressCtrl::OfsetPos

İlerleme çubuğu denetiminin geçerli konumunu *nPos* tarafından belirtilen artışla ilerletin ve çubuğu yeni konumu yansıtacak şekilde yeniden çizer.

```
int OffsetPos(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Pozisyon avans miktarı.

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu denetiminin önceki konumu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]

## <a name="cprogressctrlsetbarcolor"></a><a name="setbarcolor"></a>CProgressCtrl::SetBarColor

Geçerli ilerleme çubuğu denetiminde ilerleme göstergesi çubuğunun rengini ayarlar.

```
COLORREF SetBarColor(COLORREF clrBar);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*clrBar*|[içinde] İlerleme göstergesi çubuğunun yeni rengini belirten bir [COLORREF](/windows/win32/gdi/colorref) değeri. İlerleme çubuğunun varsayılan rengini kullanmasına neden olacak CLR_DEFAULT belirtin.|

### <a name="return-value"></a>Dönüş Değeri

COLORREF değeri olarak temsil edilen ilerleme [COLORREF](/windows/win32/gdi/colorref) göstergesi çubuğunun önceki rengi veya ilerleme göstergesi çubuğunun rengi varsayılan renk sayılsa CLR_DEFAULT.

### <a name="remarks"></a>Açıklamalar

Yöntem, `SetBarColor` yalnızca Windows Vista [teması](/windows/win32/Controls/visual-styles-overview) etkin değilse ilerleme çubuğu rengini ayarlar.

Bu yöntem, Windows SDK'da açıklanan [PBM_SETBARCOLOR](/windows/win32/Controls/pbm-setbarcolor) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_progressCtrl`ilerleme çubuğu denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, ilerleme çubuğunun rengini kırmızı, yeşil, mavi veya varsayılan olarak değiştirir.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]

## <a name="cprogressctrlsetbkcolor"></a><a name="setbkcolor"></a>CProgressCtrl::SetBkColor

İlerleme çubuğunun arka plan rengini ayarlar.

```
COLORREF SetBkColor(COLORREF clrNew);
```

### <a name="parameters"></a>Parametreler

*clrYeni*<br/>
Yeni arka plan rengini belirten bir COLORREF değeri. İlerleme çubuğu için varsayılan arka plan rengini kullanmak için CLR_DEFAULT değerini belirtin.

### <a name="return-value"></a>Dönüş Değeri

Önceki arka plan rengini gösteren [COLORREF](/windows/win32/gdi/colorref) değeri veya arka plan rengi varsayılan renk olup olmadığını CLR_DEFAULT.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]

## <a name="cprogressctrlsetmarquee"></a><a name="setmarquee"></a>CProgressCtrl::SetMarquee

Geçerli ilerleme çubuğu denetimi için seçim çerçevesi modunu açar veya kapatır.

```
BOOL SetMarquee(
    BOOL fMarqueeMode,
    int nInterval);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*fMarqueeMode*|[içinde] Seçim çerçevesi modunu açmak için TRUE veya seçim çerçevesi modunu kapatmak için FALSE.|
|*nInterval*|[içinde] Seçim çerçevesi animasyongüncelleştirmeleri arasında milisaniye cinsinden zaman.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Seçim çerçevesi modu açık olduğunda, ilerleme çubuğu animasyonlur ve bir tiyatro çerçevesi üzerinde bir işaret gibi kaydırılır.

Bu yöntem, Windows SDK'da açıklanan [PBM_SETMARQUEE](/windows/win32/Controls/pbm-setmarquee) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_progressCtrl`ilerleme çubuğu denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, seçim çerçevesi kaydırma animasyonuna başlar ve durur.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]

## <a name="cprogressctrlsetpos"></a><a name="setpos"></a>CProgressCtrl::SetPos

Progress çubuğu denetiminin geçerli konumunu *nPos* tarafından belirtildiği şekilde ayarlar ve çubuğu yeni konumu yansıtacak şekilde yeniden çizer.

```
int SetPos(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
İlerleme çubuğu denetiminin yeni konumu.

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu denetiminin önceki konumu.

### <a name="remarks"></a>Açıklamalar

İlerleme çubuğu denetiminin konumu ekrandaki fiziksel konum değil, [SetRange'de](#setrange)belirtilen üst ve alt aralık arasındadır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]

## <a name="cprogressctrlsetrange"></a><a name="setrange"></a>CProgressCtrl::SetAralığı

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
Aralığın alt sınırını belirtir (varsayılan değer sıfırdır).

*nUpper*<br/>
Aralığın üst sınırını belirtir (varsayılan değer 100'dür).

### <a name="remarks"></a>Açıklamalar

Üye işlev, `SetRange32` ilerleme denetimi için 32 bit aralığını ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]

## <a name="cprogressctrlsetstate"></a><a name="setstate"></a>CProgressCtrl::SetState

Geçerli ilerleme çubuğu denetiminin durumunu ayarlar.

```
int SetState(int iState);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iDevlet*|[içinde] İlerleme çubuğunu belirleyecek eyalet. Aşağıdaki değerlerden birini kullanın:<br /><br /> - PBST_NORMAL - Devam Ediyor<br />- PBST_ERROR - Hata<br />- PBST_PAUSED - Duraklatıldı|

### <a name="return-value"></a>Dönüş Değeri

Geçerli ilerleme çubuğu denetiminin önceki durumu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [PBM_SETSTATE](/windows/win32/Controls/pbm-setstate) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_progressCtrl`ilerleme çubuğu denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli ilerleme çubuğu denetiminin durumunu Duraklatılmış veya Devam Eden olarak ayarlar.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]

## <a name="cprogressctrlsetstep"></a><a name="setstep"></a>CProgressCtrl::SetStep

İlerleme çubuğu denetimi için adım artışını belirtir.

```
int SetStep(int nStep);
```

### <a name="parameters"></a>Parametreler

*nAdım*<br/>
Yeni adım artış.

### <a name="return-value"></a>Dönüş Değeri

Önceki adım artış.

### <a name="remarks"></a>Açıklamalar

Adım artış, ilerleme çubuğunun geçerli konumunu `CProgressCtrl::StepIt` artırma çağrısının miktarıdır.

Varsayılan adım artış 10'dur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]

## <a name="cprogressctrlstepit"></a><a name="stepit"></a>CProgressCtrl::AdımIt

İlerleme çubuğu denetimi için geçerli konumu adım adım artışla ilerletin ve çubuğu yeni konumu yansıtacak şekilde yeniden çizer.

```
int StepIt();
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu denetiminin önceki konumu.

### <a name="remarks"></a>Açıklamalar

Adım artış `CProgressCtrl::SetStep` üye işlevi tarafından ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Numune CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
