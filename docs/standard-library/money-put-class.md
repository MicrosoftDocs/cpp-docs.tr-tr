---
title: "money_put sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocmon/std::money_put
- xlocmon/std::money_put::char_type
- xlocmon/std::money_put::iter_type
- xlocmon/std::money_put::string_type
- xlocmon/std::money_put::do_put
- xlocmon/std::money_put::put
dev_langs: C++
helpviewer_keywords:
- std::money_put [C++]
- std::money_put [C++], char_type
- std::money_put [C++], iter_type
- std::money_put [C++], string_type
- std::money_put [C++], do_put
- std::money_put [C++], put
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd47afe55f1e2625dfe216afd6ef98cbcba7b21f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="moneyput-class"></a>money_put Sınıfı
Şablon sınıfı parasal değerleri denetim dönüşümleri dizilerini türü için bir yerel ayar model olarak hizmet verebilir bir nesneyi tanımlayan `CharType`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class CharType,  
    class OutputIterator = ostreambuf_iterator<CharType>>  
class money_put : public locale::facet;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `CharType`  
 Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.  
  
 `OutputIterator`  
 Parasal koyma işlevlerinin kendi çıktılarının yazılacağı yineleyici türü.  
  
## <a name="remarks"></a>Açıklamalar  
 Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Benzersiz bir pozitif değer saklı değerini erişmek için ilk deneme depolar **kimliği.**  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[money_put](#money_put)|Nesne türü Oluşturucusu `money_put`.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|  
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|  
|[STRING_TYPE](#string_type)|Tür karakterleri içeren bir dize açıklayan türü `CharType`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[do_put](#do_put)|Bir sayı ya da dizeyi parasal bir değeri temsil eden bir karakter dizisine dönüştürmek için çağrılan bir sanal işlev.|  
|[yerleştirme](#put)|Bir sayı ya da dizeyi parasal bir değeri temsil eden bir karakter dizisine dönüştürür.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
##  <a name="char_type"></a>money_put::char_type  
 Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **CharType**.  
  
##  <a name="do_put"></a>money_put::do_put  
 Bir sayı ya da dizeyi parasal bir değeri temsil eden bir karakter dizisine dönüştürmek için çağrılan bir sanal işlev.  
  
```  
virtual iter_type do_put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,   
    const string_type& val) const;

 
virtual iter_type do_put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,  
    long double val) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `next`  
 Eklenen dizenin ilk öğe adresleme yineleyici.  
  
 `_Intl`  
 Para birimi simgesini sırayla beklenen türünü gösteren bir Boole değeri: **true** uluslararası, **false** yurtiçi durumunda.  
  
 `_Iosbase`  
 Bir biçim hangi bayrak kümesi para birimi simgesini isteğe bağlıdır; olduğunu gösterdiğinde Aksi takdirde gereklidir  
  
 `_Fill`  
 Aralığı için kullanılan bir karakter.  
  
 `val`  
 Dönüştürülecek bir dize nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çıktı yineleyici adresleri son öğenin ötesinde konumu bir üretilen.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sanal korumalı üye fonksiyonu başlangıç sıralı öğeleri oluşturur `next` para çıkış alandan üretmek için [STRING_TYPE](#string_type) nesne `val`. Tarafından denetlenen dizisi `val` isteğe bağlı olarak bir eksi miktarını temsil eden işareti (-), öncesinde bir veya daha fazla ondalık basamak ile başlamalıdır. Oluşturulan para çıktı alanı ötesinde ilk öğe belirleme yineleyici işlevi döndürür.  
  
 İkinci sanal korumalı üye fonksiyonu, birinci ile aynı şekilde davranır hariç, BT'nin etkili bir şekilde ilk dönüştürür `val` isteğe bağlı olarak bir eksi işaretiyle öncesinde ondalık basamak dizisi sonra o sırada yukarıdaki dönüştürür.  
  
 Para çıktı alanı biçimi tarafından belirlenen [yerel model](../standard-library/locale-class.md#facet_class) (etkin) çağrı tarafından döndürülen fac [use_facet](../standard-library/locale-functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md) \< **CharType**, **uluslararası**>> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)).  
  
 Özellikle:  
  
- **Fac**. [pos_format](../standard-library/moneypunct-class.md#pos_format) alanının bileşenleri için negatif olmayan bir değer oluşturulur sırasını belirler.  
  
- **Fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format) alanının bileşenleri için negatif bir değer oluşturulur sırasını belirler.  
  
- **Fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) bir para birimi simgesi oluşturmak için öğelerin sırasını belirler.  
  
- **Fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) için pozitif bir oturum oluşturmak için öğeleri sırasını belirler.  
  
- **Fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign) negatif bir oturum oluşturmak için öğelerin sırasını belirler.  
  
- **Fac**. [Gruplandırma](../standard-library/moneypunct-class.md#grouping) basamak herhangi Ondalık ayırıcının solundaki nasıl gruplandırılacağını belirler.  
  
- **Fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep) herhangi Ondalık ayırıcının sol tarafındaki basamak grupları ayıran öğesi belirler.  
  
- **Fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point) tamsayı basamak herhangi kesir rakamları ayıran öğesi belirler.  
  
- **Fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits) herhangi bir ondalık ayırıcısı sağındaki önemli kesir basamak sayısını belirler.  
  
 Varsa oturum dize ( **fac**. `negative_sign`veya **fac**. `positive_sign`) sahip birden fazla öğesi, yalnızca ilk öğesi oluşturulduğu eşit öğesi **money_base::sign** biçimi desende görüntülenir ( **fac**. `neg_format`veya **fac**. `pos_format`). Kalan öğeler para çıktı alanı sonunda üretilir.  
  
 Varsa **iosbase**. [bayrakları](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase) sıfır olmayan, olan dize **fac**. `curr_symbol`oluşturulduğu eşit öğesi **money_base::symbol** biçimi desende görüntülenir. Aksi takdirde, para birimi simgesini oluşturulur.  
  
 Hiçbir gruplandırma kısıtlamaları tarafından uygulanan varsa **fac**. **Gruplandırma** (ilk öğe CHAR_MAX değeri varsa), ardından hiçbir örneği **fac**. `thousands_sep`para çıktı alanı değeri bölümünde oluşturulan (burada eşit öğesi **money_base::value** biçimi desende görünür). Varsa **fac**. `frac_digits`sıfır, sonra hiçbir örneğinin **fac**. `decimal_point`ondalık basamak oluşturulur. Aksi takdirde, sonuçta elde edilen para çıktı alanı düşük düzey yerleştirir **fac**. `frac_digits`ondalık konumun sağında ondalık basamağa.  
  
 Doldurma oluşur olması durumunda dışında herhangi bir sayısal çıktı alan ettirilmesi **iosbase**. **bayrakları** & **iosbase**. [iç](../standard-library/ios-functions.md#internal) sıfır dışında her iç doldurma olduğu oluşturulduğu eşit öğesi **money_base::space** görünüyorsa biçimi desende görüntülenir. Aksi halde, iç doldurma önce oluşturulan sıralı oluşur. Doldurma karakteri **dolgu**.  
  
 İşlev çağrıları **iosbase**. **Genişlik**alan genişliği sıfırlamak için (0).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [put](#put), sanal üye fonksiyonu tarafından çağrılır burada **put**.  
  
##  <a name="iter_type"></a>money_put::iter_type  
 Bir çıkış yineleyiciyi açıklayan tür.  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **OutputIterator.**  
  
##  <a name="money_put"></a>money_put::money_put  
 Nesne türü Oluşturucusu `money_put`.  
  
```  
explicit money_put(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Refs`  
 Bellek yönetimi nesnesinin türünü belirtmek için kullanılan tamsayı değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Olası değerler için `_Refs` parametre ve bunların anlamlı:  
  
-   0: nesne ömrü onu içeren yerel ayarları tarafından yönetilir.  
  
-   1: nesne ömrü el ile yönetilmesi gerekir.  
  
-   \>1: Bu değerleri tanımlanmamış.  
  
 Yok Edicisi korunduğu için hiçbir doğrudan örnekler mümkündür.  
  
 Oluşturucu temel nesnesiyle başlatır **locale::**[modeli](../standard-library/locale-class.md#facet_class)( `_Refs`).  
  
##  <a name="put"></a>money_put::Put  
 Bir sayı ya da dizeyi parasal bir değeri temsil eden bir karakter dizisine dönüştürür.  
  
```  
iter_type put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,   
    const string_type& val) const;

 
iter_type put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,  
    long double val) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `next`  
 Eklenen dizenin ilk öğe adresleme yineleyici.  
  
 `_Intl`  
 Para birimi simgesini sırayla beklenen türünü gösteren bir Boole değeri: **true** uluslararası, **false** yurtiçi durumunda.  
  
 `_Iosbase`  
 Bir biçim hangi bayrak kümesi para birimi simgesini isteğe bağlıdır; olduğunu gösterdiğinde Aksi takdirde gereklidir  
  
 `_Fill`  
 Aralığı için kullanılan bir karakter.  
  
 `val`  
 Dönüştürülecek bir dize nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çıktı yineleyici adresleri son öğenin ötesinde konumu bir üretilen.  
  
### <a name="remarks"></a>Açıklamalar  
 Her iki üye işlevleri dönmek [do_put](#do_put)( `next`, `_Intl`, `_Iosbase`, `_Fill`, `val`).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// money_put_put.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
//   locale loc( "german_germany" );  
   locale loc( "english_canada" );  
   basic_stringstream<char> psz, psz2;  
   ios_base::iostate st = 0;  
  
   psz2.imbue( loc );  
   psz2.flags( psz2.flags( )|ios_base::showbase ); // force the printing of the currency symbol  
   use_facet < money_put < char > >(loc).put(basic_ostream<char>::_Iter( psz2.rdbuf( ) ), true, psz2, st, 100012);  
   if (st & ios_base::failbit)  
      cout << "money_put( ) FAILED" << endl;  
   else  
      cout << "money_put( ) = \"" << psz2.rdbuf( )->str( ) <<"\""<< endl;     
  
   st = 0;  
};  
```  
  
```Output  
money_put( ) = "CAD1,000.12"  
```  
  
##  <a name="string_type"></a>money_put::string_type  
 Tür karakterleri içeren bir dize açıklayan türü **CharType**.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [basic_string](../standard-library/basic-string-class.md) olan nesneleri kaynak serisinden öğelerin sıralarının depolayabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<yerel ayar >](../standard-library/locale.md)   
 [facet sınıfı](../standard-library/locale-class.md#facet_class)   
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

