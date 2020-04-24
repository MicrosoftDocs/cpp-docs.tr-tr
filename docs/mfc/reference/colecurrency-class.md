---
title: COleCurrency Sınıfı
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
ms.openlocfilehash: cc69143101c5d00d4f9a689bd02abdd9596e5b53
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753927"
---
# <a name="colecurrency-class"></a>COleCurrency Sınıfı

OLE otomasyonunun `CURRENCY` veri türünü kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class COleCurrency
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleCurrency::COleCurrency](#colecurrency)|Bir `COleCurrency` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleCurrency::Biçim](#format)|Nesnenin biçimlendirilmiş dize `COleCurrency` temsilini oluşturur.|
|[COleCurrency::GetStatus](#getstatus)|Bu `COleCurrency` nesnenin durumunu (geçerliliğini) alır.|
|[COleCurrency::ParseCurrency](#parsecurrency)|Bir dizeden PARA BIRIMI değerini okur `COleCurrency`ve değerini ayarlar.|
|[COleCurrency::SetCurrency](#setcurrency)|Bu `COleCurrency` nesnenin değerini ayarlar.|
|[COleCurrency::SetStatus](#setstatus)|Bu `COleCurrency` nesnenin durumunu (geçerliliğini) ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Bir `COleCurrency` değeri kopyalar.|
|[işleç +, -](#operator_plus_minus)|`COleCurrency` Değerler işaretini ekler, çıkarır ve değiştirir.|
|[işleç +=, -=](#operator_plus_minus_eq)|Bu `COleCurrency` nesneden bir `COleCurrency` değer ekler ve çıkarır.|
|[işleç */](#operator_star)|Bir `COleCurrency` değeri tamsayı değeriyle ölçeklendirin.|
|[işleç *=, /=](#operator_star_div_eq)|Bu `COleCurrency` değeri tamsayı değeriyle ölçeklendirin.|
|[operatör <<](#operator_stream)|Çıkışlar `COleCurrency` için `CArchive` bir `CDumpContext`değer veya .|
|[operatör >>](#operator_stream)|Bir `COleCurrency` nesneyi `CArchive`.|
|[operatör PARA Bİrİmİ](#operator_currency)|Bir `COleCurrency` değeri PARA Birimine dönüştürür.|
|[işleç ==, <, <=, vb.](#colecurrency_relational_operators)|İki `COleCurrency` değeri karşılaştırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[Para Birimi::m_cur](#m_cur)|Bu `COleCurrency` nesne için temel PARA Birimi içerir.|
|[COleCurrency::m_status](#m_status)|Bu `COleCurrency` nesnenin durumunu içerir.|

## <a name="remarks"></a>Açıklamalar

`COleCurrency`taban sınıfa sahip değildir.

PARA BIRIMI, 10.000 ölçeklenmiş 8 baytlık, iki tamamlayıcı bir tümsedo değeri olarak uygulanır. Bu ondalık noktanın solunda 15 basamak ve sağda 4 basamak olan sabit nokta numarası verir. PARA Birimi veri türü, para içeren hesaplamalar veya doğruluğun önemli olduğu herhangi bir sabit nokta hesaplaması için son derece yararlıdır. OLE otomasyonunun `VARIANT` veri türü için olası türlerden biridir.

`COleCurrency`ayrıca bu sabit nokta türü için bazı temel aritmetik işlemler uygular. Desteklenen işlemler, sabit noktalı hesaplamalar sırasında oluşan yuvarlama hatalarını denetlemek için seçilmiştir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`COleCurrency`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="colecurrencycolecurrency"></a><a name="colecurrency"></a>COleCurrency::COleCurrency

Bir `COleCurrency` nesne inşa eder.

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
Yeni `COleCurrency` nesneye kopyalanacak bir PARA BIRIMI değeri.

*curSrc*<br/>
Varolan `COleCurrency` bir nesne yeni `COleCurrency` nesneye kopyalanacak.

*varSrc*<br/>
Varolan `VARIANT` bir veri `COleVariant` yapısı (büyük olasılıkla bir nesne) para birimi değerine `COleCurrency` dönüştürülecek (VT_CY) ve yeni nesneye kopyalanacak.

*nUnits*, *nFractionalUnits* Yeni `COleCurrency` nesneye kopyalanacak değerin birimlerini ve kesirli kısmını (1/10.000'lerde) gösterir.

### <a name="remarks"></a>Açıklamalar

Tüm bu kurucular, `COleCurrency` belirtilen değere başlalanan yeni nesneler oluşturur. Bu yapıcıların her birinin kısa bir açıklaması aşağıdaki gibidir. Aksi belirtilmedikçe, yeni `COleCurrency` öğenin durumu geçerli olarak ayarlanır.

- COleCurrency() 0 `COleCurrency` (sıfır) olarak başlatılanmış bir nesne yi kurar.

- COleCurrency(`cySrc`) Bir `COleCurrency` [nesneyi PARA BIRIMI](/windows/win32/api/wtypes/ns-wtypes-cy~r1) değerinden inşa eder.

- COleCurrency(`curSrc`) Varolan `COleCurrency` `COleCurrency` bir nesneden bir nesne yi kurar. Yeni nesne kaynak nesneyle aynı duruma sahiptir.

- COleCurrency(`varSrc`) Bir `COleCurrency` nesne yi inşa eder. [Variant](/windows/win32/api/oaidl/ns-oaidl-variant) yapısını veya `COleVariant` nesnesini para birimi (VT_CY) değerine dönüştürmeye çalışır. Bu dönüşüm başarılı olursa, dönüştürülen değer yeni `COleCurrency` nesneye kopyalanır. Değilse, `COleCurrency` nesnenin değeri sıfır (0) ve durumu geçersiz olarak ayarlanır.

- `nUnits`COleCurrency(, `nFractionalUnits`) Belirtilen `COleCurrency` sayısal bileşenlerden bir nesne oluşur. Kesirli parçanın mutlak değeri 10.000'den büyükse, birimleriçin uygun ayarlama yapılır. Birimler ve kesirli kısmı imzalı uzun değerlerle belirtilir unutmayın.

Daha fazla bilgi için Windows SDK'daki [PARA BIRIMI](/windows/win32/api/wtypes/ns-wtypes-cy~r1) ve [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) girişlerine bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnekler, sıfır parametre ve iki parametre oluşturucuların etkilerini gösterir:

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

## <a name="colecurrencyformat"></a><a name="format"></a>COleCurrency::Biçim

Para birimi değerinin biçimlendirilmiş bir temsilini oluşturmak için bu üye işlevi arayın.

```
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const;
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
Yerel ayarlar için bayrakları gösterir. Yalnızca aşağıdaki bayrak para birimiyle ilgilidir:

- LOCALE_NOUSEROVERRIDE Özel kullanıcı ayarları yerine sistemin varsayılan yerel ayarları kullanın.

*lcid*<br/>
Dönüşüm için kullanılacak yerel kimliği gösterir.

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirilmiş para birimi değerini içeren a. `CString`

### <a name="remarks"></a>Açıklamalar

Yerel dil belirtimlerini (yerel iT'ler) kullanarak değeri biçimlendiriyor. Para birimi simgesi döndürülen değere dahil edilmez. Bu `COleCurrency` nesnenin durumu null ise, döndürme değeri boş bir dize. Durum geçersizse, geri dönüş dizesi dize kaynak IDS_INVALID_CURRENCY tarafından belirtilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

## <a name="colecurrencygetstatus"></a><a name="getstatus"></a>COleCurrency::GetStatus

Belirli `COleCurrency` bir nesnenin durumunu (geçerliliğini) almak için bu üye işlevi arayın.

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleCurrency` değerin durumunu döndürür.

### <a name="remarks"></a>Açıklamalar

İade `COleCurrency` değeri, sınıf `CurrencyStatus` içinde tanımlanan numaralandırılmış tür tarafından tanımlanır.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleCurrency::valid`Bu `COleCurrency` nesnenin geçerli olduğunu gösterir.

- `COleCurrency::invalid`Bu `COleCurrency` nesnenin geçersiz olduğunu gösterir; diğer bir gerçek, değeri yanlış olabilir.

- `COleCurrency::null`Bu `COleCurrency` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlandığını gösterir. (Bu, C++ NULL'un aksine veritabanında "değer sahibi olma" anlamında "null"dur.)

Bir `COleCurrency` nesnenin durumu aşağıdaki durumlarda geçersizdir:

- Değeri bir VARYANT'tan veya `COleVariant` para birimi değerine dönüştürülmeyen bir değerden ayarlanırsa.

- Bu nesne, bir aritmetik atama işlemi sırasında bir taşma `+=` ** \* **veya taşma yaşadıysa, örneğin veya .

- Bu nesneye geçersiz bir değer atandıysa.

- Bu nesnenin durumu [SetStatus](#setstatus)kullanarak açıkça geçersiz olarak ayarlanmışsa.

Durumu geçersiz duruma göre ayarlayabilen işlemler hakkında daha fazla bilgi için aşağıdaki üye işlevlere bakın:

- [Colecurrency](#colecurrency)

- [işleç =](#operator_eq)

- [operatör + -](#operator_plus_minus)

- [işleç += ve -=](#operator_plus_minus_eq)

- [operatör * /](#operator_star)

- [işleç *= ve /=](#operator_star_div_eq)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]

## <a name="colecurrencym_cur"></a><a name="m_cur"></a>Para Birimi::m_cur

Bu `COleCurrency` nesne için temel [PARA BIRIMI](/windows/win32/api/wtypes/ns-wtypes-cy~r1) yapısı.

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> Bu işlev tarafından `CURRENCY` döndürülen işaretçi tarafından erişilen yapıdaki `COleCurrency` değeri değiştirmek bu nesnenin değerini değiştirir. Bu `COleCurrency` nesnenin durumunu değiştirmez.

Daha fazla bilgi için Windows SDK'daki [PARA Birimi](/windows/win32/api/wtypes/ns-wtypes-cy~r1) girişine bakın.

## <a name="colecurrencym_status"></a><a name="m_status"></a>COleCurrency::m_status

Bu veri üyesinin türü, `CurrencyStatus` `COleCurrency` sınıf içinde tanımlanan numaralandırılmış türüdür.

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

- `COleCurrency::invalid`Bu `COleCurrency` nesnenin geçersiz olduğunu gösterir; diğer bir gerçek, değeri yanlış olabilir.

- `COleCurrency::null`Bu `COleCurrency` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlandığını gösterir. (Bu, C++ NULL'un aksine veritabanında "değer sahibi olma" anlamında "null"dur.)

Bir `COleCurrency` nesnenin durumu aşağıdaki durumlarda geçersizdir:

- Değeri bir VARYANT'tan veya `COleVariant` para birimi değerine dönüştürülmeyen bir değerden ayarlanırsa.

- Bu nesne, bir aritmetik atama işlemi sırasında bir taşma `+=` ** \* **veya taşma yaşadıysa, örneğin veya .

- Bu nesneye geçersiz bir değer atandıysa.

- Bu nesnenin durumu [SetStatus](#setstatus)kullanarak açıkça geçersiz olarak ayarlanmışsa.

Durumu geçersiz duruma göre ayarlayabilen işlemler hakkında daha fazla bilgi için aşağıdaki üye işlevlere bakın:

- [Colecurrency](#colecurrency)

- [işleç =](#operator_eq)

- [işleç +, -](#operator_plus_minus)

- [işleç +=, -=](#operator_plus_minus_eq)

- [işleç */](#operator_star)

- [işleç *=, /=](#operator_star_div_eq)

> [!CAUTION]
> Bu veri üyesi gelişmiş programlama durumları içindir. Sıralı üye işlevleri kullanmalısınız [GetStatus](#getstatus) ve [SetStatus](#setstatus). Bu `SetStatus` veri üyesinin açıkça ayarlanmasıyla ilgili daha fazla uyarı için bkz.

## <a name="colecurrencyoperator-"></a><a name="operator_eq"></a>COleCurrency::operator =

Bu aşırı yüklü atama işleçleri `COleCurrency` kaynak para birimi değerini bu nesneye kopyalar.

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>Açıklamalar

Her işleç kısa bir açıklama aşağıdaki gibidir:

- **işleç =(** `cySrc` **)** Değer `CURRENCY` `COleCurrency` nesneye kopyalanır ve durumu geçerli olarak ayarlanır.

- **işleç =(** `curSrc` **)** Varolan `COleCurrency` bir nesne olan operand'ın değeri ve `COleCurrency` durumu bu nesneye kopyalanır.

- **operatör =(** *varSrc* **)** Değerin `VARIANT` (veya [COleVariant](../../mfc/reference/colevariant-class.md) nesnesinin) bir para `VT_CY`birimine dönüştürülmesi başarılı olursa, dönüştürülen `COleCurrency` değer bu nesneye kopyalanır ve durumu geçerli olarak ayarlanır. Dönüştürme başarılı olmazsa, `COleCurrency` nesnenin değeri 0 olarak ayarlanır ve durumu geçersiz olur.

Daha fazla bilgi için Windows SDK'daki [PARA BIRIMI](/windows/win32/api/wtypes/ns-wtypes-cy~r1) ve [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) girişlerine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

## <a name="colecurrencyoperator---"></a><a name="operator_plus_minus"></a>COleCurrency::operatör +, -

Bu işleçler, birbirinden iki `COleCurrency` değer eklemenize ve çıkarmanıza ve `COleCurrency` bir değerin işaretini değiştirmenize olanak sağlar.

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>Açıklamalar

Operandlardan biri null ise, elde edilen `COleCurrency` değerin durumu null'dur.

Aritmetik işlem taşarsa, elde `COleCurrency` edilen değer geçersizdir.

Operand geçersiz sa yılıyorsa ve diğeri null değilse, elde edilen `COleCurrency` değerin durumu geçersizdir.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

## <a name="colecurrencyoperator---"></a><a name="operator_plus_minus_eq"></a>COleCurrency::operatör +=, -=

Bu nesneye ve bu `COleCurrency` `COleCurrency` nesneye bir değer eklemenize ve çıkarmanıza izin verin.

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>Açıklamalar

Operandlardan biri null ise, bu `COleCurrency` nesnenin durumu null olarak ayarlanır.

Aritmetik işlem taşarsa, bu `COleCurrency` nesnenin durumu geçersiz olarak ayarlanır.

Operand'lardan biri geçersizse ve diğeri null değilse, bu `COleCurrency` nesnenin durumu geçersiz olarak ayarlanır.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

## <a name="colecurrencyoperator--and-"></a><a name="operator_star"></a>COleCurrency::operatör \* ve /

Bir `COleCurrency` değeri integral değerine göre ölçeklendirmenize olanak sağlar.

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>Açıklamalar

Operand `COleCurrency` null ise, elde edilen `COleCurrency` değerin durumu null'dur.

Aritmetik işlem taşarsa veya alta akarsa, `COleCurrency` elde edilen değerin durumu geçersizdir.

Operand `COleCurrency` geçersizse, elde edilen `COleCurrency` değerin durumu geçersizdir.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

## <a name="colecurrencyoperator--"></a><a name="operator_star_div_eq"></a>COleCurrency::operatör \*=, /=

Bu `COleCurrency` değeri integral değeriyle ölçeklendirmenize izin verir.

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>Açıklamalar

Operand `COleCurrency` null ise, bu `COleCurrency` nesnenin durumu null ayarlanır.

Aritmetik işlem taşarsa, bu `COleCurrency` nesnenin durumu geçersiz olarak ayarlanır.

Operand `COleCurrency` geçersizse, bu `COleCurrency` nesnenin durumu geçersiz olarak ayarlanır.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

## <a name="colecurrencyoperator-ltlt-gtgt"></a><a name="operator_stream"></a>COleCurrency::operatör &lt; &lt;,&gt;&gt;

Tanılama boşaltmave arşive depolamayı destekler.

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

Çıkarma ( **>>**) işleci bir arşivden yüklemeyi destekler.

## <a name="colecurrencyoperator-currency"></a><a name="operator_currency"></a>COleCurrency::operatör PARA BİRİmİ

Değeri `CURRENCY` bu `COleCurrency` nesneden kopyalanan bir yapı döndürür.

```
operator CURRENCY() const;
```

### <a name="remarks"></a>Açıklamalar

## <a name="colecurrencyparsecurrency"></a><a name="parsecurrency"></a>COleCurrency::ParseCurrency

Para birimi değerini okumak için bir dize ayrıştize etmek için bu üye işlevi arayın.

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
Ayrıştırılması gereken null-sonlandırılan dize için bir işaretçi.

*Dwflags*<br/>
Yerel ayarlar için bayrakları, büyük olasılıkla aşağıdaki bayrağı gösterir:

- LOCALE_NOUSEROVERRIDE Özel kullanıcı ayarları yerine sistemin varsayılan yerel ayarları kullanın.

*lcid*<br/>
Dönüşüm için kullanılacak yerel kimliği gösterir.

### <a name="return-value"></a>Dönüş Değeri

Dize başarıyla bir para birimi değerine dönüştürüldüyse sıfırsız, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kaynak dizedeki sayısal olmayan karakterlerin anlamı için yerel dil belirtimlerini (yerel adlar) kullanır.

Yerel kimlik değerlerinin tartışılması için, [Birden Çok Dili Destekleme](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages)bölümüne bakın.

Dize başarıyla bir para birimi değerine dönüştürüldüyse, bu `COleCurrency` nesnenin değeri bu değere ve durumu geçerli olarak ayarlanır.

Dize para birimi değerine dönüştürülemediyse veya sayısal bir taşma varsa, `COleCurrency` bu nesnenin durumu geçersizdir.

Bellek ayırma hataları nedeniyle dize dönüştürme başarısız olduysa, bu işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md)atar. Başka bir hata durumunda, bu işlev bir [COleException](../../mfc/reference/coleexception-class.md)atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]

## <a name="colecurrency-relational-operators"></a><a name="colecurrency_relational_operators"></a>COleCurrency İlişkisel Operatörler

Koşul doğruysa, iki para birimi değerini karşılaştırın ve sıfırsız döndürin; aksi takdirde 0.

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
> Sipariş işlemlerinin **<**(, ** \< **, , **>**, **>=**) değeri, operand'ın durumu null veya geçersizise tanımsızdır. Eşitlik işleçleri `==` `!=`( , ) operands durumunu düşünün.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

## <a name="colecurrencysetcurrency"></a><a name="setcurrency"></a>COleCurrency::SetCurrency

Birimleri ve bu `COleCurrency` nesnenin kesirli kısmını ayarlamak için bu üye işlevi arayın.

```cpp
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>Parametreler

*nUnits*, *nFractionalUnits* Bu `COleCurrency` nesneye kopyalanacak değerin birimlerini ve kesirli kısmını (1/10.000'lerde) gösterir.

### <a name="remarks"></a>Açıklamalar

Kesirli parçanın mutlak değeri 10.000'den büyükse, aşağıdaki örneklerin üçüncü kısmında gösterildiği gibi birimleriçin uygun ayarlama yapılır.

Birimler ve kesirli kısmı imzalı uzun değerlerle belirtilir unutmayın. Aşağıdaki örneklerin dördüncüsü, parametrelerfarklı işaretlere sahip olduğunda ne olduğunu gösterir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

## <a name="colecurrencysetstatus"></a><a name="setstatus"></a>COleCurrency::SetStatus

Bu `COleCurrency` nesnenin durumunu (geçerliliğini) ayarlamak için bu üye işlevi çağırın.

```cpp
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>Parametreler

*Durum*<br/>
Bu `COleCurrency` nesne için yeni durum.

### <a name="remarks"></a>Açıklamalar

*Durum* parametresi değeri, `CurrencyStatus` `COleCurrency` sınıf içinde tanımlanan numaralandırılmış türtarafından tanımlanır.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleCurrency::valid`Bu `COleCurrency` nesnenin geçerli olduğunu gösterir.

- `COleCurrency::invalid`Bu `COleCurrency` nesnenin geçersiz olduğunu gösterir; diğer bir gerçek, değeri yanlış olabilir.

- `COleCurrency::null`Bu `COleCurrency` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlandığını gösterir. (Bu, C++ NULL'un aksine veritabanında "değer sahibi olma" anlamında "null"dur.)

> [!CAUTION]
> Bu işlev gelişmiş programlama durumları içindir. Bu işlev, bu nesnedeki verileri değiştirmez. Genellikle durumu geçersiz veya geçersiz olarak ayarlamak için kullanılır. Atama işlecinin ( [işleç =](#operator_eq)) ve [SetCurrency'in](#setcurrency) kaynak değeri(ler) dayalı olarak nesnenin durumunu ayarladığını unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleVariant Sınıfı](../../mfc/reference/colevariant-class.md)
