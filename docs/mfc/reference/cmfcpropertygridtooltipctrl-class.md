---
title: CMFCPropertyGridToolTipCtrl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Create
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Deactivate
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::GetLastRect
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Hide
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::SetTextMargin
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Track
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl [MFC], CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl [MFC], Create
- CMFCPropertyGridToolTipCtrl [MFC], Deactivate
- CMFCPropertyGridToolTipCtrl [MFC], GetLastRect
- CMFCPropertyGridToolTipCtrl [MFC], Hide
- CMFCPropertyGridToolTipCtrl [MFC], SetTextMargin
- CMFCPropertyGridToolTipCtrl [MFC], Track
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
ms.openlocfilehash: 94d75f914e5f7928d08dd2a87997ab02c4f16832
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361786"
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl Sınıfı

[CMFCPropertyGridCtrl Sınıfının](../../mfc/reference/cmfcpropertygridctrl-class.md) araç uçlarını görüntülemek için kullandığı bir araç ipucu denetimi uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPropertyGridToolTipCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|Bir `CMFCPropertyGridToolTipCtrl` nesne inşa eder.|
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCPropertyGridToolTipCtrl::Oluştur](#create)|Araç ucu denetimi için bir pencere oluşturur.|
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|Araç ucu denetimini devre dışı bırakır ve gizler.|
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Araç ucu denetiminin son konumunun koordinatlarını verir.|
|[CMFCPropertyGridToolTipCtrl::Gizle](#hide)|Araç ucu denetimini gizler.|
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|[CWinApp](../../mfc/reference/cwinapp-class.md) sınıfı tarafından, pencere iletilerini [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine gönderilmeden önce çevirmek için kullanılır. [(CWnd geçersiz kılar::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|Araç ucu metni ile araç ipucu penceresinin kenarlığı arasındaki aralığı ayarlar.|
|[CMFCPropertyGridToolTipCtrl::Parça](#track)|Araç ucu denetimini görüntüler.|

## <a name="remarks"></a>Açıklamalar

İşaretçi bir özellik adına dayandığında araç ipuçları görüntülenir. [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) sınıfı, kullanıcı tarafından kolayca okunabilecek bir araç ipucu görüntüler. Genellikle, bir araç ucunun konumu işaretçinin konumuna göre belirlenir. Bu sınıfı kullanarak, araç ucu özellik adının üzerinde görünür ve özellik adının tam olarak görünür olması için doğal özellik uzantısına benzer.

MFC bu denetimi otomatik olarak oluşturur ve [CMFCPropertyGridCtrl Sınıfında](../../mfc/reference/cmfcpropertygridctrl-class.md)kullanır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCPropertyGridToolTipCtrl` nasıl oluşturulabildiğini ve araç ipucu denetiminin nasıl görüntülenebildiğini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpropertygridtooltipctrl.h

## <a name="cmfcpropertygridtooltipctrlcmfcpropertygridtooltipctrl"></a><a name="cmfcpropertygridtooltipctrl"></a>CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl

Bir `CMFCPropertyGridToolTipCtrl` nesne inşa eder.

```
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```

## <a name="cmfcpropertygridtooltipctrlcreate"></a><a name="create"></a>CMFCPropertyGridToolTipCtrl::Oluştur

Araç ucu denetimi için bir pencere oluşturur.

```
BOOL Create(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Üst pencereiçin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Pencere başarıyla oluşturulduysa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cmfcpropertygridtooltipctrldeactivate"></a><a name="deactivate"></a>CMFCPropertyGridToolTipCtrl::Deactivate

Araç ucu denetimini devre dışı bırakır ve gizler.

```
void Deactivate();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, son konumu ve metni boş değerlere ayarlar, böylece gelecekteki [cmfcPropertyGridToolTipCtrl::Araç](#track) ipucunu görüntülemeyi izleyin.

## <a name="cmfcpropertygridtooltipctrlgetlastrect"></a><a name="getlastrect"></a>CMFCPropertyGridToolTipCtrl::GetLastRect

Araç ucu denetiminin son konumunun koordinatlarını verir.

```
void GetLastRect(CRect& rect) const;
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[çıkış] Araç ucu denetiminin son konumunu içerir.

## <a name="cmfcpropertygridtooltipctrlhide"></a><a name="hide"></a>CMFCPropertyGridToolTipCtrl::Gizle

Araç ucu denetimini gizler.

```
void Hide();
```

## <a name="cmfcpropertygridtooltipctrlsettextmargin"></a><a name="settextmargin"></a>CMFCPropertyGridToolTipCtrl::SetTextMargin

Araç ucu metni ile araç ipucu penceresinin kenarlığı arasındaki aralığı ayarlar.

```
void SetTextMargin(int nTextMargin);
```

### <a name="parameters"></a>Parametreler

*nTextMargin*<br/>
[içinde] Araç ucu denetim metni ile araç ucu penceresinin kenarlığı arasındaki aralığı belirtir. Varsayılan değer 10 pikseldir.

## <a name="cmfcpropertygridtooltipctrltrack"></a><a name="track"></a>CMFCPropertyGridToolTipCtrl::Parça

Araç ucu denetimini görüntüler.

```
void Track(
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[içinde] Araç ucu denetiminin konumunu ve boyutunu belirtir.

*strText*<br/>
[içinde] Araç ipucunda gösterilecek metni belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, araç ucu denetimini *rekt*tarafından belirtilen konumda ve boyutta görüntüler. Bu yöntem çağrıldığından beri konum, boyut ve metin değişmediyse, bu yöntemin hiçbir etkisi yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
