---
title: CClientDC sınıfı
ms.date: 11/04/2016
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
ms.openlocfilehash: a67af5d7d82b8bd7d0490d4ae6f9535bf3283ea2
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58766774"
---
# <a name="cclientdc-class"></a>CClientDC sınıfı

Windows işlevlerini çağırma üstlenir [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc) oluşturma zamanında ve [ReleaseDC](/windows/desktop/api/winuser/nf-winuser-releasedc) yok etme.

## <a name="syntax"></a>Sözdizimi

```
class CClientDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CClientDC::CClientDC](#cclientdc)|Oluşturur bir `CClientDC` bağlı nesne `CWnd`.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CClientDC::m_hWnd](#m_hwnd)|Bu pencerenin HWND `CClientDC` geçerlidir.|

## <a name="remarks"></a>Açıklamalar

Cihaz bağlamı ile ilişkili buna bir `CClientDC` pencerenin istemci alanını nesnedir.

Daha fazla bilgi için `CClientDC`, bkz: [cihaz bağlamları](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cclientdc"></a>  CClientDC::CClientDC

Oluşturur bir `CClientDC` erişen istemci alanının nesne [CWnd](../../mfc/reference/cwnd-class.md) işaret ettiği *pWnd*.

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Pencere istemci alanını cihaz bağlamındaki erişim sağlar.

### <a name="remarks"></a>Açıklamalar

Windows işlevi oluşturucuyu çağırır [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc).

Bir özel durum (tür `CResourceException`) oluşturulur Windows `GetDC` çağrısı başarısız olur. Bir cihaz bağlamı Windows zaten tüm kendi kullanılabilir cihaz bağlamları ayırdığı kullanılabilir olmayabilir. Uygulamanız için beş ortak görüntü bağlamlarında kullanılabilir Windows altında herhangi bir belirli zamanda rekabet.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CClientDC::m_hWnd

`HWND` , `CWnd` İşaretçi oluşturmak için kullanılan `CClientDC` nesne.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Açıklamalar

*m_hWnd* korumalı bir değişkendir.

### <a name="example"></a>Örnek

  Örneğin bakın [CClientDC::CClientDC](#cclientdc).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)
