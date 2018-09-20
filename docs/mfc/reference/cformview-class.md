---
title: CFormView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFormView
- AFXEXT/CFormView
- AFXEXT/CFormView::CFormView
- AFXEXT/CFormView::IsInitDlgCompleted
dev_langs:
- C++
helpviewer_keywords:
- CFormView [MFC], CFormView
- CFormView [MFC], IsInitDlgCompleted
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d65a82cf66180de9b647f792ed5a4024ab425800
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372207"
---
# <a name="cformview-class"></a>CFormView sınıfı

Form görünümleri için kullanılan taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CFormView : public CScrollView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFormView::CFormView](#cformview)|Oluşturur bir `CFormView` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFormView::IsInitDlgCompleted](#isinitdlgcompleted)|Eşitleme başlatma sırasında kullanılır.|

## <a name="remarks"></a>Açıklamalar

Bir form görünümü denetimleri içeren temel bir görünümüdür. Bu denetimlerin bir iletişim şablonunu kaynak göre düzenlenmiştir. Kullanım `CFormView` uygulamanızda forms istiyorsanız. Bu görünümler destek dikey kaydırma kullanarak, gerektiği şekilde [CScrollView](../../mfc/reference/cscrollview-class.md) işlevselliği.

Olduğunuzda [form tabanlı bir uygulama oluşturma](../../mfc/reference/creating-a-forms-based-mfc-application.md), kendi görünüm sınıfı dayandırabilir `CFormView`, form tabanlı bir uygulamayı kolaylaştırır.

Ayrıca yeni ekleyebilirsiniz [Form konuları](../../mfc/form-views-mfc.md) belge-görünüm-tabanlı uygulamalara. Uygulamanızı forms başlangıçta desteklemiyor olsa da, Visual C++, yeni bir form eklediğinizde bu desteği ekler.

MFC Uygulama Sihirbazı ve sınıf Ekle komutu form tabanlı uygulamalar oluşturmak için tercih edilen yöntemlerdir. Bu yöntemleri kullanarak olmadan bir form tabanlı uygulama oluşturma gerekiyorsa bkz [form tabanlı bir uygulama oluşturma](../../mfc/reference/creating-a-forms-based-mfc-application.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

`CFormView`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxext.h

##  <a name="cformview"></a>  CFormView::CFormView

Oluşturur bir `CFormView` nesne.

```
CFormView(LPCTSTR lpszTemplateName);
CFormView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
Bir iletişim şablonunu kaynak adı null ile sonlandırılmış bir dize içerir.

*nIDTemplate*<br/>
Bir iletişim şablonunu kaynak kimliği numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Bir türde bir nesne oluşturduğunuzda, türetilen `CFormView`, Görünüm nesnesi oluşturup, görünüm temel iletişim kaynağı tanımlamak için oluşturucular birini çağırın. Kaynak adı (pass bağımsız değişkeni olarak bir dize oluşturucuya) veya (pass bağımsız değişkeni olarak bir işaretsiz tamsayı) Kimliğini tanımlayabilirsiniz.

Form görünümü penceresi ve alt denetimler kadar oluşturulmaz `CWnd::Create` çağrılır. `CWnd::Create` Belge şablonu tarafından yönetildiği için belge ve görünüm oluşturma işleminin bir parçası olarak framework tarafından çağırılır.

> [!NOTE]
>  Türetilmiş sınıfınızın *gerekir* kendi Oluşturucu sağlayın. Oluşturucusunun içinde bir oluşturucu çağırmak `CFormView::CFormView`, kaynak adı veya kimliği önceki sınıfına genel bakış ' gösterildiği gibi bir bağımsız değişken olarak.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#90](../../mfc/codesnippet/cpp/cformview-class_1.h)]

[!code-cpp[NVC_MFCDocView#91](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]

##  <a name="isinitdlgcompleted"></a>  CFormView::IsInitDlgCompleted

MFC tarafından diğer işlemleri gerçekleştirmeden önce bu başlatma tamamlandı emin olmak için kullanılır.

```
BOOL IsInitDlgCompleted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu iletişim kutusunu başlatma işlevi tamamlandıysa true.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek SNAPVW](../../visual-cpp-samples.md)<br/>
[MFC örnek VIEWEX](../../visual-cpp-samples.md)<br/>
[CScrollView Sınıfı](../../mfc/reference/cscrollview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)<br/>
[CScrollView Sınıfı](../../mfc/reference/cscrollview-class.md)
