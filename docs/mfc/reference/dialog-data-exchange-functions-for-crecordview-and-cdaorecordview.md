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
ms.openlocfilehash: 8eef2f3dc7880f9b2a937a26db1b74687fa00f1d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222842"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>CRecordView ve CDaoRecordView için İletişim Kutusu Veri Değişimi İşlevleri

Bu konuda, bir [CRecordset](../../mfc/reference/crecordset-class.md) ve [CRecordView](../../mfc/reference/crecordview-class.md) formu veya bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) formu arasında veri alışverişi yapmak için kullanılan DDX_Field işlevleri listelenmektedir. DAO, Access veritabanları ile birlikte kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

> [!NOTE]
> DDX_Field işlevler, verileri bir form içinde denetimlerle değiş tokuş ettikleri için DDX işlevleri gibidir. Ancak, DDX 'nin aksine, kayıt görünümündeki alanları yerine görünümün ilişkili kayıt kümesi nesnesinin alanlarıyla verileri değiş tokuş ederler. Daha fazla bilgi için bkz `CRecordView` . sınıflar ve `CDaoRecordView` .

### <a name="ddx_field-functions"></a>DDX_Field Işlevleri

|||
|-|-|
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|Bir kayıt kümesi alanı veri üyesi ve geçerli seçimin dizini ile bir [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)içindeki Birleşik giriş kutusunda bulunan tamsayı verilerini aktarır.|
|[DDX_FieldCBString](#ddx_fieldcbstring)|Bir `CString` kayıt kümesi alanı veri üyesi ve bir veya içindeki Birleşik giriş kutusunun düzenleme denetimi arasında veri aktarır `CRecordView` `CDaoRecordView` . Kayıt kümesinden denetime veri taşırken, bu işlev belirtilen dizedeki karakterlerle başlayan açılan kutudaki öğeyi seçer.|
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Bir `CString` kayıt kümesi alanı veri üyesi ve bir veya içindeki Birleşik giriş kutusunun düzenleme denetimi arasında veri aktarır `CRecordView` `CDaoRecordView` . Kayıt kümesinden denetime veri taşırken, bu işlev, belirtilen dizeyle tam olarak eşleşen Birleşik giriş kutusunda bulunan öğeyi seçer.|
|[DDX_FieldCheck](#ddx_fieldcheck)|Boole verilerini bir kayıt kümesi alanı veri üyesi ile veya içindeki onay kutusu arasında aktarır `CRecordView` `CDaoRecordView` .|
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|Bir kayıt kümesi alanı veri üyesi ve bir veya içindeki bir liste kutusunda geçerli seçimin dizini arasında tam sayı verilerini aktarır `CRecordView` `CDaoRecordView` .|
|[DDX_FieldLBString](#ddx_fieldlbstring)|Bir liste kutusu denetimi ve bir kayıt kümesinin alan veri üyeleri arasında [CString](../../atl-mfc-shared/reference/cstringt-class.md) verilerinin aktarımını yönetir. Kayıt kümesinden denetime veri taşırken, bu işlev belirtilen dizedeki karakterlerle başlayan liste kutusunda öğeyi seçer.|
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|`CString`Bir liste kutusu denetimi ve bir kayıt kümesinin alan veri üyeleri arasında veri aktarımını yönetir. Kayıt kümesinden denetime veri taşırken, bu işlev belirtilen dizeyle tam olarak eşleşen ilk öğeyi seçer.|
|[DDX_FieldRadio](#ddx_fieldradio)|Bir kayıt kümesi alanı veri üyesi ve bir veya içindeki radyo düğmesi grubu arasında tam sayı verilerini `CRecordView` aktarır `CDaoRecordView` .|
|[DDX_FieldScroll](#ddx_fieldscroll)|Veya içindeki bir kaydırma çubuğu denetiminin kaydırma konumunu alır veya ayarlar `CRecordView` `CDaoRecordView` . [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) işlevinizden çağrı.|
|[DDX_FieldSlider](#ddx_fieldslider)|Bir kayıt görünümündeki kaydırıcı denetiminin Thumb konumunu ve bir kayıt **`int`** kümesinin alan veri üyesini eşitler. |
|[DDX_FieldText](#ddx_fieldtext)|**`int`** **UINT** **`long`** `DWORD` [CString](../../atl-mfc-shared/reference/cstringt-class.md) **`float`** **`double`** **`short`** Bir kayıt kümesi alanı veri üyesi ve bir veya içindeki bir düzenleme kutusu arasında bir Recordset [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)alan veri üyesi ve [copacurrency](../../mfc/reference/colecurrency-class.md) verileri `CRecordView` `CDaoRecordView` aktarmak için aşırı yüklenmiş sürümler mevcuttur.|

## <a name="ddx_fieldcbindex"></a><a name="ddx_fieldcbindex"></a>DDX_FieldCBIndex

`DDX_FieldCBIndex`İşlevi bir kayıt görünümündeki Birleşik giriş kutusu denetiminin liste kutusu denetimindeki seçili öğenin dizinini ve **`int`** kayıt görünümüyle ilişkili bir kayıt kümesinin alan veri üyesini eşitler.

```cpp
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
İlişkili veya nesne içindeki bir alan veri üyesine başvuru `CRecordset` `CDaoRecordset` .

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinden denetime veri taşırken, bu işlev, *dizinde*belirtilen değere göre denetimdeki seçimi ayarlar. Kayıt kümesinden denetime yapılan bir aktarımda, kayıt kümesi alanı null ise, MFC dizin değerini 0 olarak ayarlar. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa veya hiçbir öğe seçilmezse, kayıt kümesi alanı 0 olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . Örnek, için de benzerdir `DDX_FieldCBIndex` .

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="ddx_fieldcbstring"></a><a name="ddx_fieldcbstring"></a>DDX_FieldCBString

`DDX_FieldCBString`İşlevi bir kayıt görünümündeki Birleşik giriş [CString](../../atl-mfc-shared/reference/cstringt-class.md) kutusu denetiminin düzenleme denetimi ve `CString` kayıt görünümüyle ilişkili bir kayıt kümesinin alan veri üyesi arasında CString verilerinin aktarımını yönetir.

```cpp
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

*deeri*<br/>
İlişkili veya nesne içindeki bir alan veri üyesine başvuru `CRecordset` `CDaoRecordset` .

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinden denetime veri taşırken, bu işlev Birleşik giriş kutusundaki geçerli seçimi, *değer*'de belirtilen dizedeki karakterlerle başlayan ilk satıra ayarlar. Kayıt kümesinden denetime olan bir aktarım üzerinde, kayıt kümesi alanı null ise, seçim açılan kutudan kaldırılır ve Birleşik giriş kutusunun düzenleme denetimi Empty olarak ayarlanır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, alan izin veriyorsa kayıt kümesi alanı null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . Örnek, için bir çağrısı içerir `DDX_FieldCBString` .

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="ddx_fieldcbstringexact"></a><a name="ddx_fieldcbstringexact"></a>DDX_FieldCBStringExact

`DDX_FieldCBStringExact`İşlevi bir kayıt görünümündeki Birleşik giriş [CString](../../atl-mfc-shared/reference/cstringt-class.md) kutusu denetiminin düzenleme denetimi ve `CString` kayıt görünümüyle ilişkili bir kayıt kümesinin alan veri üyesi arasında CString verilerinin aktarımını yönetir.

```cpp
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

*deeri*<br/>
İlişkili veya nesne içindeki bir alan veri üyesine başvuru `CRecordset` `CDaoRecordset` .

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinden denetime veri taşırken, bu işlev Birleşik giriş kutusundaki geçerli seçimi, *değer*'de belirtilen dizeyle tam olarak eşleşen ilk satıra ayarlar. Kayıt kümesinden denetime olan bir aktarım üzerinde, kayıt kümesi alanı NULL ise, açılan kutudan herhangi bir seçim kaldırılır ve Birleşik giriş kutusunun düzenleme kutusu boş olarak ayarlanır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanı NULL olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . İçin yapılan çağrılar `DDX_FieldCBStringExact` benzerdir.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="ddx_fieldcheck"></a><a name="ddx_fieldcheck"></a>DDX_FieldCheck

`DDX_FieldCheck`İşlevi **`int`** bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve **`int`** iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir veri üyesi içindeki bir onay kutusu denetimi arasında veri aktarımını yönetir.

```cpp
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

*deeri*<br/>
İletişim kutusu, form görünümü veya veri alışverişi yapılan denetim görünümü nesnesinin üye değişkenine başvuru.

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`DDX_FieldCheck`Çağrıldığında, *değeri* onay kutusu denetiminin geçerli durumu olarak ayarlanır veya aktarımın yönüne bağlı olarak denetimin durumu *değer*olarak ayarlanır.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="ddx_fieldlbindex"></a><a name="ddx_fieldlbindex"></a>DDX_FieldLBIndex

`DDX_FieldLBIndex`İşlevi bir kayıt görünümündeki liste kutusu denetimindeki seçili öğenin dizinini ve **`int`** kayıt görünümüyle ilişkili bir kayıt kümesinin alan veri üyesini eşitler.

```cpp
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
İlişkili veya nesne içindeki bir alan veri üyesine başvuru `CRecordset` `CDaoRecordset` .

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

## <a name="ddx_fieldlbstring"></a><a name="ddx_fieldlbstring"></a>DDX_FieldLBString

, `DDX_FieldLBString` Bir kayıt görünümündeki liste kutusu denetiminin geçerli seçimini, kayıt görünümüyle ilişkili bir kayıt kümesinin [CString](../../atl-mfc-shared/reference/cstringt-class.md) alan veri üyesine kopyalar.

```cpp
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

*deeri*<br/>
İlişkili veya nesne içindeki bir alan veri üyesine başvuru `CRecordset` `CDaoRecordset` .

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Ters yönde, bu işlev liste kutusundaki geçerli seçimi *değere*göre belirtilen dizedeki karakterlerle başlayan ilk satıra ayarlar. Kayıt kümesinden denetime olan bir aktarım üzerinde, kayıt kümesi alanı null ise, herhangi bir seçim liste kutusundan kaldırılır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanı null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . İçin yapılan çağrılar `DDX_FieldLBString` benzerdir.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="ddx_fieldlbstringexact"></a><a name="ddx_fieldlbstringexact"></a>DDX_FieldLBStringExact

`DDX_FieldLBStringExact`İşlevi bir kayıt görünümündeki liste kutusu denetiminin geçerli seçimini, kayıt görünümüyle ilişkili bir kayıt kümesinin [CString](../../atl-mfc-shared/reference/cstringt-class.md) alan veri üyesine kopyalar.

```cpp
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

*deeri*<br/>
İlişkili veya nesne içindeki bir alan veri üyesine başvuru `CRecordset` `CDaoRecordset` .

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Ters yönde, bu işlev liste kutusundaki geçerli seçimi, *değer*'de belirtilen dizeyle tam olarak eşleşen ilk satıra ayarlar. Kayıt kümesinden denetime olan bir aktarım üzerinde, kayıt kümesi alanı null ise, herhangi bir seçim liste kutusundan kaldırılır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanı null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . İçin yapılan çağrılar `DDX_FieldLBStringExact` benzerdir.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="ddx_fieldradio"></a><a name="ddx_fieldradio"></a>DDX_FieldRadio

`DDX_FieldRadio`İşlevi bir kayıt görünümü kayıt kümesinin sıfır tabanlı bir **`int`** üye değişkenini, kayıt görünümündeki radyo düğmeleri grubundaki seçili radyo düğmesiyle ilişkilendirir.

```cpp
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

*deeri*<br/>
İlişkili veya nesne içindeki bir alan veri üyesine başvuru `CRecordset` `CDaoRecordset` .

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi alanından görünüme aktarılırken, bu işlev *nth* radyo düğmesini (sıfır tabanlı) açar ve diğer düğmeleri kapatır. Ters yönde bu işlev, kayıt kümesi alanını şu anda açık olan (işaretli) radyo düğmesinin sıra numarası olarak ayarlar. Kayıt kümesinden denetime yapılan bir aktarım üzerinde, kayıt kümesi alanı null ise, hiçbir düğme seçili değildir. Denetimden kayıt kümesine bir aktarımdan, Denetim seçili değilse, alan izin veriyorsa kayıt kümesi alanı null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . İçin yapılan çağrılar `DDX_FieldRadio` benzerdir.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="ddx_fieldscroll"></a><a name="ddx_fieldscroll"></a>DDX_FieldScroll

`DDX_FieldScroll`İşlevi bir kayıt görünümündeki bir kaydırma çubuğu denetiminin kaydırma konumunu ve **`int`** kayıt görünümüyle ilişkili bir kayıt kümesinin alan veri üyesini (veya eşlemeyi seçtiğiniz tamsayı değişkeni ile) eşitler.

```cpp
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

*deeri*<br/>
İlişkili veya nesne içindeki bir alan veri üyesine başvuru `CRecordset` `CDaoRecordset` .

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinden denetime veri taşırken, bu işlev kaydırma çubuğu denetiminin kaydırma konumunu, *değer*'de belirtilen değere ayarlar. Kayıt kümesinden denetime olan bir aktarım üzerinde, kayıt kümesi alanı null ise, kaydırma çubuğu denetimi 0 olarak ayarlanır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanının değeri 0 ' dır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . İçin yapılan çağrılar `DDX_FieldScroll` benzerdir.

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="ddx_fieldslider"></a><a name="ddx_fieldslider"></a>DDX_FieldSlider

`DDX_FieldSlider`İşlevi bir kayıt görünümündeki kaydırıcı denetiminin Thumb konumunu ve **`int`** kayıt görünümüyle ilişkili bir kayıt kümesinin alan veri üyesini (veya eşlemeyi seçtiğiniz tamsayı değişkeni ile) eşitler.

### <a name="syntax"></a>Söz dizimi

```cpp
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

*deeri*<br/>
Değiş tokuş edilecek değere bir başvuru. Bu parametre, kaydırıcı denetiminin geçerli Thumb konumunu ayarlamak için veya kullanır.

*pRecordset*<br/>
`CRecordset`Verilerin alınıp alındığı ilişkili veya nesneye yönelik bir işaretçi `CDaoRecordset` .

### <a name="remarks"></a>Açıklamalar

Kayıt kümesindeki verileri kaydırıcıya taşırken, bu işlev kaydırıcının konumunu *değer*'de belirtilen değere ayarlar. Kayıt kümesinden denetime olan bir aktarım üzerinde, kayıt kümesi alanı null ise kaydırıcı denetiminin konumu 0 olarak ayarlanır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanının değeri 0 ' dır.

`DDX_FieldSlider`, yalnızca bir konum yerine bir Aralık ayarlamatabilen kaydırıcı denetimleriyle birlikte Aralık bilgilerini değiş tokuş etmez.

ODBC tabanlı sınıflarla çalışıyorsanız, işlevin ilk geçersiz kılmasını kullanın. İkinci geçersiz kılmayı DAO tabanlı sınıflarla kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../dialog-data-exchange-and-validation.md). Ve alanları için DDX hakkında örnekler ve daha fazla bilgi için `CRecordView` `CDaoRecordView` bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md). Kaydırıcı denetimleri hakkında daha fazla bilgi için bkz. [CSliderCtrl kullanma](../using-csliderctrl.md).

### <a name="example"></a>Örnek

Genel DDX_Field bir örnek için bkz. [DDX_FieldText](#ddx_fieldtext) . İçin yapılan çağrılar `DDX_FieldSlider` benzerdir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="ddx_fieldtext"></a><a name="ddx_fieldtext"></a>DDX_FieldText

`DDX_FieldText`İşlevi **`int`** , bir **`short`** **`long`** [CString](../../atl-mfc-shared/reference/cstringt-class.md) **`float`** **`double`** düzenleme kutusu denetimi ve bir kayıt kümesinin alan veri üyeleri arasında,,, DWORD, CString,,, **bool**veya **byte** verilerinin aktarımını yönetir.

```cpp
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

*deeri*<br/>
İlişkili veya nesne içindeki bir alan veri üyesine başvuru `CRecordset` `CDaoRecordset` . Değerin veri türü, kullandığınız aşırı yüklenmiş sürümlere bağlıdır `DDX_FieldText` .

*pRecordset*<br/>
Verilerin alınıp alındığı [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi. Bu işaretçi `DDX_FieldText` null değerleri algılamaya ve ayarlamaya olanak sağlar.

### <a name="remarks"></a>Açıklamalar

[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesneleri Için `DDX_FieldText` [Cotadatetime](../../atl-mfc-shared/reference/coledatetime-class.md)ve [copacurrency](../../mfc/reference/colecurrency-class.md) değerlerini aktarmayı da yönetir. Boş bir düzenleme kutusu denetimi null değeri gösterir. Kayıt kümesinden denetime yapılan bir aktarımda, kayıt kümesi alanı null ise, düzenleme kutusu boş olarak ayarlanır. Denetimden kayıt kümesine bir aktarımdan, denetim boşsa, kayıt kümesi alanı null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız, [CRecordset](../../mfc/reference/crecordset-class.md) parametrelerini içeren sürümleri kullanın. DAO tabanlı sınıflarla çalışıyorsanız, [Cdaokayıt kümesi](../../mfc/reference/cdaorecordset-class.md) parametreleriyle sürümleri kullanın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDAORECORDVIEW](../../mfc/reference/cdaorecordview-class.md) alanları için DDX hakkında örnekler ve daha fazla bilgi Için bkz. [Kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

`DoDataExchange`Bir [CRecordView](../../mfc/reference/crecordview-class.md) için aşağıdaki işlev `DDX_FieldText` üç veri türü için işlev çağrıları içerir: `IDC_COURSELIST` Birleşik giriş kutusudur; diğer iki denetim düzenleme kutularıdır. DAO programlama için *m_pSet* parametresi [CRecordset](../../mfc/reference/crecordset-class.md) veya [cdaokayıt kümesine](../../mfc/reference/cdaorecordset-class.md)yönelik bir işaretçidir.

[!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)
