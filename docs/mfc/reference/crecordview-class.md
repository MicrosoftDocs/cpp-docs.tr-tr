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
ms.openlocfilehash: d3d040f2da622cbfd6d1577729861917a5a03270
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079153"
---
# <a name="crecordview-class"></a>CRecordView sınıfı
Veritabanı kayıtlarını denetimlerinde görüntüleyen bir görünüm.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class AFX_NOVTABLE CRecordView : public CFormView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRecordView::CRecordView](#crecordview)|Oluşturan bir `CRecordView` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRecordView::IsOnFirstRecord](#isonfirstrecord)|Geçerli kayıt ilişkili kayıt kümesindeki ilk kaydı ise sıfır olmayan döndürür.|  
|[CRecordView::IsOnLastRecord](#isonlastrecord)|Son kayıt ilişkili kayıt kümesindeki geçerli kayıt değilse, sıfır olmayan bir değer döndürür.|  
|[CRecordView::OnGetRecordset](#ongetrecordset)|Türetilen sınıfın bir nesnesi için bir işaretçi döndüren `CRecordset`. ClassWizard bu işlev için geçersiz kılmaları ve gerekiyorsa, kayıt kümesi oluşturur.|  
|[CRecordView::OnMove](#onmove)||  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRecordView::OnMove](#onmove)|Geçerli kayıt değiştiyse, veri kaynağında güncelleştirir, ardından belirtilen kayda taşır (sonraki, önceki, ilk veya son).|  
  
## <a name="remarks"></a>Açıklamalar  
 Doğrudan bağlı bir form görünümü görünümdür bir `CRecordset` nesnesi. Görünüm bir iletişim şablonunu kaynaktan oluşturulur ve alanlarını görüntüler `CRecordset` iletişim şablonun denetimlerinde nesnesi. `CRecordView` Form üzerinde denetimleri ve kayıt alanları arasında veri hareketini otomatikleştirmek için nesnesini kullanan iletişim kutusu veri değişimi (DDX) ve kayıt alanı değişimi (RFX). `CRecordView` Ayrıca taşıma için varsayılan uygulamasını sağlar, ilk sonraki, önceki ya da son kaydını ve kayıtta şu anda Görünümü güncelleştirmek için bir arabirim.  
  
> [!NOTE]
>  Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıfları ile çalışıyorsanız, bir sınıf kullanma [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) yerine. Daha fazla bilgi için bkz: [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).  
  
 Uygulama Sihirbazı'nı kayıt görünümü oluşturmak için en yaygın yoludur. Kayıt görünümü sınıfı ve onun ilişkili kayıt kümesi sınıfını iskelet starter uygulamanız bir parçası olarak Tge Uygulama Sihirbazı'nı oluşturur. ClassWizard ile Uygulama Sihirbazı'nı kayıt görünümü sınıfını oluşturmazsanız, daha sonra oluşturabilirsiniz. Yalnızca tek bir form gerekiyorsa, Uygulama Sihirbazı yaklaşımı daha kolay olur. ClassWizard geliştirme işlemde daha sonra kayıt görünümü kullanmaya karar vermenizi sağlar. Kayıt görünümü ve bir kayıt kümesi ayrı ayrı oluşturmak ve bunları bağlamak için ClassWizard kullanarak olduğundan en esnek bir yaklaşım, kayıt kümesi sınıfı adlandırma içinde daha fazla denetim sağlar ve kendi. H /. CPP dosyaları. Bu yaklaşım, birden çok kayıt görünümleri aynı kayıt kümesi sınıfı üzerinde sahip sağlar.  
  
 Kayıt görünümünde kayıttan kayda taşımak son kullanıcıların kolaylaştırmak için Uygulama Sihirbazı'nı menü (ve isteğe bağlı olarak araç çubuğu) oluşturur taşıma için kaynaklar, ilk sonraki, önceki ya da son kaydı. ClassWizard ile kayıt görünümü sınıfı oluşturursanız, bu kaynakları kendiniz menü ve bit eşlem düzenleyicileri oluşturmanız gerekir.  
  
 Kayıt başka bir kaydın taşınması için varsayılan uygulaması hakkında daha fazla bilgi için bkz: `IsOnFirstRecord` ve `IsOnLastRecord` ve makale [kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md).  
  
 `CRecordView` kullanıcının konumunu kayıt kümesindeki kayıt görünümü kullanıcı arabirimini güncelleştirebilmesi izler. Kullanıcı ya da kayıt kümesinin sonuna geçtiğinde, kayıt görünümü kullanıcı arabirimi nesneleri devre dışı bırakır — menü öğesi veya araç çubuğu düğmeleri gibi — taşıma için daha fazla ile aynı yönde.  
  
 Bildirme ve kayıt kümesi sınıfları ve kayıt görünümünü kullanma hakkında daha fazla bilgi için "tasarlama ve oluşturma bir kayıt" makalesinde görmek [kayıt görünümleri](../../data/record-views-mfc-data-access.md). Makaleyi nasıl kaydı iş görünümleri ve bunların nasıl kullanılacağını hakkında daha fazla bilgi için bkz: [kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [Cformview'yu](../../mfc/reference/cformview-class.md)  
  
 `CRecordView`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  
##  <a name="crecordview"></a>  CRecordView::CRecordView  
 Bir türdeki bir nesne oluştururken türetilen `CRecordView`, görünüm nesnesini başlatır ve görünüm temel iletişim kutusu kaynağı tanımlamak için oluşturucu biçimindeki çağırın.  
  
```  
explicit CRecordView(LPCTSTR lpszTemplateName);  
explicit CRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszTemplateName*  
 Bir iletişim şablonunu kaynak adı null ile sonlandırılmış bir dize içeriyor.  
  
 *nIDTemplate*  
 Bir iletişim şablonunu kaynak kimliği numarasını içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak adı (pass bağımsız değişkeni olarak bir dize oluşturucusu için) veya Kimliğini (pass imzasız tamsayı bağımsız değişkeni olarak) tarafından ya da tanımlayabilirsiniz. Bir kaynağı kullanarak kimliği önerilir.  
  
> [!NOTE]
>  Türetilmiş sınıf *gerekir* kendi Oluşturucusu sağlayın. Türetilmiş sınıf oluşturucu Oluşturucusu çağrı `CRecordView::CRecordView` kaynak adı veya aşağıdaki örnekte gösterildiği gibi bir bağımsız değişken olarak Kimliğine sahip.  
  
 **CRecordView::OnInitialUpdate** çağrıları `UpdateData`, çağıran `DoDataExchange`. Bu ilk çağrı `DoDataExchange` bağlanır `CRecordView` (dolaylı olarak) denetimleri `CRecordset` alan veri üyeleri ClassWizard tarafından oluşturulmuş. Kadar temel sınıfı çağırdıktan sonra bu verileri üyeleri kullanılamaz **CFormView::OnInitialUpdate** üye işlevi.  
  
> [!NOTE]
>  ClassWizard kullanırsanız, sihirbazın tanımlayan bir **enum** değeri `CRecordView::IDD`sınıfı bildiriminde belirtir ve üye başlatma listesinde Oluşturucusu kullanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#32](../../mfc/codesnippet/cpp/crecordview-class_1.cpp)]  
  
##  <a name="isonfirstrecord"></a>  CRecordView::IsOnFirstRecord  
 Geçerli kayıt bu kaydı görünüm ile ilişkilendirilen kayıt kümesi nesnesindeki ilk kaydı olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsOnFirstRecord();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk kaydı kayıt kümesindeki geçerli kayıt ise, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, varsayılan, kendi uygulamalarını ClassWizard tarafından yazılan komut güncelleştirme işleyicileri yazmak için yararlıdır.  
  
 Kullanıcı ilk kayda geçerse, ilk veya önceki kayda taşımak için sahip tüm kullanıcı arabirimi nesneleri framework devre dışı bırakır.  
  
##  <a name="isonlastrecord"></a>  CRecordView::IsOnLastRecord  
 Geçerli kayıt bu kaydı görünüm ile ilişkilendirilen kayıt kümesi nesnesi son kayıtta olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsOnLastRecord();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Son kaydı kayıt kümesindeki geçerli kayıt ise, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, kendi uygulamalarında varsayılan kayıt kaydı taşımak için bir kullanıcı arabirimi destekleyecek şekilde ClassWizard Yazar komut güncelleştirme işleyicileri yazmak için yararlıdır.  
  
> [!CAUTION]
>  Kullanıcı bu taşınmıştır dek görünümü kayıt kümesinin sonuna algılayamaz dışında bu işlevin sonucu güvenilirdir. Kayıt görünümü sonraki ya da son kayda taşıma için herhangi bir kullanıcı arabirimi nesneleri mamtelemetrydisabled anlayabilirsiniz önce kullanıcı son kaydı taşımanız gerekir. Kullanıcı son kaydı ve ardından geri son kaydı taşır (veya önceki), kayıt görünümü kümesinde kullanıcının konumunu izlemenize ve kullanıcı arabirimi nesneleri doğru devre dışı bırakabilirsiniz. `IsOnLastRecord` Ayrıca uygulama işlevi çağrısı sonra güvenilir olmayan `OnRecordLast`, yürüten `ID_RECORD_LAST` komutu veya `CRecordset::MoveLast`.  
  
##  <a name="ongetrecordset"></a>  CRecordView::OnGetRecordset  
 Bir işaretçi döndürür `CRecordset`-kayıt görünümü ile ilişkili nesne türetilmiş.  
  
```  
virtual CRecordset* OnGetRecordset() = 0;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CRecordset`-nesne, başarıyla oluşturulmuş aksi nesne türetilmiş bir **NULL** işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi oluşturmak veya bir kayıt kümesi nesnesini alın ve bir işaretçi döndürmek için geçersiz kılmanız gerekir. Kayıt görünümü sınıfınız ClassWizard ile bildirirseniz, sihirbaz varsayılan geçersiz kılma yazar. ClassWizard'ın varsayılan uygulaması varsa kayıt görünümünde depolanan kayıt kümesi işaretçi döndürür. Türündeki bir kayıt kümesi nesnesi oluşturur, varsa çağrıları ve ClassWizard ile belirtilen kendi `Open` üye tabloyu veya sorguyu çalıştırmak için işlev ve ardından bir işaretçi nesneyi döndürür.  
  
 Daha fazla bilgi ve örnekler için bkz: [kayıt görünümleri: kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>  CRecordView::OnMove  
 Kayıt kümesi farklı bir kayda ve kayıt görünümü denetimlerinde alanları görüntülemek için bu üye işlevini çağırın.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDMoveCommand`  
 Aşağıdaki standart komut kimliği değerlerden biri:  
  
- `ID_RECORD_FIRST` Kayıt kümesindeki ilk kaydı taşıyın.  
  
- `ID_RECORD_LAST` Son kaydı kayıt kümesinde taşır.  
  
- `ID_RECORD_NEXT` Sonraki kayıt kümesinde taşıyın.  
  
- `ID_RECORD_PREV` Önceki kayıt kümesinde taşıyın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Taşıma başarılı olduğunda sıfır olmayan; taşıma isteği reddedildiyse aksi 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama uygun çağırır `Move` üye işlevini `CRecordset` kayıt görünümü ile ilişkili nesne.  
  
 Varsayılan olarak, `OnMove` kullanıcı kayıt görünümünde değiştirilmesi durumunda geçerli kaydı veri kaynağında güncelleştirir.  
  
 Uygulama Sihirbazı'nı ilk kaydı, son kaydı, ileri kayıt ve önceki kayıt menü öğeleriyle menü kaynağı oluşturur. Dockable Araç çubuğu seçeneğini belirlerseniz, Uygulama Sihirbazı'nı bu komutları karşılık gelen düğmelerle bir araç çubuğu da oluşturur.  
  
 Kayıt kümesindeki son kayıt geçmiş taşırsanız, kayıt görünümü son kaydı görüntülemeye devam eder. Geriye doğru ilk kaydı taşırsanız, kayıt görünümü ilk kaydı görüntülemeye devam eder.  
  
> [!CAUTION]
>  Çağırma `OnMove` hiçbir kayıt kayıt varsa, bir özel durum oluşturur. Uygun kullanıcı arabirimi güncelleştirme işleyicisi işlevini çağırın — `OnUpdateRecordFirst`, `OnUpdateRecordLast`, `OnUpdateRecordNext`, veya `OnUpdateRecordPrev` — karşılık gelen önce taşıma işlemi kayıt herhangi bir kayıt olup olmadığını belirlemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cformview'yu sınıfı](../../mfc/reference/cformview-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CRecordset sınıfı](../../mfc/reference/crecordset-class.md)   
 [CFormView Sınıfı](../../mfc/reference/cformview-class.md)
