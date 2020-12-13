---
description: 'Daha fazla bilgi edinin: CHtmlEditCtrl Class'
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
ms.openlocfilehash: d395f0f9f3e8b5ae10ad0ce35b2b1e410633e8d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184003"
---
# <a name="chtmleditctrl-class"></a>CHtmlEditCtrl sınıfı

Bir MFC penceresinde WebBrowser ActiveX denetiminin işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CHtmlEditCtrl: public CWnd,
    public CHtmlEditCtrlBase<CHtmlEditCtrl>
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|Bir `CHtmlEditCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHtmlEditCtrl:: Create](#create)|WebBrowser ActiveX denetimi oluşturur ve `CHtmlEditCtrl` nesneye ekler. Bu işlev, WebBrowser ActiveX denetimini otomatik olarak düzenleme moduna geçirir.|
|[CHtmlEditCtrl:: GetDHtmlDocument](#getdhtmldocument)|Kapsanan WebBrowser denetiminde yüklü olan belgedeki [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) arabirimini alır.|
|[CHtmlEditCtrl:: GetStartDocument](#getstartdocument)|İçerilen WebBrowser denetimine yüklenecek bir varsayılan belgenin URL 'sini alır.|

## <a name="remarks"></a>Açıklamalar

Barındırılan WebBrowser denetimi oluşturulduktan sonra otomatik olarak düzenleme moduna konur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHtmlEditCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxhtml. h

## <a name="chtmleditctrlchtmleditctrl"></a><a name="chtmleditctrl"></a> CHtmlEditCtrl::CHtmlEditCtrl

Bir `CHtmlEditCtrl` nesnesi oluşturur.

```
CHtmlEditCtrl();
```

## <a name="chtmleditctrlcreate"></a><a name="create"></a> CHtmlEditCtrl:: Create

WebBrowser ActiveX denetimi oluşturur ve `CHtmlEditCtrl` nesneye ekler. WebBrowser ActiveX denetimi otomatik olarak varsayılan bir belgeye gider ve sonra bu işlev tarafından düzenleme moduna konur.

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
Bu parametre kullanılmıyor.

*dwStyle*<br/>
Bu parametre kullanılmıyor.

*Rect*<br/>
Denetimin boyutunu ve konumunu belirtir.

*pParentWnd*<br/>
Denetimin üst penceresini belirtir. NULL olmaması gerekir.

*NID*<br/>
Denetimin KIMLIĞINI belirtir.

*pContext*<br/>
Bu parametre kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="chtmleditctrlgetdhtmldocument"></a><a name="getdhtmldocument"></a> CHtmlEditCtrl:: GetDHtmlDocument

Kapsanan WebBrowser denetiminde yüklü olan belgedeki [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) arabirimini alır

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>Parametreler

*ppDocument*<br/>
Belge arabirimi.

## <a name="chtmleditctrlgetstartdocument"></a><a name="getstartdocument"></a> CHtmlEditCtrl:: GetStartDocument

İçerilen WebBrowser denetimine yüklenecek bir varsayılan belgenin URL 'sini alır.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
