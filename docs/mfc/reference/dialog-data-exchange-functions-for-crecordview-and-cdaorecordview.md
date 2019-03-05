---
title: CRecordView ve CDaoRecordView için İletişim Kutusu Veri Değişimi İşlevleri
ms.date: 11/04/2016
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
ms.openlocfilehash: 2a794d16b2f94bf8ba66b6c0398dec262d8829e5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269896"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>CRecordView ve CDaoRecordView için İletişim Kutusu Veri Değişimi İşlevleri

Bu konuda arasında veri değişimi için kullanılan DDX_Field işlevleri listeler bir [CRecordset](../../mfc/reference/crecordset-class.md) ve [CRecordView](../../mfc/reference/crecordview-class.md) form veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ve [ CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) formu.

> [!NOTE]
>  Bunların bir formdaki denetimleri ile veri değişimi, DDX_Field işlevleri DDX gibi işlevlerdir. Ancak DDX, görünümün ilişkili kayıt kümesi nesnesi alanlarının bulunduğu yerine alanları kayıt görünümü ile veri değişimi. Daha fazla bilgi için bkz: sınıflarını `CRecordView` ve `CDaoRecordView`.

### <a name="ddxfield-functions"></a>DDX_Field işlevleri

|||
|-|-|
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|Kayıt kümesi alan veri üyesi ve geçerli seçimi birleşik giriş kutusunda dizinini arasında tamsayı veri aktarımı bir [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|
|[DDX_FieldCBString](#ddx_fieldcbstring)|Aktarımları `CString` düzenleme denetimi bir açılan bir kayıt kümesi alan veri üyesi arasında verileri kutu bir `CRecordView` veya `CDaoRecordView`. Bu işlev, öğe veri denetime kayıt kümesinden taşırken, belirtilen dizedeki karakterlerle başlayan birleşik giriş kutusundaki seçer.|
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Aktarımları `CString` düzenleme denetimi bir açılan bir kayıt kümesi alan veri üyesi arasında verileri kutu bir `CRecordView` veya `CDaoRecordView`. Veri denetime kayıt kümesinden taşırken, bu işlev birleşik giriş kutusuna tam olarak belirtilen dizesiyle eşleşen öğeyi seçer.|
|[DDX_FieldCheck](#ddx_fieldcheck)|Kayıt kümesi alan veri üyesi ve onay kutusuna arasında Boole veri aktarımı bir `CRecordView` veya `CDaoRecordView`.|
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|Kayıt kümesi alan veri üyesi ve bir liste kutusunda geçerli seçimin indisini arasında tamsayı veri aktarımı bir `CRecordView` veya `CDaoRecordView`.|
|[DDX_FieldLBString](#ddx_fieldlbstring)|Aktarımını yöneten [CString](../../atl-mfc-shared/reference/cstringt-class.md) bir liste kutusu denetimi ve bir kayıt kümesi alan veri üyeleri arasında veri. Bu işlev, öğe veri denetime kayıt kümesinden taşırken, belirtilen dizedeki karakterlerle başlayan liste kutusunda seçer.|
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|Aktarımını yöneten `CString` bir liste kutusu denetimi ve bir kayıt kümesi alan veri üyeleri arasında veri. Bu işlev, verileri kayıt kümesinden denetime taşıma, tam olarak belirtilen dizesiyle eşleşen ilk öğeyi seçer.|
|[DDX_FieldRadio](#ddx_fieldradio)|Kayıt kümesi alan veri üyesi ve bir grup radyo düğmeleri arasında tamsayı veri aktarımı bir `CRecordView` veya `CDaoRecordView`.|
|[DDX_FieldScroll](#ddx_fieldscroll)|Bir kaydırma çubuğu denetiminde kaydırma konumunu alır veya ayarlar bir `CRecordView` veya `CDaoRecordView`. Çağırmanıza, [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) işlevi.|
|[DDX_FieldSlider](#ddx_fieldslider)|Kayıt görünümü bir kaydırıcı denetimi thumb konumunu eşitler ve `int` kümesinin alan veri üyesi. |
|[DDX_FieldText](#ddx_fieldtext)|Aşırı yüklenmiş sürümleri aktarmak için kullanılabilir `int`, **UINT**, **uzun**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float** , **çift**, **kısa**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), ve [COleCurrency](../../mfc/reference/colecurrency-class.md) kayıt alan veri üyesi bir düzenleme arasında verileri kutu bir `CRecordView` veya `CDaoRecordView`.|

##  <a name="ddx_fieldcbindex"></a>  DDX_FieldCBIndex

`DDX_FieldCBIndex` İşlevi eşitler kayıt görünümü birleşik giriş kutusu denetiminde liste kutusu denetiminde seçili öğenin dizinini ve `int` kayıt görünümü ile ilişkili kayıt alan veri üyesi.

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesne.

*Dizin*<br/>
İlişkili alan veri üyesi başvuru `CRecordset` veya `CDaoRecordset` nesne.

*pRecordset*<br/>
Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesne.

### <a name="remarks"></a>Açıklamalar

Veri denetime kayıt kümesinden taşırken, bu işlev belirtilen değere göre denetiminde seçimi ayarlar *dizin*. Kayıt kümesi alanı Null ise bir aktarımı üzerinde kayıt denetimi, MFC dizin değerini 0 olarak ayarlar. Bir aktarımını denetiminden kayıt kümesi için Denetim boş ise veya hiçbir öğe seçili değilse, kayıt kümesi alanı 0 olarak ayarlanır.

ODBC tabanlı sınıflar ile çalışıyorsanız ilk sürümü kullanın. DAO dayalı sınıflar ile çalışıyorsanız dosyanın ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve daha fazla bilgi için DDX [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örnek. Bu örnek için benzer `DDX_FieldCBIndex`.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

##  <a name="ddx_fieldcbstring"></a>  DDX_FieldCBString

`DDX_FieldCBString` İşlevi aktarımını yöneten [CString](../../atl-mfc-shared/reference/cstringt-class.md) birleşik giriş kutusu denetiminde bir kayıt görünümü düzenleme denetiminin arasında veri ve `CString` kayıt görünümü ile ilişkili kayıt alan veri üyesi.

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesne.

*value*<br/>
İlişkili alan veri üyesi başvuru `CRecordset` veya `CDaoRecordset` nesne.

*pRecordset*<br/>
Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesne.

### <a name="remarks"></a>Açıklamalar

Veri denetime kayıt kümesinden taşırken, bu işlev birleşik giriş kutusunda belirtilen dizedeki karakterlerle başlayan ilk satırına geçerli seçimi ayarlar *değer*. Bir kayıt kümesi aktarımı denetlemek için kayıt kümesi alanı Null ise, herhangi bir seçimi birleşik giriş kutusundan kaldırılır ve birleşik giriş kutusunun düzenleme denetiminin ayarlayın boş. Denetim boşsa, alanın veriyorsa üzerindeki bir aktarımı denetiminden kayıt kümesine, kayıt kümesi alanı Null olarak ayarlanır.

ODBC tabanlı sınıflar ile çalışıyorsanız ilk sürümü kullanın. DAO dayalı sınıflar ile çalışıyorsanız dosyanın ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve daha fazla bilgi için DDX [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örnek. Örnek bir çağrı içerdiğine `DDX_FieldCBString`.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdao.h

## <a name="ddx_fieldcbstringexact"></a>  DDX_FieldCBStringExact

`DDX_FieldCBStringExact` İşlevi aktarımını yöneten [CString](../../atl-mfc-shared/reference/cstringt-class.md) birleşik giriş kutusu denetiminde bir kayıt görünümü düzenleme denetiminin arasında veri ve `CString` kayıt görünümü ile ilişkili kayıt alan veri üyesi.

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesne.

*value*<br/>
İlişkili alan veri üyesi başvuru `CRecordset` veya `CDaoRecordset` nesne.

*pRecordset*<br/>
Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesne.

### <a name="remarks"></a>Açıklamalar

Veri denetime kayıt kümesinden taşırken, bu işlev birleşik giriş kutusundaki içinde belirtilen dize ile tam olarak ilk satıra geçerli seçimi ayarlar *değer*. Bir kayıt kümesi aktarımı denetlemek için kayıt kümesi alanı NULL ise, herhangi bir seçimi birleşik giriş kutusundan kaldırılır ve birleşik giriş kutusunun düzenleme kutusuna ayarlamak için boş. Denetim boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanı NULL olarak ayarlandı.

ODBC tabanlı sınıflar ile çalışıyorsanız ilk sürümü kullanın. DAO dayalı sınıflar ile çalışıyorsanız dosyanın ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve daha fazla bilgi için DDX [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örnek. Çağrılar `DDX_FieldCBStringExact` benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdao.h

##  <a name="ddx_fieldcheck"></a>  DDX_FieldCheck

`DDX_FieldCheck` İşlevi aktarımını yöneten **int** arasında bir iletişim kutusu bir onay kutusu denetiminde veri form görünümü veya denetim görünüm nesnesi ve bir **int** iletişim kutusu, form görünümü veya denetim veri üyesi Görünüm nesnesi.

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliği ile ilişkilendirilmiş onay kutusu denetimi kaynak kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeninin bir başvuru.

*pRecordset*<br/>
Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesne.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_FieldCheck` çağrıldığında *değer* onay kutusu denetimi, geçerli durumuna ayarlanır veya denetimin durumunu ayarlamak *değer*aktarımı yönüne bağlı olarak.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdao.h

##  <a name="ddx_fieldlbindex"></a>  DDX_FieldLBIndex

`DDX_FieldLBIndex` İşlevi bir liste kutusu denetimini kayıt görünümü'nde seçilen öğenin dizini eşitler ve **int** kayıt görünümü ile ilişkili kayıt alan veri üyesi.

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesne.

*Dizin*<br/>
İlişkili alan veri üyesi başvuru `CRecordset` veya `CDaoRecordset` nesne.

*pRecordset*<br/>
Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesne.

### <a name="remarks"></a>Açıklamalar

Veri denetime kayıt kümesinden taşırken, bu işlev belirtilen değere göre denetiminde seçimi ayarlar *dizin*. Kayıt kümesi alanı Null ise bir aktarımı üzerinde kayıt denetimi, MFC dizin değerini 0 olarak ayarlar. Denetim boşsa, üzerindeki bir aktarımı denetiminden kayıt kümesine, kayıt kümesi alanı 0 olarak ayarlanır.

ODBC tabanlı sınıflar ile çalışıyorsanız ilk sürümü kullanın. DAO dayalı sınıflar ile çalışıyorsanız dosyanın ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve daha fazla bilgi için DDX [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örnek.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdao.h

##  <a name="ddx_fieldlbstring"></a>  DDX_FieldLBString

`DDX_FieldLBString` Kayıt bir görünümdeki bir liste kutusu denetimini oluşan geçerli seçimi kopyalar bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) kayıt görünümü ile ilişkili kayıt alan veri üyesi.

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesne.

*value*<br/>
İlişkili alan veri üyesi başvuru `CRecordset` veya `CDaoRecordset` nesne.

*pRecordset*<br/>
Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesne.

### <a name="remarks"></a>Açıklamalar

Ters yönde, bu işlev tarafından belirtilen dizedeki karakterlerle başlayan ilk satıra liste kutusunda geçerli seçimi ayarlar *değer*. Kayıt kümesi alanı Null ise bir aktarımı üzerinde kayıt denetlemek için liste kutusundan herhangi bir seçimi kaldırılır. Denetim boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanı Null olarak ayarlandı.

ODBC tabanlı sınıflar ile çalışıyorsanız ilk sürümü kullanın. DAO dayalı sınıflar ile çalışıyorsanız dosyanın ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve daha fazla bilgi için DDX [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örnek. Çağrılar `DDX_FieldLBString` benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdao.h

##  <a name="ddx_fieldlbstringexact"></a>  DDX_FieldLBStringExact

`DDX_FieldLBStringExact` İşlevi, kaydı bir görünümdeki bir liste kutusu denetimini oluşan geçerli seçimi kopyalar bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) kayıt görünümü ile ilişkili kayıt alan veri üyesi.

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesne.

*value*<br/>
İlişkili alan veri üyesi başvuru `CRecordset` veya `CDaoRecordset` nesne.

*pRecordset*<br/>
Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesne.

### <a name="remarks"></a>Açıklamalar

Liste kutusunda içinde belirtilen dize ile tam olarak ilk satıra ters yönde, bu işlev geçerli seçimi ayarlar *değer*. Kayıt kümesi alanı Null ise bir aktarımı üzerinde kayıt denetlemek için liste kutusundan herhangi bir seçimi kaldırılır. Denetim boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanı Null olarak ayarlandı.

ODBC tabanlı sınıflar ile çalışıyorsanız ilk sürümü kullanın. DAO dayalı sınıflar ile çalışıyorsanız dosyanın ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve daha fazla bilgi için DDX [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örnek. Çağrılar `DDX_FieldLBStringExact` benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdao.h

##  <a name="ddx_fieldradio"></a>  DDX_FieldRadio

`DDX_FieldRadio` İşlevi sıfır tabanlı ilişkilendirir **int** üye değişkeni şu anda seçili radyo düğmesinin bir grup radyo düğmeleri kayıt görünümü ile kayıt görünümünün kümesi.

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
İlk kimliği bitişik radyo düğmesi denetimleri (WS_GROUP stiliyle) grubu içindeki [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesne.

*value*<br/>
İlişkili alan veri üyesi başvuru `CRecordset` veya `CDaoRecordset` nesne.

*pRecordset*<br/>
Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesne.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi alanı görünüme aktarırken bu işlevi etkinleştirir *n.* radyo düğmesini (sıfır tabanlı) ve diğer düğmeleri devre dışı bırakır. Ters yönde, bu işlev şu anda (işaretli üzerinde) radyo düğmesi sıra sayısı kayıt kümesi alanı ayarlar. Kayıt kümesi alanı Null ise bir aktarımı üzerinde kayıt denetlemek için hiçbir düğmesi seçilir. Hiçbir denetim seçili alan veriyorsa bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanı Null olarak ayarlanır.

ODBC tabanlı sınıflar ile çalışıyorsanız ilk sürümü kullanın. DAO dayalı sınıflar ile çalışıyorsanız dosyanın ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve daha fazla bilgi için DDX [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örnek. Çağrılar `DDX_FieldRadio` benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdao.h

##  <a name="ddx_fieldscroll"></a>  DDX_FieldScroll

`DDX_FieldScroll` İşlevi kayıt görünümü kaydırma çubuğu denetimi kaydırma konumunu eşitler ve **int** kayıt görünümü ile (veya seçtiğiniz için eşlemek için hangi tamsayı değişkeni) ilişkili kümesinin alan veri üyesi .

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
İlk kimliği bitişik radyo düğmesi denetimleri (WS_GROUP stiliyle) grubu içindeki [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesne.

*value*<br/>
İlişkili alan veri üyesi başvuru `CRecordset` veya `CDaoRecordset` nesne.

*pRecordset*<br/>
Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlev kaydırma çubuğu denetimi kaydırma konumunu veri denetime kayıt kümesinden taşırken, belirtilen değere ayarlar. *değer*. Kayıt kümesi alanı Null ise bir aktarımı üzerinde kayıt denetlemek için kaydırma çubuğu denetimi 0 olarak ayarlanır. Denetim boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt alanının değeri 0'dır.

ODBC tabanlı sınıflar ile çalışıyorsanız ilk sürümü kullanın. DAO dayalı sınıflar ile çalışıyorsanız dosyanın ikinci sürümü kullanın.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve daha fazla bilgi için DDX [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örnek. Çağrılar `DDX_FieldScroll` benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdao.h

  ## <a name="ddx_fieldslider"></a>  DDX_FieldSlider
`DDX_FieldSlider` İşlevi kayıt görünümü bir kaydırıcı denetimi thumb konumunu eşitler ve **int** alan veri üyesi kayıt görünümü ile (veya seçtiğiniz için eşlemek için hangi tamsayı değişkeni) ilişkili bir kayıt kümesi.

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
Bir işaretçi bir [CDataExchange](cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Kaydırıcı denetimi kaynak kimliği.

*value*<br/>
Değiştirilecek değerine bir başvuru. Bu parametre tutan veya kaydırıcı denetiminin geçerli parmak konumu ayarlamak için kullanılır.

*pRecordset*<br/>
İlişkili bir işaretçiye `CRecordset` veya `CDaoRecordset` ile veri değişimi nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlev kaydırıcıyı konumunu veri kaydırıcısını kayıt kümesinden taşırken, belirtilen değere ayarlar. *değer*. Kayıt kümesi alanı Null ise bir aktarımı üzerinde kayıt denetlemek için kaydırıcı denetiminin konumu 0 olarak ayarlanır. Denetim boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt alanının değeri 0'dır.

`DDX_FieldSlider` yalnızca bir konumu yerine bir aralığı ayarını özellikli kaydırıcı denetimleri ile aralığı bilgi alışverişi değil.

ODBC tabanlı sınıflar ile çalışıyorsanız işlev ilk geçersiz kılmasını kullanın. DAO tabanlı sınıflarıyla ikinci geçersiz kılmasını kullanın.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../dialog-data-exchange-and-validation.md). Örnekler ve daha fazla bilgi için DDX `CRecordView` ve `CDaoRecordView` alanları görmek [kayıt görünümleri](../../data/record-views-mfc-data-access.md). Kaydırıcı denetimleri hakkında daha fazla bilgi için bkz. [CSliderCtrl kullanma](../using-csliderctrl.md).

### <a name="example"></a>Örnek

Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örnek. Çağrılar `DDX_FieldSlider` benzer olacaktır.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

##  <a name="ddx_fieldtext"></a>  DDX_FieldText

`DDX_FieldText` İşlevi aktarımını yöneten **int**, **kısa**, **uzun**, DWORD, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **çift**, **BOOL**, veya **bayt** düzenleme kutusu denetimi alan veri üyeleri bir kayıt kümesi arasında verileri.

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesne.

*value*<br/>
İlişkili alan veri üyesi başvuru `CRecordset` veya `CDaoRecordset` nesne. Değerin veri türü bağımlı olduğu aşırı yüklenmiş sürümlerinin `DDX_FieldText` kullanırsınız.

*pRecordset*<br/>
Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesne. Bu işaretçi sağlayan `DDX_FieldText` algılamak ve Null değerlere ayarlayın.

### <a name="remarks"></a>Açıklamalar

İçin [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesneleri `DDX_FieldText` aktarımını da yönetir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), ve [COleCurrency](../../mfc/reference/colecurrency-class.md) değerleri. Boş bir düzenleme kutusu denetimi, bir Null değeri gösterir. Düzenleme kutusu üzerindeki bir aktarımı kayıt kümesinden denetlemek için kayıt kümesi alanı Null ise ayarlanmış boş. Denetim boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanı Null olarak ayarlandı.

Sürümle [CRecordset](../../mfc/reference/crecordset-class.md) ODBC tabanlı sınıflar ile çalışıyorsanız parametreleri. Sürümle [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) DAO dayalı sınıflar ile çalışıyorsanız parametreleri.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve daha fazla bilgi için DDX [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Örnek

Aşağıdaki `DoDataExchange` için işlev bir [CRecordView](../../mfc/reference/crecordview-class.md) içeren `DDX_FieldText` üç veri türleri için işlevini çağırır: `IDC_COURSELIST` bir birleşik giriş kutusu; diğer iki düzenleme kutuları denetimlerdir. DAO programlama için *m_pSet* parametresi için bir işaretçi, bir [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

[!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](mfc-macros-and-globals.md)
