---
description: 'Daha fazla bilgi edinin: CDaoRecordView Class'
title: CDaoRecordView sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDaoRecordView
- AFXDAO/CDaoRecordView
- AFXDAO/CDaoRecordView::CDaoRecordView
- AFXDAO/CDaoRecordView::IsOnFirstRecord
- AFXDAO/CDaoRecordView::IsOnLastRecord
- AFXDAO/CDaoRecordView::OnGetRecordset
- AFXDAO/CDaoRecordView::OnMove
helpviewer_keywords:
- CDaoRecordView [MFC], CDaoRecordView
- CDaoRecordView [MFC], IsOnFirstRecord
- CDaoRecordView [MFC], IsOnLastRecord
- CDaoRecordView [MFC], OnGetRecordset
- CDaoRecordView [MFC], OnMove
ms.assetid: 5aa7d0e2-bd05-413e-b216-80c404ce18ac
ms.openlocfilehash: cb91f6d3890806ac357a1f662905845598df1680
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248183"
---
# <a name="cdaorecordview-class"></a>CDaoRecordView sınıfı

Denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

## <a name="syntax"></a>Syntax

```
class AFX_NOVTABLE CDaoRecordView : public CFormView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDaoRecordView:: CDaoRecordView](#cdaorecordview)|Bir `CDaoRecordView` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoRecordView:: IsOnFirstRecord](#isonfirstrecord)|Geçerli kayıt, ilişkili kayıt kümesindeki ilk kayıtse sıfır olmayan bir değer döndürür.|
|[CDaoRecordView:: IsOnLastRecord](#isonlastrecord)|Geçerli kayıt, ilişkili kayıt kümesindeki son kayıt ise sıfır dışında bir değer döndürür.|
|[CDaoRecordView:: OnGetRecordset](#ongetrecordset)|Öğesinden türetilmiş bir sınıfın nesnesine bir işaretçi döndürür `CDaoRecordset` . ClassWizard bu işlevi sizin için geçersiz kılar ve gerekirse kayıt kümesini oluşturur.|
|[CDaoRecordView:: OnMove](#onmove)|Geçerli kayıt değiştirildiyse, verileri veri kaynağında güncelleştirir, ardından belirtilen kayda (ileri, önceki, ilk veya son) gider.|

## <a name="remarks"></a>Açıklamalar

Görünüm bir nesneye doğrudan bağlı olan bir form görünümüdür `CDaoRecordset` . Görünüm bir iletişim kutusu şablonu kaynağından oluşturulur ve `CDaoRecordset` iletişim kutusu şablonunun denetimlerindeki nesne alanlarını görüntüler. `CDaoRecordView`Nesne, form üzerindeki denetimler ve kayıt kümesinin alanları arasında veri hareketini otomatikleştirmek için iletişim kutusu veri değişimi (DDX) ve DAO Kayıt alanı değişimi (DFX) kullanır. `CDaoRecordView` Ayrıca, ilk, sonraki, önceki veya son kayda geçiş için varsayılan bir uygulama ve şu anda görünümdeki kayıtları güncelleştirmek için bir arabirim sağlar.

> [!NOTE]
> DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) tabanlı MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adlarında "CDao" öneki vardır. ODBC veri kaynaklarına yine de DAO sınıfları ile erişebilirsiniz; DAO sınıfları, Microsoft Jet veritabanı altyapısını kullandıkları için genellikle üstün yetenekler sunar.

Kayıt görünümünüzü oluşturmanın en yaygın yolu, uygulama sihirbazdır. Uygulama Sihirbazı, iskelet başlangıç uygulamanızın bir parçası olarak hem kayıt görünümü sınıfını hem de ilişkili kayıt kümesi sınıfını oluşturur.

Yalnızca tek bir forma ihtiyacınız varsa, uygulama Sihirbazı yaklaşımı daha kolay olur. ClassWizard, geliştirme sürecinde daha sonra bir kayıt görünümü kullanmaya karar vermenizi sağlar. Kayıt görünümü sınıfını uygulama sihirbazıyla birlikte oluşturmazsanız, daha sonra ClassWizard ile oluşturabilirsiniz. Bir kayıt görünümü ve bir kayıt kümesi oluşturmak için ClassWizard 'ı kullanarak, kayıt kümesi sınıfını ve onun adlandırmasında daha fazla denetim elde etmenizi sağlayan en esnek yaklaşım bu şekilde bağlanır. H/. CPP dosyaları. Bu yaklaşım ayrıca aynı kayıt kümesi sınıfında birden çok kayıt görünümüne sahip olmanızı sağlar.

Son kullanıcıların kayıt görünümündeki kayıttan kayda taşınmasını kolaylaştırmak için, uygulama Sihirbazı ilk, sonraki, önceki veya son kayda geçmek için menü (ve isteğe bağlı araç çubuğu) kaynakları oluşturur. ClassWizard ile bir kayıt görünümü sınıfı oluşturursanız, bu kaynakları menü ve bit eşlem düzenleyicilerle kendiniz oluşturmanız gerekir.

Kayıttan kayda geçiş için varsayılan uygulama hakkında daha fazla bilgi için, ve ve `IsOnFirstRecord` `IsOnLastRecord` için geçerli olan [bir kayıt görünümü kullanan](../../data/using-a-record-view-mfc-data-access.md)makaleye bakın `CRecordView` `CDaoRecordView` .

`CDaoRecordView` kayıt görünümünün Kullanıcı arabirimini güncelleştirebilmesi için kullanıcının kayıt kümesindeki konumunu izler. Kullanıcı, kayıt kümesinin sonuna kadar hareket ettirdiğinde, kayıt görünümü menü öğeleri veya araç çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerini aynı yönde taşımak için devre dışı bırakır.

Kayıt görünümünüzü ve kayıt kümesi sınıflarınızı bildirme ve kullanma hakkında daha fazla bilgi için, makale [kaydı görünümlerinde](../../data/record-views-mfc-data-access.md)"kayıt görünümü tasarlama ve oluşturma" konusuna bakın. Kayıt görünümlerinin nasıl çalıştığı ve nasıl kullanılacağı hakkında daha fazla bilgi için, [kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md)makalesine bakın. Yukarıda bahsedilen tüm makaleler hem hem de için `CRecordView` geçerlidir `CDaoRecordView` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`CDaoRecordView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="cdaorecordviewcdaorecordview"></a><a name="cdaorecordview"></a> CDaoRecordView:: CDaoRecordView

