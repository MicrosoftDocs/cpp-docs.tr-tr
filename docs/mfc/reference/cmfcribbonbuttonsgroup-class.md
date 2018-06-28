---
title: CMFCRibbonButtonsGroup sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23f3672a3b78b1bf86c481b6991c003267e6b0bf
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037440"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup sınıfı
`CMFCRibbonButtonsGroup` Sınıfı, bir grup olarak bir dizi Şerit düğmesi düzenlemenizi sağlar. Gruptaki tüm düğmeleri yatay olarak birbirleriyle doğrudan bitişik ve bir kenarlığı içine alınmalıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Oluşturan bir `CMFCRibbonButtonsGroup` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|Bir düğme bir gruba ekler.|  
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|Düğmelerin listesini bir gruba ekler.|  
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|Belirtilen bir dizinde bulunan düğmesine bir işaretçi döndürür.|  
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|Düğme sayısını grubunda döndürür.|  
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Şerit grubunda normal görüntülerinin görüntü boyutunu döndürür (geçersiz kılmaları [CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Şerit öğesi normal boyutu döndüren (geçersiz kılmaları [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Raporlar olup olmadığını `CMFCRibbonButtonsGroup` nesne araç görüntülerini içerir.|  
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Belirtilen bir düğmesi için düğme normal, vurgulanan veya devre dışı olup olmamasına bağlı olarak, uygun resim çizer.|  
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|Tüm düğmelerden kaldırır `CMFCRibbonButtonsGroup` nesnesi.|  
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|Görüntüleri grubuna atar.|  
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Üst ayarlar `CMFCRibbonCategory` , `CMFCRibbonButtonsGroup` nesne ve içindeki tüm düğmeleri (geçersiz kılmaları [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Grup türetilir [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) ve tek bir varlık olarak yönetilebilir. Grup hiçbir panelinde ya da açılır menüde yerleştirebilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCRibbonButtonsGroup` sınıfı. Örnek nasıl oluşturulacağını gösteren bir `CMFCRibbonButtonsGroup` nesnesi, görüntüleri Şerit düğmeleri grubuna atayın ve bir düğme Şerit düğmeleri grubuna ekleyin. Bu kod parçacığını parçası olan [çizin istemci örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxribbonbuttonsgroup.h  
  
##  <a name="addbutton"></a>  CMFCRibbonButtonsGroup::AddButton  
 Bir düğme bir gruba ekler.  
  
```  
void AddButton(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pButton*  
 Bir işaretçi eklemek için bir düğme.  
  
##  <a name="addbuttons"></a>  CMFCRibbonButtonsGroup::AddButtons  
 Düğmelerin listesini bir gruba ekler.  
  
```  
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lstButtons*  
 Eklemek istediğiniz düğmelerini işaretçileri listesi.  
  
##  <a name="cmfcribbonbuttonsgroup"></a>  CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup  
 Oluşturan bir `CMFCRibbonButtonsGroup` nesnesi.  
  
```  
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pButton*  
 Yeni oluşturulan eklemek için bir düğmeye belirtir `CMFCRibbonButtonsGroup` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getbutton"></a>  CMFCRibbonButtonsGroup::GetButton  
 Belirtilen bir dizinde bulunan düğmesine bir işaretçi döndürür.  
  
```  
CMFCRibbonBaseElement* GetButton(int i) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *t*  
 Döndürülecek bir düğme sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dizinde bulunan düğmesini gösteren bir işaretçi. `NULL` Belirtilen dizin aralık dışında olması durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcount"></a>  CMFCRibbonButtonsGroup::GetCount  
 Düğme sayısını grubunda döndürür.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gruptaki düğmeleri sayısı.  
  
##  <a name="getimagesize"></a>  CMFCRibbonButtonsGroup::GetImageSize  
 Korumalı kaynak görüntü boyutu alır `CMFCToolBarImages` üye `m_Images`.  
  
```  
const CSize GetImageSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa veya bir araç görüntülerinin kaynak görüntü boyutu döndüren `CSize` sıfır değilse.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getregularsize"></a>  CMFCRibbonButtonsGroup::GetRegularSize  
 Şerit Grup öğesi olası en büyük boyutunu alır.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Şerit grubunun cihaz bağlamı işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hasimages"></a>  CMFCRibbonButtonsGroup::HasImages  
 Raporlar olup olmadığını `CMFCRibbonButtonsGroup` nesne araç görüntülerini içerir.  
  
```  
BOOL HasImages() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE değeri döndürür, korumalı `CMFCToolBarImages` üye `m_Images` tüm görüntüleri ya da FALSE ise içermez.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawimage"></a>  CMFCRibbonButtonsGroup::OnDrawImage  
 Belirtilen bir düğmesi için düğme normal, vurgulanan veya devre dışı olup olmamasına bağlı olarak, uygun resim çizer.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rectImage,  
    CMFCRibbonBaseElement* pButton,  
    int nImageIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Cihaz bağlamında işaretçi `CMFCRibbonButtonsGroup` nesnesi.  
  
 [in] *rectImage*  
 Dikdörtgen resim çizmek için içinde.  
  
 [in] *pButton*  
 Düğme için resim çizmek için.  
  
 [in] *nImageIndex*  
 (Birinde normal, vurgulanan veya devre dışı düğmelerinin üç resim Diziler) düğmesine çizmek için resmin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removeall"></a>  CMFCRibbonButtonsGroup::RemoveAll  
 Tüm düğmelerden kaldırır `CMFCRibbonButtonsGroup` nesnesi.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setimages"></a>  CMFCRibbonButtonsGroup::SetImages  
 Görüntüleri Şerit düğmeleri grubuna atar.  
  
```  
void SetImages(
    CMFCToolBarImages* pImages,  
    CMFCToolBarImages* pHotImages,  
    CMFCToolBarImages* pDisabledImages);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pImages*  
 Normal görüntüler.  
  
 [in] *pHotImages*  
 Sık kullanılan görüntüler.  
  
 [in] *pDisabledImages*  
 Devre dışı görüntüler.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `SetImages` bir gruba düğmeleri eklemeden önce. Görüntü sayısı sıfırdan büyük veya gruba eklenecek düğmeleri sayısına eşit olmalıdır.  
  
> [!NOTE]
>  Sık kullanılan görüntüleri kullanıcı düğmesinin üzerine geldiğinde görüntülenen görüntüleri bağımsızdır. Devre dışı görüntüleri düğmesi devre dışı bırakıldığında görüntülenen görüntüleri bağımsızdır.  
  
##  <a name="setparentcategory"></a>  CMFCRibbonButtonsGroup::SetParentCategory  
 Üst ayarlar `CMFCRibbonCategory` , `CMFCRibbonButtonsGroup` nesne ve içindeki tüm düğmeler.  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pCategory*  
 Ayarlamak için üst kategori işaretçisine (Şerit denetimleri sekmeli gruplarında kategoriler olarak adlandırılır).  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
