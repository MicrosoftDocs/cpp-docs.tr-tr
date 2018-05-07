---
title: CMFCRibbonMainPanel sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05257749c95b619c479538a1322746ae2b487b6a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel sınıfı
' I tıklattığınızda görüntüleyen bir Şerit panel uygulayan [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonMainPanel : public CMFCRibbonPanel  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Varsayılan Oluşturucu.|  
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonMainPanel::Add](#add)|Uygulama düğmesi bölmenin sol bölmeye Şerit öğesi ekler. (Geçersiz kılmaları [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).)|  
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|Bir metin dizesi son dosyalar listesi menüsüne ekler.|  
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|Şerit uygulaması panelinin alt bölmesinde bir Şerit öğesi ekler.|  
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|Uygulama düğmesi bölmenin sağ bölmede bir Şerit öğesi ekler.|  
|`CMFCRibbonMainPanel::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|Şerit ana bölmesi alanını temsil eden bir dikdörtgen döndürür.|  
|`CMFCRibbonMainPanel::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Framework görüntüler `CMFCRibbonMainPanel` uygulama panelini açtığınızda. Üç bölme içerir:  
  
-   Sol bölmede dosyalarıyla ilişkili komutları içeren **açık**, **kaydetmek**, **yazdırma**, ve **Kapat**. Bir komutu bu bölmesine eklemek için arama [CMFCRibbonMainPanel::Add](#add).  
  
-   Sağ bölmede, sol bölmede tıklatın komutu değiştiren seçenekleri içerir. Örneğin, tıklatırsanız **Kaydet** sol bölmeden sağ bölmede kullanılabilir dosya türlerini görüntüleyebilirsiniz. Öğe bu bölmesine eklemek için arama [CMFCRibbonMainPanel::AddToRight](#addtoright).  
  
-   Alt bölme, uygulamanın ayarlarını değiştirmek için ve programdan çıkmak için izin düğmelerini içerir. Öğe bu bölmesine eklemek için arama [CMFCRibbonMainPanel::AddToBottom](#addtobottom).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
 [CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxRibbonMainPanel.h  
  
##  <a name="add"></a>  CMFCRibbonMainPanel::Add  
 Uygulama düğmesi bölmenin sol bölmeye Şerit öğesi ekler.  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] `pElem`  
 Ana paneline eklemek için Şerit öğesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Panele bir Şerit öğesi ekler. Bu yöntem kullanılarak eklenen öğeleri ana bölmesi sol sütunda yer alır.  
  
##  <a name="addrecentfileslist"></a>  CMFCRibbonMainPanel::AddRecentFilesList  
 Bir metin dizesi son dosyalar listesi menüsüne ekler.  
  
```  
void AddRecentFilesList(
    LPCTSTR lpszLabel,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszLabel`  
 Son kullanılan dosya listesi eklenecek dizeyi belirtir.  
  
 `nWidth`  
 Son kullanılan dosyalar listesi panelini piksel cinsinden genişliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addtobottom"></a>  CMFCRibbonMainPanel::AddToBottom  
 Şerit uygulaması panelinin alt bölmesinde bir Şerit öğesi ekler.  
  
```  
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] `pElem`  
 Ana bölmesi alt kısmına eklemek için Şerit öğesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addtoright"></a>  CMFCRibbonMainPanel::AddToRight  
 Uygulama düğmesi bölmenin sağ bölmede bir Şerit öğesi ekler.  
  
```  
void AddToRight(
    CMFCRibbonBaseElement* pElem,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>Parametreler  
 `pElem`  
 Ana bölmesi sağ tarafındaki eklenecek bir Şerit öğesi için bir işaretçi.  
  
 `nWidth`  
 Sağ panelde piksel cinsinden genişliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Sağ panelde bir Şerit öğesi eklemek için bu işlevi kullanın. Son kullanılan dosya listesi genellikle sağ panelde görüntüler, ancak tüm diğer Şerit öğesi buraya ekleyebilirsiniz.  
  
##  <a name="getcommandsframe"></a>  CMFCRibbonMainPanel::GetCommandsFrame  
 Şerit ana bölmesi alanını temsil eden bir dikdörtgen döndürür.  
  
```  
CRect GetCommandsFrame() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit ana bölmesi alanını temsil eden bir dikdörtgen.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel Sınıfı](../../mfc/reference/cmfcribbonpanel-class.md)
