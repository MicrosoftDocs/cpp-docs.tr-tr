---
title: "CSimpleStringT sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: acbf4753bb29b8f28cac9fe4fb6ceff72ceda8a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csimplestringt-class"></a>CSimpleStringT sınıfı
Bu sınıfın temsil ettiği bir `CSimpleStringT` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename BaseType>
class CSimpleStringT
```  
  
### <a name="parameters"></a>Parametreler  
 `BaseType`  
 String sınıfı karakter türü. Aşağıdakilerden biri olabilir:  
  
- `char`(için ANSI karakter dizelerini).  
  
- `wchar_t`(için Unicode karakter dizeleri).  
  
- **TCHAR** (için ANSI ve Unicode karakter dizelerini).  

## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleStringT::PCXSTR](#pcxstr)|Bir sabit dize için bir işaretçi.|  
|[CSimpleStringT::PXSTR](#pxstr)|Bir dize için bir işaretçi.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleStringT::CSimpleStringT](#ctor)|Yapıları `CSimpleStringT` çeşitli şekillerde nesneleri.|  
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|Yok Edicisi.|  

  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleStringT::Append](#append)|Ekler bir `CSimpleStringT` varolan bir nesne `CSimpleStringT` nesne.|  
|[CSimpleStringT::AppendChar](#appendchar)|Var olan bir karakteri ekler `CSimpleStringT` nesnesi.|  
|[CSimpleStringT::CopyChars](#copychars)|Bir karakterin veya karakter başka bir dizeye kopyalar.|  
|[CSimpleStringT::CopyCharsOverlapped](#copycharsoverlapped)|Bir karakterin veya karakter içinde arabellekleri çakışma başka bir dizeye kopyalar.|  
|[CSimpleStringT::Empty](#empty)|Bir dize uzunluğu sıfır zorlar.|  
|[CSimpleStringT::FreeExtra](#freeextra)|Dize nesnesi tarafından önceden ayrılmış herhangi bir ek bellek boşaltır.|  
|[CSimpleStringT::GetAllocLength](#getalloclength)|Ayrılmış uzunluğunu alır bir `CSimpleStringT` nesnesi.|  
|[CSimpleStringT::GetAt](#getat)|Verilen konumunda bulunan karakteri döndürür.|  
|[CSimpleStringT::GetBuffer](#getbuffer)|Karakter işaretçi döndüren bir `CSimpleStringT`.|  
|[CSimpleStringT::GetBufferSetLength](#getbuffersetlength)|Karakter işaretçi döndüren bir `CSimpleStringT`, belirtilen uzunluğa kesiliyor.|  
|[CSimpleStringT::GetLength](#getlength)|Karakter sayısını verir bir `CSimpleStringT` nesnesi.|  
|[CSimpleStringT::GetManager](#getmanager)|Bellek Yöneticisi'nin alır `CSimpleStringT` nesnesi.|  
|[CSimpleStringT::GetString](#getstring)|Karakter dizesini alır.|  
|[CSimpleStringT::IsEmpty](#isempty)|Testleri olup bir `CSimpleStringT` nesne herhangi bir karakter içeriyor.|  
|[CSimpleStringT::LockBuffer](#lockbuffer)|Başvuru sayım devre dışı bırakır ve arabellek dizesinde korur.|  
|[CSimpleStringT::Preallocate](#preallocate)|Belirli bir bellek miktarı için karakter arabellek ayırır.|  
|[CSimpleStringT::ReleaseBuffer](#releasebuffer)|Serbest denetim tarafından döndürülen arabellek `GetBuffer`.|  
|[CSimpleStringT::ReleaseBufferSetLength](#releasebuffersetlength)|Serbest denetim tarafından döndürülen arabellek `GetBuffer`.|  
|[CSimpleStringT::SetAt](#setat)|Bir karakteri belirtilen konumda ayarlar.|  
|[CSimpleStringT::SetManager](#setmanager)|Bellek Yöneticisi'nin ayarlar bir `CSimpleStringT` nesnesi.|  
|[CSimpleStringT::SetString](#setstring)|Dizenin ayarlar bir `CSimpleStringT` nesnesi.|  
|[CSimpleStringT::StringLength](#stringlength)|Karakter sayısını belirtilen dizeyi döndürür.|  
|[CSimpleStringT::Truncate](#truncate)|Belirtilen uzunlukta dizeye tamsayıya dönüştürür.|  
|[CSimpleStringT::UnlockBuffer](#unlockbuffer)|Başvuru sayım sağlar ve arabellek dizesinde serbest bırakır.|  

### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleStringT::operator PCXSTR](#operator_pcxstr)|İçinde depolanan karakterlerin doğrudan erişir bir `CSimpleStringT` C stili dize olarak nesne.|  
|[CSimpleStringT::operator\[\]](#operator_at)|Belirtilen konumdaki karakteri döndürür — işleci değiştirme `GetAt`.|  
|[CSimpleStringT::operator +=](#operator_add_eq)|Varolan bir dizeyi sonuna yeni bir dize art arda ekler.|  
|[CSimpleStringT::operator =](#operator_eq)|Yeni bir değer atayan bir `CSimpleStringT` nesnesi.|  
  
### <a name="remarks"></a>Açıklamalar  
 `CSimpleStringT`Visual C++'ın desteklediği çeşitli dize sınıflar için temel sınıftır. Dize nesnesi ve temel ara bellek düzenlemesi bellek yönetimi için en az destek sağlar. Daha gelişmiş dize nesneler için bkz: [CStringT sınıfı](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpstr.h  


## <a name="append"></a>CSimpleStringT::Append
Ekler bir `CSimpleStringT` varolan bir nesne `CSimpleStringT` nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void Append(const CSimpleStringT& strSrc); 
void Append(PCXSTR pszSrc, int nLength); 
void Append(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>Parametreler  
 `strSrc`  
 `CSimpleStringT` Eklenecek nesne.  
  
 `pszSrc`  
 Eklenecek karakterleri içeren bir dize için bir işaretçi.  
  
 `nLength`  
 Eklenecek karakter sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Var olan eklemek için bu yöntemi çağırabilmeniz `CSimpleStringT` başka bir nesneye `CSimpleStringT` nesnesi.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::Append`.  
  
