---
title: "CMFCBaseToolBar sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar::GetDockingMode
- AFXBASETOOLBAR/CMFCBaseToolBar::GetMinSize
- AFXBASETOOLBAR/CMFCBaseToolBar::OnAfterChangeParent
dev_langs: C++
helpviewer_keywords:
- CMFCBaseToolBar [MFC], GetDockingMode
- CMFCBaseToolBar [MFC], GetMinSize
- CMFCBaseToolBar [MFC], OnAfterChangeParent
ms.assetid: 5d79206d-55e4-46f8-b1b8-042e34d7f9da
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: adea885e42f2764afafe5ad4efa7b34e9fea28c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcbasetoolbar-class"></a>CMFCBaseToolBar sınıfı
Araç çubukları için temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCBaseToolBar : public CPane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCBaseToolBar::CMFCBaseToolBar`|Varsayılan Oluşturucu.|  
|`CMFCBaseToolBar::~CMFCBaseToolBar`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCBaseToolBar::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|[CMFCBaseToolBar::GetDockingMode](#getdockingmode)|Yerleştirme modunu döndürür. (Geçersiz kılmaları [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).)|  
|[CMFCBaseToolBar::GetMinSize](#getminsize)|Araç çubuğu minimum boyutu döndürür. (Geçersiz kılmaları [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|  
|[CMFCBaseToolBar::OnAfterChangeParent](#onafterchangeparent)|Bölmesi'nin üst değiştikten sonra çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CBasePane::OnAfterChangeParent](../../mfc/reference/cbasepane-class.md#onafterchangeparent).)|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxbasetoolbar.h  
  
##  <a name="getdockingmode"></a>CMFCBaseToolBar::GetDockingMode  
 Yerleştirme modunu döndürür.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerleştirme modu.  
  
##  <a name="getminsize"></a>CMFCBaseToolBar::GetMinSize  
 Araç çubuğu minimum boyutu döndürür.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`size`  
 Araç çubuğu için en küçük boyut.  
  
##  <a name="onafterchangeparent"></a>CMFCBaseToolBar::OnAfterChangeParent  
 Bölmesi'nin üst değiştikten sonra çerçevesi tarafından çağrılır.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWndOldParent`  
 Önceki üst pencere için bir işaretçi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)
