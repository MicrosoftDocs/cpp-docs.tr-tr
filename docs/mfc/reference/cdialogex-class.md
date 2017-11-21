---
title: "CDialogEx sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
dev_langs: C++
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8efd028a8dd07d22dc1255dfe58a951bf9a8de8d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdialogex-class"></a>CDialogEx sınıfı
`CDialogEx` Sınıfı bir iletişim kutusunun arka plan resmi ve arka plan rengini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDialogEx : public CDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDialogEx::CDialogEx](#cdialogex)|Oluşturan bir `CDialogEx` nesnesi.|  
|`CDialogEx::~CDialogEx`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|İletişim kutusunun arka plan rengini belirler.|  
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|İletişim kutusunun arka plan görüntüsü olarak ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanılacak `CDialogEx` sınıfı, iletişim kutusu sınıfından türetilen `CDialogEx` sınıfının yerine `CDialog` sınıfı.  
  
 İletişim kutusunu görüntüler, bir kaynak dosyasında depolanır. Framework kaynak dosyasından yüklenen herhangi bir görüntü otomatik olarak siler. Program aracılığıyla geçerli arka plan görüntüsü silmek için arama [CDialogEx::SetBackgroundImage](#setbackgroundimage) yöntemi veya uygulama bir `OnDestroy` olay işleyicisi. Çağırdığınızda [CDialogEx::SetBackgroundImage](#setbackgroundimage) yöntemi, geçişinde bir `HBITMAP` parametre olarak görüntü tanıtıcısı. `CDialogEx` Nesne görüntü sahipliğini ve varsa silme `m_bAutoDestroyBmp` bayrağı `TRUE`.  
  
 A `CDialogEx` nesnesi, bir üst öğesi olabilir bir [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) nesnesi. [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) nesne çağrıları `CDialogEx::SetActiveMenu` yöntemi zaman [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) nesnesini açar. Daha sonra `CDialogEx` nesnesini kadar herhangi bir menü olay işleme [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) nesnesi kapalı.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdialogex.h  
  
##  <a name="cdialogex"></a>CDialogEx::CDialogEx  
 Oluşturan bir `CDialogEx` nesnesi.  
  
```  
CDialogEx(
    UINT nIDTemplate,  
    CWnd* pParent=NULL);

 
CDialogEx(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nIDTemplate`  
 Bir iletişim kutusu şablonu kaynak kimliği.  
  
 [in]`lpszTemplateName`  
 Bir iletişim kutusu şablonu kaynak adı.  
  
 [in]`pParent`  
 Üst pencere için bir işaretçi. Varsayılan değer `NULL` şeklindedir.  
  
 [in]`pParentWnd`  
 Üst pencere için bir işaretçi. Varsayılan değer `NULL` şeklindedir.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setbackgroundcolor"></a>CDialogEx::SetBackgroundColor  
 İletişim kutusunun arka plan rengini belirler.  
  
```  
void SetBackgroundColor(
    COLORREF color,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`color`  
 RGB renk değeri.  
  
 [in]`bRepaint`  
 `TRUE`Ekran hemen güncelleştirmek için; Aksi takdirde `FALSE`. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setbackgroundimage"></a>CDialogEx::SetBackgroundImage  
 İletişim kutusunun arka plan görüntüsü olarak ayarlar.  
  
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
 [in]`hBitmap`  
 Arka plan görüntüsü için bir tanıtıcı.  
  
 [in]`uiBmpResId`  
 Arka plan görüntü kaynak kimliği.  
  
 [in]`location`  
 Aşağıdakilerden birini `CDialogEx::BackgroundLocation` görüntüsünün konumu belirten değerleri. Geçerli değerler BACKGR_TILE, BACKGR_TOPLEFT, BACKGR_TOPRIGHT, BACKGR_BOTTOMLEFT ve BACKGR_BOTTOMRIGHT içerir. BACKGR_TILE varsayılan değerdir.  
  
 [in]`bAutoDestroy`  
 `TRUE`otomatik olarak arka plan görüntüsü yok etmek için; Aksi takdirde `FALSE`.  
  
 [in]`bRepaint`  
 `TRUE`anında iletişim kutusunu yeniden boyutlandırmaya; Aksi takdirde `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İkinci yöntemde sözdizimi, aşırı `TRUE` yöntemi ise, başarılı, aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirttiğiniz görüntü iletişim kutusu istemci alanını uyacak şekilde genişletilir değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md)   
 [CContextMenuManager sınıfı](../../mfc/reference/ccontextmenumanager-class.md)
