---
title: CStringT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringT
- ATLSTR/ATL::CStringT
- ATLSTR/ATL::CStringT::CStringT
- ATLSTR/ATL::CStringT::AllocSysString
- ATLSTR/ATL::CStringT::AnsiToOem
- ATLSTR/ATL::CStringT::AppendFormat
- ATLSTR/ATL::CStringT::Collate
- ATLSTR/ATL::CStringT::CollateNoCase
- ATLSTR/ATL::CStringT::Compare
- ATLSTR/ATL::CStringT::CompareNoCase
- ATLSTR/ATL::CStringT::Delete
- ATLSTR/ATL::CStringT::Find
- ATLSTR/ATL::CStringT::FindOneOf
- ATLSTR/ATL::CStringT::Format
- ATLSTR/ATL::CStringT::FormatMessage
- ATLSTR/ATL::CStringT::FormatMessageV
- ATLSTR/ATL::CStringT::FormatV
- ATLSTR/ATL::CStringT::GetEnvironmentVariable
- ATLSTR/ATL::CStringT::Insert
- ATLSTR/ATL::CStringT::Left
- ATLSTR/ATL::CStringT::LoadString
- ATLSTR/ATL::CStringT::MakeLower
- ATLSTR/ATL::CStringT::MakeReverse
- ATLSTR/ATL::CStringT::MakeUpper
- ATLSTR/ATL::CStringT::Mid
- ATLSTR/ATL::CStringT::OemToAnsi
- ATLSTR/ATL::CStringT::Remove
- ATLSTR/ATL::CStringT::Replace
- ATLSTR/ATL::CStringT::ReverseFind
- ATLSTR/ATL::CStringT::Right
- ATLSTR/ATL::CStringT::SetSysString
- ATLSTR/ATL::CStringT::SpanExcluding
- ATLSTR/ATL::CStringT::SpanIncluding
- ATLSTR/ATL::CStringT::Tokenize
- ATLSTR/ATL::CStringT::Trim
- ATLSTR/ATL::CStringT::TrimLeft
- ATLSTR/ATL::CStringT::TrimRight
- CSTRINGT/CStringT
- CSTRINGT/CStringT::CStringT
- CSTRINGT/CStringT::AllocSysString
- CSTRINGT/CStringT::AnsiToOem
- CSTRINGT/CStringT::AppendFormat
- CSTRINGT/CStringT::Collate
- CSTRINGT/CStringT::CollateNoCase
- CSTRINGT/CStringT::Compare
- CSTRINGT/CStringT::CompareNoCase
- CSTRINGT/CStringT::Delete
- CSTRINGT/CStringT::Find
- CSTRINGT/CStringT::FindOneOf
- CSTRINGT/CStringT::Format
- CSTRINGT/CStringT::FormatMessage
- CSTRINGT/CStringT::FormatMessageV
- CSTRINGT/CStringT::FormatV
- CSTRINGT/CStringT::GetEnvironmentVariable
- CSTRINGT/CStringT::Insert
- CSTRINGT/CStringT::Left
- CSTRINGT/CStringT::LoadString
- CSTRINGT/CStringT::MakeLower
- CSTRINGT/CStringT::MakeReverse
- CSTRINGT/CStringT::MakeUpper
- CSTRINGT/CStringT::Mid
- CSTRINGT/CStringT::OemToAnsi
- CSTRINGT/CStringT::Remove
- CSTRINGT/CStringT::Replace
- CSTRINGT/CStringT::ReverseFind
- CSTRINGT/CStringT::Right
- CSTRINGT/CStringT::SetSysString
- CSTRINGT/CStringT::SpanExcluding
- CSTRINGT/CStringT::SpanIncluding
- CSTRINGT/CStringT::Tokenize
- CSTRINGT/CStringT::Trim
- CSTRINGT/CStringT::TrimLeft
- CSTRINGT/CStringT::TrimRight
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f8a66f87b3c4a2c6712a1db93f97361a25b6955
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="cstringt-class"></a>CStringT sınıfı
Bu sınıfın temsil ettiği bir `CStringT` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
 
template<typename BaseType, class StringTraits>  
class CStringT :   
public CSimpleStringT<BaseType,
                      _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                      ::c_bIsMFCDLLTraits>  
 
```  
  
#### <a name="parameters"></a>Parametreler  
 `BaseType`  
 String sınıfı karakter türü. Aşağıdakilerden biri olabilir:  
  
- `char` (için ANSI karakter dizelerini).  
  
- `wchar_t` (için Unicode karakter dizeleri).  
  
- **TCHAR** (için ANSI ve Unicode karakter dizelerini).  
  
 `StringTraits`  
 String sınıfı C çalışma zamanı (CRT) kitaplık desteği ve dize kaynaklarını bulunduğu gerekip gerekmediğini belirler. Aşağıdakilerden biri olabilir:  
  
- **StrTraitATL < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Sınıfı tarafından belirtilen modülde kaynak dizeleri arar ve CRT desteği gerektirir `m_hInstResource` (uygulamanın modülü sınıf üyesi).  
  
- **StrTraitATL < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Sınıfı tarafından belirtilen modülde kaynak dizeleri arar ve CRT desteği gerektirmez `m_hInstResource` (uygulamanın modülü sınıf üyesi).  
  
- **StrTraitMFC < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Sınıf CRT desteği ve standart MFC arama algoritması kullanarak kaynak dizeleri arar gerektirir.  
  
- **StrTraitMFC < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Sınıf CRT desteği ve standart MFC arama algoritması kullanarak kaynak dizeleri arar gerektirmez.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStringT::CStringT](#cstringt)|Oluşturan bir `CStringT` çeşitli şekillerde nesnesi.|  
|[CStringT:: ~ CStringT](#_dtorcstringt)|Bozar bir `CStringT` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStringT::AllocSysString](#allocsysstring)|Ayıran bir `BSTR` gelen `CStringT` veri.|  
|[CStringT::AnsiToOem](#ansitooem)|Bir yerinde dönüştürme için OEM karakter kümesi ANSI karakter yapar.|  
|[CStringT::AppendFormat](#appendformat)|Varolan bir biçimlendirilmiş veriler ekler `CStringT` nesnesi.|  
|[CStringT::Collate](#collate)|İki dizeyi (servis talebi hassas, kullandığı yerel ayarlara özgü bilgiler) karşılaştırır.|  
|[CStringT::CollateNoCase](#collatenocase)|İki dizeyi (servis talebi duyarsız, kullandığı yerel ayarlara özgü bilgiler) karşılaştırır.|  
|[CStringT::Compare](#compare)|İki dizeyi (büyük küçük harf duyarlı) karşılaştırır.|  
|[CStringT::CompareNoCase](#comparenocase)|İki dizeyi (büyük küçük harfe duyarlı) karşılaştırır.|  
|[CStringT::Delete](#delete)|Bir karakterin veya karakter bir dizeden siler.|  
|[CStringT::Find](#find)|Bir karakter veya daha büyük bir dize içinde alt dizeyi bulur.|  
|[CStringT::FindOneOf](#findoneof)|İlk eşleşen karakter kümesinden bulur.|  
|[CStringT::Format](#format)|Dize olarak biçimlendirir `sprintf` yapar.|  
|[CStringT::FormatMessage](#formatmessage)|Bir ileti dizesi biçimlendirir.|  
|[CStringT::FormatMessageV](#formatmessagev)|Değişken bağımsız değişken listesini kullanarak bir ileti dizesi biçimlendirir.|  
|[CStringT::FormatV](#formatv)|Değişken bağımsız değişken listesini kullanarak dize biçimlendirir.|  
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|Dize belirtilen ortam değişkeninin değerine ayarlar.|  
|[CStringT::Insert](#insert)|Tek bir karakter veya alt dize dize içinde verilen dizindeki ekler.|  
|[CStringT::Left](#left)|Bir dize sol bölümü ayıklar.|  
|[CStringT::LoadString](#loadstring)|Var olan yükler `CStringT` Windows kaynak nesnesi.|  
|[CStringT::MakeLower](#makelower)|Küçük harf karakterler için bu dizeyi içindeki tüm karakterleri dönüştürür.|  
|[CStringT::MakeReverse](#makereverse)|Dize tersine çevirir.|  
|[CStringT::MakeUpper](#makeupper)|Bu dize karakterleri büyük harfe içindeki tüm karakterleri dönüştürür.|  
|[CStringT::Mid](#mid)|Bir dize Orta parçası ayıklar.|  
|[CStringT::OemToAnsi](#oemtoansi)|OEM karakter ANSI karakter kümesini kümesindeki bir yerinde dönüştürme yapar.|  
|[CStringT::Remove](#remove)|Bir dizeden karakterleri kaldırır gösterilir.|  
|[CStringT::Replace](#replace)|Değiştirir karakterleri diğer karakterlerle gösterilir.|  
|[CStringT::ReverseFind](#reversefind)|Büyük bir dizi içinde bir karakteri bulur; sonundan başlatır.|  
|[CStringT::Right](#right)|Bir dize sağ bölümünü ayıklar.|  
|[CStringT::SetSysString](#setsysstring)|Var olan ayarlar `BSTR` nesne verilerle bir `CStringT` nesnesi.|  
|[CStringT::SpanExcluding](#spanexcluding)|Tarafından tanımlanan karakter kümesi olmayan ilk karakter ile başlayarak, dizeden karakterleri ayıklar `pszCharSet`.|  
|[CStringT::SpanIncluding](#spanincluding)|Yalnızca bir karakter içeren bir alt dizesi ayıklar.|  
|[CStringT::Tokenize](#tokenize)|Ayıklar belirteçleri hedef dizesinde belirtilen.|  
|[CStringT::Trim](#trim)|Tüm öndeki ve sondaki boşluk karakterlerinden dize kırpar.|  
|[CStringT::TrimLeft](#trimleft)|Boşluk karakterleri dizeden öndeki boşlukları.|  
|[CStringT::TrimRight](#trimright)|Boşluk karakterleri dizesinden sondaki boşlukları.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](#operator_eq)|Yeni bir değer atayan bir `CStringT` nesnesi.|  
|[CStringT::operator +](#operator_add)|İki dizeyi veya bir karakter ve bir dizeyi art arda ekler.|  
|[CStringT::operator +=](#operator_add_eq)|Varolan bir dizeyi sonuna yeni bir dize art arda ekler.|  
|[CStringT::operator ==](#operator_eq_eq)|İki dizeyi mantıksal olarak eşit olup olmadığını belirler.|  
|[CStringT::operator! =](#operator_neq)|İki dizeyi eşit değilse mantıksal olarak belirler.|  
|[CStringT::operator &lt;](#operator_lt)|İşlecinin sol tarafındaki dize değerinden çok olup olmadığını belirler sağ tarafında dize.|  
|[CStringT::operator &gt;](#operator_gt)|Dize işlecinin sol tarafındaki sağ tarafında dizeye büyük olup olmadığını belirler.|  
|[CStringT::operator &lt;=](#operator_lt_eq)|İşlecinin sol tarafındaki dize değerinden küçük veya buna eşit sağ tarafında dizeye olup olmadığını belirler.|  
|[CStringT::operator &gt;=](#operator_gt_eq)|Dize işlecinin sol tarafındaki sağ tarafında dizeye eşit veya daha büyük olup olmadığını belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CStringT` öğesinden devralınan [CSimpleStringT sınıfı](../../atl-mfc-shared/reference/csimplestringt-class.md). Sıralama ve arama, karakter işleme gibi gelişmiş özellikler tarafından uygulanır `CStringT`.  
  
