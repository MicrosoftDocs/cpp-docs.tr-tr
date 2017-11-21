---
title: "Locale sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocale/std::locale
- xlocale/std::locale::category
- xlocale/std::locale::combine
- xlocale/std::locale::name
- xlocale/std::locale::classic
- xlocale/std::locale::global
- xlocale/std::locale::operator( )
- xlocale/std::locale::facet
- xlocale/std::locale::id
dev_langs: C++
helpviewer_keywords:
- std::locale [C++]
- std::locale [C++], category
- std::locale [C++], combine
- std::locale [C++], name
- std::locale [C++], classic
- std::locale [C++], global
- std::locale [C++], facet
- std::locale [C++], id
ms.assetid: 7dd6d271-472d-4750-8fb5-ea8f55fbef62
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f53f9a32da84c450825fc61b8316593e1041784c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="locale-class"></a>locale Sınıfı
Kültüre özgü bilgileri depolayan bir yerel ayar nesnesini belirli bir yerelleştirilmiş ortamı toplu olarak kapsülleyen bir modeller kümesi olarak tanımlayan sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class locale;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir model gösteren bir işaretçidir sınıfından türetilen bir sınıftan bir nesneyi [modeli](#facet_class) ortak nesnesi biçiminde olan:  
  
```  
static locale::id id;  
```  
  
 Bu modellerin açık uçlu bir kümesini tanımlayabilirsiniz. Ayrıca, modellerin rastgele bir sayısını gösteren bir yerel ayar nesnesi oluşturabilirsiniz.  
  
 Bu modellerle önceden tanımlanmış grupları temsil [yerel ayar kategorileri](#category) işlevi tarafından standart C Kitaplığı'nda geleneksel yönetilen `setlocale`.  
  
 Kategori collate (LC_COLLATE) şu modelleri içerir:  
  
```  
collate<char>  
collate<wchar_t>  
```  
  
 Kategori ctype (LC_CTYPE) şu modelleri içerir:  
  
```  
ctype<char>  
ctype<wchar_t>  
codecvt<char, char, mbstate_t>  
codecvt<wchar_t, char, mbstate_t>  
codecvt<char16_t, char, mbstate_t>  
codecvt<char32_t, char, mbstate_t>  
```  
  
 Kategori monetary (LC_MONETARY) şu modelleri içerir:  
  
```  
moneypunct<char, false>  
moneypunct<wchar_t, false>  
moneypunct<char, true>  
moneypunct<wchar_t, true>  
money_get<char, istreambuf_iterator<char>>  
money_get<wchar_t, istreambuf_iterator<wchar_t>>  
money_put<char, ostreambuf_iterator<char>>  
money_put<wchar_t, ostreambuf_iterator<wchar_t>>  
```  
  
 Kategori numeric (LC_NUMERIC) şu modelleri içerir:  
  
```  
num_get<char, istreambuf_iterator<char>>  
num_get<wchar_t, istreambuf_iterator<wchar_t>>  
num_put<char, ostreambuf_iterator<char>>  
num_put<wchar_t, ostreambuf_iterator<wchar_t>>  
numpunct<char>  
numpunct<wchar_t>  
```  
  
 Kategori time (LC_TIME) şu modelleri içerir:  
  
```  
time_get<char, istreambuf_iterator<char>>  
time_get<wchar_t, istreambuf_iterator<wchar_t>>  
time_put<char, ostreambuf_iterator<char>>  
time_put<wchar_t, ostreambuf_iterator<wchar_t>>  
```  
  
 Kategori messages (LC_MESSAGES) şu modelleri içerir:  
  
```  
messages<char>  
messages<wchar_t>  
```  
  
 (Son kategori C standart tarafından değil ama POSIX tarafından gereklidir.)  
  
 Bu önceden tanımlanmış modellerin bazıları iostreams sınıfları tarafından sayısal değerlerin to ve from metin dizilerine dönüştürülmesini denetlemek için kullanılır.  
  
 Bir nesne sınıfı yerel ayar, bir yerel ayar adı sınıfın bir nesnesi da depolar. [dize](../standard-library/string-typedefs.md#string). Yerel ayar modeli veya bir yerel ayar nesnesi oluşturmak için bir geçersiz yerel ayar adını kullanarak sınıfın bir nesnesi oluşturur [runtime_error](../standard-library/runtime-error-class.md). Depolanan yerel ayar adı `"*"` yerel nesne C tarzı yerel ayar için tam olarak karşılık geldiğini belirli olamazsa nesnesiyle temsil. Aksi halde, yerel ayar nesnesi için standart C Kitaplığı içinde eşleşen bir yerel kurup `Loc`, çağırarak `setlocale`(LC_ALL `,` `Loc`. [ad](#name)`().c_str()`).  
  
 Bu uygulamada, statik üye işlevini de çağırabilirsiniz:  
  
```  
static locale empty();
```  
  
 Böylece, modeli olmayan bir yerel bir nesne oluşturabilirsiniz. Ayrıca, saydam bir yerel ayar olan; varsa şablon işlevleri [has_facet](../standard-library/locale-functions.md#has_facet) ve [use_facet](../standard-library/locale-functions.md#use_facet) istenen model bulunamıyor saydam yerel ayarda, bunlar ilk genel yerel başvurun ve ardından, saydam ise, Klasik yerel ayar. Bu nedenle, şunu yazabilirsiniz:  
  
```  
cout.imbue(locale::empty());
```  
  
Sonraki eklemelerin [cout](../standard-library/iostream.md#cout) genel yerel geçerli durumuna göre mediated. Şunu da yazabilirsiniz:  
  
```  
locale loc(locale::empty(),
    locale::classic(),  
    locale::numeric);

cout.imbue(loc);
```   
  
 Sayısal biçimlendirme kuralları sonraki eklemeleri için `cout` tarihleri ve para tutarlar eklemek için değiştirme kuralları genel yerel kaynakları gibi C yerel olduğu gibi aynı kalır.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[yerel ayar](#locale)|Bir yerel ayar veya yerel ayar kopyası ya da modelin veya kategorinin başka bir yerel ayardaki bir model veya kategori tarafından değiştirilen bir kopyasını oluşturur.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[Kategori](#category)|Standart model aileleri belirtmek için bit maskesi değerleri sağlayan bir tamsayı türü.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Birleştirme](#combine)|Belirtilen yerel ayardaki bir modeli hedef yerel ayara ekler.|  
|[adı](#name)|Depolanan yerel ayar adını döndürür.|  
  
### <a name="static-functions"></a>Statik işlevler  
  
|||  
|-|-|  
|[Klasik](#classic)|Statik üye işlevini klasik C yerel ayarını temsil eden yerel bir nesneye döndürür.|  
|[Genel](#global)|Varsayılan programın yerel ayarını sıfırlar.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator! =](#op_neq)|İki yerel ayarın farklı olup olmadığını sınar.|  
|[işleci)](#op_call)|İki karşılaştırır `basic_string` nesneleri.|  
|[operator ==](#op_eq_eq)|İki yerel ayarın farksız olup olmadığını sınar.|  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[modeli](#facet_class)|Tüm yerel ayar modelleri için temel sınıf görevi gören sınıf.|  
|[Kimliği](#id_class)|Üye sınıfı özellikleri, bir yerel ayardaki arama modelleri için bir dizin olarak kullanılan benzersiz bir kimlik sağlar.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
##  <a name="category"></a>Locale::category  
 Standart model aileleri belirtmek için bit maskesi değerleri sağlayan bir tamsayı türü.  
  
```  
typedef int category;  
static const int collate = LC_COLLATE;  
static const int ctype = LC_CTYPE;  
static const int monetary = LC_MONETARY;  
static const int numeric = LC_NUMERIC;  
static const int time = LC_TIME;  
static const int messages = LC_MESSAGES;  
static const int all = LC_ALL;  
static const int none = 0;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türü olan bir `int` bir bit maskesi olan ayrı öğeleri grubunu temsil edebilir türü sınıfı yerel ayar için yerel yazın veya karşılık gelen C yerel ayar kategorileri birini temsil etmek için kullanılabilir. Öğeler şunlardır:  
  
- **COLLATE**, C kategorisine LC_COLLATE karşılık gelen  
  
- **CType**, C kategorisine LC_CTYPE karşılık gelen  
  
- **para**, C kategorisine LC_MONETARY karşılık gelen  
  
- **Sayısal**, C kategorisine lc_numerıc karşılık gelen  
  
- **zaman**, C kategorisine lc_tıme karşılık gelen  
  
- **iletileri**, LC_MESSAGES POSIX kategoriye karşılık gelen  
  
 Ayrıca, iki yararlı değerler şunlardır:  
  
- **Hiçbiri**, karşılık gelen None C kategorileri  
  
- **tüm**, ilişkili tüm kategorileri LC_ALL C birleşimi  
  
 Kullanarak kategorileri rasgele bir grubu temsil edebilir `OR` giriş olarak bu sabitler ile **para** &#124; **zaman**.  
  
##  <a name="classic"></a>Locale::Classic  
 Statik üye işlevini klasik C yerel ayarını temsil eden yerel bir nesneye döndürür.  
  
```  
static const locale& classic();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 C yerel bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Klasik C yerel ayar ABD'dır İngilizce ASCII yerel olmayan Uluslararası yapılan programlarda örtük olarak kullanılan standart C Kitaplığı içinde.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// locale_classic.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "german" );  
   locale loc2 = locale::global( loc1 );  
   cout << "The name of the previous locale is: " << loc2.name( )  
        << "." << endl;  
   cout << "The name of the current locale is: " << loc1.name( )   
        << "." << endl;  
  
   if (loc2 == locale::classic( ) )  
      cout << "The previous locale was classic." << endl;  
   else  
      cout << "The previous locale was not classic." << endl;  
  
   if (loc1 == locale::classic( ) )  
      cout << "The current locale is classic." << endl;  
   else  
      cout << "The current locale is not classic." << endl;  
}  
```  
  
```Output  
The name of the previous locale is: C.  
The name of the current locale is: German_Germany.1252.  
The previous locale was classic.  
The current locale is not classic.  
```  
  
##  <a name="combine"></a>Locale::Combine  
 Belirtilen yerel ayardaki bir modeli hedef yerel ayara ekler.  
  
```  
template <class Facet>  
locale combine(const locale& Loc) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `Loc`  
 Hedef yerel ayar eklenecek modeli içeren yerel ayar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlevini değiştirir veya ekler bir yerel ayar nesnesi döndüren  **\*bu** modeli `Facet` listelenen `Loc`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// locale_combine.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main() {  
   locale loc ( "German_germany" );  
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s; it comes before z in the German alphabet  
   _TCHAR * s2 = _T("Das ist weizzz.");  
   int result1 = use_facet<collate<_TCHAR> > ( loc ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;  
  
   locale loc2 ( "C" );  
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;  
  
   locale loc3 = loc2.combine<collate<_TCHAR> > (loc);  
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;  
}  
```  
  
##  <a name="facet_class"></a>facet sınıfı  
 Tüm yerel ayar modelleri için temel sınıf görevi gören sınıf.  

```    
class facet { 
protected:    
    explicit facet(size_t _Refs = 0);
   virtual ~facet();
private:    
   facet(const facet&)
   // not defined void operator=(const facet&)
     // not defined    
};  
```  
### <a name="remarks"></a>Açıklamalar  
 Kopyalayamaz veya sınıf modeli bir nesne atama olduğunu unutmayın. Oluşturun ve sınıfından türetilen nesneleri yok `locale::facet` nesneleri uygun temel sınıf. Genellikle, bir nesne oluşturmak `_Myfac` gibi bir yerel yapısı oluştururken model türetilen **localeloc**( `locale::classic`(), **yeni**`_Myfac`);  
  
 Böyle durumlarda, temel sınıf modeli Oluşturucusu sıfır olmalıdır `_Refs` bağımsız değişkeni. Nesne artık gerekli olmadığında silinir. Sıfır olmayan bir _ bu nedenle, sağladığınız *Refs* bağımsız değişkeni yalnızca ele burada nesnesinin ömrü sorumluluğunu nadir durumlarda.  
  
##  <a name="global"></a>Locale::Global  
 Program için varsayılan yerel ayar sıfırlar. C ve C++ için genel yerel etkiler.  
  
```  
static locale global(const locale& Loc);
```  
  
### <a name="parameters"></a>Parametreler  
 `Loc`  
 Varsayılan yerel ayar program tarafından kullanılmak üzere yerel ayar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan yerel ayar sıfırlamadan önceki yerel ayar.  
  
### <a name="remarks"></a>Açıklamalar  
 Program başlatma sırasında genel yerel Klasik yerel ile aynıdır. `global()` İşlev çağrıları `setlocale( LC_ALL, loc.name. c_str())` standart C Kitaplığı'nda eşleşen bir yerel ayar oluşturmak için.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// locale_global.cpp  
// compile by using: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main( )  
{  
   locale loc ( "German_germany" );  
   locale loc1;  
   cout << "The initial locale is: " << loc1.name( ) << endl;  
   locale loc2 = locale::global ( loc );  
   locale loc3;  
   cout << "The current locale is: " << loc3.name( ) << endl;  
   cout << "The previous locale was: " << loc2.name( ) << endl;  
}  
```  
  
```Output  
The initial locale is: C  
The current locale is: German_Germany.1252  
The previous locale was: C  
```  
  
##  <a name="id_class"></a>id sınıfı  
 Üye sınıfı özellikleri, bir yerel ayardaki arama modelleri için bir dizin olarak kullanılan benzersiz bir kimlik sağlar.  
  
sınıf kimliği {korumalı: id(); özel: id(const id&) / / void işleç tanımlanmamış =(const id&) / / tanımlanmamış};  
  
### <a name="remarks"></a>Açıklamalar  
 Statik üye nesne her benzersiz yerel modeli tarafından gerekli üye sınıfı açıklar. Kopyalayamaz veya sınıfın bir nesnesi atama, Not **kimliği**.  
  
##  <a name="locale"></a>Locale::Locale  
 Bir yerel ayar veya yerel ayar kopyası ya da modelin veya kategorinin başka bir yerel ayardaki bir model veya kategori tarafından değiştirilen bir kopyasını oluşturur.  
  
```  
locale();

explicit locale(const char* Locname, category Cat = all);
explicit locale(const string& Locname);
locale( const locale& Loc);
locale(const locale& Loc, const locale& Other, category Cat);
locale(const locale& Loc, const char* Locname, category Cat);

template <class Facet>  
locale(const locale& Loc, const Facet* Fac);
```  
  
### <a name="parameters"></a>Parametreler  
 `Locname`  
 Yerel ayar adı.  
  
 `Loc`  
 Yeni yerel oluştururken kopyalanacak yerel ayar.  
  
 `Other`  
 Yerel ayar çıkarılacağı bir kategori seçin.  
  
 `Cat`  
 Oluşturulan yerel atanması kategorisi.  
  
 `Fac`  
 Oluşturulan yerel değiştirilecek model.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucusu genel yerel eşleşecek şekilde nesnesini başlatır. Yerel ayar adı ile tutarlı davranışı sağlamak için tüm yerel ayar kategorileri ikinci ve üçüncü oluşturucular başlatma `Locname`. Kalan oluşturucuları kopyalama `Loc`, belirtilen özel durum dışında:  
  
 `locale(const locale& Loc, const locale& Other, category Cat);`  
  
 gelen değiştirir `Other` bu modelleri için hangi C C kategoriye karşılık gelen & `Cat` sıfır olmayan bir değer değil.  
  
 `locale(const locale& Loc, const char* Locname, category Cat);`  
  
 `locale(const locale& Loc, const string& Locname, category Cat);`  
  
 gelen değiştirir `locale(Locname, _All)` bu modelleri için hangi C C kategoriye karşılık gelen & `Cat` sıfır olmayan bir değer değil.  
  
 `template<class Facet> locale(const locale& Loc, Facet* Fac);`  
  
 değiştirir (veya ekler) `Loc` modeli `Fac`, `Fac` null işaretçi değil.  
  
 Yerel ayar adları, `Locname` null işaretçi ya da başka nedenle geçersiz işlev oluşturur [runtime_error](../standard-library/runtime-error-class.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// locale_locale.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main( ) {  
  
   // Second constructor  
   locale loc ( "German_germany" );  
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet  
   _TCHAR * s2 = _T("Das ist weizzz.");  
   int result1 = use_facet<collate<_TCHAR> > ( loc ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;  
  
   // The first (default) constructor  
   locale loc2;  
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;  
  
   // Third constructor  
   locale loc3 (loc2,loc, _M_COLLATE );  
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;  
  
   // Fourth constructor  
   locale loc4 (loc2, "German_Germany", _M_COLLATE );  
   int result4 = use_facet<collate<_TCHAR> > ( loc4 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc4 ) << result4 << endl;  
}  
```  
  
##  <a name="name"></a>Locale::Name  
 Depolanan yerel ayar adını döndürür.  
  
```  
string name() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerel ad verip bir dize.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// locale_name.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "german" );  
   locale loc2 = locale::global( loc1 );  
   cout << "The name of the previous locale is: "   
        << loc2.name( ) << "." << endl;  
   cout << "The name of the current locale is: "   
        << loc1.name( ) << "." << endl;  
}  
```  
  
```Output  
The name of the previous locale is: C.  
The name of the current locale is: German_Germany.1252.  
```  
  
##  <a name="op_neq"></a>Locale::operator! =  
 İki yerel ayarın farklı olup olmadığını sınar.  
  
```  
bool operator!=(const locale& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Yerel ayarlar için eşitsizlik sınanacak biri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir Boole değeri **true** yerel ayarlar aynı yerel; kopyalarını değilse **false** yerel ayarlar aynı yerel kopyasını varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Başka bir kopyasını ise aynı yerel olmaları durumunda ya da aynı adlara sahip iki yerel ayarı eşit.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// locale_op_ne.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "German_Germany" );  
   locale loc2( "German_Germany" );  
   locale loc3( "English" );  
  
   if ( loc1 != loc2 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc2 (" << loc2.name( ) << ") are not equal." << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc2 (" << loc2.name( ) << ") are equal." << endl;  
  
   if ( loc1 != loc3 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc3 (" << loc3.name( ) << ") are not equal." << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc3 (" << loc3.name( ) << ") are equal." << endl;  
}  
```  
  
```Output  
locales loc1 (German_Germany.1252) and  
 loc2 (German_Germany.1252) are equal.  
locales loc1 (German_Germany.1252) and  
 loc3 (English_United States.1252) are not equal.  
```  
  
##  <a name="op_call"></a>Locale:: operator()  
 İki karşılaştırır `basic_string` nesneleri.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Sol dizesi.  
  
 `right`  
 Sağ dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlevi döndürür:  
  
-   ilk dizi ikinci dizisi sayısından az karşılaştırır, -1.  
  
-   İkinci sırası ilk dizisi sayısından az karşılaştırır, + 1.  
  
-   0 sıraları eşdeğerdir.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini etkili bir şekilde çalışır:  
  
```  
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) < 0);
```  
  
 Bu nedenle, bir işlev nesnesi olarak yerel ayar nesnesini kullanabilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// locale_op_compare.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
int main( )   
{  
   using namespace std;  
   wchar_t *sa = L"ztesting";  
   wchar_t *sb = L"\0x00DFtesting";  
   basic_string<wchar_t> a( sa );  
   basic_string<wchar_t> b( sb );  
  
   locale loc( "German_Germany" );  
   cout << loc( a,b ) << endl;  
  
   const collate<wchar_t>& fac = use_facet<collate<wchar_t> >( loc );  
   cout << ( fac.compare( sa, sa + a.length( ),  
       sb, sb + b.length( ) ) < 0) << endl;  
}  
```  
  
```Output  
0  
0  
```  
  
##  <a name="op_eq_eq"></a>Locale::operator ==  
 İki yerel ayarın farksız olup olmadığını sınar.  
  
```  
bool operator==(const locale& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Eşitlik için test edilmesi için yerel ayarları biri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir Boole değeri **true** yerel ayarlar aynı yerel; kopyalarını varsa **false** yerel ayarlar aynı yerel kopyasını değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Başka bir kopyasını ise aynı yerel olmaları durumunda ya da aynı adlara sahip iki yerel ayarı eşit.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// locale_op_eq.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "German_Germany" );  
   locale loc2( "German_Germany" );  
   locale loc3( "English" );  
  
   if ( loc1 == loc2 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc2 (" << loc2.name( ) << ") are equal."   
      << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc2 (" << loc2.name( ) << ") are not equal."   
      << endl;  
  
   if ( loc1 == loc3 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc3 (" << loc3.name( ) << ") are equal."   
      << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc3 (" << loc3.name( ) << ") are not equal."   
      << endl;  
}  
```  
  
```Output  
locales loc1 (German_Germany.1252)  
 and loc2 (German_Germany.1252) are equal.  
locales loc1 (German_Germany.1252)  
 and loc3 (English_United States.1252) are not equal.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<locale>](../standard-library/locale.md)   
 [Kod sayfaları](../c-runtime-library/code-pages.md)   
 [Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

