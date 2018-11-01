---
title: CWindowDC sınıfı
ms.date: 11/04/2016
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
ms.openlocfilehash: eccea1893979c4491f7080d0d3dc980adaf19025
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553055"
---
# <a name="cwindowdc-class"></a>CWindowDC sınıfı

Türetilmiş `CDC`.

## <a name="syntax"></a>Sözdizimi

```
class CWindowDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWindowDC::CWindowDC](#cwindowdc)|Oluşturur bir `CWindowDC` nesne.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CWindowDC::m_hWnd](#m_hwnd)|Bu HWND `CWindowDC` eklenir.|

## <a name="remarks"></a>Açıklamalar

Windows işlevini çağıran [GetWindowDC](/windows/desktop/api/winuser/nf-winuser-getwindowdc)oluşturma zamanında ve [ReleaseDC](/windows/desktop/api/winuser/nf-winuser-releasedc) yok etme. Diğer bir deyişle bir `CWindowDC` nesne tüm ekran alanına eriştiği bir [CWnd](../../mfc/reference/cwnd-class.md) (hem istemci hem de istemci dışı alanlar).

Kullanma hakkında daha fazla bilgi için `CWindowDC`, bkz: [cihaz bağlamları](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>Gereksinimler

Üstbilgi: afxwin.h

##  <a name="cwindowdc"></a>  CWindowDC::CWindowDC

Oluşturur bir `CWindowDC` erişen tüm ekran alanına (hem istemci hem de istemci olmayan) nesne `CWnd` nesne tarafından işaret edilen *pWnd*.

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Penceresinin istemci alanını cihaz bağlamındaki nesne erişim sağlar.

### <a name="remarks"></a>Açıklamalar

Windows işlevi oluşturucuyu çağırır [GetWindowDC](/windows/desktop/api/winuser/nf-winuser-getwindowdc).

Bir özel durum (tür `CResourceException`) oluşturulur Windows `GetWindowDC` çağrısı başarısız olur. Bir cihaz bağlamı Windows zaten tüm kendi kullanılabilir cihaz bağlamları ayırdığı kullanılabilir olmayabilir. Uygulamanız için beş ortak görüntü bağlamlarında kullanılabilir Windows altında herhangi bir belirli zamanda rekabet.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CWindowDC::m_hWnd

HWND, `CWnd` işaretçi oluşturmak için kullanılan `CWindowDC` nesne.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Açıklamalar

`m_hWnd` HWND türündeki korumalı bir değişkendir.

### <a name="example"></a>Örnek

  Örneğin bakın [CWindowDC::CWindowDC](#cwindowdc).

## <a name="see-also"></a>Ayrıca Bkz.

[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)
