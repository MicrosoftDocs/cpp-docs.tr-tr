---
title: CClientDC sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3aa255552156fe0bbcb671f39afdcb966e7157ea
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422187"
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

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek MDI](../../visual-cpp-samples.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)
