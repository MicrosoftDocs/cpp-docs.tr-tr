---
title: "numpunct sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xlocnum/std::numpunct
- xlocnum/std::numpunct::char_type
- xlocnum/std::numpunct::string_type
- xlocnum/std::numpunct::decimal_point
- xlocnum/std::numpunct::do_decimal_point
- xlocnum/std::numpunct::do_falsename
- xlocnum/std::numpunct::do_grouping
- xlocnum/std::numpunct::do_thousands_sep
- xlocnum/std::numpunct::do_truename
- xlocnum/std::numpunct::falsename
- xlocnum/std::numpunct::grouping
- xlocnum/std::numpunct::thousands_sep
- xlocnum/std::numpunct::truename
dev_langs:
- C++
helpviewer_keywords:
- std::numpunct [C++]
- std::numpunct [C++], char_type
- std::numpunct [C++], string_type
- std::numpunct [C++], decimal_point
- std::numpunct [C++], do_decimal_point
- std::numpunct [C++], do_falsename
- std::numpunct [C++], do_grouping
- std::numpunct [C++], do_thousands_sep
- std::numpunct [C++], do_truename
- std::numpunct [C++], falsename
- std::numpunct [C++], grouping
- std::numpunct [C++], thousands_sep
- std::numpunct [C++], truename
ms.assetid: 73fb93cc-ac11-4c98-987c-bfa6267df596
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c2613f3dd4aa03b591f1edcbb10576cd5e71fdc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="numpunct-class"></a>numpunct Sınıfı
Türü dizilerini açıklamak için yerel bir model hizmet verebilir bir nesneyi tanımlayan bir şablon sınıfı `CharType` biçimlendirme ve noktalama sayısal ve Boole ifadelerin hakkında bilgi göstermek için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class CharType>  
class numpunct : public locale::facet;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `CharType`  
 Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Benzersiz bir pozitif değer saklı değerini erişmek için ilk deneme depolar **kimliği.**  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[numpunct](#numpunct)|Nesne türü Oluşturucusu `numpunct`.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|  
|[string_type](#string_type)|Tür karakterleri içeren bir dize açıklayan türü `CharType`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[decimal_point](#decimal_point)|Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.|  
|[do_decimal_point](#do_decimal_point)|Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.|  
|[do_falsename](#do_falsename)|Bir korumalı metin gösterimini değeri kullanılacak bir dize döndürecek şekilde adlı sanal üye işlevi `false`.|  
|[do_grouping](#do_grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürmek için çağrılan korumalı sanal üye işlevi.|  
|[do_thousands_sep](#do_thousands_sep)|Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.|  
|[do_truename](#do_truename)|Bir korumalı metin gösterimini değeri kullanılacak bir dize döndürecek şekilde adlı sanal üye işlevi `true`.|  
|[falsename](#falsename)|Metin gösterimini değeri kullanılacak bir dize döndürür `false`.|  
|[Gruplandırma](#grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.|  
|[thousands_sep](#thousands_sep)|Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.|  
|[truename](#truename)|Metin gösterimini değeri kullanılacak bir dize döndürür `true`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
##  <a name="char_type"></a>  numpunct::char_type  
 Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **CharType.**  
  
##  <a name="decimal_point"></a>  numpunct::decimal_point  
 Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.  
  
```  
CharType decimal_point() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ondalık noktası olarak kullanmak için bir yerel ayarlara özgü öğesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [do_decimal_point](#do_decimal_point).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// numpunct_decimal_point.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet <numpunct <char> >( loc);  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="do_decimal_point"></a>  numpunct::do_decimal_point  
 Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.  
  
```  
virtual CharType do_decimal_point() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ondalık noktası olarak kullanmak için bir yerel ayarlara özgü öğesi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [decimal_point](#decimal_point), sanal üye fonksiyonu tarafından çağrılır burada `decimal_point`.  
  
##  <a name="do_falsename"></a>  numpunct::do_falsename  
 Korumalı sanal üye fonksiyonu değeri metin gösterimi olarak kullanmak için bir dizi döndürür **false**.  
  
```  
virtual string_type do_falsename() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin gösterimini değeri kullanılacak bir dizisini içeren bir dize **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini değeri temsil etmek için "false" dizesini döndürür **false** tüm bölgelerde.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [falsename](#falsename), sanal üye fonksiyonu tarafından çağrılır burada `falsename`.  
  
##  <a name="do_grouping"></a>  numpunct::do_grouping  
 Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürmek için çağrılan korumalı sanal üye işlevi.  
  
```  
virtual string do_grouping() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sayı Ondalık ayırıcının solundaki nasıl gruplandırılacağını belirlemek için bir yerel ayarlara özgü kuralı.  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı sanal üye işlevi herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür. Aynı kodlamadır **lconv::grouping**.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [gruplandırma](#grouping), sanal üye fonksiyonu tarafından çağrılır burada **gruplandırma**.  
  
##  <a name="do_thousands_sep"></a>  numpunct::do_thousands_sep  
 Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.  
  
```  
virtual CharType do_thousands_sep() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı sanal üye fonksiyonu yerele özel öğe türü döndürür **CharType** herhangi Ondalık ayırıcının solundaki Grup ayırıcı olarak kullanılacak.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [thousands_sep](#thousands_sep), sanal üye fonksiyonu tarafından çağrılır burada `thousands_sep`.  
  
##  <a name="do_truename"></a>  numpunct::do_truename  
 Bir korumalı metin gösterimini değeri kullanılacak bir dize döndürecek şekilde adlı sanal üye işlevi **doğru**.  
  
```  
virtual string_type do_truename() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Metin gösterimini değeri kullanılacak bir dize **doğru**.  
  
 Tüm yerel değerin temsil etmek için "true" içeren bir dize döndürecek **doğru**.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [truename](#truename), sanal üye fonksiyonu tarafından çağrılır burada `truename`.  
  
##  <a name="falsename"></a>  numpunct::falsename  
 Metin gösterimini değeri kullanılacak bir dize döndürür **false**.  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir dizi içeren bir dize **CharType**değeri metin gösterimi olarak kullanmak için s **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini değeri temsil etmek için "false" dizesini döndürür **false** tüm bölgelerde.  
  
 Üye işlevi döndürür [do_falsename](#do_falsename).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// numpunct_falsename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct <char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2( "French" );  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >(loc2);  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
##  <a name="grouping"></a>  numpunct::Grouping  
 Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.  
  
```  
string grouping() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sayı Ondalık ayırıcının solundaki nasıl gruplandırılacağını belirlemek için bir yerel ayarlara özgü kuralı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [do_grouping](#do_grouping).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// numpunct_grouping.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany");  
  
   const numpunct <char> &npunct =   
       use_facet < numpunct <char> >( loc );  
   for (unsigned int i = 0; i < npunct.grouping( ).length( ); i++)  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(npunct.grouping ( )[i])   
           << endl;  
   }  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
```  
  
##  <a name="numpunct"></a>  numpunct::numpunct  
 Nesne türü Oluşturucusu `numpunct`.  
  
```  
explicit numpunct(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Refs`  
 Bellek yönetimi nesnesinin türünü belirtmek için kullanılan tamsayı değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Olası değerler için `_Refs` parametre ve bunların anlamlı:  
  
-   0: nesne ömrü onu içeren yerel ayarları tarafından yönetilir.  
  
-   1: nesne ömrü el ile yönetilmesi gerekir.  
  
-   \> 1: Bu değerleri tanımlanmamış.  
  
 Yok Edicisi korunduğu için hiçbir doğrudan örnekler mümkündür.  
  
 Oluşturucu temel nesnesiyle başlatır **locale::**[modeli](../standard-library/locale-class.md#facet_class)( `_Refs`).  
  
##  <a name="string_type"></a>  numpunct::string_type  
 Tür karakterleri içeren bir dize açıklayan türü **CharType**.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [basic_string](../standard-library/basic-string-class.md) olan nesneleri noktalama sıraları kopyalarını depolayabilirsiniz.  
  
##  <a name="thousands_sep"></a>  numpunct::thousands_sep  
 Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.  
  
```  
CharType thousands_sep() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir yerel ayarlara özgü öğesi olarak kullanılacak ayırıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [do_thousands_sep](#do_thousands_sep).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// numpunct_thou_sep.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet < numpunct < char > >( loc );  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="truename"></a>  numpunct::truename  
 Metin gösterimini değeri kullanılacak bir dize döndürür **doğru**.  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin gösterimini değeri kullanılacak bir dize **doğru**.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [do_truename](#do_truename).  
  
 Tüm yerel değerin temsil etmek için "true" içeren bir dize döndürecek **doğru**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// numpunct_truename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct < char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2("French");  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >( loc2 );  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<yerel ayar >](../standard-library/locale.md)   
 [facet sınıfı](../standard-library/locale-class.md#facet_class)   
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

