---
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
ms.openlocfilehash: a23bc489fce00d9ba0be6a3aa71468b469bf54c8
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177410"
---
# <a name="colecurrency-class"></a>Cotacurrency sınıfı

OLE otomasyonunun `CURRENCY` veri türünü kapsüller.

## <a name="syntax"></a>Sözdizimi

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
|[Copapara birimi:: biçim](#format)|Bir `COleCurrency` nesnenin biçimli dize temsilini oluşturur.|
|[Copapara birimi:: GetStatus](#getstatus)|Bu `COleCurrency` nesnenin durumunu (geçerlilik) alır.|
|[Colet para birimi::P koruması](#parsecurrency)|Bir dizeden bir para BIRIMI değeri okur ve değerini `COleCurrency`ayarlar.|
|[Copapara birimi:: SetCurrency](#setcurrency)|Bu `COleCurrency` nesnenin değerini ayarlar.|
|[Copapara birimi:: SetStatus](#setstatus)|Bu `COleCurrency` nesne için durumu (geçerlilik) ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Bir `COleCurrency` değeri kopyalar.|
|[işleç +,-](#operator_plus_minus)|`COleCurrency` Değerlerin işaretini ekler, çıkarır ve değiştirir.|
|[işleç + =,-=](#operator_plus_minus_eq)|`COleCurrency` Bu`COleCurrency` nesneden bir değer ekler ve çıkartır.|
|[işleç */](#operator_star)|Bir `COleCurrency` değeri tamsayı değerle ölçeklendirir.|
|[* =,/= işleci](#operator_star_div_eq)|Bu `COleCurrency` değeri bir tamsayı değeriyle ölçeklendirir.|
|[işleç < <](#operator_stream)|Veya `COleCurrency` `CArchive` için birdeğerverir.`CDumpContext`|
|[işleç > >](#operator_stream)|`COleCurrency` Öğesinden`CArchive`bir nesne girişler.|
|[Operatör para BIRIMI](#operator_currency)|Bir `COleCurrency` değeri para birimine dönüştürür.|
|[operator = =, <, < =, vb.](#colecurrency_relational_operators)|İki `COleCurrency` değeri karşılaştırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Colet para birimi:: m_cur](#m_cur)|Bu `COleCurrency` nesne için temeldeki para birimini içerir.|
|[Colet para birimi:: m_status](#m_status)|Bu `COleCurrency` nesnenin durumunu içerir.|

## <a name="remarks"></a>Açıklamalar

`COleCurrency`taban sınıfına sahip değildir.

PARA BIRIMI, 10.000 ile ölçeklendirilmiş bir 8 baytlık, iki adet-tamamlayıcı tamsayı değeri olarak uygulanır. Bu, ondalık noktanın solunda 15 basamakla sabit noktalı bir sayı ve sağına 4 basamak verir. PARA BIRIMI veri türü, parayla ilgili hesaplamalar veya doğruluk önemli olduğunda herhangi bir sabit noktalı hesaplama için son derece kullanışlıdır. OLE otomasyonunun `VARIANT` veri türü için olası türlerden biridir.

`COleCurrency`Ayrıca, bu sabit noktalı tür için bazı temel aritmetik işlemleri uygular. Desteklenen işlemler, sabit noktalı hesaplamalar sırasında oluşan yuvarlama hatalarının denetlenmesi için seçilmiştir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`COleCurrency`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

##  <a name="colecurrency"></a>Copapara birimi:: Cotapara birimi

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
Yeni `COleCurrency` nesneye kopyalanacak bir para birimi değeri.

*curSrc*<br/>
`COleCurrency` Yeni`COleCurrency` nesneye Kopyalanacak varolan bir nesne.

*varSrc*<br/>
Bir para `VARIANT` birimi değerine (VT_CY) `COleVariant` dönüştürülecek ve yeni `COleCurrency` nesneye kopyalanabilecek mevcut bir veri yapısı (muhtemelen bir nesne).

*nunits*, *nFractionalUnits* yeni `COleCurrency` nesneye kopyalanacak değerin birim ve kesirli kısmını (1/10000 ' de) gösterir.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuların hepsi, belirtilen değere `COleCurrency` başlatılan yeni nesneler oluşturur. Bu oluşturucuların her biri için kısa bir açıklama aşağıda verilmiştir. Aksi belirtilmediği takdirde, yeni `COleCurrency` öğenin durumu geçerli olarak ayarlanır.

- Cotacurrency (), 0 `COleCurrency` (sıfır) olarak başlatılan bir nesne oluşturur.

- Copacurrency (`cySrc`), bir `COleCurrency` [para birimi](/windows/win32/api/wtypes/ns-wtypes-cy) değerinden bir nesne oluşturur.

- Copacurrency (`curSrc`) varolan `COleCurrency` bir `COleCurrency` nesneden bir nesne oluşturur. Yeni nesne, kaynak nesneyle aynı duruma sahip.

- Copacurrency (`varSrc`) bir `COleCurrency` nesne oluşturur. Bir [değişken](/windows/win32/api/oaidl/ns-oaidl-variant) yapısını veya `COleVariant` nesneyi para birimi (VT_CY) değerine dönüştürmeye çalışır. Bu dönüştürme başarılı olursa, dönüştürülmüş değer yeni `COleCurrency` nesneye kopyalanır. Değilse, `COleCurrency` nesnenin değeri sıfır (0) ve durumu geçersiz olarak ayarlanır.

- `COleCurrency(`belirtilen sayısal`, `bileşenlerden`) Constructs a `nunits nFractionalUnits cotacurrency ' nesnesi. Kesir bölümünün mutlak değeri 10.000 ' den büyükse, birimlere uygun ayarlama yapılır. Birimler ve kesir bölümünün imzalanmış uzun değerlerle belirtilir.

Daha fazla bilgi için Windows SDK [para birimine](/windows/win32/api/wtypes/ns-wtypes-cy) ve [Varyant](/windows/win32/api/oaidl/ns-oaidl-variant) girişlerine bakın.

### <a name="example"></a>Örnek

Aşağıdaki örneklerde, sıfır parametresi ve iki parametreli oluşturucuların etkileri gösterilmektedir:

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

##  <a name="format"></a>Copapara birimi:: biçim

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

Biçimlendirilen `CString` para birimi değerini içeren bir.

### <a name="remarks"></a>Açıklamalar

Yerel dil belirtimlerini (yerel kimlik kimlikleri) kullanarak değeri biçimlendirir. Döndürülen değere bir para birimi simgesi dahil değildir. Bu `COleCurrency` nesnenin durumu null ise, dönüş değeri boş bir dizedir. Durum geçersizse, döndürülen dize IDS_INVALID_CURRENCY dize kaynağı tarafından belirtilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

##  <a name="getstatus"></a>Copapara birimi:: GetStatus

Belirli `COleCurrency` bir nesnenin durumunu (geçerlilik) almak için bu üye işlevi çağırın.

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleCurrency` değerin durumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri, `COleCurrency` sınıfı içinde tanımlanan, `CurrencyStatus` numaralandırılmış tür tarafından tanımlanır.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

  - `COleCurrency::valid`Bu `COleCurrency` nesnenin geçerli olduğunu gösterir.

  - `COleCurrency::invalid`Bu `COleCurrency` nesnenin geçersiz olduğunu gösterir; diğer bir deyişle, değeri yanlış olabilir.

  - `COleCurrency::null`Bu `COleCurrency` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlanmadığını gösterir. (Bu, "değer olmadan", C++ null değerinin aksine, veritabanı "null" değeridir.)

Bir `COleCurrency` nesnenin durumu aşağıdaki durumlarda geçersizdir:

- Değeri bir değişken veya `COleVariant` bir para birimi değerine dönüştürülemeyen bir değerden ayarlandıysa.

- Bu nesne, aritmetik atama işlemi sırasında bir taşma veya yetersiz yer içeriyorsa (örneğin `+=` veya **\* =** ).

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

##  <a name="m_cur"></a>Colet para birimi:: m_cur

Bu`COleCurrency` nesne için temeldeki [para birimi](/windows/win32/api/wtypes/ns-wtypes-cy) yapısı.

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  Bu işlevin döndürdüğü işaretçinin eriştiği `CURRENCY` yapıda değeri değiştirmek, bu `COleCurrency` nesnenin değerini değiştirecek. Bu `COleCurrency` nesnenin durumunu değiştirmez.

Daha fazla bilgi için Windows SDK [para birimi](/windows/win32/api/wtypes/ns-wtypes-cy) girdisine bakın.

##  <a name="m_status"></a>Colet para birimi:: m_status

Bu veri üyesinin türü, `CurrencyStatus` `COleCurrency` sınıfı içinde tanımlanan, numaralandırılmış türüdür.

```
enum CurrencyStatus{
    valid = 0,
    invalid = 1,
    null = 2,
};
```

### <a name="remarks"></a>Açıklamalar

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleCurrency::valid`Bu `COleCurrency` nesnenin geçerli olduğunu gösterir.

- `COleCurrency::invalid`Bu `COleCurrency` nesnenin geçersiz olduğunu gösterir; diğer bir deyişle, değeri yanlış olabilir.

- `COleCurrency::null`Bu `COleCurrency` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlanmadığını gösterir. (Bu, "değer olmadan", C++ null değerinin aksine, veritabanı "null" değeridir.)

Bir `COleCurrency` nesnenin durumu aşağıdaki durumlarda geçersizdir:

- Değeri bir değişken veya `COleVariant` bir para birimi değerine dönüştürülemeyen bir değerden ayarlandıysa.

- Bu nesne, aritmetik atama işlemi sırasında bir taşma veya yetersiz yer içeriyorsa (örneğin `+=` veya **\* =** ).

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
>  Bu veri üyesi gelişmiş programlama durumlarına yöneliktir. [GetStatus](#getstatus) ve [SetStatus](#setstatus)satır içi üye işlevlerini kullanmanız gerekir. Bu `SetStatus` veri üyesini açıkça ayarlamayla ilgili daha fazla uyarı için bkz.

##  <a name="operator_eq"></a>COleCurrency:: operator =

Bu aşırı yüklenmiş atama işleçleri, kaynak para birimi değerini bu `COleCurrency` nesneye kopyalar.

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>Açıklamalar

Her işlecin kısa bir açıklaması aşağıdadır:

- **operator = (** `cySrc` `COleCurrency` )`CURRENCY` değer nesneye kopyalanır ve durumu geçerli olarak ayarlanır.

- **operator = (** `curSrc` **)** işlenenin değeri ve durumu, varolan `COleCurrency` bir nesne bu `COleCurrency` nesneye kopyalanır.

- **operator = (** *varSrc* **)** Değer (veya [COleVariant](../../mfc/reference/colevariant-class.md) nesnesi) bir para birimine ( `VT_CY`) dönüştürme `COleCurrency` başarılı olursa, dönüştürülen değer bu nesneye kopyalanır ve durumu geçerli olarak ayarlanır. `VARIANT` Dönüştürme başarılı olmazsa, `COleCurrency` nesnenin değeri 0 olarak ve durumu geçersiz olarak ayarlanır.

Daha fazla bilgi için Windows SDK [para birimine](/windows/win32/api/wtypes/ns-wtypes-cy) ve [Varyant](/windows/win32/api/oaidl/ns-oaidl-variant) girişlerine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

##  <a name="operator_plus_minus"></a>COleCurrency:: operator +,-

Bu işleçler, birbirlerine ve bunlardan iki `COleCurrency` değer ekleyip çıkartabilir ve bir `COleCurrency` değerin işaretini değiştirmenize olanak sağlar.

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>Açıklamalar

İşlenenden biri null ise, sonuçta elde edilen `COleCurrency` değerin durumu null olur.

Aritmetik işlem taşarsa, sonuçta elde edilen `COleCurrency` değer geçersizdir.

İşlenen geçersiz ve diğeri null değilse, sonuçta elde edilen `COleCurrency` değerin durumu geçersizdir.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

##  <a name="operator_plus_minus_eq"></a>COleCurrency:: operator + =,-=

`COleCurrency` Bu`COleCurrency` nesneye ve öğesinden bir değer eklemenize ve çıkartabilir izin verir.

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>Açıklamalar

İşlenenden biri null ise, bu `COleCurrency` nesnenin durumu null olarak ayarlanır.

Aritmetik işlem taşarsa, bu `COleCurrency` nesnenin durumu geçersiz olarak ayarlanır.

İşlenenden biri geçersiz ve diğeri null değilse, bu `COleCurrency` nesnenin durumu geçersiz olarak ayarlanır.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

##  <a name="operator_star"></a>COleCurrency:: operator \* ve/

Bir `COleCurrency` değeri tamsayı değer ile ölçeklendirmenize izin verir.

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>Açıklamalar

İşlenen null ise, sonuçta elde edilen `COleCurrency` değerin durumu null olur. `COleCurrency`

Aritmetik işlem, veya daha fazla akışa taşarsa, sonuçta elde edilen `COleCurrency` değerin durumu geçersizdir.

İşlenen geçersizse, elde edilen `COleCurrency` değerin durumu geçersiz olur. `COleCurrency`

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

##  <a name="operator_star_div_eq"></a>COleCurrency:: operator \*=,/=

Bu `COleCurrency` değeri bir integral değerle ölçeklendirmenize izin verir.

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>Açıklamalar

İşlenen null ise, bu `COleCurrency` nesnenin durumu null olarak ayarlanır. `COleCurrency`

Aritmetik işlem taşarsa, bu `COleCurrency` nesnenin durumu geçersiz olarak ayarlanır.

İşlenen geçersizse, bu `COleCurrency` nesnenin durumu geçersiz olarak ayarlanır. `COleCurrency`

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

##  <a name="operator_stream"></a>COleCurrency:: işleci &lt;, &lt;&gt;&gt;

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

##  <a name="operator_currency"></a>COleCurrency:: operator para BIRIMI

Değeri bu `CURRENCY` `COleCurrency` nesneden kopyalanmış olan bir yapıyı döndürür.

```
operator CURRENCY() const;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="parsecurrency"></a>Colet para birimi::P koruması

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

##  <a name="colecurrency_relational_operators"></a>Copapara birimi Ilişkisel Işleçleri

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
>  Bir işlenenin durumu null ya da geçersiz ise **<** sıralama işlemlerinin **>** ( **>=** , **\< =** ,,) dönüş değeri tanımsızdır. Eşitlik işleçleri ( `==`, `!=`) işlenenlerin durumunu göz önünde bulundurun.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

##  <a name="setcurrency"></a>Copapara birimi:: SetCurrency

Bu `COleCurrency` nesnenin birimlerini ve kesirli kısmını ayarlamak için bu üye işlevi çağırın.

```
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>Parametreler

*nunits*, *nFractionalUnits* bu `COleCurrency` nesneye kopyalanacak değerin birim ve kesirli kısmını (1/10000 ' de) gösterir.

### <a name="remarks"></a>Açıklamalar

Kesir bölümünün mutlak değeri 10.000 ' den büyükse, aşağıdaki örneklerde üçüncü bölümünde gösterildiği gibi, birimlerde uygun ayarlama yapılır.

Birimler ve kesir bölümünün imzalanmış uzun değerlerle belirtilir. Aşağıdaki örneklerden dördüncü, parametrelerin farklı işaretleri olduğunda ne olacağını gösterir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

##  <a name="setstatus"></a>Copapara birimi:: SetStatus

Bu `COleCurrency` nesnenin durumunu (geçerlilik) ayarlamak için bu üye işlevi çağırın.

```
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>Parametreler

*status*<br/>
Bu `COleCurrency` nesnenin yeni durumu.

### <a name="remarks"></a>Açıklamalar

*Durum* parametresi değeri, `CurrencyStatus` `COleCurrency` sınıfı içinde tanımlanan, numaralandırılmış tür tarafından tanımlanır.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleCurrency::valid`Bu `COleCurrency` nesnenin geçerli olduğunu gösterir.

- `COleCurrency::invalid`Bu `COleCurrency` nesnenin geçersiz olduğunu gösterir; diğer bir deyişle, değeri yanlış olabilir.

- `COleCurrency::null`Bu `COleCurrency` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlanmadığını gösterir. (Bu, "değer olmadan", C++ null değerinin aksine, veritabanı "null" değeridir.)

> [!CAUTION]
>  Bu işlev, gelişmiş programlama durumları içindir. Bu işlev, bu nesnedeki verileri değiştirmez. En sık, durumu null veya geçersiz olarak ayarlamak için kullanılır. Atama işlecinin ( [operator =](#operator_eq)) ve [SetCurrency](#setcurrency) 'ın durumu kaynak değer (ler) temelinde nesnenin olarak ayarlandığını unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleVariant Sınıfı](../../mfc/reference/colevariant-class.md)
