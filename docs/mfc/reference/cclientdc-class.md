---
description: 'Daha fazla bilgi edinin: CClientDC sınıfı'
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
ms.openlocfilehash: 27735929734388ccb25eaf178e49d63884beed0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122466"
---
# <a name="cclientdc-class"></a>CClientDC sınıfı

Oluşturma sırasında [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) Windows işlevleri ve yok etme sırasında [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) çağırma işlemini gerçekleştirir.

## <a name="syntax"></a>Syntax

```
class CClientDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CClientDC:: CClientDC](#cclientdc)|`CClientDC`Öğesine bağlı bir nesne oluşturur `CWnd` .|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CClientDC:: m_hWnd](#m_hwnd)|Bunun geçerli olduğu pencerenin HWND 'si `CClientDC` .|

## <a name="remarks"></a>Açıklamalar

Bu, bir nesneyle ilişkili cihaz bağlamının `CClientDC` bir pencerenin istemci alanı olduğu anlamına gelir.

Hakkında daha fazla bilgi için `CClientDC` bkz. [cihaz bağlamları](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cclientdccclientdc"></a><a name="cclientdc"></a> CClientDC:: CClientDC

`CClientDC` *PWnd* tarafından Işaret edilen [CWnd](../../mfc/reference/cwnd-class.md) 'ın istemci alanına erişen bir nesne oluşturur.

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İstemci alanı cihaz bağlamı nesnesine erişecek olan pencere.

### <a name="remarks"></a>Açıklamalar

Oluşturucu, [GetDC](/windows/win32/api/winuser/nf-winuser-getdc)Windows işlevini çağırır.

Windows çağrısı başarısız olursa bir özel durum (tür `CResourceException` ) oluşturulur `GetDC` . Windows, tüm kullanılabilir cihaz bağlamlarını zaten ayırmışsa bir cihaz bağlamı kullanılamayabilir. Uygulamanız, Windows altında herhangi bir zamanda kullanılabilir olan beş ortak görüntü bağlamına sahiptir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

## <a name="cclientdcm_hwnd"></a><a name="m_hwnd"></a> CClientDC:: m_hWnd

`HWND` `CWnd` Nesneyi oluşturmak için kullanılan işaretçinin `CClientDC` .

```
HWND m_hWnd;
```

### <a name="remarks"></a>Açıklamalar

*m_hWnd* korunan bir değişkendir.

### <a name="example"></a>Örnek

  [CClientDC:: CClientDC](#cclientdc)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDC sınıfı](../../mfc/reference/cdc-class.md)
