---
title: "CMFCRibbonProgressBar sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1354b0b15837a733a890c438c7771ffe39526773
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar sınıfı
Görsel olarak uzun bir işlemin ilerlemesini gösteren bir denetimi uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|Oluşturur ve başlatır bir `CMFCRibbonProgressBar` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::GetPos](#getpos)|Geçerli ilerleme döndürür.|  
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|Geçerli aralığın maksimum değeri döndürür.|  
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|Geçerli aralığın minimum değeri döndürür.|  
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|Şerit öğesi normal boyutu döndürür. (Geçersiz kılmaları [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|İlerleme çubuğu sonsuz modunda çalışıp çalışmadığını belirtir.|  
|[CMFCRibbonProgressBar::OnDraw](#ondraw)|Şerit öğesi çizmek için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|Sonsuz modda çalışmak için ilerleme çubuğu ayarlar.|  
|[CMFCRibbonProgressBar::SetPos](#setpos)|Geçerli ilerleme ayarlar.|  
|[CMFCRibbonProgressBar::SetRange](#setrange)|Minimum ve maksimum değerleri ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 A `CMFCRibbonProgressBar` iki modda çalışabilir: normal ve sonsuz. Normal modda ilerleme çubuğu soldan sağa girilir ve en büyük değer ulaştığında durdurur. Sonsuz modunda ilerleme çubuğu art arda en büyük değer minimum değerden girilir. Sonsuz modu, bir işlem devam eden, ancak tamamlanma zamanı bilinmeyen olduğunu belirtmek için kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCRibbonProgressBar` sınıfı. Örnek, ilerleme çubuğu için minimum ve maksimum değerler ve ilerleme çubuğu geçerli konumunu ayarlayın (bir işleminin tamamlanma zamanı bilinmeyen olduğu) sonsuz modda çalışmak için ilerleme çubuğu ayarlamak nasıl gösterir. Bu kod parçacığını parçası olan [MS Office 2007 Demo örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxRibbonProgressBar.h  
  
##  <a name="cmfcribbonprogressbar"></a>CMFCRibbonProgressBar::CMFCRibbonProgressBar  
 Oluşturur ve başlatır bir [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) nesnesi.  
  
```  
CMFCRibbonProgressBar();

 
CMFCRibbonProgressBar(
    UINT nID,  
    int nWidth = 90,  
    int nHeight = 22);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
 Şerit ilerleme çubuğu komut Kimliğini belirtir.  
  
 [in]`nWidth`  
 Şerit ilerleme çubuğunun piksel cinsinden genişliğini belirtir.  
  
 [in]`nHeight`  
 Şerit ilerleme çubuğunun piksel cinsinden yüksekliği belirtir.  
  
##  <a name="getpos"></a>CMFCRibbonProgressBar::GetPos  
 İlerleme çubuğu geçerli konumunu döndürür.  
  
```  
int GetPos () const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlerleme çubuğu geçerli konumunu temsil eden bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlanan aralığı tarafından belirtilen aralıkta olmalıdır [CMFCRibbonProgressBar::SetRange](#setrange) yöntemi.  
  
##  <a name="getrangemax"></a>CMFCRibbonProgressBar::GetRangeMax  
 İlerleme çubuğu geçerli döndürür en büyük değer.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli aralığın maksimum değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrangemin"></a>CMFCRibbonProgressBar::GetRangeMin  
 İlerleme çubuğu geçerli döndürür en düşük aralık değeri.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli aralığın minimum değeri.  
  
##  <a name="getregularsize"></a>CMFCRibbonProgressBar::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isinfinitemode"></a>CMFCRibbonProgressBar::IsInfiniteMode  
 İlerleme çubuğu sonsuz modunda çalışıp çalışmadığını belirtir.  
  
```  
BOOL IsInfiniteMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`İlerleme çubuğu sonsuz modundaysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonsuz modunda ilerleme çubuğu, minimum değerden art arda en büyük değere doldurur. Sonsuz modu, bir işlem devam eden, ancak tamamlanma zamanı bilinmeyen olduğunu belirtmek için kullanabilirsiniz.  
  
##  <a name="ondraw"></a>CMFCRibbonProgressBar::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setinfinitemode"></a>CMFCRibbonProgressBar::SetInfiniteMode  
 Sonsuz modda çalışmak için ilerleme çubuğu ayarlar.  
  
```  
void SetInfiniteMode(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bSet`  
 `TRUE`İlerleme çubuğu sonsuz modunda olduğunu belirtmek için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlerleme çubuğu sonsuz modundaysa, genellikle, bu kullanıcı bir işlem devam eden, ancak tamamlanma zamanı bilinmiyor belirtiyor. Bu nedenle, ilerleme çubuğu art arda en büyük değer en küçük değerden doldurur.  
  
##  <a name="setpos"></a>CMFCRibbonProgressBar::SetPos  
 İlerleme çubuğu geçerli konumunu ayarlar.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nPos`  
 İlerleme çubuğu ayarlanmış konumunu belirtir.  
  
 [in]`bRedraw`  
 İlerleme çubuğu yeniden olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlanan aralığı tarafından belirtilen aralıkta olmalıdır [CMFCRibbonProgressBar::SetRange](#setrange) yöntemi.  
  
##  <a name="setrange"></a>CMFCRibbonProgressBar::SetRange  
 İlerleme çubuğu için minimum ve maksimum değerleri ayarlar.  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nMin`  
 Aralığın minimum değeri belirtir.  
  
 [in]`nMax`  
 Aralığın maksimum değeri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Minimum ve maksimum değerleri ayarlayarak ilerleme çubuğu aralığını tanımlamak için bu yöntemi kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
