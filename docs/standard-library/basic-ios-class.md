---
title: "basic_ios sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ios/std::basic_ios
- ios/std::basic_ios::char_type
- ios/std::basic_ios::int_type
- ios/std::basic_ios::off_type
- ios/std::basic_ios::pos_type
- ios/std::basic_ios::traits_type
- ios/std::basic_ios::bad
- ios/std::basic_ios::clear
- ios/std::basic_ios::copyfmt
- ios/std::basic_ios::eof
- ios/std::basic_ios::exceptions
- ios/std::basic_ios::fail
- ios/std::basic_ios::fill
- ios/std::basic_ios::good
- ios/std::basic_ios::imbue
- ios/std::basic_ios::init
- ios/std::basic_ios::move
- ios/std::basic_ios::narrow
- ios/std::basic_ios::rdbuf
- ios/std::basic_ios::rdstate
- ios/std::basic_ios::set_rdbuf
- ios/std::basic_ios::setstate
- ios/std::basic_ios::swap
- ios/std::basic_ios::tie
- ios/std::basic_ios::widen
- ios/std::basic_ios::explicit operator bool
dev_langs: C++
helpviewer_keywords:
- std::basic_ios [C++]
- std::basic_ios [C++], char_type
- std::basic_ios [C++], int_type
- std::basic_ios [C++], off_type
- std::basic_ios [C++], pos_type
- std::basic_ios [C++], traits_type
- std::basic_ios [C++], bad
- std::basic_ios [C++], clear
- std::basic_ios [C++], copyfmt
- std::basic_ios [C++], eof
- std::basic_ios [C++], exceptions
- std::basic_ios [C++], fail
- std::basic_ios [C++], fill
- std::basic_ios [C++], good
- std::basic_ios [C++], imbue
- std::basic_ios [C++], init
- std::basic_ios [C++], move
- std::basic_ios [C++], narrow
- std::basic_ios [C++], rdbuf
- std::basic_ios [C++], rdstate
- std::basic_ios [C++], set_rdbuf
- std::basic_ios [C++], setstate
- std::basic_ios [C++], swap
- std::basic_ios [C++], tie
- std::basic_ios [C++], widen
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0558bd962d8f646cc599ba604dbe749f5a02138b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="basicios-class"></a>basic_ios Sınıfı
Şablon sınıfı için her iki giriş akışları ortak depolama ve üye işlevleri açıklanmaktadır (şablon sınıfının [basic_istream](../standard-library/basic-istream-class.md)) ve çıkış akışları (şablon sınıfının [basic_ostream](../standard-library/basic-ostream-class.md)), bağlıdır Şablon parametreleri. (Sınıf [ios_base](../standard-library/ios-base-class.md) ortak ve şablon parametreleri bağımlı ne olduğunu açıklar.) Sınıfın bir nesnesi **basic_ios\<Elem sınıfı, nitelikler sınıf >** yardımcı türdeki öğeleri olan bir akış denetim **Elem**, olan karakter nitelikler sınıfı tarafından belirlenir  **Nitelikler**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
 
