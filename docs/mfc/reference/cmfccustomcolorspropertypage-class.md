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
ms.openlocfilehash: 8c02c2590e4143460a2cd89bb2b7e7e167c92c0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage sınıfı
Özel renkler renk iletişim kutusunda seçim yapabileceğiniz bir özellik sayfasını temsil eder.  
  
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
|`CMFCCustomColorsPropertyPage::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|`CMFCCustomColorsPropertyPage::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCCustomColorsPropertyPage::Setup](#setup)|Özellik sayfası renk bileşenlerinin ayarlar.|  
  
### <a name="remarks"></a>Açıklamalar  
 `CMFCColorDialog` Sınıfı özel renk özellik sayfasını görüntülemek için bu sınıfı kullanır. Hakkında daha fazla bilgi için `CMFCColorDialog`, bkz: [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCCustomColorsPropertyPage` nesne ve özellik sayfası renk bileşenlerinin ayarlayın.  
  
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
 Özellik sayfası renk bileşenlerinin ayarlar.  
  
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
|[in] `R`|RGB değeri kırmızı bileşenidir.|  
|[in] `G`|RGB değeri yeşil bileşenidir.|  
|[in] `B`|RGB değeri mavi bileşenidir.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, geçerli RGB ve ilişkili HLS (ton, açıklık ve Doygunluk) renk değerleri özellik sayfasının güncelleştirir. [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) yöntemi framework renk iletişim kutusu başlatır veya sol fare düğmesini kullanıcı bu yöntemi çağırır. Hakkında daha fazla bilgi için `CMFCColorDialog`, bkz: [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCStandardColorsPropertyPage Sınıfı](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
