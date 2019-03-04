---
title: CPaintDC sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
ms.openlocfilehash: 5dbe08eae911433c256d3f8dd1f60dea2db9478c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274433"
---
# <a name="cpaintdc-class"></a>CPaintDC sınıfı

Türetilen cihaz içeriği sınıfı [CDC](../../mfc/reference/cdc-class.md).

## <a name="syntax"></a>Sözdizimi

```
class CPaintDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPaintDC::CPaintDC](#cpaintdc)|Oluşturur bir `CPaintDC` belirtilen bağlı [CWnd](../../mfc/reference/cwnd-class.md).|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPaintDC::m_ps](#m_ps)|İçeren [PAINTSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagpaintstruct) istemci alanını boyamak için kullanılan.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPaintDC::m_hWnd](#m_hwnd)|Bu HWND `CPaintDC` nesne eklenmiş olmasıdır.|

## <a name="remarks"></a>Açıklamalar

Bunu gerçekleştiren bir [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) oluşturma zamanında ve [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) yok etme.

A `CPaintDC` nesne, yalnızca yanıt vermek kullanılabilir bir [WM_PAINT](/windows/desktop/gdi/wm-paint) ileti genellikle, `OnPaint` ileti işleyicisi üye işlevi.

Kullanma hakkında daha fazla bilgi için `CPaintDC`, bkz: [cihaz bağlamları](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cpaintdc"></a>  CPaintDC::CPaintDC

Oluşturur bir `CPaintDC` nesne, uygulama penceresinin boyama için hazırlar ve depolar [PAINTSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagpaintstruct) içindeki yapı [m_ps](#m_ps) üye değişkeni.

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İşaret `CWnd` nesne `CPaintDC` nesnesi aittir.

### <a name="remarks"></a>Açıklamalar

Bir özel durum (tür `CResourceException`) oluşturulur Windows [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc) çağrısı başarısız olur. Bir cihaz bağlamı Windows zaten tüm kendi kullanılabilir cihaz bağlamları ayırdığı kullanılabilir olmayabilir. Uygulamanız için beş ortak görüntü bağlamlarında kullanılabilir Windows altında herhangi bir belirli zamanda rekabet.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CPaintDC::m_hWnd

`HWND` Bu `CPaintDC` nesne eklenmiş olmasıdır.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Açıklamalar

*m_hWnd* türü HWND korumalı bir değişkendir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

##  <a name="m_ps"></a>  CPaintDC::m_ps

`m_ps` bir tür ortak üye değişkendir [PAINTSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagpaintstruct).

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>Açıklamalar

Bu `PAINTSTRUCT` geçirilecek ve tarafından doldurulmalıdır [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint).

`PAINTSTRUCT` Uygulama ile ilişkili bir pencerenin istemci alanının boyamak için kullandığı bilgileri içeren bir `CPaintDC` nesne.

Cihaz bağlamı tanıtıcı aracılığıyla erişebileceğiniz Not `PAINTSTRUCT`. Ancak, tanıtıcı aracılığıyla doğrudan erişebilir `m_hDC` üye değişkeni, `CPaintDC` CDC devralır.

### <a name="example"></a>Örnek

  Örneğin bakın [CPaintDC::m_hWnd](#m_hwnd).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../visual-cpp-samples.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
