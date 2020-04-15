---
title: CPaintDC Sınıfı
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
ms.openlocfilehash: 55342b03454a6dba07bc10ea5f0464c34e0e8db3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374769"
---
# <a name="cpaintdc-class"></a>CPaintDC Sınıfı

[CDC'den](../../mfc/reference/cdc-class.md)türetilen bir aygıt bağlamı sınıfı.

## <a name="syntax"></a>Sözdizimi

```
class CPaintDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPaintDC::CPaintDC](#cpaintdc)|Belirtilen `CPaintDC` [CWnd'ye](../../mfc/reference/cwnd-class.md)bağlı bir yapı inşa eder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPaintDC::m_ps](#m_ps)|İstemci alanını boyamak için kullanılan [PAINTSTRUCT'u](/windows/win32/api/winuser/ns-winuser-paintstruct) içerir.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPaintDC::m_hWnd](#m_hwnd)|Bu `CPaintDC` nesnenin bağlı olduğu HWND.|

## <a name="remarks"></a>Açıklamalar

Bir [CWnd gerçekleştirir::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) inşaat zamanda ve [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) yıkım zamanda.

Bir `CPaintDC` nesne yalnızca [WM_PAINT](/windows/win32/gdi/wm-paint) iletisine yanıt verirken(genellikle ileti işleyicisi üye işlevinizde) `OnPaint` kullanılabilir.

Kullanma `CPaintDC`hakkında daha fazla bilgi için [Aygıt Bağlamları'na](../../mfc/device-contexts.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cpaintdccpaintdc"></a><a name="cpaintdc"></a>CPaintDC::CPaintDC

Bir `CPaintDC` nesne hazırlar, boyama için uygulama penceresini hazırlar ve [PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct) yapısını [m_ps](#m_ps) üye değişkeninde saklar.

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Nesnenin `CWnd` ait olduğu `CPaintDC` nesneyi işaret eder.

### <a name="remarks"></a>Açıklamalar

Windows [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) `CResourceException`çağrısı başarısız olursa bir özel durum (tür) atılır. Windows kullanılabilir aygıt bağlamlarının tümünü zaten tahsis etmişse aygıt bağlamı kullanılamayabilir. Uygulamanız, Windows altında herhangi bir zamanda kullanılabilen beş ortak ekran bağlamı için yarışıyor.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

## <a name="cpaintdcm_hwnd"></a><a name="m_hwnd"></a>CPaintDC::m_hWnd

Bu `HWND` `CPaintDC` nesnenin bağlı olduğu yer.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Açıklamalar

*m_hWnd* HWND tipi korumalı bir değişkendir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

## <a name="cpaintdcm_ps"></a><a name="m_ps"></a>CPaintDC::m_ps

`m_ps`[paintstruct](/windows/win32/api/winuser/ns-winuser-paintstruct)türünde bir ortak üye değişkendir.

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>Açıklamalar

Bu geçer ve [CWnd tarafından doldurulur::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint). `PAINTSTRUCT`

Uygulamanın `PAINTSTRUCT` bir `CPaintDC` nesneyle ilişkili pencerenin istemci alanını boyamak için kullandığı bilgileri içerir.

Aygıt bağlamı koluna `PAINTSTRUCT`. Ancak, cdc'den `m_hDC` `CPaintDC` devralan üye değişken aracılığıyla işleme daha doğrudan erişebilirsiniz.

### <a name="example"></a>Örnek

  CPaintDC örneğine [bakın:m_hWnd.](#m_hwnd)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
