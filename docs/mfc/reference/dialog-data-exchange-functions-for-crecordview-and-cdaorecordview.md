---
title: CRecordView ve CDaoRecordView için İletişim Kutusu Veri Değişimi İşlevleri
ms.date: 09/17/2019
f1_keywords:
- AFXDAO/DDX_FieldCBIndex
- AFXDAO/DDX_FieldCBString
- AFXDAO/DDX_FieldCBStringExact
- AFXDAO/DDX_FieldCheck
- AFXDAO/DDX_FieldLBIndex
- AFXDAO/DDX_FieldLBString
- AFXDAO/DDX_FieldLBStringExact
- AFXDAO/DDX_FieldRadio
- AFXDAO/DDX_FieldScroll
- AFXDAO/DDX_FieldText
helpviewer_keywords:
- DDX_Field functions [MFC]
- ODBC [MFC], dialog data exchange (DDX) support
- DDX (dialog data exchange) [MFC], database support
- DDX (dialog data exchange) [MFC], functions
- databases [MFC], dialog data exchange (DDX) support
- DAO [MFC], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
ms.openlocfilehash: 48ffe6f124b91ee8ad60452f26d895bc2698779b
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447310"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>CRecordView ve CDaoRecordView için İletişim Kutusu Veri Değişimi İşlevleri

Bu konuda, bir [CRecordset](../../mfc/reference/crecordset-class.md) ve [CRecordView](../../mfc/reference/crecordview-class.md) formu veya bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) formu arasında veri alışverişi yapmak için kullanılan DDX_Field işlevleri listelenmektedir. DAO, Access veritabanları ile birlikte kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

> [!NOTE]
>  DDX_Field işlevler, verileri bir form içinde denetimlerle değiş tokuş ettikleri için DDX işlevleri gibidir. Ancak, DDX 'nin aksine, kayıt görünümündeki alanları yerine görünümün ilişkili kayıt kümesi nesnesinin alanlarıyla verileri değiş tokuş ederler. Daha fazla bilgi için bkz. sınıflar `CRecordView` ve `CDaoRecordView`.

### <a name="ddx_field-functions"></a>DDX_Field Işlevleri

