---
title: CSimpleStringT Sınıfı
ms.date: 10/18/2018
f1_keywords:
- CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::PCXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::PXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::Append
- ATLSIMPSTR/ATL::CSimpleStringT::AppendChar
- ATLSIMPSTR/ATL::CSimpleStringT::CopyChars
- ATLSIMPSTR/ATL::CSimpleStringT::CopyCharsOverlapped
- ATLSIMPSTR/ATL::CSimpleStringT::Empty
- ATLSIMPSTR/ATL::CSimpleStringT::FreeExtra
- ATLSIMPSTR/ATL::CSimpleStringT::GetAllocLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetAt
- ATLSIMPSTR/ATL::CSimpleStringT::GetBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::GetBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetManager
- ATLSIMPSTR/ATL::CSimpleStringT::GetString
- ATLSIMPSTR/ATL::CSimpleStringT::IsEmpty
- ATLSIMPSTR/ATL::CSimpleStringT::LockBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::Preallocate
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::SetAt
- ATLSIMPSTR/ATL::CSimpleStringT::SetManager
- ATLSIMPSTR/ATL::CSimpleStringT::SetString
- ATLSIMPSTR/ATL::CSimpleStringT::StringLength
- ATLSIMPSTR/ATL::CSimpleStringT::Truncate
- ATLSIMPSTR/ATL::CSimpleStringT::UnlockBuffer
helpviewer_keywords:
- shared classes, CSimpleStringT
- strings [C++], ATL class
- CSimpleStringT class
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
ms.openlocfilehash: 76d418c4f063d5787209ea72e7c681013eb37801
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747040"
---
# <a name="csimplestringt-class"></a>CSimpleStringT Sınıfı

