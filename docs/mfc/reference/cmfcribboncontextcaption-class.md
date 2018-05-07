---
title: CMFCRibbonContextCaption sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonContextCaption [MFC], GetColor
- CMFCRibbonContextCaption [MFC], GetRightTabX
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2fa63de2a633b2c8a9fff975de6eaaae7cbb470c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribboncontextcaption-class"></a>CMFCRibbonContextCaption sınıfı
Şerit kategori veya bir bağlam kategorisi üst kısmında görünür renkli bir resim yazısı uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonContextCaption : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCRibbonContextCaption::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|[CMFCRibbonContextCaption::GetColor](#getcolor)|Resim yazısı rengini döndürür.|  
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||  
|`CMFCRibbonContextCaption::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf doğrudan örneği oluşturulamıyor. [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md) sınıfı bu sınıf dahili olarak renk şeridi kategorileri eklemek için kullanır.  
  
 Şerit kategorileri rengini ayarlamak için arama [CMFCRibbonCategory::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor). Bağlam kategorileri rengini ayarlamak için arama [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxRibbonBar.h  
  
##  <a name="getcolor"></a>  CMFCRibbonContextCaption::GetColor  
 Başlık arka plan rengini döndürür.  
  
```  
AFX_RibbonCategoryColor GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürülen değer aşağıdaki numaralandırılmış değerlerden biri olabilir:  
  
- `AFX_CategoryColor_None`  
  
- `AFX_CategoryColor_Red`  
  
- `AFX_CategoryColor_Orange`  
  
- `AFX_CategoryColor_Yellow`  
  
- `AFX_CategoryColor_Green`  
  
- `AFX_CategoryColor_Blue`  
  
- `AFX_CategoryColor_Indigo`  
  
- `AFX_CategoryColor_Violet`  
  
### <a name="remarks"></a>Açıklamalar  
 Resim yazısı rengini çağırarak ayarlanabilir [CMFCRibbonCategory::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) veya [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).  
  
##  <a name="getrighttabx"></a>  CMFCRibbonContextCaption::GetRightTabX  
 Kategorinin Şerit sekmesi sağ kenarı konumunu alır.  
  
```  
int GetRightTabX() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağ taraftaki X-değerini çevreleyen dikdörtgen döndürür `CMFCRibbonCategory` nesnenin Şerit sekmesi veya sekmesinde kesilirse -1 değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonCategory sınıfı](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