> [!NOTE]
> `CStringT` özel durumları atma özellikli nesneleridir. Bu meydana olduğunda bir `CStringT` nesne herhangi bir nedenle bellek yetersiz çalıştırır.  
  
 A `CStringT` nesnesi değişken uzunlukta bir karakter dizisi içerir. `CStringT` İşlevler ve Basic için benzer bir sözdizimi kullanılarak işleçleri sağlar. Birleştirme ve Karşılaştırma işleçleri Basitleştirilmiş bellek yönetimi ile birlikte olmak `CStringT` nesneleri sıradan karakter dizileri kullanmak daha kolay.  
  
> [!NOTE]
>  Oluşturmak mümkün olmakla `CStringT` katıştırılmış boş karakterler içeren örnekleri, karşı öneririz. Yöntemleri ve işleçleri çağrılması `CStringT` katıştırılmış boş karakterler içeren nesneleri, istenmeyen sonuçları oluşturabilirsiniz.  
  
 Farklı birleşimlerini kullanarak `BaseType` ve `StringTraits` parametreleri `CStringT` misiniz aşağıdaki türlerde gelen edilmiş önceden tanımlanmış ATL kitaplıkları tarafından nesneleri.  
  
 ATL uygulamada kullanıyorsanız:  
  
 `CString`, `CStringA`, ve `CStringW` (MFC90. MFC DLL'den dışarı DLL), hiçbir zaman kullanıcıdan DLL'leri. Bunu önlemek için yapılır `CStringT` gelen birden çok kez tanımlanmış.  
  
> [!NOTE]
>  Kodunuzu açıklanan bağlayıcı hataları için geçici çözüm içeriyorsa [Linking Errors When You Import CString-Derived sınıfları "(Q309801)](https://support.microsoft.com/help/309801/you-may-receive-an-lnk2019-error-message-when-you-build-a-visual-c-200), bu kodu kaldırmanız gerekir. Artık gerekli olmadığında.  
  
 MFC tabanlı uygulamalar içinde aşağıdaki dize türleri kullanılabilir:  
  
|CStringT türü|Bildirim|  
|-------------------|-----------------|  
|`CStringA`|ANSI karakter dizesi CRT desteğiyle yazın.|  
|`CStringW`|Bir Unicode karakter dizesi CRT desteği olan yazın.|  
|`CString`|CRT desteğiyle ANSI ve Unicode karakter türleri.|  
  
 Türleri kullanılabilir aşağıdaki dizeyi projeleri **ATL_CSTRING_NO_CRT** tanımlanır:  
  
|CStringT türü|Bildirim|  
|-------------------|-----------------|  
|**CAtlStringA**|ANSI karakter dizesi CRT desteği olmadan yazın.|  
|**CAtlStringW**|Bir Unicode karakter dizesi CRT desteği olmadan yazın.|  
|**CAtlString**|CRT desteği olmadan ANSI ve Unicode karakter türleri.|  
  
 Türleri kullanılabilir aşağıdaki dizeyi projeleri **ATL_CSTRING_NO_CRT** tanımlı değil:  
  
|CStringT türü|Bildirim|  
|-------------------|-----------------|  
|**CAtlStringA**|ANSI karakter dizesi CRT desteğiyle yazın.|  
|**CAtlStringW**|Bir Unicode karakter dizesi CRT desteği olan yazın.|  
|**CAtlString**|CRT desteğiyle ANSI ve Unicode karakter türleri.|  
  
 `CString` nesneleri aynı zamanda aşağıdaki özelliklere sahiptir:  
  
- `CStringT` nesneleri birleştirme işlemleri sonucunda büyüyebilir.  
  
- `CStringT` "semantiği değeri." nesneleri izleyin Düşünün bir `CStringT` nesne gerçek bir dize olarak, bir dize için bir işaretçi olarak değil.  
  
-   Serbestçe değiştirebilirsiniz `CStringT` için nesneleri `PCXSTR` işlev bağımsız değişkenleri.  
  
-   Dize arabellekleri için özel bellek yönetimi. Daha fazla bilgi için bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="cstringt-predefined-types"></a>CStringT türleri önceden tanımlanmış  
 Çünkü `CStringT` şablon bağımsız değişken karakter türünü tanımlamak için kullanır (ya da [wchar_t](../../c-runtime-library/standard-types.md) veya [char](../../c-runtime-library/standard-types.md)) desteklenen yöntem parametre türleri bazen karmaşık olabilir. Bu sorunu basitleştirmek için bir dizi önceden tanımlanmış türleri tanımlı ve genelinde kullanılan `CStringT` sınıfı. Aşağıdaki tabloda, çeşitli türleri listelenmiştir:  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`XCHAR`|Tek bir karakter (ya da `wchar_t` veya `char`) ile aynı karakter türü `CStringT` nesnesi.|  
|**YCHAR**|Tek bir karakter (ya da `wchar_t` veya `char`) ters karakter türü ile `CStringT` nesnesi.|  
|`PXSTR`|Bir işaretçi bir karakter dizesine (ya da `wchar_t` veya `char`) ile aynı karakter türü `CStringT` nesnesi.|  
|**PYSTR**|Bir işaretçi bir karakter dizesine (ya da `wchar_t` veya `char`) ters karakter türü ile `CStringT` nesnesi.|  
|`PCXSTR`|Bir işaretçi bir **const** karakter dizesi (ya da `wchar_t` veya `char`) ile aynı karakter türü `CStringT` nesnesi.|  
|**PCYSTR**|Bir işaretçi bir **const** karakter dizesi (ya da `wchar_t` veya `char`) ters karakter türü ile `CStringT` nesnesi.|  
  
> [!NOTE]
>  Daha önce belgelenmemiş yöntemlerini kullanan kodu `CString` (gibi **AssignCopy**) aşağıdaki belgelenen yöntemlerini kullanan kodu ile değiştirilmelidir `CStringT` (gibi `GetBuffer` veya `ReleaseBuffer`). Bu yöntemler kaynağından devralındı `CSimpleStringT`.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## <a name="requirements"></a>Gereksinimler  
  
|Üstbilgi|Kullanım için|  
|------------|-------------|  
|cstringt.h|Yalnızca MFC string nesneleri|  
|atlstr.h|MFC olmayan dize nesneleri|  
  
##  <a name="allocsysstring"></a>  CStringT::AllocSysString  
 Bir otomasyon uyumlu dize türünde ayırır `BSTR` ve içeriğini kopyalar `CStringT` sonlandırma null karakteri de dahil olmak üzere, nesnesine.  
  
```  
BSTR AllocSysString() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni ayrılmış dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 MFC programlarda bir [CMemoryException sınıfı](../../mfc/reference/cmemoryexception-class.md) yeterli bellek varsa oluşturulur. ATL programlarda bir [CAtlException](../../atl/reference/catlexception-class.md) atılır. Bu işlev, normalde Otomasyon için dizeleri döndürmek için kullanılır.  
  

 Genellikle, bu dize bir COM işleve aktarılırsa bir [] parametresi, ardından bu gerektirir çağıran dizesi boş. Bu kullanılarak yapılabilir [SysFreeString](https://msdn.microsoft.com/library/windows/desktop/ms221481.aspx), Windows SDK'ın açıklandığı gibi. Daha fazla bilgi için bkz: [Allocating ve serbest bırakma bellek BSTR için](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).  
  
 Windows OLE ayırma işlevleri hakkında daha fazla bilgi için bkz: [SysAllocString](https://msdn.microsoft.com/library/windows/desktop/ms221458.aspx) Windows SDK'sındaki.  

  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CStringT::AllocSysString`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]  
  
##  <a name="ansitooem"></a>  CStringT::AnsiToOem  
 Bu tüm karakterleri dönüştürür `CStringT` OEM karakter kümesine ANSI karakter nesnesinden.  
  
```  
void AnsiToOem();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevi kullanılabilir değil, `_UNICODE` tanımlanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]  
  
##  <a name="appendformat"></a>  CStringT::AppendFormat  
 Varolan bir biçimlendirilmiş veriler ekler `CStringT` nesnesi.  
  
```  
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszFormat`  
 Bir Denetim Biçimlendir dize.  
  
 `nFormatID`  
 Denetim Biçimlendir dizesini içeren dize kaynak tanımlayıcısı.  
  
 `argument`  
 İsteğe bağlı bağımsız değişkenler.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev biçimlendirir ve bir dizi karakter ve değerler ekler `CStringT`. Her isteğe bağlı bir değişken (varsa) dönüştürülür ve karşılık gelen biçimi belirtiminde göre eklenen `pszFormat` veya tarafından tanımlanan dize kaynaktan `nFormatID`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]  
  
##  <a name="collate"></a>  CStringT::Collate  
 Genel metin işlevi kullanarak iki dizeleri karşılaştırır `_tcscoll`.  
  
```  
int Collate(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `psz`  
 Karşılaştırma için kullanılan diğer dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır dizeleri özdeş ise, < 0 bu `CStringT` nesne değerinden `psz`, veya > 0 bu `CStringT` nesnesidir büyük `psz`.  
  
### <a name="remarks"></a>Açıklamalar  
 Genel metin işlevi `_tcscoll`, TCHAR tanımlanmış. H eşlemeleri ya da `strcoll`, `wcscoll`, veya `_mbscoll`derleme zamanında tanımlanan karakter kümesi bağlı olarak. Her işlev kod sayfasına göre dizeleri büyük küçük harfe duyarlı karşılaştırması şu anda kullanımda gerçekleştirir. Daha fazla bilgi için bkz: [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
##  <a name="collatenocase"></a>  CStringT::CollateNoCase  
 Genel metin işlevi kullanarak iki dizeleri karşılaştırır `_tcscoll`.  
  
```  
int CollateNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `psz`  
 Karşılaştırma için kullanılan diğer dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizeleri varsa sıfır özdeş (göz ardı harf), < 0 bu `CStringT` nesne değerinden `psz` (durumu yok), ya da > 0 bu ise `CStringT` nesnesidir büyük `psz` (servis talebi yoksayar).  
  
### <a name="remarks"></a>Açıklamalar  
 Genel metin işlevi `_tcscoll`, TCHAR tanımlanmış. H eşlemeleri ya da `stricoll`, `wcsicoll`, veya `_mbsicoll`derleme zamanında tanımlanan karakter kümesi bağlı olarak. Her işlev şu anda kullanımda kod sayfasına göre dizeleri büyük küçük harf duyarsız bir karşılaştırma gerçekleştirir. Daha fazla bilgi için bkz: [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]  
  
##  <a name="compare"></a>  CStringT::Compare  
 İki dizeyi (büyük küçük harf duyarlı) karşılaştırır.  
  
```  
int Compare(PCXSTR psz) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `psz`  
 Karşılaştırma için kullanılan diğer dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır dizeleri özdeş ise, < 0 bu `CStringT` nesne değerinden `psz`, veya > 0 bu `CStringT` nesnesidir büyük `psz`.  
  
### <a name="remarks"></a>Açıklamalar  
 Genel metin işlevi `_tcscmp`, TCHAR tanımlanmış. H eşlemeleri ya da `strcmp`, `wcscmp`, veya `_mbscmp`derleme zamanında tanımlanan karakter kümesi bağlı olarak. Her işlev dizeleri büyük küçük harfe duyarlı karşılaştırma gerçekleştirir ve yerel ayar tarafından etkilenmez. Daha fazla bilgi için bkz: [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).  
  
 Dize katıştırılmış null değerler içeriyorsa, ilk katıştırılmış null karakteri kesilecek karşılaştırma amaçları için dize kabul edilir.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CStringT::Compare`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]  
  
##  <a name="comparenocase"></a>  CStringT::CompareNoCase  
 İki dizeyi (büyük küçük harfe duyarlı) karşılaştırır.  
  
```  
int CompareNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `psz`  
 Karşılaştırma için kullanılan diğer dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizeleri özdeş ise sıfır (durumu yok), < 0 bu ise `CStringT` nesne değerinden `psz` (durumu yok), veya > 0 bu ise `CStringT` nesnesidir büyük `psz` (servis talebi yoksayar).  
  
### <a name="remarks"></a>Açıklamalar  
 Genel metin işlevi `_tcsicmp`, TCHAR tanımlanmış. H eşlemeleri ya da `_stricmp`, `_wcsicmp` veya `_mbsicmp`derleme zamanında tanımlanan karakter kümesi bağlı olarak. Her işlev dizeleri büyük küçük harf duyarsız bir karşılaştırma gerçekleştirir. Karşılaştırma bağlıdır `LC_CTYPE` yerel yönünü ama `LC_COLLATE`. Daha fazla bilgi için bkz: [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]  
  
##  <a name="cstringt"></a>  CStringT::CStringT  
 Oluşturan bir `CStringT` nesnesi.  
  
```  
CStringT() throw() :   
    CThisSimpleString(StringTraits::GetDefaultManager());
 
explicit CStringT(IAtlStringMgr* pStringMgr) throw() :   
    CThisSimpleString( pStringMgr); 

CStringT(const VARIANT& varSrc);
 
CStringT(const VARIANT& varSrc, IAtlStringMgr* pStringMgr);
 
CStringT(const CStringT& strSrc) :   
    CThisSimpleString( strSrc);

 operator CSimpleStringT<
                    BaseType, 
                    !_CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                    :: c_bIsMFCDLLTraits> &()  
 
template <bool bMFCDLL>  
CStringT(const CSimpleStringT<BaseType, bMFCDLL>& strSrc) :   
    CThisSimpleString( strSrc);
 
template <class SystemString>  
CStringT(SystemString^ pString) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(const YCHAR* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(LPCSTR pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CStringT(LPCWSTR pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CSTRING_EXPLICIT CStringT(const unsigned char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
/*CSTRING_EXPLICIT*/ CStringT(char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(unsigned char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(wchar_t* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const unsigned char* pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CSTRING_EXPLICIT CStringT(char ch, int nLength = 1) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(wchar_t ch, int nLength = 1) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pch, int nLength) :   
    CThisSimpleString( pch, nLength, StringTraits::GetDefaultManager());
 
CStringT(const YCHAR* pch, int nLength) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pch, int nLength, AtlStringMgr* pStringMgr) :   
    CThisSimpleString( pch, nLength, pStringMgr);
 
CStringT(const YCHAR* pch, int nLength, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
```  
  
### <a name="parameters"></a>Parametreler  
 `pch`  
 Karakter uzunluğunda bir işaretçi `nLength`, null sonlandırılmamış.  
  
 `nLength`  
 Karakter sayısını `pch`.  
  
 `ch`  
 Tek bir karakter.  
  
 `pszSrc`  
 Bu kopyalanacak null ile sonlandırılmış bir dize `CStringT` nesnesi.  
  
 `pStringMgr`  
 Bellek Yöneticisi için bir işaretçi `CStringT` nesnesi. Daha fazla bilgi için `IAtlStringMgr` ve bellek yönetimi için `CStringT`, bkz: [CStringT ile bellek yönetimi](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 `strSrc`  
 Var olan `CStringT` bu kopyalanacak nesne `CStringT` nesne. Daha fazla bilgi için `CThisString` ve `CThisSimpleString`, Açıklamalar bölümüne bakın.  
  
 `varSrc`  
 Bu kopyalanacak VARIANT nesnesi `CStringT` nesnesi.  
  
 `BaseType`  
 String sınıfı karakter türü. Aşağıdakilerden biri olabilir:  
  
 `char` (için ANSI karakter dizelerini).  
  
 `wchar_t` (için Unicode karakter dizeleri).  
  
 `TCHAR` (ANSI ve Unicode karakter dizeleri için).  
  
 `bMFCDLL`  
 Proje bir MFC DLL (TRUE) olup olmadığını belirten Boolean (FALSE).  
  
 `SystemString`  
 Olmalıdır `System::String`, ve projeyi/CLR ile derlenmiş olmalıdır.  
  
 `pString`  
 İşleyici için bir `CStringT` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucular yeni ayrılmış depolama alanına giriş verilerini kopyaladığından farkında olmalıdır, bellek özel durumlara neden olabilir. Bu oluşturucu bazıları dönüştürme işlevleri hareket unutmayın. Değiştirin, örneğin, böylece bir `LPTSTR` burada bir `CStringT` nesnesi bekleniyor.  
  
- `CStringT`( `LPCSTR` `lpsz` ): Bir Unicode yapıları `CStringT` ANSI dizesinden. Bu oluşturucu, aşağıdaki örnekte gösterildiği gibi bir dize kaynağı yüklemek için de kullanabilirsiniz.  
  
- `CStringT(` `LPCWSTR` `lpsz` ): Oluşturan bir `CStringT` bir Unicode dizeden.  
  
- `CStringT`( `const unsigned char*` `psz` ): Oluşturmanıza olanak sağlayan bir `CStringT` gösteren bir işaretçi gelen `unsigned char`.  
  
> [!NOTE]
>  Tanımlamak **_CSTRING_DISABLE_NARROW_WIDE_CONVERSION** arasında örtük dize dönüştürme devre dışı bırakmak üzere makrosu [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] ve [!INCLUDE[TLA#tla_unicode](../../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] dizeleri. Makro dönüştürme desteği derleme oluşturucular dışlar.  
  
 Unutmayın `strSrc` parametresi olabilir ya da bir `CStringT` veya `CThisSimpleString` nesnesi. İçin `CStringT`, kendi varsayılan örneklemesi birini kullanın ( `CString`, `CStringA`, veya `CStringW`) için; `CThisSimpleString`, kullanan bir `this` işaretçi. `CThisSimpleString` örneği bildirir [CSimpleStringT sınıfı](../../atl-mfc-shared/reference/csimplestringt-class.md), daha küçük bir string sınıfı daha az yerleşik işlevselliğe sahip olduğu `CStringT` sınıfı.  
  
 Aşırı işleci `CSimpleStringT<>&()` oluşturan bir `CStringT` nesnesinin bir `CSimpleStringT` bildirimi.  
  
> [!NOTE]
>  Oluşturmak mümkün olmakla `CStringT` katıştırılmış boş karakterler içeren örnekleri, karşı öneririz. Yöntemleri ve işleçleri çağrılması `CStringT` katıştırılmış boş karakterler içeren nesneleri, istenmeyen sonuçları oluşturabilirsiniz.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]  
  
##  <a name="_dtorcstringt"></a>  CStringT:: ~ CStringT  
 Bozar `CStringT` nesnesi.  
  
```  
~CStringT() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bozar `CStringT` nesnesi.  
  
##  <a name="delete"></a>  CStringT::Delete  
 Verilen dizindeki karakter ile başlayan bir dizeden bir karakter ya da karakterlerini siler.  
  
```  
int Delete(int iIndex, int nCount = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `iIndex`  
 İlk karakter, sıfır tabanlı dizini `CStringT` silmek için nesne.  
  
 `nCount`  
 Kaldırılacak karakter sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değiştirilen dize uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `nCount` dizenin geri kalanı dizesi kaldırılır daha uzun.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]  
  
```Output  
Before: Soccer is best,
    but hockey is quicker!  
After: Soccer best,
    but hockey is quicker!  
```  
  
##  <a name="find"></a>  CStringT::Find  
 Bu dize bir karakter ya da alt dizenin ilk eşleşmesi için arar.  
  
```  
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszSub`  
 Aramak için bir alt dizesi.  
  
 `iStart`  
 İle aramaya başlamak için dize veya baştan başlamak için 0 karakter dizini.  
  
 `ch`  
 Aramak için tek bir karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu ilk karakteri sıfır tabanlı dizini `CStringT` istenen alt dize veya karakter eşleşen nesne; alt dize veya karakter bulunmazsa -1.  
  
### <a name="remarks"></a>Açıklamalar  
 Hem tek karakterleri kabul etmek için işlev aşırı (çalışma zamanı işlevine benzer `strchr`) ve dizeleri (benzer şekilde `strstr`).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]  
  
##  <a name="findoneof"></a>  CStringT::FindOneOf  
 İçinde yer alan herhangi bir karakterle eşleşir ilk karakter için bu dizeyi arar `pszCharSet`.  
  
```  
int FindOneOf(PCXSTR pszCharSet) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszCharSet`  
 Eşleme için karakter içeren dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk karakter de bu dize, sıfır tabanlı dizini `pszCharSet`; eşleşme yoksa -1.  
  
### <a name="remarks"></a>Açıklamalar  
 Karakterlerden herhangi birini ilk örneğini bulur `pszCharSet`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]  
  
##  <a name="format"></a>  CStringT::Format  
 Yazmaları biçimlendirilen verileri bir `CStringT` aynı şekilde bu [sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) verileri bir C tarzı karakter diziye biçimlendirir.  
  
```  
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```  
  
### <a name="parameters"></a>Parametreler  
 `nFormatID`  
 Denetim Biçimlendir dizesini içeren dize kaynak tanımlayıcısı.  
  
 `pszFormat`  
 Bir Denetim Biçimlendir dize.  
  
 `argument`  
 İsteğe bağlı bağımsız değişkenler.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev biçimlendirir ve bir dizi karakter ve değerleri depolar `CStringT`. Her isteğe bağlı bir değişken (varsa) dönüştürülür ve çıktı içinde karşılık gelen biçimi belirtimlerine göre `pszFormat` veya tarafından tanımlanan dize kaynaktan `nFormatID`.  
  
 Dize nesnesi bir parametre olarak sunulan çağrı başarısız olur `Format`. Örneğin, aşağıdaki kodu öngörülemeyen sonuçlara neden olur:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]  
  
 Daha fazla bilgi için bkz: [biçim belirtim Sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]  
  
##  <a name="formatmessage"></a>  CStringT::FormatMessage  
 Bir ileti dizesi biçimlendirir.  
  
```  
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```  
  
### <a name="parameters"></a>Parametreler  
 `nFormatID`  
 Biçimlendirilmemiş ileti metnini içeren dize kaynak tanımlayıcısı.  
  
 `pszFormat`  
 Denetim Biçimlendir dize noktalarına. Ekler için tararken ve uygun şekilde biçimlendirilmiş. Biçim dizesi çalışma zamanı işlevine benzer `printf`-rasgele bir sırada eklenecek parametrelere izin dışında biçim dizeleri stili.  
  
 `argument`  
 İsteğe bağlı bağımsız değişkenler.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev giriş olarak bir ileti tanımı gerektirir. İleti tanımı tarafından belirlenen `pszFormat` veya tarafından tanımlanan dize kaynaktan `nFormatID`. Bu işlev biçimlendirilmiş ileti metnini kopyalar `CStringT` istediyseniz INSERT sıraları herhangi katıştırılmış işleme nesnesi.  
  
> [!NOTE]
> `FormatMessage` Yeni biçimlendirilmiş dize için sistem belleği ayırmaya çalışır. Bu girişim başarısız olursa, bir bellek özel durumu otomatik olarak oluşturulur.  
  
 Her INSERT karşılık gelen bir parametre şunlara sahip olmanız gerekir `pszFormat` veya `nFormatID` parametresi. İleti metni içinde birkaç kaçış sıraları dinamik olarak iletiyi biçimlendirmek için desteklenir. Daha fazla bilgi için bkz: Windows [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) Windows SDK'sındaki işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]  
  
##  <a name="formatmessagev"></a>  CStringT::FormatMessageV  
 Değişken bağımsız değişken listesini kullanarak bir ileti dizesi biçimlendirir.  
  
```  
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszFormat`  
 Denetim Biçimlendir dize noktalarına. Ekler için tararken ve uygun şekilde biçimlendirilmiş. Biçim dizesi çalışma zamanı işlevine benzer `printf`-rasgele bir sırada eklenecek parametrelere izin dışında biçim dizeleri stili.  
  
 `pArgList`  
 Bağımsız değişkenler listesi işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev giriş olarak bir ileti tanımı gerektirir tarafından belirlenen `pszFormat`. Bu işlev biçimlendirilmiş ileti metni ve bağımsız değişken listesi kopyalar `CStringT` istediyseniz INSERT sıraları herhangi katıştırılmış işleme nesnesi.  
  
> [!NOTE]
> `FormatMessageV` çağrıları [CStringT::FormatMessage](#formatmessage), yeni biçimlendirilmiş dize için sistem belleği ayırmaya çalışır. Bu girişim başarısız olursa, bir bellek özel durumu otomatik olarak oluşturulur.  
  
 Daha fazla bilgi için bkz: Windows [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) Windows SDK'sındaki işlevi.  
  
##  <a name="formatv"></a>  CStringT::FormatV  
 Değişken bağımsız değişken listesini kullanarak bir ileti dizesi biçimlendirir.  
  
```  
void FormatV(PCXSTR pszFormat, va_list args);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszFormat`  
 Denetim Biçimlendir dize noktalarına. Ekler için tararken ve uygun şekilde biçimlendirilmiş. Biçim dizesi çalışma zamanı işlevine benzer `printf`-rasgele bir sırada eklenecek parametrelere izin dışında biçim dizeleri stili.  
  
 `args`  
 Bağımsız değişkenler listesi işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Biçimlendirilmiş bir dize ve bağımsız değişken listesi Yazar bir `CStringT` aynı dize biçimi `vsprintf_s` verileri bir C tarzı karakter diziye biçimlendirir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]  
  
##  <a name="getenvironmentvariable"></a>  CStringT::GetEnvironmentVariable  
 Dize belirtilen ortam değişkeninin değerine ayarlar.  
  
```  
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszVar`  
 İşaretçi null ile sonlandırılmış dizeye ortam değişkenini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Arama işlemi ortamı bloğundan belirtilen değişkenin değerini alır. Değer null ile sonlandırılan bir karakter dizesinin biçimindedir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]  
  
