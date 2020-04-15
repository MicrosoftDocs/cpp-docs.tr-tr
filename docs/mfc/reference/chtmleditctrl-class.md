---
title: CHtmlEditCtrl Sınıfı
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
ms.openlocfilehash: 05063c62e9f7a5d88d3fecde842f979725200f98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366851"
---
# <a name="chtmleditctrl-class"></a>CHtmlEditCtrl Sınıfı

MFC penceresinde WebBrowser ActiveX denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CHtmlEditCtrl: public CWnd,
    public CHtmlEditCtrlBase<CHtmlEditCtrl>
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|Bir `CHtmlEditCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CHtmlEditCtrl::Oluştur](#create)|Bir WebBrowser ActiveX denetimi oluşturur ve `CHtmlEditCtrl` nesneye bağlar. Bu işlev, WebBrowser ActiveX denetimini otomatik olarak edit moduna sokar.|
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|Şu anda içerdiği WebBrowser denetiminde yüklenen belgedeki [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) arabirimini alır.|
|[CHtmlEditCtrl::GetStartDocument](#getstartdocument)|URL'yi, içerdiği WebBrowser denetimine yüklemek için varsayılan bir belgeye alır.|

## <a name="remarks"></a>Açıklamalar

Barındırılan WebBrowser denetimi oluşturulduktan sonra otomatik olarak düzenle moduna geçirilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CHtmlEditCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxhtml.h

## <a name="chtmleditctrlchtmleditctrl"></a><a name="chtmleditctrl"></a>CHtmlEditCtrl::CHtmlEditCtrl

Bir `CHtmlEditCtrl` nesne inşa eder.

```
CHtmlEditCtrl();
```

## <a name="chtmleditctrlcreate"></a><a name="create"></a>CHtmlEditCtrl::Oluştur

Bir WebBrowser ActiveX denetimi oluşturur ve `CHtmlEditCtrl` nesneye bağlar. WebBrowser ActiveX denetimi otomatik olarak varsayılan bir belgeye yönlendirilir ve bu işlev tarafından düzenleme moduna geçer.

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

*Dwstyle*<br/>
Bu parametre kullanılmaz.

*Rect*<br/>
Denetimin boyutunu ve konumunu belirtir.

*pParentWnd*<br/>
Denetimin üst penceresini belirtir. NULL olmamalıdır.

*Nıd*<br/>
Denetimin kimliğini belirtir.

*Pcontext*<br/>
Bu parametre kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="chtmleditctrlgetdhtmldocument"></a><a name="getdhtmldocument"></a>CHtmlEditCtrl::GetDHtmlDocument

Şu anda içerdiği WebBrowser denetiminde yüklenen belgedeki [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) arabirimini alır

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>Parametreler

*ppBelge*<br/>
Belge arabirimi.

## <a name="chtmleditctrlgetstartdocument"></a><a name="getstartdocument"></a>CHtmlEditCtrl::GetStartDocument

URL'yi, içerdiği WebBrowser denetimine yüklemek için varsayılan bir belgeye alır.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
