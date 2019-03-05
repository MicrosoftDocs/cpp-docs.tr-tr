---
title: CHtmlEditCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::Create
- AFXHTML/CHtmlEditCtrl::GetDHtmlDocument
- AFXHTML/CHtmlEditCtrl::GetStartDocument
helpviewer_keywords:
- CHtmlEditCtrl [MFC], CHtmlEditCtrl
- CHtmlEditCtrl [MFC], Create
- CHtmlEditCtrl [MFC], GetDHtmlDocument
- CHtmlEditCtrl [MFC], GetStartDocument
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
ms.openlocfilehash: 6c1447c3157bceb4540007eca5c3eb85e8269bd2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285314"
---
# <a name="chtmleditctrl-class"></a>CHtmlEditCtrl sınıfı

Bir MFC penceresindeki WebBrowser ActiveX denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CHtmlEditCtrl: public CWnd,
    public CHtmlEditCtrlBase<CHtmlEditCtrl>
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|Oluşturur bir `CHtmlEditCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHtmlEditCtrl::Create](#create)|WebBrowser ActiveX denetimi oluşturur ve ona ekler `CHtmlEditCtrl` nesne. Bu işlev, WebBrowser ActiveX denetimi otomatik olarak düzenleme moduna geçirir.|
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|Alır [Ihtmldocument2](https://msdn.microsoft.com/library/aa752574.aspx) belge arabirimde kapsanan WebBrowser denetimi şu anda yüklü.|
|[CHtmlEditCtrl::GetStartDocument](#getstartdocument)|Kapsanan WebBrowser denetimi yüklemek için varsayılan bir belge için URL alır.|

## <a name="remarks"></a>Açıklamalar

Oluşturulduktan sonra denetimi otomatik olarak yerleştirerek barındırılan WebBrowser düzenleme modunda.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHtmlEditCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxhtml.h

##  <a name="chtmleditctrl"></a>  CHtmlEditCtrl::CHtmlEditCtrl

Oluşturur bir `CHtmlEditCtrl` nesne.

```
CHtmlEditCtrl();
```

##  <a name="create"></a>  CHtmlEditCtrl::Create

WebBrowser ActiveX denetimi oluşturur ve ona ekler `CHtmlEditCtrl` nesne. Bu işlev tarafından düzenleme modunda WebBrowser ActiveX denetimi için varsayılan bir belge otomatik olarak gider ve sonra yerleştirilir.

```
virtual BOOL Create(
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszWindowName*<br/>
Bu parametre kullanılmaz.

*dwStyle*<br/>
Bu parametre kullanılmaz.

*Rect*<br/>
Denetimin boyutunu ve konumunu belirtir.

*pParentWnd*<br/>
Denetiminin üst penceresine belirtir. NULL olmamalıdır.

*nID*<br/>
Denetimin kimliğini belirtir.

*pContext*<br/>
Bu parametre kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="getdhtmldocument"></a>  CHtmlEditCtrl::GetDHtmlDocument

Alır [Ihtmldocument2](https://msdn.microsoft.com/library/aa752574.aspx) belge arabirimi yüklü kapsanan WebBrowser denetimi

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>Parametreler

*ppDocument*<br/>
Belge arabirimi.

##  <a name="getstartdocument"></a>  CHtmlEditCtrl::GetStartDocument

Kapsanan WebBrowser denetimi yüklemek için varsayılan bir belge için URL alır.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
