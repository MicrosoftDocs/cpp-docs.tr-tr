---
title: COleDBRecordView Sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
helpviewer_keywords:
- COleDBRecordView [MFC], COleDBRecordView
- COleDBRecordView [MFC], OnGetRowset
- COleDBRecordView [MFC], OnMove
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
ms.openlocfilehash: de9c602cb747ee3d4449df479530e55ce907cb8a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366100"
---
# <a name="coledbrecordview-class"></a>COleDBRecordView Sınıfı

Denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

## <a name="syntax"></a>Sözdizimi

```
class COleDBRecordView : public CFormView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|Bir `COleDBRecordView` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Standart bir HRESULT değeri verir.|
|[COleDBRecordView::OnMove](#onmove)|Veri kaynağındaki geçerli kaydı (kirliyse) güncelleştirir ve ardından belirtilen kayda (sonraki, önceki, ilk veya son) taşınır.|

## <a name="remarks"></a>Açıklamalar

Görünüm, doğrudan bir nesneye `CRowset` bağlı bir form görünümüdür. Görünüm bir iletişim şablonu kaynağından oluşturulur ve `CRowset` iletişim şablonunun denetimlerinde nesnenin alanlarını görüntüler. Nesne, `COleDBRecordView` formdaki denetimler ile satır kümesinin alanları arasındaki `CRowset`veri hareketini otomatikleştirmek için yerleşik iletişim veri alışverişi (DDX) ve yerleşik gezinti işlevini kullanır. `COleDBRecordView`ayrıca, ilk, sonraki, önceki veya son kayda geçmek için varsayılan bir uygulama ve şu anda görünümde olan kaydı güncelleştirmek için bir arabirim sağlar.

DDX işlevlerini `COleDbRecordView` doğrudan veritabanı kayıt kümesinden veri almak ve iletişim denetiminde görüntülemek için kullanabilirsiniz. `DDX_*` `DDX_Text`Yöntemleri (gibi), `DDX_Field*` işlevleri (gibi) `DDX_FieldText`ile `COleDbRecordView`kullanmalısınız. `DDX_FieldText`türü `CRecordset*` (for) `CRecordView`veya `CDaoRecordset*` `CDaoRecordView`(for) ek bir argüman `COleDbRecordView` `DDX_FieldText` aldığından, birlikte çalışmaz.

> [!NOTE]
> OLE DB Tüketici Şablonu sınıfları yerine Veri Erişim Nesneleri (DAO) sınıflarıyla çalışıyorsanız, bunun yerine [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) sınıfını kullanın. Daha fazla bilgi için genel bakış makalesine [bakın: Veritabanı Programlama.](../../data/data-access-programming-mfc-atl.md)

`COleDBRecordView`kayıt görünümünün kullanıcı arabirimini güncelleştirebilmeleri için kullanıcının rowset'teki konumunu izler. Kullanıcı rowset'in her iki ucuna da taşındığında, kayıt görünümü aynı yönde daha fazla hareket etmek için kullanıcı arabirimi nesnelerini (menü öğeleri veya araç çubuğu düğmeleri gibi) devre dışı kılabilir.

Rowset sınıfları hakkında daha fazla bilgi [için, OLE DB Tüketici Şablonlarını Kullanma makalesine](../../data/oledb/ole-db-consumer-templates-cpp.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cview](../../mfc/reference/cview-class.md)

[Cscrollview](../../mfc/reference/cscrollview-class.md)

[Cformview](../../mfc/reference/cformview-class.md)

`COleDBRecordView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxoledb.h

## <a name="coledbrecordviewcoledbrecordview"></a><a name="coledbrecordview"></a>COleDBRecordView::COleDBRecordView

Bir `COleDBRecordView` nesne inşa eder.

