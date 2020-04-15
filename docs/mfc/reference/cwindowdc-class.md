---
title: CWindowDC Sınıfı
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
ms.openlocfilehash: 89a822280ddebca942016f9a3a334a7128d8456a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371976"
---
# <a name="cwindowdc-class"></a>CWindowDC Sınıfı

`CDC`Türetilmiş.

## <a name="syntax"></a>Sözdizimi

```
class CWindowDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CWindowDC::CWindowDC](#cwindowdc)|Bir `CWindowDC` nesne inşa eder.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CWindowDC::m_hWnd](#m_hwnd)|Bunun `CWindowDC` bağlı olduğu HWND.|

## <a name="remarks"></a>Açıklamalar

Windows işlevini, inşaat zamanında [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)ve imha zamanında [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) olarak çağırır. Bu, bir `CWindowDC` nesnenin [CWnd'nin](../../mfc/reference/cwnd-class.md) (hem istemci hem de istemci olmayan alanlar) tüm ekran alanına eriştiği anlamına gelir.

Kullanma `CWindowDC`hakkında daha fazla bilgi için [Aygıt Bağlamları'na](../../mfc/device-contexts.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>Gereksinimler

Üstbilgi: afxwin.h

## <a name="cwindowdccwindowdc"></a><a name="cwindowdc"></a>CWindowDC::CWindowDC

*PWnd*tarafından işaret edilen nesnenin `CWindowDC` `CWnd` tüm ekran alanına (hem istemci hem de istemci olmayan) erişen bir nesne oluşturuyor.

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Aygıt bağlamı nesnesinin istemci alanının erişeceği pencere.

### <a name="remarks"></a>Açıklamalar

Oluşturucu Windows işlevini [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)olarak çağırır.

Windows `GetWindowDC` araması `CResourceException`başarısız olursa bir özel durum (tür) atılır. Windows kullanılabilir aygıt bağlamlarının tümünü zaten tahsis etmişse aygıt bağlamı kullanılamayabilir. Uygulamanız, Windows altında herhangi bir zamanda kullanılabilen beş ortak ekran bağlamı için yarışıyor.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

## <a name="cwindowdcm_hwnd"></a><a name="m_hwnd"></a>CWindowDC::m_hWnd

İşaretçinHWND `CWnd` nesneoluşturmak `CWindowDC` için kullanılır.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Açıklamalar

`m_hWnd`HWND türünün korunan bir değişkenidir.

### <a name="example"></a>Örnek

  [CWindowDC::CWindowDC](#cwindowdc)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)
