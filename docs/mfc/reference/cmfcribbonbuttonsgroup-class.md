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
ms.openlocfilehash: 855bc48da10e8ca4dd83cf091e155746450a33f1
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848525"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup sınıfı
`CMFCRibbonButtonsGroup` Sınıfı, bir grup olarak Şerit düğme kümesi düzenlemenizi sağlar. Gruptaki tüm düğmeler yatay olarak doğrudan yaratır ve bir kenarlık içine alınmıştır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Oluşturur bir `CMFCRibbonButtonsGroup` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|Bir düğmeyi bir gruba ekler.|  
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|Düğmelerin listesini bir gruba ekler.|  
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|Belirtilen dizinde bulunan bir düğme için bir işaretçi döndürür.|  
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|Grup içinde düğmeleri sayısını döndürür.|  
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Şerit grubundaki normal görüntüleri görüntü boyutunu döndürür (geçersiz kılmaları [CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Şerit öğesi normal boyutunu döndürür (geçersiz kılmaları [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Raporlar olup olmadığını `CMFCRibbonButtonsGroup` nesne araç çubuğu görüntülerini içerir.|  
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Düğme normal, vurgulanan veya devre dışı olup olmamasına bağlı olarak belirtilen bir düğme için uygun resim çizer.|  
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|Tüm düğmelerden kaldırır `CMFCRibbonButtonsGroup` nesne.|  
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|Görüntüleri gruba atar.|  
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Üst ayarlar `CMFCRibbonCategory` , `CMFCRibbonButtonsGroup` nesne ve içindeki tüm düğmeler (geçersiz kılmaları [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Grup türetilir [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) ve tek bir varlık olarak yönetilebilir. Hiçbir panel ya da açılan menüde grubu konumlandırabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCRibbonButtonsGroup` sınıfı. Bu örnek nasıl oluşturulacağını gösterir. bir `CMFCRibbonButtonsGroup` nesne, görüntüleri Şerit düğme grubuna atayın ve Şerit düğmeleri gruba bir düğme ekleyin. Bu kod parçacığı parçasıdır [çizmek istemci örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxribbonbuttonsgroup.h  
  
##  <a name="addbutton"></a>  CMFCRibbonButtonsGroup::AddButton  
 Bir düğmeyi bir gruba ekler.  
  
```  
void AddButton(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pButton*  
 Bir düğme eklemek için bir işaretçi.  
  
##  <a name="addbuttons"></a>  CMFCRibbonButtonsGroup::AddButtons  
 Düğmelerin listesini bir gruba ekler.  
  
```  
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lstButtons*  
 Eklemek istediğiniz düğme için işaretçiler listesi.  
  
##  <a name="cmfcribbonbuttonsgroup"></a>  CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup  
 Oluşturur bir `CMFCRibbonButtonsGroup` nesne.  
  
```  
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pButton*  
 Yeni oluşturulan eklemeye yönelik bir düğmeyi belirtir `CMFCRibbonButtonsGroup` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getbutton"></a>  CMFCRibbonButtonsGroup::GetButton  
 Belirtilen dizinde bulunan bir düğme için bir işaretçi döndürür.  
  
```  
CMFCRibbonBaseElement* GetButton(int i) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *ediyorum*  
 Bir düğme döndürülecek bir sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dizinde bulunan bir düğme için bir işaretçi. Belirtilen dizin aralık dışında ise NULL değerini DÖNDÜRÜR.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcount"></a>  CMFCRibbonButtonsGroup::GetCount  
 Grup içinde düğmeleri sayısını döndürür.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gruptaki düğmeleri sayısı.  
  
##  <a name="getimagesize"></a>  CMFCRibbonButtonsGroup::GetImageSize  
 Kaynak görüntü boyutu korumalı alır `CMFCToolBarImages` üye `m_Images`.  
  
```  
const CSize GetImageSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa veya bir araç çubuğu görüntülerini kaynak görüntü boyutunu döndürür `CSize` sıfır değilse.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getregularsize"></a>  CMFCRibbonButtonsGroup::GetRegularSize  
 Şerit grubu öğesi olası en büyük boyutunu alır.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Cihaz bağlamı Şerit grubunun işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hasimages"></a>  CMFCRibbonButtonsGroup::HasImages  
 Raporlar olup olmadığını `CMFCRibbonButtonsGroup` nesne araç çubuğu görüntülerini içerir.  
  
```  
BOOL HasImages() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerekirse TRUE döndürür korumalı `CMFCToolBarImages` üye `m_Images` tüm görüntüler veya FALSE ise içermez.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawimage"></a>  CMFCRibbonButtonsGroup::OnDrawImage  
 Düğme normal, vurgulanan veya devre dışı olup olmamasına bağlı olarak belirtilen bir düğme için uygun resim çizer.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rectImage,  
    CMFCRibbonBaseElement* pButton,  
    int nImageIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Cihaz bağlamı işaretçisine `CMFCRibbonButtonsGroup` nesne.  
  
 [in] *rectImage*  
 Dikdörtgen içinde bir görüntü çizin.  
  
 [in] *pButton*  
 Görüntü çizme istediğiniz düğme.  
  
 [in] *nImageIndex*  
 Resmi düğmesine (normal, vurgulanan veya devre dışı düğmelerinin üç görüntü diziler biri) çizilecek dizini.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removeall"></a>  CMFCRibbonButtonsGroup::RemoveAll  
 Tüm düğmelerden kaldırır `CMFCRibbonButtonsGroup` nesne.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setimages"></a>  CMFCRibbonButtonsGroup::SetImages  
 Görüntüleri Şerit düğme grubuna atar.  
  
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
 Sık erişimli görüntüler.  
  
 [in] *pDisabledImages*  
 Devre dışı görüntüler.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `SetImages` düğmeleri grubuna eklemeden önce. Görüntü sayısı, gruba eklenecek düğmeleri sayısına eşit veya büyük olması gerekir.  
  
> [!NOTE]
>  Sık erişimli görüntüleri kullanıcı düğmenin üzerine geldiğinde görüntülenen görüntüleridir. Düğmeyi devre dışı bırakıldığında görüntülenen görüntüleri devre dışı görüntüleridir.  
  
##  <a name="setparentcategory"></a>  CMFCRibbonButtonsGroup::SetParentCategory  
 Üst ayarlar `CMFCRibbonCategory` , `CMFCRibbonButtonsGroup` nesne ve içindeki tüm düğmeler.  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pCategory*  
 Ayarlanacak üst kategori işaretçisine (Şerit denetimleri sekmeli gruplarında kategoriler olarak adlandırılır).  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