```cpp  
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```
  
##  <a name="appendchar"></a>CSimpleStringT::AppendChar
Var olan bir karakteri ekler `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void AppendChar(XCHAR ch);
```  
#### <a name="parameters"></a>Parametreler  
 *Ch*  
 Eklenecek karakter  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen karakter varolan sonuna eklemek için bu işlevi çağırmak `CSimpleStringT` nesnesi.  
  
##  <a name="copychars"></a>CSimpleStringT::CopyChars  
 Bir karakterin veya karakter kopyalar bir `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
static void CopyChars(
  XCHAR* pchDest,
  const XCHAR* pchSrc, 
  int nChars) throw();
```  
#### <a name="parameters"></a>Parametreler  
 `pchDest`  
 Bir karakter dizesi için bir işaretçi.  
  
 `pchSrc`  
 Kopyalanacak karakterler içeren bir dize için bir işaretçi.  
  
 `nChars`  
 Sayısı `pchSrc` kopyalanacak karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 Karakterlerinden kopyalamak için bu yöntemi çağırın `pchSrc` için `pchDest` dize.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::CopyChars`.  
  
```cpp  
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```
  
##  <a name="copycharsoverlapped"></a>CSimpleStringT::CopyCharsOverlapped
Bir karakterin veya karakter kopyalar bir `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
static void CopyCharsOverlapped(
  XCHAR* pchDest,
  const XCHAR* pchSrc,
  int nChars) throw(); 
