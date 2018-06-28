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
ms.openlocfilehash: 06575c4d014f72ddbae63ea5f02c3081b4228e1d
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037736"
---
# <a name="cmfcribbonslider-class"></a>CMFCRibbonSlider sınıfı
`CMFCRibbonSlider` Sınıfı bir Şerit çubuğu veya Şerit durum çubuğu ekleyebileceğiniz kaydırıcı denetimi uygular. Şerit kaydırıcı denetimi Office 2007 uygulamalarda görünür yakınlaştırma kaydırıcılar benzer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|Yapıları ve Şerit kaydırıcı denetimi başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonSlider::GetPos](#getpos)|Kaydırıcı denetimi geçerli konumunu döndürür.|  
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|Kaydırıcının en büyük değerini döndürür.|  
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|Kaydırıcının en küçük değerini döndürür.|  
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|Şerit öğesi normal boyutu döndürür. (Geçersiz kılmaları [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|Kaydırıcı denetimi yakınlaştırma artışını boyutu döndürür.|  
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|Kaydırıcı yakınlaştırma düğmeleri olup olmadığını belirtir.|  
|[CMFCRibbonSlider::OnDraw](#ondraw)|Şerit öğesi çizmek için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonSlider::SetPos](#setpos)|Kaydırıcı denetimi geçerli konumunu ayarlar.|  
|[CMFCRibbonSlider::SetRange](#setrange)|Minimum ve maksimum değerleri ayarlayarak kaydırıcı denetimi aralığını belirtir.|  
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|Gösterir veya yakınlaştırma düğmelerini gizler.|  
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|Kaydırıcı denetimi yakınlaştırma artışını boyutunu ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `SetRange` kaydırıcıyı yakınlaştırma artışlarla aralığını yapılandırmak için yöntem. Geçerli konumunu kaydırıcıyı kullanarak ayarlayabilirsiniz `SetPos` yöntemi.  
  
 Kullanarak sol ve sağ tarafındaki kaydırıcı denetimi döngüsel yakınlaştırma düğmelerini görüntüleyebilirsiniz `SetZoomButtons` yöntemi. Varsayılan olarak, kaydırıcıyı yataydır, eksi işareti sol Yakınlaştır düğmesinin görüntüler ve bir artı işareti sağ Yakınlaştır düğmesinin görüntüler.  
  
 `SetZoomIncrement` Yöntemi ekleyin veya bir kullanıcı yakınlaştırma düğmelerini tıkladığında geçerli konumundan çıkarmak için artışı tanımlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCRibbonSlider` kaydırıcıyı özelliklerini ayarlamak için sınıf. Örnek nasıl oluşturulacağını gösteren bir `CMFCRibbonSlider` nesnesi, Yakınlaştırma düğmeleri görüntülemek, kaydırıcı denetimi geçerli konumunu ayarlayın ve kaydırıcı denetimi için değer aralığını ayarlayın.  
  
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
 Olan bir Şerit kaydırıcı yapıları *nWidth* kaydırıcıyı burada eklenir paneli kategorisinde pikselden. Varsayılan olarak, kaydırıcıyı yataydır.  
  
##  <a name="getpos"></a>  CMFCRibbonSlider::GetPos  
 Kaydırıcı denetimi geçerli konumunu döndürür.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırıcı başına göreli bir konum olduğundan kaydırıcı denetimi geçerli konumu.  
  
##  <a name="getrangemax"></a>  CMFCRibbonSlider::GetRangeMax  
 Kaydırıcı üzerinde kaydırıcı denetimi ilerleyebilir kaydırıcının en büyük artış alır.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırıcı üzerinde kaydırıcı denetimi ilerleyebilir kaydırıcının en büyük artırma.  
  
##  <a name="getrangemin"></a>  CMFCRibbonSlider::GetRangeMin  
 Kaydırıcı üzerinde kaydırıcı denetimi ilerleyebilir minimum artışı döndürür.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırıcı üzerinde kaydırıcı denetimi ilerleyebilir minimum artırma.  
  
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
 Kaydırıcı denetimi yakınlaştırma artışını edinin.  
  
```  
int GetZoomIncrement() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaydırıcı denetimi için yakınlaştırma artırma.  
  
##  <a name="haszoombuttons"></a>  CMFCRibbonSlider::HasZoomButtons  
 Kaydırıcı yakınlaştırma düğmeleri olup olmadığını belirtir.  
  
```  
BOOL HasZoomButtons() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` kaydırıcı yakınlaştırma düğmesi varsa; `FALSE` Aksi takdirde.  
  
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
 Kaydırıcısının ayarlamak için konumu belirtir. Kaydırıcı başına göreli konumdur.  
  
 [in] *bRedraw*  
 Varsa `TRUE`, kaydırıcıyı çizilir.  
  
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
 Yakınlaştırma düğmeleri görüntüleme veya gizleme.  
  
```  
void SetZoomButtons(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]. *bInternet*  
 `TRUE` Yakınlaştırma düğmeleri görüntülemek için; `FALSE` gizleme.  
  
##  <a name="setzoomincrement"></a>  CMFCRibbonSlider::SetZoomIncrement  
 Kaydırıcı denetimi yakınlaştırma artışını ayarlayın.  
  
```  
void SetZoomIncrement(int nZoomIncrement);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nZoomIncrement*  
 Kaydırıcı denetimi yakınlaştırma artışını belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement Sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md)
