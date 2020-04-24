---
title: CHtmlEditView Sınıfı
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
ms.openlocfilehash: 20d4586c1ae45e5f3f56c0adbb1ecb1757084fd7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752327"
---
# <a name="chtmleditview-class"></a>CHtmlEditView Sınıfı

MFC'nin belge/görünüm mimarisi bağlamında WebBrowser düzenleme platformunun işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|Bir `CHtmlEditView` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CHtmlEditView::Oluştur](#create)|Yeni bir pencere nesnesi oluşturur.|
|[CHtmlEditView::GetDHtmlDocument](#getdhtmldocument)|Geçerli `IHTMLDocument2` belgedeki arabirimi döndürür.|
|[CHtmlEditView::GetStartDocument](#getstartdocument)|Bu görünüm için varsayılan belgenin adını alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cview](../../mfc/reference/cview-class.md)

[Cscrollview](../../mfc/reference/cscrollview-class.md)

[Cformview](../../mfc/reference/cformview-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[Chtmlview](../../mfc/reference/chtmlview-class.md)

`CHtmlEditView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxhtml.h

## <a name="chtmleditviewchtmleditview"></a><a name="chtmleditview"></a>CHtmlEditView::CHtmlEditView

Bir `CHtmlEditView` nesne inşa eder.

```
CHtmlEditView();
```

## <a name="chtmleditviewcreate"></a><a name="create"></a>CHtmlEditView::Oluştur

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
Windows sınıfını isimleyen geçersiz sonlandırılmış karakter dizesini işaret edin. Sınıf [adı, AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) global işlevine veya Windows `RegisterClass` işlevine kayıtlı herhangi bir ad olabilir. NULL ise, önceden tanımlanmış varsayılan [CFrameWnd](../../mfc/reference/cframewnd-class.md) özniteliklerini kullanır.

*lpszWindowName*<br/>
Pencere adını temsil eden null-sonlandırılan karakter dizesini gösterir.

*Dwstyle*<br/>
Pencere stili özniteliklerini belirtir. Varsayılan olarak, WS_VISIBLE ve WS_CHILD Windows stilleri ayarlanır.

*Rect*<br/>
Pencerenin boyutunu ve konumunu belirten bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru. *rectDefault* değeri, Windows'un yeni pencerenin boyutunu ve konumunu belirtmesine olanak tanır.

*pParentWnd*<br/>
Denetimin üst penceresine bir işaretçi.

*Nıd*<br/>
Görünümün kimlik numarası. Varsayılan olarak, AFX_IDW_PANE_FIRST olarak ayarlayın.

*Pcontext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md)için bir işaretçi. Varsayılan olarak NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, varsayılan bir belgeyi `Navigate` yüklemek için içerdiği WebBrowser yöntemini de çağırır (bkz. [CHtmlEditView::GetStartDocument).](#getstartdocument)

## <a name="chtmleditviewgetdhtmldocument"></a><a name="getdhtmldocument"></a>CHtmlEditView::GetDHtmlDocument

Geçerli `IHTMLDocument2` belgedeki arabirimi döndürür.

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>Parametreler

*ppBelge*<br/>
[IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) arabirimi.

## <a name="chtmleditviewgetstartdocument"></a><a name="getstartdocument"></a>CHtmlEditView::GetStartDocument

Bu görünüm için varsayılan belgenin adını alır.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>Ayrıca bkz.

[HTMLEdit Örneği](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
