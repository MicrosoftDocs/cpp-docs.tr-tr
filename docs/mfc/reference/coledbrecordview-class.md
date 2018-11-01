---
title: COleDBRecordView sınıfı
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
ms.openlocfilehash: b862ce5176a1fd4fa4ac48cabf7830cd8ebf3d92
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599608"
---
# <a name="coledbrecordview-class"></a>COleDBRecordView sınıfı

Denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

## <a name="syntax"></a>Sözdizimi

```
class COleDBRecordView : public CFormView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|Oluşturur bir `COleDBRecordView` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Standart bir HRESULT değerini döndürür.|
|[COleDBRecordView::OnMove](#onmove)|Geçerli kayıt (olumsuz) veri kaynağında güncelleştirir ve sonra belirtilen kayıda taşır (sonraki, önceki, ilk veya son).|

## <a name="remarks"></a>Açıklamalar

Doğrudan bağlı bir form görünümü görünümdür bir `CRowset` nesne. Görünüm iletişim şablon kaynağı oluşturulur ve alanlarını görüntüler `CRowset` iletişim şablonun denetimlerinde nesne. `COleDBRecordView` Nesne iletişim kutusu veri değişimi (DDX) kullanır ve gezinti işlevselliğini yerleşik `CRowset`, form üzerinde denetimleri ve alanları kümesi arasında veri taşıma işlemlerini otomatik hale getirmek için. `COleDBRecordView` Ayrıca taşımak için varsayılan bir uygulama sağlar, ilk İleri, önceki ya da son kaydını ve kayıtta şu anda Görünümü güncelleştirmek için bir arabirim.

DDX işlevleri ile kullanabileceğiniz `COleDbRecordView` doğrudan veritabanı kayıt kümesinden veri almak ve bir iletişim kutusu denetiminde görüntüleme. Kullanmanız gereken `DDX_*` yöntemleri (gibi `DDX_Text`) değil `DDX_Field*` işlevleri (gibi `DDX_FieldText`) ile `COleDbRecordView`. `DDX_FieldText` ile çalışmaz `COleDbRecordView` çünkü `DDX_FieldText` ek bağımsız değişken türü `CRecordset*` (için `CRecordView`) veya `CDaoRecordset*` (için `CDaoRecordView`).

> [!NOTE]
>  OLE DB tüketici şablonu sınıfları yerine veri erişim nesneleri (DAO) sınıfları ile çalışıyorsanız, sınıf kullanmak [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) yerine. Daha fazla bilgi için bkz [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

`COleDBRecordView` kullanıcının konumunu satır kümesindeki kayıt görünümü kullanıcı arabirimi güncelleştirebilmeniz izler. Kullanıcı her iki satır sonuna hareket ettirdiğinde kayıt görünümü kullanıcı arabirimi nesneleri devre dışı bırakır; menü öğeleri ya da araç çubuğu düğmeleri gibi — taşımak için aynı yönde başka.

Satır kümesi sınıfları hakkında daha fazla bilgi için bkz. [OLE DB Tüketici Şablonları kullanarak](../../data/oledb/ole-db-consumer-templates-cpp.md) makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`COleDBRecordView`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxoledb.h

##  <a name="coledbrecordview"></a>  COleDBRecordView::COleDBRecordView

Oluşturur bir `COleDBRecordView` nesne.

```
COleDBRecordView(LPCTSTR lpszTemplateName);
COleDBRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
Bir iletişim şablonunu kaynak adı null ile sonlandırılmış bir dize içerir.

*nIDTemplate*<br/>
Bir iletişim şablonunu kaynak kimliği numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Bir türde bir nesne oluşturduğunuzda, türetilen `COleDBRecordView`, Görünüm nesnesi oluşturup, görünüm temel iletişim kaynağı tanımlamak için oluşturucular birini çağırın. Kaynak adı (pass bağımsız değişkeni olarak bir dize oluşturucuya) veya (pass bağımsız değişkeni olarak bir işaretsiz tamsayı) Kimliğini tanımlayabilirsiniz.

> [!NOTE]
>  Türetilmiş sınıfınızın *gerekir* kendi Oluşturucu sağlayın. Oluşturucusunun içinde bir oluşturucu çağırmak `COleDBRecordView::COleDBRecordView`, kaynak adı veya kimliği bağımsız değişken olarak.

##  <a name="ongetrowset"></a>  COleDBRecordView::OnGetRowset

İçin bir tanıtıcı döndürür **CRowset <>** kayıt görünümü ile ilişkili nesne.

```
virtual CRowset<>* OnGetRowset() = 0;

```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Oluşturmak veya bir satır kümesi nesnesi edinip bir tanıtıcı döndürmek için bu üye işlevini geçersiz kılmanız gerekir. Kayıt görünümü sınıfınıza ClassWizard ile bildirirseniz, sihirbaz sizin için varsayılan geçersiz kılma yazar. ClassWizard'ın varsayılan uygulaması varsa, kayıt görünümü'nde depolanan satır kümesi tanıtıcısını döndürür. Türünde bir satır kümesi nesnesi oluşturur, varsa çağrıları ve ClassWizard ile belirtilen kendi `Open` üye işlevi tabloyu veya sorguyu çalıştırmak için ve ardından nesne için bir tanıtıcı döndürür.

> [!NOTE]
>  Önceki MFC 7.0 `OnGetRowset` işaretçisi döndürülen `CRowset`. Çağıran kod varsa `OnGetRowset`, dönüş türü şablonlaştırılmış sınıfa değiştirmeniz gerekir **CRowset <>**.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]

Daha fazla bilgi ve örnekler için bkz [kayıt görünümleri: kayıt görünümünü kullanma](../../data/using-a-record-view-mfc-data-access.md).

##  <a name="onmove"></a>  COleDBRecordView::OnMove

Satır kümesi ve görüntü farklı bir kaydı taşır denetimlerde kaydın alanlarını görüntüleyin.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>Parametreler

*nIDMoveCommand*<br/>
Aşağıdaki standart komut kimliği değerlerden biri:

- ID_RECORD_FIRST — Kayıt kümesi bulunan ilk kayda git.

- ID_RECORD_LAST — kaydı kayıt kümesinde son taşır.

- ID_RECORD_NEXT — sonraki kayda kümesinde taşıyın.

- ID_RECORD_PREV — önceki kayıt kümesinde taşıyın.

### <a name="return-value"></a>Dönüş Değeri

Taşıma başarılı olursa sıfır dışı; taşıma isteği reddedildi, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama uygun çağırır `Move` üye işlevinin `CRowset` kayıt görünümü ile ilişkili nesne.

Varsayılan olarak, `OnMove` geçerli kayıt veri kaynağı için kullanıcı kayıt görünümünde değişmişse güncelleştirir.

Uygulama Sihirbazı, bir menü kaynağı ile ilk kaydı son kayda sonraki kayıt ve önceki kayıt menü öğesi oluşturur. Yerleştirilebilir araç seçeneği seçerseniz, Uygulama Sihirbazı bir araç çubuğu düğmeleri için şu komutları karşılık gelen de oluşturur.

Kümesinde son kaydını geçmiş taşırsanız, kayıt görünümü en son kaydını görüntülemek devam eder. Kayıt görünümü ilk kaydı geriye taşırsanız, ilk kaydı görüntülemek devam eder.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

