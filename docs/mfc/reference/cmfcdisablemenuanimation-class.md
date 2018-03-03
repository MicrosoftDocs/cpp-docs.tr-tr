---
title: "CMFCDisableMenuAnimation sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
dev_langs:
- C++
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 458a35e708db41ee393da70aedd653aca44cf802
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation sınıfı
Açılır menü animasyon devre dışı bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCDisableMenuAnimation  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Oluşturan bir `CMFCDisableMenuAnimation` nesnesi.|  
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCDisableMenuAnimation::Restore](#restore)|Framework açılır menü görüntülemek için kullanılan önceki animasyon geri yükler.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`CMFCDisableMenuAnimation::m_animType`|Önceki açılır menü animasyon türü depolar.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yardımcı sınıf geçici olarak (örneğin, fare veya klavye komutları işlerken) açılır menü animasyon devre dışı bırakmak için kullanın.  
  
 A `CMFCDisableMenuAnimation` nesne yaşam süresi sırasında açılır menü animasyon devre dışı bırakır. Geçerli açılır menü animasyon türü Oluşturucusu depolar `m_animType` alan ve geçerli animasyon türü için ayarlar `CMFCPopupMenu::NO_ANIMATION`. Yok Edicisi önceki animasyon türü geri yükler.  
  
 Oluşturabileceğiniz bir `CMFCDisableMenuAnimation` açılır menü animasyon tek bir işlevi boyunca devre dışı bırakmak için yığında nesnesi. Açılan menü animasyon işlevleri arasındaki devre dışı bırakmak istiyorsanız, oluşturma bir `CMFCDisableMenuAnimation` nesne öbek üzerinde ve açılır menü animasyon geri yüklemek istediğinizde silin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek yığın geçici olarak menü animasyon devre dışı bırakmak için nasıl kullanılacağını gösterir.  
  
 [!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpopupmenu.h  
  
##  <a name="restore"></a>CMFCDisableMenuAnimation::Restore  
 Framework açılır menü görüntülemek için kullanılan önceki animasyon geri yükler.  
  
```  
void Restore ();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından çağrılır `CMFCDisableMenuAnimation` yıkıcı framework açılır menü görüntülemek için kullanılan önceki animasyon geri yüklemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu Sınıfı](../../mfc/reference/cmfcpopupmenu-class.md)
