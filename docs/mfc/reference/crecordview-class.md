---
title: CRecordView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRecordView
- AFXDB/CRecordView
- AFXDB/CRecordView::CRecordView
- AFXDB/CRecordView::IsOnFirstRecord
- AFXDB/CRecordView::IsOnLastRecord
- AFXDB/CRecordView::OnGetRecordset
- AFXDB/CRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- CRecordView [MFC], CRecordView
- CRecordView [MFC], IsOnFirstRecord
- CRecordView [MFC], IsOnLastRecord
- CRecordView [MFC], OnGetRecordset
- CRecordView [MFC], OnMove
- CRecordView [MFC], OnMove
ms.assetid: 9b4b0897-bd50-4d48-a0b4-f3323f5ccc55
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5908427a256595a032821d947ddad79ec588b6a
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853514"
---
# <a name="crecordview-class"></a>CRecordView sınıfı
Denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class AFX_NOVTABLE CRecordView : public CFormView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRecordView::CRecordView](#crecordview)|Oluşturur bir `CRecordView` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRecordView::IsOnFirstRecord](#isonfirstrecord)|Geçerli kayıt ilişkili kayıt bulunan ilk kayda ise sıfır döndürür.|  
|[CRecordView::IsOnLastRecord](#isonlastrecord)|Geçerli kayıt ilişkili kümesinde son kaydını ise sıfır döndürür.|  
|[CRecordView::OnGetRecordset](#ongetrecordset)|Türetilen bir sınıfın bir nesnesi için bir işaretçi döndürür `CRecordset`. ClassWizard bu işlevi için geçersiz kılar ve gerekirse kayıt kümesi oluşturur.|  
|[CRecordView::OnMove](#onmove)||  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRecordView::OnMove](#onmove)|Geçerli kayıt değiştiyse, veri kaynağında güncelleştirir, sonra belirtilen kayıda taşır (sonraki, önceki, ilk veya son).|  
  
## <a name="remarks"></a>Açıklamalar  
 Doğrudan bağlı bir form görünümü görünümdür bir `CRecordset` nesne. Görünüm iletişim şablon kaynağı oluşturulur ve alanlarını görüntüler `CRecordset` iletişim şablonun denetimlerinde nesne. `CRecordView` Form üzerinde denetimleri ve alanları kümesi arasında veri taşıma işlemlerini otomatik hale getirmek için nesne kullanan iletişim kutusu veri değişimi (DDX) ve kayıt alanı değişimi (RFX). `CRecordView` Ayrıca taşımak için varsayılan bir uygulama sağlar, ilk İleri, önceki ya da son kaydını ve kayıtta şu anda Görünümü güncelleştirmek için bir arabirim.  
  
> [!NOTE]
>  Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıfları ile çalışıyorsanız, sınıf kullanmak [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) yerine. Daha fazla bilgi için bkz [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).  
  
 Uygulama Sihirbazı'nı, kayıt görünümü oluşturmak için en yaygın yoludur. Kayıt görünümü sınıfını hem ilişkili kayıt kümesi sınıfıyla iskelet başlangıç uygulamanızın bir parçası olarak Tge Uygulama Sihirbazı oluşturur. ClassWizard ile Uygulama Sihirbazı'nı kayıt görünüm sınıfı oluşturmazsanız, daha sonra oluşturabilirsiniz. Yalnızca tek bir form gerekiyorsa, Uygulama Sihirbazı yaklaşım daha kolay olur. ClassWizard kayıt görünümü geliştirme işlemine daha sonra kullanmak karar vermenize olanak tanır. ClassWizard kullanarak kayıt görünümü ve bir kayıt kümesi ayrı olarak oluşturma ve bunları bağlayın olduğundan en esnek bir yaklaşım, kayıt kümesi sınıfı adlandırma içinde daha fazla denetim verir ve kendi. S /. CPP dosyalarına. Bu yaklaşım, aynı kayıt sınıfta birden çok kayıt görünümleri sahip sağlar.  
  
 Kayıt görünümünde kaydı başka bir kayda git yapmasını kolaylaştırır, Uygulama Sihirbazı'nı menü (ve isteğe bağlı olarak araç) oluşturur ve kaynaklarını taşımak için ilk İleri, önceki ya da son kayıt. Kayıt görünümü sınıfı ClassWizard ile oluşturursanız, bu kaynakları kendiniz menü ve bit eşlem ile düzenleyicileri oluşturmanız gerekir.  
  
 Kayıttan diğerine taşımak için varsayılan uygulaması hakkında daha fazla bilgi için bkz: `IsOnFirstRecord` ve `IsOnLastRecord` ve makale [kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md).  
  
 `CRecordView` kullanıcının konumunu kayıt kümesindeki kayıt görünümü kullanıcı arabirimi güncelleştirebilmeniz izler. Kullanıcı kayıt ya da sonuna taşır, kayıt görünümü kullanıcı arabirimi nesneleri devre dışı bırakır; menü öğeleri ya da araç çubuğu düğmeleri gibi — taşımak için aynı yönde başka.  
  
 Bildirme ve kayıt kümesi sınıfları ve kayıt görünümünü kullanma hakkında daha fazla bilgi için "tasarlama ve oluşturma bir kayıt" makalesinde görmek [kayıt görünümleri](../../data/record-views-mfc-data-access.md). Nasıl iş kayıt görünümleri ve bunların nasıl kullanılacağı hakkında daha fazla bilgi için bkz [kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CRecordView`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  
##  <a name="crecordview"></a>  CRecordView::CRecordView  
 Bir türde bir nesne oluşturduğunuzda, türetilen `CRecordView`, görünüm nesnesini başlatır ve görünüm tabanlı iletişim kaynağı tanımlamak için oluşturucu biçimindeki çağırın.  
  
```  
explicit CRecordView(LPCTSTR lpszTemplateName);  
explicit CRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszTemplateName*  
 Bir iletişim şablonunu kaynak adı null ile sonlandırılmış bir dize içerir.  
  
 *nIDTemplate*  
 Bir iletişim şablonunu kaynak kimliği numarasını içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak adı (pass bağımsız değişkeni olarak bir dize oluşturucuya) veya kendi Kimliğini (pass bağımsız değişkeni olarak bir işaretsiz tamsayı) ya da tespit edebilirsiniz. Bir kaynağı kullanarak kimliği önerilir.  
  
> [!NOTE]
>  Türetilmiş sınıfınızın *gerekir* kendi Oluşturucu sağlayın. Türetilmiş sınıfınızın oluşturucuda oluşturucusunu `CRecordView::CRecordView` kaynak adı veya kimliği aşağıdaki örnekte gösterildiği gibi bir bağımsız değişken olarak.  
  
 `CRecordView::OnInitialUpdate` çağrıları `UpdateData`, çağıran `DoDataExchange`. Bu ilk çağrı `DoDataExchange` bağlayan `CRecordView` (dolaylı olarak) denetimleri `CRecordset` alan ClassWizard tarafından oluşturulan veri üyeleri. Kadar da taban sınıfını çağırın, sonra bu veri üyeleri kullanılamaz `CFormView::OnInitialUpdate` üye işlevi.  
  
> [!NOTE]
>  ClassWizard kullanırsanız, sihirbazın tanımlayan bir **enum** değer `CRecordView::IDD`, sınıf bildirimi içinde belirtir ve üye başlatma listesinde Oluşturucusu kullanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#32](../../mfc/codesnippet/cpp/crecordview-class_1.cpp)]  
  
##  <a name="isonfirstrecord"></a>  CRecordView::IsOnFirstRecord  
 Bu kayıt görünümü ile ilişkili kayıt kümesi nesnesi bulunan ilk kayda geçerli kayıt olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsOnFirstRecord();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli kayıt kümesinde ilk kaydı ise sıfır olmayan; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, ClassWizard tarafından yazılan komut güncelleştirme işleyicileri varsayılan kendi uygulamaları yazmak için yararlıdır.  
  
 Kullanıcının ilk kayda taşınırsa, ilk veya önceki kayda taşımak için sahip olduğunuz herhangi bir kullanıcı arabirimi nesneleri framework devre dışı bırakır.  
  
##  <a name="isonlastrecord"></a>  CRecordView::IsOnLastRecord  
 Bu kayıt görünümü ile ilişkili kayıt kümesi nesnesi son kayıtta geçerli kayıt olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsOnLastRecord();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli kayıt kümesinde son kayıttır olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, ClassWizard kayıttan diğerine taşımak için bir kullanıcı arabirimi desteklemek için yazar komut güncelleştirme işleyicileri varsayılan kendi uygulamaları yazmak için yararlıdır.  
  
> [!CAUTION]
>  Kullanıcı, taşınan kadar görünümü kümesinin sonuna algılayamaz dışında bu işlevin sonucu güvenilirdir. Kayıt görünümü İleri veya son kayda taşımak için herhangi bir kullanıcı arabirimi nesneleri mamtelemetrydisabled söyleyebilirsiniz önce kullanıcının son kaydını taşımanız gerekir. Kullanıcının son kaydı ve ardından geri son kayıt taşır (veya önceki), kayıt görünümü kümesinde kullanıcının konumunu izlemenize ve kullanıcı arabirimi nesneleri doğru bir şekilde devre dışı bırakabilirsiniz. `IsOnLastRecord` Ayrıca uygulama işlev çağrısı yapıldıktan sonra güvenilir değil `OnRecordLast`, ID_RECORD_LAST komut işleme veya `CRecordset::MoveLast`.  
  
##  <a name="ongetrecordset"></a>  CRecordView::OnGetRecordset  
 Bir işaretçi döndürür `CRecordset`-türetilmiş bir nesneye kayıt görünümü ile ilişkili.  
  
```  
virtual CRecordset* OnGetRecordset() = 0;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CRecordset`-başarıyla oluşturulmuş; tersi durumda nesne, türetilmiş bir nesneye bir NULL işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi oluşturmak veya bir kayıt kümesi nesnesi elde etmek için bir işaretçi döndürür geçersiz kılmanız gerekir. Kayıt görünümü sınıfınıza ClassWizard ile bildirirseniz, sihirbaz sizin için varsayılan geçersiz kılma yazar. ClassWizard'ın varsayılan uygulama, varsa, kayıt görünümü'nde depolanan kayıt kümesi işaretçi döndürür. Türünde bir kayıt kümesi nesnesi oluşturur, varsa çağrıları ve ClassWizard ile belirtilen kendi `Open` üye işlevi tabloyu veya sorguyu çalıştırmak için ve ardından nesneye bir işaretçi döndürür.  
  
 Daha fazla bilgi ve örnekler için bkz [kayıt görünümleri: kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>  CRecordView::OnMove  
 Kayıt kümesi farklı bir kayda ve kayıt görünümü denetimlerinde alanlarını görüntülemek için bu üye işlevini çağırın.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDMoveCommand*  
 Aşağıdaki standart komut kimliği değerlerden biri:  
  
- Kayıt kümesi bulunan ilk kayda ID_RECORD_FIRST taşıyın.  
  
- Kümesinde son kaydını ID_RECORD_LAST taşıyın.  
  
- Sonraki kayıt kümesinde ID_RECORD_NEXT taşıyın.  
  
- Önceki kayıt kümesinde ID_RECORD_PREV taşıyın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Taşıma başarılı olursa sıfır dışı; taşıma isteği reddedildi, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama uygun çağırır `Move` üye işlevinin `CRecordset` kayıt görünümü ile ilişkili nesne.  
  
 Varsayılan olarak, `OnMove` geçerli kayıt veri kaynağı için kullanıcı kayıt görünümünde değişmişse güncelleştirir.  
  
 Uygulama Sihirbazı, bir menü kaynağı ile ilk kaydı son kayda sonraki kayıt ve önceki kayıt menü öğesi oluşturur. Yerleştirilebilir araç seçeneği seçerseniz, Uygulama Sihirbazı'nı bir araç çubuğu düğmeleri için şu komutları karşılık gelen de oluşturur.  
  
 Kümesinde son kaydını geçmiş taşırsanız, kayıt görünümü en son kaydını görüntülemek devam eder. Kayıt görünümü ilk kaydı geriye taşırsanız, ilk kaydı görüntülemek devam eder.  
  
> [!CAUTION]
>  Çağırma `OnMove` kayıt kayıt içermeyen bir özel durum oluşturur. Uygun kullanıcı arabirimini güncelleştirme işleyici işlevi çağrısı — `OnUpdateRecordFirst`, `OnUpdateRecordLast`, `OnUpdateRecordNext`, veya `OnUpdateRecordPrev` — karşılık gelen önce kayıt herhangi bir kayıt olup olmadığını belirlemek için işlem taşıyın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFormView sınıfı](../../mfc/reference/cformview-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CRecordset sınıfı](../../mfc/reference/crecordset-class.md)   
 [CFormView Sınıfı](../../mfc/reference/cformview-class.md)
