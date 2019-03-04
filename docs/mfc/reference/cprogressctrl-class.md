---
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
ms.openlocfilehash: a6d5d3becfd1c1ee4a032c74eb116ede82c42bc4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260276"
---
# <a name="cprogressctrl-class"></a>CProgressCtrl sınıfı

Windows ortak ilerleme çubuğu denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CProgressCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|Oluşturur bir `CProgressCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CProgressCtrl::Create](#create)|Bir ilerleme çubuğu denetimi oluşturur ve ona bağlanan bir `CProgressCtrl` nesne.|
|[CProgressCtrl::CreateEx](#createex)|İlerleme denetimi ile belirtilen Windows genişletilmiş stiller oluşturur ve ona ekler bir `CProgressCtrl` nesne.|
|[CProgressCtrl::GetBarColor](#getbarcolor)|İlerleme göstergesi çubuğu rengi geçerli ilerleme çubuğu denetimi için alır.|
|[CProgressCtrl::GetBkColor](#getbkcolor)|Geçerli ilerleme çubuğu arka plan rengini alır.|
|[CProgressCtrl::GetPos](#getpos)|İlerleme çubuğu geçerli konumunu alır.|
|[CProgressCtrl::GetRange](#getrange)|İlerleme çubuğu denetiminin aralığın alt ve üst sınırları alır.|
|[CProgressCtrl::GetState](#getstate)|Geçerli ilerleme çubuğu denetimi durumunu alır.|
|[CProgressCtrl::GetStep](#getstep)|İlerleme çubuğu geçerli ilerleme çubuğu denetimi için adım artırma alır.|
|[CProgressCtrl::OffsetPos](#offsetpos)|Belirtilen bir artışla bir ilerleme çubuğu denetiminin geçerli konumu ilerler ve çubuğundaki yeni konumunu gösterecek şekilde yeniden çizer.|
|[CProgressCtrl::SetBarColor](#setbarcolor)|İlerleme göstergesi çubuğu rengi geçerli ilerleme çubuğu denetimi ayarlar.|
|[CProgressCtrl::SetBkColor](#setbkcolor)|İlerleme çubuğu arka plan rengini ayarlar.|
|[CProgressCtrl::SetMarquee](#setmarquee)|Geçerli ilerleme çubuğu denetimi için kayan modunu açar veya kapatır.|
|[CProgressCtrl::SetPos](#setpos)|Geçerli konum bir ilerleme çubuğu denetimi için ayarlar ve çubuğundaki yeni konumunu gösterecek şekilde yeniden çizer.|
|[CProgressCtrl::SetRange](#setrange)|Minimum ve maksimum aralıkları bir ilerleme çubuğu denetimi için ayarlar ve çubuğundaki yeni aralıklar yansıtacak şekilde yeniden çizer.|
|[CProgressCtrl::SetState](#setstate)|Geçerli ilerleme çubuğu denetimi durumunu ayarlar.|
|[CProgressCtrl::SetStep](#setstep)|Adım artış için bir ilerleme çubuğu denetimi belirtir.|
|[CProgressCtrl::StepIt](#stepit)|İlerleme çubuğu denetiminin geçerli konumu adım artışla ilerler (bkz [SetStep](#setstep)) ve çubuğundaki yeni konumunu gösterecek şekilde yeniden çizer.|

## <a name="remarks"></a>Açıklamalar

Bir ilerleme çubuğu denetimi bir uygulamayı uzun bir işlemin ilerlemesini göstermek için kullanabileceğiniz bir penceredir. Aşamalı olarak, soldan sağa, renk sistemiyle işlem ilerledikçe vurgulamak için doldurulmuş bir dikdörtgen oluşur.

Bir ilerleme çubuğu denetimi, aralık ve geçerli bir konum vardır. Toplam işlem süresi aralığını temsil eder ve geçerli konumu uygulama işlemi tamamlamaya yönelik yapılan ilerleme durumunu temsil eder. Pencere yordamı, aralık ve geçerli konumu Vurgu rengi ile doldurmak için ilerleme çubuğu yüzdesini belirlemek için kullanır. Geçerli konum değerleri ve aralığı imzalı tamsayı olarak ifade edilir çünkü olası geçerli konum değerleri -2.147.483.648 ila 2.147.483.647 arasında kapsamlı aralığıdır.

Kullanma hakkında daha fazla bilgi için `CProgressCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [CProgressCtrl kullanma](../../mfc/using-cprogressctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CProgressCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

##  <a name="cprogressctrl"></a>  CProgressCtrl::CProgressCtrl

Oluşturur bir `CProgressCtrl` nesne.

```
CProgressCtrl();
```

### <a name="remarks"></a>Açıklamalar

Oluşturma sonrasında `CProgressCtrl` nesne, çağrı `CProgressCtrl::Create` ilerleme çubuğu denetimi oluşturmak için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]

