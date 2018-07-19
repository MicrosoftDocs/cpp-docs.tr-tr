---
title: Cmfcımageeditorpalettebar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::GetRowHeight
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorPaletteBar [MFC], GetRowHeight
- CMFCImageEditorPaletteBar [MFC], IsButtonExtraSizeAvailable
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3b10e18e12b5a2f27c0b83562ef16321da67422
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851463"
---
# <a name="cmfcimageeditorpalettebar-class"></a>Cmfcımageeditorpalettebar sınıfı
Bir Resim Düzenleyicisi iletişim kutusu için palet çubuğu işlevlerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCImageEditorPaletteBar : public CMFCToolBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCImageEditorPaletteBar::GetRowHeight](#getrowheight)|Araç çubuğu düğmeleri yüksekliğini döndürür. (Geçersiz kılmaları [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|  
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Araç çubuğu kenarlık genişletilmiş düğmeleri görüntüleyip görüntülemeyeceğini belirler. (Geçersiz kılmaları [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf doğrudan sizin kodunuzdan kullanılmak üzere tasarlanmamıştır.  
  
 Framework, bir Resim Düzenleyicisi iletişim kutusunda bir palet çubuğunu görüntülemek için bu sınıfı kullanır. Resim Düzenleyicisi iletişim kutusu hakkında daha fazla bilgi için bkz. [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [Cmfcımageeditorpalettebar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afximageeditordialog.h  
  
##  <a name="getrowheight"></a>  CMFCImageEditorPaletteBar::GetRowHeight  
 Araç çubuğu düğmeleri yüksekliğini döndürür.  
  
```  
virtual int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her araç çubuğunda yüksekliği.  
  
##  <a name="isbuttonextrasizeavailable"></a>  CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable  
 Araç çubuğu kenarlık genişletilmiş düğmeleri görüntüleyip görüntülemeyeceğini belirler.  
  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem FALSE döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog Sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md)
