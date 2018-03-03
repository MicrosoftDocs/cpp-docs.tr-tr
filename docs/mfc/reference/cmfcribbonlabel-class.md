---
title: "CMFCRibbonLabel sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 32732c08542ff766c265fda93b8cf09ad04387ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribbonlabel-class"></a>CMFCRibbonLabel sınıfı
Şerit için tıklanabilir olmayan metin etiketi uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonLabel : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|Oluşturur ve başlatır bir `CMFCRibbonLabel` nesnesi ile belirtilen metin dizesi.|  
|`CMFCRibbonLabel::~CMFCRibbonLabel`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCRibbonLabel::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|`CMFCRibbonLabel::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCRibbonLabel::SetACCData](#setaccdata)|Geçerli Şerit label öğesi için erişilebilirlik verileri belirler. (Geçersiz kılmaları [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit etiket oluşturduktan sonra çağırarak bir paneline ekleme [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
 Hızlı erişim araç şeridi etiket ekleyemezsiniz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxRibbonLabel.h  
  
##  <a name="cmfcribbonlabel"></a>CMFCRibbonLabel::CMFCRibbonLabel  
 Oluşturur ve başlatır bir [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) belirtilen metin dizesini görüntüler nesnesi.  
  
```  
CMFCRibbonLabel(
    LPCTSTR lpszText,  
    BOOL bIsMultiLine = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszText`  
 Etiketinde görüntülenecek metin.  
  
 [in]`bIsMultiLine`  
 `TRUE`Etiket çok satırlı etiket olduğunu belirtmek için; Aksi takdirde `FALSE`.  
  
##  <a name="setaccdata"></a>CMFCRibbonLabel::SetACCData  
 Geçerli Şerit label öğesi için erişilebilirlik verileri belirler.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pParent`  
 Geçerli Şerit etiketin üst pencere temsil eder.  
  
 [out]`data`  
 Türünde bir nesne `CAccessibilityData` geçerli Şerit etiketi erişilebilirlik verilerle doldurulur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa `data` parametresi başarıyla geçerli Şerit etiketin erişilebilirlik verilerle doldurulan; Aksi takdirde `FALSE`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
