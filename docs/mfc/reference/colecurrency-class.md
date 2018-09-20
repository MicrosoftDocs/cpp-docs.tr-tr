---
title: COleCurrency sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec20b4b212ee435c9538716afaca645edfe5adcc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404217"
---
# <a name="colecurrency-class"></a>COleCurrency sınıfı

Kapsülleyen `CURRENCY` OLE Otomasyonu nesnesi etkin veri türü.

## <a name="syntax"></a>Sözdizimi

```
class COleCurrency
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleCurrency::COleCurrency](#colecurrency)|Oluşturur bir `COleCurrency` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleCurrency::Format](#format)|Bir biçimlendirilmiş dize gösterimini oluşturur bir `COleCurrency` nesne.|
|[COleCurrency::GetStatus](#getstatus)|Bu durum (geçerlilik) alır `COleCurrency` nesne.|
|[COleCurrency::ParseCurrency](#parsecurrency)|Para birimi değeri bir dizeden okur ve değerini ayarlar `COleCurrency`.|
|[COleCurrency::SetCurrency](#setcurrency)|Bu ayarlar `COleCurrency` nesne.|
|[COleCurrency::SetStatus](#setstatus)|Durum (geçerlilik) Bu ayarlar `COleCurrency` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Kopya bir `COleCurrency` değeri.|
|[operator +, -](#operator_plus_minus)|Ekler, çıkarır ve değişiklikleri belirtisi `COleCurrency` değerleri.|
|[operator +=-=](#operator_plus_minus_eq)|Ekler ve çıkaran bir `COleCurrency` bu değerden `COleCurrency` nesne.|
|[operator * /](#operator_star)|Ölçekler bir `COleCurrency` değeri bir tamsayı değeri.|
|[operator * =, / =](#operator_star_div_eq)|Bu ölçeklendirir `COleCurrency` değeri bir tamsayı değeri.|
|[işleç <<](#operator_stream)|Çıkış bir `COleCurrency` değerini `CArchive` veya `CDumpContext`.|
|[İşleç >>](#operator_stream)|Giriş bir `COleCurrency` nesnesinden `CArchive`.|
|[para birimi işleci](#operator_currency)|Dönüştürür bir `COleCurrency` bir para birimi değeri.|
|[işleç ==, <, < =, vs.](#colecurrency_relational_operators)|İki karşılaştırır `COleCurrency` değerleri.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleCurrency::m_cur](#m_cur)|Bunun için temel alınan para birimi içeren `COleCurrency` nesne.|
|[COleCurrency::m_status](#m_status)|Bu durumu içeren `COleCurrency` nesne.|

## <a name="remarks"></a>Açıklamalar

`COleCurrency` bir temel sınıfa sahip değil.

Para birimi, 8 byte, 10.000 ölçeğinde ikiye tamsayı değeri olarak uygulanır. Bu seçenek, sabit noktalı bir sayı Ondalık ayırıcının solundaki 15 basamakla ve 4 rakamdan sağa sağlar. Para birimi veri türüne doğruluğu önemli olduğu parayla veya herhangi bir sabit nokta hesaplaması için fazlasıyla yararlı bir özelliktir. Olası türlerinde biridir `VARIANT` OLE Otomasyonu nesnesi etkin veri türü.

`COleCurrency` Ayrıca bu sabit nokta türü için bazı temel aritmetik işlemleri uygular. Desteklenen işlemler, hesaplamalardaki sırasında ortaya çıkan yuvarlama hataları denetlemek için seçilmedi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`COleCurrency`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

##  <a name="colecurrency"></a>  COleCurrency::COleCurrency

Oluşturur bir `COleCurrency` nesne.

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

*cysrc &*<br/>
Yeni içine kopyalanacak bir para birimi değeri `COleCurrency` nesne.

*curSrc*<br/>
Mevcut bir `COleCurrency` yeni içine kopyalanacak nesne `COleCurrency` nesne.

*varSrc*<br/>
Mevcut bir `VARIANT` veri yapısı (büyük olasılıkla bir `COleVariant` nesnesi) bir para birimi değeri (VT_CY) dönüştürülür ve yeni kopyalanan `COleCurrency` nesne.

*nUnits*, *nFractionalUnits* birimleri ve kesirli kısmını değeri (1/10, 000's içinde) yeni içine kopyalanacak belirtmek `COleCurrency` nesne.

### <a name="remarks"></a>Açıklamalar

Tüm bu oluşturucular Yeni Oluştur `COleCurrency` nesneleri belirtilen değerle başlatılır. Bu oluşturucular her kısa bir açıklaması aşağıdadır. Aksi belirtilmediği sürece, yeni durumunu `COleCurrency` öğesi için geçerli olarak ayarlanır.

- COleCurrency() yapıları bir `COleCurrency` 0 (sıfır) olarak başlatılmış bir nesne.

- COleCurrency (`cySrc`) oluşturan bir `COleCurrency` nesnesinden bir [para birimi](/windows/desktop/api/wtypes/ns-wtypes-tagcy) değeri.

- COleCurrency (`curSrc`) oluşturan bir `COleCurrency` mevcut bir nesne `COleCurrency` nesne. Yeni nesne kaynak nesne ile aynı duruma sahip.

- COleCurrency (`varSrc`) oluşturan bir `COleCurrency` nesne. Dönüştürmeye çalışır bir [değişken](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) yapısı veya `COleVariant` nesne bir para birimi (VT_CY) değeri. Bu dönüştürmenin başarılı olursa, dönüştürülen değer yeni kopyalanan `COleCurrency` nesne. Değerini, değilse `COleCurrency` nesne sıfır (0) ve kendi geçersiz durumuna ayarlanır.

- `COleCurrency(`nUnits`, `nFractionalUnits`) Constructs a `COleCurrency' belirtilen sayısal bileşenlerinden nesne. Kesirli bölümü mutlak değerini 10. 000 ' büyükse, uygun düzeltme birimleri için yapılır. Not, birimleri ve kesirli bölümü tarafından imzalanmış uzun değerler belirtilir.

Daha fazla bilgi için [para birimi](/windows/desktop/api/wtypes/ns-wtypes-tagcy) ve [değişken](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) Windows SDK'sı girdileri.

### <a name="example"></a>Örnek

Aşağıdaki örnekler, sıfır parametresi ve iki parametre oluşturucular etkilerini gösterir:

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

##  <a name="format"></a>  COleCurrency::Format

Para birimi değeri biçimlendirilmiş bir temsilini oluşturmak için bu üye işlevini çağırın.

```
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const;
```

### <a name="parameters"></a>Parametreler

*CertOpenStore*<br/>
Yerel ayarlar için bayrakları belirtir. Yalnızca aşağıdaki bayrağı, para birimi için geçerlidir:

- LOCALE_NOUSEROVERRIDE sistem varsayılan yerel ayarları yerine özel kullanıcı ayarları kullanın.

*lcid*<br/>
Dönüştürme için kullanılacak yerel ayar Kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

A `CString` , biçimlendirilmiş para birimi değeri içerir.

### <a name="remarks"></a>Açıklamalar

Yerel dil özellikleri (yerel ayar kimlikleri) kullanarak değeri biçimlendirir. Döndürülen değer bir para birimi simgesi dahil edilmez. Varsa bu durum `COleCurrency` nesnesi null ise, dönüş değeri boş bir dizedir. Geçersiz durum ise, dize kaynağı IDS_INVALID_CURRENCY dizesini belirtilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

##  <a name="getstatus"></a>  COleCurrency::GetStatus

(Geçerlilik) durumunu almak için bu üye işlevi çağrısı bir verilen `COleCurrency` nesne.

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu durumunu döndüren `COleCurrency` değeri.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri tarafından tanımlanan `CurrencyStatus` listelenmiş içinde tanımlanan bir türü `COleCurrency` sınıfı.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:

  - `COleCurrency::valid` Belirten bu `COleCurrency` nesne geçerlidir.

  - `COleCurrency::invalid` Belirten bu `COleCurrency` Nesne geçersiz; diğer bir deyişle, değeri yanlış olabilir.

  - `COleCurrency::null` Belirten bu `COleCurrency` nesnesi, null, diğer bir deyişle, bu nesne için hiçbir değer belirtilmiş. ("Null" bir "herhangi bir değer NULL C++ aksine kullanılmasının" veritabanı anlamında budur.)

Durumunu bir `COleCurrency` aşağıdaki durumlarda nesne geçersiz:

- Bir DEĞİŞKENDEN değerini ayarlarsanız veya `COleVariant` için para birimi değeri dönüştürülemedi değeri.

- Bu nesne bir taşma veya yetersiz gelme aritmetik atama işlemi sırasında örneğin karşılaştı, `+=` veya **\* =**.

- Bu nesne için geçersiz bir değere atanırsa.

- Bu nesne durumunu kullanarak geçersiz açıkça ayarlandığını [SetStatus](#setstatus).

Geçersiz, aşağıdaki üye işlevleri için durumunu ayarlayabilir işlemleri hakkında daha fazla bilgi için:

- [COleCurrency](#colecurrency)

- [işleç =](#operator_eq)

- [operator + -](#operator_plus_minus)

- [operator += ve-=](#operator_plus_minus_eq)

- [operator * /](#operator_star)

- [operator * = ve / =](#operator_star_div_eq)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]

##  <a name="m_cur"></a>  COleCurrency::m_cur

Arka plandaki [para birimi](/windows/desktop/api/wtypes/ns-wtypes-tagcy) yapısı bu `COleCurrency` nesne.

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  Değer değiştirme `CURRENCY` bu işlev tarafından döndürülen işaretçi tarafından erişilen yapısı, bu değeri değişecek `COleCurrency` nesne. Bu durumu değiştirmez `COleCurrency` nesne.

Daha fazla bilgi için [para birimi](/windows/desktop/api/wtypes/ns-wtypes-tagcy) Windows SDK'sı girişi.

##  <a name="m_status"></a>  COleCurrency::m_status

Bu veri üyesi listeden seçimli türü türüdür `CurrencyStatus`, içinde tanımlanan `COleCurrency` sınıfı.

```
enum CurrencyStatus{
    valid = 0,
    invalid = 1,
    null = 2,
};
```

### <a name="remarks"></a>Açıklamalar

Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleCurrency::valid` Belirten bu `COleCurrency` nesne geçerlidir.

