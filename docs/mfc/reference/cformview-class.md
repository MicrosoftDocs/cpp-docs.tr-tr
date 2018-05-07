---
title: Cformview'yu sınıfı | Microsoft Docs
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
ms.openlocfilehash: 3486285b7b6430e9cd6f0e4a936aa3341bd72e0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cformview-class"></a>Cformview'yu sınıfı
Form görünümleri için kullanılan temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFormView : public CScrollView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFormView::CFormView](#cformview)|Oluşturan bir `CFormView` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFormView::IsInitDlgCompleted](#isinitdlgcompleted)|Eşitleme başlatma sırasında kullanılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Form görünümünde temelde denetimleri içeren bir Görünüm ' dir. Bu denetimlerin bir iletişim şablonunu kaynak göre düzenlenmiştir. Kullanım `CFormView` uygulamanızda forms istiyorsanız. Bu görünümler destek kaydırma kullanarak gerektiği kadar [CScrollView](../../mfc/reference/cscrollview-class.md) işlevselliği.  
  
 Olduğunuzda [Forms tabanlı bir uygulama oluşturma](../../mfc/reference/creating-a-forms-based-mfc-application.md), kendi görünüm sınıfı dayandırabilir `CFormView`, form tabanlı bir uygulama yapma.  
  
 Ayrıca yeni ekleyebilirsiniz [Form konuları](../../mfc/form-views-mfc.md) belge-görünüm-tabanlı uygulamalara. Uygulamanızı forms başlangıçta desteklememektedir olsa bile, Visual C++ yeni bir form eklediğinizde bu desteği ekler.  
  
 MFC Uygulama Sihirbazı'nı ve sınıf Ekle komutu form tabanlı uygulamalar oluşturmak için tercih edilen yöntemleridir. Bu yöntemleri kullanarak olmadan forms tabanlı bir uygulama oluşturmak gerekiyorsa bkz [Forms tabanlı bir uygulama oluşturma](../../mfc/reference/creating-a-forms-based-mfc-application.md).  
  
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
 Oluşturan bir `CFormView` nesnesi.  
  
```  
CFormView(LPCTSTR lpszTemplateName);  
CFormView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszTemplateName`  
 Bir iletişim şablonunu kaynak adı null ile sonlandırılmış bir dize içeriyor.  
  
 `nIDTemplate`  
 Bir iletişim şablonunu kaynak kimliği numarasını içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir türdeki bir nesne oluştururken türetilen `CFormView`, bir görünüm nesnesi oluşturmak ve görünüm temel iletişim kutusu kaynağı tanımlamak için oluşturucular çağırma. Kaynak adı (pass bağımsız değişkeni olarak bir dize oluşturucusu için) veya (pass imzasız tamsayı bağımsız değişkeni olarak) Kimliğine göre tanımlayabilirsiniz.  
  
 Form görünümünde pencere ve alt denetimleri kadar oluşturulmaz `CWnd::Create` olarak adlandırılır. `CWnd::Create` Belge şablonu tarafından yönlendirilen belge ve görünüm oluşturma işleminin bir parçası olarak çerçevesi tarafından çağrılır.  
  
> [!NOTE]
>  Türetilmiş sınıf *gerekir* kendi Oluşturucusu sağlayın. Oluşturucuda Oluşturucusu çağırma `CFormView::CFormView`, kaynak adı veya önceki sınıfına genel bakış gösterildiği gibi bir bağımsız değişken olarak Kimliğine sahip.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#90](../../mfc/codesnippet/cpp/cformview-class_1.h)]  
  
 [!code-cpp[NVC_MFCDocView#91](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]  
  
##  <a name="isinitdlgcompleted"></a>  CFormView::IsInitDlgCompleted  
 MFC tarafından diğer işlemleri gerçekleştirmeden önce bu başlatma tamamlandı sağlamak için kullanılır.  
  
```  
BOOL IsInitDlgCompleted() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu iletişim kutusunu başlatma işlevi tamamlanmışsa true.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek SNAPVW](../../visual-cpp-samples.md)   
 [MFC örnek VIEWEX](../../visual-cpp-samples.md)   
 [CScrollView sınıfı](../../mfc/reference/cscrollview-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDialog sınıfı](../../mfc/reference/cdialog-class.md)   
 [CScrollView Sınıfı](../../mfc/reference/cscrollview-class.md)