Bu sınıf `CSimpleStringT` bir nesneyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <typename BaseType>
class CSimpleStringT
```

### <a name="parameters"></a>Parametreler

*BaseType*<br/>
String sınıfının karakter türü. Aşağıdakilerden biri olabilir:

- **char** (ANSI karakter dizeleri için).

- **wchar_t** (Unicode karakter dizeleri için).

- TCHAR (hem ANSI hem de Unicode karakter dizeleri için).

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleStringT::PCXSTR](#pcxstr)|Sabit bir dize için bir işaretçi.|
|[CSimpleStringT::PXSTR](#pxstr)|Dize için bir işaretçi.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleStringt::CSimpleStringt](#ctor)|Nesneleri `CSimpleStringT` çeşitli şekillerde inşa eder.|
|[CSimpleStringt::~CSimpleStringt](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleStringT::Ek](#append)|Varolan `CSimpleStringT` `CSimpleStringT` bir nesneye bir nesne ekler.|
|[CSimpleStringT::AppendChar](#appendchar)|Varolan `CSimpleStringT` bir nesneye bir karakter ekler.|
|[CSimpleStringT::CopyChars](#copychars)|Bir karakteri veya karakteri başka bir dize kopyalar.|
|[CSimpleStringT::CopyCharsOverlapped](#copycharsoverlapped)|Bir karakteri veya karakteri arabelleklerin çakıştüğü başka bir dize kopyalar.|
|[CSimpleStringT::Boş](#empty)|Bir dizeyi sıfır uzunluğuna zorlar.|
|[CSimpleStringT::FreeExtra](#freeextra)|Dize nesnesi tarafından daha önce ayrılan herhangi bir ek belleği serbest eder.|
|[CSimpleStringT::GetAllocLength](#getalloclength)|Bir `CSimpleStringT` nesnenin ayrılan uzunluğunu alır.|
|[CSimpleStringT::Getat](#getat)|Karakteri belirli bir konumda döndürür.|
|[CSimpleStringT::GetBuffer](#getbuffer)|Bir `CSimpleStringT`' deki karakterlere işaretçi verir.|
|[CSimpleStringT::GetBufferSetLength](#getbuffersetlength)|Bir işaretçiyi , belirtilen `CSimpleStringT`uzunluğa kesilen karakterlere döndürür.|
|[CSimpleStringT::Getlength](#getlength)|Bir `CSimpleStringT` nesnedeki karakter sayısını döndürür.|
|[CSimpleStringT::GetManager](#getmanager)|Nesnenin bellek yöneticisini `CSimpleStringT` alır.|
|[CSimpleStringT::GetString](#getstring)|Karakter dizesini alır|
|[CSimpleStringT::Boş](#isempty)|Nesnenin `CSimpleStringT` karakter içerip içermediğini sınar.|
|[CSimpleStringT::LockAraffer](#lockbuffer)|Başvuru sayma devre dışı kılabilir ve arabellekteki dizeyi korur.|
|[CSimpleStringT::P](#preallocate)|Karakter arabelleği için belirli bir bellek miktarı ayırır.|
|[CSimpleStringT::ReleaseArabellek](#releasebuffer)|`GetBuffer`Tarafından döndürülen arabelleğe denetim serbest|
|[CSimpleStringT::ReleaseBufferSetLength](#releasebuffersetlength)|`GetBuffer`Tarafından döndürülen arabelleğe denetim serbest|
|[CSimpleStringT::Setat](#setat)|Belirli bir konumda bir karakter ayarlar.|
|[CSimpleStringT::SetManager](#setmanager)|Bir `CSimpleStringT` nesnenin bellek yöneticisini ayarlar.|
|[CSimpleStringT::SetString](#setstring)|`CSimpleStringT` Nesnenin dizesini ayarlar.|
|[CSimpleStringT::StringLength](#stringlength)|Belirtilen dizedeki karakter sayısını verir.|
|[CSimpleStringT::Truncate](#truncate)|Dizeyi belirli bir uzunluğa bağlar.|
|[CSimpleStringT::UnlockAraffer](#unlockbuffer)|Başvuru sayımını sağlar ve arabellekteki dizeyi serbest bırakır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleStringT::operatör PCXSTR](#operator_pcxstr)|C stili dize olarak `CSimpleStringT` bir nesnede depolanan karakterlere doğrudan erişir.|
|[CSimpleStringT::işleç\[\]](#operator_at)|Karakteri belirli bir konumda döndürür — `GetAt`operatör ikamesi için .|
|[CSimpleStringT::işleç +=](#operator_add_eq)|Varolan bir dize sonuna yeni bir dize concatenates.|
|[CSimpleStringT::operatör =](#operator_eq)|Nesneye yeni bir `CSimpleStringT` değer atar.|

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT`Visual C++ tarafından desteklenen çeşitli dize sınıfları için taban sınıftır. Dize nesnesinin bellek yönetimi ve temel arabellek işlemesi için en az destek sağlar. Daha gelişmiş dize nesneleri için [CStringT Sınıfı'na](../../atl-mfc-shared/reference/cstringt-class.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpstr.h

## <a name="csimplestringtappend"></a><a name="append"></a>CSimpleStringT::Ek

Varolan `CSimpleStringT` `CSimpleStringT` bir nesneye bir nesne ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
void Append(const CSimpleStringT& strSrc);
void Append(PCXSTR pszSrc, int nLength);
void Append(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Parametreler

*strSrc*<br/>
Eklenecek `CSimpleStringT` nesne.

*pszSrc*<br/>
Eklenecek karakterleri içeren bir dize için bir işaretçi.

*nUzunluk*<br/>
Ekinde ekili karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Varolan `CSimpleStringT` bir nesneyi başka `CSimpleStringT` bir nesneye eklemek için bu yöntemi çağırın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::Append`

```cpp
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```

## <a name="csimplestringtappendchar"></a><a name="appendchar"></a>CSimpleStringT::AppendChar

Varolan `CSimpleStringT` bir nesneye bir karakter ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
void AppendChar(XCHAR ch);
```

#### <a name="parameters"></a>Parametreler

*Caner*<br/>
Eklenecek karakter

### <a name="remarks"></a>Açıklamalar

Belirtilen karakteri varolan `CSimpleStringT` bir nesnenin sonuna eklemek için bu işlevi çağırın.

## <a name="csimplestringtcopychars"></a><a name="copychars"></a>CSimpleStringT::CopyChars

Bir karakteri veya karakteri bir `CSimpleStringT` nesneye kopyalar.

### <a name="syntax"></a>Sözdizimi

```
static void CopyChars(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>Parametreler

*pchDest*<br/>
Karakter dizesine işaretçi.

*pchSrc*<br/>
Kopyalanacak karakterleri içeren bir dize için bir işaretçi.

*nChars*<br/>
Kopyalanacak *pchSrc* karakter sayısı.

### <a name="remarks"></a>Açıklamalar

*PchSrc'den* *pchDest* dizesine karakterleri kopyalamak için bu yöntemi arayın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::CopyChars`

```cpp
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```

## <a name="csimplestringtcopycharsoverlapped"></a><a name="copycharsoverlapped"></a>CSimpleStringT::CopyCharsOverlapped

Bir karakteri veya karakteri bir `CSimpleStringT` nesneye kopyalar.

### <a name="syntax"></a>Sözdizimi

```
static void CopyCharsOverlapped(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>Parametreler

*pchDest*<br/>
Karakter dizesine işaretçi.

*pchSrc*<br/>
Kopyalanacak karakterleri içeren bir dize için bir işaretçi.

*nChars*<br/>
Kopyalanacak *pchSrc* karakter sayısı.

### <a name="remarks"></a>Açıklamalar

*PchSrc'den* *pchDest* dizesine karakterleri kopyalamak için bu yöntemi arayın. `CopyChars`Aksine, `CopyCharsOverlapped` çakışmış olabilir karakter arabelleklerinden kopyalama için güvenli bir yöntem sağlar.

### <a name="example"></a>Örnek

[CSimpleStringT örneğine bakın:CopyChars](#copychars)veya kaynak kodu `CSimpleStringT::SetString` (atlsimpstr.h bulunur).

## <a name="csimplestringtcsimplestringt"></a><a name="ctor"></a>CSimpleStringt::CSimpleStringt

Bir `CSimpleStringT` nesne inşa eder.

### <a name="syntax"></a>Sözdizimi

```
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr);
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr);
CSimpleStringT(const CSimpleStringT& strSrc);
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw();
```

#### <a name="parameters"></a>Parametreler

*strSrc*<br/>
Varolan `CSimpleStringT` bir nesne bu `CSimpleStringT` nesneye kopyalanacak.

*pchSrc*<br/>
Uzunluk *nLength*karakter dizisi için bir işaretçi , null değil sona erdi.

*pszSrc*<br/>
Bu `CSimpleStringT` nesneye kopyalanacak null-sonlandırılan dize.

*nUzunluk*<br/>
'deki `pch`karakter sayısının sayısı.

*pStringMgr*<br/>
`CSimpleStringT` Nesnenin bellek yöneticisine bir işaretçi. Için `IAtlStringMgr` daha fazla bilgi `CSimpleStringT`ve bellek yönetimi için, [Bellek Yönetimi ve CStringT](../memory-management-with-cstringt.md)bakın.

### <a name="remarks"></a>Açıklamalar

Yeni `CSimpleStringT` bir nesne oluştur. Kurucular giriş verilerini yeni ayrılmış depolama alanına kopyaladığı için bellek özel durumları oluşabilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ATL `CSimpleStringT::CSimpleStringT` **typedef** `CSimpleString`kullanarak kullanımını göstermektedir. `CSimpleString`sınıf şablonunun `CSimpleStringT`yaygın olarak kullanılan bir uzmanlık alanıdır.

```cpp
CSimpleString s1(pMgr);
// Empty string
CSimpleString s2(_T("cat"), pMgr);
// From a C string literal

