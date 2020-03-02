---
title: CRecordView sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRecordView
- AFXDB/CRecordView
- AFXDB/CRecordView::CRecordView
- AFXDB/CRecordView::IsOnFirstRecord
- AFXDB/CRecordView::IsOnLastRecord
- AFXDB/CRecordView::OnGetRecordset
- AFXDB/CRecordView::OnMove
helpviewer_keywords:
- CRecordView [MFC], CRecordView
- CRecordView [MFC], IsOnFirstRecord
- CRecordView [MFC], IsOnLastRecord
- CRecordView [MFC], OnGetRecordset
- CRecordView [MFC], OnMove
- CRecordView [MFC], OnMove
ms.assetid: 9b4b0897-bd50-4d48-a0b4-f3323f5ccc55
ms.openlocfilehash: 409739d97c9f7ae9a730ac8f05bd86e647da2c71
ms.sourcegitcommit: ab8d7b47b63b62892a1256a09b1324a9a136eccf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2020
ms.locfileid: "78215539"
---
# <a name="crecordview-class"></a>CRecordView sınıfı

Denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CRecordView : public CFormView
```

## <a name="members"></a>Members

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CRecordView:: CRecordView](#crecordview)|`CRecordView` nesnesi oluşturur.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRecordView:: IsOnFirstRecord](#isonfirstrecord)|Geçerli kayıt, ilişkili kayıt kümesindeki ilk kayıtse sıfır olmayan bir değer döndürür.|
|[CRecordView:: IsOnLastRecord](#isonlastrecord)|Geçerli kayıt, ilişkili kayıt kümesindeki son kayıt ise sıfır dışında bir değer döndürür.|
|[CRecordView:: OnGetRecordset](#ongetrecordset)|`CRecordset`türetilen bir sınıfın nesnesine bir işaretçi döndürür. ClassWizard bu işlevi sizin için geçersiz kılar ve gerekirse kayıt kümesini oluşturur.|
|[CRecordView:: OnMove](#onmove)||

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRecordView:: OnMove](#onmove)|Geçerli kayıt değiştirildiyse, verileri veri kaynağında güncelleştirir, ardından belirtilen kayda (ileri, önceki, ilk veya son) gider.|

## <a name="remarks"></a>Açıklamalar

Görünüm bir `CRecordset` nesnesine doğrudan bağlı bir form görünümüdür. Görünüm bir iletişim kutusu şablonu kaynağından oluşturulur ve iletişim kutusu şablonunun denetimlerinde `CRecordset` nesnesinin alanlarını görüntüler. `CRecordView` nesnesi, form üzerindeki denetimler ve kayıt kümesi alanları arasında veri hareketini otomatik hale getirmek için iletişim kutusu veri değişimi (DDX) ve kayıt alanı değişimi (RFX) kullanır. `CRecordView` Ayrıca ilk, sonraki, önceki veya son kayda geçiş için varsayılan bir uygulama ve şu anda görünümdeki kayıtları güncelleştirmek için bir arabirim sağlar.

> [!NOTE]
>  Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıflarıyla çalışıyorsanız, bunun yerine [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) sınıfını kullanın. Daha fazla bilgi için bkz. [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

Kayıt görünümünüzü oluşturmanın en yaygın yolu, uygulama sihirbazdır. Uygulama Sihirbazı, iskelet başlangıç uygulamanızın bir parçası olarak hem kayıt görünümü sınıfını hem de ilişkili kayıt kümesi sınıfını oluşturur. Kayıt görünümü sınıfını uygulama sihirbazıyla birlikte oluşturmazsanız, daha sonra ClassWizard ile oluşturabilirsiniz. Yalnızca tek bir forma ihtiyacınız varsa, uygulama Sihirbazı yaklaşımı daha kolay olur. ClassWizard, geliştirme sürecinde daha sonra bir kayıt görünümü kullanmaya karar vermenizi sağlar. Bir kayıt görünümü ve bir kayıt kümesi oluşturmak için ClassWizard 'ı kullanarak, kayıt kümesi sınıfını ve onun adlandırmasında daha fazla denetim elde etmenizi sağlayan en esnek yaklaşım bu şekilde bağlanır. H/. CPP dosyaları. Bu yaklaşım ayrıca aynı kayıt kümesi sınıfında birden çok kayıt görünümüne sahip olmanızı sağlar.

Son kullanıcıların kayıt görünümündeki kayıttan kayda taşınmasını kolaylaştırmak için, uygulama Sihirbazı ilk, sonraki, önceki veya son kayda geçmek için menü (ve isteğe bağlı araç çubuğu) kaynakları oluşturur. ClassWizard ile bir kayıt görünümü sınıfı oluşturursanız, bu kaynakları menü ve bit eşlem düzenleyicilerle kendiniz oluşturmanız gerekir.

Kayıttan kayda geçiş için varsayılan uygulama hakkında daha fazla bilgi için, bkz. `IsOnFirstRecord` ve `IsOnLastRecord` ve [bir kayıt görünümü kullanma](../../data/using-a-record-view-mfc-data-access.md)makalesi.

`CRecordView`, kayıt görünümünün Kullanıcı arabirimini güncelleştirebilmesi için kullanıcının kayıt kümesindeki konumunu izlemesine devam eder. Kullanıcı, kayıt kümesinin sonuna kadar hareket ettirdiğinde, kayıt görünümü menü öğeleri veya araç çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerini aynı yönde taşımak için devre dışı bırakır.

Kayıt görünümünüzü ve kayıt kümesi sınıflarınızı bildirme ve kullanma hakkında daha fazla bilgi için, makale [kaydı görünümlerinde](../../data/record-views-mfc-data-access.md)"kayıt görünümü tasarlama ve oluşturma" konusuna bakın. Kayıt görünümlerinin nasıl çalıştığı ve nasıl kullanılacağı hakkında daha fazla bilgi için, [kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`CRecordView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

