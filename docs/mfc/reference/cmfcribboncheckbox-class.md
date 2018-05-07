---
title: CMFCRibbonCheckBox sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetCompactSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetIntermediateSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetRegularSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::IsDrawTooltipImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDraw
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawMenuImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawOnList
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::SetACCData
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCheckBox [MFC], CMFCRibbonCheckBox
- CMFCRibbonCheckBox [MFC], GetCompactSize
- CMFCRibbonCheckBox [MFC], GetIntermediateSize
- CMFCRibbonCheckBox [MFC], GetRegularSize
- CMFCRibbonCheckBox [MFC], IsDrawTooltipImage
- CMFCRibbonCheckBox [MFC], OnDraw
- CMFCRibbonCheckBox [MFC], OnDrawMenuImage
- CMFCRibbonCheckBox [MFC], OnDrawOnList
- CMFCRibbonCheckBox [MFC], SetACCData
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 109c3b2f6337adece6c371f1fafa98291468485e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribboncheckbox-class"></a>CMFCRibbonCheckBox sınıfı
`CMFCRibbonCheckBox` Sınıfı bir Şerit panelinde, hızlı erişim araç çubuğu veya açılan menüye ekleyebilirsiniz bir onay kutusu uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonCheckBox : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|(Geçersiz kılmaları [CMFCRibbonButton::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|  
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|(Geçersiz kılmaları [CMFCRibbonButton::GetIntermediateSize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).)|  
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|(Geçersiz kılmaları [CMFCRibbonButton::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|  
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|(Geçersiz kılmaları `CMFCRibbonButton::IsDrawTooltipImage`.)|  
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|(Geçersiz kılmaları [CMFCRibbonButton::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|  
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|(Geçersiz kılmaları [CMFCRibbonBaseElement::OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|  
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|(Geçersiz kılmaları `CMFCRibbonButton::OnDrawOnList`.)|  
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|(Geçersiz kılmaları [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanılacak bir `CMFCRibbonCheckBox` uygulamanızda, kodunuzu aşağıdaki oluşturucuyu ekleyin:  
  
```  
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)  
```  
Burada `nID` onay kutusunu komut kimliği ve `lpszText` onay kutusunun metin etiketi.  
  
 Kullanarak bir onay kutusu Şerit paneline ekleyebilir [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxribboncheckbox.h  
  
##  <a name="cmfcribboncheckbox"></a>  CMFCRibbonCheckBox::CMFCRibbonCheckBox  
 Şerit onay kutusunu nesnesinin Oluşturucusu  
  
```  
CMFCRibbonCheckBox(
    UINT nID,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nID`  
 Komut kimliğini belirtir.  
  
 [in] `lpszText`  
 Metin etiketi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit onay kutusunu nesnesi oluşturur.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCRibbonCheckBox` sınıfı.  
  
 [!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]  
  
##  <a name="getcompactsize"></a>  CMFCRibbonCheckBox::GetCompactSize  
 Geçersiz kılındığında, onay kutusunu compact boyutunu alır.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 İşaretçi `CDC` checkbox ile ilişkilendirilmiş.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `CSize` onay kutusunu compact boyutunu içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçersiz kılınmazsa, onay kutusunu Ara boyutu döndürür.  
  
##  <a name="getintermediatesize"></a>  CMFCRibbonCheckBox::GetIntermediateSize  
 Onay kutusu Ara boyutunu alır.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 İşaretçi `CDC` bu onay kutusu ile ilişkilendirilmiş.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CSize` onay kutusunu Ara boyutu içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçersiz kılınmazsa, Ara boyutu varsayılan onay kutusu boyutu olarak hesaplar ( `AFX_CHECK_BOX_DEFAULT_SIZE`) metin boyutu ve kenar boşlukları artı.  
  
##  <a name="getregularsize"></a>  CMFCRibbonCheckBox::GetRegularSize  
 Onay kutusu normal boyutunu alır.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 İşaretçi `CDC` bu onay kutusu ile ilişkili nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `CSize` onay kutusunu normal boyutunu içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçersiz kılınmazsa, onay kutusunu Ara boyutu döndürür.  
  
##  <a name="isdrawtooltipimage"></a>  CMFCRibbonCheckBox::IsDrawTooltipImage  
 Checkbox ile ilişkilendirilmiş bir araç ipucu görüntüsü olup olmadığını gösterir.  
  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` checkbox ile ilişkilendirilmiş bir araç ipucu görüntüsü ise veya `FALSE` değilse.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondraw"></a>  CMFCRibbonCheckBox::OnDraw  
 Belirtilen cihaz bağlamı kullanma onay kutusu Çiz çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 İşaretçi `CDC` onay kutusu Çiz edileceği.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawmenuimage"></a>  CMFCRibbonCheckBox::OnDrawMenuImage  
 Menü görüntüsü onay kutusu çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `CDC*`  
 İşaretçi `CDC` checkbox ile ilişkilendirilmiş.  
  
 [in] `CRect`  
 A `CRect` menü görüntüsü çizmek için dikdörtgende belirtme nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` görüntü çizilmiş varsa veya `FALSE` değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçersiz kılınmazsa, döndürür `FALSE`.  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonCheckBox::OnDrawOnList  
 Onay kutusu komutları liste kutusunda çizmek için framework tarafından çağrılır.  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Onay kutusu çizmek cihaz bağlamı işaretçi.  
  
 [in] `strText`  
 Görüntü metni.  
  
 [in] `nTextOffset`  
 Liste kutusu görüntüleme metni için sol tarafındaki piksel cinsinden uzaklığı.  
  
 [in] `rect`  
 Görüntü dikdörtgen onay kutusu.  
  
 [in] `bIsSelected`  
 `TRUE` onay kutusu seçili değilse veya `FALSE` değilse.  
  
 [in] `bHighlighted`  
 `TRUE` onay kutusu vurgulanmış, veya `FALSE` değilse.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setaccdata"></a>  CMFCRibbonCheckBox::SetACCData  
 Onay kutusu için erişilebilirlik verilerini ayarlar.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParent`  
 Onay kutusu üst pencere.  
  
 `data`  
 Onay için erişilebilirlik verileri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman döndürür `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak bu yöntem onay kutusu ve her zaman erişilebilirlik veri döndürür ayarlar `TRUE`. Erişilebilirlik veri kümesi ve başarı veya başarısızlık belirten bir değer döndürmek için bu yöntemi geçersiz kılın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel Sınıfı](../../mfc/reference/cmfcribbonpanel-class.md)
