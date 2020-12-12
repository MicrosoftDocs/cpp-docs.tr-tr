---
description: 'Daha fazla bilgi edinin: COleDBRecordView sınıfı'
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
ms.openlocfilehash: bce03a482aff558ed6d22c7720ff74f304a9214f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227318"
---
# <a name="coledbrecordview-class"></a>COleDBRecordView sınıfı

Denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

## <a name="syntax"></a>Syntax

```
class COleDBRecordView : public CFormView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleDBRecordView:: COleDBRecordView](#coledbrecordview)|Bir `COleDBRecordView` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDBRecordView:: OnGetRowset](#ongetrowset)|Standart bir HRESULT değeri döndürür.|
|[COleDBRecordView:: OnMove](#onmove)|Veri kaynağında geçerli kaydı (kirli ise) güncelleştirir ve sonra belirtilen kayda (ileri, önceki, ilk veya son) gider.|

## <a name="remarks"></a>Açıklamalar

Görünüm bir nesneye doğrudan bağlı olan bir form görünümüdür `CRowset` . Görünüm bir iletişim kutusu şablonu kaynağından oluşturulur ve `CRowset` iletişim kutusu şablonunun denetimlerindeki nesne alanlarını görüntüler. `COleDBRecordView`Nesne, `CRowset` form üzerindeki denetimler ve satır kümesinin alanları arasında veri hareketini otomatik hale getirmek için iletişim kutusu veri DEĞIŞIMI (DDX) ve yerleşik gezinme işlevlerini kullanır. `COleDBRecordView` Ayrıca, ilk, sonraki, önceki veya son kayda geçiş için varsayılan bir uygulama ve şu anda görünümdeki kayıtları güncelleştirmek için bir arabirim sağlar.

`COleDbRecordView`Doğrudan veritabanı kayıt kümesinden veri almak ve bir iletişim kutusu denetiminde göstermek için, Ile DDX işlevlerini kullanabilirsiniz. `DDX_*` `DDX_Text` İle işlevleri değil (gibi) yöntemleri (gibi) kullanmanız gerekir `DDX_Field*` `DDX_FieldText` `COleDbRecordView` . `DDX_FieldText` , `COleDbRecordView` `DDX_FieldText` `CRecordset*` (için `CRecordView` ) veya `CDaoRecordset*` (için) türünde ek bir bağımsız değişken aldığı için ile birlikte çalışmaz `CDaoRecordView` .

> [!NOTE]
> OLE DB Tüketici şablonu sınıfları yerine veri erişim nesneleri (DAO) sınıflarıyla çalışıyorsanız, bunun yerine Class [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) kullanın. Daha fazla bilgi için bkz. [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

`COleDBRecordView` kayıt görünümünün Kullanıcı arabirimini güncelleştirebilmesi için Kullanıcı kümesindeki konumunu izler. Kullanıcı satır kümesinin sonuna kadar hareket ettirirse, kayıt görünümü menü öğeleri veya araç çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerini aynı yönde taşımak için devre dışı bırakır.

Satır kümesi sınıfları hakkında daha fazla bilgi için [OLE DB tüketici şablonları kullanma](../../data/oledb/ole-db-consumer-templates-cpp.md) makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`COleDBRecordView`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxoledb. h

## <a name="coledbrecordviewcoledbrecordview"></a><a name="coledbrecordview"></a> COleDBRecordView:: COleDBRecordView

Bir `COleDBRecordView` nesnesi oluşturur.

```
COleDBRecordView(LPCTSTR lpszTemplateName);
COleDBRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
Bir iletişim şablonu kaynağının adı olan null ile sonlandırılmış bir dize içerir.

