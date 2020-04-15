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
ms.openlocfilehash: 3128b1ba459cb017d1cdb2321bc55d865aa4f8b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365782"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>CRecordView ve CDaoRecordView için İletişim Kutusu Veri Değişimi İşlevleri

Bu konu, [CRecordset](../../mfc/reference/crecordset-class.md) ile [CRecordView](../../mfc/reference/crecordview-class.md) formu veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) formu arasında veri alışverişi için kullanılan DDX_Field işlevleri ni listeler. DAO Access veritabanları ile kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3.6 son sürümüdür ve eski miş olarak kabul edilir.

> [!NOTE]
> DDX_Field işlevleri, bir formdaki denetimlerle veri alışverişinde bulunmaları için DDX işlevleri gibidir. Ancak DDX'in aksine, kayıt görünümü alanları yerine görünümün ilişkili kayıt kümesi nesnesinin alanlarıyla veri alışverişi yaparlar. Daha fazla bilgi `CRecordView` için `CDaoRecordView`sınıflara bakın ve .

### <a name="ddx_field-functions"></a>DDX_Field Fonksiyonları

|||
|-|-|
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|Bir kaydedici alan veri üyesi ile [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView'daki](../../mfc/reference/cdaorecordview-class.md)açılan kutudaki geçerli seçimin dizini arasında tamsayı verileri aktarın.|
|[DDX_FieldCBString](#ddx_fieldcbstring)|Verileri `CString` bir kayıt kümesi alanı veri üyesi ile bir `CRecordView` veya `CDaoRecordView`'deki açılan kutunun edit denetimi arasında aktarın. Verileri kayıt kümesinden denetime taşımakta, bu işlev belirtilen dizedeki karakterlerle başlayan açılan kutudaki öğeyi seçer.|
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Verileri `CString` bir kayıt kümesi alanı veri üyesi ile bir `CRecordView` veya `CDaoRecordView`'deki açılan kutunun edit denetimi arasında aktarın. Verileri kayıt kümesinden denetime taşımakta, bu işlev açılan kutudaki belirtilen dizeyle tam olarak eşleşen öğeyi seçer.|
|[DDX_FieldCheck](#ddx_fieldcheck)|Boolean verilerini kayıt kümesi alanı veri üyesi ile `CRecordView` bir `CDaoRecordView`veya ' deki onay kutusu arasında aktarın.|
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|Tamsayı verilerini, bir kayıt kümesi alanı veri üyesi ile bir `CRecordView` liste kutusundaki `CDaoRecordView`geçerli seçimin dizini arasında aktarAn bir veya .|
|[DDX_FieldLBString](#ddx_fieldlbstring)|[CString](../../atl-mfc-shared/reference/cstringt-class.md) verilerinin liste kutusu denetimi ile bir kayıt kümesinin alan veri üyeleri arasında aktarılmasını yönetir. Verileri kayıt kümesinden denetime taşımakta, bu işlev liste kutusunda belirtilen dizedeki karakterlerle başlayan öğeyi seçer.|
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|Bir liste kutusu `CString` denetimi ile bir kayıt kümesinin alan veri üyeleri arasındaki veri aktarımını yönetir. Verileri kayıt kümesinden denetime taşımakta, bu işlev belirtilen dizeyle tam olarak eşleşen ilk öğeyi seçer.|
|[DDX_FieldRadio](#ddx_fieldradio)|Tamsayı verilerini bir kayıt kümesi alanı veri üyesi ile bir `CRecordView` radyo `CDaoRecordView`düğmesi grubu arasında aktarAn bir veya .|
|[DDX_FieldScroll](#ddx_fieldscroll)|Bir kaydırma çubuğu denetiminin kaydırma konumunu `CRecordView` ayarlar `CDaoRecordView`veya alır. [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) işlevinizden arayın.|
|[DDX_FieldSlider](#ddx_fieldslider)|Bir kaymak denetiminin başparmak konumunu bir kayıt görünümünde ve bir kayıt kümesinin `int` alan veri üyesini eşitler. |
|[DDX_FieldText](#ddx_fieldtext)|Aşırı yüklü sürümleri aktarmak `int`için kullanılabilir , **UINT**, **uzun**, `DWORD` [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **çift**, **kısa**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), ve `CRecordView` [COleCurrency](../../mfc/reference/colecurrency-class.md) veri bir kayıt alanı veri üyesi ve bir veya bir bir edit kutusu arasında . `CDaoRecordView`|

## <a name="ddx_fieldcbindex"></a><a name="ddx_fieldcbindex"></a>DDX_FieldCBIndex

İşlev, `DDX_FieldCBIndex` liste kutusu denetiminde bir kayıt görünümünde açılan kutu denetiminde seçili `int` öğenin dizinini ve kayıt görünümüyle ilişkili bir kayıt kümesinin alan veri üyesini eşitler.

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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
[CRecordView veya CDaoRecordView](../../mfc/reference/crecordview-class.md) nesnesindeki denetimin kimliği. [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)

*Dizin*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnedeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin değiş tokuş edildiği [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Verileri kayıt kümesinden denetime taşınırken, bu işlev denetimde seçimi *dizinte*belirtilen değere göre ayarlar. Kayıt kümesinden denetime aktarımda, kayıt kümesi alanı Null ise, MFC dizin değerini 0 olarak ayarlar. Denetimden kayıt kümesine aktarımda, denetim boşsa veya öğe seçili değilse, kayıt kümesi alanı 0 olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın. [CRecordView ve CDaoRecordView](../../mfc/reference/crecordview-class.md) alanları [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) için DDX hakkında örnekler ve daha fazla bilgi için [Kayıt Görünümleri](../../data/record-views-mfc-data-access.md)makalesine bakın.

### <a name="example"></a>Örnek

Genel DDX_Field örneği için [DDX_FieldText](#ddx_fieldtext) bakın. Örnek için `DDX_FieldCBIndex`benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="ddx_fieldcbstring"></a><a name="ddx_fieldcbstring"></a>DDX_FieldCBString

İşlev, `DDX_FieldCBString` [cstring](../../atl-mfc-shared/reference/cstringt-class.md) verilerinin bir kayıt görünümündeki açılan kutu denetiminin edit `CString` denetimi ile kayıt görünümüyle ilişkili bir kayıt kümesinin alan veri üyesi arasında aktarılmasını yönetir.

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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
[CRecordView veya CDaoRecordView](../../mfc/reference/crecordview-class.md) nesnesindeki denetimin kimliği. [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)

*Değer*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnedeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin değiş tokuş edildiği [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Verileri kayıt kümesinden denetime taşımakta, bu işlev açılan kutudaki geçerli seçimi *değer*olarak belirtilen dizedeki karakterlerle başlayan ilk satıra ayarlar. Kayıt kümesinden denetime aktarımda, kayıt kümesi alanı Null ise, tüm seçim açılan kutudan kaldırılır ve açılan kutunun edit denetimi boş olarak ayarlanır. Denetimden kayıt kümesine aktarımda, denetim boşsa, alan izin verirse kayıt kümesi alanı Null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın. [CRecordView ve CDaoRecordView](../../mfc/reference/crecordview-class.md) alanları [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) için DDX hakkında örnekler ve daha fazla bilgi için [Kayıt Görünümleri](../../data/record-views-mfc-data-access.md)makalesine bakın.

### <a name="example"></a>Örnek

Genel DDX_Field örneği için [DDX_FieldText](#ddx_fieldtext) bakın. Örnek, '' `DDX_FieldCBString`ye yapılan bir çağrıyı içerir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxdao.h

## <a name="ddx_fieldcbstringexact"></a><a name="ddx_fieldcbstringexact"></a>DDX_FieldCBStringExact

İşlev, `DDX_FieldCBStringExact` [cstring](../../atl-mfc-shared/reference/cstringt-class.md) verilerinin bir kayıt görünümündeki açılan kutu denetiminin edit `CString` denetimi ile kayıt görünümüyle ilişkili bir kayıt kümesinin alan veri üyesi arasında aktarılmasını yönetir.

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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
[CRecordView veya CDaoRecordView](../../mfc/reference/crecordview-class.md) nesnesindeki denetimin kimliği. [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)

*Değer*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnedeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin değiş tokuş edildiği [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Verileri kayıt kümesinden denetime taşımakta, bu işlev açılan kutudaki geçerli seçimi *değerolarak*belirtilen dizeyle tam olarak eşleşen ilk satıra ayarlar. Kayıt kümesinden denetime aktarımda, kayıt kümesi alanı NULL ise, tüm seçim açılan kutudan kaldırılır ve açılan kutunun ediniş kutusu boş olarak ayarlanır. Denetimden kayıt kümesine aktarımda, denetim boşsa, kayıt kümesi alanı NULL olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın. [CRecordView ve CDaoRecordView](../../mfc/reference/crecordview-class.md) alanları [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) için DDX hakkında örnekler ve daha fazla bilgi için [Kayıt Görünümleri](../../data/record-views-mfc-data-access.md)makalesine bakın.

### <a name="example"></a>Örnek

Genel DDX_Field örneği için [DDX_FieldText](#ddx_fieldtext) bakın. Aramalar `DDX_FieldCBStringExact` benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxdao.h

## <a name="ddx_fieldcheck"></a><a name="ddx_fieldcheck"></a>DDX_FieldCheck

İşlev, `DDX_FieldCheck` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **int** veri üyesindeki bir onay kutusu denetimi arasında **int** verilerinin aktarılmasını yönetir.

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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliğiyle ilişkili onay kutusu denetiminin kaynak kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin değiş tokuş edildiği denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

*pRecordset*<br/>
Verilerin değiş tokuş edildiği [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, `DDX_FieldCheck` *değer* onay kutusu denetiminin geçerli durumuna ayarlanır veya denetimin durumu aktarım yönüne bağlı olarak *değer*olarak ayarlanır.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxdao.h

## <a name="ddx_fieldlbindex"></a><a name="ddx_fieldlbindex"></a>DDX_FieldLBIndex

İşlev, `DDX_FieldLBIndex` bir liste kutusu denetiminde seçili öğenin dizinini bir kayıt görünümünde ve kayıt görünümüyle ilişkili bir kayıt kümesinin **int** alan veri üyesini eşitler.

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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
[CRecordView veya CDaoRecordView](../../mfc/reference/crecordview-class.md) nesnesindeki denetimin kimliği. [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)

*Dizin*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnedeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin değiş tokuş edildiği [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Verileri kayıt kümesinden denetime taşınırken, bu işlev denetimde seçimi *dizinte*belirtilen değere göre ayarlar. Kayıt kümesinden denetime aktarımda, kayıt kümesi alanı Null ise, MFC dizin değerini 0 olarak ayarlar. Denetimden kayıt kümesine aktarımda, denetim boşsa, kayıt kümesi alanı 0 olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın. [CRecordView ve CDaoRecordView](../../mfc/reference/crecordview-class.md) alanları [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) için DDX hakkında örnekler ve daha fazla bilgi için [Kayıt Görünümleri](../../data/record-views-mfc-data-access.md)makalesine bakın.

### <a name="example"></a>Örnek

Genel DDX_Field örneği için [DDX_FieldText](#ddx_fieldtext) bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxdao.h

## <a name="ddx_fieldlbstring"></a><a name="ddx_fieldlbstring"></a>DDX_FieldLBString

Kayıt `DDX_FieldLBString` görünümüyle ilişkili bir kayıt kümesinin [CString](../../atl-mfc-shared/reference/cstringt-class.md) alan veri üyesine kayıt görünümünde liste kutusu denetiminin geçerli seçimini kopyalar.

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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
[CRecordView veya CDaoRecordView](../../mfc/reference/crecordview-class.md) nesnesindeki denetimin kimliği. [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)

*Değer*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnedeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin değiş tokuş edildiği [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Ters yönde, bu işlev liste kutusundaki geçerli seçimi *değer*tarafından belirtilen dizedeki karakterlerle başlayan ilk satıra ayarlar. Kayıt kümesinden denetime aktarımda, kayıt kümesi alanı Null ise, herhangi bir seçim liste kutusundan kaldırılır. Denetimden kayıt kümesine aktarımda, denetim boşsa, kayıt kümesi alanı Null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın. [CRecordView ve CDaoRecordView](../../mfc/reference/crecordview-class.md) alanları [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) için DDX hakkında örnekler ve daha fazla bilgi için [Kayıt Görünümleri](../../data/record-views-mfc-data-access.md)makalesine bakın.

### <a name="example"></a>Örnek

Genel DDX_Field örneği için [DDX_FieldText](#ddx_fieldtext) bakın. Aramalar `DDX_FieldLBString` benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxdao.h

## <a name="ddx_fieldlbstringexact"></a><a name="ddx_fieldlbstringexact"></a>DDX_FieldLBStringExact

İşlev, `DDX_FieldLBStringExact` kayıt görünümüyle ilişkili bir kayıt kümesinin [CString](../../atl-mfc-shared/reference/cstringt-class.md) alan veri üyesine kayıt görünümünde liste kutusu denetiminin geçerli seçimini kopyalar.

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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
[CRecordView veya CDaoRecordView](../../mfc/reference/crecordview-class.md) nesnesindeki denetimin kimliği. [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)

*Değer*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnedeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin değiş tokuş edildiği [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Ters yönde, bu işlev liste kutusundaki geçerli seçimi *değerolarak*belirtilen dizeyle tam olarak eşleşen ilk satıra ayarlar. Kayıt kümesinden denetime aktarımda, kayıt kümesi alanı Null ise, herhangi bir seçim liste kutusundan kaldırılır. Denetimden kayıt kümesine aktarımda, denetim boşsa, kayıt kümesi alanı Null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın. [CRecordView ve CDaoRecordView](../../mfc/reference/crecordview-class.md) alanları [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) için DDX hakkında örnekler ve daha fazla bilgi için [Kayıt Görünümleri](../../data/record-views-mfc-data-access.md)makalesine bakın.

### <a name="example"></a>Örnek

Genel DDX_Field örneği için [DDX_FieldText](#ddx_fieldtext) bakın. Aramalar `DDX_FieldLBStringExact` benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxdao.h

## <a name="ddx_fieldradio"></a><a name="ddx_fieldradio"></a>DDX_FieldRadio

İşlev, `DDX_FieldRadio` kayıt görünümündeki bir grup radyo düğmesinde şu anda seçili olan radyo düğmesiyle, kayıt görünümündeki kayıt kümesinin sıfır tabanlı **int** üye değişkenini ilişkilendirer.

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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesindeki bitişik radyo düğmesi denetimlerinin gruptaki ilk kimliği (stil WS_GROUP).

*Değer*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnedeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin değiş tokuş edildiği [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi alanından görünüme aktarırken, bu işlev *nth* radyo düğmesini (sıfır tabanlı) açar ve diğer düğmeleri kapatır. Bu işlev, ters yönde, kayıt kümesi alanını şu anda açık olan (kontrol edilen) radyo düğmesinin ordinal numarasına ayarlar. Kayıt kümesinden denetime aktarımda, kayıt kümesi alanı Null ise, hiçbir düğme seçilmez. Denetimden kayıt kümesine aktarımda, denetim seçili değilse, alan buna izin verirse, kayıt kümesi alanı Null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın. [CRecordView ve CDaoRecordView](../../mfc/reference/crecordview-class.md) alanları [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) için DDX hakkında örnekler ve daha fazla bilgi için [Kayıt Görünümleri](../../data/record-views-mfc-data-access.md)makalesine bakın.

### <a name="example"></a>Örnek

Genel DDX_Field örneği için [DDX_FieldText](#ddx_fieldtext) bakın. Aramalar `DDX_FieldRadio` benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxdao.h

## <a name="ddx_fieldscroll"></a><a name="ddx_fieldscroll"></a>DDX_FieldScroll

İşlev, `DDX_FieldScroll` kayıt görünümünde kaydırma çubuğu denetiminin kaydırma konumunu ve kayıt görünümüyle ilişkili bir kayıt kümesinin **int** alan veri üyesini (veya eşlemeyi seçtiğiniz her tamsayı değişkeniyle) eşitler.

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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesindeki bitişik radyo düğmesi denetimlerinin gruptaki ilk kimliği (stil WS_GROUP).

*Değer*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnedeki bir alan veri üyesine başvuru.

*pRecordset*<br/>
Verilerin değiş tokuş edildiği [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Verileri kayıt kümesinden denetime taşımakta, bu işlev kaydırma çubuğu denetiminin kaydırma konumunu *değerde*belirtilen değere ayarlar. Kayıt kümesinden denetime aktarımda, kayıt kümesi alanı Null ise kaydırma çubuğu denetimi 0 olarak ayarlanır. Denetimden kayıt kümesine aktarımda, denetim boşsa, kayıt kümesi alanının değeri 0'dır.

ODBC tabanlı sınıflarla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflarla çalışıyorsanız ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın. [CRecordView ve CDaoRecordView](../../mfc/reference/crecordview-class.md) alanları [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) için DDX hakkında örnekler ve daha fazla bilgi için [Kayıt Görünümleri](../../data/record-views-mfc-data-access.md)makalesine bakın.

### <a name="example"></a>Örnek

Genel DDX_Field örneği için [DDX_FieldText](#ddx_fieldtext) bakın. Aramalar `DDX_FieldScroll` benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxdao.h

## <a name="ddx_fieldslider"></a><a name="ddx_fieldslider"></a>DDX_FieldSlider

İşlev, `DDX_FieldSlider` bir kaydırıcı denetiminin başparmak konumunu bir kayıt görünümünde ve kayıt görünümüyle ilişkili bir kayıt kümesinin **int** alan veri üyesini (veya eşlemeyi seçtiğiniz her tamsayı değişkeniyle) eşitler.

### <a name="syntax"></a>Sözdizimi

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

*Pdx*<br/>
[CDataExchange](cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Kaydırıcı denetiminin kaynak kimliği.

*Değer*<br/>
Değiştirilecek değere bir başvuru. Bu parametre kaydırıcı denetiminin geçerli başparmak konumunu ayarlamak için tutar veya kullanılır.

*pRecordset*<br/>
Verilerin değiş tokuş edildiği ilişkili `CRecordset` veya `CDaoRecordset` nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Verileri kaydediciden kaydırıcıya taşınırken, bu işlev kaydırıcının konumunu *değerde*belirtilen değere ayarlar. Kayıt kümesinden denetime aktarımda, kayıt kümesi alanı Null ise, kaydırıcı denetiminin konumu 0 olarak ayarlanır. Denetimden kayıt kümesine aktarımda, denetim boşsa, kayıt kümesi alanının değeri 0'dır.

`DDX_FieldSlider`sadece bir pozisyon yerine bir aralık ayarı yeteneğine sahip kaydırıcı kontrolleri ile aralık bilgisi alışverişi yapmaz.

ODBC tabanlı sınıflarla çalışıyorsanız işlevin ilk geçersiz kılmasını kullanın. DAO tabanlı sınıfları ile ikinci geçersiz kılma kullanın.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../dialog-data-exchange-and-validation.md)bakın. Örnekler ve ddx ve `CRecordView` `CDaoRecordView` alanlar hakkında daha fazla bilgi için [bkz.](../../data/record-views-mfc-data-access.md) Kaydırıcı denetimleri hakkında daha fazla bilgi için [Bkz. CSliderCtrl'yi kullanma.](../using-csliderctrl.md)

### <a name="example"></a>Örnek

Genel DDX_Field örneği için [DDX_FieldText](#ddx_fieldtext) bakın. Aramalar `DDX_FieldSlider` benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="ddx_fieldtext"></a><a name="ddx_fieldtext"></a>DDX_FieldText

İşlev, `DDX_FieldText` bir düzenleme kutusu denetimi ile bir kayıt kümesinin alan veri üyeleri arasında **int,** **short**, **long,** DWORD, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **double**, **BOOL**veya **BYTE** verilerinin aktarılmasını yönetir.

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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
[CRecordView veya CDaoRecordView](../../mfc/reference/crecordview-class.md) nesnesindeki denetimin kimliği. [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)

*Değer*<br/>
İlişkili `CRecordset` veya `CDaoRecordset` nesnedeki bir alan veri üyesine başvuru. Değerin veri türü, aşırı yüklenen sürümlerinden `DDX_FieldText` hangisinin kullanıldığına bağlıdır.

*pRecordset*<br/>
Verilerin değiş tokuş edildiği [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine işaretçi. Bu işaretçi, Null değerlerini `DDX_FieldText` algılamayı ve ayarlamayı sağlar.

### <a name="remarks"></a>Açıklamalar

[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesneleri için, `DDX_FieldText` [COleDateTime ve COleCurrency](../../atl-mfc-shared/reference/coledatetime-class.md)değerlerini aktarmayı da yönetir. [COleCurrency](../../mfc/reference/colecurrency-class.md) Boş bir edit kutusu denetimi Null değerini gösterir. Kayıt kümesinden denetime aktarımda, kayıt kümesi alanı Null ise, edit kutusu boş olarak ayarlanır. Denetimden kayıt kümesine aktarımda, denetim boşsa, kayıt kümesi alanı Null olarak ayarlanır.

ODBC tabanlı sınıflarla çalışıyorsanız [CRecordset](../../mfc/reference/crecordset-class.md) parametrelerine sahip sürümleri kullanın. DAO tabanlı sınıflarla çalışıyorsanız [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) parametrelerine sahip sürümleri kullanın.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın. [CRecordView ve CDaoRecordView](../../mfc/reference/crecordview-class.md) alanları [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) için DDX hakkında örnekler ve daha fazla bilgi için [Kayıt Görünümleri](../../data/record-views-mfc-data-access.md)makalesine bakın.

### <a name="example"></a>Örnek

[CRecordView](../../mfc/reference/crecordview-class.md) için aşağıdaki `DDX_FieldText` `IDC_COURSELIST` `DoDataExchange` işlev üç veri türü için işlev çağrıları içerir: bir açılan kutudur; diğer iki denetim leri kutularını edit. DAO programlama için *m_pSet* parametresi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)için bir işaretçidir.

[!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](mfc-macros-and-globals.md)
