---
title: CMFCRibbonStatusBarPane sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBarPane [MFC], CMFCRibbonStatusBarPane
- CMFCRibbonStatusBarPane [MFC], GetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], GetTextAlign
- CMFCRibbonStatusBarPane [MFC], IsAnimation
- CMFCRibbonStatusBarPane [MFC], IsExtended
- CMFCRibbonStatusBarPane [MFC], OnDrawBorder
- CMFCRibbonStatusBarPane [MFC], OnFillBackground
- CMFCRibbonStatusBarPane [MFC], SetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], SetAnimationList
- CMFCRibbonStatusBarPane [MFC], SetTextAlign
- CMFCRibbonStatusBarPane [MFC], StartAnimation
- CMFCRibbonStatusBarPane [MFC], StopAnimation
- CMFCRibbonStatusBarPane [MFC], OnFinishAnimation
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f59822504e317ee43ad7fb84345fa616fe72fae
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038438"
---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane sınıfı
`CMFCRibbonStatusBarPane` Sınıfı için Şerit durum çubuğu ekleyebileceğiniz bir Şerit öğesi uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Oluşturur ve başlatır bir `CMFCRibbonStatusBarPane` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|Kesmeden bölmesinde görüntülenen uzun metin dizesi tanımlayan bir dize döndürür.|  
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|Metin hizalama geçerli ayarını döndürür.|  
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|Animasyonun ediyor olup olmadığını belirler.|  
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|Bölmesini Şerit durum çubuğu genişletilmiş alanında bulunup bulunmadığını belirler.|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(Geçersiz kılmaları [CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|  
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(Geçersiz kılmaları [CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Kesmeden bölmesinde görüntülenen uzun metin dizesini tanımlar.|  
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Animasyon için kullanılabilecek bir görüntü listesi bölmesine atar.|  
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|Metin hizalamasını ayarlar.|  
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|Bölmesine atanan animasyonu başlatır.|  
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Bölmesine atanan animasyon durdurur. biçimindeki telefon numarasıdır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Bölmesine atanan animasyon durduğunda çerçevesi tarafından çağrılır.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemleri kullanımı gösterilmiştir `CMFCRibbonStatusBarPane` sınıfı. Örnek nasıl oluşturulacağını gösteren bir `CMFCRibbonStatusBarPane` nesne, durum çubuğu bölmesinin etiketinin metin hizalamasını ayarlama, kesmeden durum çubuğu bölmesinde görüntülenen, durum çubuğu bölmesine eklemek için kullanılan bir görüntü listesi uzun metin tanımlayan bir Meti ve başlangıç animasyon.  
  
 [!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxribbonstatusbarpane.h  
  
##  <a name="cmfcribbonstatusbarpane"></a>  CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane  
 Durum çubuğu bölmesinin nesnesinde oluşturun.  
  
```  
CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    BOOL bIsStatic=FALSE,  
    HICON hIcon=NULL,  
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nCmdID*  
 Bölmesinde komut Kimliğini belirtir.  
  
 [in] *lpszText*  
 Bölmesinde görüntülenecek metin dizesini belirtir.  
  
 [in] *bIsStatic*  
 Varsa `TRUE`, durum bölmesi vurgulanmış veya tıklayarak seçilmedi.  
  
 [in] *hIcon*  
 Bölmede gösterilecek bir simge için tanıtıcı belirtir.  
  
 [in] *lpszAlmostLargeText*  
 Bölmede görüntülenen uzun metin dizesini belirtir.  
  
 [in] *hBmpAnimationList*  
 Animasyon için kullanılan bir görüntü listesi için bir tanıtıcı belirtir.  
  
 [in] *cxAnimation*  
 Animasyon için kullanılan görüntü listesinde simgesinin piksel cinsinden genişliğini belirtir.  
  
 [in] *clrTrnsp*  
 Animasyon için kullanılan görüntü listesinde görüntüleri saydam rengini belirtir.  
  
 [in] *uiAnimationListResID*  
 Animasyon için kullanılan bir görüntü listesi kaynak Kimliğini belirtir.  
  
##  <a name="getalmostlargetext"></a>  CMFCRibbonStatusBarPane::GetAlmostLargeText  
 Durum çubuğu bölmesinin görüntüleyebilirsiniz uzun metin dizesini alır.  
  
```  
LPCTSTR GetAlmostLargeText() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durum çubuğu bölmesinin görüntüleyebilirsiniz uzun metin dizesi.  
  
##  <a name="gettextalign"></a>  CMFCRibbonStatusBarPane::GetTextAlign  
 Durum çubuğu bölmesinin etiketinin metin hizalaması geçerli ayarını alır.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şunlardan biri olabilir geçerli metni hizalama:  
  
-   TA_LEFT  
  
-   TA_CENTER  
  
-   TA_RIGHT.  
  
##  <a name="isanimation"></a>  CMFCRibbonStatusBarPane::IsAnimation  
 Animasyonun ediyor olup olmadığını belirler.  
  
```  
BOOL IsAnimation() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` animasyon devam ediyor `FALSE` Aksi takdirde.  
  
##  <a name="isextended"></a>  CMFCRibbonStatusBarPane::IsExtended  
 Bölmesini Şerit durum çubuğu genişletilmiş alanında bulunup bulunmadığını belirler.  
  
```  
BOOL IsExtended() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Durum çubuğu genişletilmiş alanı bölmesinde ise. `FALSE` Aksi takdirde.  
  
##  <a name="ondrawborder"></a>  CMFCRibbonStatusBarPane::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC*);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *CDC**  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onfillbackground"></a>  CMFCRibbonStatusBarPane::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onfinishanimation"></a>  CMFCRibbonStatusBarPane::OnFinishAnimation  
 Bölmesine atanan animasyon sona erdiğinde framework bu yöntemi çağırır.  
  
```  
virtual void OnFinishAnimation();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `StopAnimation` Yöntem çağrıları `OnFinishAnimation` animasyon sona erdiğinde verileri temizleme için kullanabileceğiniz yöntemi.  
  
##  <a name="setalmostlargetext"></a>  CMFCRibbonStatusBarPane::SetAlmostLargeText  
 Kesmeden durum çubuğu bölmesinde görüntülenen uzun metin tanımlayın.  
  
```  
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszAlmostLargeText*  
 Durum çubuğu bölmesinin kesmeden gösterilebilir uzun dizeyi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Metin boyutu kitaplığı hesaplar, *lpszAlmostLargeText* belirtir ve bölmesinde buna göre yeniden boyutlandırır. Bölmesinde hala sığmadığı metin kesilir.  
  
##  <a name="setanimationlist"></a>  CMFCRibbonStatusBarPane::SetAnimationList  
 Durum çubuğu bölmesine animasyon için kullanılabilecek bir görüntü listesi ekler.  
  
```  
void SetAnimationList(
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hBmpAnimationList*  
 Görüntü listesi için bir tanıtıcı belirtir.  
  
 [in] *cxAnimation*  
 Piksel cinsinden görüntü listesi çerçevede genişliğini belirtir.  
  
 [in] *clrTransp*  
 Resim listesi saydam rengini belirtir.  
  
 [in] *uiAnimationListResID*  
 Resim listesi kaynak Kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Resim listesi başarıyla durum çubuğu bölmesine bağlıysa; `FALSE` Aksi takdirde.  
  
##  <a name="settextalign"></a>  CMFCRibbonStatusBarPane::SetTextAlign  
 Durum çubuğu bölmesinin etiketinin metin hizalaması ayarlar.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nAlign*  
 Metin hizalamasını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 *nAlign* şu değerlerden biri olabilir:  
  
- `TA_LEFT`: hizalama sol  
  
- `TA_CENTER:` Ortala  
  
- `TA_RIGHT:` sağa hizalama  
  
##  <a name="startanimation"></a>  CMFCRibbonStatusBarPane::StartAnimation  
 Bölmesine atadığınız animasyonu başlatır.  
  
```  
void StartAnimation(
    UINT nFrameDelay=500,  
    UINT nDuration=-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nFrameDelay*  
 Animasyon kare hızı, milisaniye cinsinden belirtir.  
  
 [in] *nDuration*  
 Animasyon, milisaniye cinsinden yürütmek için ne kadar süreyle belirtir. -1 için sonsuz bir döngüde kullanın.  
  
### <a name="remarks"></a>Açıklamalar  
 Arama yapmadan önce bir resim listesi için bir tanıtıcı belirtmelisiniz `StartAnimation` kullanarak `SetAnimationList`.  
  
##  <a name="stopanimation"></a>  CMFCRibbonStatusBarPane::StopAnimation  
 Durum çubuğu bölmesine atanan animasyon durdurur.  
  
```  
void StopAnimation();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonStatusBar Sınıfı](../../mfc/reference/cmfcribbonstatusbar-class.md)