```
COleDBRecordView(LPCTSTR lpszTemplateName);
COleDBRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
İletişim şablonu kaynağının adı olan null-sonlandırılan bir dize içerir.

*nIDTemplate*<br/>
İletişim şablonu kaynağının kimlik numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Türetilen bir tür bir nesne `COleDBRecordView`oluşturduğunuzda, görünüm nesnesi oluşturmak ve görünümün dayandığı iletişim kaynağını tanımlamak için oluşturuculardan birini çağırın. Kaynağı ada göre (bir dizeyi bağımsız değişken olarak oluşturucuya geçirin) veya kimliğiyle (bağımsız değişken olarak imzasız bir tamsayı geçirin) tanımlayabilirsiniz.

> [!NOTE]
> Türemiş sınıfınız kendi oluşturucusu *sağlamalıdır.* Oluşturucuolarak, `COleDBRecordView::COleDBRecordView`kaynak adı veya kimlik bir bağımsız değişken olarak, oluşturucu çağırın.

## <a name="coledbrecordviewongetrowset"></a><a name="ongetrowset"></a>COleDBRecordView::OnGetRowset

**CRowset<>** nesnesi için bir tanıtıcı döndürür.

```
virtual CRowset<>* OnGetRowset() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bir satır kümesi nesnesi oluşturmak veya elde etmek ve ona bir tanıtıcı döndürmek için bu üye işlevi geçersiz kılmanız gerekir. ClassWizard ile kayıt görünümü sınıfını bildirirseniz, sihirbaz sizin için varsayılan geçersiz kılma yazar. ClassWizard'ın varsayılan uygulaması varsa kayıt görünümünde depolanan satır kümesi tanıtıcısını döndürür. Değilse, ClassWizard ile belirttiğiniz türden bir satır kümesi nesnesi oluşturuyor ve tabloyu açmak veya sorguyu çalıştırmak için `Open` üye işlevini çağırır ve sonra nesneye bir tanıtıcı döndürür.

> [!NOTE]
> MFC 7.0'dan `OnGetRowset` önce, `CRowset`bir işaretçi . Çağıran kodunuz `OnGetRowset`varsa, iade türünü<>**crowset **sınıfıyla değiştirmeniz gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]

Daha fazla bilgi ve örnekler için Kayıt Görünümleri makalesine [bakın: Kayıt Görünümü kullanma.](../../data/using-a-record-view-mfc-data-access.md)

## <a name="coledbrecordviewonmove"></a><a name="onmove"></a>COleDBRecordView::OnMove

Satır kümesinde farklı bir kayda taşınır ve alanlarını kayıt görünümü denetimlerinde görüntüler.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>Parametreler

*nIDMoveCommand*<br/>
Aşağıdaki standart komut kimliği değerlerinden biri:

- ID_RECORD_FIRST — Kayıt setindeki ilk kayda geçin.

- ID_RECORD_LAST — Kayıt setindeki son kayda geçin.

- ID_RECORD_NEXT — Kayıt setindeki bir sonraki kayda geçin.

- ID_RECORD_PREV — Kayıt setindeönceki kayda geçin.

### <a name="return-value"></a>Dönüş Değeri

Hareket başarılı olduysa sıfırolmayan; aksi takdirde 0 taşıma isteği reddedildi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, kayıt `Move` görünümüyle `CRowset` ilişkili nesnenin uygun üye işlevini çağırır.

Varsayılan olarak, kullanıcı kayıt görünümünde değiştirdiyse, `OnMove` veri kaynağındaki geçerli kaydı güncelleştirir.

Uygulama Sihirbazı, İlk Kayıt, Son Kayıt, Sonraki Kayıt ve Önceki Kayıt menü öğelerini içeren bir menü kaynağı oluşturur. Takılabilir Araç Çubuğu seçeneğini seçerseniz, Uygulama Sihirbazı da bu komutlara karşılık gelen düğmeleri içeren bir araç çubuğu oluşturur.

Kayıt kümesindeki son kaydı geçerseniz, kayıt görünümü son kaydı görüntülemeye devam edin. İlk kaydın ötesine geçerseniz, kayıt görünümü ilk kaydı görüntülemeye devam edin.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