Öğesinden türetilmiş bir türden bir nesne oluşturduğunuzda `CDaoRecordView` , görünüm nesnesini başlatmak ve görünümün temel aldığı iletişim kaynağını belirlemek için Oluşturucu biçimini çağırın.

```
explicit CDaoRecordView(LPCTSTR lpszTemplateName);
explicit CDaoRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
Bir iletişim kutusu şablonu kaynağının adı olan null ile sonlandırılmış bir dize içerir.

*Nıdtemplate*<br/>
İletişim kutusu şablonu kaynağının KIMLIK numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Kaynağı ada (oluşturucuya bağımsız değişken olarak bir dize) veya KIMLIğINE göre tanımlayabilir (bağımsız değişken olarak işaretsiz bir tamsayı geçirin). Kaynak KIMLIĞI kullanılması önerilir.

> [!NOTE]
> Türetilmiş sınıfınızın kendi oluşturucusunu sağlaması gerekir. Türetilmiş sınıfınızın oluşturucusunda, oluşturucuyu `CDaoRecordView::CDaoRecordView` bir bağımsız değişken olarak kaynak adı veya kimliğiyle çağırın.

`CDaoRecordView::OnInitialUpdate` çağrısı `CWnd::UpdateData` olan çağırır `CWnd::DoDataExchange` . Bu ilk çağrı, `DoDataExchange` , `CDaoRecordView` `CDaoRecordset` ClassWizard tarafından oluşturulan alan veri üyelerine denetimleri (dolaylı olarak) bağlar. Bu veri üyeleri, temel sınıf üye işlevini çağırana kadar kullanılamaz `CFormView::OnInitialUpdate` .

> [!NOTE]
> ClassWizard kullanırsanız, sihirbaz **`enum`** sınıf bildiriminde bir değer tanımlar `CDaoRecordView::IDD` ve bunu oluşturucunun üye başlatma listesinde kullanır.

[!code-cpp[NVC_MFCDatabase#35](../../mfc/codesnippet/cpp/cdaorecordview-class_1.cpp)]

## <a name="cdaorecordviewisonfirstrecord"></a><a name="isonfirstrecord"></a> CDaoRecordView:: IsOnFirstRecord

Geçerli kaydın bu kayıt görünümüyle ilişkili kayıt kümesi nesnesindeki ilk kayıt olup olmadığını öğrenmek için bu üye işlevini çağırın.

```
BOOL IsOnFirstRecord();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıt, kayıt kümesindeki ilk kayıt ise sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ClassWizard tarafından yazılan varsayılan komut güncelleştirme işleyicilerinin kendi uygulamalarınızı yazmak için yararlıdır.