##  <a name="insert"></a>  CStringT::Insert  
 Tek bir karakter veya alt dize dize içinde verilen dizindeki ekler.  
  
```  
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```  
  
### <a name="parameters"></a>Parametreler  
 `iIndex`  
 Öncesinde ekleme gerçekleşecek karakter dizini.  
  
 `psz`  
 Eklenecek alt dizeyi gösteren bir işaretçi.  
  
 `ch`  
 Eklenecek karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değiştirilen dize uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 `iIndex` Parametresi karakter veya alt dize yer açmak amacıyla taşınır ilk karakter tanımlar. Varsa `nIndex` ekleme önce tüm dizeyi oluşacaktır sıfırdır. Varsa `nIndex` işlevi dize uzunluğu, mevcut dize birleştirme ve yeni malzeme ya da sağlanan büyük `ch` veya `psz`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]  
  
##  <a name="left"></a>  CStringT::Left  
 Soldaki ayıklar `nCount` bu karakterlerinden `CStringT` nesne ve bir kopyasını ayıklanan alt dizeyi döndürür.  
  
```  
CStringT Left(int nCount) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `nCount`  
 Buradan ayıklamak için karakter sayısını `CStringT` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CStringT` Belirtilen aralıktaki karakterleri bir kopyasını içeren nesne. Döndürülen `CStringT` nesnesi boş olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `nCount` dize uzunluğu aşıyor ve ardından tüm dizeyi ayıklanır. `Left` Temel benzer `Left` işlevi.  
  
 Çok baytlı karakter kümeleri (MBCS) için `nCount` bir karakteri olarak her 8 bit sırası değerlendirir böylece `nCount` iki tarafından çarpılan çok baytlı karakterlerin sayısını döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]  
  