template <class Elem, class Traits>  
class basic_ios : public ios_base  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Elem`  
 Bir tür.  
  
 `Traits`  
 Türünde bir değişken `char_traits`.  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi **basic_ios\<Elem sınıfı, nitelikler sınıf >** depolar:  
  
-   Bir nesne türü için bir bağ işaretçi [basic_istream](../standard-library/basic-istream-class.md)**\<Elem, nitelikler >**.  
  
-   Bir nesne türü için bir Akış Arabellek işaretçi [basic_streambuf](../standard-library/basic-streambuf-class.md)**\<Elem, nitelikler >**.  
  
- [Biçimlendirme bilgilerini](../standard-library/ios-base-class.md).  
  
- [Akış durum bilgilerini](../standard-library/ios-base-class.md) temel nesne türü olarak [ios_base](../standard-library/ios-base-class.md).  
  
-   Türünde bir nesne bir dolgu karakter `char_type`.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[basic_ios](#basic_ios)|Yapıları `basic_ios` sınıfı.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[char_type](#char_type)|Şablon parametresi için bir eş anlamlı `Elem`.|  
|[int_type](#int_type)|Eşanlamlısı `Traits::int_type`.|  
|[off_type](#off_type)|Eşanlamlısı `Traits::off_type`.|  
|[pos_type](#pos_type)|Eşanlamlısı `Traits::pos_type`.|  
|[traits_type](#traits_type)|Şablon parametresi için bir eş anlamlı `Traits`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[hatalı](#bad)|Akışı arabelleğe bütünlüğünü kaybı gösterir.|  
|[Temizle](#clear)|Tüm hata bayrakları temizler.|  
|[copyfmt](#copyfmt)|Bayrakları bir akıştan başka bir konuma kopyalar.|  
|[EOF](#eof)|Bir akışın sonuna ulaşıldı olmadığını gösterir.|  
|[özel durumlar](#exceptions)|Akış tarafından hangi özel durum atılır gösterir.|  
|[başarısız](#fail)|Geçerli bir alan bir akıştan ayıklamak için başarısız olduğunu gösterir.|  
|[doldurma](#fill)|Metin akış olarak kadar geniş olmadığında kullanılacak karakter döndürür veya belirtir.|  
|[iyi](#good)|Akış iyi durumda olduğunu gösterir.|  
|[imbue](#imbue)|Yerel olarak değiştirir.|  
|[Init](#init)|Tarafından çağrılır `basic_ios` oluşturucular.|  
|[taşıma](#move)|Geçerli nesneye parametre akışı arabelleğe işaretçi dışındaki tüm değerleri taşır.|  
|[daraltma](#narrow)|Eşdeğer char bulur bir verilen `char_type`.|  
|[rdbuf](#rdbuf)|Belirtilen arabellek yollar akış.|  
|[rdstate](#rdstate)|Bit bayrakları için durumunu okur.|  
|[set_rdbuf](#set_rdbuf)|Bu akış nesne için Okuma arabelleği olması için Akış Arabellek atar.|  
|[setstate](#setstate)|Ek bayrakları ayarlar.|  
|[değiştirme](#swap)|Bu değerler alış verişleri `basic_ios` kişiler başka bir nesne `basic_ios` nesne. Akış Arabellek işaretçiler takas değil.|  
|[tie](#tie)|Bu bir akış önce başka bir akış işlenen sağlar.|  
|[widen](#widen)|Eşdeğer bulur `char_type` verilen char için.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[Açık işleç bool değeri](#op_bool)|Kullanılmasına bir `basic_ios` nesnesinin bir `bool`. Otomatik tür dönüştürme ortak, istenmeyen yan etkileri önlemek için devre dışı bırakılır.|  
|[işleç hükümsüz *](#op_void_star)|Akış iyi olup olmadığını gösterir.|  
|[işleci!](#op_not)|Akış bozuk olup olmadığını gösterir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<ios >  
  
 **Namespace:** std  
  
##  <a name="bad"></a>basic_ios::bad  
 Akışı arabelleğe bütünlüğünü kaybı gösterir  
  
```  
bool bad() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsa `rdstate & badbit` sıfır olmayan; Aksi takdirde `false`.  
  
 Daha fazla bilgi için `badbit`, bkz: [ios_base::iostate](../standard-library/ios-base-class.md#iostate).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_ios_bad.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( void )  
{  
  using namespace std;  
  bool b = cout.bad( );  
  cout << boolalpha;  
  cout << b << endl;  
    
  b = cout.good( );  
  cout << b << endl;  
}  
  
```  
  
##  <a name="basic_ios"></a>basic_ios::basic_ios  
 Basic_ios sınıfı oluşturur.  
  
```   
explicit basic_ios(basic_streambuf<Elem,  Traits>* sb);
basic_ios();
```  
  
### <a name="parameters"></a>Parametreler  
 `sb`  
 Giriş veya çıkış öğeleri depolamak için standart bir arabellek.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu çağırarak üye nesnelerine başlatır [init](#init)(_ *Sb*). İkinci (korumalı) Oluşturucu kendi üyesi başlatılmadı nesneleri bırakır. Sonraki çağrı **init** güvenle yok önce nesne başlatması gerekir.  
  
##  <a name="char_type"></a>basic_ios::char_type  
 Şablon parametresi için bir eş anlamlı **Elem**.  
  
```   
typedef Elem char_type;  
```  
  
##  <a name="clear"></a>basic_ios::Clear  
 Tüm hata bayrakları temizler.  
  
```   
void clear(iostate state = goodbit, bool reraise = false); 
void clear(io_state state);
```  
  
### <a name="parameters"></a>Parametreler  
 `state`(isteğe bağlı)  
 Tüm bayraklar temizledikten sonra ayarlamak istediğiniz bayraklar. Varsayılan olarak `goodbit`.  
  
 `reraise`(isteğe bağlı)  
 Özel durum yeniden yükseltilmiş olup olmayacağını belirtir. Varsayılan olarak `false` (özel durum yeniden oluşturmaz).  
  
### <a name="remarks"></a>Açıklamalar  
 Bayraklar **goodbit**, **failbit**, **eofbit**, ve **badbit**. Bu bayrakların ile test [iyi](#good), [hatalı](#bad), [eof](#eof), ve [başarısız](#fail)  
  
 Üye işlevi saklı akış durum bilgileri ile değiştirir:  
  
 `state`&#124; `(` [rdbuf](#rdbuf) ! = 0 **goodbit** : **badbit**)  
  
 Varsa `state`  **&**  [özel durumları](#exceptions) olan sıfır olmayan, bunu daha sonra sınıfın bir nesnesi oluşturur [hatası](../standard-library/ios-base-class.md#failure).  
  
### <a name="example"></a>Örnek  
  Bkz: [rdstate](#rdstate) ve [getline](../standard-library/string-functions.md#getline) kullanan örnekler için **temizleyin**.  
  
##  <a name="copyfmt"></a>basic_ios::copyfmt  
 Bayrakları bir akıştan başka bir konuma kopyalar.  
  
```   
basic_ios<Elem, Traits>& copyfmt(
const basic_ios<Elem, Traits>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Bayrakları kopyalamak istediğiniz akış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **Bu** bayrakları kopyalama akış nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini geri çağırma olay raporları **silme\_olay**. Bunun ardından kopyalar `right` içine  **\*bu** doldurma karakteri, bağ işaretçi ve biçimlendirme bilgileri. Özel Durum maskesi değiştirmeden önce geri çağırma olay raporları **copyfmt_event**. Kopyalama tamamlandıktan sonra IF **durumu &**[özel durumları](#exceptions) olan sıfır olmayan, işlevi etkili bir şekilde çağırır [temizleyin](#clear) bağımsız değişkeniyle [rdstate](#rdstate). Döndürdüğü  **\*bu**.  
  
### <a name="example"></a>Örnek  
  
```cpp    
// basic_ios_copyfmt.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )  
{  
  using namespace std;  
  ofstream x( "test.txt" );  
  int i = 10;  
    
  x << showpos;  
  cout << i << endl;  
  cout.copyfmt( x );  
  cout << i << endl;  
}  
  
```  
  
##  <a name="eof"></a>basic_ios::EOF  
 Bir akışın sonuna ulaşıldı olmadığını gösterir.  
  
```  
bool eof() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Akışın sonuna ulaşıldı, `false` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür `true` varsa [rdstate](#rdstate) `& eofbit` sıfır olmayan bir değer değil. Daha fazla bilgi için `eofbit`, bkz: [ios_base::iostate](../standard-library/ios-base-class.md#iostate).  
  
### <a name="example"></a>Örnek  
  
```cpp    
// basic_ios_eof.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
using namespace std;  
  
int main( int argc, char* argv[] )  
{  
  fstream   fs;  
  int n = 1;  
  fs.open( "basic_ios_eof.txt" );   // an empty file  
  cout << boolalpha  
  cout << fs.eof() << endl;  
  fs >> n;   // Read the char in the file  
  cout << fs.eof() << endl;  
}  
  
```  
  
##  <a name="exceptions"></a>basic_ios::Exceptions  
 Akış tarafından hangi özel durum atılır gösterir.  
  
```   
iostate exceptions() const; 
void exceptions(iostate Newexcept);
void exceptions(io_state Newexcept);
```  
  
### <a name="parameters"></a>Parametreler  
 *Newexcept*  
 Bir özel durum istediğiniz bayraklar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu an için özel durum akış için belirtilen bayraklar.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi depolanan özel durum maskesi döndürür. İkinci üye fonksiyonu depoları *_Except* özel durum maskesi döndürür, önceki değeri depolanır. Yeni bir özel durum maskesi depolama bir özel durum çağrı gibi atabilirsiniz Not [temizleyin](#clear)( [rdstate](#rdstate) ).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_ios_exceptions.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
    
  cout << cout.exceptions( ) << endl;  
  cout.exceptions( ios::eofbit );  
  cout << cout.exceptions( ) << endl;  
  try  
  {  
    cout.clear( ios::eofbit );   // Force eofbit on  
  }  
  catch ( exception &e )  
  {  
    cout.clear( );  
    cout << "Caught the exception." << endl;  
    cout << "Exception class: " << typeid(e).name()  << endl;  
    cout << "Exception description: " << e.what() << endl;  
  }  
}  
  
```  
  
```Output  
  
0  
1  
Caught the exception.  
Exception class: class std::ios_base::failure  
Exception description: ios_base::eofbit set   
```  
  
##  <a name="fail"></a>basic_ios::Fail  
 Geçerli bir alan bir akıştan ayıklamak için başarısız olduğunu gösterir.  
  
```  
bool fail() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsa [rdstate](#rdstate) `& (badbit|failbit)` Aksi takdirde sıfır olmayan, değer `false`.  
  
 Daha fazla bilgi için `failbit`, bkz: [ios_base::iostate](../standard-library/ios-base-class.md#iostate).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_ios_fail.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( void )  
{  
  using namespace std;  
  bool b = cout.fail( );  
  cout << boolalpha;  
  cout << b << endl;  
}  
  
```  
  
##  <a name="fill"></a>basic_ios::Fill  
 Metin akış olarak kadar geniş olmadığında kullanılacak karakter döndürür veya belirtir.  
  
```   
char_type fill() const; 
char_type fill(char_type Char);
```  
  
### <a name="parameters"></a>Parametreler  
 `Char`  
 Doldurma karakteri olarak istediğiniz karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli dolgu karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi saklı doldurma karakteri döndürür. İkinci üye fonksiyonu depoları `Char` doldurma karakteri döndürür, önceki değeri depolanır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_ios_fill.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iomanip>  
  
int main( )  
{  
  using namespace std;  
    
  cout << setw( 5 ) << 'a' << endl;     
  cout.fill( 'x' );  
  cout << setw( 5 ) << 'a' << endl;      
  cout << cout.fill( ) << endl;  
}  
  
```  
  
```Output  
  
a  
xxxxa  
x   
```  
  
##  <a name="good"></a>basic_ios::good  
 Akış iyi durumda olduğunu gösterir.  
  
```  
bool good() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsa [rdstate](#rdstate) `== goodbit` (hiçbir durumu bayrakları ayarlanır), aksi takdirde `false`.  
  
 Daha fazla bilgi için `goodbit`, bkz: [ios_base::iostate](../standard-library/ios-base-class.md#iostate).  
  
### <a name="example"></a>Örnek  
  Bkz: [basic_ios::bad](#bad) kullanma örneği için `good`.  
  
##  <a name="imbue"></a>basic_ios::imbue  
 Yerel olarak değiştirir.  
  
```   
locale imbue(const locale& Loc);
```  
  
### <a name="parameters"></a>Parametreler  
 `Loc`  
 Yerel ayar dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki yerel ayar.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa [rdbuf](#rdbuf) değil null gösteren bir işaretçidir, üye işlev çağrıları  
  
 `rdbuf`-> [pubimbue](../standard-library/basic-streambuf-class.md#pubimbue)(_ *Loc*)  
  
 Her iki durumda da döndürür [ios_base::imbue](../standard-library/ios-base-class.md#imbue)(_ *Loc*).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_ios_imbue.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <locale>  
  
int main( )  
{  
  using namespace std;  
    
  cout.imbue( locale( "french_france" ) );  
  double x = 1234567.123456;  
  cout << x << endl;  
}  
  
```  
  
##  <a name="init"></a>basic_ios::init  
 Basic_ios oluşturucular tarafından çağrılır.  
  
```  
 
void init(basic_streambuf<Elem,Traits>* _Sb, bool _Isstd = false);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Sb`  
 Giriş veya çıkış öğeleri depolamak için standart bir arabellek.  
  
 `_Isstd`  
 Bu standart bir akış olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi tüm üye nesnelerindeki değerleri depolar böylece:  
  
- [rdbuf](#rdbuf) döndürür *_Sb.*  
  
- [tie](#tie) null işaretçi döndürür.  
  
- [rdstate](#rdstate) döndürür [goodbit](../standard-library/ios-base-class.md#iostate) varsa `_Sb` döndürdüğü sıfır olmayan tersi durumda [badbit](../standard-library/ios-base-class.md#iostate).  
  
- [özel durumlar](#exceptions) döndürür **goodbit**.  
  
- [bayrakları](../standard-library/ios-base-class.md#flags) döndürür [skipws](../standard-library/ios-base-class.md#fmtflags) &#124; [Ara](../standard-library/ios-base-class.md#fmtflags).  
  
- [Genişlik](../standard-library/ios-base-class.md#width) 0 döndürür.  
  
- [Duyarlık](../standard-library/ios-base-class.md#precision) 6 döndürür.  
  
- [Dolgu](#fill) boşluk karakteri döndürür.  
  
- [getloc](../standard-library/ios-base-class.md#getloc) döndürür `locale::classic`.  
  
- [iword](../standard-library/ios-base-class.md#iword) sıfır verir ve [pword](../standard-library/ios-base-class.md#pword) tüm bağımsız değişken değeri için boş bir işaretçi döndürür.  
  
##  <a name="int_type"></a>basic_ios::int_type  
 Eşanlamlısı **traits_type::int_type**.  
  
```  
typedef typename traits_type::int_type int_type;  
```  
  
##  <a name="move"></a>basic_ios::Move  
 Geçerli nesneye parametre akışı arabelleğe işaretçi dışındaki tüm değerleri taşır.  
  
```   
void move(basic_ios&& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 `ios_base` Değerlerinden taşımak için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı üye fonksiyonu içinde depolanan tüm değerleri taşır `right` için `*this` dışındaki saklı `stream buffer pointer`, içinde değişmeden `right` ve bir null işaretçi koymak `*this`. Saklı `tie pointer` içinde null bir işaretçi olarak ayarlanmış `right`.  
  
##  <a name="narrow"></a>basic_ios::Narrow  
 Eşdeğer char bulur bir verilen `char_type`.  
  
```  
char narrow(char_type Char, char Default = '\0') const;
```  
  
### <a name="parameters"></a>Parametreler  
 `Char`  
 `char` Dönüştürülemiyor.  
  
 `Default`  
 `char` Eşdeğeri bulunursa, döndürülen istiyor.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşdeğer `char` için bir verilen `char_type`.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [use_facet](../standard-library/basic-filebuf-class.md#open)\<ctype\<E >> ( [getloc](../standard-library/ios-base-class.md#getloc)()).`narrow` ( `Char`, `Default`).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_ios_narrow.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <wchar.h>  
  
int main( )  
{  
  using namespace std;  
  wchar_t *x = L"test";  
  char y[10];  
  cout << x[0] << endl;  
  wcout << x << endl;  
  y[0] = wcout.narrow( x[0] );  
  cout << y[0] << endl;  
}  
```  
  
##  <a name="off_type"></a>basic_ios::off_type  
 Eşanlamlısı **traits_type::off_type**.  
  
```  
typedef typename traits_type::off_type off_type;  
```  
  
##  <a name="op_void_star"></a>basic_ios::operator void *  
 Akış iyi olup olmadığını gösterir.  
  
```  
 operator void *() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Null işaretçinin yalnızca IF işleci döndürür [başarısız](#fail).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_ios_opgood.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  cout << (bool)(&cout != 0) << endl;   // Stream is still good  
}  
  
```  
  
```Output  
1  
```  
  
##  <a name="op_not"></a>basic_ios::operator!  
 Akış bozuk olup olmadığını gösterir.  
  
```   
bool operator!() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür [başarısız](#fail).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_ios_opbad.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  cout << !cout << endl;   // Stream is not bad  
}  
  
```  
  
```Output  
0  
```  
  
##  <a name="op_bool"></a>basic_ios::operator bool  
 Kullanılmasına bir `basic_ios` nesnesinin bir `bool`. Otomatik tür dönüştürme ortak, istenmeyen yan etkileri önlemek için devre dışı bırakılır.  
  
```  
explicit operator bool() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir değer dönüştürülebilir işleci döndürür `false` yalnızca `fail()`. Dönüş türü yalnızca dönüştürülebilir `bool`, değil `void *` veya diğer bilinen skaler bir tür.  
  
##  <a name="pos_type"></a>basic_ios::pos_type  
 Eşanlamlısı **traits_type::pos_type**.  
  
```  
typedef typename traits_type::pos_type pos_type;  
```  
  
##  <a name="rdbuf"></a>basic_ios::rdbuf  
 Belirtilen arabellek yollar akış.  
  
```   
basic_streambuf<Elem, Traits> *rdbuf() const; 
basic_streambuf<Elem, Traits> *rdbuf(
basic_streambuf<Elem, Traits>* _Sb);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Sb`  
 Bir akış.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi saklı Akış Arabellek işaretçi döndürür.  
  
 İkinci üye fonksiyonu depoları `_Sb` saklı Akış Arabellek işaretçi olarak ve daha önce depolanan değeri döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_ios_rdbuf.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main( )  
{  
  using namespace std;  
  ofstream file( "rdbuf.txt" );  
  streambuf *x = cout.rdbuf( file.rdbuf( ) );  
  cout << "test" << endl;   // Goes to file  
  cout.rdbuf(x);  
  cout << "test2" << endl;  
}  
  
```  
  
```Output  
test2  
```  
  
##  <a name="rdstate"></a>basic_ios::rdstate  
 Bit bayrakları için durumunu okur.  
  
```  
 
iostate rdstate() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Saklı akış durumu bilgisi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_ios_rdstate.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
using namespace std;  
  
void TestFlags( ios& x )  
{  
  cout << ( x.rdstate( ) & ios::badbit ) << endl;  
  cout << ( x.rdstate( ) & ios::failbit ) << endl;  
  cout << ( x.rdstate( ) & ios::eofbit ) << endl;  
  cout << endl;  
}  
  
int main( )  
{  
  fstream x( "c:\test.txt", ios::out );  
  x.clear( );  
  TestFlags( x );  
  x.clear( ios::badbit | ios::failbit | ios::eofbit );  
  TestFlags( x );  
}  
  
```  
  
```Output  
  
0  
0  
0  
  
4  
2  
1   
```  
  
##  <a name="setstate"></a>basic_ios::setstate  
 Ek bayrakları ayarlar.  
  
```   
void setstate(iostate _State);
```  
  
### <a name="parameters"></a>Parametreler  
 `_State`  
 Ayarlamak için ek bayrakları.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini etkili bir şekilde çağırır [temizleyin](#clear)(_ *durumu* &#124; [rdstate](#rdstate)).  
  
### <a name="example"></a>Örnek  
  
```cpp    
// basic_ios_setstate.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
  bool b = cout.bad( );  
  cout << b << endl;   // Good  
  cout.clear( ios::badbit );  
  b = cout.bad( );  
  // cout.clear( );  
  cout << b << endl;   // Is bad, good  
  b = cout.fail( );  
  cout << b << endl;   // Not failed  
  cout.setstate( ios::failbit );  
  b = cout.fail( );  
  cout.clear( );  
  cout << b << endl;   // Is failed, good  
  return 0;  
}  
  
```  
  
```Output  
  
0  
1   
```  
  
##  <a name="set_rdbuf"></a>basic_ios::set_rdbuf  
 Bu akış nesne için Okuma arabelleği olması için Akış Arabellek atar.  
  
```   
void set_rdbuf(
basic_streambuf<Elem, Tr>* strbuf)  
```  
  
### <a name="parameters"></a>Parametreler  
 `strbuf`  
 Okuma arabelleği olmasını akış arabellek.  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı üye fonksiyonu depoları `strbuf` içinde `stream buffer pointer`. Arama `clear`.  
  
##  <a name="tie"></a>basic_ios::tie  
 Bu bir akış önce başka bir akış işlenen sağlar.  
  
```  
 
basic_ostream<Elem, Traits> *tie() const; 
basic_ostream<Elem, Traits> *tie(
basic_ostream<Elem, Traits>* str);
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 Bir akış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işlevi saklı bağ işaretçi döndürür. İkinci üye fonksiyonu depoları `str` bağ işaretçi döndürür, önceki değeri depolanır.  
  
### <a name="remarks"></a>Açıklamalar  
 `tie`diğer akış işlemleri tamamlandıktan sonra bir akış üzerinde işlemler meydana şekilde eşitlenmesi iki akışlarının neden olur.  
  
### <a name="example"></a>Örnek  
  Bu örnekte, cout, cin bağlamadan tarafından onu, garanti "bir sayı girin:" dizesi gider numarası önce konsola kendisini cin ayıklanır. Bu olasılığını ortadan kaldırır, "bir sayı girin:" numarası okunduğunda dize arabellekte hala durduğunu, böylece biz eminseniz kullanıcı yanıtlamak için bazı komut gerçekte vardır.. Varsayılan olarak, cin ve cout bağlıdır.  
  
```  
  
#include <ios>  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  int i;  
  cin.tie( &cout );  
  cout << "Enter a number:";  
  cin >> i;  
}  
  
```  
  
##  <a name="traits_type"></a>basic_ios::traits_type  
 Şablon parametresi için bir eş anlamlı **nitelikler**.  
  
```   
typedef Traits traits_type;  
```  
  
##  <a name="widen"></a>basic_ios::widen  
 Eşdeğer bulur `char_type` için bir verilen `char`.  
  
```   
char_type widen(char Char) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `Char`  
 Dönüştürülecek karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşdeğer bulur `char_type` için bir verilen `char`.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype** \< **E**>> ( [getloc](../standard-library/ios-base-class.md#getloc)). `widen`( `Char`).  
  
### <a name="example"></a>Örnek  
  
```cpp    
// basic_ios_widen.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <wchar.h>  
  
int main( )  
{  
  using namespace std;  
  char *z = "Hello";  
  wchar_t y[2] = {0,0};  
  cout << z[0] << endl;  
  y[0] = wcout.widen( z[0] );  
  wcout << &y[0] << endl;  
}  
  
```  
  
##  <a name="swap"></a>basic_ios::Swap  
 Bu değerler alış verişleri `basic_ios` kişiler başka bir nesne `basic_ios` nesne. Ancak, akış arabellekleri işaretçiler takas değil.  
  
```   
void swap(basic_ios&& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 `basic_ios` Değerleri değişimi için kullanılan nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı üye fonksiyonu içinde depolanan tüm değerleri değiştirir `right` ile `*this` dışındaki saklı `stream buffer pointer`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams kuralları](../standard-library/iostreams-conventions.md)