##  <a name="create"></a>  CProgressCtrl::Create

Bir ilerleme çubuğu denetimi oluşturur ve ona bağlanan bir `CProgressCtrl` nesne.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
İlerleme çubuğu denetiminin stilini belirtir. Uygulama penceresi stylesdescribed içinde herhangi bir birleşimini [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) aşağıdaki ilerleme çubuğu denetimi için denetim stilleri yanı sıra Windows SDK:

- Pbs_vertıcal görüntüler dikey ilerleme bilgileri, en alt kısma. Bu bayrağı olmadan ilerleme çubuğu denetimi, yatay, soldan sağa görüntüler.

- PBS_SMOOTH görüntüler gradual, ilerleme çubuğu denetimi doldurma kesintisiz. Bu bayrak olmadan, denetim blokları ile doldurur.

*Rect*<br/>
İlerleme çubuğu denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı. Denetimi alt pencere olması gerektiğinden, belirtilen koordinatlara göre istemci alanının olan *pParentWnd*.

*pParentWnd*<br/>
İlerleme çubuğu denetiminin üst penceresine, genellikle belirtir bir `CDialog`. NULL olmamalıdır.

*nID*<br/>
İlerleme çubuğu denetimin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

TRUE ise `CProgressCtrl` nesne başarıyla oluşturuldu; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CProgressCtrl` iki adımda nesne. İlk olarak, oluşturan oluşturucu çağrısı `CProgressCtrl` nesnesi ve ardından arama `Create`, ilerleme çubuğu denetimi oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]

##  <a name="createex"></a>  CProgressCtrl::CreateEx

Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CProgressCtrl` nesne.

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
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri bir listesi için bkz. *dwExStyle* parametresi için [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK.

*dwStyle*<br/>
İlerleme çubuğu denetiminin stilini belirtir. Herhangi bir birleşimini açıklanan pencere stilleri uygulamak [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) Windows SDK.

*Rect*<br/>
Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları olarak oluşturulması için pencerenin konumunu ve boyutunu açıklayan yapısı *pParentWnd*.

*pParentWnd*<br/>
Denetimin ana penceresine bir işaretçi.

*nID*<br/>
Denetimin alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kullanım `CreateEx` yerine [Oluştur](#create) Windows genişletilmiş sitil önsöz tarafından belirtilen Genişletilmiş Windows stilleri uygulamak için **WS_EX_**.

##  <a name="getbarcolor"></a>  CProgressCtrl::GetBarColor

İlerleme göstergesi çubuğu rengi geçerli ilerleme çubuğu denetimi için alır.

```
COLORREF GetBarColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir ilerleme çubuğu rengi temsil olarak bir [COLORREF](/windows/desktop/gdi/colorref) değeri ya da İlerleme göstergesi çubuğu rengi kullanılan varsayılan rengi ise CLR_DEFAULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PBM_GETBARCOLOR](/windows/desktop/Controls/pbm-getbarcolor) Windows SDK'da açıklanan ileti.

##  <a name="getbkcolor"></a>  CProgressCtrl::GetBkColor

Geçerli ilerleme çubuğu arka plan rengini alır.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arka plan rengi geçerli ilerleme çubuğu olarak temsil bir [COLORREF](/windows/desktop/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PBM_GETBKCOLOR](/windows/desktop/Controls/pbm-getbkcolor) Windows SDK'da açıklanan ileti.

##  <a name="getpos"></a>  CProgressCtrl::GetPos

İlerleme çubuğu geçerli konumunu alır.

```
int GetPos();
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu denetimi konumu.

### <a name="remarks"></a>Açıklamalar

İlerleme çubuğu denetiminin konumunu ekranında fiziksel konumu değildir, ancak yerine arasındaki üst ve alt aralığı belirtilen [SetRange](#setrange).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]

##  <a name="getrange"></a>  CProgressCtrl::GetRange

Geçerli alt ve üst sınırlarını veya dizi ilerleme çubuğu denetimi alır.

```
void GetRange(
    int& nLower,
    int& nUpper);
```

### <a name="parameters"></a>Parametreler

*nLower*<br/>
Bir başvuru alma alt sınırı ilerleme çubuğu denetiminin bir tamsayı.

*nUpper*<br/>
İlerleme çubuğu denetiminin üst sınırını alma tamsayı başvuru.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından başvurulan tamsayı değerleri alt ve üst sınırlarını kopyalar *nLower* ve *nUpper*sırasıyla.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]

##  <a name="getstate"></a>  CProgressCtrl::GetState

Geçerli ilerleme çubuğu denetimi durumunu alır.

```
int GetState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri geçerli ilerleme çubuğu denetimi durumu:

|Değer|Durum|
|-----------|-----------|
|PBST_NORMAL|Sürüyor|
|PBST_ERROR|Hata|
|PBST_PAUSED|Duraklatıldı|

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PBM_GETSTATE](/windows/desktop/Controls/pbm-getstate) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_progressCtrl`, yani ilerleme çubuğu denetimi programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli ilerleme çubuğu denetimi durumunu alır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]

##  <a name="getstep"></a>  CProgressCtrl::GetStep

İlerleme çubuğu geçerli ilerleme çubuğu denetimi için adım artırma alır.

```
int GetStep() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğunun adım artırma.

### <a name="remarks"></a>Açıklamalar

Adım artırma tutarı olan bir çağrı [CProgressCtrl::StepIt](#stepit) ilerleme çubuğu geçerli konumunu artırır.

Bu yöntem gönderir [PBM_GETSTEP](/windows/desktop/Controls/pbm-getstep) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_progressCtrl`, yani ilerleme çubuğu denetimi programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli ilerleme çubuğu denetiminin adım artırma alır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]

