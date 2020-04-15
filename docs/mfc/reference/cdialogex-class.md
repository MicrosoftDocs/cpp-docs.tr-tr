---
title: CDialogEx Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
ms.openlocfilehash: b34c441ac63b023ae6272a1646151aad4be1bfbc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375630"
---
# <a name="cdialogex-class"></a>CDialogEx Sınıfı

Sınıf, `CDialogEx` iletişim kutusunun arka plan rengini ve arka plan görüntüsünü belirtir.

## <a name="syntax"></a>Sözdizimi

```
class CDialogEx : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDialogEx::CDialogEx](#cdialogex)|Bir `CDialogEx` nesne inşa eder.|
|`CDialogEx::~CDialogEx`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|İletişim kutusunun arka plan rengini ayarlar.|
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|İletişim kutusunun arka plan görüntüsünü ayarlar.|

## <a name="remarks"></a>Açıklamalar

Sınıfı kullanmak için iletişim kutusu sınıfınızı `CDialog` sınıf `CDialogEx` yerine sınıftan türetin. `CDialogEx`

İletişim kutusu görüntüleri bir kaynak dosyasında depolanır. Çerçeve, kaynak dosyasından yüklenen tüm görüntüleri otomatik olarak siler. Geçerli arka plan görüntüsünü programlı bir şekilde silmek için [CDialogEx::SetBackgroundImage](#setbackgroundimage) yöntemini arayın veya bir `OnDestroy` olay işleyicisi uygulayın. [CDialogEx::SetBackgroundImage](#setbackgroundimage) yöntemini aradiğinizde, görüntü `HBITMAP` tutamacı olarak bir parametre geçirin. Nesne `CDialogEx` görüntünün sahipliğini alır ve `m_bAutoDestroyBmp` bayrak. `TRUE`

`CDialogEx` Nesne, [CMFCPopUpMenu Sınıf](../../mfc/reference/cmfcpopupmenu-class.md) nesnesinin üst öğesi olabilir. [CMFCPopUpMenu Sınıf](../../mfc/reference/cmfcpopupmenu-class.md) nesnesi `CDialogEx::SetActiveMenu` [CMFCPopUpMenu Sınıf](../../mfc/reference/cmfcpopupmenu-class.md) nesnesi açıldığında yöntemi çağırır. Daha sonra, `CDialogEx` [cmfcpopupMenu Sınıf](../../mfc/reference/cmfcpopupmenu-class.md) nesnesi kapatılır kadar nesne herhangi bir menü olay işler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdialogex.h

## <a name="cdialogexcdialogex"></a><a name="cdialogex"></a>CDialogEx::CDialogEx

Bir `CDialogEx` nesne inşa eder.

```
CDialogEx(
    UINT nIDTemplate,
    CWnd* pParent=NULL);

CDialogEx(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd=NULL);
```

### <a name="parameters"></a>Parametreler

*nIDTemplate*<br/>
[içinde] İletişim kutusu şablonunun kaynak kimliği.

*lpszTemplateName*<br/>
[içinde] İletişim kutusu şablonunun kaynak adı.

*pParent*<br/>
[içinde] Üst pencereiçin bir işaretçi. Varsayılan değer NULL'dur.

*pParentWnd*<br/>
[içinde] Üst pencereiçin bir işaretçi. Varsayılan değer NULL'dur.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdialogexsetbackgroundcolor"></a><a name="setbackgroundcolor"></a>CDialogEx::SetBackgroundColor

İletişim kutusunun arka plan rengini ayarlar.

```
void SetBackgroundColor(
    COLORREF color,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
[içinde] RGB renk değeri.

*bRepaint*<br/>
[içinde] EKRANI HEMEN GÜNCELLEMEK IÇIN TRUE; aksi takdirde, YANLIŞ. Varsayılan değer TRUE'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cdialogexsetbackgroundimage"></a><a name="setbackgroundimage"></a>CDialogEx::SetBackgroundImage

İletişim kutusunun arka plan görüntüsünü ayarlar.

```
void SetBackgroundImage(
    HBITMAP hBitmap,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bAutoDestroy=TRUE,
    BOOL bRepaint=TRUE);

BOOL SetBackgroundImage(
    UINT uiBmpResId,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>Parametreler

*Hbıtmap*<br/>
[içinde] Arka plan görüntüsüne bir tutamaç.

*uiBmpResId*<br/>
[içinde] Arka plan görüntüsünün kaynak kimliği.

*Konum*<br/>
[içinde] Görüntünün `CDialogEx::BackgroundLocation` konumunu belirten değerlerden biri. Geçerli değerler BACKGR_TILE, BACKGR_TOPLEFT, BACKGR_TOPRIGHT, BACKGR_BOTTOMLEFT ve BACKGR_BOTTOMRIGHT içerir. Varsayılan değer BACKGR_TILE.

*bAutoDestroy*<br/>
[içinde] TRUE otomatik olarak arka plan görüntüsünü yok etmek için; aksi takdirde, YANLIŞ.

*bRepaint*<br/>
[içinde] İletişim kutusunu hemen yeniden çizmek için TRUE; aksi takdirde, YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

İkinci yöntemde sözdizimini aşırı yükle, yöntem başarılı olursa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Belirttiğiniz görüntü iletişim kutusu istemci alanına uyacak şekilde uzatılmış değildir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopUpMenü Sınıfı](../../mfc/reference/cmfcpopupmenu-class.md)<br/>
[CContextMenuManager Sınıfı](../../mfc/reference/ccontextmenumanager-class.md)
