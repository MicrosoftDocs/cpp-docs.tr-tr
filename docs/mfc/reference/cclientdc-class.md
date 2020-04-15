---
title: CClientDC Sınıfı
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
ms.openlocfilehash: abe8a3220fd37a0375fcf37504c715edf4c6962e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352303"
---
# <a name="cclientdc-class"></a>CClientDC Sınıfı

Windows [işlevlerigetDC'yi](/windows/win32/api/winuser/nf-winuser-getdc) inşaat zamanında ve [ReleaseDC'yi](/windows/win32/api/winuser/nf-winuser-releasedc) imha zamanında aramayı halleder.

## <a name="syntax"></a>Sözdizimi

```
class CClientDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CClientDC::CClientDC](#cclientdc)|'ye `CClientDC` bağlı bir nesne inşa eder. `CWnd`|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CClientDC::m_hWnd](#m_hwnd)|Bunun `CClientDC` geçerli olduğu pencerenin HWND'si.|

## <a name="remarks"></a>Açıklamalar

Bu, bir `CClientDC` nesneyle ilişkili aygıt bağlamının pencerenin istemci alanı olduğu anlamına gelir.

Daha fazla `CClientDC`bilgi için [Bkz. Aygıt Bağlamları.](../../mfc/device-contexts.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cclientdccclientdc"></a><a name="cclientdc"></a>CClientDC::CClientDC

`CClientDC` *PWnd*tarafından işaret edilen [CWnd](../../mfc/reference/cwnd-class.md) istemci alanına erişen bir nesne yapıları.

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Aygıt bağlam nesnesinin istemci alanının erişeceği pencere.

### <a name="remarks"></a>Açıklamalar

Oluşturucu Windows işlevini [GetDC](/windows/win32/api/winuser/nf-winuser-getdc)olarak adlandırır.

Windows `GetDC` araması `CResourceException`başarısız olursa bir özel durum (tür) atılır. Windows kullanılabilir aygıt bağlamlarının tümünü zaten tahsis etmişse aygıt bağlamı kullanılamayabilir. Uygulamanız, Windows altında herhangi bir zamanda kullanılabilen beş ortak ekran bağlamı için yarışıyor.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

## <a name="cclientdcm_hwnd"></a><a name="m_hwnd"></a>CClientDC::m_hWnd

Nesneyi `HWND` `CWnd` oluşturmak için kullanılan işaretçin. `CClientDC`

```
HWND m_hWnd;
```

### <a name="remarks"></a>Açıklamalar

*m_hWnd* korunan bir değişkendir.

### <a name="example"></a>Örnek

  [CClientDC::CClientDC](#cclientdc)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)