##  <a name="offsetpos"></a>  CProgressCtrl::OffsetPos

İlerleme çubuğu denetiminin geçerli konumu tarafından belirtilen artış ilerler *nPos* ve çubuğundaki yeni konumunu gösterecek şekilde yeniden çizer.

```
int OffsetPos(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Konumuna ilerleyin tutar.

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu denetimi önceki konumu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]

##  <a name="setbarcolor"></a>  CProgressCtrl::SetBarColor

İlerleme göstergesi çubuğu rengi geçerli ilerleme çubuğu denetimi ayarlar.

```
COLORREF SetBarColor(COLORREF clrBar);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*clrBar*|[in] A [COLORREF](/windows/desktop/gdi/colorref) İlerleme göstergesi yeni rengini belirten bir değer. Varsayılan rengini kullanılacak ilerleme çubuğu neden CLR_DEFAULT belirtin.|

### <a name="return-value"></a>Dönüş Değeri

İlerleme göstergesi önceki rengi temsil olarak bir [COLORREF](/windows/desktop/gdi/colorref) değeri ya da İlerleme göstergesi rengini varsayılan rengi ise CLR_DEFAULT.

### <a name="remarks"></a>Açıklamalar

`SetBarColor` Yöntemini ayarlar ilerleme çubuğu renk yalnızca şu durumlarda bir Windows Vista [tema](/windows/desktop/Controls/visual-styles-overview) etkili değildir.

Bu yöntem gönderir [PBM_SETBARCOLOR](/windows/desktop/Controls/pbm-setbarcolor) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_progressCtrl`, yani ilerleme çubuğu denetimi programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, kırmızı, yeşil, mavi veya varsayılan ilerleme çubuğu rengini değiştirir.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]

##  <a name="setbkcolor"></a>  CProgressCtrl::SetBkColor

İlerleme çubuğu arka plan rengini ayarlar.

```
COLORREF SetBkColor(COLORREF clrNew);
```

### <a name="parameters"></a>Parametreler

*clrNew*<br/>
Yeni arka plan rengini belirtir COLORREF değeri. Varsayılan arka plan rengi ilerleme çubuğu için kullanılacak CLR_DEFAULT değeri belirtin.

### <a name="return-value"></a>Dönüş Değeri

[COLORREF](/windows/desktop/gdi/colorref) arka plan rengini varsayılan rengi ise önceki arka plan rengi veya CLR_DEFAULT belirten değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]

##  <a name="setmarquee"></a>  CProgressCtrl::SetMarquee

Geçerli ilerleme çubuğu denetimi için kayan modunu açar veya kapatır.

```
BOOL SetMarquee(
    BOOL fMarqueeMode,
    int nInterval);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*fMarqueeMode*|[in] Açık veya kayan modu devre dışı bırakmak için FALSE dönüş çerçevesi modu için true.|
