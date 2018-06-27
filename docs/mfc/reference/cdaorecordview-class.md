---
title: CDaoRecordView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoRecordView
- AFXDAO/CDaoRecordView
- AFXDAO/CDaoRecordView::CDaoRecordView
- AFXDAO/CDaoRecordView::IsOnFirstRecord
- AFXDAO/CDaoRecordView::IsOnLastRecord
- AFXDAO/CDaoRecordView::OnGetRecordset
- AFXDAO/CDaoRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- CDaoRecordView [MFC], CDaoRecordView
- CDaoRecordView [MFC], IsOnFirstRecord
- CDaoRecordView [MFC], IsOnLastRecord
- CDaoRecordView [MFC], OnGetRecordset
- CDaoRecordView [MFC], OnMove
ms.assetid: 5aa7d0e2-bd05-413e-b216-80c404ce18ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a228a545061c4807688014b62907c4c41a82151e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952310"
---
# <a name="cdaorecordview-class"></a>CDaoRecordView sınıfı
Veritabanı kayıtlarını denetimlerinde görüntüleyen bir görünüm.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class AFX_NOVTABLE CDaoRecordView : public CFormView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoRecordView::CDaoRecordView](#cdaorecordview)|Oluşturan bir `CDaoRecordView` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoRecordView::IsOnFirstRecord](#isonfirstrecord)|Geçerli kayıt ilişkili kayıt kümesindeki ilk kaydı ise sıfır olmayan döndürür.|  
|[CDaoRecordView::IsOnLastRecord](#isonlastrecord)|Son kayıt ilişkili kayıt kümesindeki geçerli kayıt değilse, sıfır olmayan bir değer döndürür.|  
|[CDaoRecordView::OnGetRecordset](#ongetrecordset)|Türetilen sınıfın bir nesnesi için bir işaretçi döndüren `CDaoRecordset`. ClassWizard bu işlev için geçersiz kılmaları ve gerekiyorsa, kayıt kümesi oluşturur.|  
|[CDaoRecordView::OnMove](#onmove)|Geçerli kayıt değiştiyse, veri kaynağında güncelleştirir, ardından belirtilen kayda taşır (sonraki, önceki, ilk veya son).|  
  
## <a name="remarks"></a>Açıklamalar  
 Doğrudan bağlı bir form görünümü görünümdür bir `CDaoRecordset` nesnesi. Görünüm bir iletişim şablonunu kaynaktan oluşturulur ve alanlarını görüntüler `CDaoRecordset` iletişim şablonun denetimlerinde nesnesi. `CDaoRecordView` Form üzerinde denetimleri ve kayıt alanları arasında veri hareketini otomatikleştirmek için nesnesini kullanan iletişim kutusu veri değişimi (DDX) ve DAO kayıt alanı değişimi (DFX). `CDaoRecordView` Ayrıca taşıma için varsayılan uygulamasını sağlar, ilk sonraki, önceki ya da son kaydını ve kayıtta şu anda Görünümü güncelleştirmek için bir arabirim.  
  
> [!NOTE]
>  DAO veritabanı sınıfları açık veritabanı bağlantısı (ODBC) üzerinde tabanlı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. DAO sınıfları ile erişim ODBC veri kaynakları hala yapabilecekleriniz; Microsoft Jet veritabanı altyapısı kullandığından DAO sınıfları genellikle üstün yetenekleri sunar.  
  
 Uygulama Sihirbazı'nı kayıt görünümü oluşturmak için en yaygın yoludur. Uygulama Sihirbazı'nı kayıt görünümü sınıfı ve onun ilişkili kayıt kümesi sınıfını iskelet starter uygulamanız bir parçası olarak oluşturur.  
  
 Yalnızca tek bir form gerekiyorsa, Uygulama Sihirbazı yaklaşımı daha kolay olur. ClassWizard geliştirme işlemde daha sonra kayıt görünümü kullanmaya karar vermenizi sağlar. ClassWizard ile Uygulama Sihirbazı'nı kayıt görünümü sınıfını oluşturmazsanız, daha sonra oluşturabilirsiniz. Kayıt görünümü ve bir kayıt kümesi ayrı ayrı oluşturmak ve bunları bağlamak için ClassWizard kullanarak olduğundan en esnek bir yaklaşım, kayıt kümesi sınıfı adlandırma içinde daha fazla denetim sağlar ve kendi. H /. CPP dosyaları. Bu yaklaşım, birden çok kayıt görünümleri aynı kayıt kümesi sınıfı üzerinde sahip sağlar.  
  
 Kayıt görünümünde kayıttan kayda taşımak son kullanıcıların kolaylaştırmak için Uygulama Sihirbazı'nı menü (ve isteğe bağlı olarak araç çubuğu) oluşturur taşıma için kaynaklar, ilk sonraki, önceki ya da son kaydı. ClassWizard ile kayıt görünümü sınıfı oluşturursanız, bu kaynakları kendiniz menü ve bit eşlem düzenleyicileri oluşturmanız gerekir.  
  
 Kayıt başka bir kaydın taşınması için varsayılan uygulaması hakkında daha fazla bilgi için bkz: `IsOnFirstRecord` ve `IsOnLastRecord` ve makale [kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md), hem de uygulandığı `CRecordView` ve `CDaoRecordView`.  
  
 `CDaoRecordView` kullanıcının konumunu kayıt kümesindeki kayıt görünümü kullanıcı arabirimini güncelleştirebilmesi izler. Kullanıcı ya da kayıt kümesinin sonuna geçtiğinde, kayıt görünümü kullanıcı arabirimi nesneleri devre dışı bırakır — menü öğesi veya araç çubuğu düğmeleri gibi — taşıma için daha fazla ile aynı yönde.  
  
 Bildirme ve kayıt kümesi sınıfları ve kayıt görünümünü kullanma hakkında daha fazla bilgi için "tasarlama ve oluşturma bir kayıt" makalesinde görmek [kayıt görünümleri](../../data/record-views-mfc-data-access.md). Makaleyi nasıl kaydı iş görünümleri ve bunların nasıl kullanılacağını hakkında daha fazla bilgi için bkz: [kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md). Yukarıda belirtilen tüm makaleleri hem de uygulama `CRecordView` ve `CDaoRecordView`.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [Cformview'yu](../../mfc/reference/cformview-class.md)  
  
 `CDaoRecordView`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
##  <a name="cdaorecordview"></a>  CDaoRecordView::CDaoRecordView  
 Bir türdeki bir nesne oluştururken türetilen `CDaoRecordView`, görünüm nesnesini başlatır ve görünüm temel iletişim kutusu kaynağı tanımlamak için oluşturucu biçimindeki çağırın.  
  
```  
explicit CDaoRecordView(LPCTSTR lpszTemplateName);  
explicit CDaoRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszTemplateName*  
 Bir iletişim şablonunu kaynak adı null ile sonlandırılmış bir dize içeriyor.  
  
 *nIDTemplate*  
 Bir iletişim şablonunu kaynak kimliği numarasını içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak adı (pass bağımsız değişkeni olarak bir dize oluşturucusu için) veya Kimliğini (pass imzasız tamsayı bağımsız değişkeni olarak) tarafından ya da tanımlayabilirsiniz. Bir kaynağı kullanarak kimliği önerilir.  
  
> [!NOTE]
>  Türetilmiş sınıf kendi Oluşturucusu sağlamanız gerekir. Türetilmiş sınıf oluşturucu Oluşturucusu çağrı `CDaoRecordView::CDaoRecordView` kaynak adı veya bağımsız değişken olarak Kimliğine sahip.  
  
 `CDaoRecordView::OnInitialUpdate` çağrıları `CWnd::UpdateData`, çağıran `CWnd::DoDataExchange`. Bu ilk çağrı `DoDataExchange` bağlanır `CDaoRecordView` (dolaylı olarak) denetimleri `CDaoRecordset` alan veri üyeleri ClassWizard tarafından oluşturulmuş. Kadar temel sınıfı çağırdıktan sonra bu verileri üyeleri kullanılamaz `CFormView::OnInitialUpdate` üye işlevi.  
  
> [!NOTE]
>  ClassWizard kullanırsanız, sihirbazın tanımlayan bir **enum** değeri `CDaoRecordView::IDD` sınıf bildirimi ve oluşturucusu için üye başlatma içinde listesinde kullanır.  
  
 [!code-cpp[NVC_MFCDatabase#35](../../mfc/codesnippet/cpp/cdaorecordview-class_1.cpp)]  
  
##  <a name="isonfirstrecord"></a>  CDaoRecordView::IsOnFirstRecord  
 Geçerli kayıt bu kaydı görünüm ile ilişkilendirilen kayıt kümesi nesnesindeki ilk kaydı olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsOnFirstRecord();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk kaydı kayıt kümesindeki geçerli kayıt ise, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, komut güncelleştirme işleyicileri ClassWizard tarafından yazılan varsayılan kendi uygulamaları yazmak için yararlıdır.  
  
 Kullanıcı ilk kayda geçerse, herhangi bir kullanıcı arabirimi (örneğin menü öğesi veya araç çubuğu düğmeleri) nesnelerini devre dışı bırakır framework ilk veya önceki kayda taşımak için sahip.  
  
##  <a name="isonlastrecord"></a>  CDaoRecordView::IsOnLastRecord  
 Geçerli kayıt bu kaydı görünüm ile ilişkilendirilen kayıt kümesi nesnesi son kayıtta olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsOnLastRecord();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Son kaydı kayıt kümesindeki geçerli kayıt ise, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, kendi uygulamalarında varsayılan kayıt kaydı taşımak için bir kullanıcı arabirimi destekleyecek şekilde ClassWizard Yazar komut güncelleştirme işleyicileri yazmak için yararlıdır.  
  
> [!CAUTION]
>  Görünüm kayıt kümesinin son kullanıcı bu taşınmıştır kadar algılayabilir olmayabilir dışında bu işlevin sonucu güvenilirdir. Kullanıcı kayıt görünümü sonraki ya da son kayda taşıma için herhangi bir kullanıcı arabirimi nesneleri mamtelemetrydisabled anlayabilirsiniz önce son kaydı taşımanız gerekebilir. Kullanıcı son kaydı ve ardından geri son kaydı taşır (veya önceki), kayıt görünümü kümesinde kullanıcının konumunu izlemenize ve kullanıcı arabirimi nesneleri doğru devre dışı bırakabilirsiniz.  
  
##  <a name="ongetrecordset"></a>  CDaoRecordView::OnGetRecordset  
 Bir işaretçi döndürür `CDaoRecordset`-kayıt görünümü ile ilişkili nesne türetilmiş.  
  
```  
virtual CDaoRecordset* OnGetRecordset() = 0;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CDaoRecordset`-nesne, başarıyla oluşturulmuş aksi nesne türetilmiş bir **NULL** işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi oluşturmak veya bir kayıt kümesi nesnesini alın ve bir işaretçi döndürmek için geçersiz kılmanız gerekir. Kayıt görünümü sınıfınız ClassWizard ile bildirirseniz, sihirbaz varsayılan geçersiz kılma yazar. ClassWizard'ın varsayılan uygulaması varsa kayıt görünümünde depolanan kayıt kümesi işaretçi döndürür. Türündeki bir kayıt kümesi nesnesi oluşturur, varsa çağrıları ve ClassWizard ile belirtilen kendi `Open` üye tabloyu veya sorguyu çalıştırmak için işlev ve ardından bir işaretçi nesneyi döndürür.  
  
 Daha fazla bilgi ve örnekler için bkz: [kayıt görünümleri: kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>  CDaoRecordView::OnMove  
 Kayıt kümesi farklı bir kayda ve kayıt görünümü denetimlerinde alanları görüntülemek için bu üye işlevini çağırın.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDMoveCommand*  
 Aşağıdaki standart komut kimliği değerlerden biri:  
  
- `ID_RECORD_FIRST` Kayıt kümesindeki ilk kaydı taşıyın.  
  
- `ID_RECORD_LAST` Son kaydı kayıt kümesinde taşır.  
  
- `ID_RECORD_NEXT` Sonraki kayıt kümesinde taşıyın.  
  
- `ID_RECORD_PREV` Önceki kayıt kümesinde taşıyın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Taşıma başarılı olduğunda sıfır olmayan; taşıma isteği reddedildiyse aksi 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama uygun taşıma üye işlevini çağırır `CDaoRecordset` kayıt görünümü ile ilişkili nesne.  
  
 Varsayılan olarak, `OnMove` kullanıcı kayıt görünümünde değiştirilmesi durumunda geçerli kaydı veri kaynağında güncelleştirir.  
  
 Uygulama Sihirbazı'nı ilk kaydı, son kaydı, ileri kayıt ve önceki kayıt menü öğeleriyle menü kaynağı oluşturur. İlk araç seçeneği belirlerseniz, Uygulama Sihirbazı'nı bu komutları karşılık gelen düğmelerle bir araç çubuğu da oluşturur.  
  
 Kayıt kümesindeki son kayıt geçmiş taşırsanız, kayıt görünümü son kaydı görüntülemeye devam eder. Geriye doğru ilk kaydı taşırsanız, kayıt görünümü ilk kaydı görüntülemeye devam eder.  
  
> [!CAUTION]
>  Çağırma `OnMove` hiçbir kayıt kayıt varsa, bir özel durum oluşturur. Uygun kullanıcı arabirimi güncelleştirme işleyicisi işlevini çağırın — `OnUpdateRecordFirst`, `OnUpdateRecordLast`, `OnUpdateRecordNext`, veya `OnUpdateRecordPrev` — karşılık gelen önce taşıma işlemi kayıt herhangi bir kayıt olup olmadığını belirlemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cformview'yu sınıfı](../../mfc/reference/cformview-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset sınıfı](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef sınıfı](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef sınıfı](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase sınıfı](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace sınıfı](../../mfc/reference/cdaoworkspace-class.md)   
 [CFormView Sınıfı](../../mfc/reference/cformview-class.md)
