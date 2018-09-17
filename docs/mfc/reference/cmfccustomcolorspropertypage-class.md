---
title: CMFCCustomColorsPropertyPage sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
dev_langs:
- C++
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c8fea125c61bebe836a31c0b2718741e8c531d3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716874"
---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage sınıfı
Özel renkler bir renk iletişim kutusunda seçim yapabileceğiniz bir özellik sayfasını temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCCustomColorsPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|Varsayılan Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`CMFCCustomColorsPropertyPage::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|  
|`CMFCCustomColorsPropertyPage::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|  
|[CMFCCustomColorsPropertyPage::Setup](#setup)|Özellik sayfasını renk bileşenlerinin ayarlar.|  
  
### <a name="remarks"></a>Açıklamalar  
 `CMFCColorDialog` Sınıfı özel renk özellik sayfasını görüntülemek için bu sınıfı kullanır. Hakkında daha fazla bilgi için `CMFCColorDialog`, bkz: [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCCustomColorsPropertyPage` nesne ve özellik sayfasının renk bileşenlerine ayarlayın.  
  
 [!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcustomcolorspropertypage.h  
  
##  <a name="setup"></a>  CMFCCustomColorsPropertyPage::Setup  
 Özellik sayfasını renk bileşenlerinin ayarlar.  
  
```  
void Setup(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*R*|[in] Kırmızı bileşeni RGB değeri.|  
|*G*|[in] RGB değeri için yeşil bileşeni.|  
|*B*|[in] Mavi bileşeni RGB değeri.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, geçerli RGB ve ilişkili HLS (hue, açıklık ve Doygunluk) renk değerleri özellik sayfasının güncelleştirir. [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) yöntemi renk iletişim kutusu çerçevesi başlatır veya kullanıcının sol fare düğmesine bastığında bu yöntemi çağırır. Hakkında daha fazla bilgi için `CMFCColorDialog`, bkz: [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCStandardColorsPropertyPage Sınıfı](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
