---
description: 'Daha fazla bilgi edinin: CPaintDC Class'
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
ms.openlocfilehash: cb8f3b81615390ab6af8e9a244a95f91a3b3f96c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345218"
---
# <a name="cpaintdc-class"></a>CPaintDC sınıfı

[CDC](../../mfc/reference/cdc-class.md)'den türetilmiş bir cihaz bağlamı sınıfı.

## <a name="syntax"></a>Syntax

```
class CPaintDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPaintDC:: CPaintDC](#cpaintdc)|`CPaintDC`Belirtilen [CWnd](../../mfc/reference/cwnd-class.md)'e bağlı bir yapı oluşturur.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPaintDC:: m_ps](#m_ps)|İstemci alanını boyamak için kullanılan [PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct) içerir.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPaintDC:: m_hWnd](#m_hwnd)|Bu `CPaintDC` nesnenin EKLENDIĞI HWND.|

## <a name="remarks"></a>Açıklamalar

Oluşturma zamanında bir [CWnd:: BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) ve yok etme sırasında [CWnd:: EndPaint](../../mfc/reference/cwnd-class.md#endpaint) gerçekleştirir.

Bir `CPaintDC` nesne, genellikle [](/windows/win32/gdi/wm-paint) `OnPaint` ileti işleyici üye işlevinizde bir WM_PAINT iletisine yanıt verme sırasında kullanılabilir.

Kullanma hakkında daha fazla bilgi için `CPaintDC` bkz. [cihaz bağlamları](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cpaintdccpaintdc"></a><a name="cpaintdc"></a> CPaintDC:: CPaintDC

Bir `CPaintDC` nesne oluşturur, boyama için uygulama penceresini hazırlar ve [paıntstruct](/windows/win32/api/winuser/ns-winuser-paintstruct) yapısını [m_ps](#m_ps) üye değişkeninde depolar.

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
`CWnd` `CPaintDC` Nesnenin ait olduğu nesnesine işaret eder.

### <a name="remarks"></a>Açıklamalar

`CResourceException`Windows [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) çağrısı başarısız olursa bir özel durum (tür) oluşturulur. Windows, tüm kullanılabilir cihaz bağlamlarını zaten ayırmışsa bir cihaz bağlamı kullanılamayabilir. Uygulamanız, Windows altında herhangi bir zamanda kullanılabilir olan beş ortak görüntü bağlamına sahiptir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

## <a name="cpaintdcm_hwnd"></a><a name="m_hwnd"></a> CPaintDC:: m_hWnd

`HWND`Bu `CPaintDC` nesnenin eklendiği yer.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Açıklamalar

*m_hWnd* , HWND türünde korunan bir değişkendir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

## <a name="cpaintdcm_ps"></a><a name="m_ps"></a> CPaintDC:: m_ps

`m_ps` , [PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct)türünde bir ortak üye değişkenidir.

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>Açıklamalar

`PAINTSTRUCT`Bu, [CWnd:: BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint)tarafından geçirilir ve doldurulur.

, `PAINTSTRUCT` Uygulamanın bir nesneyle ilişkili pencerenin istemci alanını boyamak için kullandığı bilgileri içerir `CPaintDC` .

Üzerinden cihaz bağlamı tanıtıcısına erişebileceğinizi unutmayın `PAINTSTRUCT` . Ancak, tanıtıcıya, `m_hDC` CDC 'den devralan üye değişkeni aracılığıyla doğrudan erişebilirsiniz `CPaintDC` .

### <a name="example"></a>Örnek

  [CPaintDC:: m_hWnd](#m_hwnd)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
