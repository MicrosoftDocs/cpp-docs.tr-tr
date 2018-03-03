---
title: "CComBSTR sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComBSTR
- ATLBASE/ATL::CComBSTR
- ATLBASE/ATL::CComBSTR::CComBSTR
- ATLBASE/ATL::CComBSTR::Append
- ATLBASE/ATL::CComBSTR::AppendBSTR
- ATLBASE/ATL::CComBSTR::AppendBytes
- ATLBASE/ATL::CComBSTR::ArrayToBSTR
- ATLBASE/ATL::CComBSTR::AssignBSTR
- ATLBASE/ATL::CComBSTR::Attach
- ATLBASE/ATL::CComBSTR::BSTRToArray
- ATLBASE/ATL::CComBSTR::ByteLength
- ATLBASE/ATL::CComBSTR::Copy
- ATLBASE/ATL::CComBSTR::CopyTo
- ATLBASE/ATL::CComBSTR::Detach
- ATLBASE/ATL::CComBSTR::Empty
- ATLBASE/ATL::CComBSTR::Length
- ATLBASE/ATL::CComBSTR::LoadString
- ATLBASE/ATL::CComBSTR::ReadFromStream
- ATLBASE/ATL::CComBSTR::ToLower
- ATLBASE/ATL::CComBSTR::ToUpper
- ATLBASE/ATL::CComBSTR::WriteToStream
- ATLBASE/ATL::CComBSTR::m_str
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 604e3b9841ab628343a48e72612d2e50e85913f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccombstr-class"></a>CComBSTR sınıfı
Bu sınıf için sarmalayıcı, `BSTR`s.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComBSTR
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComBSTR::CComBSTR](#ccombstr)|Oluşturucu.|  
|[CComBSTR:: ~ CComBSTR](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComBSTR::Append](#append)|Bir dize ekler `m_str`.|  
|[CComBSTR::AppendBSTR](#appendbstr)|Ekler bir `BSTR` için `m_str`.|  
|[CComBSTR::AppendBytes](#appendbytes)|Belirtilen sayıda baytı için ekler `m_str`.|  
|[CComBSTR::ArrayToBSTR](#arraytobstr)|Oluşturur bir `BSTR` safearray içindeki her öğesinin ilk karakter ve ekleninceye `CComBSTR` nesnesi.|  
|[CComBSTR::AssignBSTR](#assignbstr)|Atayan bir `BSTR` için `m_str`.|  
|[CComBSTR::Attach](#attach)|Bağlayan bir `BSTR` için `CComBSTR` nesnesi.|  
|[CComBSTR::BSTRToArray](#bstrtoarray)|Dizideki her öğe bir karakter olduğu bir sıfır tabanlı bir tek boyutlu safearray oluşturur `CComBSTR` nesnesi.|  
|[CComBSTR::ByteLength](#bytelength)|Uzunluğunu döndürür `m_str` bayt.|  
|[CComBSTR::Copy](#copy)|Bir kopyasını döndürür `m_str`.|  
|[CComBSTR::CopyTo](#copyto)|Bir kopyasını döndürür `m_str` aracılığıyla bir **[Çıkış]** parametresi|  
|[CComBSTR::Detach](#detach)|Ayırır `m_str` gelen `CComBSTR` nesnesi.|  
|[CComBSTR::Empty](#empty)|Serbest bırakma `m_str`.|  
|[CComBSTR::Length](#length)|Uzunluğunu döndürür `m_str`.|  
|[CComBSTR::LoadString](#loadstring)|Bir dize kaynağı yükler.|  
|[CComBSTR::ReadFromStream](#readfromstream)|Yükleri bir `BSTR` bir akış nesnesi.|  
|[CComBSTR::ToLower](#tolower)|Dizeyi küçük harflere dönüştürür.|  
|[CComBSTR::ToUpper](#toupper)|Büyük harfe dönüştürür.|  
|[CComBSTR::WriteToStream](#writetostream)|Kaydeder `m_str` akış.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComBSTR::operator BSTR](#operator_bstr)|Atamalar bir `CComBSTR` nesnesine bir `BSTR`.|  
|[CComBSTR::operator!](#operator_not)|Döndürür `true` veya `false`bağlı olarak mı yoksa `m_str`olan `NULL`.|  
|[CComBSTR::operator! =](#operator_neq)|Karşılaştıran bir `CComBSTR` içeren bir dize.|  
|[CComBSTR::operator &](#operator_amp)|Adresini döndürür `m_str`.|  
|[CComBSTR::operator +=](#operator_add_eq)|Ekler bir `CComBSTR` nesnesine.|  
|[CComBSTR::operator <](#operator_lt)|Karşılaştıran bir `CComBSTR` içeren bir dize.|  
|[CComBSTR::operator =](#operator_eq)|Bir değeri atar `m_str`.|  
|[CComBSTR::operator ==](#operator_eq_eq)|Karşılaştıran bir `CComBSTR` içeren bir dize.|  
|[CComBSTR::operator >](#operator_gt)|Karşılaştıran bir `CComBSTR` içeren bir dize.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComBSTR::m_str](#m_str)|İçeren `BSTR` ile ilişkili `CComBSTR` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComBSTR` İçin sarmalayıcı sınıftır `BSTR`uzunluğu önekli dizelerdir s. Uzunluğu bir tamsayı veri dizesinde önceki bellek konumda olarak depolanır.  
  
 A [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) null-sonra son karakter sayılan ancak aynı zamanda null dizede katıştırılmış karakter içerebilir sonlandırılır. Dize uzunluğu değil ilk null karakter karakter sayısı tarafından belirlenir.  
  
> [!NOTE]
>  `CComBSTR` Sınıfı, bir ANSI veya Unicode dizeleri bağımsız değişken olarak alan üye sayısı (Oluşturucular, atama işleçleri ve Karşılaştırma işleçleri) sağlar. Geçici Unicode dizeleri genellikle dahili oluşturduğundan bu işlevlerin ANSI sürümleri Unicode dekiler az verimlidir. Verimlilik için mümkün olduğunda Unicode sürümleri kullanın.  
  
> [!NOTE]
>  Visual Studio .NET içinde uygulanan geliştirilmiş arama davranışı nedeniyle gibi kod `bstr = L"String2" + bstr;`, hangi önceki sürümlerde, derlenmiş yerine olarak gerçekleştirilen `bstr = CStringW(L"String2") + bstr`.  
  
 Kullanırken uyarılar listesi `CComBSTR`, bkz: [CComBSTR ile programlama](../../atl/programming-with-ccombstr-atl.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="append"></a>CComBSTR::Append  
 Ya da ekler `lpsz` veya `BSTR` üyesi `bstrSrc` için [m_str](#m_str).  
  
```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `bstrSrc`  
 [in] A `CComBSTR` eklenecek nesne.  
  
 *Ch*  
 [in] Eklenecek bir karakter.  
  
 `lpsz`  
 [in] Eklenecek sıfır sonlandırılan bir karakter dizesi. Bir UNICODE dizesi aracılığıyla geçirebilirsiniz **LPCOLESTR** aşırı ya da bir ANSI dize aracılığıyla `LPCSTR` sürümü.  
  
 `nLen`  
 [in] Karakter sayısı `lpsz` eklenecek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK`Başarı veya herhangi bir standart `HRESULT` hata değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir ANSI dizesi eklenmiş önce Unicode'a dönüştürülür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]  
  
##  <a name="appendbstr"></a>CComBSTR::AppendBSTR  
 Belirtilen ekler `BSTR` için [m_str](#m_str).  
  
```
HRESULT AppendBSTR(BSTR p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 [in] A `BSTR` eklenecek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK`Başarı veya herhangi bir standart `HRESULT` hata değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Normal bir joker karakter dizesi, bu yönteme geçmeyin. Derleyici Hatası catch ve çalışma zamanı hataları oluşur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]  
  
##  <a name="appendbytes"></a>CComBSTR::AppendBytes  
 Belirtilen sayıda baytı için ekler [m_str](#m_str) dönüştürme olmadan.  
  
```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpsz`  
 [in] Eklenecek bir bayt dizisi için bir işaretçi.  
  
 `p`  
 [in] Eklenecek bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK`Başarı veya herhangi bir standart `HRESULT` hata değeri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]  
  
##  <a name="arraytobstr"></a>CComBSTR::ArrayToBSTR  
 Varolan bir dizeyi içinde tutulan boşaltır `CComBSTR` nesne sonra oluşturur bir `BSTR` safearray içindeki her öğesinin ilk karakter ve ona ekler `CComBSTR` nesne.  
  
```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pSrc`  
 [in] Dizesi oluşturmak için kullanılan öğeleri içeren safearray.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK`Başarı veya herhangi bir standart `HRESULT` hata değeri.  
  
##  <a name="assignbstr"></a>CComBSTR::AssignBSTR  
 Atayan bir `BSTR` için [m_str](#m_str).  
  
```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `bstrSrc`  
 [in] A `BSTR` geçerli atamak için `CComBSTR` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK`Başarı veya herhangi bir standart `HRESULT` hata değeri.  
  
##  <a name="attach"></a>CComBSTR::Attach  
 Bağlayan bir `BSTR` için `CComBSTR` ayarlayarak nesne [m_str](#m_str) üyesine *src*.  
  
```
void Attach(BSTR src) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *src*  
 [in] `BSTR` Nesnesine eklenecek.  
  
### <a name="remarks"></a>Açıklamalar  
 Normal bir joker karakter dizesi, bu yönteme geçmeyin. Derleyici Hatası catch ve çalışma zamanı hataları oluşur.  
  
> [!NOTE]
>  Bu yöntem, onay `m_str` olan olmayan **NULL**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="bstrtoarray"></a>CComBSTR::BSTRToArray  
 Dizideki her öğe bir karakter olduğu bir sıfır tabanlı bir tek boyutlu safearray oluşturur `CComBSTR` nesnesi.  
  
```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ppArray`  
 [out] İşlevinin sonuçlarını tutmak için kullanılan safearray yönelik işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK`Başarı veya herhangi bir standart `HRESULT` hata değeri.  
  
##  <a name="bytelength"></a>CComBSTR::ByteLength  
 Bayt sayısını döndürür `m_str`, sonlandırma null karakteri hariç.  
  
```
unsigned int ByteLength() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uzunluğu [m_str](#m_str) bayt üye.  
  
### <a name="remarks"></a>Açıklamalar  
 0 döndürür `m_str` olan **NULL**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]  
  
##  <a name="ccombstr"></a>CComBSTR::CComBSTR  
 Oluşturucu. Varsayılan Oluşturucu kümeleri [m_str](#m_str) üyesine **NULL**.  
  
```
CComBSTR() throw();
CComBSTR(const CComBSTR& src);  
CComBSTR(REFGUID  guid);  
CComBSTR(int nSize);  
CComBSTR(int nSize, LPCOLESTR sz);  
CComBSTR(int nSize, LPCSTR sz);  
CComBSTR(LPCOLESTR pSrc);  
CComBSTR(LPCSTR pSrc);  
CComBSTR(CComBSTR&& src) throw(); // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parametreler  
 `nSize`  
 [in] Kopyalanacak karakter sayısını `sz` veya karakter cinsinden başlangıç boyutu `CComBSTR`.  
  
 `sz`  
 [in] Kopyalamak için bir dize. Unicode sürümünü belirten bir **LPCOLESTR**; ANSI sürümünü belirten bir `LPCSTR`.  
  
 `pSrc`  
 [in] Kopyalamak için bir dize. Unicode sürümünü belirten bir **LPCOLESTR**; ANSI sürümünü belirten bir `LPCSTR`.  
  
 *src*  
 [in] A `CComBSTR` nesnesi.  
  
 `guid`  
 [in] Bir başvuru bir **GUID** yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kopya Oluşturucu kümeleri `m_str` bir kopyasına `BSTR` üyesi *src*. **REFGUID** Oluşturucusu dönüştürür **GUID** kullanarak bir dize için **StringFromGUID2** ve sonucu depolar.  
  
 Diğer oluşturucular kümesi `m_str` belirtilen dizenin kopyalanacak. Bir değer geçirmek, `nSize`, sonra yalnızca `nSize` karakterleri kopyalanacak, sonlandırma bir null karakter.  
  
 `CComBSTR`destekler semantiği taşıyın. Taşıma Oluşturucusu kullanabilirsiniz (rvalue başvuru alan oluşturucu ( `&&`) aynı temel alınan veri geçirdiğiniz nesne kopyalama yükü olmadan bir bağımsız değişken olarak eski nesnesi olarak kullanan yeni bir nesne oluşturmak için.  
  
 Yok Edicisi gösterdiği dize boşaltır `m_str`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]  
  
##  <a name="dtor"></a>CComBSTR:: ~ CComBSTR  
 Yok Edicisi.  
  
```
~CComBSTR();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi gösterdiği dize boşaltır `m_str`.  
  
##  <a name="copy"></a>CComBSTR::Copy  
 Ayırır ve bir kopyasını döndürür `m_str`.  
  
```
BSTR Copy() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kopyasını [m_str](#m_str) üyesi. Varsa `m_str` olan **NULL**, döndürür **NULL**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]  
  
##  <a name="copyto"></a>CComBSTR::CopyTo  
 Ayırır ve bir kopyasını döndürür [m_str](#m_str) parametresi aracılığıyla.  
  
```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pbstr*  
 [out] Adresini bir `BSTR` , bu yöntem tarafından ayrılan dize döndürür.  
  
 `pvarDest`  
 [out] Adresini bir **değişken** , bu yöntem tarafından ayrılan dize döndürür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` başarı veya başarısızlık kopyanın belirten değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağrıldıktan sonra **değişken** gösterdiği `pvarDest` türünün `VT_BSTR`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]  
  
##  <a name="detach"></a>CComBSTR::Detach  
 Ayırır [m_str](#m_str) gelen `CComBSTR` nesne ve ayarlar `m_str` için **NULL**.  
  
```
BSTR Detach() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `BSTR` İle ilişkili `CComBSTR` nesnesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]  
  
##  <a name="empty"></a>CComBSTR::Empty  
 Serbest bırakma [m_str](#m_str) üyesi.  
  
```
void Empty() throw();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]  
  
##  <a name="length"></a>CComBSTR::Length  
 Karakter sayısını verir `m_str`, sonlandırma null karakteri hariç.  
  
```
unsigned int Length() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uzunluğu [m_str](#m_str) üyesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]  
  
##  <a name="loadstring"></a>CComBSTR::LoadString  
 Tarafından belirtilen bir dize kaynağı yükler `nID` ve bu nesnesinde depolar.  
  
```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 Bkz: [LoadString](http://msdn.microsoft.com/library/windows/desktop/ms647486) Windows SDK.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** dize ise, başarıyla yüklenen; Aksi takdirde, döndürür **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk işlev, tarafından tanımlanan modülden kaynak yükler `hInst` parametresi. İkinci işlev ile ilişkili kaynak modülden kaynak yükler [CComModule](../../atl/reference/ccommodule-class.md)-bu projede kullanılan nesnesi türetilmiş.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]  
  
##  <a name="m_str"></a>CComBSTR::m_str  
 İçeren `BSTR` ile ilişkili `CComBSTR` nesnesi.  
  
```
BSTR m_str;
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]  
  
##  <a name="operator_bstr"></a>CComBSTR::operator BSTR  
 Atamalar bir `CComBSTR` nesnesine bir `BSTR`.  
  
```  
operator BSTR() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçirmenizi sağlar `CComBSTR` olan işlevler nesnelere **[in] BSTR** parametreleri.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CComBSTR::m_str](#m_str).  
  
##  <a name="operator_not"></a>CComBSTR::operator!  
 Denetler olup olmadığını `BSTR` boş bir dizedir.  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** varsa [m_str](#m_str) üye **NULL**; Aksi halde, **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç yalnızca boş bir dize için bir NULL değer olup olmadığını denetler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="operator_neq"></a>CComBSTR::operator! =  
 Mantıksal tersini döndürür [işleç ==](#operator_eq_eq).  
  
```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `bstrSrc`  
 [in] A `CComBSTR` nesnesi.  
  
 `pszSrc`  
 [in] Sıfır ile sonlandırılan bir dize.  
  
 `nNull`  
 [in] Olmalıdır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** karşılaştırılan öğesi eşit değilse `CComBSTR` nesne; Aksi halde döndürür **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 `CComBSTR`s kullanıcının varsayılan yerel ayar bağlamında textually karşılaştırılır. Son karşılaştırma işleci yalnızca kapsanan dize karşı karşılaştırır **NULL**.  
  
##  <a name="operator_amp"></a>CComBSTR::operator&amp;  
 Adresini döndürür `BSTR` depolanan [m_str](#m_str) üyesi.  
  
```
BSTR* operator&() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CComBstr operator &`özel bir onaylama bellek sızıntıları tanımlamaya yardımcı olmak için ilişkilendirilir. Programın ne zaman assert `m_str` üye başlatılır. Burada Programcı kullanan durumları belirlemek için bu onay oluşturulduğu `& operator` için yeni bir değer atamak için `m_str` ilk ayrılması boşaltma olmadan üye `m_str`. Varsa `m_str` NULL eşittir, o m_str değildi ayrılan henüz program varsayar. Bu durumda, program assert değil.  
  
 Bu onay varsayılan olarak etkin değildir. Tanımlamak `ATL_CCOMBSTR_ADDRESS_OF_ASSERT` bu onaylama etkinleştirmek için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]  
  
##  <a name="operator_add_eq"></a>CComBSTR::operator +=  
 Bir dize ekler `CComBSTR` nesnesi.  
  
```
CComBSTR& operator+= (const CComBSTR& bstrSrc);  
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `bstrSrc`  
 [in] A `CComBSTR` eklenecek nesne.  
  
 `pszSrc`  
 [in] Eklenecek sıfır sonlandırılan dize.  
  
### <a name="remarks"></a>Açıklamalar  
 `CComBSTR`s kullanıcının varsayılan yerel ayar bağlamında textually karşılaştırılır. **LPCOLESTR** karşılaştırma yapılır kullanarak `memcmp` her dizesinde ham verileri. `LPCSTR` Karşılaştırma gerçekleştirilir aynı şekilde Unicode geçici bir kopyası sonra `pszSrc` oluşturuldu. Son karşılaştırma işleci yalnızca kapsanan dize karşı karşılaştırır **NULL**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]  
  
##  <a name="operator_lt"></a>CComBSTR::operator&lt;  
 Karşılaştıran bir `CComBSTR` içeren bir dize.  
  
```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** karşılaştırılan madde ise küçük `CComBSTR` nesne; Aksi halde döndürür **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Karşılaştırma kullanıcının varsayılan yerel ayar kullanılarak gerçekleştirilir.  
  
##  <a name="operator_eq"></a>CComBSTR::operator =  
 Ayarlar [m_str](#m_str) bir kopyasını üyesine `pSrc` veya bir kopyasını `BSTR` üyesi *src*. Taşıma atama işleci taşır `src` kopyalamak olmadan.   
  
```
CComBSTR& operator= (const CComBSTR& src);  
CComBSTR& operator= (LPCOLESTR pSrc);  
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```  
  
### <a name="remarks"></a>Açıklamalar  
 `pSrc` Parametresi belirtir ya da bir **LPCOLESTR** Unicode sürümleri veya `LPCSTR` ANSI sürümleri için.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CComBSTR::Copy](#copy).  
  
##  <a name="operator_eq_eq"></a>CComBSTR::operator ==  
 Karşılaştıran bir `CComBSTR` içeren bir dize. `CComBSTR`s kullanıcının varsayılan yerel ayar bağlamında textually karşılaştırılır.  
  
```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `bstrSrc`  
 [in] A `CComBSTR` nesnesi.  
  
 `pszSrc`  
 [in] Sıfır ile sonlandırılan bir dize.  
  
 `nNull`  
 [in] Olmalıdır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** karşılaştırılan madde eşit ise `CComBSTR` nesne; Aksi halde döndürür **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Son karşılaştırma işleci yalnızca kapsanan dize karşı karşılaştırır **NULL**.  
  
##  <a name="operator_gt"></a>CComBSTR::operator&gt;  
 Karşılaştıran bir `CComBSTR` içeren bir dize.  
  
```
bool operator>(const CComBSTR& bstrSrc) const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** karşılaştırılan öğesi büyükse `CComBSTR` nesne; Aksi halde döndürür **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Karşılaştırma kullanıcının varsayılan yerel ayar kullanılarak gerçekleştirilir.  
  
##  <a name="readfromstream"></a>CComBSTR::ReadFromStream  
 Ayarlar [m_str](#m_str) üyesine `BSTR` belirtilen akışında yer alan.  
  
```
HRESULT ReadFromStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pStream`  
 [in] Bir işaretçi [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) verileri içeren akışı arabirimde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 **ReadToStream** için yapılan bir çağrı tarafından yazılan veri biçimi ile uyumlu olacak şekilde geçerli konumundaki akış içeriğini gerektirir [WriteToStream](#writetostream).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]  
  
##  <a name="tolower"></a>CComBSTR::ToLower  
 Kapsanan dize küçük harflere dönüştürür.  
  
```
HRESULT ToLower() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: **CharLowerBuff** dönüştürme nasıl gerçekleştirildiğini hakkında daha fazla bilgi.  
  
##  <a name="toupper"></a>CComBSTR::ToUpper  
 Kapsanan büyük harfe dönüştürür.  
  
```
HRESULT ToUpper() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: **CharUpperBuff** dönüştürme nasıl gerçekleştirildiğini hakkında daha fazla bilgi.  
  
##  <a name="writetostream"></a>CComBSTR::WriteToStream  
 Kaydeder [m_str](#m_str) üye akış.  
  
```
HRESULT WriteToStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pStream`  
 [in] Bir işaretçi [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) bir akış üzerinde arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 BSTR kullanarak akış içeriğinin yeniden [ReadFromStream](#readfromstream) işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md)