CSimpleString s3(s2);
// Copy constructor
CSimpleString s4(s2 + _T(" ") + s3);

// From a string expression
CSimpleString s5(_T("xxxxxx"), 6, pMgr);
// s5 = "xxxxxx"
```

## <a name="csimplestringtempty"></a><a name="empty"></a>CSimpleStringT::Boş

Bu `CSimpleStringT` nesneyi boş bir dize yapar ve belleği uygun şekilde serbest kılar.

### <a name="syntax"></a>Sözdizimi

```cpp
void Empty() throw();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. Dizeleri: CString Özel Durum Temizleme.](../cstring-exception-cleanup.md)

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::Empty`

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtfreeextra"></a><a name="freeextra"></a>CSimpleStringT::FreeExtra

Daha önce dize tarafından ayrılan ancak artık gerekmeden ayrılan herhangi bir ekstra belleği serbest bırakmaz.

### <a name="syntax"></a>Sözdizimi

```cpp
void FreeExtra();
```

### <a name="remarks"></a>Açıklamalar

Bu, dize nesnesi tarafından tüketilen bellek yükü azaltmalıdır. Yöntem, arabelleği [GetLength](#getlength)tarafından döndürülen tam uzunluğa göre yeniden tahsis eder.

### <a name="example"></a>Örnek

```cpp
CAtlString basestr;
IAtlStringMgr* pMgr;

pMgr= basestr.GetManager();
ASSERT(pMgr != NULL);