##  <a name="loadstring"></a>  CStringT::LoadString  
 Tarafından tanımlanan bir Windows dize kaynağı okur `nID`, mevcut bir uygulamasına `CStringT` nesnesi.  
  
```  
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `hInstance`  
 Modül örneği için bir tanıtıcı.  
  
 `nID`  
 Bir Windows dize kaynak kimliği  
  
 `wLanguageID`  
 Dize kaynak dili.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynak yükü başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Dize kaynağını yükler ( `nID`) Belirtilen modül ( `hInstance`) belirtilen dili kullanarak ( `wLanguage`).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]  
  
##  <a name="makelower"></a>  CStringT::MakeLower  
 Dönüştürür `CStringT` küçük harf dize nesnesi.  
  
```  
CStringT& MakeLower();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonuçta elde edilen küçük harf dize.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]  
  
##  <a name="makereverse"></a>  CStringT::MakeReverse  
 Karakter sırasını tersine çevirir `CStringT` nesnesi.  
  
```  
CStringT& MakeReverse();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Elde edilen dizesi ters.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]  
  
##  <a name="makeupper"></a>  CStringT::MakeUpper  
 Dönüştürür `CStringT` büyük bir dize nesnesi.  
  
```  
CStringT& MakeUpper();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonuçta elde edilen büyük harf dize.  
  
