---
title: CRecordView Sınıfı
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
ms.openlocfilehash: b706a80f91a3c952d80da13f453a807c775b9405
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368349"
---
# <a name="crecordview-class"></a>CRecordView Sınıfı

Denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CRecordView : public CFormView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CRecordView::CRecordView](#crecordview)|Bir `CRecordView` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRecordView::IsonFirstRecord](#isonfirstrecord)|Geçerli kayıt ilişkili kayıt kümesindeki ilk kayıtsa sıfırsız döndürür.|
|[CRecordView::IsonLastRecord](#isonlastrecord)|Geçerli kayıt ilişkili kayıt kümesindeki son kayıtsa sıfırsız döndürür.|
|[CRecordView::OnGetRecordset](#ongetrecordset)|Bir işaretçiyi türetilen bir `CRecordset`sınıfın nesnesine döndürür. ClassWizard bu işlevi sizin için geçersiz kılar ve gerekirse kayıt kümesini oluşturur.|
|[CRecordView::OnMove](#onmove)||

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRecordView::OnMove](#onmove)|Geçerli kayıt değiştiyse, veri kaynağında güncelleştirir, ardından belirtilen kayda (sonraki, önceki, ilk veya son) taşınır.|

## <a name="remarks"></a>Açıklamalar

Görünüm, doğrudan bir nesneye `CRecordset` bağlı bir form görünümüdür. Görünüm bir iletişim şablonu kaynağından oluşturulur ve `CRecordset` iletişim şablonunun denetimlerinde nesnenin alanlarını görüntüler. Nesne, `CRecordView` formdaki denetimler ile kayıt kümesinin alanları arasındaki veri hareketini otomatikleştirmek için iletişim veri alışverişi (DDX) ve kayıt alanı değişimi (RFX) kullanır. `CRecordView`ayrıca, ilk, sonraki, önceki veya son kayda geçmek için varsayılan bir uygulama ve şu anda görünümde olan kaydı güncelleştirmek için bir arabirim sağlar.

> [!NOTE]
> Açık Veritabanı Bağlantısı (ODBC) sınıfları yerine Veri Erişim Nesneleri (DAO) sınıflarıyla çalışıyorsanız, bunun yerine [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) sınıfını kullanın. Daha fazla bilgi için genel bakış makalesine [bakın: Veritabanı Programlama.](../../data/data-access-programming-mfc-atl.md)

Kayıt görünümünüzü oluşturmanın en yaygın yolu Uygulama Sihirbazı'dır. Uygulama Sihirbazı, iskelet başlatıcı uygulamanızın bir parçası olarak hem kayıt görünümü sınıfını hem de ilişkili kayıt kümesi sınıfını oluşturur. Uygulama Sihirbazı ile kayıt görünümü sınıfını oluşturmazsanız, daha sonra ClassWizard ile oluşturabilirsiniz. Tek bir forma ihtiyacınız varsa, Uygulama Sihirbazı yaklaşımı daha kolaydır. ClassWizard, geliştirme işleminin ilerleyen saatlerinde bir kayıt görünümü kullanmaya karar vermenizi sağlar. Bir kayıt görünümü ve bir kayıt kümesi oluşturmak için ClassWizard kullanarak ayrı ayrı ve sonra bunları bağlamak en esnek bir yaklaşımdır çünkü kayıt kümesi sınıf ve onun adlandırma daha fazla kontrol sağlar. H/. CPP dosyaları. Bu yaklaşım, aynı kayıt kümesi sınıfında birden çok kayıt görüntülemeniz iniz de sağlar.

Son kullanıcıların kayıt görünümünde kayıttan kayda geçmelerini kolaylaştırmak için, Uygulama Sihirbazı ilk, sonraki, önceki veya son kayda geçmek için menü (ve isteğe bağlı araç çubuğu) kaynakları oluşturur. ClassWizard ile bir kayıt görünümü sınıfı oluşturursanız, menü ve bitmap düzenleyicileri ile bu kaynakları kendiniz oluşturmanız gerekir.

Kayıttan kayda geçmek için varsayılan uygulama `IsOnFirstRecord` hakkında `IsOnLastRecord` bilgi için bkz ve [Kayıt Görünümü Kullanma](../../data/using-a-record-view-mfc-data-access.md)makalesi.

`CRecordView`kayıt görünümünün kullanıcı arabirimini güncelleştirebilmeleri için kullanıcının kayıt kümesindeki konumunu izler. Kullanıcı kayıt kümesinin her iki ucuna da taşındığında, kayıt görünümü aynı yönde daha fazla hareket etmek için kullanıcı arabirimi nesnelerini (menü öğeleri veya araç çubuğu düğmeleri gibi) devre dışı kılabilir.

Kayıt görünümü ve kayıt kümesi sınıflarınızı bildirme ve kullanma hakkında daha fazla bilgi için [Kayıt Görünümleri](../../data/record-views-mfc-data-access.md)makalesinde "Kayıt Görünümü Tasarlama ve Oluşturma" bölümüne bakın. Kayıt görünümleri nasıl çalıştığı ve bunların nasıl kullanılacağı hakkında daha fazla bilgi için [Kayıt Görünümü Kullanma](../../data/using-a-record-view-mfc-data-access.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cview](../../mfc/reference/cview-class.md)

[Cscrollview](../../mfc/reference/cscrollview-class.md)

[Cformview](../../mfc/reference/cformview-class.md)

`CRecordView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="crecordviewcrecordview"></a><a name="crecordview"></a>CRecordView::CRecordView

Türetilen bir tür bir nesne `CRecordView`oluşturduğunuzda, görünüm nesnesini başlatmaya ve görünümün dayandığı iletişim kaynağını tanımlamak için yapı oluşturucunun her iki formunu da arayın.

```
explicit CRecordView(LPCTSTR lpszTemplateName);
explicit CRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
İletişim şablonu kaynağının adı olan null-sonlandırılan bir dize içerir.

*nIDTemplate*<br/>
İletişim şablonu kaynağının kimlik numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Kaynağı ada göre tanımlayabilir (bir dizeyi oluşturucuya bağımsız değişken olarak geçirin) veya kimliğiyle (bağımsız değişken olarak imzasız bir tamsayı geçirin). Kaynak kimliği kullanılması önerilir.

> [!NOTE]
> Türemiş sınıfınız kendi oluşturucusu *sağlamalıdır.* Türemiş sınıfınızın oluşturucusunda, `CRecordView::CRecordView` aşağıdaki örnekte gösterildiği gibi kaynak adı veya kimliği içeren oluşturucuyu bağımsız değişken olarak arayın.

`CRecordView::OnInitialUpdate`aramalar `UpdateData`, `DoDataExchange`hangi çağırır . Bu ilk `DoDataExchange` çağrı, `CRecordView` denetimleri (dolaylı `CRecordset` olarak) ClassWizard tarafından oluşturulan alan veri üyelerine bağlar. Bu veri üyeleri, taban sınıf `CFormView::OnInitialUpdate` üye işlevini aramadan sonra kullanılamaz.

> [!NOTE]
> ClassWizard kullanıyorsanız, sihirbaz bir **enum** `CRecordView::IDD`değeri tanımlar, sınıf bildiriminde belirtir ve oluşturucu için üye başlatma listesinde kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#32](../../mfc/codesnippet/cpp/crecordview-class_1.cpp)]

## <a name="crecordviewisonfirstrecord"></a><a name="isonfirstrecord"></a>CRecordView::IsonFirstRecord

Geçerli kaydın bu kayıt görünümüyle ilişkili kayıt kümesi nesnesindeki ilk kayıt olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsOnFirstRecord();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıt kayıt kümesindeki ilk kayıtsa sıfır sız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ClassWizard tarafından yazılmış varsayılan komut güncelleştirme işleyicileri kendi uygulamalarını yazmak için yararlıdır.

Kullanıcı ilk kayda geçerse, çerçeve ilk veya önceki kayda geçmek için sahip olduğunuz kullanıcı arabirimi nesnelerini devre dışı kılabilir.

## <a name="crecordviewisonlastrecord"></a><a name="isonlastrecord"></a>CRecordView::IsonLastRecord

Geçerli kaydın bu kayıt görünümüyle ilişkili kayıt kümesi nesnesindeki son kayıt olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsOnLastRecord();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıt kayıt kümesindeki son kayıtsa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ClassWizard'ın kayıttan kayda geçmek için kullanıcı arabirimini desteklemek için yazdığı varsayılan komut güncelleştirme işleyicilerinin kendi uygulamalarını yazmak için yararlıdır.

> [!CAUTION]
> Bu işlevin sonucu, görünümün kullanıcı geçmiş taşıyınana kadar kayıt kümesinin sonunu algılayamadığı dışında güvenilirdir. Kayıt görünümü, bir sonraki veya son kayda geçmek için herhangi bir kullanıcı arabirimi nesnelerini devre dışı bırakması gerektiğini söyleyebilmek için kullanıcının son kaydın ötesine geçmesi gerekir. Kullanıcı son kaydı geçip son kayda (veya ondan önce) geri dönerse, kayıt görünümü kullanıcının kayıt kümesindeki konumunu izleyebilir ve kullanıcı arabirimi nesnelerini doğru şekilde devre dışı bırakabilirsiniz. `IsOnLastRecord`uygulama işlevine `OnRecordLast`yapılan bir çağrıdan sonra da güvenilmezdir , `CRecordset::MoveLast`ID_RECORD_LAST komutunu işler veya.

## <a name="crecordviewongetrecordset"></a><a name="ongetrecordset"></a>CRecordView::OnGetRecordset

Bir işaretçiyi `CRecordset`kayıt görünümüyle ilişkili türetilmiş nesneye döndürür.

```
virtual CRecordset* OnGetRecordset() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla `CRecordset`oluşturulduysa, türetilmiş bir nesneye işaretçi; aksi takdirde bir NULL işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturmak veya elde etmek ve bir işaretçi döndürmek için bu üye işlevi geçersiz kılmanız gerekir. ClassWizard ile kayıt görünümü sınıfını bildirirseniz, sihirbaz sizin için varsayılan geçersiz kılma yazar. ClassWizard'ın varsayılan uygulaması, varsa kayıt görünümünde depolanan kayıt kümesi işaretçisini döndürür. Değilse, ClassWizard ile belirttiğiniz türün bir kayıt kümesi nesnesi inşa eder ve tabloyu açmak veya sorguyu çalıştırmak için `Open` üye işlevini çağırır ve sonra nesneye bir işaretçi döndürür.

Daha fazla bilgi ve örnekler için Kayıt Görünümleri makalesine [bakın: Kayıt Görünümü kullanma.](../../data/using-a-record-view-mfc-data-access.md)

## <a name="crecordviewonmove"></a><a name="onmove"></a>CRecordView::OnMove

Kayıt kümesinde farklı bir kayda geçmek ve alanlarını kayıt görünümü denetimlerinde görüntülemek için bu üye işlevini çağırın.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>Parametreler

*nIDMoveCommand*<br/>
Aşağıdaki standart komut kimliği değerlerinden biri:

- ID_RECORD_FIRST Kayıt setindeki ilk rekora geçin.

- ID_RECORD_LAST Kayıt setindeki son rekora geçin.

- ID_RECORD_NEXT Kayıt setinde bir sonraki kayda geçin.

- ID_RECORD_PREV Kayıt kümesindeki önceki rekora geçin.

### <a name="return-value"></a>Dönüş Değeri

Hareket başarılı olduysa sıfırolmayan; aksi takdirde 0 taşıma isteği reddedildi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, kayıt `Move` görünümüyle `CRecordset` ilişkili nesnenin uygun üye işlevini çağırır.

Varsayılan olarak, kullanıcı kayıt görünümünde değiştirdiyse, `OnMove` veri kaynağındaki geçerli kaydı güncelleştirir.

Uygulama Sihirbazı, İlk Kayıt, Son Kayıt, Sonraki Kayıt ve Önceki Kayıt menü öğelerini içeren bir menü kaynağı oluşturur. Takılabilir Araç Çubuğu seçeneğini seçerseniz, Uygulama Sihirbazı da bu komutlara karşılık gelen düğmeleri içeren bir araç çubuğu oluşturur.

Kayıt kümesindeki son kaydı geçerseniz, kayıt görünümü son kaydı görüntülemeye devam edin. İlk kaydın ötesine geçerseniz, kayıt görünümü ilk kaydı görüntülemeye devam edin.

> [!CAUTION]
> Kayıt `OnMove` kümesinde kayıt yoksa arama bir özel durum oluşturur. Kayıt kümesinde herhangi bir kayıt `OnUpdateRecordFirst` `OnUpdateRecordLast`olup `OnUpdateRecordNext`olmadığını `OnUpdateRecordPrev` belirlemek için ilgili taşıma işleminden önce uygun kullanıcı arabirimi güncelleştirme işleyicisi işlevini (, , , veya — ) çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[CFormView Sınıfı](../../mfc/reference/cformview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CFormView Sınıfı](../../mfc/reference/cformview-class.md)
