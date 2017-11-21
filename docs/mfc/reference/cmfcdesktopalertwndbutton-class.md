---
title: "CMFCDesktopAlertWndButton sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
dev_langs: C++
helpviewer_keywords:
- CMFCDesktopAlertWndButton [MFC], IsCaptionButton
- CMFCDesktopAlertWndButton [MFC], IsCloseButton
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0ddf357c8da29f7e52546c8185f148b854a9611c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton sınıfı
Bir Masaüstü Uyarısı iletişim kutusu eklenmesi için düğmeler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCDesktopAlertWndButton : public CMFCButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Varsayılan Oluşturucu.|  
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|Düğme Uyarısı iletişim kutusu başlığı alanında görüntülenip görüntülenmeyeceğini belirler.|  
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|Düğme uyarı iletişim kutusu kapanır olup olmadığını belirler.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Düğme Uyarısı iletişim kutusu başlığı alanında görüntülenip görüntülenmeyeceğini belirtir bir Boole değeri.|  
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Düğmesini uyarı iletişim kutusu kapanır olup olmadığını belirten bir Boole değeri.|  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, Oluşturucusu ayarlar `m_bIsCaptionButton` ve `m_bIsCloseButton` veri üyelerine `FALSE`. Üst `CMFCDesktopAlertDialog` nesne kümeleri `m_bIsCaptionButton` için `TRUE` düğmesini Uyarısı iletişim kutusu başlığı alanında konumlandırılır durumunda. `CMFCDesktopAlertDialog` Sınıfı oluşturur bir `CMFCDesktopAlertWndButton` uyarı iletişim kutusunu kapatır düğmesi gören kutusuna ve ayarlar nesnesi `m_bIsCloseButton` için `TRUE`.  
  
 Ekleme `CMFCDesktopAlertWndButton` nesneleri için bir `CMFCDesktopAlertDialog` nesnesi gibi herhangi bir düğmeye eklersiniz. Hakkında daha fazla bilgi için `CMFCDesktopAlertDialog`, bkz: [CMFCDesktopAlertDialog sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `SetImage` yönteminde `CMFCDesktopAlertWndButton` sınıfı. Bu kod parçacığını parçası olan [Masaüstü uyarı demosu örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdesktopalertwnd.h  
  
##  <a name="iscaptionbutton"></a>CMFCDesktopAlertWndButton::IsCaptionButton  
 Düğme Uyarısı iletişim kutusu başlığı alanında görüntülenip görüntülenmeyeceğini belirler.  
  
```  
BOOL IsCaptionButton() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme Uyarısı iletişim kutusu başlığı alanında görüntüleniyorsa, sıfır olmayan; Aksi takdirde, 0.  
  
##  <a name="isclosebutton"></a>CMFCDesktopAlertWndButton::IsCloseButton  
 Düğme uyarı iletişim kutusu kapanır olup olmadığını belirler.  
  
```  
BOOL IsCloseButton() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme Uyarısı iletişim kutusu kapandığında, sıfır olmayan; Aksi takdirde, 0.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertDialog sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md)
