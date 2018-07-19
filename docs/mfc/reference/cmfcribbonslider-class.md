---
title: CMFCRibbonSlider sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMax
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMin
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRegularSize
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetZoomIncrement
- AFXRIBBONSLIDER/CMFCRibbonSlider::HasZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::OnDraw
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetRange
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomIncrement
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSlider [MFC], CMFCRibbonSlider
- CMFCRibbonSlider [MFC], GetPos
- CMFCRibbonSlider [MFC], GetRangeMax
- CMFCRibbonSlider [MFC], GetRangeMin
- CMFCRibbonSlider [MFC], GetRegularSize
- CMFCRibbonSlider [MFC], GetZoomIncrement
- CMFCRibbonSlider [MFC], HasZoomButtons
- CMFCRibbonSlider [MFC], OnDraw
- CMFCRibbonSlider [MFC], SetPos
- CMFCRibbonSlider [MFC], SetRange
- CMFCRibbonSlider [MFC], SetZoomButtons
- CMFCRibbonSlider [MFC], SetZoomIncrement
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 307b7f769035a9ddb84a3d0e51e0ff6d8a016472
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850858"
---
# <a name="cmfcribbonslider-class"></a>CMFCRibbonSlider sınıfı
`CMFCRibbonSlider` Sınıfı bir Şerit çubuğuna veya Şerit durum çubuğuna ekleyebileceğiniz kaydırıcı denetimi uygular. Şerit kaydırıcı denetimi Office 2007 uygulamalarında görünen yakınlaştırma kaydırıcılarına benzer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|Yapıları ve bir Şerit kaydırıcı denetimi başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonSlider::GetPos](#getpos)|Kaydırıcı denetimi geçerli konumunu döndürür.|  
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|Kaydırıcının en büyük değerini döndürür.|  
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|Kaydırıcının en küçük değerini döndürür.|  
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|Şerit öğesi normal boyutunu döndürür. (Geçersiz kılmaları [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|Yakınlaştırma artış kaydırıcı denetimi için boyutu döndürür.|  
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|Kaydıracın yakınlaştırma düğmelerini olup olmadığını belirtir.|  
|[CMFCRibbonSlider::OnDraw](#ondraw)|Şerit öğesi çizmek için framework tarafından çağırılır. (Geçersiz kılmaları [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonSlider::SetPos](#setpos)|Kaydırıcı denetimi geçerli konumunu ayarlar.|  
|[CMFCRibbonSlider::SetRange](#setrange)|Minimum ve maksimum değerleri ayarlayarak kaydırıcı denetimi aralığını belirtir.|  
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|Yakınlaştırma düğmelerini gizler veya gösterir.|  
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|Kaydırıcı denetimi yakınlaştırma artışı boyutunu ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `SetRange` yakınlaştırma artışlarla kaydırıcı aralığını yapılandırmak için yöntem. Geçerli konumunu kaydırıcıyı kullanarak ayarlayabilirsiniz `SetPos` yöntemi.  
  
 Kullanarak sol ve sağ tarafında kaydırıcı denetimi döngüsel yakınlaştırma düğmelerini görüntüleyebilirsiniz `SetZoomButtons` yöntemi. Varsayılan olarak, kaydırıcıyı yatay, eksi işareti sol Yakınlaştır düğmesinin görüntüler ve doğru Yakınlaştır düğmesinin bir artı işareti görüntüler.  
  
 `SetZoomIncrement` Yöntemi ekleyin veya kullanıcı yakınlaştırma düğmelerini tıkladığında, geçerli konumdan çıkarma aralığını tanımlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCRibbonSlider` kaydıracın özelliklerini ayarlamak için sınıf. Bu örnek nasıl oluşturulacağını gösterir. bir `CMFCRibbonSlider` nesne, yakınlaştırma düğmelerini görüntüleme, kaydırıcı denetiminin geçerli konumu ayarlayın ve kaydırıcı denetimi için değer aralığını ayarlayın.  
  
 [!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxribbonslider.h  
  
##  <a name="cmfcribbonslider"></a>  CMFCRibbonSlider::CMFCRibbonSlider  
 Şerit kaydırıcı oluşturun.  
  
```  
CMFCRibbonSlider(
    UINT nID,  
    int nWidth=100);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nID*  
 Kaydırıcı kimliği.  
  
 [in]. *nWidth*  
 Kaydırıcı piksel cinsinden genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit kaydırıcı, yapıları *nWidth* kaydırıcı nereden eklenir paneli kategorisinde piksel. Varsayılan olarak, kaydırıcıyı yataydır.  
  
##  <a name="getpos"></a>  CMFCRibbonSlider::GetPos  
 Kaydırıcı denetimi geçerli konumunu döndürür.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kaydırıcının başlangıca konumu kaydırıcı denetiminin geçerli konumu.  
  
##  <a name="getrangemax"></a>  CMFCRibbonSlider::GetRangeMax  
 Kaydırıcı üzerinde kaydırıcı denetimi ilerleyebilir kaydırıcının en büyük artışı alır.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırıcı kaydırıcı denetimi ilerleyebilir kaydırıcının en büyük artış.  
  
##  <a name="getrangemin"></a>  CMFCRibbonSlider::GetRangeMin  
 Kaydırıcı üzerinde kaydırıcı denetimi ilerleyebilir minimum artış döndürür.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırıcı üzerinde kaydırıcı denetimi ilerleyebilir en düşük artırma.  
  
##  <a name="getregularsize"></a>  CMFCRibbonSlider::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getzoomincrement"></a>  CMFCRibbonSlider::GetZoomIncrement  
 Kaydırıcı denetimi yakınlaştırma artışı edinin.  
  
```  
int GetZoomIncrement() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırıcı denetimi için yakınlaştırma artırma.  
  
##  <a name="haszoombuttons"></a>  CMFCRibbonSlider::HasZoomButtons  
 Kaydıracın yakınlaştırma düğmelerini olup olmadığını belirtir.  
  
```  
BOOL HasZoomButtons() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydıracın yakınlaştırma düğmelerini varsa TRUE; FALSE Aksi takdirde.  
  
##  <a name="ondraw"></a>  CMFCRibbonSlider::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpos"></a>  CMFCRibbonSlider::SetPos  
 Kaydırıcı denetimi geçerli konumunu ayarlayın.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nPos*  
 Kaydırıcısını konumu belirtir. Kaydırıcı başlangıcına göre konumdur.  
  
 [in] *bRedraw*  
 TRUE ise, kaydırıcıyı çizilir.  
  
##  <a name="setrange"></a>  CMFCRibbonSlider::SetRange  
 Kaydırıcı denetimi için değer aralığını ayarlayın.  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nMin*  
 Kaydırıcı denetimi en küçük değerini belirtir.  
  
 [in] *nMax*  
 Kaydırıcı denetimi en büyük değerini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Minimum ve maksimum değerleri ayarlayarak kaydırıcı denetimi için değer aralığını belirtir.  
  
##  <a name="setzoombuttons"></a>  CMFCRibbonSlider::SetZoomButtons  
 Yakınlaştırma düğmelerini görüntüleme veya gizleme.  
  
```  
void SetZoomButtons(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]. *bInternet*  
 Yakınlaştırma düğmeleri görüntülemek için TRUE; Bunları gizlemek için FALSE.  
  
##  <a name="setzoomincrement"></a>  CMFCRibbonSlider::SetZoomIncrement  
 Kaydırıcı denetimi yakınlaştırma artışı ayarlayın.  
  
```  
void SetZoomIncrement(int nZoomIncrement);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nZoomIncrement*  
 Kaydırıcı denetimi yakınlaştırma artışı belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement Sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md)