Kullanıcı ilk kayda geçerse, çerçeve tüm Kullanıcı arabirimi nesnelerini (örneğin, menü öğeleri veya araç çubuğu düğmeleri), ilk veya önceki kayda geçmek için devre dışı bırakır.

## <a name="cdaorecordviewisonlastrecord"></a><a name="isonlastrecord"></a> CDaoRecordView:: IsOnLastRecord

Geçerli kaydın bu kayıt görünümüyle ilişkili kayıt kümesi nesnesindeki son kayıt olup olmadığını öğrenmek için bu üye işlevini çağırın.

```
BOOL IsOnLastRecord();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıt, kayıt kümesindeki son kayıt ise sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ClassWizard 'ın kayıttan kayda geçiş için bir kullanıcı arabirimini desteklemek üzere yazdığı varsayılan komut güncelleştirme işleyicilerinin kendi uygulamalarınızı yazmak için yararlıdır.

> [!CAUTION]
> Bu işlevin sonucu, görünüm, Kullanıcı daha önce taşınana kadar kayıt kümesinin sonunu algılayamayabilir. Kayıt görünümü, bir sonraki veya son kayda geçiş için herhangi bir kullanıcı arabirimi nesnesini devre dışı bırakmasının gerektiğini anlayabilmeniz için, kullanıcının son kaydın ötesine taşınması gerekebilir. Kullanıcı son kaydı geçti ve sonra son kayda geri (veya daha önce) geçerse, kayıt görünümü kullanıcının kayıt kümesindeki konumunu izleyebilir ve Kullanıcı arabirimi nesnelerini doğru şekilde devre dışı bırakabilir.

## <a name="cdaorecordviewongetrecordset"></a><a name="ongetrecordset"></a> CDaoRecordView:: OnGetRecordset

`CDaoRecordset`Kayıt görünümüyle ilişkili, türetilmiş nesneye bir işaretçi döndürür.

```
virtual CDaoRecordset* OnGetRecordset() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

`CDaoRecordset`Nesne başarıyla oluşturulduysa türetilmiş nesneye yönelik bir işaretçi; aksi takdırde null işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturmak veya almak ve ona bir işaretçi döndürmek için bu üye işlevi geçersiz kılmalısınız. Kayıt görünümü sınıfınızı ClassWizard ile bildirirseniz, sihirbaz sizin için varsayılan bir geçersiz kılma yazar. ClassWizard 'ın varsayılan uygulama, varsa kayıt görünümünde depolanan kayıt kümesi işaretçisini döndürür. Aksi takdirde, ClassWizard ile belirlediğiniz türden bir kayıt kümesi nesnesi oluşturur ve `Open` tabloyu açmak veya sorguyu çalıştırmak için üye işlevini çağırır ve sonra nesneye bir işaretçi döndürür.

Daha fazla bilgi ve örnek için bkz. kayıt [görünümleri: kayıt görünümü kullanma](../../data/using-a-record-view-mfc-data-access.md).

## <a name="cdaorecordviewonmove"></a><a name="onmove"></a> CDaoRecordView:: OnMove

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

Varsayılan uygulama, `CDaoRecordset` kayıt görünümüyle ilişkili nesnenin uygun taşıma üye işlevini çağırır.

Varsayılan olarak, `OnMove` Kullanıcı kayıt görünümünde değiştiyse, veri kaynağındaki geçerli kaydı güncelleştirir.

Uygulama Sihirbazı, Ilk kayıt, son kayıt, sonraki kayıt ve önceki kayıt menü öğelerini içeren bir menü kaynağı oluşturur. Ilk araç çubuğu seçeneğini belirlerseniz, uygulama Sihirbazı bu komutlara karşılık gelen düğmelere sahip bir araç çubuğu da oluşturur.

Kayıt kümesindeki son kaydı geçmiş yaparsanız, kayıt görünümü son kaydı görüntülemeye devam eder. İlk kaydı daha sonra geri taşırsanız, kayıt görünümü ilk kaydı görüntülemeye devam eder.

> [!CAUTION]
> Çağıran `OnMove` , kayıt kümesinde kayıt yoksa bir özel durum oluşturur. `OnUpdateRecordFirst` `OnUpdateRecordLast` `OnUpdateRecordNext` `OnUpdateRecordPrev` Kayıt kümesinde herhangi bir kayıt olup olmadığını anlamak için karşılık gelen taşıma işleminden önce uygun Kullanıcı arabirimi güncelleştirme işleyicisi işlevini (,, veya) çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[CFormView sınıfı](../../mfc/reference/cformview-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoWorkspace sınıfı](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CFormView sınıfı](../../mfc/reference/cformview-class.md)