##  <a name="crecordview"></a>CRecordView:: CRecordView

`CRecordView`türetilmiş bir türden bir nesne oluşturduğunuzda, görünüm nesnesini başlatmak ve görünümün temel aldığı iletişim kaynağını belirlemek için Oluşturucu biçimini çağırın.

```
explicit CRecordView(LPCTSTR lpszTemplateName);
explicit CRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
Bir iletişim kutusu şablonu kaynağının adı olan null ile sonlandırılmış bir dize içerir.

*Nıdtemplate*<br/>
İletişim kutusu şablonu kaynağının KIMLIK numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Kaynağı ada (oluşturucuya bağımsız değişken olarak bir dize) veya KIMLIğINE göre tanımlayabilir (bağımsız değişken olarak işaretsiz bir tamsayı geçirin). Kaynak KIMLIĞI kullanılması önerilir.

> [!NOTE]
>  Türetilmiş sınıfınızın kendi oluşturucusunu sağlaması *gerekir* . Türetilmiş sınıfınızın oluşturucusunda, aşağıdaki örnekte gösterildiği gibi, Oluşturucu `CRecordView::CRecordView` kaynak adı veya KIMLIKLE birlikte bir bağımsız değişken olarak çağırın.

`CRecordView::OnInitialUpdate`, `DoDataExchange`çağıran `UpdateData`çağırır. Bu ilk `DoDataExchange` çağrısı, `CRecordView` denetimlerini (dolaylı) ClassWizard tarafından oluşturulan `CRecordset` alan veri üyelerine bağlar. Bu veri üyeleri, temel sınıf `CFormView::OnInitialUpdate` üye işlevini çağırana kadar kullanılamaz.

> [!NOTE]
>  ClassWizard kullanırsanız, sihirbaz bir **sabit listesi** değeri tanımlar `CRecordView::IDD`, sınıf bildiriminde belirtir ve bu öğeyi oluşturucunun üye başlatma listesinde kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#32](../../mfc/codesnippet/cpp/crecordview-class_1.cpp)]

##  <a name="isonfirstrecord"></a>CRecordView:: IsOnFirstRecord

Geçerli kaydın bu kayıt görünümüyle ilişkili kayıt kümesi nesnesindeki ilk kayıt olup olmadığını öğrenmek için bu üye işlevini çağırın.

```
BOOL IsOnFirstRecord();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıt, kayıt kümesindeki ilk kayıt ise sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ClassWizard tarafından yazılan varsayılan komut güncelleştirme işleyicilerinden kendi uygulamalarınızı yazmak için yararlıdır.

Kullanıcı ilk kayda taşınırsa, çerçeve ilk veya önceki kayda taşımak için sahip olduğunuz tüm Kullanıcı arabirimi nesnelerini devre dışı bırakır.

##  <a name="isonlastrecord"></a>CRecordView:: IsOnLastRecord

Geçerli kaydın bu kayıt görünümüyle ilişkili kayıt kümesi nesnesindeki son kayıt olup olmadığını öğrenmek için bu üye işlevini çağırın.

