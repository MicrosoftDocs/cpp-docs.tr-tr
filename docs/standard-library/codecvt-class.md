---
title: "codecvt sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
dev_langs:
- C++
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b456472fc28b473da29169acb899a1a8a142c095
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="codecvt-class"></a>codecvt Sınıfı
Bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı. Programın içindeki karakterleri ve program dışındaki karakterleri kodlamak için kullanılan değerler dizisi arasındaki dönüştürmeleri denetleyebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class CharType, class Byte, class StateType>  
class codecvt : public locale::facet, codecvt_base;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `CharType`  
 Bir program içindeki karakterleri kodlamak için kullanılan tür.  
  
 `Byte`  
 Bir program dışındaki karakterleri kodlamak için kullanılan bir tür.  
  
 `StateType`  
 Karakter temsillerinin iç ve dış türleri arasındaki bir dönüştürmenin ara durumlarını temsil etmek için kullanılan bir tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı olarak hizmet verebilir bir nesneyi tanımlayan bir [yerel model](../standard-library/locale-class.md#facet_class), bir dizi türü değerleri arasında dönüştürme denetlemek için `CharType` ve bir dizi türü değerleri `Byte`. Sınıf `StateType` --dönüştürme ve sınıfın bir nesnesi belirtir `StateType` herhangi bir dönüştürme sırasında gerekli durum bilgilerini depolar.  
  
 İç kodlama bir gösterimini bayt karakter başına sabit sayıda genellikle ya da yazın kullanır `char` veya türü `wchar_t`.  
  
 Tüm yerel model statik nesnesi ile `id` bir ilk sıfır değeri saklanan. Benzersiz bir pozitif değer saklı değerini erişmek için ilk deneme depolar `id`.  
  
 Şablon sürümleri [do_in](#do_in) ve [do_out](#do_out) her zaman geri `codecvt_base::noconv`.  
  
 C++ Standart Kitaplığı birkaç açık özelleştirmeleri tanımlar:  
  
 `template<>`  
  
 `codecvt<wchar_t, char, mbstate_t>`  
  
 arasında dönüştürür `wchar_t` ve `char` sıraları.  
  
 `template<>`  
  
 `codecvt<char16_t, char, mbstate_t>`  
  
 arasında dönüştürür `char16_t` UTF-16 kodlanmış sıraları ve `char` UTF-8 olarak kodlanmış sıraları.  
  
 `template<>`  
  
 `codecvt<char32_t, char, mbstate_t>`  
  
 arasında dönüştürür `char32_t` UTF-32 (UCS-4) kodlanmış sıraları ve `char` UTF-8 olarak kodlanmış sıraları.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[codecvt](#codecvt)|Sınıfının nesneleri için oluşturucu `codecvt` dönüşümleri işlemek için yerel ayar model görev yapar.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[extern_type](#extern_type)|Dış temsiller için kullanılan karakter türü.|  
|[intern_type](#intern_type)|İç temsiller için kullanılan karakter türü.|  
|[state_type](#state_type)|İç ve dış temsiller arasındaki dönüştürmeler sırasında ara durumları temsil etmek için kullanılan bir karakter türü.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[always_noconv](#always_noconv)|Bir dönüştürme yapılıp yapılmayacağını sınar.|  
|[do_always_noconv](#do_always_noconv)|Hiçbir dönüştürme yapılması gerekip gerekmediğini sınamak için çağrılan bir sanal işlev.|  
|[do_encoding](#do_encoding)|Testleri bir sanal işlev kodlamasını `Byte` akışıdır durumu bağımlı olup arasındaki oran `Byte`kullanılan s ve `CharType`üretilen s sabittir ve, varsa, o oranı değeri belirler.|  
|[do_in](#do_in)|Bir sanal işlev olarak adlandırılan bir dizi iç dönüştürmek için `Byte`harici bir dizi s `CharType`s.|  
|[do_length](#do_length)|Belirleyen sanal işlev kaç `Byte`dış belirli bir dizi s'den `Byte`s ürettiği iç verilen sayıdan fazla `CharType`s ve o sayısını döndürür `Byte`s.|  
|[do_max_length](#do_max_length)|Dış bayt sayısını bir üretmek gerekli iç döndüren bir sanal işlev `CharType`.|  
|[do_out](#do_out)|Bir sanal işlev olarak adlandırılan bir dizi iç dönüştürmek için `CharType`s dış bayt dizisi.|  
|[do_unshift](#do_unshift)|Bir sanal işlev adlı sağlamak için `Byte`durumu bağımlı dönüştürmede bir dizi son karakter tamamlamak için gereken s `Byte`s.|  
|[encoding](#encoding)|Varsa testleri kodlamasını `Byte` akışıdır durumu bağımlı olup arasındaki oran `Byte`kullanılan s ve `CharType`üretilen s sabittir ve, varsa, o oranı değeri belirler.|  
|[in](#in)|Bir dizi harici temsilini dönüştürür `Byte`bir dizi iç bir temsili s `CharType`s.|  
|[uzunluğu](#length)|Belirler kaç `Byte`dış belirli bir dizi s'den `Byte`s ürettiği iç verilen sayıdan fazla `CharType`s ve o sayısını döndürür `Byte`s.|  
|[max_length](#max_length)|Dış maksimum sayısını döndürür `Byte`s bir dahili üretmek için gerekli `CharType`.|  
|[out](#out)|Bir dizi iç dönüştürür `CharType`harici bir dizi s `Byte`s.|  
|[unshift](#unshift)|Dış sağlar `Byte`durumu bağımlı dönüştürmede dizisini son karakter tamamlamak için gereken s `Byte`s.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
##  <a name="always_noconv"></a>  codecvt::always_noconv  
 Bir dönüştürme yapılıp yapılmayacağını sınar.  
  
```  
bool always_noconv() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir Boole değeri **true** hiçbir dönüşümleri yapılması; **false** yapılması en az bir gerekiyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [do_always_noconv](#do_always_noconv).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// codecvt_always_noconv.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >   
      ( loc ).always_noconv( );  
  
   if ( result1 )  
      cout << "No conversion is needed." << endl;  
   else  
      cout << "At least one conversion is required." << endl;  
  
   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >   
      ( loc ).always_noconv( );  
  
   if ( result2 )  
      cout << "No conversion is needed." << endl;  
   else  
      cout << "At least one conversion is required." << endl;  
}  
```  
  
```Output  
No conversion is needed.  
At least one conversion is required.  
```  
  
##  <a name="codecvt"></a>  codecvt::codecvt  
 Dönüşümler işlemek için yerel ayar model hizmet veren sınıfı codecvt nesnelerin Oluşturucusu.  
  
```  
explicit codecvt(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Refs`  
 Bellek yönetimi nesnesinin türünü belirtmek için kullanılan tamsayı değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Olası değerler için `_Refs` parametre ve bunların anlamlı:  
  
-   0: nesne ömrü onu içeren yerel ayarları tarafından yönetilir.  
  
-   1: nesne ömrü el ile yönetilmesi gerekir.  
  
-   \> 1: Bu değerleri tanımlanmamış.  
  
 Oluşturucu başlatır, `locale::facet` temel nesnesiyle **yerel ayar::**[modeli](../standard-library/locale-class.md#facet_class)(`_Refs`).  
  
##  <a name="do_always_noconv"></a>  codecvt::do_always_noconv  
 Hiçbir dönüştürme yapılması gerekip gerekmediğini sınamak için çağrılan bir sanal işlev.  
  
```  
virtual bool do_always_noconv() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Korumalı sanal üye fonksiyonu döndürür **true** yalnızca her çağrı için [do_in](#do_in) veya [do_out](#do_out) döndürür **noconv**.  
  
 Şablon sürümü her zaman döndürür **doğru**.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [always_noconv](#always_noconv), çağıran `do_always_noconv`.  
  
##  <a name="do_encoding"></a>  codecvt::do_encoding  
 Testleri bir sanal işlev kodlamasını **bayt** akışıdır durumu bağımlı olup arasındaki oran **bayt**kullanılan s ve **CharType**üretilen s sabit ve, varsa, o oranı değeri belirler.  
  
```  
virtual int do_encoding() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Korumalı sanal üye fonksiyonu döndürür:  
  
-   -1, değilse kodlama türü dizilerini `extern_type` durumuna bağlıdır.  
  
-   0, kodlama, değişken uzunlukta sıraları içeriyorsa.  
  
- *N*, kodlama uzunluğu yalnızca sıraları içeriyorsa *N*  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [kodlama](#encoding), çağıran `do_encoding`.  
  
##  <a name="do_in"></a>  codecvt::do_in  
 Bir sanal işlev adlı dış bir dizi dönüştürmek için **bayt**bir dizi iç s **CharType**s.  
  
```  
virtual result do_in(
    StateType& _State,  
    const Byte* first1,   
    const Byte* last1,   
    const Byte*& next1,  
    CharType* first2,  
    CharType* last2,  
    CharType*& next2,) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_State`  
 Üye işlev çağrıları arasında korunur dönüştürme durumu.  
  
 `first1`  
 Dönüştürülecek dizisi başına işaretçi.  
  
 `last1`  
 Dönüştürülecek bitişinde işaretçi.  
  
 `next1`  
 İşaretçi ötesinde ilk Dönüştürülmeyen karaktere dönüştürülen dizisi.  
  
 `first2`  
 Dönüştürülen dizisi başına işaretçi.  
  
 `last2`  
 Dönüştürülen bitişinde işaretçi.  
  
 `next2`  
 İşaretçi **CharType** son dönüştürülen sonra gelir **CharType**, hedef sıradaki ilk değiştirilmemiş karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, kısmi başarılı veya başarısız işlem gösterir döndürür. İşlevi döndürür:  
  
- **codecvt_base::Error** kaynak sırası hatalı olması durumunda oluşturulmuş.  
  
- `codecvt_base::noconv` hiçbir dönüştürme işlevi uyguluyorsa.  
  
- **codecvt_base::ok** dönüştürme başarılı olursa.  
  
- **codecvt_base::partial** kaynak yetersiz olması veya hedef dönüştürme işleminin başarılı olması için yeterince büyük değil.  
  
### <a name="remarks"></a>Açıklamalar  
 `_State` Yeni bir kaynak sırası ilk dönüştürme durumunu başında temsil etmesi gerekir. İşlev depolanan değeri başarılı bir dönüştürme geçerli durumunu yansıtacak şekilde değiştirir. Saklı değerini, aksi takdirde belirtilmeyen olur.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [içinde](#in), çağıran `do_in`.  
  
##  <a name="do_length"></a>  codecvt::do_length  
 Belirleyen sanal işlev kaç **bayt**dış belirli bir dizi s'den **bayt**s ürettiği iç verilen sayıdan fazla **CharType**s ve getirir sayısı **bayt**s.  
  
```  
virtual int do_length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_State`  
 Üye işlev çağrıları arasında korunur dönüştürme durumu.  
  
 `first1`  
 İşaretçi başına dış dizisi.  
  
 `last1`  
 Dış bitişinde işaretçi.  
  
 `_Len2`  
 En fazla sayısını **bayt**üye işlevi tarafından döndürülen s.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüştürme, değerden daha fazla en fazla sayısını temsil eden bir tamsayı `_Len2`, dış kaynak sırası tarafından tanımlanan [ `first1`, `last1`).  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı sanal üye fonksiyonu etkili bir şekilde çağırır `do_in`( `_State`, `first1`, `last1`, `next1`, `_Buf`, `_Buf`  +  `_Len2`, `next2`) için`_State` (bir kopyasını durumu), bazı arabellek `_Buf`, işaretçileri ve `next1`ve `next2`.  
  
 Daha sonra döndürür `next2`  -  **arabelleğe**. Bu nedenle, dönüştürme, değerden daha fazla maksimum sayısını sayar `_Len2`, kaynak sırası tarafından tanımlanan [ `first1`, `last1`).  
  
 Şablon sürümü her zaman küçük olanı döndürür `last1`  -  `first1` ve `_Len2`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [uzunluğu](#length), çağıran **do_length**.  
  
##  <a name="do_max_length"></a>  codecvt::do_max_length  
 Dış üst sınırını döndüren bir sanal işlev **bayt**s bir dahili üretmek için gerekli **CharType**.  
  
```  
virtual int do_max_length() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 En fazla sayısını **bayt**s bir üretmek için gerekli **CharType**.  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı sanal üye fonksiyonu tarafından döndürülen izin verilen en büyük değeri döndürür [do_length](#do_length)( `first1`, `last1`, 1) rasgele geçerli değerler için `first1` ve `last1`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [max_length](#max_length), çağıran `do_max_length`.  
  
##  <a name="do_out"></a>  codecvt::do_out  
 Bir sanal işlev olarak adlandırılan bir dizi iç dönüştürmek için **CharType**harici bir dizi s **bayt**s.  
  
```  
virtual result do_out(
    StateType& _State,  
    const CharType* first1,   
    const CharType* last1,  
    const CharType*& next1,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_State`  
 Üye işlev çağrıları arasında korunur dönüştürme durumu.  
  
 `first1`  
 Dönüştürülecek dizisi başına işaretçi.  
  
 `last1`  
 Dönüştürülecek bitişinde işaretçi.  
  
 `next1`  
 İlk gösteren bir işaretçi başvuru dönüştürmeden **CharType**, son sonra **CharType** dönüştürülür.  
  
 `first2`  
 Dönüştürülen dizisi başına işaretçi.  
  
 `last2`  
 Dönüştürülen bitişinde işaretçi.  
  
 `next2`  
 İlk gösteren bir işaretçi başvuru dönüştürmeden **bayt**, son sonra **bayt** dönüştürülür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlevi döndürür:  
  
- **codecvt_base::Error** kaynak sırası hatalı olması durumunda oluşturulmuş.  
  
- `codecvt_base::noconv` hiçbir dönüştürme işlevi uyguluyorsa.  
  
- **codecvt_base::ok** dönüştürme başarılı olursa.  
  
- **codecvt_base::partial** kaynak yetersiz olması veya hedef dönüştürme işleminin başarılı olması için yeterince büyük değil.  
  
### <a name="remarks"></a>Açıklamalar  
 `_State` Yeni bir kaynak sırası ilk dönüştürme durumunu başında temsil etmesi gerekir. İşlev depolanan değeri başarılı bir dönüştürme geçerli durumunu yansıtacak şekilde değiştirir. Saklı değerini, aksi takdirde belirtilmeyen olur.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [çıkışı](#out), çağıran `do_out`.  
  
##  <a name="do_unshift"></a>  codecvt::do_unshift  
 Bir sanal işlev adlı sağlamak için **bayt**durumu bağımlı dönüştürmede bir dizi son karakter tamamlamak için gereken s **bayt**s.  
  
```  
virtual result do_unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_State`  
 Üye işlev çağrıları arasında korunur dönüştürme durumu.  
  
 `first2`  
 Hedef aralıktaki ilk konuma yönelik işaretçi.  
  
 `last2`  
 Hedef aralık son konuma yönelik işaretçi.  
  
 `next2`  
 Hedef sırası ilk değiştirilmemiş öğe işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlevi döndürür:  
  
- **codecvt_base::Error** , _ *durumu* geçersiz bir durum temsil eder  
  
- `codecvt_base::noconv` işlev dönüştürme gerçekleştirirse  
  
- **codecvt_base::ok** dönüştürme başarılı olursa  
  
- **codecvt_base::partial** hedef dönüştürme işleminin başarılı olması için yeterince büyük değilse  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı sanal üye fonksiyonu source öğesi değiştirmeye çalıştığında **CharType**(0) içinde depolayan bir hedef dizisine [ `first2`, `last2`), sonlandırma öğesi dışında **bayt** (0). Her zaman depolar `next2` hedef sırası ilk değiştirilmemiş öğe için bir işaretçi.  
  
 _ *Durumu* ilk dönüştürme durumunu başında yeni bir kaynak dizisini temsil etmesi gerekir. İşlev depolanan değeri başarılı bir dönüştürme geçerli durumunu yansıtacak şekilde değiştirir. Genellikle, kaynak öğenin dönüştürme **CharType**(0) geçerli durumu ilk dönüştürme durumda bırakır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [unshift](#unshift), çağıran `do_unshift`.  
  
##  <a name="encoding"></a>  codecvt::Encoding  
 Varsa testleri kodlamasını **bayt** akışıdır durumu bağımlı olup arasındaki oran **bayt**kullanılan s ve **CharType**üretilen s sabittir ve, varsa, belirler Bu oranı değeri.  
  
```  
int encoding() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri pozitif sonra bu değeri sabit sayısıdır **bayt** üretmek için gereken karakter **CharType** karakter.  
  
 Korumalı sanal üye fonksiyonu döndürür:  
  
-   -1, değilse kodlama türü dizilerini `extern_type` durumuna bağlıdır.  
  
-   0, kodlama, değişken uzunlukta sıraları içeriyorsa.  
  
- *N*, kodlama uzunluğu yalnızca sıraları içeriyorsa *n*  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [do_encoding](#do_encoding).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// codecvt_encoding.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );  
   cout << result1 << endl;  
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );  
   cout << result1 << endl;  
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );  
   cout << result1 << endl;  
}  
```  
  
```Output  
1  
1  
1  
```  
  
##  <a name="extern_type"></a>  codecvt::extern_type  
 Dış temsiller için kullanılan karakter türü.  
  
```  
typedef Byte extern_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **bayt**.  
  
##  <a name="in"></a>  codecvt::in  
 Bir dizi harici temsilini dönüştürür **bayt**bir dizi iç bir temsili s **CharType**s.  
  
```  
result in(
    StateType& _State,  
    const Byte* first1,   
    const Byte* last1,   
    const Byte*& next1,  
    CharType* first2,  
    CharType* last2,  
    CharType*& next2,) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_State`  
 Üye işlev çağrıları arasında korunur dönüştürme durumu.  
  
 `first1`  
 Dönüştürülecek dizisi başına işaretçi.  
  
 `last1`  
 Dönüştürülecek bitişinde işaretçi.  
  
 `next1`  
 İşaretçi ilk Dönüştürülmeyen karakter dönüştürülen dizinin ötesinde.  
  
 `first2`  
 Dönüştürülen dizisi başına işaretçi.  
  
 `last2`  
 Dönüştürülen bitişinde işaretçi.  
  
 `next2`  
 İşaretçi **CharType** son dönüştürülen sonra gelir **Chartype** hedef sıradaki ilk değiştirilmemiş karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, kısmi başarılı veya başarısız işlem gösterir döndürür. İşlevi döndürür:  
  
- **codecvt_base::Error** kaynak sırası hatalı olması durumunda oluşturulmuş.  
  
- `codecvt_base::noconv` hiçbir dönüştürme işlevi uyguluyorsa.  
  
- **codecvt_base::ok** dönüştürme başarılı olursa.  
  
- **codecvt_base::partial** kaynak yetersiz olması veya hedef dönüştürme işleminin başarılı olması için yeterince büyük değil.  
  
### <a name="remarks"></a>Açıklamalar  
 `_State` Yeni bir kaynak sırası ilk dönüştürme durumunu başında temsil etmesi gerekir. İşlev saklı değerini gerektiğinde başarılı dönüştürme geçerli durumunu yansıtacak biçimde değiştirir. Kısmi dönüştürmeden sonra `_State` dönüştürme yeni karakterler geldiğinde sürdürmek için izin vermek amacıyla ayarlamanız gerekir.  
  
 Üye işlevi döndürür [do_in](#do_in)( `_State`, _ *First1, last1, next1, First2, _Llast2, next2*).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// codecvt_in.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char* pszExt = "This is the string to be converted!";  
   wchar_t pwszInt [LEN+1];  
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));  
   const char* pszNext;  
   wchar_t* pwszNext;  
   mbstate_t state = {0};  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
     ( loc ).in( state,  
          pszExt, &pszExt[strlen(pszExt)], pszNext,  
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );  
   pwszInt[strlen(pszExt)] = 0;  
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )  
   << L"The converted string is:\n ["  
   << &pwszInt[0]  
   << L"]" << endl;  
   exit(-1);  
}  
```  
  
```Output  
It worked! The converted string is:  
 [This is the string to be converted!]  
```  
  
##  <a name="intern_type"></a>  codecvt::intern_type  
 İç temsiller için kullanılan karakter türü.  
  
```  
typedef CharType intern_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **CharType**.  
  
##  <a name="length"></a>  codecvt::length  
 Belirler kaç **bayt**dış belirli bir dizi s'den **bayt**s ürettiği iç verilen sayıdan fazla **CharType**s ve o sayısınıdöndürür**Bayt**s.  
  
```  
int length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_State`  
 Üye işlev çağrıları arasında korunur dönüştürme durumu.  
  
 `first1`  
 İşaretçi başına dış dizisi.  
  
 `last1`  
 Dış bitişinde işaretçi.  
  
 `_Len2`  
 Üye işlevi tarafından döndürülen bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüştürme, değerden daha fazla en fazla sayısını temsil eden bir tamsayı `_Len2`, dış kaynak sırası tarafından tanımlanan [ `first1`, `last1`).  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [do_length](#do_length)( *_State, first1*, `last1`, `_Len2`).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// codecvt_length.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char* pszExt = "This is the string whose length is to be measured!";  
   mbstate_t state = {0};  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
     ( loc ).length( state,  
          pszExt, &pszExt[strlen(pszExt)], LEN );  
   cout << "The length of the string is: ";  
   wcout << res;  
   cout << "." << endl;  
   exit(-1);  
}  
```  
  
```Output  
The length of the string is: 50.  
```  
  
##  <a name="max_length"></a>  codecvt::max_length  
 Dış maksimum sayısını döndürür **bayt**s bir dahili üretmek için gerekli **CharType**.  
  
```  
int max_length() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 En fazla sayısını **bayt**s bir üretmek için gerekli **CharType**.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [do_max_length](#do_max_length).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// codecvt_max_length.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc( "C");//English_Britain" );//German_Germany  
   int res = use_facet<codecvt<char, char, mbstate_t> >  
     ( loc ).max_length( );  
   wcout << res << endl;  
}  
```  
  
```Output  
1  
```  
  
##  <a name="out"></a>  codecvt::out  
 Bir dizi iç dönüştürür **CharType**harici bir dizi s **bayt**s.  
  
```  
result out(
    StateType& _State,  
    const CharType* first1,   
    const CharType* last1,  
    const CharType*& next1,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_State`  
 Üye işlev çağrıları arasında korunur dönüştürme durumu.  
  
 `first1`  
 Dönüştürülecek dizisi başına işaretçi.  
  
 `last1`  
 Dönüştürülecek bitişinde işaretçi.  
  
 `next1`  
 İlk gösteren bir işaretçi başvuru dönüştürmeden **CharType** son sonra **CharType** dönüştürülür.  
  
 `first2`  
 Dönüştürülen dizisi başına işaretçi.  
  
 `last2`  
 Dönüştürülen bitişinde işaretçi.  
  
 `next2`  
 İlk gösteren bir işaretçi başvuru dönüştürmeden **bayt** son dönüştürülen sonra **bayt**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlevi döndürür [do_out](#do_out)( `_State`, `first1`, `last1`, `next1`, `first2`, `last2`, `next2`).  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [codecvt::do_out](#do_out).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// codecvt_out.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
#include <wchar.h>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char pszExt[LEN+1];  
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";  
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );  
   char* pszNext;  
   const wchar_t* pwszNext;  
   mbstate_t state;  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
      ( loc ).out( state,  
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,  
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );  
   pszExt[wcslen( pwszInt )] = 0;  
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )  
   << "The converted string is:\n ["  
   << &pszExt[0]  
   << "]" << endl;  
}  
```  
  
```Output  
It worked: The converted string is:  
 [This is the wchar_t string to be converted.]  
```  
  
##  <a name="state_type"></a>  codecvt::state_type  
 İç ve dış temsiller arasındaki dönüştürmeler sırasında ara durumları temsil etmek için kullanılan bir karakter türü.  
  
```  
typedef StateType state_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **StateType**.  
  
##  <a name="unshift"></a>  codecvt::unshift  
 Sağlar **bayt**durumu bağımlı dönüştürmede bir dizi son karakter tamamlamak için gereken s **bayt**s.  
  
```  
result unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_State`  
 Üye işlev çağrıları arasında korunur dönüştürme durumu.  
  
 `first2`  
 Hedef aralıktaki ilk konuma yönelik işaretçi.  
  
 `last2`  
 Hedef aralık son konuma yönelik işaretçi.  
  
 `next2`  
 Hedef sırası ilk değiştirilmemiş öğe işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlevi döndürür:  
  
- **codecvt_base::Error** durumu geçersiz bir durum temsil ediyorsa.  
  
- `codecvt_base::noconv` hiçbir dönüştürme işlevi uyguluyorsa.  
  
- **codecvt_base::ok** dönüştürme başarılı olursa.  
  
- **codecvt_base::partial** hedef dönüştürme işleminin başarılı olması için yeterince büyük değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı sanal üye fonksiyonu source öğesi değiştirmeye çalıştığında **CharType**(0) içinde depolayan bir hedef dizisine [ `first2`, `last2`), sonlandırma öğesi dışında **bayt** (0). Her zaman depolar `next2` hedef sırası ilk değiştirilmemiş öğe için bir işaretçi.  
  
 `_State` Yeni bir kaynak sırası ilk dönüştürme durumunu başında temsil etmesi gerekir. İşlev saklı değerini gerektiğinde başarılı dönüştürme geçerli durumunu yansıtacak biçimde değiştirir. Genellikle, kaynak öğenin dönüştürme **CharType**(0) geçerli durumu ilk dönüştürme durumda bırakır.  
  
 Üye işlevi döndürür [do_unshift](#do_unshift)( `_State`, `first2`, `last2`, `next2` ).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<yerel ayar >](../standard-library/locale.md)   
 [Kod sayfaları](../c-runtime-library/code-pages.md)   
 [Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

