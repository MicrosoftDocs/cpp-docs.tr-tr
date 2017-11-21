---
title: "CCommonDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
dev_langs: C++
helpviewer_keywords: CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d97bef4a21a926f1b6015d43f4da74bfc52185f6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccommondialog-class"></a>CCommonDialog sınıfı
Windows ortak iletişim kutuları işlevselliğini kapsülleyen sınıflar için temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CCommonDialog : public CDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCommonDialog::CCommonDialog](#ccommondialog)|Oluşturan bir `CCommonDialog` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki sınıflar Windows ortak iletişim kutuları işlevselliğini kapsülleyen:  
  
- [CFileDialog](../../mfc/reference/cfiledialog-class.md)  
  
- [CFontDialog](../../mfc/reference/cfontdialog-class.md)  
  
- [CColorDialog](../../mfc/reference/ccolordialog-class.md)  
  
- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)  
  
- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)  
  
- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)  
  
- [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)  
  
- [COleDialog](../../mfc/reference/coledialog-class.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CCommonDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdlgs.h  
  
##  <a name="ccommondialog"></a>CCommonDialog::CCommonDialog  
 Oluşturan bir `CCommonDialog` nesnesi.  
  
```  
explicit CCommonDialog(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentWnd`  
 İşaret üst veya sahibi pencere nesnesi için (tür [CWnd](../../mfc/reference/cwnd-class.md)) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim nesnenin üst pencere ana uygulama penceresine ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [CDialog::CDialog](../../mfc/reference/cdialog-class.md#cdialog) tam bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDialog sınıfı](../../mfc/reference/cdialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)   
 [CFontDialog sınıfı](../../mfc/reference/cfontdialog-class.md)   
 [CColorDialog sınıfı](../../mfc/reference/ccolordialog-class.md)   
 [CPageSetupDialog sınıfı](../../mfc/reference/cpagesetupdialog-class.md)   
 [CPrintDialog sınıfı](../../mfc/reference/cprintdialog-class.md)   
 [CFindReplaceDialog sınıfı](../../mfc/reference/cfindreplacedialog-class.md)   
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)
