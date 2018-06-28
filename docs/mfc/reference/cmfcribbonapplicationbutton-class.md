---
title: CMFCRibbonApplicationButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonApplicationButton [MFC], CMFCRibbonApplicationButton
- CMFCRibbonApplicationButton [MFC], SetImage
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c105938fbca6abf98f46ff5c62c27bfa2b83a38e
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037427"
---
# <a name="cmfcribbonapplicationbutton-class"></a>CMFCRibbonApplicationButton sınıfı
Implements özel düğmesini uygulama penceresinin sol üst köşesinde yer. Düğme tıklatıldığında, genellikle ortak içeren menü açar **dosya** gibi komutlar **açık**, **kaydetmek**, ve **çıkış**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonApplicationButton : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](#cmfcribbonapplicationbutton)|Oluşturur ve başlatır bir `CMFCRibbonApplicationButton` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCRibbonApplicationButton::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|`CMFCRibbonApplicationButton::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCRibbonApplicationButton::SetImage](#setimage)|Görüntü için Şerit uygulama düğmesi atar.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCRibbonApplicationButton` sınıfı. Örnek Uygulama düğmesi görüntü atama ve araç ipucu ayarlama gösterir. Bu kod parçacığını parçası olan [çizin istemci örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxRibbonBar.h  
  
##  <a name="cmfcribbonapplicationbutton"></a>  CMFCRibbonApplicationButton::CMFCRibbonApplicationButton  
 Oluşturur ve başlatır bir [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md) nesnesi.  
  
```  
CMFCRibbonApplicationButton();  
CMFCRibbonApplicationButton(UINT uiBmpResID);  
  CMFCRibbonApplicationButton(HBITMAP hBmp);
```  
  
### <a name="parameters"></a>Parametreler  
 `uiBmpResID`  
 Uygulama düğmesi görüntülemek için kaynak kimliği görüntü.  
  
 `hBmp`  
 Uygulama düğmesi görüntülemek için bir bit eşlem için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit uygulaması düğmesi uygulama penceresinin sol üst köşesinde bulunan bir özel düğme vardır. Bir kullanıcı bu düğmesine tıkladığında, uygulama genellikle ortak içeren menü açılır **dosya** gibi komutlar **açık**, **kaydetmek**, ve **çıkış**.  
  
##  <a name="setimage"></a>  CMFCRibbonApplicationButton::SetImage  
 Görüntü uygulama düğmesi atar.  
  
```  
void SetImage(UINT uiBmpResID);  
void SetImage(HBITMAP hBmp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiBmpResID*  
 Uygulama düğmesi görüntülemek için kaynak kimliği görüntü.  
  
 [in] *hBmp*  
 Uygulama düğmesi görüntülemek için bir bit eşlem için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme oluşturduktan sonra yeni bir görüntü için Şerit uygulama düğmesi atamak için bu yöntemi kullanın. Uygulama düğmesi uygulama penceresinin sol üst köşesinde yer alır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