```  
#### <a name="parameters"></a>Parametreler  
 `pchDest`  
 Bir karakter dizesi için bir işaretçi.  
  
 `pchSrc`  
 Kopyalanacak karakterler içeren bir dize için bir işaretçi.  
  
 `nChars`  
 Sayısı `pchSrc` kopyalanacak karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 Karakterlerinden kopyalamak için bu yöntemi çağırın `pchSrc` için `pchDest` dize. Farklı `CopyChars`, `CopyCharsOverlapped` çakışan karakter önbelleklerden kopyalama için güvenli bir yöntem sağlar.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CSimpleStringT::CopyChars](#copychars), veya kaynak kodu `CSimpleStringT::SetString` (atlsimpstr.h içinde bulunur).  
  
##  <a name="ctor"></a>CSimpleStringT::CSimpleStringT  
 Oluşturan bir `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr); 
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr); 
CSimpleStringT(const CSimpleStringT& strSrc); 
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw(); 
```  
#### <a name="parameters"></a>Parametreler  
 `strSrc`  
 Var olan `CSimpleStringT` bu kopyalanacak nesne `CSimpleStringT` nesne.  
  
 `pchSrc`  
 Karakter uzunluğunda bir işaretçi `nLength`, sonlandırıldı null.  
  
 `pszSrc`  
 Bu kopyalanacak null ile sonlandırılmış bir dize `CSimpleStringT` nesnesi.  
  
 `nLength`  
 Karakter sayısını `pch`.  
  
 `pStringMgr`  
 Bellek Yöneticisi'nin bir işaretçi `CSimpleStringT` nesnesi. Hakkında daha fazla bilgi için `IAtlStringMgr` ve bellek yönetimi için `CSimpleStringT`, bkz: [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir oluşturmak `CSimpleStringT` nesnesi. Oluşturucular yeni ayrılmış depolama alanına giriş verilerini kopyaladığından bellek özel durumlara neden olabilir.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::CSimpleStringT` ATL kullanarak `typedef` `CSimpleString`. `CSimpleString`sınıf şablonu yaygın olarak kullanılan uzmanlığı olan `CSimpleStringT`.  
  
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

  
##  <a name="empty"></a>CSimpleStringT::Empty
Böylece `CSimpleStringT` boş bir dize nesnesi ve uygun şekilde belleği serbest bırakır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void Empty() throw();  
```  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [dizeleri: CString özel durum Temizleme](../cstring-exception-cleanup.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::Empty`.  
  
```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());  
```  
  
##  <a name="freeextra"></a>CSimpleStringT::FreeExtra
Dizesi tarafından önceden ayrılmış ancak artık gerekli ek belleği serbest bırakır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void FreeExtra(); 
```  
### <a name="remarks"></a>Açıklamalar  
 Bu dize nesnesi tarafından kullanılan bellek yükünü azaltmanız gerekir. Yöntemi tarafından döndürülen tam uzunluk arabelleğe yeniden ayırır [GetLength](#getlength).  
  
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
 Bu örnek çıkışı aşağıdaki gibidir:  
  
 `Alloc length is 1031, String length is 1024`  
  
 `Alloc length is 1031, String length is 15`  
  
 `Alloc length is 15, String length is 15`  
  
##  <a name="getalloclength"></a>CSimpleStringT::GetAllocLength  
Ayrılmış uzunluğunu alır bir `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
int GetAllocLength() const throw();  
```  
### <a name="return-value"></a>Dönüş Değeri  
 Bu nesne için ayrılan karakter sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ayrılmış karakterleri sayısını belirlemek için bu yöntemi çağırın `CSimpleStringT` nesnesi. Bkz: [FreeExtra](#freeextra) bu işlev çağırma örneği için.  
  
##  <a name="getat"></a>CSimpleStringT::GetAt  
Bir karakter döndürür bir `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
XCHAR GetAt(int iChar) const;
```  
#### <a name="parameters"></a>Parametreler  
 `iChar`  
 Karakter, sıfır tabanlı dizini `CSimpleStringT` nesnesi. `iChar` Parametresi değerinden büyük veya 0 değerine eşit ve tarafından döndürülen değer küçük olmalıdır [GetLength](#getlength). Aksi takdirde, `GetAt` bir özel durum oluşturur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `XCHAR` , dize belirtilen konumda bir karakter içeriyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirlenen bir karakterin döndürmek için bu yöntemi çağırabilmeniz `iChar`. Aşırı yüklenmiş alt simge (`[]`) işleç için kullanışlı bir diğer ad olarak `GetAt`. Kullanarak bir özel durum oluşturmadan null Sonlandırıcı adreslenebilir `GetAt`. Ancak, bunu tarafından sayılmaz `GetLength`, ve döndürülen değer 0'dır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `CSimpleStringT::GetAt`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```
  