- `COleCurrency::invalid` Belirten bu `COleCurrency` Nesne geçersiz; diğer bir deyişle, değeri yanlış olabilir.

- `COleCurrency::null` Belirten bu `COleCurrency` nesnesi, null, diğer bir deyişle, bu nesne için hiçbir değer belirtilmiş. ("Null" bir "herhangi bir değer NULL C++ aksine kullanılmasının" veritabanı anlamında budur.)

Durumunu bir `COleCurrency` aşağıdaki durumlarda nesne geçersiz:

- Bir DEĞİŞKENDEN değerini ayarlarsanız veya `COleVariant` için para birimi değeri dönüştürülemedi değeri.

- Bu nesne bir taşma veya yetersiz gelme aritmetik atama işlemi sırasında örneğin karşılaştı, `+=` veya **\* =**.

- Bu nesne için geçersiz bir değere atanırsa.

- Bu nesne durumunu kullanarak geçersiz açıkça ayarlandığını [SetStatus](#setstatus).

Geçersiz, aşağıdaki üye işlevleri için durumunu ayarlayabilir işlemleri hakkında daha fazla bilgi için:

- [COleCurrency](#colecurrency)

- [işleç =](#operator_eq)

- [operator +, -](#operator_plus_minus)

- [operator +=-=](#operator_plus_minus_eq)

- [operator * /](#operator_star)

- [operator * =, / =](#operator_star_div_eq)

> [!CAUTION]
>  Gelişmiş programlama durumlar için bu verileri üyesidir. Satır içi üye işlevleri kullanmalıdır [GetStatus](#getstatus) ve [SetStatus](#setstatus). Bkz: `SetStatus` açıkça bu veri üyesi ayarlama ile ilgili daha fazla uyarılar için.

##  <a name="operator_eq"></a>  COleCurrency::operator =

Bu aşırı yüklenmiş atama işleçleri bu kaynak para birimi değeri kopyalayın `COleCurrency` nesne.

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
  const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>Açıklamalar

Her işleç kısa bir açıklaması aşağıdaki gibidir:

- **operator = (** `cySrc` **)** `CURRENCY` değeri kopyalanır `COleCurrency` nesne ve durumuna ayarlanır için geçerli.

- **işleç = (** `curSrc` **)** mevcut bir işlenen, durumunu ve değer `COleCurrency` nesne bu kopyalanır `COleCurrency` nesne.

- **işleç = (** *varSrc* **)** varsa dönüştürülmesi `VARIANT` değeri (veya [COleVariant](../../mfc/reference/colevariant-class.md) nesne) para birimine ( `VT_CY`) olan başarılı, dönüştürülen değer bu kopyalanır `COleCurrency` nesne ve durumuna ayarlanır için geçerli. Dönüştürme başarılı ise değerini `COleCurrency` nesnesi, 0'geçersiz durumu ayarlanır.

Daha fazla bilgi için [para birimi](/windows/desktop/api/wtypes/ns-wtypes-tagcy) ve [değişken](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) Windows SDK'sı girdileri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

##  <a name="operator_plus_minus"></a>  COleCurrency::operator +, -

Bu işleçler, ekleme ve çıkarmayı iki izin `COleCurrency` değerleri için ve birbirlerinden ve işaretini değiştirmek için bir `COleCurrency` değeri.

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>Açıklamalar

İşlenenler biri geçerli olduğunda null, ortaya çıkan durumunu `COleCurrency` değeri NULL'dur.

Aritmetik işlem taşma durumunda, ortaya çıkan `COleCurrency` değeri geçersiz.

İşlenen geçersiz ve diğeri ise null değil ortaya çıkan durumu olan `COleCurrency` değeri geçersiz.

Geçerli, geçersiz ve boş durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

##  <a name="operator_plus_minus_eq"></a>  COleCurrency::operator +=-=

Ekleme ve çıkarma olanak tanıyan bir `COleCurrency` için ve bu değer `COleCurrency` nesne.

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>Açıklamalar

İşlenenden ya da ise null, bu durumu `COleCurrency` kümesi nesnesi null.

Aritmetik işlemi bu durumu taşıyor, `COleCurrency` kümesi nesnesi geçersiz.

İşlenenden ya da geçersiz ve diğerini null değilse, bu durumu `COleCurrency` kümesi nesnesi geçersiz.

Geçerli, geçersiz ve boş durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

##  <a name="operator_star"></a>  COleCurrency::operator \* ve /

Ölçeklendirme izin bir `COleCurrency` değeri bir tamsayı değeri.

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>Açıklamalar

Varsa `COleCurrency` işleneni null sonuç durumunu `COleCurrency` değeri NULL'dur.

Aritmetik işlem taşarsa veya yetersiz, ortaya çıkan durumunu `COleCurrency` değeri geçersiz.

Varsa `COleCurrency` işlenen geçersiz durum ortaya çıkan `COleCurrency` değeri geçersiz.

Geçerli, geçersiz ve boş durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

##  <a name="operator_star_div_eq"></a>  COleCurrency::operator \*=, / =

Bu ölçek izin `COleCurrency` değeri bir tamsayı değeri.

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>Açıklamalar

Varsa `COleCurrency` işlenen, null, bu durumu `COleCurrency` kümesi nesnesi null.

Aritmetik işlemi bu durumu taşıyor, `COleCurrency` kümesi nesnesi geçersiz.

`COleCurrency` İşlenen geçersiz durum bu `COleCurrency` kümesi nesnesi geçersiz.

Geçerli, geçersiz ve boş durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

##  <a name="operator_stream"></a>  COleCurrency::operator &lt; &lt;, &gt;&gt;

Tanılama dökme ve bir arşiv Depolama'yı destekler.

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

Çıkarma ( **>>**) işleci bir arşiv yüklenmesini destekler.

##  <a name="operator_currency"></a>  COleCurrency::operator para birimi

Döndürür bir `CURRENCY` değeri bu kopyalanır yapısı `COleCurrency` nesne.

```
operator CURRENCY() const;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="parsecurrency"></a>  COleCurrency::ParseCurrency

Para birimi değeri okumak için bir dizeyi ayrıştırmak için bu üye işlevini çağırın.

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
Ayrıştırılacak olan boş sonlandırılmış dizeye bir işaretçi.

*CertOpenStore*<br/>
Yerel ayarlar, büyük olasılıkla aşağıdaki bayrağı bayrakları gösterir:

- LOCALE_NOUSEROVERRIDE sistem varsayılan yerel ayarları yerine özel kullanıcı ayarları kullanın.

*lcid*<br/>
Dönüştürme için kullanılacak yerel ayar Kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Dize, bir para birimi değeri için Aksi durumda 0 başarıyla dönüştürüldü olursa sıfır dışı.

### <a name="remarks"></a>Açıklamalar

Yerel dil özellikleri (yerel ayar kimlikleri), sayısal karakter kaynak dizesi anlamını için kullanır.

Yerel ayar kimliği değerlerin bir açıklaması için bkz. [birden fazla dili destekleyen](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages).

Dize, bir para birimi başarıyla dönüştürüldü değeri, bu değeri `COleCurrency` nesne ayarlandığından bu değeri ve durumu için geçerli.

Dize için para birimi değeri dönüştürülemedi veya sayısal bir taşma, bu durum ise `COleCurrency` nesnesi geçersiz.

Bellek ayırma hataları nedeniyle dize dönüştürme başarısız olursa bu işlev oluşturur. bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md). Diğer hata durumu, bu işlev oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]

##  <a name="colecurrency_relational_operators"></a>  COleCurrency ilişkisel işleçleri

İki para birimi değerini karşılaştırır ve koşul true ise sıfır olmayan döndürür; Aksi durumda 0.

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
>  Sıralama işlemleri dönüş değerini ( **<**, **\< =**, **>**, **>=**) iki işlenenden durumu null veya geçersiz ise tanımsızdır. Eşitlik işleçleri ( `==`, `!=`) işlenenleri durumunu göz önünde bulundurun.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

##  <a name="setcurrency"></a>  COleCurrency::SetCurrency

Birimleri ve kesirli kısmı ayarlamak için bu üye işlevi çağrısı `COleCurrency` nesne.

```
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>Parametreler

*nUnits*, *nFractionalUnits* birimleri ve kesirli kısmını değeri (1/10, 000's içinde) bu kopyalanacak belirtmek `COleCurrency` nesne.

### <a name="remarks"></a>Açıklamalar

Kesirli bölümü mutlak değerini 10. 000 ' büyükse, uygun düzeltme üçüncü aşağıdaki örneklerde gösterildiği gibi birimleri için yapılır.

Not, birimleri ve kesirli bölümü tarafından imzalanmış uzun değerler belirtilir. Aşağıdaki örneklerin dördüncü parametrelere farklı işaretlere sahipse ne olacağını gösterir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

##  <a name="setstatus"></a>  COleCurrency::SetStatus

Bu durum (geçerlilik) ayarlamak için bu üye işlevi çağrısı `COleCurrency` nesne.

```
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>Parametreler

*Durumu*<br/>
Bu yeni durum `COleCurrency` nesne.

### <a name="remarks"></a>Açıklamalar

*Durumu* parametre değeri tarafından tanımlanan `CurrencyStatus` listelenmiş içinde tanımlanan bir türü `COleCurrency` sınıfı.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleCurrency::valid` Belirten bu `COleCurrency` nesne geçerlidir.

- `COleCurrency::invalid` Belirten bu `COleCurrency` Nesne geçersiz; diğer bir deyişle, değeri yanlış olabilir.

- `COleCurrency::null` Belirten bu `COleCurrency` nesnesi, null, diğer bir deyişle, bu nesne için hiçbir değer belirtilmiş. ("Null" bir "herhangi bir değer NULL C++ aksine kullanılmasının" veritabanı anlamında budur.)

> [!CAUTION]
>  Bu işlev, Gelişmiş programlama durumlar için kullanılır. Bu işlev, bu nesne verileri değiştirmez. Çoğunlukla, null veya geçersiz durumu ayarlamak için de kullanılır. Unutmayın atama işleci ( [işleç =](#operator_eq)) ve [SetCurrency](#setcurrency) kaynak değerleri üzerinde temel nesnenin durumunu ayarlayın.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleVariant Sınıfı](../../mfc/reference/colevariant-class.md)
