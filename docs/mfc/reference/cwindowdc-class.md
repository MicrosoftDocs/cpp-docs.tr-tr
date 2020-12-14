---
description: 'Daha fazla bilgi edinin: CWindowDC sınıfı'
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
ms.openlocfilehash: 1fc36614f5e6ded32a47146771991c3ab06998eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344932"
---
# <a name="cwindowdc-class"></a>CWindowDC sınıfı

Öğesinden türetilir `CDC` .

## <a name="syntax"></a>Syntax

```
class CWindowDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWindowDC:: CWindowDC](#cwindowdc)|Bir `CWindowDC` nesnesi oluşturur.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CWindowDC:: m_hWnd](#m_hwnd)|Bu `CWindowDC` eklenen HWND.|

## <a name="remarks"></a>Açıklamalar

Oluşturma sırasında [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)Windows işlevini çağırır ve yok etme sırasında [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) . Bu `CWindowDC` , bir nesnenin bir [CWnd](../../mfc/reference/cwnd-class.md) (hem istemci hem de istemci olmayan alan) tüm ekran alanına eriştiği anlamına gelir.

Kullanma hakkında daha fazla bilgi için `CWindowDC` bkz. [cihaz bağlamları](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>Gereksinimler

Üstbilgi: Afxwin. h

## <a name="cwindowdccwindowdc"></a><a name="cwindowdc"></a> CWindowDC:: CWindowDC

`CWindowDC` `CWnd` *PWnd* tarafından işaret edilen nesnenin tüm ekran alanına (hem istemci hem de istemci olmayan) erişen bir nesne oluşturur.

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İstemci alanı cihaz bağlamı nesnesine erişecek olan pencere.

### <a name="remarks"></a>Açıklamalar

Oluşturucu, [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)Windows işlevini çağırır.

Windows çağrısı başarısız olursa bir özel durum (tür `CResourceException` ) oluşturulur `GetWindowDC` . Windows, tüm kullanılabilir cihaz bağlamlarını zaten ayırmışsa bir cihaz bağlamı kullanılamayabilir. Uygulamanız, Windows altında herhangi bir zamanda kullanılabilir olan beş ortak görüntü bağlamına sahiptir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

## <a name="cwindowdcm_hwnd"></a><a name="m_hwnd"></a> CWindowDC:: m_hWnd

`CWnd`IŞARETÇININ HWND 'si nesneyi oluşturmak için kullanılır `CWindowDC` .

```
HWND m_hWnd;
```

### <a name="remarks"></a>Açıklamalar

`m_hWnd` , HWND türünde korunan bir değişkendir.

### <a name="example"></a>Örnek

  [CWindowDC:: CWindowDC](#cwindowdc)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CDC sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDC sınıfı](../../mfc/reference/cdc-class.md)