##  <a name="getbuffer"></a>CSimpleStringT::GetBuffer  
İç karakter arabellek için bir işaretçi döndürür `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
PXSTR GetBuffer(int nMinBufferLength); 
PXSTR GetBuffer();
```  
#### <a name="parameters"></a>Parametreler  
 `nMinBufferLength`  
 Karakter arabellek tutabilir karakter minimum sayısı. Bu değer null Sonlandırıcı alanı içermez.  
  
 Varsa `nMinBufferLength` geçerli arabelleğin uzunluğundan büyük `GetBuffer` geçerli arabellek yok eder, istenen boyutta bir arabellek değiştirir ve nesne başvurusu sayısı sıfır olarak sıfırlar. Daha önce adı, [LockBuffer](#lockbuffer) bu arabelleği, arabellek kilit kaybedersiniz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `PXSTR` nesnenin (boşluksuz) karakter arabellek işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Arabellek içeriğini döndürmek için bu yöntemi çağırabilmeniz `CSimpleStringT` nesnesi. Döndürülen `PXSTR` bir sabit değil ve bu nedenle doğrudan değiştirilmesine izin verir `CSimpleStringT` içeriği.  
  
 Tarafından döndürülen işaretçi kullanırsanız `GetBuffer` dize içeriklerini değiştirme için çağırmalısınız [ReleaseBuffer](#releasebuffer) diğer kullanmadan önce `CSimpleStringT` üye yöntemleri.  
  
 Tarafından döndürülen adresi `GetBuffer` çağrısından sonra geçerli olmayabilir `ReleaseBuffer` çünkü ek `CSimpleStringT` operations neden olabilecek `CSimpleStringT` ayrılabilecek arabellek. Uzunluğu değişiklik yapmazsanız, arabellek yeniden tahsis değil `CSimpleStringT`.  
  
 Arabellek otomatik olarak bellektir ne zaman serbest `CSimpleStringT` nesne yok.  
  
 Dize uzunluğu kendiniz kaydını tutabilirsiniz, sonlandırma null karakteri eklemediğinizden. Ancak, arabellekle bıraktığınızda, son dize uzunluğu belirtmelisiniz `ReleaseBuffer`. Sonlandırma bir null karakter ekleme, -1 (varsayılan) uzunluğu geçirmelisiniz. `ReleaseBuffer`ardından arabellek uzunluğunu belirler.  
  
 Karşılamak için yeterli bellek varsa `GetBuffer` isteği, bu yöntem oluşturulur CMemoryException *.  
  
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
  
##  <a name="getbuffersetlength"></a>CSimpleStringT::GetBufferSetLength  
İç karakter arabellek için bir işaretçi döndürür `CSimpleStringT` kesilmesi ya da tam olarak belirtilen uzunluğu ile eşleşecek şekilde gerekirse uzunluğu büyüyen nesne `nLength`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
PXSTR GetBufferSetLength(int nLength);
```  
#### <a name="parameters"></a>Parametreler  
 `nLength`  
 Tam boyutunu `CSimpleStringT` karakterleri karakter arabellek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `PXSTR` nesnenin (boşluksuz) karakter arabellek işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen bir iç arabellek uzunluğu almak için bu yöntemi çağırın `CSimpleStringT` nesnesi. Döndürülen `PXSTR` işaretçisi değil `const` ve böylece doğrudan değiştirilmesine izin verir `CSimpleStringT` içeriği.  
  
 Tarafından döndürülen işaretçi kullanırsanız [GetBufferSetLength](#getbuffersetlength) dize içeriklerini değiştirme çağrısı `ReleaseBuffer` iç durumunu güncelleştirmek için `CsimpleStringT` diğer kullanmadan önce `CSimpleStringT` yöntemleri.  
  
 Tarafından döndürülen adresi `GetBufferSetLength` çağrısından sonra geçerli olmayabilir `ReleaseBuffer` çünkü ek `CSimpleStringT` operations neden olabilecek `CSimpleStringT` ayrılabilecek arabellek. Uzunluğu değişiklik yapmazsanız, arabellek yeniden atandığında değil `CSimpleStringT`.  
  
 Arabellek otomatik olarak bellektir ne zaman serbest `CSimpleStringT` nesne yok.  
  
 Değil, dize uzunluğu kendiniz izlemek, sonlandırma null karakteri eklemeyin. Kullanarak arabellek serbest bıraktığınızda, son dize uzunluğu belirtmelisiniz `ReleaseBuffer`. Çağırdığınızda sonlandırma bir null karakter ekleme, `ReleaseBuffer`, -1 (varsayılan) uzunluğa geçirin `ReleaseBuffer`, ve `ReleaseBuffer` gerçekleştirecek bir `strlen` uzunluğu belirlemek için arabellek üzerinde.  
  
 Başvuru sayım hakkında daha fazla bilgi için aşağıdaki makalelere bakın:  
  
- [Başvuru sayımı yoluyla nesne yaşam süresi yönetme](http://msdn.microsoft.com/library/windows/desktop/ms687260) Windows SDK. 
  
- [Başvuru sayım uygulama](http://msdn.microsoft.com/library/windows/desktop/ms693431) Windows SDK.
  
- [Başvuru sayıları yönetmek için kuralları](http://msdn.microsoft.com/library/windows/desktop/ms692481) Windows SDK.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::GetBufferSetLength`.  
  
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
  
##  <a name="getlength"></a>CSimpleStringT::GetLength  
Karakter sayısını verir `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
int GetLength() const throw();  
```  
### <a name="return-value"></a>Dönüş Değeri  
 Dizedeki karakter sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne karakter sayısını döndürmek için bu yöntemi çağırın. Sayı null Sonlandırıcı içermez.  
  
 (MBCS) birden çok baytlı karakter kümeleri için `GetLength` sayıları her 8 bit karakter; diğer bir deyişle, bir sağlama ve izi bayt bir çok baytlı karakter iki bayt olarak sayılır. Bkz: [FreeExtra](#freeextra) bu işlev çağırma örneği için.  
  
##  <a name="getmanager"></a>CSimpleStringT::GetManager  
Bellek Yöneticisi'nin alır `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
IAtlStringMgr* GetManager() const throw();  
```  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek Yöneticisi için bir işaretçi `CSimpleStringT` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöneticisi tarafından kullanılan bellek almak için bu yöntemi çağırın `CSimpleStringT` nesnesi. Bellek yöneticilerini ve dize nesneleri hakkında daha fazla bilgi için bkz: [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).  
  
##  <a name="getstring"></a>CSimpleStringT::GetString
Karakter dizesini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
PCXSTR GetString() const throw();
```  
### <a name="return-value"></a>Dönüş Değeri  
 Bir null olarak sonlandırılan bir karakter dizesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 İle ilişkili karakter dizesini almak için bu yöntemi çağırın `CSimpleStringT` nesnesi.  
  
> [!NOTE]
>  Döndürülen `PCXSTR` işaretçi `const` ve doğrudan değiştirilmesine izin vermiyor `CSimpleStringT` içeriği.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::GetString`.  
  
```cpp  
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```
  
##  <a name="isempty"></a>CSimpleStringT::IsEmpty  
Testleri bir `CSimpleStringT` nesnesi için boş koşulu.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool IsEmpty() const throw();  
```  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** varsa `CSimpleStringT` nesnesi uzunluğu 0 sahiptir; Aksi halde **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne boş bir dize içerip içermediğini belirlemek için bu yöntemi çağırın.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::IsEmpty`.  
  
```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```
  
##  <a name="lockbuffer"></a>CSimpleStringT::LockBuffer  
Başvuru sayım devre dışı bırakır ve arabellek dizesinde korur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
PXSTR LockBuffer();
```  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CSimpleStringT` nesne ya da null ile sonlandırılmış bir dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Arabelleği kilitlemek için bu yöntemi çağırın `CSimpleStringT` nesnesi. Çağırarak `LockBuffer`, başvuru sayımı için -1 ile dize bir kopyasını oluşturun. Başvuru sayı değeri -1 olduğunda, arabellek dizesindeki "kilitli" durumda olarak kabul edilir. Kilitli bir durumda karşın, dize iki yolla korunur:  
  
-   Bu dizeyi kilitli dizeye atanmış olsa bile başka bir dize kilitli dizesinde verilere bir başvuru elde edebilirsiniz.  
  
-   Bu bir dize kilitli dizeye kopyalansa bile kilitli dize hiçbir zaman başka bir dize başvurur.  
  
 Arabellekte dize kilitleyerek dizesinin özel arabellek beklemeye değişmeden kalır emin olun.  
  
 İle bitirdikten sonra `LockBuffer`, çağrı [UnlockBuffer](#unlockbuffer) başvuru sayısı 1 olarak sıfırlanır.  
  
> [!NOTE]
>  Çağırırsanız [GetBuffer](#getbuffer) kilitli bir arabellek ve bunu ayarlamak `GetBuffer` parametresi `nMinBufferLength` arabellek kilit kaybedersiniz büyüktür için geçerli arabellek uzunluğu,. Bu tür bir çağrı `GetBuffer` geçerli arabellek yok eder, istenen boyutta bir arabellek değiştirir ve başvuru sayısı sıfır olarak sıfırlar.  
  
 Başvuru sayım hakkında daha fazla bilgi için aşağıdaki makalelere bakın:  
  
- [Başvuru sayımı yoluyla nesne yaşam süresi yönetme](http://msdn.microsoft.com/library/windows/desktop/ms687260) Windows SDK  
  
- [Başvuru sayım uygulama](http://msdn.microsoft.com/library/windows/desktop/ms693431) Windows SDK  
  
- [Başvuru sayıları yönetmek için kuralları](http://msdn.microsoft.com/library/windows/desktop/ms692481) Windows SDK  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::LockBuffer`.  
  
```cpp  
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```
  
##  <a name="operator_at"></a>CSimpleStringT::operator\[\]  
Tek bir karakterin karakter dizisinin erişmek için bu işlevini çağırın.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
XCHAR operator[](int iChar) const;
```  
#### <a name="parameters"></a>Parametreler  
 `iChar`  
 Dizedeki karakter sıfır tabanlı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşırı yüklenmiş alt simge (`[]`) operatörü içindeki sıfır tabanlı dizin tarafından belirtilen tek bir karakter döndürür `iChar`. Bu işleç için uygun bir alternatif olarak [GetAt](#getat) üye işlevi.  
  
> [!NOTE]
>  Alt simge kullanabilirsiniz (`[]`) bir karakter değerini almak için işleci bir `CSimpleStringT`, ancak bir karakter değerini değiştirmek için kullanamazsınız bir `CSimpleStringT`.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren **CSimpleStringT::operator []**.  
  
```cpp  
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```
  
## <a name="operator_at"></a>CSimpleStringT::operator\[\]
Tek bir karakterin karakter dizisinin erişmek için bu işlevini çağırın.  
  
### <a name="syntax"></a>Sözdizimi  
  
```   
XCHAR operator[](int iChar) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `iChar`  
 Dizedeki karakter sıfır tabanlı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşırı yüklenmiş alt simge (`[]`) operatörü içindeki sıfır tabanlı dizin tarafından belirtilen tek bir karakter döndürür `iChar`. Bu işleç için uygun bir alternatif olarak [GetAt](#getat) üye işlevi.  
  
> [!NOTE]
>  Alt simge kullanabilirsiniz (`[]`) bir karakter değerini almak için işleci bir `CSimpleStringT`, ancak bir karakter değerini değiştirmek için kullanamazsınız bir `CSimpleStringT`.  
  
  
##  <a name="operator_add_eq"></a>CSimpleStringT::operator +=  
Varolan bir dizeyi sonuna yeni bir dize veya karakter birleştirir.  
  
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
 `pszSrc`  
 Sonlandırılmış bir dize için bir işaretçi.  
  
 `strSrc`  
 Var olan bir işaretçi `CSimpleStringT` nesnesi.  
  
 *Ch*  
 Eklenecek karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç başka kabul `CSimpleStringT` nesnesi veya bir karakter. Bu bellek Not özel durumlar için eklenen karakter için yeni bir depolama birimi ayrılan çünkü bu birleştirme işleci kullandığınızda oluşabilir `CSimpleStringT` nesnesi.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren **CSimpleStringT::operator +=**.  
  
```cpp  
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```
  
##  <a name="operator_eq"></a>CSimpleStringT::operator =  
Yeni bir değer atayan bir `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
CSimpleStringT& operator =(PCXSTR pszSrc); 
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```  
#### <a name="parameters"></a>Parametreler  
 `pszSrc`  
 Sonlandırılmış bir dize için bir işaretçi.  
  
 `strSrc`  
 Var olan bir işaretçi `CSimpleStringT` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hedef dizesi (sol tarafta) zaten yeni veri deposu için yeterince büyük olduğundan, yeni bir bellek ayırma gerçekleştirilir. Bu bellek Not yeni depolama genellikle sonuç tutmak için ayrılmış olduğundan, atama işleci kullandığınızda özel durumlar oluşabilir `CSimpleStringT` nesnesi.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren **CSimpleStringT::operator =**.  
  
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
  
##  <a name="operator_pcxstr"></a>CSimpleStringT::operator PCXSTR  

 İçinde depolanan karakterlerin doğrudan erişir bir `CSimpleStringT` C stili dize olarak nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
operator PCXSTR() const throw();
```  
### <a name="return-value"></a>Dönüş Değeri  
 Dizesinin veri için bir karakter işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir karakter kopyalanır; yalnızca bir işaretçi döndürdü. Bu işleç ile dikkatli olun. Değiştirirseniz bir `CString` nesne karakter işaretçi aldıktan sonra yeniden ayırma işaretçinin geçersiz kılar bellek neden olabilir.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren **CSimpleStringT::operator PCXSTR**.  
  
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
  
##  <a name="pcxstr"></a>CSimpleStringT::PCXSTR
Bir sabit dize için bir işaretçi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;    
```  
##  <a name="preallocate"></a>CSimpleStringT::Preallocate  
Bayt için belirli bir miktarda ayırır `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void Preallocate( int nLength);
```  
#### <a name="parameters"></a>Parametreler  
 `nLength`  
 Tam boyutunu `CSimpleStringT` karakterleri karakter arabellek.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli bir arabellek boyutu için ayırmak için bu yöntemi çağırın `CSimpleStringT` nesnesi.  
  
 `CSimpleStringT`oluşturan bir `STATUS_NO_MEMORY` alanı için karakter arabellek ayıramadı ise özel durum. Varsayılan olarak, bellek ayırma WIN32 API işlevleri tarafından gerçekleştirilen `HeapAlloc` veya `HeapReAlloc`.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::Preallocate`.  
  
```cpp  
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```
  
##  <a name="pxstr"></a>CSimpleStringT::PXSTR  
Bir dize için bir işaretçi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;  
```  
##  <a name="releasebuffer"></a>CSimpleStringT::ReleaseBuffer  
Serbest denetimi tarafından ayrılan arabellek [GetBuffer](#getbuffer).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void ReleaseBuffer(int nNewLength = -1);
```  
#### <a name="parameters"></a>Parametreler  
 `nNewLength`  
 Null Sonlandırıcı saymaz karakter dizesini yeni uzunluğu. Dize sonlandırıldı de null ise,-1 varsayılan değeri ayarlar `CSimpleStringT` geçerli dize uzunluğu boyut.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden kullanıma alabilmeniz veya dize nesnesi arabelleği serbest için bu yöntemi çağırın. Biliyorsanız sonlandırıldı null dizedir arabelleği, size atlayabilirsiniz `nNewLength` bağımsız değişkeni. Sonlandırılmış dizenizi null değilse, kullanın `nNewLength` uzunluğunu belirtmek için. Tarafından döndürülen adresi [GetBuffer](#getbuffer) çağrısından sonra geçersiz `ReleaseBuffer` veya diğer `CSimpleStringT` işlemi.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::ReleaseBuffer`.  
  
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
  
##  <a name="releasebuffersetlength"></a>CSimpleStringT::ReleaseBufferSetLength

Serbest denetimi tarafından ayrılan arabellek [GetBuffer](#getbuffer).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void ReleaseBufferSetLength(int nNewLength);
```  
#### <a name="parameters"></a>Parametreler  
 `nNewLength`  
 Yayımlanan dize uzunluğu  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev işlevsel olarak benzer [ReleaseBuffer](#releasebuffer) dışında dize nesnesi için geçerli bir uzunluğu geçirilmelidir.  
  
##  <a name="setat"></a>CSimpleStringT::SetAt  
Bir tek karakteri ayarlar bir `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void SetAt(int iChar, XCHAR ch);
```  
#### <a name="parameters"></a>Parametreler  
 `iChar`  
 Karakter, sıfır tabanlı dizini `CSimpleStringT` nesnesi. `iChar` Parametresi değerinden büyük veya 0 değerine eşit ve tarafından döndürülen değer küçük olmalıdır [GetLength](#getlength).  
  
 *Ch*  
 Yeni karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 Konumunda bulunan karakteri üzerine yazmak için bu yöntemi çağırabilmeniz `iChar`. Bu yöntem dize varsa büyütür değil `iChar` varolan dizesi sınırları aşıyor.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::SetAt`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
``` 
  
##  <a name="setmanager"></a>CSimpleStringT::SetManager  
Bellek Yöneticisi'nin belirtir `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void SetManager(IAtlStringMgr* pStringMgr);
```  
#### <a name="parameters"></a>Parametreler  
 `pStringMgr`  
 Yeni bellek yöneticisi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöneticisi tarafından kullanılan yeni bir bellek belirtmek için bu yöntemi çağırın `CSimpleStringT` nesnesi. Bellek yöneticilerini ve dize nesneleri hakkında daha fazla bilgi için bkz: [bellek yönetimi ve CStringT](../memory-management-with-cstringt.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::SetManager`.  
  
```cpp  
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```
  
##  <a name="setstring"></a>CSimpleStringT::SetString  
Dizenin ayarlar bir `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void SetString(PCXSTR pszSrc, int nLength); 
void SetString(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>Parametreler  
 `pszSrc`  
 Sonlandırılmış bir dize için bir işaretçi.  
  
 `nLength`  
 Karakter sayısını `pszSrc`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizeye kopyalama `CSimpleStringT` nesnesi. `SetString`eski dize veri arabelleği üzerine yazar.  
  
 Her iki sürümü `SetString` denetleyin olup olmadığını `pszSrc` null işaretçi ve ise, throw bir **E_INVALIDARG** hata.  
  
 Bir parametre sürümü `SetString` bekliyor `pszSrc` null ile sonlandırılmış bir dizeye yönlendirin.  
  
 İki parametre sürümü `SetString` de bekliyor `pszSrc` null ile sonlandırılmış bir dize olmalıdır. Kullandığı `nLength` dize uzunluğu olarak null Sonlandırıcı ilk bulduğu sürece.  
  
 İki parametre sürümü `SetString` ayrıca denetler olup olmadığını `pszSrc` geçerli arabellekte bir konumda işaret `CSimpleStringT`. Bu özel durumda `SetString` arabelleğini geri dize verilerini kopyalar, dize verilerini üzerine yazmaz bir bellek kopyalama işlevini kullanır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::SetString`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```
  
##  <a name="stringlength"></a>CSimpleStringT::StringLength  
Karakter sayısını belirtilen dizeyi döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```  
#### <a name="parameters"></a>Parametreler  
 `psz`  
 Sonlandırılmış bir dize için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karakter sayısını `psz`; null Sonlandırıcı sayım değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Gösterdiği dizedeki karakter sayısını almak için bu yöntemi çağırın `psz`.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::StringLength`.  
  
```cpp  
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
``` 
  
##  <a name="truncate"></a>CSimpleStringT::Truncate
Yeni uzunluğu dizeye tamsayıya dönüştürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void Truncate(int nNewLength);
```  
#### <a name="parameters"></a>Parametreler  
 `nNewLength`  
 Dize yeni uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni uzunluğu dizeye içeriğini kesmek için bu yöntemi çağırın.  
  
> [!NOTE]
>  Bu, ayrılan arabellek uzunluğu etkilemez. Geçerli arabellek artırmak veya azaltmak için bkz: [FreeExtra](#freeextra) ve [Preallocate](#preallocate).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CSimpleStringT::Truncate`.  
  
```cpp  
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
``` 
  
##  <a name="unlockbuffer"></a>CSimpleStringT::UnlockBuffer
 Arabelleğin kilidini açarak `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void UnlockBuffer() throw();
```  
### <a name="remarks"></a>Açıklamalar  
 Dize başvuru sayısı 1 olarak sıfırlamak için bu yöntemi çağırın.  
  
 `CSimpleStringT` Yıkıcı otomatik olarak çağırır `UnlockBuffer` yıkıcı çağrıldığında arabellek kilitlenmediğinden emin olmak için. Bu yöntem bir örnek için bkz: [LockBuffer](#lockbuffer).  
  
##  <a name="dtor"></a>CSimpleStringT:: ~ CSimpleStringT
Bozar bir `CSimpleStringT` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
~CSimpleStringT() throw();
```  
### <a name="remarks"></a>Açıklamalar  
 Yok etmek için bu yöntemi çağırabilmeniz `CSimpleStringT` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC sınıfları paylaşılan](../../atl-mfc-shared/atl-mfc-shared-classes.md)