### <a name="remarks"></a>Açıklamalar  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]  
  
##  <a name="mid"></a>  CStringT::Mid  
 Bir dizenin uzunluğunu ayıklar `nCount` bu karakterlerinden `CStringT` konumdan başlayarak nesne `iFirst` (sıfır tabanlı).  
  
```  
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `iFirst`  
 Bu ilk karakteri sıfır tabanlı dizini `CStringT` içinde ayıklanan substring eklenecek nesne.  
  
 `nCount`  
 Buradan ayıklamak için karakter sayısını `CStringT` nesnesi. Bu parametre sağlanmazsa, dizenin geri kalanı ayıklanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CStringT` Belirtilen aralıktaki karakterleri bir kopyasını içeren nesne. Unutmayın döndürülen `CStringT` nesnesi boş olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevi bir kopyasını ayıklanan alt dizeyi döndürür. `Mid` (temel dizinlerde tabanlı) temel Mid işlevi benzerdir.  
  
 (MBCS) birden çok baytlı karakter kümeleri için `nCount` her biri birden çok baytlı karakter iki karakter olarak sayılır 8 bit karakter; diğer bir deyişle, bir sağlama ve izi bayt başvuruyor.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]  
  
##  <a name="oemtoansi"></a>  CStringT::OemToAnsi  
 Bu tüm karakterleri dönüştürür `CStringT` ANSI karakter kümesi OEM karakter nesnesinden.  
  
