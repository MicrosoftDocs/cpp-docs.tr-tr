---
title: CCommonDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
dev_langs:
- C++
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53f53bdb19c6f40d73179b600051ecfaf6b69c94
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950641"
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
  
##  <a name="ccommondialog"></a>  CCommonDialog::CCommonDialog  
 Oluşturan bir `CCommonDialog` nesnesi.  
  
```  
explicit CCommonDialog(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 *pParentWnd*  
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
 [COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
