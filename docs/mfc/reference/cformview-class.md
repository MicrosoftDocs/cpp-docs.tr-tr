---
description: 'Daha fazla bilgi edinin: CFormView sınıfı'
title: CFormView sınıfı
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
ms.openlocfilehash: ec37a3819f299830fef96bfdf93c0170b2969c66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184315"
---
# <a name="cformview-class"></a>CFormView sınıfı

Form görünümleri için kullanılan temel sınıf.

## <a name="syntax"></a>Syntax

```
class CFormView : public CScrollView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFormView:: CFormView](#cformview)|Bir `CFormView` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFormView:: ısınitısdtamamlandı](#isinitdlgcompleted)|Başlatma sırasında eşitleme için kullanılır.|

## <a name="remarks"></a>Açıklamalar

Form görünümü temelde denetimleri içeren bir görünümüdür. Bu denetimler bir iletişim kutusu şablonu kaynağına göre düzenlenir. `CFormView`Uygulamanızda form istiyorsanız kullanın. Bu görünümler, [CScrollView](../../mfc/reference/cscrollview-class.md) işlevini kullanarak gerektiğinde kaydırmayı destekler.

[Bir Forms-Based uygulaması oluştururken](../../mfc/reference/creating-a-forms-based-mfc-application.md), `CFormView` form tabanlı bir uygulama yaparak görünüm sınıfını temel alabilirsiniz.

Belge görünümü tabanlı uygulamalara yeni [form konuları](../../mfc/form-views-mfc.md) da ekleyebilirsiniz. Uygulamanız başlangıçta formları desteklemeseler bile, yeni bir form eklediğinizde Visual C++ bu desteği ekler.

MFC Uygulama Sihirbazı ve sınıf Ekle komutu, form tabanlı uygulamalar oluşturmak için tercih edilen yöntemlerdir. Bu yöntemleri kullanmadan form tabanlı bir uygulama oluşturmanız gerekiyorsa bkz. [Forms-Based uygulama oluşturma](../../mfc/reference/creating-a-forms-based-mfc-application.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

`CFormView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

## <a name="cformviewcformview"></a><a name="cformview"></a> CFormView:: CFormView

Bir `CFormView` nesnesi oluşturur.

```
CFormView(LPCTSTR lpszTemplateName);
CFormView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
Bir iletişim şablonu kaynağının adı olan null ile sonlandırılmış bir dize içerir.

*Nıdtemplate*<br/>
İletişim kutusu-şablon kaynağının KIMLIK numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Öğesinden türetilmiş bir türden bir nesne oluşturduğunuzda `CFormView` , görünüm nesnesini oluşturmak ve görünümün temel aldığı iletişim kaynağını belirlemek için oluşturuculardan birini çağırın. Kaynağı ada göre (oluşturucuya bağımsız değişken olarak bir dize geçirerek) veya KIMLIğINE göre (bağımsız değişken olarak işaretsiz bir tamsayı geçirin) belirleyebilirsiniz.

Form görünümü penceresi ve alt denetimleri, `CWnd::Create` çağrılana kadar oluşturulmaz. `CWnd::Create` , belge şablonu tarafından yönetilen belge ve görünüm oluşturma işleminin parçası olarak Framework tarafından çağırılır.

> [!NOTE]
> Türetilmiş sınıfınızın kendi oluşturucusunu sağlaması *gerekir* . Oluşturucuda, `CFormView::CFormView` kaynak adı veya kimliğiyle, önceki sınıfa genel bakış bölümünde gösterildiği gibi bir bağımsız değişken olarak oluşturucuyu çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#90](../../mfc/codesnippet/cpp/cformview-class_1.h)]

[!code-cpp[NVC_MFCDocView#91](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]

## <a name="cformviewisinitdlgcompleted"></a><a name="isinitdlgcompleted"></a> CFormView:: ısınitısdtamamlandı

Diğer işlemleri gerçekleştirmeden önce başlatmanın tamamlanmasını sağlamak için MFC tarafından kullanılır.

```
BOOL IsInitDlgCompleted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu iletişim kutusu için başlatma işlevi tamamlanırsa true.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[CScrollView sınıfı](../../mfc/reference/cscrollview-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDialog sınıfı](../../mfc/reference/cdialog-class.md)<br/>
[CScrollView sınıfı](../../mfc/reference/cscrollview-class.md)