```  
void OemToAnsi();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev kullanılamıyor, `_UNICODE` tanımlanır.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CStringT::AnsiToOem](#ansitooem).  
  
##  <a name="operator_add"></a>  CStringT::operator +  
 İki dizeyi veya bir karakter ve bir dizeyi art arda ekler.  
  
```  
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```  
  
### <a name="parameters"></a>Parametreler  
 `ch1`  
 Bir dizeyle birleştirmek için bir ANSI veya Unicode karakter.  
  
 `ch2`  
 Bir dizeyle birleştirmek için bir ANSI veya Unicode karakter.  
  
 `str1`  
 A `CStringT` bir dize veya karakter ile birleştirmek için.  
  
 `str2`  
 A `CStringT` bir dize veya karakter ile birleştirmek için.  
  
 `psz1`  
 Bir dize veya karakter ile birleştirmek için null ile sonlandırılmış bir dize için bir işaretçi.  
  
 `psz2`  
 Bir dize veya karakter ile birleştirmek için bir dize için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yedi aşırı biçimlerinin vardır `CStringT::operator+` işlevi. İlk sürüm iki varolan art arda ekler `CStringT` nesneleri. Sonraki iki Birleştir bir `CStringT` nesne ve null sonlandırılmış bir dize. Sonraki iki Birleştir bir `CStringT` nesnesi ve bir ANSI karakter. Son iki Birleştir bir `CStringT` nesnesi ve bir Unicode karakter.  
  
> [!NOTE]
>  Oluşturmak mümkün olmakla `CStringT` katıştırılmış boş karakterler içeren örnekleri, karşı öneririz. Yöntemleri ve işleçleri çağrılması `CStringT` katıştırılmış boş karakterler içeren nesneleri, istenmeyen sonuçları oluşturabilirsiniz.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]  
  
##  <a name="operator_add_eq"></a>  CStringT::operator +=  
 Dize sonu karakterleri art arda ekler.  
  
```  
CStringT& operator+=(const CThisSimpleString& str);

template<bool bMFCDLL>  
CStringT& operator+=(const const CSimpleStringT<BaseType, bMFCDLL>& str);

template<int t_nSize>  
CStringT& operator+=(const CStaticString<XCHAR, t_nSize>& strSrc);
CStringT& operator+=(PCXSTR pszSrc);
CStringT& operator+=(PCYSTR pszSrc);
CStringT& operator+=(char ch);
CStringT& operator+=(unsigned char ch);
CStringT& operator+=(wchar_t ch);
CStringT& operator+=(const VARIANT& var);
```  
  
### <a name="parameters"></a>Parametreler  
 str  
 Bir başvuru bir `CThisSimpleString` nesnesi.  
  
 `bMFCDLL`  
 Proje bir MFC DLL olup olmadığını belirten bir Boole değeri.  
  
 `BaseType`  
 Dize temel türü.  
  
 `var`  
 Bu dizeyi birleştirmek için bir VARIANT nesnesi.  
  
 `ch`  
 Bir dizeyle birleştirmek için bir ANSI veya Unicode karakter.  
  
 `pszSrc`  
 Birleştirilmiş özgün dize için bir işaretçi.  
  
 `strSrc`  
 A `CStringT` bu dizeyi birleştirmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç başka kabul `CStringT` nesnesi, bir karakter işaretçi veya tek bir karakter. Bilmeniz gereken özel durumlar için eklenen karakter için yeni bir depolama birimi ayrılmış olduğundan, bu birleştirme işleci kullandığınızda oluşabilir belleğin `CStringT` nesnesi.  
  
 Hakkında bilgi için `CThisSimpleString`, Açıklamalar bölümüne bakın [CStringT::CStringT](#cstringt).  
  
> [!NOTE]
>  Oluşturmak mümkün olmakla `CStringT` katıştırılmış boş karakterler içeren örnekleri, karşı öneririz. Yöntemleri ve işleçleri çağrılması `CStringT` katıştırılmış boş karakterler içeren nesneleri, istenmeyen sonuçları oluşturabilirsiniz.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]  
  
##  <a name="operator_eq_eq"></a>  CStringT::operator ==  
 İki dizeyi mantıksal olarak eşit olup olmadığını belirler.  
  
```  
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ch1`  
 Karşılaştırma için bir ANSI veya Unicode karakter.  
  
 `ch2`  
 Karşılaştırma için bir ANSI veya Unicode karakter.  
  
 `str1`  
 A `CStringT` karşılaştırması.  
  
 `str2`  
 A `CStringT` karşılaştırması.  
  
 `psz1`  
 Karşılaştırma için bir null ile sonlandırılmış dize için bir işaretçi.  
  
 `psz2`  
 Karşılaştırma için bir null ile sonlandırılmış dize için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dize veya karakter sol tarafındaki bir dize veya karakter sağ tarafında eşit ve TRUE veya false değerini uygun şekilde döndürür olup olmadığını sınar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]  
  
##  <a name="operator_neq"></a>  CStringT::operator! =  
 İki dizeyi eşit olup olmadığını mantıksal olarak belirler.  
  
```  
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ch1`  
 Bir dizeyle birleştirmek için bir ANSI veya Unicode karakter.  
  
 `ch2`  
 Bir dizeyle birleştirmek için bir ANSI veya Unicode karakter.  
  
 `str1`  
 A `CStringT` karşılaştırması.  
  
 `str2`  
 A `CStringT` karşılaştırması.  
  
 `psz1`  
 Karşılaştırma için bir null ile sonlandırılmış dize için bir işaretçi.  
  
 `psz2`  
 Karşılaştırma için bir null ile sonlandırılmış dize için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Testleri bir dize veya karakter sol tarafındaki bir dize veya karakter sağ tarafında eşit değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]  
  
##  <a name="operator_lt"></a>  CStringT::operator &lt;  
 Dize işlecinin sol tarafındaki sağ tarafında dize değerinden olup olmadığını belirler.  
  
```  
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 A `CStringT` karşılaştırması.  
  
 `str2`  
 A `CStringT` karşılaştırması.  
  
 `psz1`  
 Karşılaştırma için bir null ile sonlandırılmış dize için bir işaretçi.  
  
 `psz2`  
 Karşılaştırma için bir null ile sonlandırılmış dize için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizeleri, karakter kadar lexicographical karşılaştırması:  
  
-   İki karşılık gelen karakter eşit olmayan bulur ve bunların karşılaştırma sonucu arasında dizeleri karşılaştırma sonucu olarak alınır.  
  
