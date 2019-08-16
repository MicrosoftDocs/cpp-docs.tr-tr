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
ms.openlocfilehash: 46428740d052c70218d4443395777428cdf3c3b0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507334"
---
# <a name="cclientdc-class"></a>CClientDC sınıfı

Oluşturma sırasında [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) Windows işlevleri ve yok etme sırasında [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) çağırma işlemini gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```
class CClientDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CClientDC:: CClientDC](#cclientdc)|Öğesine bağlı `CClientDC` bir nesne oluşturur. `CWnd`|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CClientDC:: m_hWnd](#m_hwnd)|Bunun `CClientDC` geçerli olduğu pencerenin HWND 'si.|

## <a name="remarks"></a>Açıklamalar

Bu, bir `CClientDC` nesneyle ilişkili cihaz bağlamının bir pencerenin istemci alanı olduğu anlamına gelir.

Hakkında `CClientDC`daha fazla bilgi için bkz. [cihaz bağlamları](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="cclientdc"></a>CClientDC:: CClientDC

`CClientDC` *PWnd*tarafından işaret edilen [CWnd](../../mfc/reference/cwnd-class.md) 'ın istemci alanına erişen bir nesne oluşturur.

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İstemci alanı cihaz bağlamı nesnesine erişecek olan pencere.

### <a name="remarks"></a>Açıklamalar

Oluşturucu, [GetDC](/windows/win32/api/winuser/nf-winuser-getdc)Windows işlevini çağırır.

`CResourceException` Windows`GetDC` çağrısı başarısız olursa bir özel durum (tür) oluşturulur. Windows, tüm kullanılabilir cihaz bağlamlarını zaten ayırmışsa bir cihaz bağlamı kullanılamayabilir. Uygulamanız, Windows altında herhangi bir zamanda kullanılabilir olan beş ortak görüntü bağlamına sahiptir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

##  <a name="m_hwnd"></a>CClientDC:: m_hWnd

Nesneyi oluşturmak için kullanılan `CWnd`işaretçinin. `HWND` `CClientDC`

```
HWND m_hWnd;
```

### <a name="remarks"></a>Açıklamalar

*m_hWnd* , korumalı bir değişkendir.

### <a name="example"></a>Örnek

  [CClientDC:: CClientDC](#cclientdc)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)
