---
title: CSimpleStringT sınıfı
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
ms.openlocfilehash: c033346b7a687a1c6778ad23e30ee0e73c787ad8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491440"
---
# <a name="csimplestringt-class"></a>CSimpleStringT sınıfı

Bu sınıf bir `CSimpleStringT` nesneyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <typename BaseType>
class CSimpleStringT
```

### <a name="parameters"></a>Parametreler

*BaseType*<br/>
Dize sınıfının karakter türü. Aşağıdakilerden biri olabilir:

- **char** (ANSI karakter dizeleri için).

- **wchar_t** (Unicode karakter dizeleri için).

- TCHAR (hem ANSI hem de Unicode karakter dizeleri için).

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleStringT::P CXSTR](#pcxstr)|Sabit dize işaretçisi.|
|[CSimpleStringT::P XSTR](#pxstr)|Dize işaretçisi.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleStringT:: CSimpleStringT](#ctor)|Nesneleri `CSimpleStringT` çeşitli şekillerde oluşturur.|
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleStringT:: Append](#append)|`CSimpleStringT` Varolan`CSimpleStringT` bir nesneye bir nesne ekler.|
|[CSimpleStringT:: AppendChar](#appendchar)|Varolan `CSimpleStringT` bir nesneye bir karakter ekler.|
|[CSimpleStringT:: CopyChars](#copychars)|Bir karakteri veya karakteri başka bir dizeye kopyalar.|
|[CSimpleStringT:: Copycharsoverladmış](#copycharsoverlapped)|Bir karakteri veya karakterleri, arabelleklerin çakıştığı başka bir dizeye kopyalar.|
|[CSimpleStringT:: Empty](#empty)|Bir dizeyi sıfır uzunluğuna zorlar.|
|[CSimpleStringT:: FreeExtra](#freeextra)|Dize nesnesi tarafından daha önce ayrılan ek belleği serbest bırakır.|
|[CSimpleStringT:: GetAllocLength](#getalloclength)|Bir `CSimpleStringT` nesnenin ayrılan uzunluğunu alır.|
|[CSimpleStringT:: GetAt](#getat)|Verilen konumdaki karakteri döndürür.|
|[CSimpleStringT:: GetBuffer](#getbuffer)|İçindeki karakterlere bir işaretçi döndürür `CSimpleStringT`.|
|[CSimpleStringT:: GetBufferSetLength](#getbuffersetlength)|İçindeki karakterlere bir `CSimpleStringT`işaretçi döndürür, belirtilen uzunluğa kesiliyor.|
|[CSimpleStringT:: GetLength](#getlength)|Bir `CSimpleStringT` nesnedeki karakter sayısını döndürür.|
|[CSimpleStringT:: GetManager](#getmanager)|`CSimpleStringT` Nesnenin bellek yöneticisini alır.|
|[CSimpleStringT:: GetString](#getstring)|Karakter dizesini alır|
|[CSimpleStringT:: IsEmpty](#isempty)|Bir `CSimpleStringT` nesnenin karakter içerip içermediğini test eder.|
|[CSimpleStringT:: LockBuffer](#lockbuffer)|Başvuru saymayı devre dışı bırakır ve arabellekteki dizeyi korur.|
|[CSimpleStringT::P yeniden tahsis](#preallocate)|Karakter arabelleği için belirli miktarda bellek ayırır.|
|[CSimpleStringT:: ReleaseBuffer](#releasebuffer)|Tarafından `GetBuffer`döndürülen arabelleğin denetimini yayınlar.|
|[CSimpleStringT:: ReleaseBufferSetLength](#releasebuffersetlength)|Tarafından `GetBuffer`döndürülen arabelleğin denetimini yayınlar.|
|[CSimpleStringT:: SetAt](#setat)|Verilen konumda bir karakter ayarlar.|
|[CSimpleStringT:: SetManager](#setmanager)|Bir `CSimpleStringT` nesnenin bellek yöneticisini ayarlar.|
|[CSimpleStringT:: SetString](#setstring)|Bir `CSimpleStringT` nesnenin dizesini ayarlar.|
|[CSimpleStringT:: StringLength](#stringlength)|Belirtilen dizedeki karakter sayısını döndürür.|
|[CSimpleStringT:: Truncate](#truncate)|Dizeyi belirtilen uzunluğa kırpar.|
|[CSimpleStringT:: UnlockBuffer](#unlockbuffer)|Başvuru saymayı ve arabellekteki dizeyi serbest bırakır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleStringT:: operator PCXSTR](#operator_pcxstr)|Bir `CSimpleStringT` nesnede depolanan karakterlere doğrudan C stili dize olarak erişir.|
|[CSimpleStringT:: işleci\[\]](#operator_at)|Verilen konumdaki karakteri döndürür — için `GetAt`işleç değiştirme.|
|[CSimpleStringT:: operator + =](#operator_add_eq)|Varolan bir dizenin sonuna yeni bir dize ekler.|
|[CSimpleStringT:: operator =](#operator_eq)|`CSimpleStringT` Nesnesine yeni bir değer atar.|

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT`, görsel C++tarafından desteklenen çeşitli dize sınıfları için temel sınıftır. Dize nesnesinin bellek yönetimi ve temel arabellek düzenlemesi için en düşük desteği sağlar. Daha gelişmiş dize nesneleri için bkz. [CStringT sınıfı](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpstr. h

## <a name="append"></a>CSimpleStringT:: Append

`CSimpleStringT` Varolan`CSimpleStringT` bir nesneye bir nesne ekler.

### <a name="syntax"></a>Sözdizimi

```
void Append(const CSimpleStringT& strSrc);
void Append(PCXSTR pszSrc, int nLength);
void Append(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Parametreler

*strSrc*<br/>
Eklenecek `CSimpleStringT` nesne.

*pszSrc*<br/>
Eklenecek karakterleri içeren bir dize işaretçisi.

*nLength*<br/>
Eklenecek karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Varolan `CSimpleStringT` bir nesneyi başka bir `CSimpleStringT` nesneye eklemek için bu yöntemi çağırın.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::Append`kullanımını gösterir.

```cpp
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```

##  <a name="appendchar"></a>CSimpleStringT:: AppendChar

Varolan `CSimpleStringT` bir nesneye bir karakter ekler.

### <a name="syntax"></a>Sözdizimi

```
void AppendChar(XCHAR ch);
```

#### <a name="parameters"></a>Parametreler

*ch*<br/>
Eklenecek karakter

### <a name="remarks"></a>Açıklamalar

Belirtilen karakteri varolan `CSimpleStringT` bir nesnenin sonuna eklemek için bu işlevi çağırın.

##  <a name="copychars"></a>CSimpleStringT:: CopyChars

Bir karakteri veya karakterleri `CSimpleStringT` nesnesine kopyalar.

### <a name="syntax"></a>Sözdizimi

```
static void CopyChars(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>Parametreler

*pchDest*<br/>
Karakter dizesinin işaretçisi.

*pchSrc*<br/>
Kopyalanacak karakterleri içeren bir dize işaretçisi.

*Nchar 'lar*<br/>
Kopyalanacak *pchSrc* karakter sayısı.

### <a name="remarks"></a>Açıklamalar

*PchSrc* 'Den *pchDest* dizesine karakter kopyalamak için bu yöntemi çağırın.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::CopyChars`kullanımını gösterir.

```cpp
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```

##  <a name="copycharsoverlapped"></a>CSimpleStringT:: Copycharsoverladmış

Bir karakteri veya karakterleri `CSimpleStringT` nesnesine kopyalar.

### <a name="syntax"></a>Sözdizimi

```
static void CopyCharsOverlapped(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>Parametreler

*pchDest*<br/>
Karakter dizesinin işaretçisi.

*pchSrc*<br/>
Kopyalanacak karakterleri içeren bir dize işaretçisi.

*Nchar 'lar*<br/>
Kopyalanacak *pchSrc* karakter sayısı.

### <a name="remarks"></a>Açıklamalar

*PchSrc* 'Den *pchDest* dizesine karakter kopyalamak için bu yöntemi çağırın. Aksine `CopyChars` ,`CopyCharsOverlapped` çakışan karakter arabelleklerinden kopyalamak için güvenli bir yöntem sağlar.

### <a name="example"></a>Örnek

[CSimpleStringT:: CopyChars](#copychars)örneğine veya kaynak koduna `CSimpleStringT::SetString` (atlsimpstr. h içinde bulunur) bakın.

##  <a name="ctor"></a>CSimpleStringT:: CSimpleStringT

Bir `CSimpleStringT` nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr);
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr);
CSimpleStringT(const CSimpleStringT& strSrc);
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw();
```

#### <a name="parameters"></a>Parametreler

*strSrc*<br/>
`CSimpleStringT` Bu`CSimpleStringT` nesneye Kopyalanacak varolan bir nesne.

*pchSrc*<br/>
Null ile değil, *nLength*uzunluklu bir karakter dizisine yönelik bir işaretçi.

*pszSrc*<br/>
Bu `CSimpleStringT` nesneye kopyalanacak null ile sonlandırılmış bir dize.

*nLength*<br/>
İçindeki `pch`karakterlerin sayısı.

*pStringMgr*<br/>
`CSimpleStringT` Nesnenin bellek Yöneticisi işaretçisi. Ve için `IAtlStringMgr` `CSimpleStringT`bellek yönetimi hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).

