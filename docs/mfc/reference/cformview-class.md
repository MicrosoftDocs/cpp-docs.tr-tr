---
title: CFormView Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CFormView
- AFXEXT/CFormView
- AFXEXT/CFormView::CFormView
- AFXEXT/CFormView::IsInitDlgCompleted
helpviewer_keywords:
- CFormView [MFC], CFormView
- CFormView [MFC], IsInitDlgCompleted
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
ms.openlocfilehash: a9b897c661731878f0bf78c9d04ae7c4ba28cd42
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373796"
---
# <a name="cformview-class"></a>CFormView Sınıfı

Form görünümleri için kullanılan taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CFormView : public CScrollView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFormView::CFormView](#cformview)|Bir `CFormView` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFormView::IsInitDlgTamamlandı](#isinitdlgcompleted)|Başlatma sırasında eşitleme için kullanılır.|

## <a name="remarks"></a>Açıklamalar

Form görünümü temelde denetimleri içeren bir görünümdür. Bu denetimler, iletişim şablonu kaynağına göre düzenlenir. Başvurunuzdaki formları istiyorsanız kullanın. `CFormView` Bu görünümler, [gerektiğinde CScrollView](../../mfc/reference/cscrollview-class.md) işlevini kullanarak kaydırmayı destekler.

[Form Tabanlı Bir Uygulama Oluştururken,](../../mfc/reference/creating-a-forms-based-mfc-application.md)görünüm sınıfını `CFormView`form tabanlı bir uygulama haline getirerek temel alabilirsiniz.

Belge görünümü tabanlı uygulamalara yeni [Form Konuları](../../mfc/form-views-mfc.md) da ekleyebilirsiniz. Uygulamanız başlangıçta formları desteklememiş olsa bile, yeni bir form eklediğinizde Visual C++ bu desteği ekler.

MFC Uygulama Sihirbazı ve Sınıf Ekle komutu form tabanlı uygulamalar oluşturmak için tercih edilen yöntemlerdir. Bu yöntemleri kullanmadan forms tabanlı bir uygulama oluşturmanız gerekiyorsa, [bkz.](../../mfc/reference/creating-a-forms-based-mfc-application.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cview](../../mfc/reference/cview-class.md)

[Cscrollview](../../mfc/reference/cscrollview-class.md)

`CFormView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="cformviewcformview"></a><a name="cformview"></a>CFormView::CFormView

Bir `CFormView` nesne inşa eder.

```
CFormView(LPCTSTR lpszTemplateName);
CFormView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
İletişim şablonu kaynağının adı olan null-sonlandırılan bir dize içerir.

*nIDTemplate*<br/>
İletişim şablonu kaynağının kimlik numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Türetilen bir tür bir nesne `CFormView`oluşturduğunuzda, görünüm nesnesi oluşturmak ve görünümün dayandığı iletişim kaynağını tanımlamak için oluşturuculardan birini çağırın. Kaynağı ada göre (bir dizeyi bağımsız değişken olarak oluşturucuya geçirin) veya kimliğiyle (bağımsız değişken olarak imzasız bir tamsayı geçirin) tanımlayabilirsiniz.

Form görünümü penceresi ve alt denetimler `CWnd::Create` çağrılana kadar oluşturulmaz. `CWnd::Create`belge ve görünüm oluşturma işleminin bir parçası olarak çerçeve tarafından çağrılır, belge şablonu tarafından yönlendirilir.

> [!NOTE]
> Türemiş sınıfınız kendi oluşturucusu *sağlamalıdır.* Oluşturucuolarak, önceki sınıfgenel `CFormView::CFormView`bakışta gösterildiği gibi bir bağımsız değişken olarak kaynak adı veya kimlik ile, oluşturucu çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#90](../../mfc/codesnippet/cpp/cformview-class_1.h)]

[!code-cpp[NVC_MFCDocView#91](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]

## <a name="cformviewisinitdlgcompleted"></a><a name="isinitdlgcompleted"></a>CFormView::IsInitDlgTamamlandı

Diğer işlemleri gerçekleştirmeden önce başlatmanın tamamlandığından emin olmak için MFC tarafından kullanılır.

```
BOOL IsInitDlgCompleted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu iletişim kutusunun başlatma işlevi tamamlandıysa doğru.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[CScrollView Sınıfı](../../mfc/reference/cscrollview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)<br/>
[CScrollView Sınıfı](../../mfc/reference/cscrollview-class.md)
