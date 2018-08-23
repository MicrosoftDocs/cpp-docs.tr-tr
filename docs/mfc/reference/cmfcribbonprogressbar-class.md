---
title: CMFCRibbonProgressBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82c72a928c3f747251f4c02305cc61b83cfcedcb
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465367"
---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar sınıfı
Uzun bir işlemin ilerlemesini görsel olarak belirten bir denetim uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|Oluşturur ve başlatır bir `CMFCRibbonProgressBar` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::GetPos](#getpos)|Geçerli ilerleme durumunu döndürür.|  
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|Geçerli aralığın en büyük değerini döndürür.|  
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|Geçerli aralığın en küçük değerini döndürür.|  
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|Şerit öğesi normal boyutunu döndürür. (Geçersiz kılmaları [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|İlerleme çubuğu sonsuz modunda çalışıp çalışmadığını belirtir.|  
|[CMFCRibbonProgressBar::OnDraw](#ondraw)|Şerit öğesi çizmek için framework tarafından çağırılır. (Geçersiz kılmaları [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|İlerleme çubuğu sonsuz modunda çalışacak şekilde ayarlar.|  
|[CMFCRibbonProgressBar::SetPos](#setpos)|Geçerli ilerleme durumunu ayarlar.|  
|[CMFCRibbonProgressBar::SetRange](#setrange)|Minimum ve maksimum değerleri ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 A `CMFCRibbonProgressBar` iki modda çalışabilir: normal ve sonsuz. Normal mod, ilerleme çubuğu soldan sağa doldurulur ve en yüksek değer ulaştığında durdurur. Sonsuz modunda ilerleme çubuğu için maksimum değer minimum değerden tekrar tekrar girilir. Sonsuz modu, bir işlem devam ediyor, ancak tamamlama süresi bilinmeyen olduğunu belirtmek için kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCRibbonProgressBar` sınıfı. Örnek, ilerleme çubuğu için minimum ve maksimum değerler ve ilerleme çubuğu geçerli konumunu ayarlayın (bir işlemi tamamlama süresi bilinmeyen olduğu), sonsuz modunda çalışacak şekilde ilerleme çubuğu ayarlama işlemini gösterir. Bu kod parçacığı parçasıdır [MS Office 2007 Demo örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxRibbonProgressBar.h  
  
##  <a name="cmfcribbonprogressbar"></a>  CMFCRibbonProgressBar::CMFCRibbonProgressBar  
 Oluşturur ve başlatır bir [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) nesne.  
  
```  
CMFCRibbonProgressBar();

 
CMFCRibbonProgressBar(
    UINT nID,  
    int nWidth = 90,  
    int nHeight = 22);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nID*  
 Şerit ilerleme çubuğu komut Kimliğini belirtir.  
  
 [in] *nWidth*  
 Şerit ilerleme çubuğunun piksel cinsinden genişliğini belirtir.  
  
 [in] *nHeight*  
 Şerit ilerleme çubuğunun piksel cinsinden yüksekliğini belirtir.  
  
##  <a name="getpos"></a>  CMFCRibbonProgressBar::GetPos  
 İlerleme çubuğu geçerli konumunu döndürür.  
  
```  
int GetPos () const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlerleme çubuğu geçerli konumunu temsil eden bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlanan aralığı tarafından belirtilen aralıkta olmalıdır [CMFCRibbonProgressBar::SetRange](#setrange) yöntemi.  
  
##  <a name="getrangemax"></a>  CMFCRibbonProgressBar::GetRangeMax  
 İlerleme çubuğu geçerli döndürür maksimum değer.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli aralığın maksimum değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrangemin"></a>  CMFCRibbonProgressBar::GetRangeMin  
 İlerleme çubuğu geçerli döndürür en düşük aralık değeri.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli aralığın minimum değeri.  
  
##  <a name="getregularsize"></a>  CMFCRibbonProgressBar::GetRegularSize  
 Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isinfinitemode"></a>  CMFCRibbonProgressBar::IsInfiniteMode  
 İlerleme çubuğu sonsuz modunda çalışıp çalışmadığını belirtir.  
  
```  
BOOL IsInfiniteMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlerleme çubuğu sonsuz modundaysa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonsuz modunda, ilerleme çubuğu için maksimum değer minimum değerden art arda doldurur. Sonsuz modu, bir işlem devam ediyor, ancak tamamlama süresi bilinmeyen olduğunu belirtmek için kullanabilirsiniz.  
  
##  <a name="ondraw"></a>  CMFCRibbonProgressBar::OnDraw  
 Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setinfinitemode"></a>  CMFCRibbonProgressBar::SetInfiniteMode  
 İlerleme çubuğu sonsuz modunda çalışacak şekilde ayarlar.  
  
```  
void SetInfiniteMode(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bInternet*  
 İlerleme çubuğu sonsuz modunda olduğunu belirtmek için TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 İlerleme çubuğu sonsuz modundaysa, genellikle, kullanıcı bir işlem devam ediyor, ancak tamamlama süresi bilinmiyor söylüyor. Bu nedenle, ilerleme çubuğu için maksimum değer minimum değerden art arda doldurur.  
  
##  <a name="setpos"></a>  CMFCRibbonProgressBar::SetPos  
 İlerleme çubuğu geçerli konumunu ayarlar.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nPos*  
 İlerleme çubuğu için ayarlanmış konumunu belirtir.  
  
 [in] *bRedraw*  
 İlerleme çubuğu çizilmesi olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlanan aralığı tarafından belirtilen aralıkta olmalıdır [CMFCRibbonProgressBar::SetRange](#setrange) yöntemi.  
  
##  <a name="setrange"></a>  CMFCRibbonProgressBar::SetRange  
 İlerleme çubuğu için minimum ve maksimum değerleri ayarlar.  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nMin*  
 En küçük aralık değerini belirtir.  
  
 [in] *nMax*  
 En büyük aralık değerini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Minimum ve maksimum değerleri ayarlayarak ilerleme çubuğu aralığını tanımlamak için bu yöntemi kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