*Nıdtemplate*<br/>
İletişim kutusu-şablon kaynağının KIMLIK numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Öğesinden türetilmiş bir türden bir nesne oluşturduğunuzda `COleDBRecordView` , görünüm nesnesini oluşturmak ve görünümün temel aldığı iletişim kaynağını belirlemek için oluşturuculardan birini çağırın. Kaynağı ada göre (oluşturucuya bağımsız değişken olarak bir dize geçirerek) veya KIMLIğINE göre (bağımsız değişken olarak işaretsiz bir tamsayı geçirin) belirleyebilirsiniz.

> [!NOTE]
> Türetilmiş sınıfınızın kendi oluşturucusunu sağlaması *gerekir* . Oluşturucuda, `COleDBRecordView::COleDBRecordView` kaynak adı veya kimliğiyle bir bağımsız değişken olarak oluşturucuyu çağırın.

## <a name="coledbrecordviewongetrowset"></a><a name="ongetrowset"></a> COleDBRecordView:: OnGetRowset

Kayıt görünümüyle ilişkili **CRowset<>** nesnesi için bir tanıtıcı döndürür.

```
virtual CRowset<>* OnGetRowset() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bir satır kümesi nesnesi oluşturmak veya almak ve buna bir tanıtıcı döndürmek için bu üye işlevi geçersiz kılmalısınız. Kayıt görünümü sınıfınızı ClassWizard ile bildirirseniz, sihirbaz sizin için varsayılan bir geçersiz kılma yazar. ClassWizard 'ın varsayılan uygulama, varsa kayıt görünümünde depolanan satır kümesi tanıtıcısını döndürür. Aksi takdirde, ClassWizard ile belirttiğiniz türden bir Rowset nesnesi oluşturur ve `Open` tabloyu açmak veya sorguyu çalıştırmak için üye işlevini çağırır ve sonra nesneye bir tanıtıcı döndürür.

> [!NOTE]
> MFC 7,0 ' den önceki `OnGetRowset` bir işaretçisi döndürdü `CRowset` . ' I çağıran bir kodunuz varsa `OnGetRowset` , dönüş türünü **şablon<>** templatılaştırılmış sınıf CRowset olarak değiştirmeniz gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]

Daha fazla bilgi ve örnek için bkz. kayıt [görünümleri: kayıt görünümü kullanma](../../data/using-a-record-view-mfc-data-access.md).

## <a name="coledbrecordviewonmove"></a><a name="onmove"></a> COleDBRecordView:: OnMove

Satır kümesinde farklı bir kayda gider ve alanlarını kayıt görünümünün denetimlerinde görüntüler.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>Parametreler

*Nıdmovecommand*<br/>
Aşağıdaki standart komut KIMLIĞI değerlerinden biri:

- ID_RECORD_FIRST — kayıt kümesindeki ilk kayda geçin.

- ID_RECORD_LAST — kayıt kümesindeki son kayda taşıyın.

- ID_RECORD_NEXT — kayıt kümesindeki bir sonraki kayda geçin.

- ID_RECORD_PREV — kayıt kümesindeki bir önceki kayda geçin.

### <a name="return-value"></a>Dönüş Değeri

Taşıma başarılı olursa sıfır dışı; tersi durumda, taşıma isteği reddedildiyse 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, `Move` `CRowset` kayıt görünümüyle ilişkili nesnenin uygun üye işlevini çağırır.

Varsayılan olarak, `OnMove` Kullanıcı kayıt görünümünde değiştiyse, veri kaynağındaki geçerli kaydı güncelleştirir.

Uygulama Sihirbazı, Ilk kayıt, son kayıt, sonraki kayıt ve önceki kayıt menü öğelerini içeren bir menü kaynağı oluşturur. Dockable araç çubuğu seçeneğini belirlerseniz, uygulama Sihirbazı bu komutlara karşılık gelen düğmelere sahip bir araç çubuğu da oluşturur.

Kayıt kümesindeki son kaydı geçmiş yaparsanız, kayıt görünümü son kaydı görüntülemeye devam eder. İlk kaydı daha sonra geri taşırsanız, kayıt görünümü ilk kaydı görüntülemeye devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