// Create a CSimpleString with 28 characters
CSimpleString str(_T("Many sports are fun to play."), 28, pMgr);
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// Assigning a smaller string won't cause CSimpleString to free its
// memory, because it assumes the string will grow again anyway.
str = _T("Soccer is best!");
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// This call forces CSimpleString to release the extra
// memory it doesn't need.
str.FreeExtra();
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());
```

### <a name="remarks"></a>Açıklamalar

Bu örnekteki çıktı aşağıdaki gibidir:

```Output
Alloc length is 1031, String length is 1024
Alloc length is 1031, String length is 15
Alloc length is 15, String length is 15
```

## <a name="csimplestringtgetalloclength"></a><a name="getalloclength"></a>CSimpleStringT::GetAllocLength

Bir `CSimpleStringT` nesnenin ayrılan uzunluğunu alır.

### <a name="syntax"></a>Sözdizimi

```
int GetAllocLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne için ayrılan karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Bu `CSimpleStringT` nesne için ayrılan karakter sayısını belirlemek için bu yöntemi çağırın. Bu işlevi arama örneği için [FreeExtra'ya](#freeextra) bakın.

## <a name="csimplestringtgetat"></a><a name="getat"></a>CSimpleStringT::Getat

Bir nesneden `CSimpleStringT` bir karakter döndürür.

### <a name="syntax"></a>Sözdizimi

```
XCHAR GetAt(int iChar) const;
```

#### <a name="parameters"></a>Parametreler

*iChar*<br/>
`CSimpleStringT` Nesnedeki karakterin sıfır tabanlı dizini. *iChar* parametresi 0'dan büyük veya eşit ve [GetLength](#getlength)tarafından döndürülen değerden daha az olmalıdır. Aksi `GetAt` takdirde, bir özel durum oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Dizede `XCHAR` belirtilen konumdaki karakteri içeren bir karakter.

### <a name="remarks"></a>Açıklamalar

*iChar*tarafından belirtilen bir karakteri döndürmek için bu yöntemi arayın. Aşırı yüklenen alt komut dosyası (**[]**) `GetAt`işleci için uygun bir diğer addır. Null terminator kullanarak `GetAt`bir özel durum oluşturmadan ele alınabiliyor. Ancak, `GetLength`tarafından sayılmaz ve döndürülen değer 0'dır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, nasıl kullanılacağını `CSimpleStringT::GetAt`gösterir.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```

## <a name="csimplestringtgetbuffer"></a><a name="getbuffer"></a>CSimpleStringT::GetBuffer

`CSimpleStringT` Nesne için iç karakter arabelleği için bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```
PXSTR GetBuffer(int nMinBufferLength);
PXSTR GetBuffer();
```

#### <a name="parameters"></a>Parametreler

*nMinBufferLength*<br/>
Karakter arabelleği tutabileceği en az karakter sayısı. Bu değer, null terminator için alan içermez.

*nMinBufferLength* geçerli arabellek uzunluğundan daha büyükse, geçerli arabelleği yok eder, `GetBuffer` istenen boyutun arabelleğiyle değiştirir ve nesne başvuru sayısını sıfırlar. Bu arabellekte daha önce [LockBuffer'ı](#lockbuffer) aradıysanız, arabellek kilidini kaybedersiniz.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin (null-sonlandırılan) karakter arabelleği için bir `PXSTR` işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesnenin arabellek içeriğini döndürmek için `CSimpleStringT` bu yöntemi çağırın. Döndürülen `PXSTR` sabit değildir ve bu nedenle `CSimpleStringT` içeriğin doğrudan değiştirilmesine izin verir.

Dize içeriğini değiştirmek `GetBuffer` için döndürülen işaretçiyi kullanırsanız, diğer `CSimpleStringT` üye yöntemleri kullanmadan önce [ReleaseBuffer'ı](#releasebuffer) aramanız gerekir.

Ek `CSimpleStringT` işlemler `CSimpleStringT` `GetBuffer` arabelleğin yeniden ayrılmasına `ReleaseBuffer` neden olabileceğinden, iade edilen adres aramadan sonra geçerli olmayabilir. 'nin uzunluğunu değiştirmezseniz arabellek yeniden tahsis `CSimpleStringT`edilmez.

`CSimpleStringT` Nesne yok edildiğinde arabellek belleği otomatik olarak serbest bırakılır.

Dize uzunluğunu kendiniz izlerseniz, sonlandırıcı null karakteri uygulamamalısınız. Ancak, arabelleği `ReleaseBuffer`' ile serbest bırakdığınızda son dize uzunluğunu belirtmeniz gerekir. Sonlandırıcı null karakterini eklerseniz, uzunluk için -1 (varsayılan) geçmeniz gerekir. `ReleaseBuffer`sonra arabellek uzunluğunu belirler.

İsteği `GetBuffer` karşılamak için yeterli bellek varsa, bu yöntem bir CMemoryException* atar.

### <a name="example"></a>Örnek

```cpp
CSimpleString s(_T("abcd"), pMgr);
LPTSTR pBuffer = s.GetBuffer(10);
int sizeOfBuffer = s.GetAllocLength();

// Directly access CSimpleString buffer
_tcscpy_s(pBuffer, sizeOfBuffer, _T("Hello"));
ASSERT(_tcscmp(s, _T("Hello")) == 0);
s.ReleaseBuffer();
```

## <a name="csimplestringtgetbuffersetlength"></a><a name="getbuffersetlength"></a>CSimpleStringT::GetBufferSetLength

*NLength'ta*belirtilen uzunluğu tam `CSimpleStringT` olarak eşleştirmek için gerekirse, nesne için iç karakter arabelleği için bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```
PXSTR GetBufferSetLength(int nLength);
```

#### <a name="parameters"></a>Parametreler

*nUzunluk*<br/>
Karakterlerdeki `CSimpleStringT` karakter arabelleği tam boyutu.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin (null-sonlandırılan) karakter arabelleği için bir `PXSTR` işaretçi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesnenin iç arabelleği belirli bir uzunluk almak için bu yöntemi arayın. Döndürülen `PXSTR` işaretçi **const** değildir ve `CSimpleStringT` böylece içeriğin doğrudan değiştirilmesine izin verir.

Dize içeriğini değiştirmek için [GetBufferSetLength](#getbuffersetlength) tarafından döndürülen `ReleaseBuffer` işaretçiyi kullanırsanız, diğer `CsimpleStringT` `CSimpleStringT` yöntemleri kullanmadan önce iç durumunu güncelleştirmek için arayın.

Ek `CSimpleStringT` işlemler `CSimpleStringT` `GetBufferSetLength` arabelleğin yeniden ayrılmasına `ReleaseBuffer` neden olabileceğinden, iade edilen adres aramadan sonra geçerli olmayabilir. 'nin uzunluğunu `CSimpleStringT`değiştirmezseniz arabellek yeniden atanmamış.

`CSimpleStringT` Nesne yok edildiğinde arabellek belleği otomatik olarak serbest bırakılır.

Dize uzunluğunu kendiniz izlerseniz, sonlandırıcı null karakteri eklemayın. Arabelleği kullanarak serbest bırakdığınızda son dize uzunluğunu belirtmeniz `ReleaseBuffer`gerekir. Uzunluk `ReleaseBuffer` `ReleaseBuffer`için -1 (varsayılan) geç' i aradiğinizde sonlandırıcı bir null karakteri eklerseniz ve `ReleaseBuffer` uzunluğunu belirlemek için arabellekte bir `strlen` işlem gerçekleştirir.

Başvuru sayımı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- Windows SDK'da [Başvuru Sayımı yoluyla Nesne Yaşam Ömürlerini Yönetme.](/windows/win32/com/managing-object-lifetimes-through-reference-counting)

- Windows SDK'da [Başvuru Sayımı'nı uygulama.](/windows/win32/com/implementing-reference-counting)

- Windows SDK'da [Başvuru Sayılarını Yönetme Kuralları.](/windows/win32/com/rules-for-managing-reference-counts)

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::GetBufferSetLength`

```cpp
CSimpleString str(pMgr);
LPTSTR pstr = str.GetBufferSetLength(3);
pstr[0] = _T('C');
pstr[1] = _T('u');
pstr[2] = _T('p');

// No need for trailing zero or call to ReleaseBuffer()
// because GetBufferSetLength() set it for us.

str += _T(" soccer is best!");
ASSERT(_tcscmp(str, _T("Cup soccer is best!")) == 0);
```

## <a name="csimplestringtgetlength"></a><a name="getlength"></a>CSimpleStringT::Getlength

Nesnedeki `CSimpleStringT` karakter sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```
int GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizedeki karakterlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Nesnedeki karakter sayısını döndürmek için bu yöntemi çağırın. Sayım null terminator içermez.

Çok bayt karakter kümeleri (MBCS) `GetLength` için her 8 bitlik karakter sayar; diğer bir deyişle, bir çok bayt karakterde bir kurşun ve iz bayt iki bayt olarak sayılır. Bu işlevi arama örneği için [FreeExtra'ya](#freeextra) bakın.

## <a name="csimplestringtgetmanager"></a><a name="getmanager"></a>CSimpleStringT::GetManager

Nesnenin bellek yöneticisini `CSimpleStringT` alır.

### <a name="syntax"></a>Sözdizimi

```
IAtlStringMgr* GetManager() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne için bellek yöneticisine `CSimpleStringT` bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesne tarafından kullanılan bellek yöneticisini almak için bu yöntemi arayın. Bellek yöneticileri ve dize nesneleri hakkında daha fazla bilgi için Bellek [Yönetimi ve CStringT'e](../memory-management-with-cstringt.md)bakın.

## <a name="csimplestringtgetstring"></a><a name="getstring"></a>CSimpleStringT::GetString

Karakter dizesini alır.

### <a name="syntax"></a>Sözdizimi

```
PCXSTR GetString() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Null-sonlandırılan karakter dizesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesneyle ilişkili karakter dizesini `CSimpleStringT` almak için bu yöntemi çağırın.

> [!NOTE]
> Döndürülen `PCXSTR` işaretçi **const'tür** ve `CSimpleStringT` içeriğin doğrudan değiştirilmesine izin vermez.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::GetString`

```cpp
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```

## <a name="csimplestringtisempty"></a><a name="isempty"></a>CSimpleStringT::Boş

Boş `CSimpleStringT` durum için bir nesneyi sınar.

### <a name="syntax"></a>Sözdizimi

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin `CSimpleStringT` 0 uzunluğu varsa TRUE döndürür; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Nesneboş bir dize içeriyorsa belirlemek için bu yöntemi arayın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::IsEmpty`

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtlockbuffer"></a><a name="lockbuffer"></a>CSimpleStringT::LockAraffer

Başvuru sayma devre dışı kılabilir ve arabellekteki dizeyi korur.

### <a name="syntax"></a>Sözdizimi

```
PXSTR LockBuffer();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CSimpleStringT` nesneye işaretçi veya null-sonlandırılan dize.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesnenin arabelleği kilitlemek için bu yöntemi arayın. Arayarak, `LockBuffer`başvuru sayısı için -1 ile dize bir kopyasını oluşturun. Başvuru sayısı değeri -1 olduğunda, arabellekteki dize "kilitli" durumda olarak kabul edilir. Kilitli bir durumdayken, dize iki şekilde korunur:

- Başka hiçbir dize, bu dize kilitli dize atansa bile, kilitli dizedeki verilere başvuru alamaz.

- Kilitli dize, diğer dize kilitli dize kopyalanmış olsa bile, başka bir dize başvuruasla.

Arabellekteki dizeyi kilitleyerek, dizesinin arabelleküzerindeki özel tutmasının bozulmadan kalmasını sağlarsınız.

Bitirdikten `LockBuffer`sonra, başvuru sayısını 1'e sıfırlamak için [UnlockBuffer'ı](#unlockbuffer) arayın.

> [!NOTE]
> Kilitli bir arabelleküzerinde [GetBuffer'ı](#getbuffer) arar `GetBuffer` ve `nMinBufferLength` parametreyi geçerli arabellek uzunluğundan daha büyük olarak ayarlarsanız, arabellek kilidini kaybedersiniz. Geçerli arabelleği yok etmek için `GetBuffer` böyle bir çağrı, istenen boyutun bir arabellek ile değiştirir ve sıfırlanır.

Başvuru sayımı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- Windows SDK'da [Başvuru Sayımı yoluyla Nesne Yaşam Ömürlerini Yönetme](/windows/win32/com/managing-object-lifetimes-through-reference-counting)

- Windows SDK'da [Başvuru Sayımı](/windows/win32/com/implementing-reference-counting) Uygulama

- Windows SDK'da [Başvuru Sayılarını Yönetme Kuralları](/windows/win32/com/rules-for-managing-reference-counts)

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::LockBuffer`

```cpp
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```

## <a name="csimplestringtoperator"></a><a name="operator_at"></a>CSimpleStringT::işleç\[\]

Karakter dizisinin tek bir karakterine erişmek için bu işlevi arayın.

### <a name="syntax"></a>Sözdizimi

```
XCHAR operator[](int iChar) const;
```

#### <a name="parameters"></a>Parametreler

*iChar*<br/>
Dizedeki bir karakterin sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Aşırı yüklenen alt yazı (**[]**) işleci *iChar'da*sıfır tabanlı dizin tarafından belirtilen tek bir karakteri döndürür. Bu işleç [GetAt](#getat) üye işlevi için uygun bir yedektir.

> [!NOTE]
> Bir karakterin değerini almak için alt komut dosyası (**[]**) işleci `CSimpleStringT`kullanabilirsiniz, ancak bir `CSimpleStringT`karakterin değerini değiştirmek için kullanamazsınız.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::operator []`

```cpp
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```

## <a name="csimplestringtoperator-"></a><a name="operator_at"></a>CSimpleStringT::işleç\[\]

Karakter dizisinin tek bir karakterine erişmek için bu işlevi arayın.

### <a name="syntax"></a>Sözdizimi

```
XCHAR operator[](int iChar) const;
```

### <a name="parameters"></a>Parametreler

*iChar*<br/>
Dizedeki bir karakterin sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Aşırı yüklenen alt yazı (**[]**) işleci *iChar'da*sıfır tabanlı dizin tarafından belirtilen tek bir karakteri döndürür. Bu işleç [GetAt](#getat) üye işlevi için uygun bir yedektir.

> [!NOTE]
> Bir karakterin değerini almak için alt komut dosyası (**[]**) işleci `CSimpleStringT`kullanabilirsiniz, ancak bir `CSimpleStringT`karakterin değerini değiştirmek için kullanamazsınız.

## <a name="csimplestringtoperator-"></a><a name="operator_add_eq"></a>CSimpleStringT::işleç +=

Varolan bir dize sonuna kadar yeni bir dize veya karakter birleştirir.

### <a name="syntax"></a>Sözdizimi

```
CSimpleStringT& operator +=(PCXSTR pszSrc);
CSimpleStringT& operator +=(const CSimpleStringT& strSrc);
template<int t_nSize>
CSimpleStringT& operator+=(const CStaticString< XCHAR, t_nSize >& strSrc);
CSimpleStringT& operator +=(char ch);
CSimpleStringT& operator +=(unsigned char ch);
CSimpleStringT& operator +=(wchar_t ch);
```

#### <a name="parameters"></a>Parametreler

*pszSrc*<br/>
Null-sonlandırılan dize için bir işaretçi.

*strSrc*<br/>
Varolan `CSimpleStringT` bir nesneye işaretçi.

*Caner*<br/>
Eklenecek karakter.

### <a name="remarks"></a>Açıklamalar

İşleç başka `CSimpleStringT` bir nesneyi veya karakteri kabul eder. Bu karmaşıklaştırma işleci kullandığınızda bellek özel durumları oluşabilir, çünkü bu `CSimpleStringT` nesneye eklenen karakterler için yeni depolama alanı ayrılabilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::operator +=`

```cpp
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```

## <a name="csimplestringtoperator-"></a><a name="operator_eq"></a>CSimpleStringT::operatör =

Nesneye yeni bir `CSimpleStringT` değer atar.

### <a name="syntax"></a>Sözdizimi

```
CSimpleStringT& operator =(PCXSTR pszSrc);
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```

#### <a name="parameters"></a>Parametreler

*pszSrc*<br/>
Null-sonlandırılan dize için bir işaretçi.

*strSrc*<br/>
Varolan `CSimpleStringT` bir nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Hedef dize (sol taraf) yeni verileri depolayacak kadar büyükse, yeni bellek ayırma işlemi yapılmaz. Atama işlecini her kullandığınızda bellek özel durumları oluşabilir, çünkü yeni depolama `CSimpleStringT` genellikle ortaya çıkan nesneyi tutmak için ayrılmıştır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::operator =`

```cpp
CSimpleString s1(pMgr), s2(pMgr);
// Empty CSimpleStringT objects

s1 = _T("cat");
// s1 = "cat"
ASSERT(_tcscmp(s1, _T("cat")) == 0);

s2 = s1;               // s1 and s2 each = "cat"
ASSERT(_tcscmp(s2, _T("cat")) == 0);

s1 = _T("the ") + s1;
// Or expressions
ASSERT(_tcscmp(s1, _T("the cat")) == 0);

s1 = _T("x");
// Or just individual characters
ASSERT(_tcscmp(s1, _T("x")) == 0);
```

## <a name="csimplestringtoperator-pcxstr"></a><a name="operator_pcxstr"></a>CSimpleStringT::operatör PCXSTR

C stili dize olarak `CSimpleStringT` bir nesnede depolanan karakterlere doğrudan erişir.

### <a name="syntax"></a>Sözdizimi

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dize verilerine bir karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Hiçbir karakter kopyalanır; yalnızca bir işaretçi döndürülür. Bu operatöre dikkat edin. Karakter işaretçisini aldıktan sonra bir `CString` nesneyi değiştirirseniz, işaretçiyi geçersiz sayan bellek yeniden tahsisine neden olabilirsiniz.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::operator PCXSTR`

```cpp
// If the prototype of a function is known to the compiler,
// the PCXSTR cast operator may be invoked implicitly.

CSimpleString strSports(L"Soccer is Best!", pMgr);
WCHAR sz[1024];

wcscpy_s(sz, strSports);

// If the prototype isn't known or is a va_arg prototype,
// you must invoke the cast operator explicitly. For example,
// the va_arg part of a call to swprintf_s() needs the cast:

swprintf_s(sz, 1024, L"I think that %s!\n", (PCWSTR)strSports);

// While the format parameter is known to be an PCXSTR and
// therefore doesn't need the cast:

swprintf_s(sz, 1024, strSports);

// Note that some situations are ambiguous. This line will
// put the address of the strSports object to stdout:

wcout << strSports;

// while this line will put the content of the string out:

wcout << (PCWSTR)strSports;
```

## <a name="csimplestringtpcxstr"></a><a name="pcxstr"></a>CSimpleStringT::PCXSTR

Sabit bir dize için bir işaretçi.

### <a name="syntax"></a>Sözdizimi

```
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;
```

## <a name="csimplestringtpreallocate"></a><a name="preallocate"></a>CSimpleStringT::P

`CSimpleStringT` Nesne için belirli bir bayt miktarı ayırır.

### <a name="syntax"></a>Sözdizimi

```cpp
void Preallocate( int nLength);
```

#### <a name="parameters"></a>Parametreler

*nUzunluk*<br/>
Karakterlerdeki `CSimpleStringT` karakter arabelleği tam boyutu.

### <a name="remarks"></a>Açıklamalar

Nesne için belirli bir arabellek boyutu `CSimpleStringT` ayırmak için bu yöntemi çağırın.

`CSimpleStringT`karakter arabelleği için alan ayıramıyorsa STATUS_NO_MEMORY bir özel durum oluşturur. Varsayılan olarak, bellek ayırma WIN32 API işlevleri `HeapAlloc` veya `HeapReAlloc`.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::Preallocate`

```cpp
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```

## <a name="csimplestringtpxstr"></a><a name="pxstr"></a>CSimpleStringT::PXSTR

Dize için bir işaretçi.

### <a name="syntax"></a>Sözdizimi

```
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;
```

## <a name="csimplestringtreleasebuffer"></a><a name="releasebuffer"></a>CSimpleStringT::ReleaseArabellek

[GetBuffer](#getbuffer)tarafından ayrılan arabellek denetimini serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
void ReleaseBuffer(int nNewLength = -1);
```

#### <a name="parameters"></a>Parametreler

*nNewLength*<br/>
Karakterlerdeki dizenin yeni uzunluğu, null terminator'u sayma. Dize null sonlandırılırsa, -1 `CSimpleStringT` varsayılan değer boyutu dizenin geçerli uzunluğuna ayarlar.

### <a name="remarks"></a>Açıklamalar

Dize nesnesinin arabelleği yeniden tahsis etmek veya serbest serbest bu yöntemi arayın. Arabellekteki dize geçersiz olduğunu biliyorsanız, *nNewLength* bağımsız değişkenini atlayabilirsiniz. Dizeniz null sonlandırılmazsa, uzunluğunu belirtmek için *nNewLength'ı* kullanın. [GetBuffer](#getbuffer) tarafından döndürülen adres, aramadan `ReleaseBuffer` veya `CSimpleStringT` başka bir işlemden sonra geçersizdir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::ReleaseBuffer`

```cpp
const int bufferSize = 1024;
CSimpleString s(_T("abc"), pMgr);
LPTSTR p = s.GetBuffer(bufferSize);
_tcscpy_s(p, bufferSize, _T("abc"));

// use the buffer directly
ASSERT(s.GetLength() == 3);

// String length = 3
s.ReleaseBuffer();

// Surplus memory released, p is now invalid.
ASSERT(s.GetLength() == 3);

// Length still 3
```

## <a name="csimplestringtreleasebuffersetlength"></a><a name="releasebuffersetlength"></a>CSimpleStringT::ReleaseBufferSetLength

[GetBuffer](#getbuffer)tarafından ayrılan arabellek denetimini serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
void ReleaseBufferSetLength(int nNewLength);
```

#### <a name="parameters"></a>Parametreler

*nNewLength*<br/>
Serbest bırakılan dize uzunluğu

### <a name="remarks"></a>Açıklamalar

Bu işlev, dize nesnesi için geçerli bir uzunluk geçirilmesi gerektiği [dışında, ReleaseBuffer'a](#releasebuffer) işlevsel olarak benzer.

## <a name="csimplestringtsetat"></a><a name="setat"></a>CSimpleStringT::Setat

Bir nesneden tek `CSimpleStringT` bir karakter ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetAt(int iChar, XCHAR ch);
```

#### <a name="parameters"></a>Parametreler

*iChar*<br/>
`CSimpleStringT` Nesnedeki karakterin sıfır tabanlı dizini. *iChar* parametresi 0'dan büyük veya eşit ve [GetLength](#getlength)tarafından döndürülen değerden daha az olmalıdır.

*Caner*<br/>
Yeni karakter.

### <a name="remarks"></a>Açıklamalar

*iChar'da*bulunan karakterin üzerine yazmak için bu yöntemi arayın. *iChar* varolan dize sınırlarını aşarsa, bu yöntem dize büyütmez.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::SetAt`

```cpp
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
```

## <a name="csimplestringtsetmanager"></a><a name="setmanager"></a>CSimpleStringT::SetManager

Nesnenin bellek yöneticisini `CSimpleStringT` belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetManager(IAtlStringMgr* pStringMgr);
```

#### <a name="parameters"></a>Parametreler

*pStringMgr*<br/>
Yeni bellek yöneticisi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesne tarafından kullanılan yeni bir bellek yöneticisi belirtmek için bu yöntemi arayın. Bellek yöneticileri ve dize nesneleri hakkında daha fazla bilgi için Bellek [Yönetimi ve CStringT'e](../memory-management-with-cstringt.md)bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::SetManager`

```cpp
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```

## <a name="csimplestringtsetstring"></a><a name="setstring"></a>CSimpleStringT::SetString

`CSimpleStringT` Nesnenin dizesini ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetString(PCXSTR pszSrc, int nLength);
void SetString(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Parametreler

*pszSrc*<br/>
Null-sonlandırılan dize için bir işaretçi.

*nUzunluk*<br/>
*pszSrc*karakter sayısı nın sayısı.

### <a name="remarks"></a>Açıklamalar

Bir dizeyi `CSimpleStringT` nesneye kopyalayın. `SetString`arabellekteki eski dize verilerinin üzerine yazar.

`SetString` *PszSrc'nin* her iki sürümüde de null işaretçi olup olmadığını kontrol edin ve varsa E_INVALIDARG bir hata atın.

`SetString` *PszSrc'nin* tek parametreli sürümü, null-terminatedstring'e işaret eder.

`SetString` *PszSrc'nin* iki parametreli versiyonu da geçersiz bir dize olmasını bekler. Önce null terminator ile karşılaşmadığı sürece dize uzunluğu olarak *nLength* kullanır.

*PszSrc'nin* `SetString` iki parametreli sürümü, geçerli arabellekteki bir `CSimpleStringT`konuma işaret edip etmediğini de denetler. Bu özel durumda, `SetString` dize verilerini arabelleğine kopyalarken dize verilerinin üzerine yazmayan bir bellek kopyalama işlevi kullanır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::SetString`

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```

## <a name="csimplestringtstringlength"></a><a name="stringlength"></a>CSimpleStringT::StringLength

Belirtilen dizedeki karakter sayısını verir.

### <a name="syntax"></a>Sözdizimi

```
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```

#### <a name="parameters"></a>Parametreler

*Psz*<br/>
Null-sonlandırılan dize için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

*psz*karakter sayısı; null terminatör saymıyorum.

### <a name="remarks"></a>Açıklamalar

*Psz*tarafından işaret edilen dizedeki karakter sayısını almak için bu yöntemi arayın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::StringLength`

```cpp
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
```

## <a name="csimplestringttruncate"></a><a name="truncate"></a>CSimpleStringT::Truncate

Dizeyi yeni uzunluğa doğru truncates.

### <a name="syntax"></a>Sözdizimi

```cpp
void Truncate(int nNewLength);
```

#### <a name="parameters"></a>Parametreler

*nNewLength*<br/>
Dizenin yeni uzunluğu.

### <a name="remarks"></a>Açıklamalar

Dize içeriğini yeni uzunluğa ayırmak için bu yöntemi çağırın.

> [!NOTE]
> Bu, arabelleğe ayrılan uzunluğunu etkilemez. Geçerli arabelleği azaltmak veya artırmak için [FreeExtra](#freeextra) ve [Preallocate'a](#preallocate)bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ..000.000.000.000.000.000. `CSimpleStringT::Truncate`

```cpp
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
```

## <a name="csimplestringtunlockbuffer"></a><a name="unlockbuffer"></a>CSimpleStringT::UnlockAraffer

`CSimpleStringT` Nesnenin arabelleği kilidini açar.

### <a name="syntax"></a>Sözdizimi

```cpp
void UnlockBuffer() throw();
```

### <a name="remarks"></a>Açıklamalar

Dize referans sayısını 1'e sıfırlamak için bu yöntemi çağırın.

`CSimpleStringT` Yıkıcı, yıkıcı çağrıldığında `UnlockBuffer` arabelleğenin kilitli olmadığından emin olmak için otomatik olarak arar. Bu yöntemin bir örneği için [Bkz. LockBuffer.](#lockbuffer)

## <a name="csimplestringtcsimplestringt"></a><a name="dtor"></a>CSimpleStringt::~CSimpleStringt

Bir `CSimpleStringT` nesneyi yok eder.

### <a name="syntax"></a>Sözdizimi

```
~CSimpleStringT() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi yok etmek `CSimpleStringT` için bu yöntemi çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC Paylaşılan Sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