### <a name="remarks"></a>Açıklamalar

Yeni `CSimpleStringT` bir nesne oluşturun. Oluşturucular giriş verilerini yeni ayrılmış depolama alanına kopyalayacağından, bellek özel durumları oluşabilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ATL **typedef** `CSimpleString`kullanılarak öğesinin `CSimpleStringT::CSimpleStringT` kullanımını gösterir. `CSimpleString`, sınıf şablonunun `CSimpleStringT`yaygın olarak kullanılan bir özelleştirmesi.

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

##  <a name="empty"></a>CSimpleStringT:: Empty

Bu `CSimpleStringT` nesneyi boş bir dize yapar ve uygun şekilde belleği serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```
void Empty() throw();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz [. dizeler: CString özel durum](../cstring-exception-cleanup.md)Temizleme.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::Empty`kullanımını gösterir.

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

##  <a name="freeextra"></a>CSimpleStringT:: FreeExtra

Daha önce dize tarafından ayrılan ancak artık gerekli olmayan ek belleği serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```
void FreeExtra();
```

### <a name="remarks"></a>Açıklamalar

Bu, dize nesnesi tarafından tüketilen bellek ek yükünü azaltmalıdır. Yöntemi, arabelleği [GetLength](#getlength)tarafından döndürülen tam uzunluğa yeniden konumlandırır.

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

##  <a name="getalloclength"></a>CSimpleStringT:: GetAllocLength

Bir `CSimpleStringT` nesnenin ayrılan uzunluğunu alır.

### <a name="syntax"></a>Sözdizimi

```
int GetAllocLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne için ayrılan karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Bu `CSimpleStringT` nesne için ayrılan karakter sayısını öğrenmek için bu yöntemi çağırın. Bu işlevi çağırma örneği için [FreeExtra](#freeextra) bölümüne bakın.

##  <a name="getat"></a>CSimpleStringT:: GetAt

`CSimpleStringT` Nesnesinden bir karakter döndürür.

### <a name="syntax"></a>Sözdizimi

```
XCHAR GetAt(int iChar) const;
```

#### <a name="parameters"></a>Parametreler

*ICHAR*<br/>
`CSimpleStringT` Nesnedeki karakterin sıfır tabanlı dizini. *Ihar* parametresi 0 ' dan büyük veya buna eşit ve [GetLength](#getlength)tarafından döndürülen değerden küçük olmalıdır. Aksi takdirde `GetAt` , bir özel durum oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Dizedeki `XCHAR` belirtilen konumdaki karakteri içeren bir.

### <a name="remarks"></a>Açıklamalar

*ICHAR*tarafından belirtilen bir karakteri döndürmek için bu yöntemi çağırın. Aşırı yüklenmiş alt simge ( **[]** ) işleci için `GetAt`uygun bir diğer addır. Null Sonlandırıcı kullanılarak `GetAt`özel bir durum üretilmeden adreslenebilir. Ancak, tarafından `GetLength`sayılmaz ve döndürülen değer 0 ' dır.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl `CSimpleStringT::GetAt`kullanılacağını göstermektedir.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```

##  <a name="getbuffer"></a>CSimpleStringT:: GetBuffer

`CSimpleStringT` Nesnenin iç karakter arabelleğine yönelik bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```
PXSTR GetBuffer(int nMinBufferLength);
PXSTR GetBuffer();
```

#### <a name="parameters"></a>Parametreler

*nMinBufferLength*<br/>
Karakter arabelleğinin tutabileceğinden en az karakter sayısı. Bu değer, null Sonlandırıcı için boşluk içermez.

*NMinBufferLength* geçerli arabelleğin uzunluğundan daha büyükse, `GetBuffer` geçerli arabelleği yok eder, istenen boyutun bir arabelleği ile değiştirir ve nesne başvuru sayısını sıfıra sıfırlar. Daha önce bu arabellekte [LockBuffer](#lockbuffer) çağrılırsa, arabellek kilidini kaybedersiniz.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin `PXSTR` (null ile sonlandırılmış) karakter arabelleğinin bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesnenin arabellek içeriğini döndürmek için bu yöntemi çağırın. Döndürülen `PXSTR` bir sabit değildir ve bu nedenle `CSimpleStringT` içeriğin doğrudan değiştirilmesine izin verir.

Tarafından `GetBuffer` döndürülen işaretçiyi dize içeriklerini değiştirmek için kullanırsanız, başka `CSimpleStringT` bir üye yöntemi kullanmadan önce [ReleaseBuffer](#releasebuffer) öğesini çağırmanız gerekir.

Tarafından `GetBuffer` döndürülen adres, ' e yapılan `ReleaseBuffer` çağrıdan sonra geçerli olmayabilir çünkü `CSimpleStringT` ek `CSimpleStringT` işlemler arabelleğin yeniden ayrılmasına neden olabilir. Uzunluğunu değiştirmeyin arabelleği yeniden tahsis edilmez `CSimpleStringT`.

Arabellek belleği, `CSimpleStringT` nesne yok edildiğinde otomatik olarak serbest bırakılır.

Dize uzunluğunu kendiniz izlemenize sonra, Sonlandırıcı null karakterini eklememelisiniz. Ancak, ile `ReleaseBuffer`arabelleği serbest bırakıldığında son dize uzunluğunu belirtmeniz gerekir. Bir Sonlandırıcı null karakteri ekleymeniz durumunda, uzunluğu için-1 (varsayılan) geçişi yapmalısınız. `ReleaseBuffer`sonra arabellek uzunluğunu belirler.

`GetBuffer` İsteği karşılamak için yeterli bellek yoksa, bu yöntem bir CMemoryException * oluşturur.

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

##  <a name="getbuffersetlength"></a>CSimpleStringT:: GetBufferSetLength

`CSimpleStringT` Nesne için iç karakter arabelleğinin bir işaretçisini, *nLength*olarak belirtilen uzunlukla tam olarak eşleşmesi gerekiyorsa, kesilmesi veya büyümesini sağlar.

### <a name="syntax"></a>Sözdizimi

```
PXSTR GetBufferSetLength(int nLength);
```

#### <a name="parameters"></a>Parametreler

*nLength*<br/>
`CSimpleStringT` Karakter arabelleğinin karakter cinsinden tam boyutu.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin `PXSTR` (null ile sonlandırılmış) karakter arabelleğinin bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesnenin iç arabelleğinin belirtilen uzunluğunu almak için bu yöntemi çağırın. Döndürülen `PXSTR` işaretçi **const** değildir ve bu nedenle `CSimpleStringT` içeriğin doğrudan değiştirilmesine izin verir.

Dize içeriklerini değiştirmek için [GetBufferSetLength](#getbuffersetlength) tarafından döndürülen işaretçiyi kullanırsanız, diğer `ReleaseBuffer` `CSimpleStringT` herhangi bir yöntemi kullanmadan `CsimpleStringT` önce iç durumunu güncelleştirme ' yi çağırın.

Tarafından `GetBufferSetLength` döndürülen adres, ' e yapılan `ReleaseBuffer` çağrıdan sonra geçerli olmayabilir çünkü `CSimpleStringT` ek `CSimpleStringT` işlemler arabelleğin yeniden ayrılmasına neden olabilir. Uzunluğunu değiştirmeyin, arabellek yeniden atanmaz `CSimpleStringT`.

Arabellek belleği, `CSimpleStringT` nesne yok edildiğinde otomatik olarak serbest bırakılır.

Dize uzunluğunu kendiniz izlemenize devam ederseniz, Sonlandırıcı null karakterini eklemeyin. Kullanarak `ReleaseBuffer`arabelleği serbest aktardığınızda son dize uzunluğunu belirtmeniz gerekir. ' I çağırdığınızda `ReleaseBuffer`bir Sonlandırıcı null karakteri eklerseniz, `ReleaseBuffer`uzunluğu için-1 ' i (varsayılan) olarak geçirin ve `ReleaseBuffer` `strlen` uzunluğunu belirlemede arabelleğe alır.

Başvuru sayımı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- Windows SDK [başvuru sayımı aracılığıyla nesne yaşam sürelerini yönetme](/windows/win32/com/managing-object-lifetimes-through-reference-counting) .

- Windows SDK [başvuru sayımı uygulama](/windows/win32/com/implementing-reference-counting) .

- Windows SDK [başvuru sayılarını yönetme kuralları](/windows/win32/com/rules-for-managing-reference-counts) .

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::GetBufferSetLength`kullanımını gösterir.

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

##  <a name="getlength"></a>CSimpleStringT:: GetLength

`CSimpleStringT` Nesnedeki karakter sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```
int GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizedeki karakterlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Nesnedeki karakter sayısını döndürmek için bu yöntemi çağırın. Sayı null Sonlandırıcı içermiyor.

Çok baytlı karakter kümeleri (MBCS) `GetLength` için her 8 bitlik karakteri sayar; diğer bir deyişle, bir çok baytlı karakter içindeki bir öncü ve sondaki bayt iki bayt olarak sayılır. Bu işlevi çağırma örneği için [FreeExtra](#freeextra) bölümüne bakın.

##  <a name="getmanager"></a>CSimpleStringT:: GetManager

`CSimpleStringT` Nesnenin bellek yöneticisini alır.

### <a name="syntax"></a>Sözdizimi

```
IAtlStringMgr* GetManager() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSimpleStringT` Nesne için bellek Yöneticisi işaretçisi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesne tarafından kullanılan bellek yöneticisini almak için bu yöntemi çağırın. Bellek yöneticileri ve dize nesneleri hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).

##  <a name="getstring"></a>CSimpleStringT:: GetString

Karakter dizesini alır.

### <a name="syntax"></a>Sözdizimi

```
PCXSTR GetString() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Null ile sonlandırılmış bir karakter dizesinin işaretçisi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesneyle ilişkili karakter dizesini almak için bu yöntemi çağırın.

> [!NOTE]
>  Döndürülen `PCXSTR` işaretçi **const** olur ve doğrudan `CSimpleStringT` içerik değişikliğine izin vermez.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::GetString`kullanımını gösterir.

```cpp
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```

##  <a name="isempty"></a>CSimpleStringT:: IsEmpty

Boş koşul `CSimpleStringT` için bir nesneyi sınar.

### <a name="syntax"></a>Sözdizimi

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSimpleStringT` Nesnenin 0 uzunluğu varsa true, değilse false döndürür.

### <a name="remarks"></a>Açıklamalar

Nesnenin boş bir dize içerip içermediğini anlamak için bu yöntemi çağırın.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::IsEmpty`kullanımını gösterir.

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

##  <a name="lockbuffer"></a>CSimpleStringT:: LockBuffer

Başvuru saymayı devre dışı bırakır ve arabellekteki dizeyi korur.

### <a name="syntax"></a>Sözdizimi

```
PXSTR LockBuffer();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CSimpleStringT` nesne veya null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesne arabelleğini kilitlemek için bu yöntemi çağırın. Çağırarak `LockBuffer`, başvuru sayısı için-1 ile dizenin bir kopyasını oluşturursunuz. Başvuru sayısı değeri-1 olduğunda, arabellekteki dize "kilitli" durumunda olduğu kabul edilir. Kilitli durumda olan dize iki şekilde korunur:

- Başka hiçbir dize, bu dize kilitli dizeye atanmış olsa bile, kilitli dizedeki verilere başvuru alamaz.

- Başka bir dize kilitli dizeye kopyalansa bile, kilitli dize hiçbir şekilde başka bir dizeye başvurmayacaktır.

Arabellekteki dizeyi kilitleyerek, dizenin arabelleğe ait dışlamalı tutmanın bozulmadan kalacağından emin olursunuz.

İle `LockBuffer`işiniz bittiğinde, başvuru sayısını 1 ' e sıfırlamak için [UnlockBuffer](#unlockbuffer) ' ı çağırın.

> [!NOTE]
>  [GetBuffer](#getbuffer) öğesini kilitli bir arabellekte çağırırsanız ve `GetBuffer` parametreyi `nMinBufferLength` geçerli arabelleğin uzunluğundan daha büyük olarak ayarlarsanız, arabellek kilidini kaybedersiniz. Bu tür bir çağrı `GetBuffer` geçerli arabelleği yok eder, istenen boyutun arabelleği ile değiştirir ve başvuru sayısını sıfıra sıfırlar.

Başvuru sayımı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- Windows SDK [başvuru sayımı aracılığıyla nesne yaşam sürelerini yönetme](/windows/win32/com/managing-object-lifetimes-through-reference-counting)

- Windows SDK [başvuru sayımı uygulama](/windows/win32/com/implementing-reference-counting)

- Windows SDK [başvuru sayılarını yönetmeye yönelik kurallar](/windows/win32/com/rules-for-managing-reference-counts)

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::LockBuffer`kullanımını gösterir.

```cpp
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```

##  <a name="operator_at"></a>CSimpleStringT:: işleci\[\]

Karakter dizisinin tek bir karakterine erişmek için bu işlevi çağırın.

### <a name="syntax"></a>Sözdizimi

```
XCHAR operator[](int iChar) const;
```

#### <a name="parameters"></a>Parametreler

*ICHAR*<br/>
Dizedeki bir karakterin sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Aşırı yüklenmiş alt simge ( **[]** ) Işleci, *ıhar*'da sıfır tabanlı dizin tarafından belirtilen tek bir karakter döndürür. Bu işleç, [GetAt](#getat) üye işlevinin kullanışlı bir alternatifi.

> [!NOTE]
>  `CSimpleStringT`' Deki bir karakterin değerini almak için alt simge ( **[]** ) işlecini kullanabilirsiniz, ancak bunu, içindeki `CSimpleStringT`bir karakterin değerini değiştirmek için kullanamazsınız.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::operator []`kullanımını gösterir.

```cpp
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```

## <a name="operator_at"></a>CSimpleStringT:: işleci\[\]

Karakter dizisinin tek bir karakterine erişmek için bu işlevi çağırın.

### <a name="syntax"></a>Sözdizimi

```
XCHAR operator[](int iChar) const;
```

### <a name="parameters"></a>Parametreler

*ICHAR*<br/>
Dizedeki bir karakterin sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Aşırı yüklenmiş alt simge ( **[]** ) Işleci, *ıhar*'da sıfır tabanlı dizin tarafından belirtilen tek bir karakter döndürür. Bu işleç, [GetAt](#getat) üye işlevinin kullanışlı bir alternatifi.

> [!NOTE]
>  `CSimpleStringT`' Deki bir karakterin değerini almak için alt simge ( **[]** ) işlecini kullanabilirsiniz, ancak bunu, içindeki `CSimpleStringT`bir karakterin değerini değiştirmek için kullanamazsınız.

##  <a name="operator_add_eq"></a>CSimpleStringT:: operator + =

Varolan bir dizenin sonuna yeni bir dize veya karakter birleştirir.

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
Null ile sonlandırılmış bir dize işaretçisi.

*strSrc*<br/>
Varolan `CSimpleStringT` bir nesneye yönelik bir işaretçi.

*ch*<br/>
Eklenecek karakter.

### <a name="remarks"></a>Açıklamalar

İşleç başka `CSimpleStringT` bir nesneyi veya karakteri kabul eder. Bu `CSimpleStringT` nesneye eklenen karakterler için yeni depolama alanı ayrıldığından, bu birleştirme işlecini her kullandığınızda bellek özel durumlarının gerçekleşebileceğini unutmayın.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::operator +=`kullanımını gösterir.

```cpp
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```

##  <a name="operator_eq"></a>CSimpleStringT:: operator =

`CSimpleStringT` Nesnesine yeni bir değer atar.

### <a name="syntax"></a>Sözdizimi

```
CSimpleStringT& operator =(PCXSTR pszSrc);
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```

#### <a name="parameters"></a>Parametreler

*pszSrc*<br/>
Null ile sonlandırılmış bir dize işaretçisi.

*strSrc*<br/>
Varolan `CSimpleStringT` bir nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Hedef dize (sol tarafta) yeni verileri depolamak için zaten büyükse, yeni bir bellek ayırma gerçekleştirilmez. Yeni depolama genellikle sonuçta elde edilen `CSimpleStringT` nesneyi tutmak üzere ayrıldığından, atama işlecini her kullandığınızda bellek özel durumlarının gerçekleşebileceğini unutmayın.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::operator =`kullanımını gösterir.

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

##  <a name="operator_pcxstr"></a>CSimpleStringT:: operator PCXSTR

Bir `CSimpleStringT` nesnede depolanan karakterlere doğrudan C stili dize olarak erişir.

### <a name="syntax"></a>Sözdizimi

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin verilerine yönelik bir karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Hiçbir karakter kopyalanmaz; yalnızca bir işaretçi döndürülür. Bu işleçle dikkatli olun. Karakter işaretçisini elde ettikten `CString` sonra bir nesneyi değiştirirseniz, işaretçiyi geçersiz kılan belleğin yeniden alınmasına neden olabilirsiniz.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::operator PCXSTR`kullanımını gösterir.

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

##  <a name="pcxstr"></a>CSimpleStringT::P CXSTR

Sabit dize işaretçisi.

### <a name="syntax"></a>Sözdizimi

```
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;
```

##  <a name="preallocate"></a>CSimpleStringT::P yeniden tahsis

`CSimpleStringT` Nesne için belirli bir bayt miktarı ayırır.

### <a name="syntax"></a>Sözdizimi

```
void Preallocate( int nLength);
```

#### <a name="parameters"></a>Parametreler

*nLength*<br/>
`CSimpleStringT` Karakter arabelleğinin karakter cinsinden tam boyutu.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesne için belirli bir arabellek boyutunu ayırmak üzere bu yöntemi çağırın.

`CSimpleStringT`karakter arabelleği için alan ayıramadığında bir STATUS_NO_MEMORY özel durumu oluşturur. Varsayılan olarak, bellek ayırma wın32 API işlevleri `HeapAlloc` veya `HeapReAlloc`tarafından gerçekleştirilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::Preallocate`kullanımını gösterir.

```cpp
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```

##  <a name="pxstr"></a>CSimpleStringT::P XSTR

Dize işaretçisi.

### <a name="syntax"></a>Sözdizimi

```
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;
```

##  <a name="releasebuffer"></a>CSimpleStringT:: ReleaseBuffer

[GetBuffer](#getbuffer)tarafından ayrılan arabelleğin denetimini yayınlar.

### <a name="syntax"></a>Sözdizimi

```
void ReleaseBuffer(int nNewLength = -1);
```

#### <a name="parameters"></a>Parametreler

*nNewLength*<br/>
Dizenin karakter cinsinden yeni uzunluğu, null sonlandırıcıyı saymaz. Dize null sonlandırılırsa,-1 varsayılan değeri dizenin geçerli uzunluğuna ayarlanır `CSimpleStringT` .

### <a name="remarks"></a>Açıklamalar

Dize nesnesinin arabelleğini yeniden ayırmak veya boşaltmak için bu yöntemi çağırın. Arabellekteki dizenin null sonlandırıldığını biliyorsanız, *nNewLength* bağımsız değişkenini atlayabilirsiniz. Dizeniz null sonlandırılırsa, uzunluğunu belirtmek için *nNewLength* kullanın. [GetBuffer](#getbuffer) tarafından döndürülen adres, `ReleaseBuffer` ya da başka `CSimpleStringT` bir işlem çağrısından sonra geçersizdir.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::ReleaseBuffer`kullanımını gösterir.

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

##  <a name="releasebuffersetlength"></a>CSimpleStringT:: ReleaseBufferSetLength

[GetBuffer](#getbuffer)tarafından ayrılan arabelleğin denetimini yayınlar.

### <a name="syntax"></a>Sözdizimi

```
void ReleaseBufferSetLength(int nNewLength);
```

#### <a name="parameters"></a>Parametreler

*nNewLength*<br/>
Serbest bırakılmakta olan dizenin uzunluğu

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir dize nesnesi için geçerli bir uzunluk iletilmesi dışında, işleve [ReleaseBuffer](#releasebuffer) ile benzerdir.

##  <a name="setat"></a>CSimpleStringT:: SetAt

`CSimpleStringT` Nesnesinden tek bir karakter ayarlar.

### <a name="syntax"></a>Sözdizimi

```
void SetAt(int iChar, XCHAR ch);
```

#### <a name="parameters"></a>Parametreler

*ICHAR*<br/>
`CSimpleStringT` Nesnedeki karakterin sıfır tabanlı dizini. *Ihar* parametresi 0 ' dan büyük veya buna eşit ve [GetLength](#getlength)tarafından döndürülen değerden küçük olmalıdır.

*ch*<br/>
Yeni karakter.

### <a name="remarks"></a>Açıklamalar

*ICHAR*konumunda bulunan karakterin üzerine yazmak için bu yöntemi çağırın. Bu yöntem, *ıhar* varolan dizenin sınırlarını aşarsa dizeyi genişletmeyecektir.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::SetAt`kullanımını gösterir.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
```

##  <a name="setmanager"></a>CSimpleStringT:: SetManager

`CSimpleStringT` Nesnenin bellek yöneticisini belirtir.

### <a name="syntax"></a>Sözdizimi

```
void SetManager(IAtlStringMgr* pStringMgr);
```

#### <a name="parameters"></a>Parametreler

*pStringMgr*<br/>
Yeni bellek yöneticisine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesnesi tarafından kullanılan yeni bir bellek yöneticisi belirtmek için bu yöntemi çağırın. Bellek yöneticileri ve dize nesneleri hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::SetManager`kullanımını gösterir.

```cpp
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```

##  <a name="setstring"></a>CSimpleStringT:: SetString

Bir `CSimpleStringT` nesnenin dizesini ayarlar.

### <a name="syntax"></a>Sözdizimi

```
void SetString(PCXSTR pszSrc, int nLength);
void SetString(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Parametreler

*pszSrc*<br/>
Null ile sonlandırılmış bir dize işaretçisi.

*nLength*<br/>
*PszSrc*içindeki karakterlerin sayısı.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesnesine bir dize kopyalayın. `SetString`Arabellekteki eski dize verilerinin üzerine yazar.

Her iki sürümü `SetString` de *pszSrc* 'nin null bir işaretçi olup olmadığını denetler ve varsa, bir E_INVALIDARG hatası oluşturur.

Öğesinin `SetString` tek parametreli sürümü *pszSrc* 'in null ile sonlandırılmış bir dizeye işaret etmek bekler.

Öğesinin `SetString` iki parametreli sürümü de *pszSrc* 'nin null ile sonlandırılmış bir dize olmasını bekler. İlk olarak bir null Sonlandırıcı ile karşılaşmadığı sürece dize uzunluğu olarak *nLength* kullanır.

İki parametreli sürümü, `SetString` *pszSrc* 'nin içindeki `CSimpleStringT`geçerli arabellekte bir konuma işaret ettiğini de denetler. Bu özel durumda, `SetString` dize verilerini arabelleğine geri kopyalayan dize verilerinin üzerine yazmayan bir bellek kopyalama işlevi kullanır.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::SetString`kullanımını gösterir.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```

##  <a name="stringlength"></a>CSimpleStringT:: StringLength

Belirtilen dizedeki karakter sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```

#### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Null ile sonlandırılmış bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

*PSZ*; içindeki karakter sayısı null Sonlandırıcı sayılıyor.

### <a name="remarks"></a>Açıklamalar

*PSZ*tarafından işaret edilen dizedeki karakter sayısını almak için bu yöntemi çağırın.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::StringLength`kullanımını gösterir.

```cpp
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
```

##  <a name="truncate"></a>CSimpleStringT:: Truncate

Dizeyi yeni uzunluğa kırpar.

### <a name="syntax"></a>Sözdizimi

```
void Truncate(int nNewLength);
```

#### <a name="parameters"></a>Parametreler

*nNewLength*<br/>
Dizenin yeni uzunluğu.

### <a name="remarks"></a>Açıklamalar

Dizenin içeriğini yeni uzunluğa kesmek için bu yöntemi çağırın.

> [!NOTE]
>  Bu, arabelleğin ayrılan uzunluğunu etkilemez. Geçerli arabelleği azaltmak veya artırmak için bkz. [FreeExtra](#freeextra) ve [preallocate](#preallocate).

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin `CSimpleStringT::Truncate`kullanımını gösterir.

```cpp
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
```

##  <a name="unlockbuffer"></a>CSimpleStringT:: UnlockBuffer

`CSimpleStringT` Nesnesinin arabelleğini kaldırır.

### <a name="syntax"></a>Sözdizimi

```
void UnlockBuffer() throw();
```

### <a name="remarks"></a>Açıklamalar

Dizenin başvuru sayısını 1 ' e sıfırlamak için bu yöntemi çağırın.

Yıkıcı çağrıldığında arabelleğin kilitlenmemesini sağlamak için otomatik olarak çağırır `UnlockBuffer`. `CSimpleStringT` Bu yöntemin bir örneği için bkz. [LockBuffer](#lockbuffer).

##  <a name="dtor"></a>CSimpleStringT:: ~ CSimpleStringT

Bir `CSimpleStringT` nesneyi yok eder.

### <a name="syntax"></a>Sözdizimi

```
~CSimpleStringT() throw();
```

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Nesneyi yok etmek için bu yöntemi çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
