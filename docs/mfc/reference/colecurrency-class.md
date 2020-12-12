---
description: 'Daha fazla bilgi edinin: Cotacurrency sınıfı'
title: Cotacurrency sınıfı
ms.date: 08/29/2019
f1_keywords:
- COleCurrency
- AFXDISP/COleCurrency
- AFXDISP/COleCurrency::COleCurrency
- AFXDISP/COleCurrency::Format
- AFXDISP/COleCurrency::GetStatus
- AFXDISP/COleCurrency::ParseCurrency
- AFXDISP/COleCurrency::SetCurrency
- AFXDISP/COleCurrency::SetStatus
- AFXDISP/COleCurrency::m_cur
- AFXDISP/COleCurrency::m_status
helpviewer_keywords:
- COleCurrency [MFC], COleCurrency
- COleCurrency [MFC], Format
- COleCurrency [MFC], GetStatus
- COleCurrency [MFC], ParseCurrency
- COleCurrency [MFC], SetCurrency
- COleCurrency [MFC], SetStatus
- COleCurrency [MFC], m_cur
- COleCurrency [MFC], m_status
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
ms.openlocfilehash: 4a877d455de3f4254711a752bc422bb1cbdcd8c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227396"
---
# <a name="colecurrency-class"></a>Cotacurrency sınıfı

`CURRENCY`OLE otomasyonunun veri türünü kapsüller.

## <a name="syntax"></a>Syntax

```
class COleCurrency
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Copapara birimi:: Cotapara birimi](#colecurrency)|Bir `COleCurrency` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Copapara birimi:: biçim](#format)|Bir nesnenin biçimli dize temsilini oluşturur `COleCurrency` .|
|[Copapara birimi:: GetStatus](#getstatus)|Bu nesnenin durumunu (geçerlilik) alır `COleCurrency` .|
|[Colet para birimi::P koruması](#parsecurrency)|Bir dizeden bir para BIRIMI değeri okur ve değerini ayarlar `COleCurrency` .|
|[Copapara birimi:: SetCurrency](#setcurrency)|Bu nesnenin değerini ayarlar `COleCurrency` .|
|[Copapara birimi:: SetStatus](#setstatus)|Bu nesne için durumu (geçerlilik) ayarlar `COleCurrency` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Bir `COleCurrency` değeri kopyalar.|
|[işleç +,-](#operator_plus_minus)|Değerlerin işaretini ekler, çıkarır ve değiştirir `COleCurrency` .|
|[işleç + =,-=](#operator_plus_minus_eq)|`COleCurrency`Bu nesneden bir değer ekler ve çıkartır `COleCurrency` .|
|[işleç */](#operator_star)|Bir `COleCurrency` değeri tamsayı değerle ölçeklendirir.|
|[* =,/= işleci](#operator_star_div_eq)|Bu `COleCurrency` değeri bir tamsayı değeriyle ölçeklendirir.|
|[işleç <<](#operator_stream)|`COleCurrency`Veya için bir değer `CArchive` verir `CDumpContext` .|
|[işleç >>](#operator_stream)|Öğesinden bir `COleCurrency` nesne girişler `CArchive` .|
|[Operatör para BIRIMI](#operator_currency)|Bir `COleCurrency` DEĞERI para birimine dönüştürür.|
|[operator = =, <, <=, vb.](#colecurrency_relational_operators)|İki `COleCurrency` değeri karşılaştırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Colet para birimi:: m_cur](#m_cur)|Bu nesne için temeldeki para BIRIMINI içerir `COleCurrency` .|
|[Colet para birimi:: m_status](#m_status)|Bu nesnenin durumunu içerir `COleCurrency` .|

## <a name="remarks"></a>Açıklamalar

`COleCurrency` taban sınıfına sahip değildir.

PARA BIRIMI, 10.000 ile ölçeklendirilmiş bir 8 baytlık, iki adet-tamamlayıcı tamsayı değeri olarak uygulanır. Bu, ondalık noktanın solunda 15 basamakla sabit noktalı bir sayı ve sağına 4 basamak verir. PARA BIRIMI veri türü, parayla ilgili hesaplamalar veya doğruluk önemli olduğunda herhangi bir sabit noktalı hesaplama için son derece kullanışlıdır. `VARIANT`OLE otomasyonunun veri türü için olası türlerden biridir.

`COleCurrency` Ayrıca, bu sabit noktalı tür için bazı temel aritmetik işlemleri uygular. Desteklenen işlemler, sabit noktalı hesaplamalar sırasında oluşan yuvarlama hatalarının denetlenmesi için seçilmiştir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`COleCurrency`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="colecurrencycolecurrency"></a><a name="colecurrency"></a> Copapara birimi:: Cotapara birimi

Bir `COleCurrency` nesnesi oluşturur.

```
COleCurrency();
COleCurrency(CURRENCY cySrc);
COleCurrency(const COleCurrency& curSrc);
COleCurrency(const VARIANT& varSrc);

COleCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>Parametreler

*cySrc*<br/>
Yeni nesneye kopyalanacak bir para BIRIMI değeri `COleCurrency` .

*curSrc*<br/>
`COleCurrency`Yeni nesneye Kopyalanacak varolan bir nesne `COleCurrency` .

*varSrc*<br/>
`VARIANT` `COleVariant` Bir para birimi değerine (VT_CY) dönüştürülecek ve yeni nesneye kopyalanabilecek mevcut bir veri yapısı (muhtemelen bir nesne) `COleCurrency` .

*nunits*, *nFractionalUnits* yeni nesneye kopyalanacak değerin birim ve kesirli kısmını (1/10000 ' de) gösterir `COleCurrency` .

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuların hepsi `COleCurrency` , belirtilen değere başlatılan yeni nesneler oluşturur. Bu oluşturucuların her biri için kısa bir açıklama aşağıda verilmiştir. Aksi belirtilmediği takdirde, yeni `COleCurrency` öğenin durumu geçerli olarak ayarlanır.

- Cotacurrency (), `COleCurrency` 0 (sıfır) olarak başlatılan bir nesne oluşturur.

- Copacurrency ( `cySrc` ), `COleCurrency` bir [para birimi](/windows/win32/api/wtypes/ns-wtypes-cy-r1) değerinden bir nesne oluşturur.

- Copacurrency ( `curSrc` ) varolan bir `COleCurrency` nesneden bir nesne oluşturur `COleCurrency` . Yeni nesne, kaynak nesneyle aynı duruma sahip.

- Copacurrency ( `varSrc` ) bir `COleCurrency` nesne oluşturur. Bir [değişken](/windows/win32/api/oaidl/ns-oaidl-variant) yapısını veya `COleVariant` nesneyi para birimi (VT_CY) değerine dönüştürmeye çalışır. Bu dönüştürme başarılı olursa, dönüştürülmüş değer yeni `COleCurrency` nesneye kopyalanır. Değilse, `COleCurrency` nesnenin değeri sıfır (0) ve durumu geçersiz olarak ayarlanır.

- Copapara birimi ( `nUnits` , `nFractionalUnits` ) `COleCurrency` belirtilen sayısal bileşenlerden bir nesne oluşturur. Kesir bölümünün mutlak değeri 10.000 ' den büyükse, birimlere uygun ayarlama yapılır. Birimler ve kesir bölümünün imzalanmış uzun değerlerle belirtilir.

Daha fazla bilgi için Windows SDK [para birimine](/windows/win32/api/wtypes/ns-wtypes-cy-r1) ve [Varyant](/windows/win32/api/oaidl/ns-oaidl-variant) girişlerine bakın.

### <a name="example"></a>Örnek

Aşağıdaki örneklerde, sıfır parametresi ve iki parametreli oluşturucuların etkileri gösterilmektedir:

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

## <a name="colecurrencyformat"></a><a name="format"></a> Copapara birimi:: biçim

Para birimi değerinin biçimli bir gösterimini oluşturmak için bu üye işlevini çağırın.

```
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const;
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
Yerel ayar ayarlarına yönelik bayrakları gösterir. Yalnızca aşağıdaki bayrak para birimiyle ilgilidir:

- LOCALE_NOUSEROVERRIDE özel Kullanıcı ayarları yerine sistem varsayılan yerel ayar ayarlarını kullanın.

*lcid*<br/>
Dönüştürme için kullanılacak yerel ayar KIMLIĞINI gösterir.

### <a name="return-value"></a>Dönüş Değeri

`CString`Biçimlendirilen para birimi değerini içeren bir.

### <a name="remarks"></a>Açıklamalar

Yerel dil belirtimlerini (yerel kimlik kimlikleri) kullanarak değeri biçimlendirir. Döndürülen değere bir para birimi simgesi dahil değildir. Bu `COleCurrency` nesnenin durumu null ise, dönüş değeri boş bir dizedir. Durum geçersiz ise, dönüş dizesi IDS_INVALID_CURRENCY dize kaynağı tarafından belirtilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

## <a name="colecurrencygetstatus"></a><a name="getstatus"></a> Copapara birimi:: GetStatus

Belirli bir nesnenin durumunu (geçerlilik) almak için bu üye işlevi çağırın `COleCurrency` .

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu değerin durumunu döndürür `COleCurrency` .

### <a name="remarks"></a>Açıklamalar

Dönüş değeri, `CurrencyStatus` sınıfı içinde tanımlanan, numaralandırılmış tür tarafından tanımlanır `COleCurrency` .

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleCurrency::valid` Bu `COleCurrency` nesnenin geçerli olduğunu gösterir.

- `COleCurrency::invalid` Bu `COleCurrency` nesnenin geçersiz olduğunu gösterir; diğer bir deyişle, değeri yanlış olabilir.

- `COleCurrency::null` Bu `COleCurrency` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlanmadığını gösterir. (Bu, C++ NULL değerinin aksine "hiçbir değer olmadan" veritabanı açısından "null" değeridir.)

Bir `COleCurrency` nesnenin durumu aşağıdaki durumlarda geçersizdir:

- Değeri bir DEĞIŞKEN veya `COleVariant` bir para birimi değerine dönüştürülemeyen bir değerden ayarlandıysa.

- Bu nesne, aritmetik atama işlemi sırasında bir taşma veya yetersiz yer içeriyorsa (örneğin veya) `+=` **\*=** .

- Bu nesneye geçersiz bir değer atanmışsa.

- Bu nesnenin durumu, [SetStatus](#setstatus)kullanılarak açıkça geçersiz olarak ayarlandıysa.

Durumu geçersiz olarak ayarlayaetkileyebilecek işlemler hakkında daha fazla bilgi için aşağıdaki üye işlevlere bakın:

- [Colet para birimi](#colecurrency)

- [işleç =](#operator_eq)

- [işleç +-](#operator_plus_minus)

- [+ = ve-= işleci](#operator_plus_minus_eq)

- [işleç */](#operator_star)

- [* = ve/= işleci](#operator_star_div_eq)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]

## <a name="colecurrencym_cur"></a><a name="m_cur"></a> Colet para birimi:: m_cur

Bu nesne için temeldeki [para birimi](/windows/win32/api/wtypes/ns-wtypes-cy-r1) yapısı `COleCurrency` .

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> `CURRENCY`Bu işlevin döndürdüğü işaretçinin eriştiği yapıda değeri değiştirmek, bu nesnenin değerini değiştirecek `COleCurrency` . Bu nesnenin durumunu değiştirmez `COleCurrency` .

Daha fazla bilgi için Windows SDK [para birimi](/windows/win32/api/wtypes/ns-wtypes-cy-r1) girdisine bakın.

## <a name="colecurrencym_status"></a><a name="m_status"></a> Colet para birimi:: m_status

Bu veri üyesinin türü, `CurrencyStatus` sınıfı içinde tanımlanan, numaralandırılmış türüdür `COleCurrency` .

```
enum CurrencyStatus{
    valid = 0,
    invalid = 1,
    null = 2,
};
```

### <a name="remarks"></a>Açıklamalar

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleCurrency::valid` Bu `COleCurrency` nesnenin geçerli olduğunu gösterir.

- `COleCurrency::invalid` Bu `COleCurrency` nesnenin geçersiz olduğunu gösterir; diğer bir deyişle, değeri yanlış olabilir.

- `COleCurrency::null` Bu `COleCurrency` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlanmadığını gösterir. (Bu, C++ NULL değerinin aksine "hiçbir değer olmadan" veritabanı açısından "null" değeridir.)

Bir `COleCurrency` nesnenin durumu aşağıdaki durumlarda geçersizdir:

- Değeri bir DEĞIŞKEN veya `COleVariant` bir para birimi değerine dönüştürülemeyen bir değerden ayarlandıysa.

- Bu nesne, aritmetik atama işlemi sırasında bir taşma veya yetersiz yer içeriyorsa (örneğin veya) `+=` **\*=** .

- Bu nesneye geçersiz bir değer atanmışsa.

- Bu nesnenin durumu, [SetStatus](#setstatus)kullanılarak açıkça geçersiz olarak ayarlandıysa.

Durumu geçersiz olarak ayarlayaetkileyebilecek işlemler hakkında daha fazla bilgi için aşağıdaki üye işlevlere bakın:

- [Colet para birimi](#colecurrency)

- [işleç =](#operator_eq)

- [işleç +,-](#operator_plus_minus)

- [işleç + =,-=](#operator_plus_minus_eq)

- [işleç */](#operator_star)

- [* =,/= işleci](#operator_star_div_eq)

> [!CAUTION]
> Bu veri üyesi gelişmiş programlama durumlarına yöneliktir. [GetStatus](#getstatus) ve [SetStatus](#setstatus)satır içi üye işlevlerini kullanmanız gerekir. `SetStatus`Bu veri üyesini açıkça ayarlamayla ilgili daha fazla uyarı için bkz..

## <a name="colecurrencyoperator-"></a><a name="operator_eq"></a> COleCurrency:: operator =

Bu aşırı yüklenmiş atama işleçleri, kaynak para birimi değerini bu `COleCurrency` nesneye kopyalar.

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>Açıklamalar

Her işlecin kısa bir açıklaması aşağıdadır:

- **operator = (** `cySrc` **)** `CURRENCY` değer `COleCurrency` nesneye kopyalanır ve durumu geçerli olarak ayarlanır.

- **operator = (** `curSrc` **)** işlenenin değeri ve durumu, varolan bir `COleCurrency` nesne bu `COleCurrency` nesneye kopyalanır.

- **operator = (** *varSrc* **)** `VARIANT` Değer (veya [COleVariant](../../mfc/reference/colevariant-class.md) nesnesi) bir para birimine ( `VT_CY` ) dönüştürme başarılı olursa, dönüştürülen değer bu `COleCurrency` nesneye kopyalanır ve durumu geçerli olarak ayarlanır. Dönüştürme başarılı olmazsa, `COleCurrency` nesnenin değeri 0 olarak ve durumu geçersiz olarak ayarlanır.

Daha fazla bilgi için Windows SDK [para birimine](/windows/win32/api/wtypes/ns-wtypes-cy-r1) ve [Varyant](/windows/win32/api/oaidl/ns-oaidl-variant) girişlerine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

## <a name="colecurrencyoperator---"></a><a name="operator_plus_minus"></a> COleCurrency:: operator +,-

Bu işleçler `COleCurrency` , birbirlerine ve bunlardan iki değer ekleyip çıkartabilir ve bir değerin işaretini değiştirmenize olanak sağlar `COleCurrency` .

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>Açıklamalar

İşlenenden biri null ise, sonuçta elde edilen `COleCurrency` değerin durumu null olur.

Aritmetik işlem taşarsa, sonuçta elde edilen `COleCurrency` değer geçersizdir.

İşlenen geçersiz ve diğeri null değilse, sonuçta elde edilen `COleCurrency` değerin durumu geçersizdir.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

## <a name="colecurrencyoperator---"></a><a name="operator_plus_minus_eq"></a> COleCurrency:: operator + =,-=

`COleCurrency`Bu nesneye ve öğesinden bir değer eklemenize ve çıkartabilir izin verir `COleCurrency` .

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>Açıklamalar

İşlenenden biri null ise, bu `COleCurrency` nesnenin durumu null olarak ayarlanır.

Aritmetik işlem taşarsa, bu `COleCurrency` nesnenin durumu geçersiz olarak ayarlanır.

İşlenenden biri geçersiz ve diğeri null değilse, bu `COleCurrency` nesnenin durumu geçersiz olarak ayarlanır.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

## <a name="colecurrencyoperator--and-"></a><a name="operator_star"></a> COleCurrency:: operator \* ve/

Bir `COleCurrency` değeri tamsayı değer ile ölçeklendirmenize izin verir.

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>Açıklamalar

`COleCurrency`İşlenen null ise, sonuçta elde edilen `COleCurrency` değerin durumu null olur.

Aritmetik işlem, veya daha fazla akışa taşarsa, sonuçta elde edilen `COleCurrency` değerin durumu geçersizdir.

`COleCurrency`İşlenen geçersizse, elde edilen `COleCurrency` değerin durumu geçersiz olur.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

## <a name="colecurrencyoperator--"></a><a name="operator_star_div_eq"></a> COleCurrency:: operator \* =,/=

Bu `COleCurrency` değeri bir integral değerle ölçeklendirmenize izin verir.

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>Açıklamalar

`COleCurrency`İşlenen null ise, bu `COleCurrency` nesnenin durumu null olarak ayarlanır.

Aritmetik işlem taşarsa, bu `COleCurrency` nesnenin durumu geçersiz olarak ayarlanır.

`COleCurrency`İşlenen geçersizse, bu `COleCurrency` nesnenin durumu geçersiz olarak ayarlanır.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

## <a name="colecurrencyoperator-ltlt-gtgt"></a><a name="operator_stream"></a>COleCurrency:: işleci &lt; &lt; ,&gt;&gt;

Tanılama dökümünü ve bir arşive depolamayı destekler.

```
friend CDumpContext& operator<<(
    CDumpContext& dc,
    COleCurrency curSrc);

friend CArchive& operator<<(
    CArchive& ar,
    COleCurrency curSrc);

friend CArchive& operator>>(
    CArchive& ar,
    COleCurrency& curSrc);
```

### <a name="remarks"></a>Açıklamalar

Ayıklama ( **>>** ) işleci bir arşivden yüklemeyi destekler.

## <a name="colecurrencyoperator-currency"></a><a name="operator_currency"></a> COleCurrency:: operator para BIRIMI

`CURRENCY`Değeri bu nesneden kopyalanmış olan bir yapıyı döndürür `COleCurrency` .

```
operator CURRENCY() const;
```

### <a name="remarks"></a>Açıklamalar

## <a name="colecurrencyparsecurrency"></a><a name="parsecurrency"></a> Colet para birimi::P koruması

Bir para birimi değerini okumak üzere bir dizeyi ayrıştırmak için bu üye işlevi çağırın.

```
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT);

throw(CMemoryException*);
throw(COleException*);
```

### <a name="parameters"></a>Parametreler

*lpszCurrency*<br/>
Ayrıştırılacak null ile sonlandırılmış dizeye yönelik bir işaretçi.

*dwFlags*<br/>
Yerel ayar ayarlarına yönelik bayrakları gösterir, muhtemelen şu bayrağa sahiptir:

- LOCALE_NOUSEROVERRIDE özel Kullanıcı ayarları yerine sistem varsayılan yerel ayar ayarlarını kullanın.

*lcid*<br/>
Dönüştürme için kullanılacak yerel ayar KIMLIĞINI gösterir.

### <a name="return-value"></a>Dönüş Değeri

Dize bir para birimi değerine başarıyla dönüştürülürse sıfır dışı, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kaynak dizedeki sayısal olmayan karakterlerin anlamı için yerel dil belirtimleri (yerel ayar kimlikleri) kullanır.

Yerel ayar KIMLIĞI değerleri hakkında bir tartışma için bkz. [birden çok dili destekleme](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages).

Dize bir para birimi değerine başarıyla dönüştürülürse, bu nesnenin değeri bu `COleCurrency` değere ve durumu geçerli olarak ayarlanır.

Dize bir para birimi değerine dönüştürülemiyorsa veya sayısal bir taşma varsa, bu `COleCurrency` nesnenin durumu geçersiz olur.

Dize dönüştürme, bellek ayırma hataları nedeniyle başarısız olduysa, bu işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md)oluşturur. Diğer herhangi bir hata durumunda bu işlev bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]

## <a name="colecurrency-relational-operators"></a><a name="colecurrency_relational_operators"></a> Copapara birimi Ilişkisel Işleçleri

İki para birimi değerini karşılaştırın ve koşul true ise sıfır dışında bir değer döndürür; Aksi takdirde 0.

```
BOOL operator==(const COleCurrency& cur) const;
BOOL operator!=(const COleCurrency& cur) const;
BOOL operator<(const COleCurrency& cur) const;
BOOL operator>(const COleCurrency& cur) const;
BOOL operator<=(const COleCurrency& cur) const;
BOOL operator>=(const COleCurrency& cur) const;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bir **<** **\<=**, **>** **>=** işlenenin durumu null ya da geçersiz ise sıralama işlemlerinin (,,) dönüş değeri tanımsız. Eşitlik işleçleri ( `==` , `!=` ) işlenenlerin durumunu göz önünde bulundurun.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

## <a name="colecurrencysetcurrency"></a><a name="setcurrency"></a> Copapara birimi:: SetCurrency

Bu nesnenin birimlerini ve kesirli kısmını ayarlamak için bu üye işlevi çağırın `COleCurrency` .

```cpp
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>Parametreler

*nunits*, *nFractionalUnits* bu nesneye kopyalanacak değerin birim ve kesirli kısmını (1/10000 ' de) gösterir `COleCurrency` .

### <a name="remarks"></a>Açıklamalar

Kesir bölümünün mutlak değeri 10.000 ' den büyükse, aşağıdaki örneklerde üçüncü bölümünde gösterildiği gibi, birimlerde uygun ayarlama yapılır.

Birimler ve kesir bölümünün imzalanmış uzun değerlerle belirtilir. Aşağıdaki örneklerden dördüncü, parametrelerin farklı işaretleri olduğunda ne olacağını gösterir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

## <a name="colecurrencysetstatus"></a><a name="setstatus"></a> Copapara birimi:: SetStatus

Bu nesnenin durumunu (geçerlilik) ayarlamak için bu üye işlevi çağırın `COleCurrency` .

```cpp
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>Parametreler

*durumlarına*<br/>
Bu nesnenin yeni durumu `COleCurrency` .

### <a name="remarks"></a>Açıklamalar

*Durum* parametresi değeri, `CurrencyStatus` sınıfı içinde tanımlanan, numaralandırılmış tür tarafından tanımlanır `COleCurrency` .

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleCurrency::valid` Bu `COleCurrency` nesnenin geçerli olduğunu gösterir.

- `COleCurrency::invalid` Bu `COleCurrency` nesnenin geçersiz olduğunu gösterir; diğer bir deyişle, değeri yanlış olabilir.

- `COleCurrency::null` Bu `COleCurrency` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlanmadığını gösterir. (Bu, C++ NULL değerinin aksine "hiçbir değer olmadan" veritabanı açısından "null" değeridir.)

> [!CAUTION]
> Bu işlev, gelişmiş programlama durumları içindir. Bu işlev, bu nesnedeki verileri değiştirmez. En sık, durumu null veya geçersiz olarak ayarlamak için kullanılır. Atama işlecinin ( [operator =](#operator_eq)) ve [SetCurrency](#setcurrency) 'ın durumu kaynak değer (ler) temelinde nesnenin olarak ayarlandığını unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Cotavariant sınıfı](../../mfc/reference/colevariant-class.md)
