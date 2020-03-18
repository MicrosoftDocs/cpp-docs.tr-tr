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
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418197"
---
# <a name="csimplestringt-class"></a>CSimpleStringT sınıfı

Bu sınıf bir `CSimpleStringT` nesnesini temsil eder.

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

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleStringT::P CXSTR](#pcxstr)|Sabit dize işaretçisi.|
|[CSimpleStringT::P XSTR](#pxstr)|Dize işaretçisi.|

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleStringT:: CSimpleStringT](#ctor)|Çeşitli yollarla `CSimpleStringT` nesneleri oluşturur.|
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleStringT:: Append](#append)|Varolan bir `CSimpleStringT` nesnesine bir `CSimpleStringT` nesnesi ekler.|
|[CSimpleStringT:: AppendChar](#appendchar)|Varolan bir `CSimpleStringT` nesnesine bir karakter ekler.|
|[CSimpleStringT:: CopyChars](#copychars)|Bir karakteri veya karakteri başka bir dizeye kopyalar.|
|[CSimpleStringT:: Copycharsoverladmış](#copycharsoverlapped)|Bir karakteri veya karakterleri, arabelleklerin çakıştığı başka bir dizeye kopyalar.|
|[CSimpleStringT:: Empty](#empty)|Bir dizeyi sıfır uzunluğuna zorlar.|
|[CSimpleStringT:: FreeExtra](#freeextra)|Dize nesnesi tarafından daha önce ayrılan ek belleği serbest bırakır.|
|[CSimpleStringT:: GetAllocLength](#getalloclength)|`CSimpleStringT` nesnesinin ayrılan uzunluğunu alır.|
|[CSimpleStringT:: GetAt](#getat)|Verilen konumdaki karakteri döndürür.|
|[CSimpleStringT:: GetBuffer](#getbuffer)|`CSimpleStringT`karakterlere bir işaretçi döndürür.|
|[CSimpleStringT:: GetBufferSetLength](#getbuffersetlength)|`CSimpleStringT`karakterlerin bir işaretçisini belirtilen uzunluğa kırpmadan döndürür.|
|[CSimpleStringT:: GetLength](#getlength)|`CSimpleStringT` nesnesindeki karakter sayısını döndürür.|
|[CSimpleStringT:: GetManager](#getmanager)|`CSimpleStringT` nesnesinin bellek yöneticisini alır.|
|[CSimpleStringT:: GetString](#getstring)|Karakter dizesini alır|
|[CSimpleStringT:: IsEmpty](#isempty)|`CSimpleStringT` nesnenin karakter içerip içermediğini sınar.|
|[CSimpleStringT:: LockBuffer](#lockbuffer)|Başvuru saymayı devre dışı bırakır ve arabellekteki dizeyi korur.|
|[CSimpleStringT::P yeniden tahsis](#preallocate)|Karakter arabelleği için belirli miktarda bellek ayırır.|
|[CSimpleStringT:: ReleaseBuffer](#releasebuffer)|`GetBuffer`tarafından döndürülen arabelleğin denetimini yayınlar.|
|[CSimpleStringT:: ReleaseBufferSetLength](#releasebuffersetlength)|`GetBuffer`tarafından döndürülen arabelleğin denetimini yayınlar.|
|[CSimpleStringT:: SetAt](#setat)|Verilen konumda bir karakter ayarlar.|
|[CSimpleStringT:: SetManager](#setmanager)|Bir `CSimpleStringT` nesnesinin bellek yöneticisini ayarlar.|
|[CSimpleStringT:: SetString](#setstring)|Bir `CSimpleStringT` nesnesinin dizesini ayarlar.|
|[CSimpleStringT:: StringLength](#stringlength)|Belirtilen dizedeki karakter sayısını döndürür.|
|[CSimpleStringT:: Truncate](#truncate)|Dizeyi belirtilen uzunluğa kırpar.|
|[CSimpleStringT:: UnlockBuffer](#unlockbuffer)|Başvuru saymayı ve arabellekteki dizeyi serbest bırakır.|

### <a name="public-operators"></a>Genel İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleStringT:: operator PCXSTR](#operator_pcxstr)|`CSimpleStringT` nesnesinde depolanan karakterlere doğrudan C stili dize olarak erişir.|
|[CSimpleStringT:: operator\[\]](#operator_at)|Verilen konumdaki karakteri döndürür — `GetAt`için işleç değiştirme.|
|[CSimpleStringT:: operator + =](#operator_add_eq)|Varolan bir dizenin sonuna yeni bir dize ekler.|
|[CSimpleStringT:: operator =](#operator_eq)|`CSimpleStringT` nesnesine yeni bir değer atar.|

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT`, görsel C++tarafından desteklenen çeşitli dize sınıfları için temel sınıftır. Dize nesnesinin bellek yönetimi ve temel arabellek düzenlemesi için en düşük desteği sağlar. Daha gelişmiş dize nesneleri için bkz. [CStringT sınıfı](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpstr. h

## <a name="append"></a>CSimpleStringT:: Append

Varolan bir `CSimpleStringT` nesnesine bir `CSimpleStringT` nesnesi ekler.

### <a name="syntax"></a>Sözdizimi

```
void Append(const CSimpleStringT& strSrc);
void Append(PCXSTR pszSrc, int nLength);
void Append(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Parametreler

*strSrc*<br/>
Eklenecek `CSimpleStringT` nesnesi.

*pszSrc*<br/>
Eklenecek karakterleri içeren bir dize işaretçisi.

*nLength*<br/>
Eklenecek karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Varolan bir `CSimpleStringT` nesnesini başka bir `CSimpleStringT` nesnesine eklemek için bu yöntemi çağırın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::Append`kullanımını gösterir.

```cpp
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```

##  <a name="appendchar"></a>CSimpleStringT:: AppendChar

Varolan bir `CSimpleStringT` nesnesine bir karakter ekler.

### <a name="syntax"></a>Sözdizimi

```
void AppendChar(XCHAR ch);
```

#### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*<br/>
Eklenecek karakter

### <a name="remarks"></a>Açıklamalar

Belirtilen karakteri varolan bir `CSimpleStringT` nesnesinin sonuna eklemek için bu işlevi çağırın.

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

Aşağıdaki örnek, `CSimpleStringT::CopyChars`kullanımını gösterir.

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

*PchSrc* 'Den *pchDest* dizesine karakter kopyalamak için bu yöntemi çağırın. `CopyChars`aksine `CopyCharsOverlapped`, çakışan karakter arabelleklerinden kopyalamak için güvenli bir yöntem sağlar.

### <a name="example"></a>Örnek

[CSimpleStringT:: CopyChars](#copychars)örneğine veya `CSimpleStringT::SetString` için kaynak koda (atlsimpstr. h içinde bulunur) bakın.

##  <a name="ctor"></a>CSimpleStringT:: CSimpleStringT

`CSimpleStringT` nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr);
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr);
CSimpleStringT(const CSimpleStringT& strSrc);
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw();
```

#### <a name="parameters"></a>Parametreler

*strSrc*<br/>
Bu `CSimpleStringT` nesnesine Kopyalanacak varolan bir `CSimpleStringT` nesnesi.

*pchSrc*<br/>
Null ile değil, *nLength*uzunluklu bir karakter dizisine yönelik bir işaretçi.

*pszSrc*<br/>
Bu `CSimpleStringT` nesnesine kopyalanacak null ile sonlandırılmış bir dize.

*nLength*<br/>
`pch`karakterlerin sayısı.

*pStringMgr*<br/>
`CSimpleStringT` nesnesinin bellek yöneticisine yönelik bir işaretçi. `CSimpleStringT`için `IAtlStringMgr` ve bellek yönetimi hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).

### <a name="remarks"></a>Açıklamalar

Yeni bir `CSimpleStringT` nesnesi oluşturun. Oluşturucular giriş verilerini yeni ayrılmış depolama alanına kopyalayacağından, bellek özel durumları oluşabilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ATL **typedef** `CSimpleString`kullanılarak `CSimpleStringT::CSimpleStringT` kullanımını gösterir. `CSimpleString`, `CSimpleStringT`sınıf şablonunun yaygın olarak kullanılan bir özelleştirmesi.

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

Bu `CSimpleStringT` nesnesini boş bir dize yapar ve uygun şekilde belleği serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```
void Empty() throw();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [dizeler: CString özel durum temizleme](../cstring-exception-cleanup.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::Empty`kullanımını gösterir.

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

`CSimpleStringT` nesnesinin ayrılan uzunluğunu alır.

### <a name="syntax"></a>Sözdizimi

```
int GetAllocLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne için ayrılan karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Bu `CSimpleStringT` nesnesi için ayrılan karakter sayısını öğrenmek için bu yöntemi çağırın. Bu işlevi çağırma örneği için [FreeExtra](#freeextra) bölümüne bakın.

##  <a name="getat"></a>CSimpleStringT:: GetAt

`CSimpleStringT` nesnesinden bir karakter döndürür.

### <a name="syntax"></a>Sözdizimi

```
XCHAR GetAt(int iChar) const;
```

#### <a name="parameters"></a>Parametreler

*ICHAR*<br/>
`CSimpleStringT` nesnesindeki karakterin sıfır tabanlı dizini. *Ihar* parametresi 0 ' dan büyük veya buna eşit ve [GetLength](#getlength)tarafından döndürülen değerden küçük olmalıdır. Aksi takdirde `GetAt` bir özel durum oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Dizedeki belirtilen konumda bulunan karakteri içeren bir `XCHAR`.

### <a name="remarks"></a>Açıklamalar

*ICHAR*tarafından belirtilen bir karakteri döndürmek için bu yöntemi çağırın. Aşırı yüklenmiş alt simge ( **[]** ) işleci `GetAt`için kullanışlı bir diğer addır. Null Sonlandırıcı, `GetAt`kullanılarak özel durum üretilmeden adreslenebilir. Ancak, `GetLength`tarafından sayılmaz ve döndürülen değer 0 ' dır.

### <a name="example"></a>Örnek

Aşağıdaki örnek `CSimpleStringT::GetAt`nasıl kullanacağınızı gösterir.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```

##  <a name="getbuffer"></a>CSimpleStringT:: GetBuffer

`CSimpleStringT` nesnesi için iç karakter arabelleğine yönelik bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```
PXSTR GetBuffer(int nMinBufferLength);
PXSTR GetBuffer();
```

#### <a name="parameters"></a>Parametreler

*nMinBufferLength*<br/>
Karakter arabelleğinin tutabileceğinden en az karakter sayısı. Bu değer, null Sonlandırıcı için boşluk içermez.

*NMinBufferLength* geçerli arabelleğin uzunluğundan fazlaysa, `GetBuffer` geçerli arabelleği yok eder, istenen boyutun arabelleği ile değiştirir ve nesne başvuru sayısını sıfıra sıfırlar. Daha önce bu arabellekte [LockBuffer](#lockbuffer) çağrılırsa, arabellek kilidini kaybedersiniz.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin (null ile sonlandırılmış) karakter arabelleğinin `PXSTR` işaretçisi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` nesnesinin arabellek içeriğini döndürmek için bu yöntemi çağırın. Döndürülen `PXSTR` bir sabit değildir ve bu nedenle `CSimpleStringT` içeriğinin doğrudan değiştirilmesine izin verir.

Dize içeriklerini değiştirmek için `GetBuffer` tarafından döndürülen işaretçiyi kullanırsanız, başka bir `CSimpleStringT` üye yöntemi kullanmadan önce [ReleaseBuffer](#releasebuffer) öğesini çağırmanız gerekir.

`GetBuffer` tarafından döndürülen adres, `ReleaseBuffer` çağrısından sonra geçerli olmayabilir, çünkü ek `CSimpleStringT` işlemleri `CSimpleStringT` arabelleğinin yeniden ayrılmasına neden olabilir. `CSimpleStringT`uzunluğunu değiştirmeyin, arabellek yeniden ayrılmaz.

`CSimpleStringT` nesnesi yok edildiğinde arabellek belleği otomatik olarak serbest bırakılır.

Dize uzunluğunu kendiniz izlemenize sonra, Sonlandırıcı null karakterini eklememelisiniz. Ancak, `ReleaseBuffer`ile arabelleği serbest bırakdığınızda son dize uzunluğunu belirtmeniz gerekir. Bir Sonlandırıcı null karakteri ekleymeniz durumunda, uzunluğu için-1 (varsayılan) geçişi yapmalısınız. `ReleaseBuffer` daha sonra arabellek uzunluğunu belirler.

`GetBuffer` isteğini karşılamak için yeterli bellek yoksa, bu yöntem bir CMemoryException * oluşturur.

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

`CSimpleStringT` nesne için iç karakter arabelleğine yönelik bir işaretçi döndürür, gerekirse, *nLength*belirtilen uzunlukla tam olarak eşleşmesi gerekiyorsa, bu dosyanın uzunluğu kesiliyor veya artıyor.

### <a name="syntax"></a>Sözdizimi

```
PXSTR GetBufferSetLength(int nLength);
```

#### <a name="parameters"></a>Parametreler

*nLength*<br/>
`CSimpleStringT` karakter arabelleğinin karakter cinsinden tam boyutu.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin (null ile sonlandırılmış) karakter arabelleğinin `PXSTR` işaretçisi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` nesnesinin iç arabelleğinin belirtilen uzunluğunu almak için bu yöntemi çağırın. Döndürülen `PXSTR` işaretçi **const** değildir ve bu nedenle `CSimpleStringT` içeriğinin doğrudan değiştirilmesine izin verir.

Dize içeriklerini değiştirmek için [GetBufferSetLength](#getbuffersetlength) tarafından döndürülen işaretçiyi kullanırsanız, başka bir `CSimpleStringT` yöntemini kullanmadan önce `CsimpleStringT` iç durumunu güncelleştirmek için `ReleaseBuffer` çağırın.

`GetBufferSetLength` tarafından döndürülen adres, `ReleaseBuffer` çağrısından sonra geçerli olmayabilir, çünkü ek `CSimpleStringT` işlemleri `CSimpleStringT` arabelleğinin yeniden ayrılmasına neden olabilir. `CSimpleStringT`uzunluğunu değiştirmeyin, arabellek yeniden atanmaz.

`CSimpleStringT` nesnesi yok edildiğinde arabellek belleği otomatik olarak serbest bırakılır.

Dize uzunluğunu kendiniz izlemenize devam ederseniz, Sonlandırıcı null karakterini eklemeyin. `ReleaseBuffer`kullanarak arabelleği serbest aktardığınızda son dize uzunluğunu belirtmeniz gerekir. `ReleaseBuffer`çağırdığınızda bir Sonlandırıcı null karakteri eklerseniz, `ReleaseBuffer`uzunluğu için-1 (varsayılan) değerini geçirin ve `ReleaseBuffer` uzunluğunu belirlemede arabellek üzerinde `strlen` yapar.

Başvuru sayımı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- Windows SDK [başvuru sayımı aracılığıyla nesne yaşam sürelerini yönetme](/windows/win32/com/managing-object-lifetimes-through-reference-counting) .

- Windows SDK [başvuru sayımı uygulama](/windows/win32/com/implementing-reference-counting) .

- Windows SDK [başvuru sayılarını yönetme kuralları](/windows/win32/com/rules-for-managing-reference-counts) .

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::GetBufferSetLength`kullanımını gösterir.

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

`CSimpleStringT` nesnesindeki karakter sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```
int GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizedeki karakterlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Nesnedeki karakter sayısını döndürmek için bu yöntemi çağırın. Sayı null Sonlandırıcı içermiyor.

Çok baytlı karakter kümeleri (MBCS) için, `GetLength` her 8 bit karakteri sayar; diğer bir deyişle, bir çok baytlı karakter içindeki bir lider ve sondaki bayt iki bayt olarak sayılır. Bu işlevi çağırma örneği için [FreeExtra](#freeextra) bölümüne bakın.

##  <a name="getmanager"></a>CSimpleStringT:: GetManager

`CSimpleStringT` nesnesinin bellek yöneticisini alır.

### <a name="syntax"></a>Sözdizimi

```
IAtlStringMgr* GetManager() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSimpleStringT` nesnesi için bellek Yöneticisi işaretçisi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` nesnesi tarafından kullanılan bellek yöneticisini almak için bu yöntemi çağırın. Bellek yöneticileri ve dize nesneleri hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).

##  <a name="getstring"></a>CSimpleStringT:: GetString

Karakter dizesini alır.

### <a name="syntax"></a>Sözdizimi

```
PCXSTR GetString() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Null ile sonlandırılmış bir karakter dizesinin işaretçisi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` nesnesiyle ilişkili karakter dizesini almak için bu yöntemi çağırın.

> [!NOTE]
>  Döndürülen `PCXSTR` işaretçi **const** ve `CSimpleStringT` içeriğinin doğrudan değiştirilmesine izin vermez.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::GetString`kullanımını gösterir.

```cpp
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```

##  <a name="isempty"></a>CSimpleStringT:: IsEmpty

Boş koşul için `CSimpleStringT` nesnesini sınar.

### <a name="syntax"></a>Sözdizimi

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSimpleStringT` nesnesi 0 uzunluğa sahipse TRUE değerini döndürür; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Nesnenin boş bir dize içerip içermediğini anlamak için bu yöntemi çağırın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::IsEmpty`kullanımını gösterir.

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

`CSimpleStringT` nesnesine veya null ile sonlandırılmış dizeye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` nesnesinin arabelleğini kilitlemek için bu yöntemi çağırın. `LockBuffer`çağırarak, başvuru sayısı için-1 ile dizenin bir kopyasını oluşturursunuz. Başvuru sayısı değeri-1 olduğunda, arabellekteki dize "kilitli" durumunda olduğu kabul edilir. Kilitli durumda olan dize iki şekilde korunur:

- Başka hiçbir dize, bu dize kilitli dizeye atanmış olsa bile, kilitli dizedeki verilere başvuru alamaz.

- Başka bir dize kilitli dizeye kopyalansa bile, kilitli dize hiçbir şekilde başka bir dizeye başvurmayacaktır.

Arabellekteki dizeyi kilitleyerek, dizenin arabelleğe ait dışlamalı tutmanın bozulmadan kalacağından emin olursunuz.

`LockBuffer`ile işiniz bittiğinde, başvuru sayısını 1 ' e sıfırlamak için [UnlockBuffer](#unlockbuffer) ' ı çağırın.

> [!NOTE]
>  [GetBuffer](#getbuffer) 'ı kilitli bir arabellekte çağırırsanız ve `GetBuffer` parametresi `nMinBufferLength` geçerli arabelleğin uzunluğundan daha büyük olarak ayarlarsanız, arabellek kilidini kaybedersiniz. Bu tür bir `GetBuffer` çağrı geçerli arabelleği yok eder, istenen boyutun arabelleği ile değiştirir ve başvuru sayısını sıfıra sıfırlar.

Başvuru sayımı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- Windows SDK [başvuru sayımı aracılığıyla nesne yaşam sürelerini yönetme](/windows/win32/com/managing-object-lifetimes-through-reference-counting)

- Windows SDK [başvuru sayımı uygulama](/windows/win32/com/implementing-reference-counting)

- Windows SDK [başvuru sayılarını yönetmeye yönelik kurallar](/windows/win32/com/rules-for-managing-reference-counts)

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::LockBuffer`kullanımını gösterir.

```cpp
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```

##  <a name="operator_at"></a>CSimpleStringT:: operator\[\]

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
>  Bir `CSimpleStringT`karakterin değerini almak için alt simge ( **[]** ) işlecini kullanabilirsiniz, ancak bir `CSimpleStringT`karakterin değerini değiştirmek için kullanamazsınız.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::operator []`kullanımını gösterir.

```cpp
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```

## <a name="operator_at"></a>CSimpleStringT:: operator \[\]

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
>  Bir `CSimpleStringT`karakterin değerini almak için alt simge ( **[]** ) işlecini kullanabilirsiniz, ancak bir `CSimpleStringT`karakterin değerini değiştirmek için kullanamazsınız.

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
Varolan bir `CSimpleStringT` nesnesine yönelik bir işaretçi.

*denetleyebilirsiniz*<br/>
Eklenecek karakter.

### <a name="remarks"></a>Açıklamalar

İşleç başka bir `CSimpleStringT` nesnesini veya bir karakteri kabul eder. Bu `CSimpleStringT` nesnesine eklenen karakterler için yeni depolama alanı ayrıldığından, bu birleştirme işlecini her kullandığınızda bellek özel durumlarının gerçekleşebileceğini unutmayın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::operator +=`kullanımını gösterir.

```cpp
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```

##  <a name="operator_eq"></a>CSimpleStringT:: operator =

`CSimpleStringT` nesnesine yeni bir değer atar.

### <a name="syntax"></a>Sözdizimi

```
CSimpleStringT& operator =(PCXSTR pszSrc);
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```

#### <a name="parameters"></a>Parametreler

*pszSrc*<br/>
Null ile sonlandırılmış bir dize işaretçisi.

*strSrc*<br/>
Varolan bir `CSimpleStringT` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Hedef dize (sol tarafta) yeni verileri depolamak için zaten büyükse, yeni bir bellek ayırma gerçekleştirilmez. Yeni depolama, sonuçta elde edilen `CSimpleStringT` nesnesini tutmak için genellikle ayrıldığından, atama işlecini her kullandığınızda bellek özel durumlarının gerçekleşebileceğini unutmayın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::operator =`kullanımını gösterir.

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

`CSimpleStringT` nesnesinde depolanan karakterlere doğrudan C stili dize olarak erişir.

### <a name="syntax"></a>Sözdizimi

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin verilerine yönelik bir karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Hiçbir karakter kopyalanmaz; yalnızca bir işaretçi döndürülür. Bu işleçle dikkatli olun. Karakter işaretçisini elde ettikten sonra bir `CString` nesnesini değiştirirseniz, işaretçiyi geçersiz kılan belleğin bir yeniden tahsisat olmasına neden olabilirsiniz.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::operator PCXSTR`kullanımını gösterir.

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

`CSimpleStringT` nesnesi için belirli bir bayt miktarını ayırır.

### <a name="syntax"></a>Sözdizimi

```
void Preallocate( int nLength);
```

#### <a name="parameters"></a>Parametreler

*nLength*<br/>
`CSimpleStringT` karakter arabelleğinin karakter cinsinden tam boyutu.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` nesnesi için belirli bir arabellek boyutunu ayırmak üzere bu yöntemi çağırın.

`CSimpleStringT`, karakter arabelleği için alan ayıramadığında bir STATUS_NO_MEMORY özel durumu oluşturur. Varsayılan olarak, bellek ayırma, `HeapAlloc` veya `HeapReAlloc`WIN32 API işlevleri tarafından gerçekleştirilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::Preallocate`kullanımını gösterir.

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
Dizenin karakter cinsinden yeni uzunluğu, null sonlandırıcıyı saymaz. Dize null sonlandırılırsa,-1 varsayılan değer `CSimpleStringT` boyutunu dizenin geçerli uzunluğuna ayarlar.

### <a name="remarks"></a>Açıklamalar

Dize nesnesinin arabelleğini yeniden ayırmak veya boşaltmak için bu yöntemi çağırın. Arabellekteki dizenin null sonlandırıldığını biliyorsanız, *nNewLength* bağımsız değişkenini atlayabilirsiniz. Dizeniz null sonlandırılırsa, uzunluğunu belirtmek için *nNewLength* kullanın. [GetBuffer](#getbuffer) tarafından döndürülen adres, `ReleaseBuffer` çağrısından sonra geçersiz veya başka bir `CSimpleStringT` işlemi.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::ReleaseBuffer`kullanımını gösterir.

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

`CSimpleStringT` nesnesinden tek bir karakter ayarlar.

### <a name="syntax"></a>Sözdizimi

```
void SetAt(int iChar, XCHAR ch);
```

#### <a name="parameters"></a>Parametreler

*ICHAR*<br/>
`CSimpleStringT` nesnesindeki karakterin sıfır tabanlı dizini. *Ihar* parametresi 0 ' dan büyük veya buna eşit ve [GetLength](#getlength)tarafından döndürülen değerden küçük olmalıdır.

*denetleyebilirsiniz*<br/>
Yeni karakter.

### <a name="remarks"></a>Açıklamalar

*ICHAR*konumunda bulunan karakterin üzerine yazmak için bu yöntemi çağırın. Bu yöntem, *ıhar* varolan dizenin sınırlarını aşarsa dizeyi genişletmeyecektir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::SetAt`kullanımını gösterir.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
```

##  <a name="setmanager"></a>CSimpleStringT:: SetManager

`CSimpleStringT` nesnesinin bellek yöneticisini belirtir.

### <a name="syntax"></a>Sözdizimi

```
void SetManager(IAtlStringMgr* pStringMgr);
```

#### <a name="parameters"></a>Parametreler

*pStringMgr*<br/>
Yeni bellek yöneticisine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` nesnesi tarafından kullanılan yeni bir bellek yöneticisi belirtmek için bu yöntemi çağırın. Bellek yöneticileri ve dize nesneleri hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::SetManager`kullanımını gösterir.

```cpp
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```

##  <a name="setstring"></a>CSimpleStringT:: SetString

Bir `CSimpleStringT` nesnesinin dizesini ayarlar.

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

`CSimpleStringT` nesnesine bir dize kopyalayın. `SetString` arabellekteki eski dize verilerinin üzerine yazar.

Her iki `SetString` sürümü de *pszSrc* 'in boş bir işaretçi olup olmadığını denetleyin ve varsa, bir E_INVALIDARG hatası oluşturur.

Tek parametreli `SetString` sürümü *pszSrc* 'nin null ile sonlandırılmış bir dizeyi işaret etmek istiyor.

`SetString` iki parametreli sürümü de *pszSrc* 'nin null ile sonlandırılmış bir dize olmasını bekler. İlk olarak bir null Sonlandırıcı ile karşılaşmadığı sürece dize uzunluğu olarak *nLength* kullanır.

`SetString` iki parametreli sürümü, *pszSrc* 'nin `CSimpleStringT`geçerli arabellekte bir konuma işaret ettiğini de denetler. Bu özel durumda `SetString`, dize verilerini arabelleğine geri kopyalayan dize verilerinin üzerine yazmayan bir bellek kopyalama işlevi kullanır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CSimpleStringT::SetString`kullanımını gösterir.

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

Aşağıdaki örnek, `CSimpleStringT::StringLength`kullanımını gösterir.

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

Aşağıdaki örnek, `CSimpleStringT::Truncate`kullanımını gösterir.

```cpp
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
```

##  <a name="unlockbuffer"></a>CSimpleStringT:: UnlockBuffer

`CSimpleStringT` nesnesinin arabelleğini kaldırır.

### <a name="syntax"></a>Sözdizimi

```
void UnlockBuffer() throw();
```

### <a name="remarks"></a>Açıklamalar

Dizenin başvuru sayısını 1 ' e sıfırlamak için bu yöntemi çağırın.

`CSimpleStringT` yıkıcısı, yıkıcı çağrıldığında arabelleğin kilitlenmemesini sağlamak için `UnlockBuffer` otomatik olarak çağırır. Bu yöntemin bir örneği için bkz. [LockBuffer](#lockbuffer).

##  <a name="dtor"></a>CSimpleStringT:: ~ CSimpleStringT

`CSimpleStringT` nesnesini yok eder.

### <a name="syntax"></a>Sözdizimi

```
~CSimpleStringT() throw();
```

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` nesnesini yok etmek için bu yöntemi çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
