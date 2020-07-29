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
ms.openlocfilehash: bbbab04ff311d874fc209d2c46fadda57e79a222
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219098"
---
# <a name="csimplestringt-class"></a>CSimpleStringT sınıfı

Bu sınıf bir nesneyi temsil eder `CSimpleStringT` .

## <a name="syntax"></a>Söz dizimi

```
template <typename BaseType>
class CSimpleStringT
```

### <a name="parameters"></a>Parametreler

*BaseType*<br/>
Dize sınıfının karakter türü. Aşağıdakilerden biri olabilir:

- **`char`**(ANSI karakter dizeleri için).

- **`wchar_t`**(Unicode karakter dizeleri için).

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
|[CSimpleStringT:: CSimpleStringT](#ctor)|`CSimpleStringT`Nesneleri çeşitli şekillerde oluşturur.|
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleStringT:: Append](#append)|Varolan bir `CSimpleStringT` nesneye bir nesne ekler `CSimpleStringT` .|
|[CSimpleStringT:: AppendChar](#appendchar)|Varolan bir nesneye bir karakter ekler `CSimpleStringT` .|
|[CSimpleStringT:: CopyChars](#copychars)|Bir karakteri veya karakteri başka bir dizeye kopyalar.|
|[CSimpleStringT:: Copycharsoverladmış](#copycharsoverlapped)|Bir karakteri veya karakterleri, arabelleklerin çakıştığı başka bir dizeye kopyalar.|
|[CSimpleStringT:: Empty](#empty)|Bir dizeyi sıfır uzunluğuna zorlar.|
|[CSimpleStringT:: FreeExtra](#freeextra)|Dize nesnesi tarafından daha önce ayrılan ek belleği serbest bırakır.|
|[CSimpleStringT:: GetAllocLength](#getalloclength)|Bir nesnenin ayrılan uzunluğunu alır `CSimpleStringT` .|
|[CSimpleStringT:: GetAt](#getat)|Verilen konumdaki karakteri döndürür.|
|[CSimpleStringT:: GetBuffer](#getbuffer)|İçindeki karakterlere bir işaretçi döndürür `CSimpleStringT` .|
|[CSimpleStringT:: GetBufferSetLength](#getbuffersetlength)|İçindeki karakterlere bir işaretçi döndürür `CSimpleStringT` , belirtilen uzunluğa kesiliyor.|
|[CSimpleStringT:: GetLength](#getlength)|Bir nesnedeki karakter sayısını döndürür `CSimpleStringT` .|
|[CSimpleStringT:: GetManager](#getmanager)|Nesnenin bellek yöneticisini alır `CSimpleStringT` .|
|[CSimpleStringT:: GetString](#getstring)|Karakter dizesini alır|
|[CSimpleStringT:: IsEmpty](#isempty)|Bir `CSimpleStringT` nesnenin karakter içerip içermediğini test eder.|
|[CSimpleStringT:: LockBuffer](#lockbuffer)|Başvuru saymayı devre dışı bırakır ve arabellekteki dizeyi korur.|
|[CSimpleStringT::P yeniden tahsis](#preallocate)|Karakter arabelleği için belirli miktarda bellek ayırır.|
|[CSimpleStringT:: ReleaseBuffer](#releasebuffer)|Tarafından döndürülen arabelleğin denetimini yayınlar `GetBuffer` .|
|[CSimpleStringT:: ReleaseBufferSetLength](#releasebuffersetlength)|Tarafından döndürülen arabelleğin denetimini yayınlar `GetBuffer` .|
|[CSimpleStringT:: SetAt](#setat)|Verilen konumda bir karakter ayarlar.|
|[CSimpleStringT:: SetManager](#setmanager)|Bir nesnenin bellek yöneticisini ayarlar `CSimpleStringT` .|
|[CSimpleStringT:: SetString](#setstring)|Bir nesnenin dizesini ayarlar `CSimpleStringT` .|
|[CSimpleStringT:: StringLength](#stringlength)|Belirtilen dizedeki karakter sayısını döndürür.|
|[CSimpleStringT:: Truncate](#truncate)|Dizeyi belirtilen uzunluğa kırpar.|
|[CSimpleStringT:: UnlockBuffer](#unlockbuffer)|Başvuru saymayı ve arabellekteki dizeyi serbest bırakır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleStringT:: operator PCXSTR](#operator_pcxstr)|Bir nesnede depolanan karakterlere doğrudan `CSimpleStringT` C stili dize olarak erişir.|
|[CSimpleStringT:: işleci\[\]](#operator_at)|Verilen konumdaki karakteri döndürür — için işleç değiştirme `GetAt` .|
|[CSimpleStringT:: operator + =](#operator_add_eq)|Varolan bir dizenin sonuna yeni bir dize ekler.|
|[CSimpleStringT:: operator =](#operator_eq)|Nesnesine yeni bir değer atar `CSimpleStringT` .|

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT`, Visual C++ tarafından desteklenen çeşitli dize sınıfları için temel sınıftır. Dize nesnesinin bellek yönetimi ve temel arabellek düzenlemesi için en düşük desteği sağlar. Daha gelişmiş dize nesneleri için bkz. [CStringT sınıfı](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpstr. h

## <a name="csimplestringtappend"></a><a name="append"></a>CSimpleStringT:: Append

Varolan bir `CSimpleStringT` nesneye bir nesne ekler `CSimpleStringT` .

### <a name="syntax"></a>Söz dizimi

```cpp
void Append(const CSimpleStringT& strSrc);
void Append(PCXSTR pszSrc, int nLength);
void Append(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Parametreler

*strSrc*<br/>
`CSimpleStringT`Eklenecek nesne.

*pszSrc*<br/>
Eklenecek karakterleri içeren bir dize işaretçisi.

*nLength*<br/>
Eklenecek karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Varolan bir `CSimpleStringT` nesneyi başka bir nesneye eklemek için bu yöntemi çağırın `CSimpleStringT` .

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::Append` .

```cpp
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```

## <a name="csimplestringtappendchar"></a><a name="appendchar"></a>CSimpleStringT:: AppendChar

Varolan bir nesneye bir karakter ekler `CSimpleStringT` .

### <a name="syntax"></a>Söz dizimi

```cpp
void AppendChar(XCHAR ch);
```

#### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*<br/>
Eklenecek karakter

### <a name="remarks"></a>Açıklamalar

Belirtilen karakteri varolan bir nesnenin sonuna eklemek için bu işlevi çağırın `CSimpleStringT` .

## <a name="csimplestringtcopychars"></a><a name="copychars"></a>CSimpleStringT:: CopyChars

Bir karakteri veya karakterleri `CSimpleStringT` nesnesine kopyalar.

### <a name="syntax"></a>Söz dizimi

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

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::CopyChars` .

```cpp
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```

## <a name="csimplestringtcopycharsoverlapped"></a><a name="copycharsoverlapped"></a>CSimpleStringT:: Copycharsoverladmış

Bir karakteri veya karakterleri `CSimpleStringT` nesnesine kopyalar.

### <a name="syntax"></a>Söz dizimi

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

*PchSrc* 'Den *pchDest* dizesine karakter kopyalamak için bu yöntemi çağırın. Aksine `CopyChars` , `CopyCharsOverlapped` Çakışan karakter arabelleklerinden kopyalamak için güvenli bir yöntem sağlar.

### <a name="example"></a>Örnek

[CSimpleStringT:: CopyChars](#copychars)örneğine veya kaynak koduna `CSimpleStringT::SetString` (atlsimpstr. h içinde bulunur) bakın.

## <a name="csimplestringtcsimplestringt"></a><a name="ctor"></a>CSimpleStringT:: CSimpleStringT

Bir `CSimpleStringT` nesnesi oluşturur.

### <a name="syntax"></a>Söz dizimi

```
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr);
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr);
CSimpleStringT(const CSimpleStringT& strSrc);
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw();
```

#### <a name="parameters"></a>Parametreler

*strSrc*<br/>
`CSimpleStringT`Bu nesneye Kopyalanacak varolan bir nesne `CSimpleStringT` .

*pchSrc*<br/>
Null ile değil, *nLength*uzunluklu bir karakter dizisine yönelik bir işaretçi.

*pszSrc*<br/>
Bu nesneye kopyalanacak null ile sonlandırılmış bir dize `CSimpleStringT` .

*nLength*<br/>
İçindeki karakterlerin sayısı `pch` .

*pStringMgr*<br/>
Nesnenin bellek Yöneticisi işaretçisi `CSimpleStringT` . Ve için bellek yönetimi hakkında daha fazla bilgi için `IAtlStringMgr` `CSimpleStringT` bkz. [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).

### <a name="remarks"></a>Açıklamalar

Yeni bir `CSimpleStringT` nesne oluşturun. Oluşturucular giriş verilerini yeni ayrılmış depolama alanına kopyalayacağından, bellek özel durumları oluşabilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, ATL kullanarak öğesinin kullanımını gösterir `CSimpleStringT::CSimpleStringT` **`typedef`** `CSimpleString` . `CSimpleString`, sınıf şablonunun yaygın olarak kullanılan bir özelleştirmesi `CSimpleStringT` .

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

## <a name="csimplestringtempty"></a><a name="empty"></a>CSimpleStringT:: Empty

Bu `CSimpleStringT` nesneyi boş bir dize yapar ve uygun şekilde belleği serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
void Empty() throw();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [dizeler: CString özel durum temizleme](../cstring-exception-cleanup.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::Empty` .

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtfreeextra"></a><a name="freeextra"></a>CSimpleStringT:: FreeExtra

Daha önce dize tarafından ayrılan ancak artık gerekli olmayan ek belleği serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
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

## <a name="csimplestringtgetalloclength"></a><a name="getalloclength"></a>CSimpleStringT:: GetAllocLength

Bir nesnenin ayrılan uzunluğunu alır `CSimpleStringT` .

### <a name="syntax"></a>Sözdizimi

```
int GetAllocLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne için ayrılan karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Bu nesne için ayrılan karakter sayısını öğrenmek için bu yöntemi çağırın `CSimpleStringT` . Bu işlevi çağırma örneği için [FreeExtra](#freeextra) bölümüne bakın.

## <a name="csimplestringtgetat"></a><a name="getat"></a>CSimpleStringT:: GetAt

Nesnesinden bir karakter döndürür `CSimpleStringT` .

### <a name="syntax"></a>Söz dizimi

```
XCHAR GetAt(int iChar) const;
```

#### <a name="parameters"></a>Parametreler

*ICHAR*<br/>
Nesnedeki karakterin sıfır tabanlı dizini `CSimpleStringT` . *Ihar* parametresi 0 ' dan büyük veya buna eşit ve [GetLength](#getlength)tarafından döndürülen değerden küçük olmalıdır. Aksi takdirde, `GetAt` bir özel durum oluşturur.

### <a name="return-value"></a>Dönüş Değeri

`XCHAR`Dizedeki belirtilen konumdaki karakteri içeren bir.

### <a name="remarks"></a>Açıklamalar

*ICHAR*tarafından belirtilen bir karakteri döndürmek için bu yöntemi çağırın. Aşırı yüklenmiş alt simge (**[]**) işleci için uygun bir diğer addır `GetAt` . Null Sonlandırıcı kullanılarak özel bir durum üretilmeden adreslenebilir `GetAt` . Ancak, tarafından sayılmaz `GetLength` ve döndürülen değer 0 ' dır.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını göstermektedir `CSimpleStringT::GetAt` .

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```

## <a name="csimplestringtgetbuffer"></a><a name="getbuffer"></a>CSimpleStringT:: GetBuffer

Nesnenin iç karakter arabelleğine yönelik bir işaretçi döndürür `CSimpleStringT` .

### <a name="syntax"></a>Söz dizimi

```
PXSTR GetBuffer(int nMinBufferLength);
PXSTR GetBuffer();
```

#### <a name="parameters"></a>Parametreler

*nMinBufferLength*<br/>
Karakter arabelleğinin tutabileceğinden en az karakter sayısı. Bu değer, null Sonlandırıcı için boşluk içermez.

*NMinBufferLength* geçerli arabelleğin uzunluğundan daha büyükse, `GetBuffer` geçerli arabelleği yok eder, istenen boyutun bir arabelleği ile değiştirir ve nesne başvuru sayısını sıfıra sıfırlar. Daha önce bu arabellekte [LockBuffer](#lockbuffer) çağrılırsa, arabellek kilidini kaybedersiniz.

### <a name="return-value"></a>Dönüş Değeri

`PXSTR`Nesnenin (null ile sonlandırılmış) karakter arabelleğinin bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

Nesnenin arabellek içeriğini döndürmek için bu yöntemi çağırın `CSimpleStringT` . Döndürülen `PXSTR` bir sabit değildir ve bu nedenle içeriğin doğrudan değiştirilmesine izin verir `CSimpleStringT` .

Tarafından döndürülen işaretçiyi `GetBuffer` dize içeriklerini değiştirmek için kullanırsanız, başka bir üye yöntemi kullanmadan önce [ReleaseBuffer](#releasebuffer) öğesini çağırmanız gerekir `CSimpleStringT` .

Tarafından döndürülen adres, ' `GetBuffer` e yapılan çağrıdan sonra geçerli olmayabilir `ReleaseBuffer` çünkü ek `CSimpleStringT` İşlemler `CSimpleStringT` arabelleğin yeniden ayrılmasına neden olabilir. Uzunluğunu değiştirmeyin arabelleği yeniden tahsis edilmez `CSimpleStringT` .

Arabellek belleği, nesne yok edildiğinde otomatik olarak serbest bırakılır `CSimpleStringT` .

Dize uzunluğunu kendiniz izlemenize sonra, Sonlandırıcı null karakterini eklememelisiniz. Ancak, ile arabelleği serbest bırakıldığında son dize uzunluğunu belirtmeniz gerekir `ReleaseBuffer` . Bir Sonlandırıcı null karakteri ekleymeniz durumunda, uzunluğu için-1 (varsayılan) geçişi yapmalısınız. `ReleaseBuffer`sonra arabellek uzunluğunu belirler.

İsteği karşılamak için yeterli bellek yoksa `GetBuffer` , bu yöntem bir CMemoryException * oluşturur.

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

## <a name="csimplestringtgetbuffersetlength"></a><a name="getbuffersetlength"></a>CSimpleStringT:: GetBufferSetLength

Nesne için iç karakter arabelleğinin bir işaretçisini `CSimpleStringT` , *nLength*olarak belirtilen uzunlukla tam olarak eşleşmesi gerekiyorsa, kesilmesi veya büyümesini sağlar.

### <a name="syntax"></a>Söz dizimi

```
PXSTR GetBufferSetLength(int nLength);
```

#### <a name="parameters"></a>Parametreler

*nLength*<br/>
`CSimpleStringT`Karakter arabelleğinin karakter cinsinden tam boyutu.

### <a name="return-value"></a>Dönüş Değeri

`PXSTR`Nesnenin (null ile sonlandırılmış) karakter arabelleğinin bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

Nesnenin iç arabelleğinin belirtilen uzunluğunu almak için bu yöntemi çağırın `CSimpleStringT` . Döndürülen `PXSTR` işaretçi değildir ve bu **`const`** nedenle içeriğin doğrudan değiştirilmesine izin verir `CSimpleStringT` .

Dize içeriklerini değiştirmek için [GetBufferSetLength](#getbuffersetlength) tarafından döndürülen işaretçiyi kullanırsanız, `ReleaseBuffer` `CsimpleStringT` diğer herhangi bir yöntemi kullanmadan önce iç durumunu güncelleştirme ' yi çağırın `CSimpleStringT` .

Tarafından döndürülen adres, ' `GetBufferSetLength` e yapılan çağrıdan sonra geçerli olmayabilir `ReleaseBuffer` çünkü ek `CSimpleStringT` İşlemler `CSimpleStringT` arabelleğin yeniden ayrılmasına neden olabilir. Uzunluğunu değiştirmeyin, arabellek yeniden atanmaz `CSimpleStringT` .

Arabellek belleği, nesne yok edildiğinde otomatik olarak serbest bırakılır `CSimpleStringT` .

Dize uzunluğunu kendiniz izlemenize devam ederseniz, Sonlandırıcı null karakterini eklemeyin. Kullanarak arabelleği serbest aktardığınızda son dize uzunluğunu belirtmeniz gerekir `ReleaseBuffer` . ' I çağırdığınızda bir Sonlandırıcı null karakteri eklerseniz `ReleaseBuffer` , uzunluğu için-1 ' i (varsayılan) olarak geçirin `ReleaseBuffer` ve `ReleaseBuffer` `strlen` uzunluğunu belirlemede arabelleğe alır.

Başvuru sayımı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- Windows SDK [başvuru sayımı aracılığıyla nesne yaşam sürelerini yönetme](/windows/win32/com/managing-object-lifetimes-through-reference-counting) .

- Windows SDK [başvuru sayımı uygulama](/windows/win32/com/implementing-reference-counting) .

- Windows SDK [başvuru sayılarını yönetme kuralları](/windows/win32/com/rules-for-managing-reference-counts) .

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::GetBufferSetLength` .

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

## <a name="csimplestringtgetlength"></a><a name="getlength"></a>CSimpleStringT:: GetLength

Nesnedeki karakter sayısını döndürür `CSimpleStringT` .

### <a name="syntax"></a>Sözdizimi

```
int GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizedeki karakterlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Nesnedeki karakter sayısını döndürmek için bu yöntemi çağırın. Sayı null Sonlandırıcı içermiyor.

Çok baytlı karakter kümeleri (MBCS) için `GetLength` her 8 bitlik karakteri sayar; diğer bir deyişle, bir çok baytlı karakter içindeki bir öncü ve sondaki bayt iki bayt olarak sayılır. Bu işlevi çağırma örneği için [FreeExtra](#freeextra) bölümüne bakın.

## <a name="csimplestringtgetmanager"></a><a name="getmanager"></a>CSimpleStringT:: GetManager

Nesnenin bellek yöneticisini alır `CSimpleStringT` .

### <a name="syntax"></a>Sözdizimi

```
IAtlStringMgr* GetManager() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne için bellek Yöneticisi işaretçisi `CSimpleStringT` .

### <a name="remarks"></a>Açıklamalar

Nesne tarafından kullanılan bellek yöneticisini almak için bu yöntemi çağırın `CSimpleStringT` . Bellek yöneticileri ve dize nesneleri hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).

## <a name="csimplestringtgetstring"></a><a name="getstring"></a>CSimpleStringT:: GetString

Karakter dizesini alır.

### <a name="syntax"></a>Sözdizimi

```
PCXSTR GetString() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Null ile sonlandırılmış bir karakter dizesinin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Nesneyle ilişkili karakter dizesini almak için bu yöntemi çağırın `CSimpleStringT` .

> [!NOTE]
> Döndürülen `PCXSTR` işaretçi, **`const`** içerik doğrudan değişikliğine izin vermez `CSimpleStringT` .

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::GetString` .

```cpp
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```

## <a name="csimplestringtisempty"></a><a name="isempty"></a>CSimpleStringT:: IsEmpty

`CSimpleStringT`Boş koşul için bir nesneyi sınar.

### <a name="syntax"></a>Sözdizimi

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSimpleStringT`Nesnenin 0 uzunluğu varsa true, DEĞILSE false döndürür.

### <a name="remarks"></a>Açıklamalar

Nesnenin boş bir dize içerip içermediğini anlamak için bu yöntemi çağırın.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::IsEmpty` .

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtlockbuffer"></a><a name="lockbuffer"></a>CSimpleStringT:: LockBuffer

Başvuru saymayı devre dışı bırakır ve arabellekteki dizeyi korur.

### <a name="syntax"></a>Sözdizimi

```
PXSTR LockBuffer();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CSimpleStringT` nesne veya null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Nesne arabelleğini kilitlemek için bu yöntemi çağırın `CSimpleStringT` . Çağırarak `LockBuffer` , başvuru sayısı için-1 ile dizenin bir kopyasını oluşturursunuz. Başvuru sayısı değeri-1 olduğunda, arabellekteki dize "kilitli" durumunda olduğu kabul edilir. Kilitli durumda olan dize iki şekilde korunur:

- Başka hiçbir dize, bu dize kilitli dizeye atanmış olsa bile, kilitli dizedeki verilere başvuru alamaz.

- Başka bir dize kilitli dizeye kopyalansa bile, kilitli dize hiçbir şekilde başka bir dizeye başvurmayacaktır.

Arabellekteki dizeyi kilitleyerek, dizenin arabelleğe ait dışlamalı tutmanın bozulmadan kalacağından emin olursunuz.

İle işiniz bittiğinde `LockBuffer` , başvuru sayısını 1 ' e sıfırlamak Için [UnlockBuffer](#unlockbuffer) ' ı çağırın.

> [!NOTE]
> [GetBuffer](#getbuffer) öğesini kilitli bir arabellekte çağırırsanız ve `GetBuffer` parametreyi `nMinBufferLength` geçerli arabelleğin uzunluğundan daha büyük olarak ayarlarsanız, arabellek kilidini kaybedersiniz. Bu tür bir çağrı `GetBuffer` geçerli arabelleği yok eder, istenen boyutun arabelleği ile değiştirir ve başvuru sayısını sıfıra sıfırlar.

Başvuru sayımı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- Windows SDK [başvuru sayımı aracılığıyla nesne yaşam sürelerini yönetme](/windows/win32/com/managing-object-lifetimes-through-reference-counting)

- Windows SDK [başvuru sayımı uygulama](/windows/win32/com/implementing-reference-counting)

- Windows SDK [başvuru sayılarını yönetmeye yönelik kurallar](/windows/win32/com/rules-for-managing-reference-counts)

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::LockBuffer` .

```cpp
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```

## <a name="csimplestringtoperator"></a><a name="operator_at"></a>CSimpleStringT:: işleci\[\]

Karakter dizisinin tek bir karakterine erişmek için bu işlevi çağırın.

### <a name="syntax"></a>Söz dizimi

```
XCHAR operator[](int iChar) const;
```

#### <a name="parameters"></a>Parametreler

*ICHAR*<br/>
Dizedeki bir karakterin sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Aşırı yüklenmiş alt simge (**[]**) Işleci, *ıhar*'da sıfır tabanlı dizin tarafından belirtilen tek bir karakter döndürür. Bu işleç, [GetAt](#getat) üye işlevinin kullanışlı bir alternatifi.

> [!NOTE]
> ' Deki bir karakterin değerini almak için alt simge (**[]**) işlecini kullanabilirsiniz `CSimpleStringT` , ancak bunu, içindeki bir karakterin değerini değiştirmek için kullanamazsınız `CSimpleStringT` .

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::operator []` .

```cpp
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```

## <a name="csimplestringtoperator-"></a><a name="operator_at"></a>CSimpleStringT:: işleci\[\]

Karakter dizisinin tek bir karakterine erişmek için bu işlevi çağırın.

### <a name="syntax"></a>Söz dizimi

```
XCHAR operator[](int iChar) const;
```

### <a name="parameters"></a>Parametreler

*ICHAR*<br/>
Dizedeki bir karakterin sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Aşırı yüklenmiş alt simge (**[]**) Işleci, *ıhar*'da sıfır tabanlı dizin tarafından belirtilen tek bir karakter döndürür. Bu işleç, [GetAt](#getat) üye işlevinin kullanışlı bir alternatifi.

> [!NOTE]
> ' Deki bir karakterin değerini almak için alt simge (**[]**) işlecini kullanabilirsiniz `CSimpleStringT` , ancak bunu, içindeki bir karakterin değerini değiştirmek için kullanamazsınız `CSimpleStringT` .

## <a name="csimplestringtoperator-"></a><a name="operator_add_eq"></a>CSimpleStringT:: operator + =

Varolan bir dizenin sonuna yeni bir dize veya karakter birleştirir.

### <a name="syntax"></a>Söz dizimi

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
Varolan bir nesneye yönelik bir işaretçi `CSimpleStringT` .

*denetleyebilirsiniz*<br/>
Eklenecek karakter.

### <a name="remarks"></a>Açıklamalar

İşleç başka bir `CSimpleStringT` nesneyi veya karakteri kabul eder. Bu nesneye eklenen karakterler için yeni depolama alanı ayrıldığından, bu birleştirme işlecini her kullandığınızda bellek özel durumlarının gerçekleşebileceğini unutmayın `CSimpleStringT` .

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::operator +=` .

```cpp
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```

## <a name="csimplestringtoperator-"></a><a name="operator_eq"></a>CSimpleStringT:: operator =

Nesnesine yeni bir değer atar `CSimpleStringT` .

### <a name="syntax"></a>Söz dizimi

```
CSimpleStringT& operator =(PCXSTR pszSrc);
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```

#### <a name="parameters"></a>Parametreler

*pszSrc*<br/>
Null ile sonlandırılmış bir dize işaretçisi.

*strSrc*<br/>
Varolan bir nesneye yönelik bir işaretçi `CSimpleStringT` .

### <a name="remarks"></a>Açıklamalar

Hedef dize (sol tarafta) yeni verileri depolamak için zaten büyükse, yeni bir bellek ayırma gerçekleştirilmez. Yeni depolama genellikle sonuçta elde edilen nesneyi tutmak üzere ayrıldığından, atama işlecini her kullandığınızda bellek özel durumlarının gerçekleşebileceğini unutmayın `CSimpleStringT` .

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::operator =` .

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

## <a name="csimplestringtoperator-pcxstr"></a><a name="operator_pcxstr"></a>CSimpleStringT:: operator PCXSTR

Bir nesnede depolanan karakterlere doğrudan `CSimpleStringT` C stili dize olarak erişir.

### <a name="syntax"></a>Sözdizimi

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin verilerine yönelik bir karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Hiçbir karakter kopyalanmaz; yalnızca bir işaretçi döndürülür. Bu işleçle dikkatli olun. `CString`Karakter işaretçisini elde ettikten sonra bir nesneyi değiştirirseniz, işaretçiyi geçersiz kılan belleğin yeniden alınmasına neden olabilirsiniz.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::operator PCXSTR` .

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

## <a name="csimplestringtpcxstr"></a><a name="pcxstr"></a>CSimpleStringT::P CXSTR

Sabit dize işaretçisi.

### <a name="syntax"></a>Sözdizimi

```
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;
```

## <a name="csimplestringtpreallocate"></a><a name="preallocate"></a>CSimpleStringT::P yeniden tahsis

Nesne için belirli bir bayt miktarı ayırır `CSimpleStringT` .

### <a name="syntax"></a>Söz dizimi

```cpp
void Preallocate( int nLength);
```

#### <a name="parameters"></a>Parametreler

*nLength*<br/>
`CSimpleStringT`Karakter arabelleğinin karakter cinsinden tam boyutu.

### <a name="remarks"></a>Açıklamalar

Nesne için belirli bir arabellek boyutunu ayırmak üzere bu yöntemi çağırın `CSimpleStringT` .

`CSimpleStringT`karakter arabelleği için alan ayıramadığında STATUS_NO_MEMORY bir özel durum oluşturur. Varsayılan olarak, bellek ayırma WIN32 API işlevleri veya tarafından gerçekleştirilir `HeapAlloc` `HeapReAlloc` .

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::Preallocate` .

```cpp
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```

## <a name="csimplestringtpxstr"></a><a name="pxstr"></a>CSimpleStringT::P XSTR

Dize işaretçisi.

### <a name="syntax"></a>Sözdizimi

```
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;
```

## <a name="csimplestringtreleasebuffer"></a><a name="releasebuffer"></a>CSimpleStringT:: ReleaseBuffer

[GetBuffer](#getbuffer)tarafından ayrılan arabelleğin denetimini yayınlar.

### <a name="syntax"></a>Söz dizimi

```cpp
void ReleaseBuffer(int nNewLength = -1);
```

#### <a name="parameters"></a>Parametreler

*nNewLength*<br/>
Dizenin karakter cinsinden yeni uzunluğu, null sonlandırıcıyı saymaz. Dize null sonlandırılırsa,-1 varsayılan değeri `CSimpleStringT` dizenin geçerli uzunluğuna ayarlanır.

### <a name="remarks"></a>Açıklamalar

Dize nesnesinin arabelleğini yeniden ayırmak veya boşaltmak için bu yöntemi çağırın. Arabellekteki dizenin null sonlandırıldığını biliyorsanız, *nNewLength* bağımsız değişkenini atlayabilirsiniz. Dizeniz null sonlandırılırsa, uzunluğunu belirtmek için *nNewLength* kullanın. [GetBuffer](#getbuffer) tarafından döndürülen adres, `ReleaseBuffer` ya da başka bir işlem çağrısından sonra geçersizdir `CSimpleStringT` .

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::ReleaseBuffer` .

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

## <a name="csimplestringtreleasebuffersetlength"></a><a name="releasebuffersetlength"></a>CSimpleStringT:: ReleaseBufferSetLength

[GetBuffer](#getbuffer)tarafından ayrılan arabelleğin denetimini yayınlar.

### <a name="syntax"></a>Söz dizimi

```cpp
void ReleaseBufferSetLength(int nNewLength);
```

#### <a name="parameters"></a>Parametreler

*nNewLength*<br/>
Serbest bırakılmakta olan dizenin uzunluğu

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir dize nesnesi için geçerli bir uzunluk iletilmesi dışında, işleve [ReleaseBuffer](#releasebuffer) ile benzerdir.

## <a name="csimplestringtsetat"></a><a name="setat"></a>CSimpleStringT:: SetAt

Nesnesinden tek bir karakter ayarlar `CSimpleStringT` .

### <a name="syntax"></a>Söz dizimi

```cpp
void SetAt(int iChar, XCHAR ch);
```

#### <a name="parameters"></a>Parametreler

*ICHAR*<br/>
Nesnedeki karakterin sıfır tabanlı dizini `CSimpleStringT` . *Ihar* parametresi 0 ' dan büyük veya buna eşit ve [GetLength](#getlength)tarafından döndürülen değerden küçük olmalıdır.

*denetleyebilirsiniz*<br/>
Yeni karakter.

### <a name="remarks"></a>Açıklamalar

*ICHAR*konumunda bulunan karakterin üzerine yazmak için bu yöntemi çağırın. Bu yöntem, *ıhar* varolan dizenin sınırlarını aşarsa dizeyi genişletmeyecektir.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::SetAt` .

```cpp
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
```

## <a name="csimplestringtsetmanager"></a><a name="setmanager"></a>CSimpleStringT:: SetManager

Nesnenin bellek yöneticisini belirtir `CSimpleStringT` .

### <a name="syntax"></a>Söz dizimi

```cpp
void SetManager(IAtlStringMgr* pStringMgr);
```

#### <a name="parameters"></a>Parametreler

*pStringMgr*<br/>
Yeni bellek yöneticisine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesnesi tarafından kullanılan yeni bir bellek yöneticisi belirtmek için bu yöntemi çağırın `CSimpleStringT` . Bellek yöneticileri ve dize nesneleri hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::SetManager` .

```cpp
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```

## <a name="csimplestringtsetstring"></a><a name="setstring"></a>CSimpleStringT:: SetString

Bir nesnenin dizesini ayarlar `CSimpleStringT` .

### <a name="syntax"></a>Söz dizimi

```cpp
void SetString(PCXSTR pszSrc, int nLength);
void SetString(PCXSTR pszSrc);
```

#### <a name="parameters"></a>Parametreler

*pszSrc*<br/>
Null ile sonlandırılmış bir dize işaretçisi.

*nLength*<br/>
*PszSrc*içindeki karakterlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Nesnesine bir dize kopyalayın `CSimpleStringT` . `SetString`Arabellekteki eski dize verilerinin üzerine yazar.

Her iki sürümü de `SetString` *pszSrc* 'nin null bir işaretçi olup olmadığını denetler ve varsa E_INVALIDARG bir hata oluşturur.

Öğesinin tek parametreli sürümü `SetString` *pszSrc* 'in null ile sonlandırılmış bir dizeye işaret etmek bekler.

Öğesinin iki parametreli sürümü `SetString` de *pszSrc* 'nin null ile sonlandırılmış bir dize olmasını bekler. İlk olarak bir null Sonlandırıcı ile karşılaşmadığı sürece dize uzunluğu olarak *nLength* kullanır.

İki parametreli sürümü, `SetString` *pszSrc* 'nin içindeki geçerli arabellekte bir konuma işaret ettiğini de denetler `CSimpleStringT` . Bu özel durumda, `SetString` dize verilerini arabelleğine geri kopyalayan dize verilerinin üzerine yazmayan bir bellek kopyalama işlevi kullanır.

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::SetString` .

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```

## <a name="csimplestringtstringlength"></a><a name="stringlength"></a>CSimpleStringT:: StringLength

Belirtilen dizedeki karakter sayısını döndürür.

### <a name="syntax"></a>Söz dizimi

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

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::StringLength` .

```cpp
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
```

## <a name="csimplestringttruncate"></a><a name="truncate"></a>CSimpleStringT:: Truncate

Dizeyi yeni uzunluğa kırpar.

### <a name="syntax"></a>Söz dizimi

```cpp
void Truncate(int nNewLength);
```

#### <a name="parameters"></a>Parametreler

*nNewLength*<br/>
Dizenin yeni uzunluğu.

### <a name="remarks"></a>Açıklamalar

Dizenin içeriğini yeni uzunluğa kesmek için bu yöntemi çağırın.

> [!NOTE]
> Bu, arabelleğin ayrılan uzunluğunu etkilemez. Geçerli arabelleği azaltmak veya artırmak için bkz. [FreeExtra](#freeextra) ve [preallocate](#preallocate).

### <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir `CSimpleStringT::Truncate` .

```cpp
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
```

## <a name="csimplestringtunlockbuffer"></a><a name="unlockbuffer"></a>CSimpleStringT:: UnlockBuffer

Nesnesinin arabelleğini kaldırır `CSimpleStringT` .

### <a name="syntax"></a>Sözdizimi

```cpp
void UnlockBuffer() throw();
```

### <a name="remarks"></a>Açıklamalar

Dizenin başvuru sayısını 1 ' e sıfırlamak için bu yöntemi çağırın.

Yıkıcı `CSimpleStringT` `UnlockBuffer` çağrıldığında arabelleğin kilitlenmemesini sağlamak için otomatik olarak çağırır. Bu yöntemin bir örneği için bkz. [LockBuffer](#lockbuffer).

## <a name="csimplestringtcsimplestringt"></a><a name="dtor"></a>CSimpleStringT:: ~ CSimpleStringT

Bir nesneyi yok eder `CSimpleStringT` .

### <a name="syntax"></a>Sözdizimi

```
~CSimpleStringT() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi yok etmek için bu yöntemi çağırın `CSimpleStringT` .

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