```
BOOL IsOnLastRecord();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıt, kayıt kümesindeki son kayıt ise sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ClassWizard 'ın kayıttan kayda geçiş için bir kullanıcı arabirimini desteklemek üzere yazdığı varsayılan komut güncelleştirme işleyicilerinin kendi uygulamalarınızı yazmak için yararlıdır.

> [!CAUTION]
>  Bu işlevin sonucu, görünümün Son Kullanıcı tarafından taşınana kadar kayıt kümesini algılayamayacağı durumlar dışında güvenilirdir. Kayıt görünümü, bir sonraki veya son kayda geçiş için herhangi bir kullanıcı arabirimi nesnesini devre dışı bırakmasının gerektiğini anlayabilmeniz için, kullanıcının son kaydın ötesine taşınması gerekir. Kullanıcı son kaydı geçti ve sonra son kayda geri (veya daha önce) geçerse, kayıt görünümü kullanıcının kayıt kümesindeki konumunu izleyebilir ve Kullanıcı arabirimi nesnelerini doğru şekilde devre dışı bırakabilir. `IsOnLastRecord`, ID_RECORD_LAST komutunu veya `CRecordset::MoveLast`işleyen uygulama işlevi `OnRecordLast`çağrısından sonra da güvenilmez.

##  <a name="ongetrecordset"></a>CRecordView:: OnGetRecordset

Kayıt görünümüyle ilişkili `CRecordset`türetilmiş nesneye bir işaretçi döndürür.

```
virtual CRecordset* OnGetRecordset() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulduysa `CRecordset`türetilmiş nesneye yönelik bir işaretçi; Aksi takdirde NULL işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturmak veya almak ve ona bir işaretçi döndürmek için bu üye işlevi geçersiz kılmalısınız. Kayıt görünümü sınıfınızı ClassWizard ile bildirirseniz, sihirbaz sizin için varsayılan bir geçersiz kılma yazar. ClassWizard 'ın varsayılan uygulama, varsa kayıt görünümünde depolanan kayıt kümesi işaretçisini döndürür. Aksi takdirde, ClassWizard ile belirlediğiniz türden bir kayıt kümesi nesnesi oluşturur ve tabloyu açmak veya sorguyu çalıştırmak için `Open` üye işlevini çağırır ve sonra nesneye bir işaretçi döndürür.

Daha fazla bilgi ve örnek için bkz. kayıt [görünümleri: kayıt görünümü kullanma](../../data/using-a-record-view-mfc-data-access.md).

##  <a name="onmove"></a>CRecordView:: OnMove

Kayıt kümesindeki farklı bir kayda gitmek ve kayıt görünümünün denetimlerinde alanlarını görüntülemek için bu üye işlevini çağırın.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>Parametreler

*Nıdmovecommand*<br/>
Aşağıdaki standart komut KIMLIĞI değerlerinden biri:

- ID_RECORD_FIRST, kayıt kümesindeki ilk kayda taşınır.

- ID_RECORD_LAST, kayıt kümesindeki son kayda taşınır.

- ID_RECORD_NEXT, kayıt kümesindeki bir sonraki kayda geçer.

- ID_RECORD_PREV, kayıt kümesindeki bir önceki kayda taşınır.

### <a name="return-value"></a>Dönüş Değeri

Taşıma başarılı olursa sıfır dışı; tersi durumda, taşıma isteği reddedildiyse 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, kayıt görünümüyle ilişkili `CRecordset` nesnesinin uygun `Move` üye işlevini çağırır.

Varsayılan olarak, Kullanıcı kayıt görünümünde değiştiyse, `OnMove` veri kaynağındaki geçerli kaydı güncelleştirir.

Uygulama Sihirbazı, Ilk kayıt, son kayıt, sonraki kayıt ve önceki kayıt menü öğelerini içeren bir menü kaynağı oluşturur. Dockable araç çubuğu seçeneğini belirlerseniz, uygulama Sihirbazı bu komutlara karşılık gelen düğmelere sahip bir araç çubuğu da oluşturur.

Kayıt kümesindeki son kaydı geçmiş yaparsanız, kayıt görünümü son kaydı görüntülemeye devam eder. İlk kaydı daha sonra geri taşırsanız, kayıt görünümü ilk kaydı görüntülemeye devam eder.

> [!CAUTION]
>  `OnMove` çağrısı, kayıt kümesinde kayıt yoksa bir özel durum oluşturur. Kayıt kümesinde herhangi bir kayıt olup olmadığını anlamak için ilgili taşıma işleminden önce, uygun Kullanıcı arabirimi güncelleştirme işleyicisi işlevini (`OnUpdateRecordFirst`, `OnUpdateRecordLast`, `OnUpdateRecordNext`veya `OnUpdateRecordPrev`) çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[CFormView Sınıfı](../../mfc/reference/cformview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CFormView Sınıfı](../../mfc/reference/cformview-class.md)