|||
|-|-|
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|Bir kayıt kümesi alanı veri üyesi ve geçerli seçimin dizini ile bir [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)içindeki Birleşik giriş kutusunda bulunan tamsayı verilerini aktarır.|
|[DDX_FieldCBString](#ddx_fieldcbstring)|Bir kayıt kümesi alanı veri üyesi ve bir `CRecordView` veya `CDaoRecordView`Birleşik giriş kutusunun düzenleme denetimi arasında veri `CString` aktarır. Kayıt kümesinden denetime veri taşırken, bu işlev belirtilen dizedeki karakterlerle başlayan açılan kutudaki öğeyi seçer.|
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Bir kayıt kümesi alanı veri üyesi ve bir `CRecordView` veya `CDaoRecordView`Birleşik giriş kutusunun düzenleme denetimi arasında veri `CString` aktarır. Kayıt kümesinden denetime veri taşırken, bu işlev, belirtilen dizeyle tam olarak eşleşen Birleşik giriş kutusunda bulunan öğeyi seçer.|
|[DDX_FieldCheck](#ddx_fieldcheck)|Bir kayıt kümesi alanı veri üyesi ve bir `CRecordView` veya `CDaoRecordView`onay kutusu arasında Boole verileri aktarır.|
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|Bir kayıt kümesi alanı veri üyesi ve bir `CRecordView` veya `CDaoRecordView`bir liste kutusunda geçerli seçimin dizini arasında tam sayı verilerini aktarır.|
|[DDX_FieldLBString](#ddx_fieldlbstring)|Bir liste kutusu denetimi ve bir kayıt kümesinin alan veri üyeleri arasında [CString](../../atl-mfc-shared/reference/cstringt-class.md) verilerinin aktarımını yönetir. Kayıt kümesinden denetime veri taşırken, bu işlev belirtilen dizedeki karakterlerle başlayan liste kutusunda öğeyi seçer.|
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|Bir liste kutusu denetimi ve bir kayıt kümesinin alan veri üyeleri arasında `CString` verilerinin aktarımını yönetir. Kayıt kümesinden denetime veri taşırken, bu işlev belirtilen dizeyle tam olarak eşleşen ilk öğeyi seçer.|
|[DDX_FieldRadio](#ddx_fieldradio)|Bir kayıt kümesi alanı veri üyesi ve bir `CRecordView` veya `CDaoRecordView`radyo düğmeleri grubu arasında tamsayı verilerini aktarır.|
|[DDX_FieldScroll](#ddx_fieldscroll)|Bir `CRecordView` veya `CDaoRecordView`kaydırma çubuğu denetiminin kaydırma konumunu ayarlar veya alır. [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) işlevinizden çağrı.|
|[DDX_FieldSlider](#ddx_fieldslider)|Bir kayıt görünümündeki kaydırıcı denetiminin Thumb konumunu ve bir kayıt kümesinin `int` alan veri üyesini eşitler. |
|[DDX_FieldText](#ddx_fieldtext)|Aşırı yüklenmiş sürümler `int`, **UINT**, **Long**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **Double**, **Short**, [copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md)ve [cokatcurrency](../../mfc/reference/colecurrency-class.md) verilerinin bir kayıt kümesi alanı veri üyesi ve bir `CRecordView` ya da `CDaoRecordView`bir düzenleme kutusu arasında aktarılması için kullanılabilir.|

##  <a name="ddx_fieldcbindex"></a>DDX_FieldCBIndex

`DDX_FieldCBIndex` işlevi bir kayıt görünümündeki Birleşik giriş kutusu denetiminin liste kutusu denetimindeki seçili öğenin dizinini ve kayıt görünümüyle ilişkili bir kayıt kümesinin `int` alan veri üyesini eşitler.

```
void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesindeki bir denetimin kimliği.

*indeks*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnesindeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinden denetime veri taşırken, bu işlev, *dizinde*belirtilen değere göre denetimdeki seçimi ayarlar. Kayıt kümesinden denetime yapılan bir aktarımda, kayıt kümesi alanı null ise, MFC dizin değerini 0 olarak ayarlar. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa veya hiçbir öğe seçilmezse, kayıt kümesi alanı 0 olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . Örnek `DDX_FieldCBIndex`benzerdir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

##  <a name="ddx_fieldcbstring"></a>DDX_FieldCBString

`DDX_FieldCBString` işlevi, bir kayıt görünümündeki Birleşik giriş kutusu denetiminin düzenleme denetimi ve kayıt görünümüyle ilişkili bir kayıt kümesinin `CString` alanı veri üyesi arasında [CString](../../atl-mfc-shared/reference/cstringt-class.md) verilerinin aktarımını yönetir.

```
void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesindeki bir denetimin kimliği.

*value*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnesindeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinden denetime veri taşırken, bu işlev Birleşik giriş kutusundaki geçerli seçimi, *değer*'de belirtilen dizedeki karakterlerle başlayan ilk satıra ayarlar. Kayıt kümesinden denetime olan bir aktarım üzerinde, kayıt kümesi alanı null ise, seçim açılan kutudan kaldırılır ve Birleşik giriş kutusunun düzenleme denetimi Empty olarak ayarlanır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, alan izin veriyorsa kayıt kümesi alanı null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . Örnek, `DDX_FieldCBString`için bir çağrı içerir.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="ddx_fieldcbstringexact"></a>DDX_FieldCBStringExact

`DDX_FieldCBStringExact` işlevi, bir kayıt görünümündeki Birleşik giriş kutusu denetiminin düzenleme denetimi ve kayıt görünümüyle ilişkili bir kayıt kümesinin `CString` alanı veri üyesi arasında [CString](../../atl-mfc-shared/reference/cstringt-class.md) verilerinin aktarımını yönetir.

```
void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesindeki bir denetimin kimliği.

*value*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnesindeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinden denetime veri taşırken, bu işlev Birleşik giriş kutusundaki geçerli seçimi, *değer*'de belirtilen dizeyle tam olarak eşleşen ilk satıra ayarlar. Kayıt kümesinden denetime olan bir aktarım üzerinde, kayıt kümesi alanı NULL ise, açılan kutudan herhangi bir seçim kaldırılır ve Birleşik giriş kutusunun düzenleme kutusu boş olarak ayarlanır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanı NULL olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . `DDX_FieldCBStringExact` çağrıları benzerdir.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

##  <a name="ddx_fieldcheck"></a>DDX_FieldCheck

`DDX_FieldCheck` işlevi bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir **int** veri üyesi içindeki bir onay kutusu denetimi arasında **int** verilerinin aktarılmasını yönetir.

```
void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Denetim özelliğiyle ilişkili onay kutusu denetiminin kaynak KIMLIĞI.

*value*<br/>
İletişim kutusu, form görünümü veya veri alışverişi yapılan denetim görünümü nesnesinin üye değişkenine başvuru.

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`DDX_FieldCheck` çağrıldığında, *değer* onay kutusu denetiminin geçerli durumu olarak ayarlanır veya aktarımın yönüne bağlı olarak denetimin durumu *değer*olarak ayarlanır.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

##  <a name="ddx_fieldlbindex"></a>DDX_FieldLBIndex

`DDX_FieldLBIndex` işlevi bir kayıt görünümündeki liste kutusu denetimindeki seçili öğenin dizinini ve kayıt görünümüyle ilişkili bir kayıt kümesinin **int** alan veri üyesini eşitler.

```
void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesindeki bir denetimin kimliği.

*indeks*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnesindeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinden denetime veri taşırken, bu işlev, *dizinde*belirtilen değere göre denetimdeki seçimi ayarlar. Kayıt kümesinden denetime yapılan bir aktarımda, kayıt kümesi alanı null ise, MFC dizin değerini 0 olarak ayarlar. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanı 0 olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) .

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

##  <a name="ddx_fieldlbstring"></a>DDX_FieldLBString

`DDX_FieldLBString`, bir kayıt görünümündeki liste kutusu denetiminin geçerli seçimini, kayıt görünümüyle ilişkili bir kayıt kümesinin [CString](../../atl-mfc-shared/reference/cstringt-class.md) alan veri üyesine kopyalar.

```
void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesindeki bir denetimin kimliği.

*value*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnesindeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Ters yönde, bu işlev liste kutusundaki geçerli seçimi *değere*göre belirtilen dizedeki karakterlerle başlayan ilk satıra ayarlar. Kayıt kümesinden denetime olan bir aktarım üzerinde, kayıt kümesi alanı null ise, herhangi bir seçim liste kutusundan kaldırılır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanı null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . `DDX_FieldLBString` çağrıları benzerdir.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

##  <a name="ddx_fieldlbstringexact"></a>DDX_FieldLBStringExact

`DDX_FieldLBStringExact` işlevi bir kayıt görünümündeki liste kutusu denetiminin geçerli seçimini, kayıt görünümüyle ilişkili bir kayıt kümesinin [CString](../../atl-mfc-shared/reference/cstringt-class.md) alan veri üyesine kopyalar.

```
void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesindeki bir denetimin kimliği.

*value*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnesindeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Ters yönde, bu işlev liste kutusundaki geçerli seçimi, *değer*'de belirtilen dizeyle tam olarak eşleşen ilk satıra ayarlar. Kayıt kümesinden denetime olan bir aktarım üzerinde, kayıt kümesi alanı null ise, herhangi bir seçim liste kutusundan kaldırılır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanı null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . `DDX_FieldLBStringExact` çağrıları benzerdir.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

##  <a name="ddx_fieldradio"></a>DDX_FieldRadio

`DDX_FieldRadio` işlevi, kayıt görünümündeki bir radyo düğmeleri grubundaki seçili radyo düğmesiyle bir kayıt görünümünün kayıt kümesinin sıfır tabanlı bir **int** üye değişkenini ilişkilendirir.

```
void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesindeki bitişik radyo düğmesi DENETIMLERININ bir gruptaki ilk kimliği (stil ws_group).

*value*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnesindeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi alanından görünüme aktarılırken, bu işlev *nth* radyo düğmesini (sıfır tabanlı) açar ve diğer düğmeleri kapatır. Ters yönde bu işlev, kayıt kümesi alanını şu anda açık olan (işaretli) radyo düğmesinin sıra numarası olarak ayarlar. Kayıt kümesinden denetime yapılan bir aktarım üzerinde, kayıt kümesi alanı null ise, hiçbir düğme seçili değildir. Denetimden kayıt kümesine bir aktarımdan, Denetim seçili değilse, alan izin veriyorsa kayıt kümesi alanı null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . `DDX_FieldRadio` çağrıları benzerdir.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

##  <a name="ddx_fieldscroll"></a>DDX_FieldScroll

`DDX_FieldScroll` işlevi bir kayıt görünümündeki bir kaydırma çubuğu denetiminin kaydırma konumunu ve kayıt görünümüyle ilişkili bir kayıt kümesinin (ya da eşlemeyi seçtiğiniz tamsayı değişkeni ile) bir **int** alan veri üyesine eşitler.

```
void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesindeki bitişik radyo düğmesi DENETIMLERININ bir gruptaki ilk kimliği (stil ws_group).

*value*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnesindeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinden denetime veri taşırken, bu işlev kaydırma çubuğu denetiminin kaydırma konumunu, *değer*'de belirtilen değere ayarlar. Kayıt kümesinden denetime olan bir aktarım üzerinde, kayıt kümesi alanı null ise, kaydırma çubuğu denetimi 0 olarak ayarlanır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanının değeri 0 ' dır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . `DDX_FieldScroll` çağrıları benzerdir.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="ddx_fieldslider"></a>DDX_FieldSlider

`DDX_FieldSlider` işlevi bir kayıt görünümündeki kaydırıcı denetiminin Thumb konumunu ve kayıt görünümüyle ilişkili bir kayıt kümesinin (veya eşlemesini seçtiğiniz herhangi bir tamsayı değişkeniyle) bir **int** alan veri üyesine eşitler.

### <a name="syntax"></a>Sözdizimi

  ```
   void AFXAPI DDX_FieldSlider(
       CDataExchange* pDX,
       int nIDC,
       int& value,
       CRecordset* pRecordset );

void AFXAPI DDX_FieldSlider(
   CDataExchange* pDX,
   int nIDC,
   int& value,
   CDaoRecordset* pRecordset );
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Kaydırıcı denetiminin kaynak KIMLIĞI.

*value*<br/>
Değiş tokuş edilecek değere bir başvuru. Bu parametre, kaydırıcı denetiminin geçerli Thumb konumunu ayarlamak için veya kullanır.

*pRecordset*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesindeki verileri kaydırıcıya taşırken, bu işlev kaydırıcının konumunu *değer*'de belirtilen değere ayarlar. Kayıt kümesinden denetime olan bir aktarım üzerinde, kayıt kümesi alanı null ise kaydırıcı denetiminin konumu 0 olarak ayarlanır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanının değeri 0 ' dır.

`DDX_FieldSlider`, yalnızca bir konum yerine bir Aralık ayarlamatabilen kaydırıcı denetimleriyle birlikte Aralık bilgilerini değiş tokuş etmez.

ODBC tabanlı sınıflarla çalışıyorsanız, işlevin ilk geçersiz kılmasını kullanın. İkinci geçersiz kılmayı DAO tabanlı sınıflarla kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../dialog-data-exchange-and-validation.md). `CRecordView` ve `CDaoRecordView` alanlarına yönelik DDX hakkında örnekler ve daha fazla bilgi için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md). Kaydırıcı denetimleri hakkında daha fazla bilgi için bkz. [CSliderCtrl kullanma](../using-csliderctrl.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . `DDX_FieldSlider` çağrıları benzerdir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

##  <a name="ddx_fieldtext"></a>DDX_FieldText

`DDX_FieldText` işlevi, bir düzenleme kutusu denetimi ve bir kayıt kümesinin alan veri üyeleri arasında **int**, **Short**, **Long**, DWORD, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **Double**, **bool**veya **byte** verilerinin aktarımını yönetir.

```
void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    UINT& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    long& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    float& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    double& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    short& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BOOL& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    long& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    float& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    double& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    COleCurrency& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesindeki bir denetimin kimliği.

*value*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnesindeki bir alan veri üyesine başvuru. Değerin veri türü, kullandığınız `DDX_FieldText` aşırı yüklenmiş sürümlerine bağlıdır.

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi. Bu işaretçi `DDX_FieldText`, null değerleri algılayıp ayarlayabilmesini sağlar.

### <a name="remarks"></a>Açıklamalar

[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesneleri için, `DDX_FieldText` [cotadatetime](../../atl-mfc-shared/reference/coledatetime-class.md)ve [copacurrency](../../mfc/reference/colecurrency-class.md) değerlerini aktarmayı da yönetir. Boş bir düzenleme kutusu denetimi null değeri gösterir. Kayıt kümesinden denetime yapılan bir aktarımda, kayıt kümesi alanı null ise, düzenleme kutusu boş olarak ayarlanır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanı null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız, [CRecordset](../../mfc/reference/crecordset-class.md) parametrelerini içeren sürümleri kullanın. DAO tabanlı sınıflarla çalışıyorsanız, [Cdaokayıt kümesi](../../mfc/reference/cdaorecordset-class.md) parametreleriyle sürümleri kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Bir [CRecordView](../../mfc/reference/crecordview-class.md) için aşağıdaki `DoDataExchange` işlevi üç veri türü için `DDX_FieldText` işlev çağrıları içerir: `IDC_COURSELIST` Birleşik giriş kutusudur; diğer iki denetim düzenleme kutularıdır. DAO programlama için *m_pSet* parametresi [CRecordset](../../mfc/reference/crecordset-class.md) veya [cdaokayıt kümesine](../../mfc/reference/cdaorecordset-class.md)yönelik bir işaretçidir.

[!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)
