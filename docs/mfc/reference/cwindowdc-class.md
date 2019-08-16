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
ms.openlocfilehash: 0ef9b4917dc834eb8335690f9b0d171245f5c170
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502147"
---
# <a name="cwindowdc-class"></a>CWindowDC sınıfı

Öğesinden `CDC`türetilir.

## <a name="syntax"></a>Sözdizimi

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

Oluşturma sırasında [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)Windows işlevini çağırır ve yok etme sırasında [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) . Bu, bir `CWindowDC` nesnenin bir [CWnd](../../mfc/reference/cwnd-class.md) (hem istemci hem de istemci olmayan alan) tüm ekran alanına eriştiği anlamına gelir.

Kullanma `CWindowDC`hakkında daha fazla bilgi için bkz. [cihaz bağlamları](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>Gereksinimler

Üstbilgi: Afxwin. h

##  <a name="cwindowdc"></a>CWindowDC:: CWindowDC

`CWindowDC` *PWnd*tarafından işaret edilen `CWnd` nesnenin tüm ekran alanına (hem istemci hem de istemci olmayan) erişen bir nesne oluşturur.

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İstemci alanı cihaz bağlamı nesnesine erişecek olan pencere.

### <a name="remarks"></a>Açıklamalar

Oluşturucu, [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)Windows işlevini çağırır.

`CResourceException` Windows`GetWindowDC` çağrısı başarısız olursa bir özel durum (tür) oluşturulur. Windows, tüm kullanılabilir cihaz bağlamlarını zaten ayırmışsa bir cihaz bağlamı kullanılamayabilir. Uygulamanız, Windows altında herhangi bir zamanda kullanılabilir olan beş ortak görüntü bağlamına sahiptir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

##  <a name="m_hwnd"></a>CWindowDC:: m_hWnd

`CWnd` İşaretçinin HWND 'si `CWindowDC` nesneyi oluşturmak için kullanılır.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Açıklamalar

`m_hWnd`, HWND türünde korunan bir değişkendir.

### <a name="example"></a>Örnek

  [CWindowDC:: CWindowDC](#cwindowdc)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)
