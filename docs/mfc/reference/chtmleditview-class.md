---
description: 'Daha fazla bilgi edinin: CHtmlEditView Class'
title: CHtmlEditView sınıfı
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
ms.openlocfilehash: 9ab998ca16a26fd4ef7a23e4dc58c6542ec330b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261326"
---
# <a name="chtmleditview-class"></a>CHtmlEditView sınıfı

, MFC 'nin belge/görünüm mimarisi bağlamında WebBrowser düzenlemesi platformunun işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|Bir `CHtmlEditView` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHtmlEditView:: Create](#create)|Yeni bir pencere nesnesi oluşturur.|
|[CHtmlEditView:: GetDHtmlDocument](#getdhtmldocument)|`IHTMLDocument2`Geçerli belgedeki arabirimi döndürür.|
|[CHtmlEditView:: GetStartDocument](#getstartdocument)|Bu görünüm için varsayılan belgenin adını alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CHtmlView](../../mfc/reference/chtmlview-class.md)

`CHtmlEditView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxhtml. h

## <a name="chtmleditviewchtmleditview"></a><a name="chtmleditview"></a> CHtmlEditView::CHtmlEditView

Bir `CHtmlEditView` nesnesi oluşturur.

```
CHtmlEditView();
```

## <a name="chtmleditviewcreate"></a><a name="create"></a> CHtmlEditView:: Create

Yeni bir pencere nesnesi oluşturur.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>
Windows sınıfına ad veren null ile sonlandırılmış bir karakter dizesini işaret eder. Sınıf adı, [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) genel işlevine veya Windows işlevine kayıtlı herhangi bir ad olabilir `RegisterClass` . NULL ise, önceden tanımlanmış varsayılan [CFrameWnd](../../mfc/reference/cframewnd-class.md) özniteliklerini kullanır.

*lpszWindowName*<br/>
Pencere adını temsil eden, null ile sonlandırılmış bir karakter dizesini işaret eder.

*dwStyle*<br/>
Pencere stili özniteliklerini belirtir. WS_VISIBLE ve WS_CHILD Windows stilleri varsayılan olarak ayarlanır.

*Rect*<br/>
Pencerenin boyutunu ve konumunu belirten bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru. *RectDefault* değeri Windows 'un yeni pencerenin boyutunu ve konumunu belirlemesine izin verir.

*pParentWnd*<br/>
Denetimin üst penceresine yönelik bir işaretçi.

*NID*<br/>
Görünümün KIMLIK numarası. Varsayılan olarak, AFX_IDW_PANE_FIRST olarak ayarlayın.

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md)işaretçisi. Varsayılan olarak NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `Navigate` varsayılan bir belgeyi yüklemek için Içerilen WebBrowser 'ın metodunu da çağırır (bkz. [CHtmlEditView:: GetStartDocument](#getstartdocument)).

## <a name="chtmleditviewgetdhtmldocument"></a><a name="getdhtmldocument"></a> CHtmlEditView:: GetDHtmlDocument

`IHTMLDocument2`Geçerli belgedeki arabirimi döndürür.

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>Parametreler

*ppDocument*<br/>
[IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) arabirimi.

## <a name="chtmleditviewgetstartdocument"></a><a name="getstartdocument"></a> CHtmlEditView:: GetStartDocument

Bu görünüm için varsayılan belgenin adını alır.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>Ayrıca bkz.

[HTMLEdit örneği](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