-   Hiçbir inequalities bulur, ancak bir dizesi uzun dize değerinden diğer ve daha kısa bir dize olarak kabul daha fazla karakter içeriyor.  
  
-   Hiçbir inequalities ve aynı sayıda karakter dizeleri olan ve böylece dizeleri eşit bulur bulur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]  
  
##  <a name="operator_gt"></a>  CStringT::operator &gt;  
 Dize işlecinin sol tarafındaki sağ tarafında dize değerinden olup olmadığını belirler.  
  
```  
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 A `CStringT` karşılaştırması.  
  
 `str2`  
 A `CStringT` karşılaştırması.  
  
 `psz1`  
 Karşılaştırma için bir null ile sonlandırılmış dize için bir işaretçi.  
  
 `psz2`  
 Karşılaştırma için bir null ile sonlandırılmış dize için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizeleri, karakter kadar lexicographical karşılaştırması:  
  
-   İki karşılık gelen karakter eşit olmayan bulur ve bunların karşılaştırma sonucu arasında dizeleri karşılaştırma sonucu olarak alınır.  
  
-   Hiçbir inequalities bulur, ancak bir dizesi uzun dize değerinden diğer ve daha kısa bir dize olarak kabul daha fazla karakter içeriyor.  
  
-   Hiçbir inequalities ve dizeleri eşit olacak şekilde dizeleri aynı sayıda karakter olan bulur bulur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]  
  
##  <a name="operator_lt_eq"></a>  CStringT::operator &lt;=  
 İşlecinin sol tarafındaki dize değerinden küçük veya buna eşit sağ tarafında dizeye olup olmadığını belirler.  
  
```  
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 A `CStringT` karşılaştırması.  
  
 `str2`  
 A `CStringT` karşılaştırması.  
  
 `psz1`  
 Karşılaştırma için bir null ile sonlandırılmış dize için bir işaretçi.  
  
 `psz2`  
 Karşılaştırma için bir null ile sonlandırılmış dize için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizeleri, karakter kadar lexicographical karşılaştırması:  
  
-   İki karşılık gelen karakter eşit olmayan bulur ve bunların karşılaştırma sonucu arasında dizeleri karşılaştırma sonucu olarak alınır.  
  
-   Hiçbir inequalities bulur, ancak bir dizesi uzun dize değerinden diğer ve daha kısa bir dize olarak kabul daha fazla karakter içeriyor.  
  
-   Hiçbir inequalities ve dizeleri eşit olacak şekilde dizeleri aynı sayıda karakter olan bulur bulur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]  
  
##  <a name="operator_gt_eq"></a>  CStringT::operator &gt;=  
 Dize işlecinin sol tarafındaki sağ tarafında dizeye eşit veya daha büyük olup olmadığını belirler.  
  
```  
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 A `CStringT` karşılaştırması.  
  
 `str2`  
 A `CStringT` karşılaştırması.  
  
 `psz1`  
 Karşılaştırma için bir dize için bir işaretçi.  
  
 `psz2`  
 Karşılaştırma için bir dize için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizeleri, karakter kadar lexicographical karşılaştırması:  
  
-   İki karşılık gelen karakter eşit olmayan bulur ve bunların karşılaştırma sonucu arasında dizeleri karşılaştırma sonucu olarak alınır.  
  
-   Hiçbir inequalities bulur, ancak bir dizesi uzun dize değerinden diğer ve daha kısa bir dize olarak kabul daha fazla karakter içeriyor.  
  
-   Hiçbir inequalities ve dizeleri eşit olacak şekilde dizeleri aynı sayıda karakter olan bulur bulur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]  
  
##  <a name="remove"></a>  CStringT::Remove  
 Dizeden belirtilen karakterin tüm örneklerini kaldırır.  
  
```  
int Remove(XCHAR chRemove);
```  
  
### <a name="parameters"></a>Parametreler  
 `chRemove`  
 Bir dizeden kaldırılacak karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karakter sayısı dizeden kaldırıldı. Sıfır dize değişmez.  
  
### <a name="remarks"></a>Açıklamalar  
 Karakter karşılaştırma büyük küçük harf duyarlıdır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]  
  
##  <a name="replace"></a>  CStringT::Replace  
 İki sürümü vardır `Replace`. İlk sürüm, başka bir alt dizesi kullanarak bir alt dizesi bir veya daha fazla kopyasını yerini alır. Her iki alt dizeler null sonlandırıldı. İkinci Sürüm, başka bir karakter kullanarak bir karakterin bir veya daha fazla kopyasını yerini alır. Her iki sürümünü de depolanan karakter veri çalışmayabilir `CStringT`.  
  
```  
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszOld`  
 Sonlandırılmış bir dize olarak değiştirilir gösteren bir işaretçi `pszNew`.  
  
 `pszNew`  
 Değiştirir null ile sonlandırılmış bir dize için bir işaretçi `pszOld`.  
  
 `chOld`  
 Karakter olarak değiştirilir `chNew`.  
  
 `chNew`  
 Karakter değiştirme `chOld`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dize değişmez varsa karakter veya alt dize ya da sıfır değiştirilen örnek sayısı değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `Replace` dize uzunluğu çünkü değiştirebilirsiniz `pszNew` ve `pszOld` aynı uzunlukta olması gerekmez ve eski alt dizeyi birçok kopyası için yeni bir değiştirilebilir. Büyük küçük harfe duyarlı bir eşleşme işlevi gerçekleştirir.  
  
 Örnekleri `CStringT` örnekleri `CString`, `CStringA`, ve `CStringW`.  
  
 İçin `CStringA`, `Replace` ANSI veya birden çok baytlı (MBCS) karakterler ile çalışır. İçin `CStringW`, `Replace` geniş karakterler ile çalışır.  
  
 İçin `CString`, karakter veri türü sabitleri aşağıdaki tabloda tanımlanmış olan temel derleme zamanında seçilir.  
  
|Tanımlanan sabiti|Karakter veri türü|  
|----------------------|-------------------------|  
|`_UNICODE`|Geniş karakterler|  
|`_MBCS`|Çok baytlı karakterler|  
|Ne|Tek baytlı karakterler|  
|Her ikisi|Tanımlanmamış|  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]  
  
##  <a name="reversefind"></a>  CStringT::ReverseFind  
 Bu arar `CStringT` nesne bir karakterin son eşleşme.  
  
```  
int ReverseFind(XCHAR ch) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ch`  
 Aranacak karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu son karakter sıfır tabanlı dizini `CStringT` karakter bulunmazsa eşleşen istenen karakter ya da -1 nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev çalışma zamanı işlevine benzer `strrchr`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]  
  
##  <a name="right"></a>  CStringT::Right  
 Son ayıklar (diğer bir deyişle, en sağdaki) `nCount` bu karakterlerinden `CStringT` nesne ve bir kopyasını ayıklanan alt dizeyi döndürür.  
  
```  
CStringT Right(int nCount) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `nCount`  
 Buradan ayıklamak için karakter sayısını `CStringT` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CStringT` Belirtilen aralıktaki karakterleri bir kopyasını içeren nesne. Unutmayın döndürülen `CStringT` nesnesi boş olamaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `nCount` dize uzunluğu aşıyor ve ardından tüm dizeyi ayıklanır. `Right` Temel benzer `Right` (Basic dizinlerde sıfır tabanlı ancak bu) işlev.  
  
 (MBCS) birden çok baytlı karakter kümeleri için `nCount` her biri birden çok baytlı karakter iki karakter olarak sayılır 8 bit karakter; diğer bir deyişle, bir sağlama ve izi bayt başvuruyor.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]  
  
##  <a name="setsysstring"></a>  CStringT::SetSysString  
 Yeniden ayırır `BSTR` gösterdiği `pbstr` ve içeriğini kopyalar `CStringT` dahil olmak üzere, nesnesine `NULL` karakter.  
  
```  
BSTR SetSysString(BSTR* pbstr) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `pbstr`  
 Bir karakter dizesi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni bir dize.  
  
