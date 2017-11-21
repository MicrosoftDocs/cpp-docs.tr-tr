---
title: "CMFCToolBarInfo sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
dev_langs: C++
helpviewer_keywords:
- CMFCToolBarInfo [MFC], m_uiColdResID
- CMFCToolBarInfo [MFC], m_uiDisabledResID
- CMFCToolBarInfo [MFC], m_uiHotResID
- CMFCToolBarInfo [MFC], m_uiLargeColdResID
- CMFCToolBarInfo [MFC], m_uiLargeDisabledResID
- CMFCToolBarInfo [MFC], m_uiLargeHotResID
- CMFCToolBarInfo [MFC], m_uiMenuDisabledResID
- CMFCToolBarInfo [MFC], m_uiMenuResID
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 817e710546a695addaa6cae0e266bd1ff1ddc701
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfctoolbarinfo-class"></a>CMFCToolBarInfo sınıfı
Kaynak kimlikleri araç görüntülerinin çeşitli durumlarını içerir. `CMFCToolBarInfo`bir parametresi olarak kullanılan bir yardımcı sınıf olan [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) yöntemi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCToolBarInfo  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarInfo::m_uiColdResID](#m_uicoldresid)|Normal (cold) araç görüntüleri içeren araç bit eşlem kaynak kimliği.|  
|[CMFCToolBarInfo::m_uiDisabledResID](#m_uidisabledresid)|Devre dışı bırakılmış araç görüntüleri içeren araç bit eşlem kaynak kimliği.|  
|[CMFCToolBarInfo::m_uiHotResID](#m_uihotresid)|Seçili (etkin) araç görüntüleri içeren araç bit eşlem kaynak kimliği.|  
|[CMFCToolBarInfo::m_uiLargeColdResID](#m_uilargecoldresid)|Büyük, normal araç görüntüleri içeren araç bit eşlem kaynak kimliği.|  
|[CMFCToolBarInfo::m_uiLargeDisabledResID](#m_uilargedisabledresid)|Kaynak Kimliği büyük içeren araç bit eşlem araç görüntüleri devre dışı.|  
|[CMFCToolBarInfo::m_uiLargeHotResID](#m_uilargehotresid)|Büyük, seçilen araç görüntüleri içeren araç bit eşlem kaynak kimliği.|  
|[CMFCToolBarInfo::m_uiMenuDisabledResID](#m_uimenudisabledresid)|Devre dışı bırakılmış menü görüntüsü yer araç bit eşlem kaynak kimliği.|  
|[CMFCToolBarInfo::m_uiMenuResID](#m_uimenuresid)|Menü görüntüsü yer araç bit eşlem kaynak kimliği.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tam araç çubuğu bit eşlem küçük araç görüntülerini sabit bir boyuta (düğme) oluşur. Depolanan her kaynak kimliği bir `CMFCToolBarInfo` (örneğin, seçili, devre dışı bırakıldı, büyük veya menü görüntüler için) tek bir durumda araç görüntülerinin tam kümesi içeren bir bit eşlem nesnesidir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtoolbar.h  
  
##  <a name="m_uicoldresid"></a>CMFCToolBarInfo::m_uiColdResID  
 Araç çubuğunun tüm normal düğmesi görüntüleri için kaynak Kimliğini belirtir.  
  
```  
UINT m_uiColdResID;  
```  
  
##  <a name="m_uidisabledresid"></a>CMFCToolBarInfo::m_uiDisabledResID  
 Araç çubuğu düğmesi kullanılamıyor görüntüler için bir kaynak kimliği belirtir.  
  
```  
UINT m_uiDisabledResID;  
```  
  
##  <a name="m_uihotresid"></a>CMFCToolBarInfo::m_uiHotResID  
 Araç çubuğunun tüm vurgulanan düğmesi görüntüleri için kaynak Kimliğini belirtir.  
  
```  
UINT m_uiHotResID  
```  
  
##  <a name="m_uilargecoldresid"></a>CMFCToolBarInfo::m_uiLargeColdResID  
 Tüm büyük normal düğme görüntülerini bir araç için bir kaynak kimliği belirtir.  
  
```  
UINT m_uiLargeColdResID  
```  
  
##  <a name="m_uilargedisabledresid"></a>CMFCToolBarInfo::m_uiLargeDisabledResID  
 Araç çubuğunun tüm büyük devre dışı düğme görüntüleri için kaynak Kimliğini belirtir.  
  
```  
UINT m_uiLargeDisabledResID;  
```  
  
##  <a name="m_uilargehotresid"></a>CMFCToolBarInfo::m_uiLargeHotResID  
 Tüm büyük vurgulanan görüntüleri bir araç için bir kaynak kimliği belirtir.  
  
```  
UINT m_uiLargeHotResID;  
```  
  
##  <a name="m_uimenudisabledresid"></a>CMFCToolBarInfo::m_uiMenuDisabledResID  
 Araç çubuğu komutu kullanılamaz görüntüler için bir kaynak kimliği belirtir.  
  
```  
UINT m_uiMenuDisabledResID;  
```  
  
##  <a name="m_uimenuresid"></a>CMFCToolBarInfo::m_uiMenuResID  
 Tüm normal menü öğesi görüntülerini bir araç için bir kaynak kimliği belirtir.  
  
```  
UINT m_uiMenuResID;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)
