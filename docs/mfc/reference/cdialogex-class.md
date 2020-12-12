---
description: 'Daha fazla bilgi edinin: CDialogEx Class'
title: CDialogEx sınıfı
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
ms.openlocfilehash: 27ec0011935871d472734cae6f0d62b402382727
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185251"
---
# <a name="cdialogex-class"></a>CDialogEx sınıfı

`CDialogEx`Sınıfı, bir iletişim kutusunun arka plan rengini ve arka plan resmini belirtir.

## <a name="syntax"></a>Syntax

```
class CDialogEx : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDialogEx::CDialogEx](#cdialogex)|Bir `CDialogEx` nesnesi oluşturur.|
|`CDialogEx::~CDialogEx`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDialogEx:: SetBackgroundColor](#setbackgroundcolor)|İletişim kutusunun arka plan rengini ayarlar.|
|[CDialogEx:: SetBackgroundImage](#setbackgroundimage)|İletişim kutusunun arka plan resmini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Sınıfını kullanmak için `CDialogEx` , sınıf yerine sınıfından iletişim kutusu sınıfınızı türetirsiniz `CDialogEx` `CDialog` .

İletişim kutusu görüntüleri bir kaynak dosyasında depolanır. Çerçeve, kaynak dosyasından yüklenen tüm görüntüyü otomatik olarak siler. Geçerli arka plan görüntüsünü programlı bir şekilde silmek için, [CDialogEx:: SetBackgroundImage](#setbackgroundimage) metodunu çağırın veya bir `OnDestroy` olay işleyicisi uygulayın. [CDialogEx:: SetBackgroundImage](#setbackgroundimage) metodunu çağırdığınızda, `HBITMAP` görüntü tutamacı olarak bir parametre geçirin. `CDialogEx`Nesne görüntünün sahipliğini alır ve `m_bAutoDestroyBmp` bayrak ise onu siler `TRUE` .

Bir `CDialogEx` nesne bir [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) nesnesinin üst öğesi olabilir. CMFCPopupMenu sınıfı nesnesi açıldığında [CMFCPopupMenu sınıf](../../mfc/reference/cmfcpopupmenu-class.md) nesnesi `CDialogEx::SetActiveMenu` yöntemini çağırır. [](../../mfc/reference/cmfcpopupmenu-class.md) Daha sonra, `CDialogEx` nesne [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) nesnesi kapatılana kadar herhangi bir menü olayını işler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdialogex. h

## <a name="cdialogexcdialogex"></a><a name="cdialogex"></a> CDialogEx::CDialogEx

Bir `CDialogEx` nesnesi oluşturur.

```
CDialogEx(
    UINT nIDTemplate,
    CWnd* pParent=NULL);

CDialogEx(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd=NULL);
```

### <a name="parameters"></a>Parametreler

*Nıdtemplate*<br/>
'ndaki İletişim kutusu şablonunun kaynak KIMLIĞI.

*lpszTemplateName*<br/>
'ndaki Bir iletişim kutusu şablonunun kaynak adı.

*pParent*<br/>
'ndaki Ana pencereye yönelik bir işaretçi. Varsayılan değer NULL.

*pParentWnd*<br/>
'ndaki Ana pencereye yönelik bir işaretçi. Varsayılan değer NULL.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdialogexsetbackgroundcolor"></a><a name="setbackgroundcolor"></a> CDialogEx:: SetBackgroundColor

İletişim kutusunun arka plan rengini ayarlar.

```cpp
void SetBackgroundColor(
    COLORREF color,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Bir RGB renk değeri.

*bYeniden çizmeyi*<br/>
'ndaki Ekranı hemen güncelleştirmek için TRUE; Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cdialogexsetbackgroundimage"></a><a name="setbackgroundimage"></a> CDialogEx:: SetBackgroundImage

İletişim kutusunun arka plan resmini ayarlar.

```cpp
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

*HBITMAP*<br/>
'ndaki Arka plan resmine yönelik bir tanıtıcı.

*Uıımpresd*<br/>
'ndaki Arka plan resminin kaynak KIMLIĞI.

*konumuna*<br/>
'ndaki `CDialogEx::BackgroundLocation` Görüntünün konumunu belirten değerlerden biri. Geçerli değerler BACKGR_TILE, BACKGR_TOPLEFT, BACKGR_TOPRIGHT, BACKGR_BOTTOMLEFT ve BACKGR_BOTTOMRIGHT içerir. Varsayılan değer BACKGR_TILE.

*bAutoDestroy*<br/>
'ndaki Arka plan görüntüsünü otomatik olarak yok etmek için TRUE; Aksi takdirde, FALSE.

*bYeniden çizmeyi*<br/>
'ndaki İletişim kutusunun hemen yeniden çizilebilmesi için TRUE. Aksi takdirde, FALSE.

### <a name="return-value"></a>Dönüş Değeri

İkinci yöntem aşırı yükleme sözdiziminde, Yöntem başarılı olursa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Belirttiğiniz görüntü, iletişim kutusu istemci alanına uyacak şekilde uzatılmamıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md)<br/>
[CContextMenuManager sınıfı](../../mfc/reference/ccontextmenumanager-class.md)
