---
title: CDialogEx sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
dev_langs:
- C++
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02a8ae81ea94c47cd11beae0b3ed0eacee77db07
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386307"
---
# <a name="cdialogex-class"></a>CDialogEx sınıfı

`CDialogEx` Sınıfı bir iletişim kutusunun arka plan görüntüsü ve arka plan rengini belirtir.

## <a name="syntax"></a>Sözdizimi

```
class CDialogEx : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDialogEx::CDialogEx](#cdialogex)|Oluşturur bir `CDialogEx` nesne.|
|`CDialogEx::~CDialogEx`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|İletişim kutusunun arka plan rengini ayarlar.|
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|İletişim kutusunun arka plan resmini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Kullanılacak `CDialogEx` sınıfı, sizin iletişim kutusu sınıfından türetilir `CDialogEx` sınıfı yerine `CDialog` sınıfı.

İletişim kutusunu görüntüler, bir kaynak dosyasında depolanır. Framework kaynak dosyasından yüklenen herhangi bir görüntüyü otomatik olarak siler. Geçerli arka plan resmi program aracılığıyla silme çağrısı [CDialogEx::SetBackgroundImage](#setbackgroundimage) yöntemi veya uygulama bir `OnDestroy` olay işleyicisi. Çağırdığınızda [CDialogEx::SetBackgroundImage](#setbackgroundimage) geçişinde yöntemi bir `HBITMAP` parametre olarak görüntü tanıtıcısı. `CDialogEx` Nesne görüntü sahipliğini ve varsa silin `m_bAutoDestroyBmp` bayrağı `TRUE`.

A `CDialogEx` nesnenin üst öğesi olabilir bir [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) nesne. [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) nesne çağrıları `CDialogEx::SetActiveMenu` yöntemi zaman [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) nesnesini açar. Daha sonra `CDialogEx` nesnesini kadar herhangi bir menü olay işleme [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) nesnesi kapalı.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdialogex.h

##  <a name="cdialogex"></a>  CDialogEx::CDialogEx

Oluşturur bir `CDialogEx` nesne.

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
[in] Bir iletişim kutusu şablonu kaynak kimliği.

*lpszTemplateName*<br/>
[in] Bir iletişim kutusu şablonu kaynak adı.

*pParent*<br/>
[in] Üst penceresine bir işaretçi. Varsayılan değer NULL olur.

*pParentWnd*<br/>
[in] Üst penceresine bir işaretçi. Varsayılan değer NULL olur.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="setbackgroundcolor"></a>  CDialogEx::SetBackgroundColor

İletişim kutusunun arka plan rengini ayarlar.

```
void SetBackgroundColor(
    COLORREF color,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
[in] Bir RGB renk değeri.

*bRepaint*<br/>
[in] Ekranın hemen güncelleştirmek için TRUE; Aksi takdirde FALSE. Varsayılan değer True'dur.

### <a name="remarks"></a>Açıklamalar

##  <a name="setbackgroundimage"></a>  CDialogEx::SetBackgroundImage

İletişim kutusunun arka plan resmini ayarlar.

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
[in] Arka plan görüntüsü için bir tanıtıcı.

*uiBmpResId*<br/>
[in] Arka plan görüntü kaynak kimliği.

*Konum*<br/>
[in] Aşağıdakilerden birini `CDialogEx::BackgroundLocation` görüntüsünün konumu belirten değerleri. Geçerli değerler BACKGR_TILE, BACKGR_TOPLEFT BACKGR_TOPRIGHT BACKGR_BOTTOMLEFT ve BACKGR_BOTTOMRIGHT içerir. BACKGR_TILE varsayılan değerdir.

*bAutoDestroy*<br/>
[in] Otomatik olarak arka plan görüntüsü yok etmek için TRUE; Aksi takdirde FALSE.

*bRepaint*<br/>
[in] Hemen iletişim kutusunu yeniden çizmek için TRUE; Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa İkinci yöntemde sözdiziminin doğru aşırı; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Belirttiğiniz görüntü iletişim kutusu istemci alanını uyacak şekilde uzatılır değil.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu Sınıfı](../../mfc/reference/cmfcpopupmenu-class.md)<br/>
[CContextMenuManager Sınıfı](../../mfc/reference/ccontextmenumanager-class.md)
