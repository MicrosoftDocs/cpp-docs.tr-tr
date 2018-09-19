---
title: CSimpleStringT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CSimpleStringT
- strings [C++], ATL class
- CSimpleStringT class
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98187d7f5946496af26e0cf4ff7929f12e5a6eb7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088962"
---
# <a name="csimplestringt-class"></a>CSimpleStringT sınıfı

Bu sınıfın temsil ettiği bir `CSimpleStringT` nesne.

## <a name="syntax"></a>Sözdizimi

```
template <typename BaseType>
class CSimpleStringT
```

### <a name="parameters"></a>Parametreler

*BaseType*  
Dize sınıfı karakter türü. Aşağıdakilerden biri olabilir:

- **char** (için ANSI karakter dizeleri).

- **wchar_t** (için Unicode karakter dizeleri).

- TCHAR (için ANSI hem Unicode karakter dizeleri).  

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleStringT::PCXSTR](#pcxstr)|Bir sabit dize işaretçisi.|
|[CSimpleStringT::PXSTR](#pxstr)|Bir dizeye bir işaretçi.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleStringT::CSimpleStringT](#ctor)|Yapıları `CSimpleStringT` çeşitli yollarla nesneleri.|
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|Yıkıcı.|  


### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleStringT::Append](#append)|Ekler bir `CSimpleStringT` varolan nesne `CSimpleStringT` nesne.|
|[CSimpleStringT::AppendChar](#appendchar)|Varolan bir karakter ekler `CSimpleStringT` nesne.|
|[CSimpleStringT::CopyChars](#copychars)|Bir karakterin veya başka bir dizeye kopyalar.|
|[CSimpleStringT::CopyCharsOverlapped](#copycharsoverlapped)|Bir karakteri veya karakterleri, arabellek örtüşmesi başka bir dizeye kopyalar.|
|[CSimpleStringT::Empty](#empty)|Sıfır uzunlukta bir dize zorlar.|
|[CSimpleStringT::FreeExtra](#freeextra)|Dize nesnesi tarafından önceden ayrılmış herhangi bir ek bellek kazandırır.|
|[CSimpleStringT::GetAllocLength](#getalloclength)|Ayrılmış uzunluğunu alır. bir `CSimpleStringT` nesne.|
|[CSimpleStringT::GetAt](#getat)|Belirtilen konumdaki karakteri döndürür.|
|[CSimpleStringT::GetBuffer](#getbuffer)|Karakter için işaretçi döndüren bir `CSimpleStringT`.|
|[CSimpleStringT::GetBufferSetLength](#getbuffersetlength)|Karakter için işaretçi döndüren bir `CSimpleStringT`, belirtilen uzunlukta kesiliyor.|
|[CSimpleStringT::GetLength](#getlength)|Karakter sayısını döndüren bir `CSimpleStringT` nesne.|
|[CSimpleStringT::GetManager](#getmanager)|Bellek Yöneticisi alır `CSimpleStringT` nesne.|
|[CSimpleStringT::GetString](#getstring)|Karakter dizesi alır.|
|[CSimpleStringT::IsEmpty](#isempty)|Testleri olup olmadığını bir `CSimpleStringT` nesne herhangi bir karakter içeriyor.|
|[CSimpleStringT::LockBuffer](#lockbuffer)|Başvuru sayımı devre dışı bırakır ve dize arabelleğindeki korur.|
|[CSimpleStringT::Preallocate](#preallocate)|Karakter arabelleği için belirli miktarda bellek ayırır.|
|[CSimpleStringT::ReleaseBuffer](#releasebuffer)|Serbest denetimi tarafından döndürülen arabellek `GetBuffer`.|
|[CSimpleStringT::ReleaseBufferSetLength](#releasebuffersetlength)|Serbest denetimi tarafından döndürülen arabellek `GetBuffer`.|
|[CSimpleStringT::SetAt](#setat)|Bir karakter, belirli bir konumda ayarlar.|
|[CSimpleStringT::SetManager](#setmanager)|Bellek Yöneticisi ayarlar bir `CSimpleStringT` nesne.|
|[CSimpleStringT::SetString](#setstring)|Dizenin ayarlar bir `CSimpleStringT` nesne.|
|[CSimpleStringT::StringLength](#stringlength)|Belirtilen dizenin karakter sayısını döndürür.|
|[CSimpleStringT::Truncate](#truncate)|Belirtilen uzunlukta dizeye keser.|
|[CSimpleStringT::UnlockBuffer](#unlockbuffer)|Başvuru sayımı sağlar ve dize arabelleğindeki serbest bırakır.|  

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleStringT::operator PCXSTR](#operator_pcxstr)|İçinde depolanan karakterlerin doğrudan erişir bir `CSimpleStringT` C stili dize olarak nesnesi.|
|[CSimpleStringT::operator\[\]](#operator_at)|Belirtilen konumdaki karakteri döndürür; işleci alternatifi için `GetAt`.|
|[CSimpleStringT::operator +=](#operator_add_eq)|Yeni bir dize sonuna kadar varolan bir dizeyi art arda ekler.|
|[CSimpleStringT::operator =](#operator_eq)|Yeni bir değer atar bir `CSimpleStringT` nesne.|

### <a name="remarks"></a>Açıklamalar

`CSimpleStringT` Visual C++ tarafından desteklenen çeşitli dize sınıfları için temel sınıftır. Dize nesnesi ve temel ara bellek düzenlemesi, bellek yönetimi için en az destek sağlar. Daha gelişmiş dize nesneler için bkz: [CStringT sınıfı](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpstr.h  

## <a name="append"></a> CSimpleStringT::Append

Ekler bir `CSimpleStringT` varolan nesne `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
void Append(const CSimpleStringT& strSrc); 
void Append(PCXSTR pszSrc, int nLength); 
void Append(PCXSTR pszSrc);
```
#### <a name="parameters"></a>Parametreler

*strSrc*  
`CSimpleStringT` Eklenecek nesne.

*pszSrc*  
Eklenecek karakter içeren bir dize işaretçisi.

*nLength*  
Sona eklenecek karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Mevcut bir eklemek için bu yöntemi çağırın `CSimpleStringT` başka bir nesneye `CSimpleStringT` nesne.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::Append`.

```cpp  
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```

##  <a name="appendchar"></a> CSimpleStringT::AppendChar

Varolan bir karakter ekler `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
void AppendChar(XCHAR ch);
```
#### <a name="parameters"></a>Parametreler

*ch*  
Eklenecek karakter

### <a name="remarks"></a>Açıklamalar

Belirtilen karakterin varolan eklemek için bu işlevi çağırın `CSimpleStringT` nesne.

##  <a name="copychars"></a> CSimpleStringT::CopyChars

Bir karakteri veya karakterleri kopyalar bir `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi  

```
static void CopyChars(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>Parametreler

*pchDest*  
Bir karakter dizesine bir işaretçi.

*pchSrc*  
Kopyalanacak karakter içeren bir dize işaretçisi.

*nChars*  
Sayısını *pchSrc* kopyalanacak karakter.

### <a name="remarks"></a>Açıklamalar

Karakterleri kopyalamak için bu yöntemi çağırın *pchSrc* için *pchDest* dize.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::CopyChars`.

```cpp  
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```

##  <a name="copycharsoverlapped"></a>  CSimpleStringT::CopyCharsOverlapped

Bir karakteri veya karakterleri kopyalar bir `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi  

```
static void CopyCharsOverlapped(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>Parametreler

*pchDest*  
Bir karakter dizesine bir işaretçi.

*pchSrc*  
Kopyalanacak karakter içeren bir dize işaretçisi.

*nChars*  
Sayısını *pchSrc* kopyalanacak karakter.

### <a name="remarks"></a>Açıklamalar

Karakterleri kopyalamak için bu yöntemi çağırın *pchSrc* için *pchDest* dize. Farklı `CopyChars`, `CopyCharsOverlapped` çakışan karakter önbelleklerden kopyalamak için güvenli bir yöntem sağlar.

### <a name="example"></a>Örnek

Örneğin bakın [CSimpleStringT::CopyChars](#copychars), veya kaynak kodu `CSimpleStringT::SetString` (atlsimpstr.h içinde bulunur).

##  <a name="ctor"></a>  CSimpleStringT::CSimpleStringT

Oluşturur bir `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr); 
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr); 
CSimpleStringT(const CSimpleStringT& strSrc); 
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw(); 
```
#### <a name="parameters"></a>Parametreler

*strSrc*  
Mevcut bir `CSimpleStringT` bu kopyalanacak nesne `CSimpleStringT` nesne.

*pchSrc*  
Karakter uzunlukta bir dizi işaretçi *nLength*, olmayan değişkende null.

*pszSrc*  
Null ile sonlandırılmış bir dize bu kopyalanacak `CSimpleStringT` nesne.

*nLength*  
Karakter sayısını `pch`.

*pStringMgr*  
Bellek Yöneticisi için bir işaretçi `CSimpleStringT` nesne. Hakkında daha fazla bilgi için `IAtlStringMgr` ve bellek yönetimi için `CSimpleStringT`, bkz: [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).

### <a name="remarks"></a>Açıklamalar

Yeni bir oluşturmak `CSimpleStringT` nesne. Oluşturucular girdi verilerini yeni ayrılan depolama alanına kopyalayın çünkü bellek özel durumlara neden olabilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::CSimpleStringT` ATL kullanarak **typedef** `CSimpleString`. `CSimpleString` yaygın olarak kullanılan bir sınıf şablonu uzmanlığı olan `CSimpleStringT`.

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


##  <a name="empty"></a>  CSimpleStringT::Empty

Böylece `CSimpleStringT` boş bir dize nesnesi ve uygun olarak bellek serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```
void Empty() throw();  
```
### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [dizeleri: CString özel durum Temizleme](../cstring-exception-cleanup.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::Empty`.

```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());  
```

##  <a name="freeextra"></a>  CSimpleStringT::FreeExtra

Dize tarafından önceden ayrılmış, ancak artık gerekli tüm ek bellek kazandırır.

### <a name="syntax"></a>Sözdizimi

```
void FreeExtra(); 
```
### <a name="remarks"></a>Açıklamalar

Bu dize nesnesi tarafından kullanılan bellek yükünü azaltmanız gerekir. Yöntem tarafından döndürülen tam uzunluğu arabelleğe yeniden tahsis ederse [GetLength](#getlength).

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

Bu örnek çıktısı aşağıdaki gibidir:

```Output
Alloc length is 1031, String length is 1024
Alloc length is 1031, String length is 15
Alloc length is 15, String length is 15
```

##  <a name="getalloclength"></a>  CSimpleStringT::GetAllocLength

Ayrılmış uzunluğunu alır. bir `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
int GetAllocLength() const throw();  
```
### <a name="return-value"></a>Dönüş Değeri

Bu nesne için ayrılan karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Bunun için ayrılmış karakter sayısını belirlemek için bu yöntemi çağırın `CSimpleStringT` nesne. Bkz: [FreeExtra](#freeextra) örneği bu işlevi çağırmak için.

##  <a name="getat"></a>  CSimpleStringT::GetAt

Bir karakter döndürür bir `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
XCHAR GetAt(int iChar) const;
```
#### <a name="parameters"></a>Parametreler

*iChar*  
Öğesindeki taban karakterin sıfır tabanlı dizin `CSimpleStringT` nesne. *İChar* parametresi değerinden büyük veya 0'a eşit ve döndürdüğü değerden daha az olmalıdır [GetLength](#getlength). Aksi takdirde, `GetAt` bir özel durum oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Bir `XCHAR` , belirli bir konumda bir dizedeki bir karakter içeriyor.

### <a name="remarks"></a>Açıklamalar

Tarafından belirtilen bir karakter döndürmek için bu yöntemi çağırın *iChar*. Aşırı yüklenmiş alt simge (**[]**) işleç için kullanışlı bir diğer ad olarak `GetAt`. Kullanarak bir özel durum oluşmadan null Sonlandırıcı adreslenebilir `GetAt`. Ancak, bunu tarafından katılmaz `GetLength`, ve döndürülen değer 0'dır.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `CSimpleStringT::GetAt`.

```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```

##  <a name="getbuffer"></a>  CSimpleStringT::GetBuffer

İç karakter arabelleği için bir işaretçi döndürür `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
PXSTR GetBuffer(int nMinBufferLength); 
PXSTR GetBuffer();
```
#### <a name="parameters"></a>Parametreler

*nMinBufferLength*  
Karakter arabelleği içerebileceği karakter en küçük sayısı. Bu değer, null sonlandırıcıyı ortasının içermez.

Varsa *nMinBufferLength* geçerli arabelleğin uzunluğundan büyük `GetBuffer` geçerli arabelleğini yok eder, istenen boyutta bir arabellek ile değiştirir ve nesne başvuru sayısı sıfır olarak sıfırlar. Daha önce çağrılırsa [LockBuffer](#lockbuffer) bu arabelleği, arabellek kilit kaybedersiniz.

### <a name="return-value"></a>Dönüş Değeri

Bir `PXSTR` nesnenin (null ile sonlandırılmış) karakter arabellek için işaretçi.

### <a name="remarks"></a>Açıklamalar

Arabellek içeriğini döndürmek için bu yöntemi çağırın `CSimpleStringT` nesne. Döndürülen `PXSTR` bir sabit değil ve bu nedenle doğrudan değiştirilmesine izin verir `CSimpleStringT` içeriği.

Tarafından döndürülen işaretçi kullanırsanız `GetBuffer` dize içeriklerini değiştirmek için çağırmalıdır [ReleaseBuffer](#releasebuffer) diğer kullanmadan önce `CSimpleStringT` üye yöntemi.

Tarafından döndürülen adresini `GetBuffer` çağrısından sonra geçerli olmayabilir `ReleaseBuffer` çünkü ek `CSimpleStringT` işlemleri neden olabilir `CSimpleStringT` ayrılabilecek arabellek. Arabellek uzunluğu değiştirmezseniz bırakılan değil `CSimpleStringT`.

Otomatik olarak arabellek olduğu zaman serbest `CSimpleStringT` nesnesi yok edildiğinde.

Dize uzunluğu kendiniz takip, sondaki boş karakter eklememeniz gerekir. Ancak, arabellek ile serbest bıraktığınızda son dize uzunluğu belirtmelisiniz `ReleaseBuffer`. Bir sonlandırıcı null karakter ekleme uzunluğu için -1 (varsayılan) geçirmesi gerekir. `ReleaseBuffer` ardından arabellek uzunluğunu belirler.

Karşılamak için yeterli bellek yoksa `GetBuffer` isteği, bu yöntemin oluşturduğu CMemoryException *.

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

##  <a name="getbuffersetlength"></a>  CSimpleStringT::GetBufferSetLength

İç karakter arabelleği için bir işaretçi döndürür `CSimpleStringT` kesilmesi ya da tam tümcesinde belirtilen uzunluğundan eşleşecek şekilde gerekirse uzunluğunu büyüyen nesne *nLength*.

### <a name="syntax"></a>Sözdizimi

```
PXSTR GetBufferSetLength(int nLength);
```
#### <a name="parameters"></a>Parametreler

*nLength*  
Tam boyutunu `CSimpleStringT` karakter karakter arabelleği.

### <a name="return-value"></a>Dönüş Değeri

A `PXSTR` nesnenin (null ile sonlandırılmış) karakter arabellek için işaretçi.

### <a name="remarks"></a>Açıklamalar

Belirtilen bir iç arabellek uzunluğunu almak için bu yöntemi çağırın `CSimpleStringT` nesne. Döndürülen `PXSTR` işaretçisi değil **const** ve bu nedenle doğrudan değiştirilmesine izin verir `CSimpleStringT` içeriği.

Tarafından döndürülen işaretçi kullanırsanız [GetBufferSetLength](#getbuffersetlength) dize içeriklerini değiştirmek için çağrı `ReleaseBuffer` iç durumunu güncelleştirmek için `CsimpleStringT` diğer kullanmadan önce `CSimpleStringT` yöntemleri.

Tarafından döndürülen adresini `GetBufferSetLength` çağrısından sonra geçerli olmayabilir `ReleaseBuffer` çünkü ek `CSimpleStringT` işlemleri neden olabilir `CSimpleStringT` ayrılabilecek arabellek. Arabellek uzunluğu değiştirmezseniz yeniden değil `CSimpleStringT`.

Otomatik olarak arabellek olduğu zaman serbest `CSimpleStringT` nesnesi yok edildiğinde.

Dize uzunluğu kendiniz takip, sondaki boş karakter eklemeyin. Arabellek kullanarak serbest bıraktığınızda, son dize uzunluğu belirtmelisiniz `ReleaseBuffer`. Çağırdığınızda bir sonlandırıcı null karakter ekleme, `ReleaseBuffer`, uzunluğu için -1 (varsayılan) geçirin `ReleaseBuffer`, ve `ReleaseBuffer` gerçekleştirecek bir `strlen` arabellekte uzunluğunu belirlemek için.

Başvuru sayımı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [Başvuru sayımı yoluyla, nesne kullanım ömrü Yönetimi](/windows/desktop/com/managing-object-lifetimes-through-reference-counting) Windows SDK içinde.

- [Başvuru sayma uygulayan](/windows/desktop/com/implementing-reference-counting) Windows SDK içinde.

- [Başvuru sayısı yönetmek için kuralları](/windows/desktop/com/rules-for-managing-reference-counts) Windows SDK içinde.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::GetBufferSetLength`.

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

##  <a name="getlength"></a>  CSimpleStringT::GetLength

Karakter sayısını döndürür `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
int GetLength() const throw();  
```
### <a name="return-value"></a>Dönüş Değeri

Dizedeki karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Nesnesinde karakter sayısını döndürmek için bu yöntemi çağırın. Sayı, bir null Sonlandırıcı içermez.

Çok baytlı karakter kümeleri (MBCS) için `GetLength` sayıları her 8-bit karakter; diğer bir deyişle, bir ön ve baytlık bir çok baytlı karakter iki bayt olarak sayılır. Bkz: [FreeExtra](#freeextra) örneği bu işlevi çağırmak için.

##  <a name="getmanager"></a>  CSimpleStringT::GetManager

Bellek Yöneticisi alır `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
IAtlStringMgr* GetManager() const throw();  
```
### <a name="return-value"></a>Dönüş Değeri

Bellek Yöneticisi için bir işaretçiye `CSimpleStringT` nesne.

### <a name="remarks"></a>Açıklamalar

Yöneticisi tarafından kullanılan bellek almak için bu yöntemi çağırın `CSimpleStringT` nesne. Bellek yöneticilerini ve dize nesneleri hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).

##  <a name="getstring"></a>  CSimpleStringT::GetString

Karakter dizesi alır.

### <a name="syntax"></a>Sözdizimi

```
PCXSTR GetString() const throw();
```
### <a name="return-value"></a>Dönüş Değeri

Null ile sonlandırılmış dizeye bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İle ilişkili bir karakter dizesini almak için bu yöntemi çağırın `CSimpleStringT` nesne.

> [!NOTE]
>  Döndürülen `PCXSTR` işaretçisi **const** ve doğrudan değiştirilmesine izin vermiyor `CSimpleStringT` içeriği.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::GetString`.

```cpp  
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```

##  <a name="isempty"></a>  CSimpleStringT::IsEmpty

Testleri bir `CSimpleStringT` boş koşul için nesne.

### <a name="syntax"></a>Sözdizimi

```
bool IsEmpty() const throw();  
```
### <a name="return-value"></a>Dönüş Değeri

Gerekirse TRUE döndürür `CSimpleStringT` nenesindeki 0 uzunluğu; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Nesne boş bir dize içerip içermediğini belirlemek için bu yöntemi çağırın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::IsEmpty`.

```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

##  <a name="lockbuffer"></a>  CSimpleStringT::LockBuffer

Başvuru sayımı devre dışı bırakır ve dize arabelleğindeki korur.

### <a name="syntax"></a>Sözdizimi

```
PXSTR LockBuffer();
```
### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CSimpleStringT` nesnesi veya null ile sonlandırılmış bir dize.

### <a name="remarks"></a>Açıklamalar

Arabelleği kilitlemek için bu yöntemi çağırın `CSimpleStringT` nesne. Çağırarak `LockBuffer`, başvuru sayısı için -1, dizenin bir kopyasını oluşturun. Başvuru sayısı değeri -1 olduğunda dize arabelleğindeki "kilitli" bir durumda olmasını olarak kabul edilir. Kilitli durumda olsa dizesi iki şekilde korunur:

- Bu dize kilitli dizeye atanmış olsa bile başka bir dize kilitli dizesinde verilere başvuru alabilirsiniz.

- Bu bir dize kilitli dizeye kopyalansa dahi kilitli dize hiçbir zaman başka bir dize başvurur.

Dize arabellek kilitleyerek arabellek özel beklemeye dizenin değişmeden kalır emin olun.

İle tamamladıktan sonra `LockBuffer`, çağrı [UnlockBuffer](#unlockbuffer) başvuru sayısı 1 olarak sıfırlanır.

> [!NOTE]
>  Çağırırsanız [GetBuffer](#getbuffer) kilitli bir arabellek ve, `GetBuffer` parametre `nMinBufferLength` arabellek kilit kaybedersiniz geçerli arabelleğin uzunluğundan için büyük,. Böyle bir çağrı `GetBuffer` geçerli arabelleğini yok eder, istenen boyutta bir arabellek ile değiştirir ve başvuru sayısı sıfır olarak sıfırlar.

Başvuru sayımı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [Başvuru sayımı yoluyla, nesne kullanım ömrü Yönetimi](/windows/desktop/com/managing-object-lifetimes-through-reference-counting) Windows SDK içinde

- [Başvuru sayma uygulayan](/windows/desktop/com/implementing-reference-counting) Windows SDK içinde

- [Başvuru sayısı yönetmek için kuralları](/windows/desktop/com/rules-for-managing-reference-counts) Windows SDK içinde

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::LockBuffer`.

```cpp  
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```

##  <a name="operator_at"></a>  CSimpleStringT::operator\[\]

Tek bir karakter karakter dizisinin erişmek için bu işlevi çağırın.

### <a name="syntax"></a>Sözdizimi

```
XCHAR operator[](int iChar) const;
```
#### <a name="parameters"></a>Parametreler

*iChar*  
Bir karakter dizesi, sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Aşırı yüklenmiş alt simge (**[]**) işleci sıfır tabanlı dizin tarafından belirtilen tek bir karakter döndürür *iChar*. Bu işleci için kolay bir alternatif, [GetAt](#getat) üye işlevi.

> [!NOTE]
>  Alt simge kullanabilirsiniz (**[]**) işleci, bir karakter değerini almak için bir `CSimpleStringT`, ancak bir karakter değerini değiştirmek için kullanamazsınız bir `CSimpleStringT`.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::operator []`.

```cpp  
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```

## <a name="operator_at"></a>  CSimpleStringT::operator \[\]

Tek bir karakter karakter dizisinin erişmek için bu işlevi çağırın.

### <a name="syntax"></a>Sözdizimi

``` 
XCHAR operator[](int iChar) const;
```

### <a name="parameters"></a>Parametreler

*iChar*  
Bir karakter dizesi, sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Aşırı yüklenmiş alt simge (**[]**) işleci sıfır tabanlı dizin tarafından belirtilen tek bir karakter döndürür *iChar*. Bu işleci için kolay bir alternatif, [GetAt](#getat) üye işlevi.

> [!NOTE]
>  Alt simge kullanabilirsiniz (**[]**) işleci, bir karakter değerini almak için bir `CSimpleStringT`, ancak bir karakter değerini değiştirmek için kullanamazsınız bir `CSimpleStringT`.


##  <a name="operator_add_eq"></a>  CSimpleStringT::operator +=

Mevcut bir dizenin sonuna yeni bir dize veya karakter birleştirir.

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

*pszSrc*  
Null ile sonlandırılmış dizeye bir işaretçi.

*strSrc*  
Varolan bir işaretçi `CSimpleStringT` nesne.

*ch*  
Eklenecek karakter.

### <a name="remarks"></a>Açıklamalar

Başka bir işleç kabul `CSimpleStringT` nesne ya da bir karakter. Bu bellek dikkat edin çünkü bu eklenen karakter için yeni bir depolama birimi ayrılabilir, bu birleştirme işleci kullandığınızda özel durumları oluşabilir `CSimpleStringT` nesne.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::operator +=`.

```cpp  
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```

##  <a name="operator_eq"></a>  CSimpleStringT::operator =

Yeni bir değer atar bir `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
CSimpleStringT& operator =(PCXSTR pszSrc); 
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```
#### <a name="parameters"></a>Parametreler

*pszSrc*  
Null ile sonlandırılmış dizeye bir işaretçi.

*strSrc*  
Varolan bir işaretçi `CSimpleStringT` nesne.

### <a name="remarks"></a>Açıklamalar

Hedef dize (sol taraf) zaten yeni veri deposu için büyük ise, hiçbir yeni bellek ayırma gerçekleştirilir. Bu bellek Not yeni depolama genellikle sonuç tutmak için ayrılmış olduğundan, atama işleci kullandığınızda, özel durumlar oluşabilir `CSimpleStringT` nesne.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::operator =`.

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

##  <a name="operator_pcxstr"></a>  CSimpleStringT::operator PCXSTR  

İçinde depolanan karakterlerin doğrudan erişir bir `CSimpleStringT` C stili dize olarak nesnesi.

### <a name="syntax"></a>Sözdizimi

```
operator PCXSTR() const throw();
```
### <a name="return-value"></a>Dönüş Değeri

Dizenin veri karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Hiçbir karakter kopyalanır; yalnızca bir işaretçi döndürülür. Bu işleç dikkat edin. Değiştirirseniz bir `CString` nesne karakter işaretçisi elde ettikten sonra bir işaretçinin geçersiz kılan bellek reallocation neden olabilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::operator PCXSTR`.

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

##  <a name="pcxstr"></a>  CSimpleStringT::PCXSTR

Bir sabit dize işaretçisi.

### <a name="syntax"></a>Sözdizimi

```
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;    
```
##  <a name="preallocate"></a>  CSimpleStringT::Preallocate

Belirli bir süre için bayt ayırır `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
void Preallocate( int nLength);
```
#### <a name="parameters"></a>Parametreler

*nLength*  
Tam boyutunu `CSimpleStringT` karakter karakter arabelleği.

### <a name="remarks"></a>Açıklamalar

Belirli arabellek boyutu için ayırmak için bu yöntemi çağırın `CSimpleStringT` nesne.

`CSimpleStringT` Karakter arabelleği için boşluk ayrılamıyor ise STATUS_NO_MEMORY özel durum oluşturur. Varsayılan olarak, bellek ayırma WIN32 API işlevleri tarafından gerçekleştirilen `HeapAlloc` veya `HeapReAlloc`.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::Preallocate`.

```cpp  
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```

##  <a name="pxstr"></a>  CSimpleStringT::PXSTR

Bir dizeye bir işaretçi.

### <a name="syntax"></a>Sözdizimi

```
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;  
```
##  <a name="releasebuffer"></a>  CSimpleStringT::ReleaseBuffer

Serbest denetimi tarafından ayrılan arabelleğin [GetBuffer](#getbuffer).

### <a name="syntax"></a>Sözdizimi

```
void ReleaseBuffer(int nNewLength = -1);
```
#### <a name="parameters"></a>Parametreler

*nNewLength*  
Yeni karakter, bir null Sonlandırıcı sayılmaz dize uzunluğu. Sonlandırılan dize null ise,-1 varsayılan değerini ayarlar `CSimpleStringT` boyut geçerli dize uzunluğu.

### <a name="remarks"></a>Açıklamalar

Yeniden kullanıma alabilmeniz veya boş dize nesnesinin arabelleğini için bu yöntemi çağırın. Biliyorsanız, dizedir null sonlandırılmış arabelleği, atlayabilirsiniz *nNewLength* bağımsız değişken. Sonlandırılan dizenizi null değilse, kullanın *nNewLength* uzunluğunu belirtmek için. Tarafından döndürülen adresini [GetBuffer](#getbuffer) çağrısından sonra geçersiz `ReleaseBuffer` veya diğer `CSimpleStringT` işlemi.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::ReleaseBuffer`.

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

##  <a name="releasebuffersetlength"></a>  CSimpleStringT::ReleaseBufferSetLength

Serbest denetimi tarafından ayrılan arabelleğin [GetBuffer](#getbuffer).

### <a name="syntax"></a>Sözdizimi

```
void ReleaseBufferSetLength(int nNewLength);
```
#### <a name="parameters"></a>Parametreler

*nNewLength*  
Yayımlanan dizenin uzunluğu

### <a name="remarks"></a>Açıklamalar

Bu işlev işlevsellik aşağıdakine benzer [ReleaseBuffer](#releasebuffer) dışında dize nesnesi için geçerli bir uzunluğu geçirilmelidir.

##  <a name="setat"></a>  CSimpleStringT::SetAt

Tek bir karakter gelen ayarlar bir `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
void SetAt(int iChar, XCHAR ch);
```
#### <a name="parameters"></a>Parametreler

*iChar*  
Öğesindeki taban karakterin sıfır tabanlı dizin `CSimpleStringT` nesne. *İChar* parametresi değerinden büyük veya 0'a eşit ve döndürdüğü değerden daha az olmalıdır [GetLength](#getlength).

*ch*  
Yeni karakter.

### <a name="remarks"></a>Açıklamalar

Konumunda bulunan karakteri üzerine yazmak için bu yöntemi çağırın *iChar*. Bu yöntem bir dize ise büyütür değil *iChar* varolan bir dizeyi sınırları aşıyor.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::SetAt`.

```cpp  
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
```

##  <a name="setmanager"></a>  CSimpleStringT::SetManager

Bellek Yöneticisi'nin belirtir `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
void SetManager(IAtlStringMgr* pStringMgr);
```
#### <a name="parameters"></a>Parametreler

*pStringMgr*  
Yeni bellek yöneticisi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Yöneticisi tarafından kullanılan yeni bir bellek belirtmek için bu yöntemi çağırın `CSimpleStringT` nesne. Bellek yöneticilerini ve dize nesneleri hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::SetManager`.

```cpp  
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```

##  <a name="setstring"></a>  CSimpleStringT::SetString

Dizenin ayarlar bir `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
void SetString(PCXSTR pszSrc, int nLength); 
void SetString(PCXSTR pszSrc);
```
#### <a name="parameters"></a>Parametreler

*pszSrc*  
Null ile sonlandırılmış dizeye bir işaretçi.

*nLength*  
Karakter sayısını *pszSrc*.

### <a name="remarks"></a>Açıklamalar

Bir dizeye kopyalar `CSimpleStringT` nesne. `SetString` eski dize arabelleğindeki verinin üzerine yazar.

Her iki sürümü `SetString` denetleyin olup olmadığını *pszSrc* null bir işaretçiyse ve ise, E_INVALIDARG hata oluşturur.

Bir parametre sürümünü `SetString` bekliyor *pszSrc* null ile sonlandırılmış dizeye işaret edecek şekilde.

İki parametre sürümünü `SetString` ayrıca bekliyor *pszSrc* null ile sonlandırılmış bir dize olmalıdır. Kullandığı *nLength* dize uzunluğu olarak bir null Sonlandırıcı ilk karşılaştığında sürece.

İki parametre sürümünü `SetString` da denetler olmadığını *pszSrc* geçerli arabellekteki bir konuma işaret `CSimpleStringT`. Bu özel durumda `SetString` , dize verileri, arabelleğe kopyalar, dize verilerini geçersiz kılmaz bir bellek kopyalama işlevi kullanır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::SetString`.

```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```

##  <a name="stringlength"></a>  CSimpleStringT::StringLength

Belirtilen dizenin karakter sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```
#### <a name="parameters"></a>Parametreler

*psz*  
Null ile sonlandırılmış dizeye bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Karakter sayısı *psz*; bir null Sonlandırıcı sayılmaz.

### <a name="remarks"></a>Açıklamalar

İşaret ettiği dizedeki karakter sayısını almak için bu yöntemi çağırın *psz*.

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::StringLength`.

```cpp  
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
```

##  <a name="truncate"></a>  CSimpleStringT::Truncate

Yeni uzunluğu dizeye keser.

### <a name="syntax"></a>Sözdizimi

```
void Truncate(int nNewLength);
```
#### <a name="parameters"></a>Parametreler

*nNewLength*  
Yeni dize uzunluğu.

### <a name="remarks"></a>Açıklamalar

Yeni uzunluğu dizeye içeriğini kesmek için bu yöntemi çağırın.

> [!NOTE]
>  Bu, ayrılan bir arabellek uzunluğu etkilemez. Geçerli arabelleğini artırmak veya azaltmak için bkz: [FreeExtra](#freeextra) ve [Preallocate](#preallocate).

### <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir `CSimpleStringT::Truncate`.

```cpp  
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
```

##  <a name="unlockbuffer"></a>  CSimpleStringT::UnlockBuffer

Arabelleğin kilidini açarak `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
void UnlockBuffer() throw();
```
### <a name="remarks"></a>Açıklamalar

Dize başvuru sayısı 1 olarak sıfırlamak için bu yöntemi çağırın.

`CSimpleStringT` Yıkıcı otomatik olarak çağırır `UnlockBuffer` yok edici çağrıldığında arabellek kilitlenmediğinden emin olmak için. Bu yöntem bir örnek için bkz [LockBuffer](#lockbuffer).

##  <a name="dtor"></a>  CSimpleStringT:: ~ CSimpleStringT

Yok eder bir `CSimpleStringT` nesne.

### <a name="syntax"></a>Sözdizimi

```
~CSimpleStringT() throw();
```
### <a name="remarks"></a>Açıklamalar

Yok etmek için bu yöntemi çağırın `CSimpleStringT` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)