### <a name="remarks"></a>Açıklamalar  
 İçeriğini bağlı olarak `CStringT` nesnesi, değeri `BSTR` tarafından başvurulan `pbstr` değiştirebilirsiniz. İşlev oluşturur bir `CMemoryException` yeterli bellek varsa.  
  
 Bu işlev, normalde başvuruya göre Otomasyon için geçirilen dize değeri değiştirmek için kullanılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]  
  
##  <a name="spanexcluding"></a>  CStringT::SpanExcluding  
 Tarafından tanımlanan karakter kümesi olmayan ilk karakter ile başlayarak, dizeden karakterleri ayıklar `pszCharSet`.  
  
```  
CStringT SpanExcluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `pszCharSet`  
 Bir dizeyi bir karakter kümesi yorumlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dize olmayan karakter içeren bir alt dizesi `pszCharSet`, ilk karakter, dize ile başlayan ve de dizesinde bulunan ilk karakter ile biten `pszCharSet` (diğer bir deyişle, ilk karakter, başlayarak dize ve kadar ancak ilk karakter, dize hariç bulunamadı `pszCharSet`). Hiçbir karakter ise tüm dizeyi döndürür `pszCharSet` dizesinde bulunamadı.  
  
### <a name="remarks"></a>Açıklamalar  
 `SpanExcluding` ayıklar ve bir karakter ilk örneğini önceki tüm karakterleri verir `pszCharSet` (diğer bir deyişle, karakterlerinden `pszCharSet` ve dizesinde sonraki tüm karakterler alınmadı). Hiçbir karakter varsa `pszCharSet` dizesinde sonra bulunan `SpanExcluding` tüm dizeyi döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]  
  
##  <a name="spanincluding"></a>  CStringT::SpanIncluding  
 Tarafından tanımlanan karakter kümesi olan ilk karakter ile başlayarak, dizeden karakterleri ayıklar `pszCharSet`.  
  
```  
CStringT SpanIncluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `pszCharSet`  
 Bir dizeyi bir karakter kümesi yorumlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bulunan dizedeki karakter içeren bir alt dizesi `pszCharSet`, ilk karakter, dize ile başlayan ve bir karakter değil dizesinde bulunduğunda bitiş `pszCharSet`. `SpanIncluding` ilk karakter dizesi, belirtilen kümesinde değilse boş bir alt dizeyi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizenin ilk karakterin karakter kümesinde sonra değilse `SpanIncluding` boş bir dize döndürür. Aksi takdirde, kümesinde yer alan ardışık bir karakter dizisi döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]  
  
##  <a name="tokenize"></a>  CStringT::Tokenize  
 Bir hedef dizisindeki sonraki belirteç bulur  
  
```  
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `pszTokens`  
 Belirteç sınırlayıcıları içeren bir dize. Bu sınırlayıcılar sırası önemli değildir.  
  
 `iStart`  
 Aramaya başlamak için sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CStringT` geçerli belirteç değeri içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `Tokenize` İşlevi hedef dizesinde sonraki belirteç bulur. Karakter kümesi `pszTokens` bulunamadığı için belirteç olası sınırlayıcılar belirtir. Her çağrıda `Tokenize` işlevi başlar `iStart`başında sınırlayıcıları atlar ve döndürür bir `CStringT` sonraki sınırlayıcı karakter en fazla karakter dizesidir geçerli belirteci içeren nesne. Değeri `iStart` dize sonuna ulaşıldı bitiş sınırlayıcı karakter veya -1 izlemeyi konumu olacak şekilde güncelleştirildi. Daha fazla belirteçleri çağrıları için bir dizi hedef dizesi geri kalanı dışında ayrılabilir `Tokenize`kullanarak `iStart` sonraki belirtecidir okumak için dize where izlemek için. Başka belirteç olduğunda işlevi boş bir dize döndürür ve `iStart` -1 olarak ayarlayın.  
  
 CRT gibi işlevler simgeleştirilecek [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md), `Tokenize` hedef dizesi değiştirmez.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]  
  
### <a name="remarks"></a>Açıklamalar  
 Bu örnek çıkışı aşağıdaki gibidir:  
  
 `Resulting Token: First`  
  
 `Resulting Token: Second`  
  
 `Resulting Token: Third`  
  
##  <a name="trim"></a>  CStringT::Trim  
 Baştaki ve sondaki dizeden karakterleri kırpar.  
  
```  
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```  
  
### <a name="parameters"></a>Parametreler  
 `chTarget`  
 Aynı hedef karakteri.  
  
 `pszTargets`  
 Kırpılmış olması için hedef karakterler içeren bir dize için bir işaretçi. Tüm öndeki ve sondaki karakter oluşumları `pszTarget` gelen kırpılmış `CStringT` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölünen dize döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm öndeki ve sondaki aşağıdakilerden birini kaldırır:  
  
-   Belirtilen karakter `chTarget.`  
  
-   Tüm karakterler tarafından belirtilen dizede bulundu `pszTargets.`  
  
-   Boşluk.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]  
  
### <a name="remarks"></a>Açıklamalar  
 Bu örnek çıkışı aşağıdaki gibidir:  
  
 `Before: "******Soccer is best, but liquor is quicker!!!!!"`  
  
 `After : "Soccer is best, but liquor is quicker"`  
  
##  <a name="trimleft"></a>  CStringT::TrimLeft  
 Dizeden karakterleri baştaki kırpar.  
  
```  
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```  
  
### <a name="parameters"></a>Parametreler  
 `chTarget`  
 Aynı hedef karakteri.  
  
 `pszTargets`  
 Kırpılmış olması için hedef karakterler içeren bir dize için bir işaretçi. Karakter önde gelen tüm oluşumlarını `pszTarget` gelen kırpılmış `CStringT` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonuç kesilmiş dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm öndeki ve sondaki aşağıdakilerden birini kaldırır:  
  
-   Belirtilen karakter `chTarget.`  
  
-   Tüm karakterler tarafından belirtilen dizede bulundu `pszTargets.`  
  
-   Boşluk.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]  
  
##  <a name="trimright"></a>  CStringT::TrimRight  
 Sondaki dizeden karakterleri kırpar.  
  
```  
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```  
  
### <a name="parameters"></a>Parametreler  
 `chTarget`  
 Aynı hedef karakteri.  
  
 `pszTargets`  
 Kırpılmış olması için hedef karakterler içeren bir dize için bir işaretçi. Tüm karakterleri oluşumları sondaki `pszTarget` gelen kırpılmış `CStringT` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `CStringT` bölünen dize içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdakilerden birini oluşumları sondaki kaldırır:  
  
-   Belirtilen karakter `chTarget.`  
  
-   Tüm karakterler tarafından belirtilen dizede bulundu `pszTargets.`  
  
-   Boşluk.  
  
 `CStringT& TrimRight(XCHAR chTarget)` Sürüm bir karakter parametresini kabul edip bu karakteri tüm kopyalarını sonundan kaldırır `CStringT` dize verileri. Dizesinin sonundan başlatır ve öne doğru çalışır. Veya farklı bir karakter bulduğu zaman durdurur `CSTringT` karakter verileri dışında çalışır.  
  
 `CStringT& TrimRight(PCXSTR pszTargets)` Sürüm aramak için farklı tüm karakterleri içeren null ile sonlandırılan bir karakter kabul eder. Tüm kopyalarını karakterleri kaldırır `CStringT` nesnesi. Dizenin sonunda başlatır ve öne doğru çalışır. Hedef dize olmayan bir karakter bulduğunda ya da zaman durdurur `CStringT` karakter verileri dışında çalışır. Bir alt dizenin sonunda tüm hedef dizeye eşleşecek şekilde denemez `CStringT`.  
  
 `CStringT& TrimRight()` Sürümünü parametresiz gerektirir. Sondaki boşluk karakterlerini sonundan kırpar `CStringT` dize. Boşluk karakterleri, satır sonları, boşluk ya da sekme olabilir.  
  
-  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC sınıfları paylaşılan](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [CSimpleStringT Sınıfı](../../atl-mfc-shared/reference/csimplestringt-class.md)


