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
ms.openlocfilehash: 78d0dd3715ceb6a366ae1ab9ef2c2104432b30af
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446102"
---
# <a name="cdaorecordview-class"></a>CDaoRecordView sınıfı

Denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CDaoRecordView : public CFormView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDaoRecordView::CDaoRecordView](#cdaorecordview)|Oluşturur bir `CDaoRecordView` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoRecordView::IsOnFirstRecord](#isonfirstrecord)|Geçerli kayıt ilişkili kayıt bulunan ilk kayda ise sıfır döndürür.|
|[CDaoRecordView::IsOnLastRecord](#isonlastrecord)|Geçerli kayıt ilişkili kümesinde son kaydını ise sıfır döndürür.|
|[CDaoRecordView::OnGetRecordset](#ongetrecordset)|Türetilen bir sınıfın bir nesnesi için bir işaretçi döndürür `CDaoRecordset`. ClassWizard bu işlevi için geçersiz kılar ve gerekirse kayıt kümesi oluşturur.|
|[CDaoRecordView::OnMove](#onmove)|Geçerli kayıt değiştiyse, veri kaynağında güncelleştirir, sonra belirtilen kayıda taşır (sonraki, önceki, ilk veya son).|

## <a name="remarks"></a>Açıklamalar

Doğrudan bağlı bir form görünümü görünümdür bir `CDaoRecordset` nesne. Görünüm iletişim şablon kaynağı oluşturulur ve alanlarını görüntüler `CDaoRecordset` iletişim şablonun denetimlerinde nesne. `CDaoRecordView` Form üzerinde denetimleri ve alanları kümesi arasında veri taşıma işlemlerini otomatik hale getirmek için nesne kullanan iletişim kutusu veri değişimi (DDX) ve DAO kayıt alanı değişimi (DFX). `CDaoRecordView` Ayrıca taşımak için varsayılan bir uygulama sağlar, ilk İleri, önceki veya son kaydını ve kayıtta şu anda Görünümü güncelleştirmek için bir arabirim.

> [!NOTE]
>  DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) üzerinde göre MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. Hala DAO sınıfları ile ODBC veri kaynaklarına erişim de kullanabilirsiniz. DAO sınıfları, genellikle Microsoft Jet Veritabanı Altyapısı'na kullandığından üstün özellikler sunar.

Uygulama Sihirbazı'nı, kayıt görünümü oluşturmak için en yaygın yoludur. Kayıt görünümü sınıfını hem ilişkili kayıt kümesi sınıfıyla iskelet başlangıç uygulamanızın bir parçası olarak uygulama Sihirbazı oluşturur.

Yalnızca tek bir form gerekiyorsa, Uygulama Sihirbazı yaklaşım daha kolay olur. ClassWizard kayıt görünümü geliştirme işlemine daha sonra kullanmak karar vermenize olanak tanır. ClassWizard ile Uygulama Sihirbazı'nı kayıt görünüm sınıfı oluşturmazsanız, daha sonra oluşturabilirsiniz. ClassWizard kullanarak kayıt görünümü ve bir kayıt kümesi ayrı olarak oluşturma ve bunları bağlayın olduğundan en esnek bir yaklaşım, kayıt kümesi sınıfı adlandırma içinde daha fazla denetim verir ve kendi. S /. CPP dosyalarına. Bu yaklaşım, aynı kayıt sınıfta birden çok kayıt görünümleri sahip sağlar.

Kayıt görünümünde kaydı başka bir kayda git yapmasını kolaylaştırır, Uygulama Sihirbazı'nı menü (ve isteğe bağlı olarak araç) oluşturur ve kaynaklarını taşımak için ilk İleri, önceki ya da son kayıt. Kayıt görünümü sınıfı ClassWizard ile oluşturursanız, bu kaynakları kendiniz menü ve bit eşlem ile düzenleyicileri oluşturmanız gerekir.

Kayıttan diğerine taşımak için varsayılan uygulaması hakkında daha fazla bilgi için bkz: `IsOnFirstRecord` ve `IsOnLastRecord` ve makale [kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md), her ikisi de olarak uygulandığı `CRecordView` ve `CDaoRecordView`.

`CDaoRecordView` kullanıcının konumunu kayıt kümesindeki kayıt görünümü kullanıcı arabirimi güncelleştirebilmeniz izler. Kullanıcı kayıt ya da sonuna taşır, kayıt görünümü kullanıcı arabirimi nesneleri devre dışı bırakır; menü öğeleri ya da araç çubuğu düğmeleri gibi — taşımak için aynı yönde başka.

Bildirme ve kayıt kümesi sınıfları ve kayıt görünümünü kullanma hakkında daha fazla bilgi için "tasarlama ve oluşturma bir kayıt" makalesinde görmek [kayıt görünümleri](../../data/record-views-mfc-data-access.md). Nasıl iş kayıt görünümleri ve bunların nasıl kullanılacağı hakkında daha fazla bilgi için bkz [kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md). Yukarıda belirtilen tüm makaleler için her ikisinin de geçerli `CRecordView` ve `CDaoRecordView`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`CDaoRecordView`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

##  <a name="cdaorecordview"></a>  CDaoRecordView::CDaoRecordView

Bir türde bir nesne oluşturduğunuzda, türetilen `CDaoRecordView`, görünüm nesnesini başlatır ve görünüm tabanlı iletişim kaynağı tanımlamak için oluşturucu biçimindeki çağırın.

```
explicit CDaoRecordView(LPCTSTR lpszTemplateName);
explicit CDaoRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
Bir iletişim şablonunu kaynak adı null ile sonlandırılmış bir dize içerir.

*nIDTemplate*<br/>
Bir iletişim şablonunu kaynak kimliği numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Kaynak adı (pass bağımsız değişkeni olarak bir dize oluşturucuya) veya kendi Kimliğini (pass bağımsız değişkeni olarak bir işaretsiz tamsayı) ya da tespit edebilirsiniz. Bir kaynağı kullanarak kimliği önerilir.

> [!NOTE]
>  Türetilmiş sınıfınızın kendi Oluşturucusu sağlamanız gerekir. Türetilmiş sınıfınızın oluşturucuda oluşturucusunu `CDaoRecordView::CDaoRecordView` kaynak adı veya kimliği bağımsız değişken olarak.

`CDaoRecordView::OnInitialUpdate` çağrıları `CWnd::UpdateData`, çağıran `CWnd::DoDataExchange`. Bu ilk çağrı `DoDataExchange` bağlayan `CDaoRecordView` (dolaylı olarak) denetimleri `CDaoRecordset` alan ClassWizard tarafından oluşturulan veri üyeleri. Kadar da taban sınıfını çağırın, sonra bu veri üyeleri kullanılamaz `CFormView::OnInitialUpdate` üye işlevi.

> [!NOTE]
>  ClassWizard kullanırsanız, sihirbazın tanımlayan bir **enum** değer `CDaoRecordView::IDD` Oluşturucu üye başlatma içinde listesinde kullanımları ve sınıf bildirimi içinde.

[!code-cpp[NVC_MFCDatabase#35](../../mfc/codesnippet/cpp/cdaorecordview-class_1.cpp)]

##  <a name="isonfirstrecord"></a>  CDaoRecordView::IsOnFirstRecord

Bu kayıt görünümü ile ilişkili kayıt kümesi nesnesi bulunan ilk kayda geçerli kayıt olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsOnFirstRecord();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıt kümesinde ilk kaydı ise sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ClassWizard tarafından yazılan komut güncelleştirme işleyicileri varsayılan kendi uygulamaları yazmak için yararlıdır.

Kullanıcının ilk kayda geçerse framework devre dışı bırakır (örneğin, menü öğeleri veya araç çubuğu düğmeleri) herhangi bir kullanıcı arabirimi nesneleri ilk veya önceki kayda taşımak için sahip.

##  <a name="isonlastrecord"></a>  CDaoRecordView::IsOnLastRecord

Bu kayıt görünümü ile ilişkili kayıt kümesi nesnesi son kayıtta geçerli kayıt olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsOnLastRecord();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıt kümesinde son kayıttır olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ClassWizard kayıttan diğerine taşımak için bir kullanıcı arabirimi desteklemek için yazar komut güncelleştirme işleyicileri varsayılan kendi uygulamaları yazmak için yararlıdır.

> [!CAUTION]
>  Görünüm kümesi son kullanıcı, taşınan kadar algılayabilir olmayabilir dışında bu işlevin sonucu güvenilirdir. Kullanıcı, kayıt görünümü İleri veya son kayda taşımak için herhangi bir kullanıcı arabirimi nesneleri mamtelemetrydisabled söyleyebilirsiniz önce en son kaydını taşınması gerekebilir. Kullanıcının son kaydı ve ardından geri son kayıt taşır (veya önceki), kayıt görünümü kümesinde kullanıcının konumunu izlemenize ve kullanıcı arabirimi nesneleri doğru bir şekilde devre dışı bırakabilirsiniz.

##  <a name="ongetrecordset"></a>  CDaoRecordView::OnGetRecordset

Bir işaretçi döndürür `CDaoRecordset`-türetilmiş bir nesneye kayıt görünümü ile ilişkili.

```
virtual CDaoRecordset* OnGetRecordset() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CDaoRecordset`-başarıyla oluşturulmuş; tersi durumda nesne, türetilmiş bir nesneye bir NULL işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi oluşturmak veya bir kayıt kümesi nesnesi elde etmek için bir işaretçi döndürür geçersiz kılmanız gerekir. Kayıt görünümü sınıfınıza ClassWizard ile bildirirseniz, sihirbaz sizin için varsayılan geçersiz kılma yazar. ClassWizard'ın varsayılan uygulama, varsa, kayıt görünümü'nde depolanan kayıt kümesi işaretçi döndürür. Türünde bir kayıt kümesi nesnesi oluşturur, varsa çağrıları ve ClassWizard ile belirtilen kendi `Open` üye işlevi tabloyu veya sorguyu çalıştırmak için ve ardından nesneye bir işaretçi döndürür.

Daha fazla bilgi ve örnekler için bkz [kayıt görünümleri: kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md).

##  <a name="onmove"></a>  CDaoRecordView::OnMove

Kayıt kümesi farklı bir kayda ve kayıt görünümü denetimlerinde alanlarını görüntülemek için bu üye işlevini çağırın.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>Parametreler

*nIDMoveCommand*<br/>
Aşağıdaki standart komut kimliği değerlerden biri:

- Kayıt kümesi bulunan ilk kayda ID_RECORD_FIRST taşıyın.

- Kümesinde son kaydını ID_RECORD_LAST taşıyın.

- Sonraki kayıt kümesinde ID_RECORD_NEXT taşıyın.

- Önceki kayıt kümesinde ID_RECORD_PREV taşıyın.

### <a name="return-value"></a>Dönüş Değeri

Taşıma başarılı olursa sıfır dışı; taşıma isteği reddedildi, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama uygun taşıma üye işlevini çağırır `CDaoRecordset` kayıt görünümü ile ilişkili nesne.

Varsayılan olarak, `OnMove` geçerli kayıt veri kaynağı için kullanıcı kayıt görünümünde değişmişse güncelleştirir.

Uygulama Sihirbazı, bir menü kaynağı ile ilk kaydı son kayda sonraki kayıt ve önceki kayıt menü öğesi oluşturur. İlk araç seçeneği seçerseniz, Uygulama Sihirbazı'nı bir araç çubuğu düğmeleri için şu komutları karşılık gelen de oluşturur.

Kümesinde son kaydını geçmiş taşırsanız, kayıt görünümü en son kaydını görüntülemek devam eder. Kayıt görünümü ilk kaydı geriye taşırsanız, ilk kaydı görüntülemek devam eder.

> [!CAUTION]
>  Çağırma `OnMove` kayıt kayıt içermeyen bir özel durum oluşturur. Uygun kullanıcı arabirimini güncelleştirme işleyici işlevi çağrısı — `OnUpdateRecordFirst`, `OnUpdateRecordLast`, `OnUpdateRecordNext`, veya `OnUpdateRecordPrev` — karşılık gelen önce kayıt herhangi bir kayıt olup olmadığını belirlemek için işlem taşıyın.

## <a name="see-also"></a>Ayrıca Bkz.

[CFormView Sınıfı](../../mfc/reference/cformview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoWorkspace Sınıfı](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CFormView Sınıfı](../../mfc/reference/cformview-class.md)
