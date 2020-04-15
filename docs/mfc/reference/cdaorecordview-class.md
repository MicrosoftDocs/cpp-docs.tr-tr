---
title: CDaoRecordView Sınıfı
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
ms.openlocfilehash: b8c411dbd29316219759351f1f1633b6e57b92e8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377140"
---
# <a name="cdaorecordview-class"></a>CDaoRecordView Sınıfı

Denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CDaoRecordView : public CFormView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDaoRecordView::CDaoRecordView](#cdaorecordview)|Bir `CDaoRecordView` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDaoRecordView::IsOnFirstRecord](#isonfirstrecord)|Geçerli kayıt ilişkili kayıt kümesindeki ilk kayıtsa sıfırsız döndürür.|
|[CDaoRecordView::IsOnLastRecord](#isonlastrecord)|Geçerli kayıt ilişkili kayıt kümesindeki son kayıtsa sıfırsız döndürür.|
|[CDaoRecordView::OnGetRecordset](#ongetrecordset)|Bir işaretçiyi türetilen bir `CDaoRecordset`sınıfın nesnesine döndürür. ClassWizard bu işlevi sizin için geçersiz kılar ve gerekirse kayıt kümesini oluşturur.|
|[CDaoRecordView::OnMove](#onmove)|Geçerli kayıt değiştiyse, veri kaynağında güncelleştirir, ardından belirtilen kayda (sonraki, önceki, ilk veya son) taşınır.|

## <a name="remarks"></a>Açıklamalar

Görünüm, doğrudan bir nesneye `CDaoRecordset` bağlı bir form görünümüdür. Görünüm bir iletişim şablonu kaynağından oluşturulur ve `CDaoRecordset` iletişim şablonunun denetimlerinde nesnenin alanlarını görüntüler. Nesne, `CDaoRecordView` form daki denetimler ile kayıt kümesinin alanları arasındaki veri hareketini otomatikleştirmek için iletişim veri alışverişi (DDX) ve DAO kayıt alanı değişimi (DFX) kullanır. `CDaoRecordView`ayrıca, ilk, sonraki, önceki veya son kayda geçmek için varsayılan bir uygulama ve şu anda görünümde olan kaydı güncelleştirmek için bir arabirim sağlar.

> [!NOTE]
> DAO veritabanı sınıfları Açık Veritabanı Bağlantısı (ODBC) dayalı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" öneki vardır. DaO sınıfları ile ODBC veri kaynaklarına erişebilirsiniz; DAO sınıfları, Microsoft Jet veritabanı altyapısını kullandıklarından genellikle üstün özellikler sunar.

Kayıt görünümünüzü oluşturmanın en yaygın yolu Uygulama Sihirbazı'dır. Uygulama Sihirbazı, iskelet başlatıcı uygulamanızın bir parçası olarak hem kayıt görünümü sınıfını hem de ilişkili kayıt kümesi sınıfını oluşturur.

Tek bir forma ihtiyacınız varsa, Uygulama Sihirbazı yaklaşımı daha kolaydır. ClassWizard, geliştirme işleminin ilerleyen saatlerinde bir kayıt görünümü kullanmaya karar vermenizi sağlar. Uygulama Sihirbazı ile kayıt görünümü sınıfını oluşturmazsanız, daha sonra ClassWizard ile oluşturabilirsiniz. Bir kayıt görünümü ve bir kayıt kümesi oluşturmak için ClassWizard kullanarak ayrı ayrı ve sonra bunları bağlamak en esnek bir yaklaşımdır çünkü kayıt kümesi sınıf ve onun adlandırma daha fazla kontrol sağlar. H/. CPP dosyaları. Bu yaklaşım, aynı kayıt kümesi sınıfında birden çok kayıt görüntülemeniz iniz de sağlar.

Son kullanıcıların kayıt görünümünde kayıttan kayda geçmelerini kolaylaştırmak için, Uygulama Sihirbazı ilk, sonraki, önceki veya son kayda geçmek için menü (ve isteğe bağlı araç çubuğu) kaynakları oluşturur. ClassWizard ile bir kayıt görünümü sınıfı oluşturursanız, menü ve bitmap düzenleyicileri ile bu kaynakları kendiniz oluşturmanız gerekir.

Kayıttan kayda geçmek için varsayılan uygulama `IsOnFirstRecord` hakkında `IsOnLastRecord` bilgi [Using a Record View](../../data/using-a-record-view-mfc-data-access.md)için, bkz ve hem de `CRecordView` `CDaoRecordView`.

`CDaoRecordView`kayıt görünümünün kullanıcı arabirimini güncelleştirebilmeleri için kullanıcının kayıt kümesindeki konumunu izler. Kullanıcı kayıt kümesinin her iki ucuna da taşındığında, kayıt görünümü aynı yönde daha fazla hareket etmek için kullanıcı arabirimi nesnelerini (menü öğeleri veya araç çubuğu düğmeleri gibi) devre dışı kılabilir.

Kayıt görünümü ve kayıt kümesi sınıflarınızı bildirme ve kullanma hakkında daha fazla bilgi için [Kayıt Görünümleri](../../data/record-views-mfc-data-access.md)makalesinde "Kayıt Görünümü Tasarlama ve Oluşturma" bölümüne bakın. Kayıt görünümleri nasıl çalıştığı ve bunların nasıl kullanılacağı hakkında daha fazla bilgi için [Kayıt Görünümü Kullanma](../../data/using-a-record-view-mfc-data-access.md)makalesine bakın. Yukarıda belirtilen tüm makaleler hem `CRecordView` `CDaoRecordView`de geçerlidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cview](../../mfc/reference/cview-class.md)

[Cscrollview](../../mfc/reference/cscrollview-class.md)

[Cformview](../../mfc/reference/cformview-class.md)

`CDaoRecordView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="cdaorecordviewcdaorecordview"></a><a name="cdaorecordview"></a>CDaoRecordView::CDaoRecordView

Türetilen bir tür bir nesne `CDaoRecordView`oluşturduğunuzda, görünüm nesnesini başlatmaya ve görünümün dayandığı iletişim kaynağını tanımlamak için yapı oluşturucunun her iki formunu da arayın.

```
explicit CDaoRecordView(LPCTSTR lpszTemplateName);
explicit CDaoRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
İletişim şablonu kaynağının adı olan null-sonlandırılan bir dize içerir.

*nIDTemplate*<br/>
İletişim şablonu kaynağının kimlik numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Kaynağı ada göre tanımlayabilir (bir dizeyi oluşturucuya bağımsız değişken olarak geçirin) veya kimliğiyle (bağımsız değişken olarak imzasız bir tamsayı geçirin). Kaynak kimliği kullanılması önerilir.

> [!NOTE]
> Türemiş sınıfınız kendi oluşturucusu sağlamalıdır. Türemiş sınıfınızın oluşturucusunda, `CDaoRecordView::CDaoRecordView` kaynak adı veya kimliği olan oluşturucuyu bağımsız değişken olarak arayın.

`CDaoRecordView::OnInitialUpdate`aramalar `CWnd::UpdateData`, `CWnd::DoDataExchange`hangi çağırır . Bu ilk `DoDataExchange` çağrı, `CDaoRecordView` denetimleri (dolaylı `CDaoRecordset` olarak) ClassWizard tarafından oluşturulan alan veri üyelerine bağlar. Bu veri üyeleri, taban sınıf `CFormView::OnInitialUpdate` üye işlevini aramadan sonra kullanılamaz.

> [!NOTE]
> ClassWizard kullanırsanız, sihirbaz sınıf bildiriminde `CDaoRecordView::IDD` bir **enum** değeri tanımlar ve oluşturucu için üye başlatma listesinde kullanır.

[!code-cpp[NVC_MFCDatabase#35](../../mfc/codesnippet/cpp/cdaorecordview-class_1.cpp)]

## <a name="cdaorecordviewisonfirstrecord"></a><a name="isonfirstrecord"></a>CDaoRecordView::IsOnFirstRecord

Geçerli kaydın bu kayıt görünümüyle ilişkili kayıt kümesi nesnesindeki ilk kayıt olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsOnFirstRecord();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıt kayıt kümesindeki ilk kayıtsa sıfır sız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ClassWizard tarafından yazılmış varsayılan komut güncelleştirme işleyicileri kendi uygulamalarını yazmak için yararlıdır.

Kullanıcı ilk kayda geçerse, çerçeve ilk veya önceki kayda geçmek için sahip olduğunuz kullanıcı arabirimi nesnelerini (örneğin, menü öğeleri veya araç çubuğu düğmeleri) devre dışı kılabilir.

## <a name="cdaorecordviewisonlastrecord"></a><a name="isonlastrecord"></a>CDaoRecordView::IsOnLastRecord

Geçerli kaydın bu kayıt görünümüyle ilişkili kayıt kümesi nesnesindeki son kayıt olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsOnLastRecord();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıt kayıt kümesindeki son kayıtsa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ClassWizard'ın kayıttan kayda geçmek için kullanıcı arabirimini desteklemek için yazdığı varsayılan komut güncelleştirme işleyicilerinin kendi uygulamalarını yazmak için yararlıdır.

> [!CAUTION]
> Bu işlevin sonucu, kullanıcı geçmiş taşıyınceye kadar görünümün kayıt kümesinin sonunu algılayamaması dışında güvenilirdir. Kayıt görünümü, bir sonraki veya son kayda geçmek için herhangi bir kullanıcı arabirimi nesnelerini devre dışı bırakmanız gerektiğini söyleyebilmek için kullanıcının son kaydın ötesine geçmesi gerekebilir. Kullanıcı son kaydı geçip son kayda (veya ondan önce) geri dönerse, kayıt görünümü kullanıcının kayıt kümesindeki konumunu izleyebilir ve kullanıcı arabirimi nesnelerini doğru şekilde devre dışı bırakabilirsiniz.

## <a name="cdaorecordviewongetrecordset"></a><a name="ongetrecordset"></a>CDaoRecordView::OnGetRecordset

Bir işaretçiyi `CDaoRecordset`kayıt görünümüyle ilişkili türetilmiş nesneye döndürür.

```
virtual CDaoRecordset* OnGetRecordset() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla `CDaoRecordset`oluşturulduysa, türetilmiş bir nesneye işaretçi; aksi takdirde bir NULL işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturmak veya elde etmek ve bir işaretçi döndürmek için bu üye işlevi geçersiz kılmanız gerekir. ClassWizard ile kayıt görünümü sınıfını bildirirseniz, sihirbaz sizin için varsayılan geçersiz kılma yazar. ClassWizard'ın varsayılan uygulaması, varsa kayıt görünümünde depolanan kayıt kümesi işaretçisini döndürür. Değilse, ClassWizard ile belirttiğiniz türün bir kayıt kümesi nesnesi inşa eder ve tabloyu açmak veya sorguyu çalıştırmak için `Open` üye işlevini çağırır ve sonra nesneye bir işaretçi döndürür.

Daha fazla bilgi ve örnekler için Kayıt Görünümleri makalesine [bakın: Kayıt Görünümü kullanma.](../../data/using-a-record-view-mfc-data-access.md)

## <a name="cdaorecordviewonmove"></a><a name="onmove"></a>CDaoRecordView::OnMove

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

Varsayılan uygulama, kayıt görünümüyle ilişkili `CDaoRecordset` nesnenin uygun Taşı üye işlevini çağırır.

Varsayılan olarak, kullanıcı kayıt görünümünde değiştirdiyse, `OnMove` veri kaynağındaki geçerli kaydı güncelleştirir.

Uygulama Sihirbazı, İlk Kayıt, Son Kayıt, Sonraki Kayıt ve Önceki Kayıt menü öğelerini içeren bir menü kaynağı oluşturur. İlk Araç Çubuğu seçeneğini seçerseniz, Uygulama Sihirbazı da bu komutlara karşılık gelen düğmeleri içeren bir araç çubuğu oluşturur.

Kayıt kümesindeki son kaydı geçerseniz, kayıt görünümü son kaydı görüntülemeye devam edin. İlk kaydın ötesine geçerseniz, kayıt görünümü ilk kaydı görüntülemeye devam edin.

> [!CAUTION]
> Kayıt `OnMove` kümesinde kayıt yoksa arama bir özel durum oluşturur. Kayıt kümesinde herhangi bir kayıt `OnUpdateRecordFirst` `OnUpdateRecordLast`olup `OnUpdateRecordNext`olmadığını `OnUpdateRecordPrev` belirlemek için ilgili taşıma işleminden önce uygun kullanıcı arabirimi güncelleştirme işleyicisi işlevini (, , , veya — ) çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[CFormView Sınıfı](../../mfc/reference/cformview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoWorkspace Sınıf](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CFormView Sınıfı](../../mfc/reference/cformview-class.md)