|*Naralık*|[in] Güncelleştirmeleri çerçevesi animasyonun arasındaki milisaniye cinsinden süre.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem, her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Kayan modu açık, İlerleme çubuğunda bir animasyon görünür ve kayarken ister bir oturum açma tiyatro çerçevesi.

Bu yöntem gönderir [PBM_SETMARQUEE](/windows/desktop/Controls/pbm-setmarquee) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_progressCtrl`, yani ilerleme çubuğu denetimi programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, başlatır ve kaydırma animasyon çerçevesini durdurur.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]

##  <a name="setpos"></a>  CProgressCtrl::SetPos

İlerleme çubuğu denetiminin geçerli konumu tarafından belirtilen ayarlar *nPos* ve çubuğundaki yeni konumunu gösterecek şekilde yeniden çizer.

```
int SetPos(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
İlerleme çubuğu denetimi yeni konumu.

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu denetimi önceki konumu.

### <a name="remarks"></a>Açıklamalar

İlerleme çubuğu denetiminin konumunu ekranında fiziksel konumu değildir, ancak yerine arasındaki üst ve alt aralığı belirtilen [SetRange](#setrange).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]

##  <a name="setrange"></a>  CProgressCtrl::SetRange

İlerleme çubuğu denetiminin aralık alt ve üst sınırlarını tanımlar ve çubuğundaki yeni aralıklar yansıtacak şekilde yeniden çizer.

```
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Parametreler

*nLower*<br/>
Aralığın alt sınırını belirtir (varsayılan değer sıfır).

*nUpper*<br/>
Aralık sayısı üst sınırını belirtir (varsayılan değer 100).

### <a name="remarks"></a>Açıklamalar

Üye işlevi `SetRange32` 32-bit aralığın ilerleme denetimi için ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]

##  <a name="setstate"></a>  CProgressCtrl::SetState

Geçerli ilerleme çubuğu denetimi durumunu ayarlar.

```
int SetState(int iState);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iState*|[in] İlerleme çubuğu ayarlanacak durumu. Aşağıdaki değerlerden birini kullanın:<br /><br /> -İlerleme PBST_NORMAL-<br />-PBST_ERROR - hata<br />-PBST_PAUSED - duraklatıldı|

### <a name="return-value"></a>Dönüş Değeri

Geçerli ilerleme çubuğu denetimi önceki durumu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [PBM_SETSTATE](/windows/desktop/Controls/pbm-setstate) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_progressCtrl`, yani ilerleme çubuğu denetimi programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, duraklatıldı ya da sürüyor geçerli ilerleme çubuğu denetimi durumunu ayarlar.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]

##  <a name="setstep"></a>  CProgressCtrl::SetStep

Adım artış için bir ilerleme çubuğu denetimi belirtir.

```
int SetStep(int nStep);
```

### <a name="parameters"></a>Parametreler

*nStep*<br/>
Yeni adım artırma.

### <a name="return-value"></a>Dönüş Değeri

Önceki adım artırma.

### <a name="remarks"></a>Açıklamalar

Adım artırma tutarı olan bir çağrı `CProgressCtrl::StepIt` ilerleme artırır çubuk geçerli konumu kullanıcının.

Varsayılan adım artırma 10'dur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]

##  <a name="stepit"></a>  CProgressCtrl::StepIt

İlerleme çubuğu denetiminin geçerli konumu adım artışla ilerler ve çubuğundaki yeni konumunu gösterecek şekilde yeniden çizer.

```
int StepIt();
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu denetimi önceki konumu.

### <a name="remarks"></a>Açıklamalar

Adım artırma belirlediği `CProgressCtrl::SetStep` üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CMNCTRL2](../../visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
