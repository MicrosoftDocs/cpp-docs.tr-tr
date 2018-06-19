---
title: CMFCRibbonQuickAccessToolBarDefaultState sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CMFCRibbonQuickAccessToolBarDefaultState
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], AddCommand
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CopyFrom
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], RemoveAll
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9baeb204234a6df50be062c5944e9b257cb2d2c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370926"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState sınıfı
Şerit çubuğunda konumlandırılmış hızlı erişim araç için varsayılan duruma yöneten bir yardımcı sınıfı ( [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonQuickAccessToolBarDefaultState  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|Oluşturan bir `CMFCRibbonQuickAccessToolbarDefaultState` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)|Bir komut hızlı erişim araç çubuğu için varsayılan duruma ekler. Bu araç değiştirmez.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|Bir hızlı erişim araç çubuğu özelliklerini başka bir konuma kopyalar.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](#removeall)|Tüm komutları hızlı erişim araç çubuğundan kaldırır. Bu araç değiştirmez.|  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulamanızda hızlı erişim araç oluşturduktan sonra da çağırarak varsayılan durumuna ayarlamanızı öneririz [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate). Bir kullanıcı tıkladığında bu varsayılan duruma geri **sıfırlama** düğmesini **Özelleştir** uygulamanızın sayfasının **seçenekleri** iletişim kutusu.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCRibbonQuickAccessToolbarDefaultState` sınıfı ve hızlı erişim araç çubuğu için varsayılan duruma komut eklemek nasıl.  
  
 [!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxribbonquickaccesstoolbar.h  
  
##  <a name="addcommand"></a>  CMFCRibbonQuickAccessToolBarDefaultState::AddCommand  
 Bir komut hızlı erişim araç çubuğu için varsayılan duruma ekler.  
  
```  
void AddCommand(
    UINT uiCmd,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `[in] uiCmd`  
 Komut kimliğini belirtir.  
  
 `[in] bIsVisible`  
 Hızlı Erişim Araç varsayılan durumda olduğunda komutu görünürlüğünü ayarlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir komutu CMFCRibbonQuickAccessToolBarDefaultState eklenmesi üç sonuçları gerçekleştirir. İlk olarak, eklenen her komut hızlı erişim araç çubuğu sağ tarafında açılan listelenir. Bu şekilde, bir kullanıcı kolayca ekleyebilir veya bu komut hızlı erişim araç çubuğundaki kaldırabilirsiniz. İkinci olarak, kullanıcı tıklattığında listelenen komutları varsayılan durumda olarak görünür göstermek üzere hızlı erişim araç sıfırlama **sıfırlama** düğmesini **Özelleştir** iletişim kutusu. Çağrılmaz durumunda üçüncü [CMFCRibbonBar::SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands), hızlı erişim araç görünür komutları bu listeden varsayılan görünür komutları bir kullanıcı, uygulamanızın ilk çalıştığında kullanır. İstediğiniz tüm komutları ekledikten sonra arama [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) Bu örnek için hızlı erişim araç bu Şerit çubuğunun varsayılan durumu olarak ayarlamak için.  
  
##  <a name="copyfrom"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom  
 Bir hızlı erişim araç çubuğu özelliklerini başka bir konuma kopyalar.  
  
```  
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `src`  
 Bir başvuru kaynağı `CMFCRibbonQuickAccessToolBarDefaultState` kopyalamak için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, her komutun kaynaktan kopyalar `CMFCRibbonQuickAccessToolBarDefaultState` kullanarak bu nesnesini [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) yöntemi.  
  
##  <a name="cmfcribbonquickaccesstoolbardefaultstate"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState  
 Hızlı Erişim Araç çubuğu varsayılan durumu nesnesi oluşturur.  
  
```  
CMFCRibbonQuickAccessToolBarDefaultState();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, listesini komutlar, yeni bir örneğini [CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) içeren boş.  
  
##  <a name="removeall"></a>  CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll  
 Hızlı Erişim Araç varsayılan komutlarda listesini temizler.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bu örneğinden tüm komutları kaldırır, önceki çağrıları [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) eklendi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
