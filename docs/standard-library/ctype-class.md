---
title: "CType sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocale/std::ctype
- xlocale/std::ctype::char_type
- xlocale/std::ctype::do_is
- xlocale/std::ctype::do_narrow
- xlocale/std::ctype::do_scan_is
- xlocale/std::ctype::do_scan_not
- xlocale/std::ctype::do_tolower
- xlocale/std::ctype::do_toupper
- xlocale/std::ctype::do_widen
- xlocale/std::ctype::is
- xlocale/std::ctype::narrow
- xlocale/std::ctype::scan_is
- xlocale/std::ctype::scan_not
- xlocale/std::ctype::tolower
- xlocale/std::ctype::toupper
- xlocale/std::ctype::widen
dev_langs: C++
helpviewer_keywords:
- std::ctype [C++]
- std::ctype [C++], char_type
- std::ctype [C++], do_is
- std::ctype [C++], do_narrow
- std::ctype [C++], do_scan_is
- std::ctype [C++], do_scan_not
- std::ctype [C++], do_tolower
- std::ctype [C++], do_toupper
- std::ctype [C++], do_widen
- std::ctype [C++], is
- std::ctype [C++], narrow
- std::ctype [C++], scan_is
- std::ctype [C++], scan_not
- std::ctype [C++], tolower
- std::ctype [C++], toupper
- std::ctype [C++], widen
ms.assetid: 3627154c-49d9-47b5-b28f-5bbedee38e3b
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 10bc57e29383386df63de4cd6f27299a8f9986a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ctype-class"></a>ctype Sınıfı
Büyük küçük harflerden ve yerel karakter kümesiyle yerel ayar tarafından kullanılan küme arasında dönüştürme yapan, karakterleri sınıflandırmak için kullanılan model sağlayan bir sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class CharType>  
class ctype : public ctype_base;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `CharType`  
 Bir program içindeki karakterleri kodlamak için kullanılan tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Benzersiz bir pozitif değer saklı değerini erişmek için ilk deneme depolar **kimliği.** Sınıflandırma ölçütü temel sınıf ctype_base içindeki bir iç içe bit maskesi türünde sağlanır.  
  
 C++ Standart Kitaplığı, bu şablonu sınıfın iki açık özelleştirmeleri tanımlar:  
  
- [CType](../standard-library/ctype-char-class.md)< `char`>, bir açık uzmanlığı olan farklar ayrı olarak açıklanmıştır.  
  
- **CType**< `wchar_t`>, geniş karakter olarak öğeleri değerlendirir.  
  
 Şablon sınıfının diğer özelleştirmeleri **ctype** \< **CharType**>:  
  
-   Bir değeri dönüştürme ***ch*** türü **CharType** türünde bir değer için `char` with ifadesi ( `char`) **ch**.  
  
-   Bir değeri dönüştürme ***bayt*** türü `char` türünde bir değer için **CharType** ifade ile **CharType** ( **bayt**).  
  
 Diğer tüm işlemleri üzerinde gerçekleştirilen `char` açık uzmanlık ettirilmesi aynı şekilde değerleri **ctype**< `char`>.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[CType](#ctype)|Sınıfının nesneleri için oluşturucu `ctype` , yerel ayar model karakter olarak hizmet verir.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlayan tür.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[do_is](#do_is)|Tek bir karakterin belirli bir özniteliği olup olmadığını sınamak veya bir aralıktaki her bir karakter özniteliğini sınıflandırmak ve bunları bir dizide saklamak için çağrılan bir sanal işlev.|  
|[do_narrow](#do_narrow)|Bir sanal işlev olarak adlandırılan bir karakter türü dönüştürmek için `CharType` karşılık gelen karakter türü için bir yerel tarafından kullanılan `char` yerel karakter kümesi.|  
|[do_scan_is](#do_scan_is)|Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.|  
|[do_scan_not](#do_scan_not)|Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.|  
|[do_tolower](#do_tolower)|Bir karakteri ya da karakter aralığını kendi küçük harflerine dönüştürmek için çağrılan bir sanal işlev.|  
|[do_toupper](#do_toupper)|Bir karakteri ya da karakter aralığını kendi büyük harflerine dönüştürmek için çağrılan bir sanal işlev.|  
|[do_widen](#do_widen)|Adlı bir sanal işleve bir karakter türü dönüştürür `char` yerel karakter türüne karşılık gelen karakter kümesinde `CharType` yerel ayarı tarafından kullanılır.|  
|[değil](#is)|Tek bir karakterin belirli bir özniteliği olup olmadığını sınar veya bir aralıktaki her bir karakter özniteliğini sınıflandırır ve bunları bir dizide saklar.|  
|[daraltma](#narrow)|Bir karakter türü dönüştürür `CharType` bir yerel tür char yerel karakter kümesinde karşılık gelen karakter tarafından kullanılır.|  
|[scan_is](#scan_is)|Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulur.|  
|[scan_not](#scan_not)|Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulur.|  
|[tolower](#tolower)|Bir karakteri ya da karakter aralığını küçük harflere dönüştürür.|  
|[toupper](#toupper)|Bir karakteri ya da karakter aralığını büyük harflere dönüştürür.|  
|[widen](#widen)|Bir karakter türü dönüştürür `char` yerel karakter türüne karşılık gelen karakter kümesinde `CharType` yerel ayarı tarafından kullanılır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
##  <a name="char_type"></a>CType::char_type  
 Bir yerel ayar tarafından kullanılan bir karakteri tanımlayan tür.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **CharType**.  
  
### <a name="example"></a>Örnek  
  Üye işlevine bakın [widen](#widen) kullanan bir örnek `char_type` dönüş değeri olarak.  
  
##  <a name="ctype"></a>CType::CType  
 Yerel ayar model karakter olarak hizmet sınıfı ctype nesnelerin Oluşturucusu.  
  
```  
explicit ctype(size_t _Refs = 0);
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
  
 Oluşturucu başlatır, `locale::facet` temel nesnesiyle **yerel ayar::**[modeli](../standard-library/locale-class.md#facet_class)( `_Refs`).  
  
##  <a name="do_is"></a>CType::do_is  
 Tek bir karakterin belirli bir özniteliği olup olmadığını sınamak veya bir aralıktaki her bir karakter özniteliğini sınıflandırmak ve bunları bir dizide saklamak için çağrılan bir sanal işlev.  
  
```  
virtual bool do_is(
    mask maskVal,   
    CharType ch) const;

 
virtual const CharType *do_is(
    const CharType* first,   
    const CharType* last,  
    mask* dest) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `maskVal`  
 Karakter sınanacak olduğu maskesi değeri.  
  
 `ch`  
 Sınanacak niteliklerini olan karakter.  
  
 `first`  
 Niteliklerini sınıflandırılabilir üzeresiniz aralıktaki ilk karakter bir işaretçi.  
  
 `last`  
 Bir işaretçi niteliklerini sınıflandırılabilir üzeresiniz aralıktaki son karakter hemen ardından karakter.  
  
 `dest`  
 Her karakterine özniteliklerini characterizing maskesi değerlerinin depolanması olduğu dizisi başına bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işlevi olan bir Boole değeri döndürür **true** test karakter maskesi değerle; tanımlanan özniteliğine sahipse, **false** özniteliğine sahip başarısız olursa.  
  
 İkinci üye işlevi öznitelikleri her bir aralıktaki karakterleri characterizing maskesi değerleri içeren bir dizi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Karakterleri özniteliklerini sınıflandırma maskesi değerleri sınıfı tarafından sağlanan [ctype_base](../standard-library/ctype-base-class.md), hangi ctype türer. İlk üye işlev ifadeleri için bit maskesi olarak adlandırılır ve maskesi değerleri birleşiminden mantıksal bit düzeyinde işleçler tarafından oluşturulmuş, ilk parametresinin için kabul edebilirsiniz (&#124; &, ^, ~).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [olan](#is), çağıran `do_is`.  
  
##  <a name="do_narrow"></a>CType::do_narrow  
 Bir sanal işlev olarak adlandırılan bir karakter türü dönüştürmek için `CharType` karşılık gelen karakter türü için bir yerel tarafından kullanılan `char` yerel karakter kümesi.  
  
```  
virtual char do_narrow(
    CharType ch,   
    char default = '\0') const;

 
virtual const CharType* do_narrow(
    const CharType* first,   
    const CharType* last,  
    char default,   
    char* dest) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `ch`  
 Karakter türü `Chartype` dönüştürülecek yerel tarafından kullanılır.  
  
 `default`  
 Karakter türündeki üye işlevi tarafından atanacak varsayılan değer `CharType` karşılık gelen karakter türü olmayan `char`.  
  
 `first`  
 Dönüştürülecek karakter aralığı ilk karakteri bir işaretçi.  
  
 `last`  
 Dönüştürülecek karakter aralığı son karakter hemen ardından karakteri gösteren bir işaretçi.  
  
 `dest`  
 Const işaretçi türü ilk karakteri `char` hedef aralığında Dönüştürülmüş aralıktaki karakterleri depolar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk korumalı üye işlevi türü parametre karakterine karşılık gelen tür char yerel karakteri döndürür `CharType` veya `default` hiçbir karşılık gelen tanımlanmış olması durumunda.  
  
 Yerel karakter türü karakterlerinden dönüştürülen hedef aralığı için bir işaretçi ikinci korumalı üye işlevi döndürür `CharType`.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci korumalı üye şablon işlevi depolarında `dest`[ `I`] değeri `do_narrow`( `first` [ `I`], `default`), için `I` aralığında [0, `last`  -  `first`).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [daraltmak](#narrow), çağıran `do_narrow`.  
  
##  <a name="do_scan_is"></a>CType::do_scan_is  
 Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.  
  
```  
virtual const CharType *do_scan_is(
    mask maskVal,   
    const CharType* first,   
    const CharType* last) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `maskVal`  
 Bir karakter eşleştirilmesini maskesi değeri.  
  
 `first`  
 Taranacak aralıktaki ilk karakter bir işaretçi.  
  
 `last`  
 Taranacak aralıktaki son karakter hemen ardından karakteri gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen kodla eşleşmiyor bir aralıktaki ilk karakteri bir işaretçi. Böyle bir değeri var olup olmadığını işlevi döndürür`last.`  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı üye fonksiyonu en küçük işaretçi döndüren `ptr` aralığında [ `first`, `last`) kendisi için [do_is](#do_is)( `maskVal`, * `ptr`) geçerlidir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [scan_is](#scan_is), çağıran `do_scan_is`.  
  
##  <a name="do_scan_not"></a>CType::do_scan_not  
 Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.  
  
```  
virtual const CharType *do_scan_not(
    mask maskVal,   
    const CharType* first,   
    const CharType* last) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `maskVal`  
 Bir karakter değil eşleştirilecek maskesi değeri.  
  
 `first`  
 Taranacak aralıktaki ilk karakter bir işaretçi.  
  
 `last`  
 Taranacak aralıktaki son karakter hemen ardından karakteri gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen maske eşleşmeyen bir aralıktaki ilk karakteri bir işaretçi. Böyle bir değeri var olup olmadığını işlevi döndürür `last`.  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı üye fonksiyonu en küçük işaretçi döndüren `ptr` aralığında [ `first`, `last`) kendisi için [do_is](#do_is)( `maskVal`, * `ptr`) yanlış.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [scan_not](#scan_not), çağıran `do_scan_not`.  
  
##  <a name="do_tolower"></a>CType::do_tolower  
 Bir karakter ya da bir aralıktaki karakterleri küçük harfe dönüştürmek için adlı bir sanal işlev.  
  
```  
virtual CharType do_tolower(CharType ch) const;

 
virtual const CharType *do_tolower(
    CharType* first,   
    const CharType* last) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `ch`  
 Küçük harflere dönüştürülecek karakter.  
  
 `first`  
 Dönüştürülecek olan durumlarda karakterler aralığındaki ilk karakteri bir işaretçi.  
  
 `last`  
 Dönüştürülecek olan durumlarda karakterler aralığındaki son karakter hemen ardından karakteri gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk korumalı üye işlevi parametresi küçük biçiminde döndürür `ch`. Küçük harf form var olup olmadığını döndürür `ch`. İkinci korumalı üye işlev dönüşleri `last`.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci korumalı üye şablon işlevi her öğesini değiştirir `first` [ `I`], için `I` aralığında [0, `last`  -  `first`), ile `do_tolower`( `first` [ `I`]).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [tolower](#tolower), çağıran `do_tolower`.  
  
##  <a name="do_toupper"></a>CType::do_toupper  
 Bir karakteri ya da karakter aralığını kendi büyük harflerine dönüştürmek için çağrılan bir sanal işlev.  
  
```  
virtual CharType do_toupper(CharType ch) const;

 
virtual const CharType *do_toupper(
    CharType* first,   
    const CharType* last) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `ch`  
 Büyük harfe dönüştürülecek karakter.  
  
 `first`  
 Dönüştürülecek olan durumlarda karakterler aralığındaki ilk karakteri bir işaretçi.  
  
 `last`  
 Dönüştürülecek olan durumlarda karakterler aralığındaki son karakter hemen ardından karakteri gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk korumalı üye işlevi parametresi büyük biçiminde döndürür `ch`. Büyük harf form var olup olmadığını döndürür `ch`. İkinci korumalı üye işlev dönüşleri `last`.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci korumalı üye şablon işlevi her öğesini değiştirir `first` [ `I`], için `I` aralığında [0, `last`  -  `first`), ile `do_toupper`( `first` [ `I`]).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [toupper](#toupper), çağıran `do_toupper`.  
  
##  <a name="do_widen"></a>CType::do_widen  
 Adlı bir sanal işleve bir karakter türü dönüştürür `char` yerel karakter türüne karşılık gelen karakter kümesinde `CharType` yerel ayarı tarafından kullanılır.  
  
```  
virtual CharType do_widen(char byte) const;

 
virtual const char *do_widen(
    const char* first,   
    const char* last,   
    CharType* dest) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `byte`  
 Karakter türü `char` yerel karakter dönüştürülecek kümesinde.  
  
 `first`  
 Dönüştürülecek karakter aralığı ilk karakteri bir işaretçi.  
  
 `last`  
 Dönüştürülecek karakter aralığı son karakter hemen ardından karakteri gösteren bir işaretçi.  
  
 `dest`  
 İlk karakter türü için bir işaretçi `CharType` hedef aralığında Dönüştürülmüş aralıktaki karakterleri depolar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk korumalı üye işlev türü karakteri döndürür `CharType` yerel tür parametresi karakterine karşılık gelen `char`.  
  
 İkinci korumalı üye fonksiyonu karakter türü hedef aralığı için bir işaretçi döndürür `CharType` yerel türü karakterlerinden dönüştürülen bir yerel tarafından kullanılan `char`.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci korumalı üye şablon işlevi depolarında `dest`[ `I`] değeri `do_widen`( `first`[ `I`]), için `I` aralığında [0, `last`  -  `first`).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [widen](#widen), çağıran `do_widen`.  
  
##  <a name="is"></a>CType::is  
 Tek bir karakter belirli bir özniteliği var veya bir aralıktaki her karakter özniteliklerini sınıflandırır ve bunları bir dizide depolar olup olmadığını sınar.  
  
```  
bool is(mask maskVal, CharType ch) const;

 
const CharType *is(
    const CharType* first,   
    const CharType* last,  
    mask* dest) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `maskVal`  
 Karakter sınanacak olduğu maskesi değeri.  
  
 `ch`  
 Sınanacak niteliklerini olan karakter.  
  
 `first`  
 Niteliklerini sınıflandırılabilir üzeresiniz aralıktaki ilk karakter bir işaretçi.  
  
 `last`  
 Bir işaretçi niteliklerini sınıflandırılabilir üzeresiniz aralıktaki son karakter hemen ardından karakter.  
  
 `dest`  
 Her karakterine özniteliklerini characterizing maskesi değerlerinin depolanması olduğu dizisi başına bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işlevinin döndürdüğü `true` test karakter maskesi değerle; tanımlanan özniteliğine sahipse, `false` özniteliğine sahip başarısız olursa.  
  
 İkinci üye işlevi niteliklerini sınıflandırılabilir üzeresiniz aralıktaki son karakter bir işaretçi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Karakterleri özniteliklerini sınıflandırma maskesi değerleri sınıfı tarafından sağlanan [ctype_base sınıfı](../standard-library/ctype-base-class.md), hangi ctype türer. İlk üye işlev ifadeleri için bit maskesi olarak adlandırılır ve maskesi değerleri birleşiminden mantıksal bit düzeyinde işleçler tarafından oluşturulmuş, ilk parametresinin için kabul edebilirsiniz (&#124; &, ^, ~).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ctype_is.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main() {  
   locale loc1 ( "German_Germany" ), loc2 ( "English_Australia" );  
  
   if (use_facet<ctype<char> > ( loc1 ).is( ctype_base::alpha, 'a' ))  
      cout << "The character 'a' in locale loc1 is alphabetic."   
           << endl;  
   else  
      cout << "The character 'a' in locale loc1 is not alphabetic."   
           << endl;  
  
   if (use_facet<ctype<char> > ( loc2 ).is( ctype_base::alpha, '!' ))  
      cout << "The character '!' in locale loc2 is alphabetic."   
           << endl;  
   else  
      cout << "The character '!' in locale loc2 is not alphabetic."   
           << endl;  
  
   char *string = "Hello, my name is John!";  
   ctype<char>::mask maskarray[30];  
   use_facet<ctype<char> > ( loc2 ).is(  
      string, string + strlen(string), maskarray );  
   for (unsigned int i = 0; i < strlen(string); i++) {  
      cout << string[i] << ": "  
           << (maskarray[i] & ctype_base::alpha  "alpha"  
                                                : "not alpha")  
           << endl;;  
   };  
}  
```  
  
##  <a name="narrow"></a>CType::Narrow  
 Tür karakterleri dönüştürür `CharType` yerel ayar karşılık gelen karakter türü tarafından kullanılan `char` yerel karakter kümesi.  
  
```  
char narrow(CharType ch, char default = '\0') const;

 
const CharType* narrow(
    const CharType* first,   
    const CharType* last,  
    char default,   
    char* dest) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `ch`  
 Karakter türü `Chartype` dönüştürülecek yerel tarafından kullanılır.  
  
 `default`  
 Karakter türündeki üye işlevi tarafından atanacak varsayılan değer `CharType` karşılık gelen karakter türü olmayan `char`.  
  
 `first`  
 Dönüştürülecek karakter aralığı ilk karakteri bir işaretçi.  
  
 `last`  
 Dönüştürülecek karakter aralığı son karakter hemen ardından karakteri gösteren bir işaretçi.  
  
 `dest`  
 Const işaretçi türü ilk karakteri `char` hedef aralığında Dönüştürülmüş aralıktaki karakterleri depolar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işlevi türü yerel karakteri döndürür `char` türü parametre karakterine karşılık gelen `CharType default` değil karşılık gelen tanımlanmış olması durumunda.  
  
 İkinci üye işlevi türü karakterlerinden dönüştürülen yerel karakter hedef aralığı için bir işaretçi döndürür `CharType`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevinin döndürdüğü [do_narrow](#do_narrow)( `ch`, `default`). İkinci üye işlevinin döndürdüğü [do_narrow](#do_narrow) ( `first`, `last`, `default`, `dest`). Yalnızca temel kaynak karakterleri benzersiz bir ters görüntüsü olması garanti `CharType` altında `narrow`. Bu temel kaynak karakterler için aşağıdaki değişmeyen tutar: `narrow` ( [widen](#widen) ( **c** ), 0) == **c**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ctype_narrow.cpp  
// compile with: /EHsc /W3  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   locale loc1 ( "english" );  
   wchar_t *str1 = L"\x0392fhello everyone";  
   char str2 [16];  
   bool result1 = (use_facet<ctype<wchar_t> > ( loc1 ).narrow  
      ( str1, str1 + wcslen(str1), 'X', &str2[0] ) != 0);  // C4996  
   str2[wcslen(str1)] = '\0';  
   wcout << str1 << endl;  
   cout << &str2[0] << endl;  
}  
```  
  
```Output  
Xhello everyone  
```  
  
##  <a name="scan_is"></a>CType::scan_is  
 Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulur.  
  
```  
const CharType *scan_is(
    mask maskVal,   
    const CharType* first,   
    const CharType* last) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `maskVal`  
 Bir karakter eşleştirilmesini maskesi değeri.  
  
 `first`  
 Taranacak aralıktaki ilk karakter bir işaretçi.  
  
 `last`  
 Taranacak aralıktaki son karakter hemen ardından karakteri gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen kodla eşleşmiyor bir aralıktaki ilk karakteri bir işaretçi. Böyle bir değeri var olup olmadığını işlevi döndürür`last.`  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [do_scan_is](#do_scan_is)( `maskVal`, `first`, `last`).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ctype_scan_is.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc1 ( "German_Germany" );  
  
   char *string = "Hello, my name is John!";  
  
   const char* i = use_facet<ctype<char> > ( loc1 ).scan_is  
      ( ctype_base::punct, string, string + strlen(string) );  
   cout << "The first punctuation is \"" << *i << "\" at position: "   
      << i - string << endl;  
}  
```  
  
```Output  
The first punctuation is "," at position: 5  
```  
  
##  <a name="scan_not"></a>CType::scan_not  
 Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulur.  
  
```  
const CharType *scan_not(
    mask maskVal,   
    const CharType* first,   
    const CharType* last) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `maskVal`  
 Bir karakter değil eşleştirilecek maskesi değeri.  
  
 `first`  
 Taranacak aralıktaki ilk karakter bir işaretçi.  
  
 `last`  
 Taranacak aralıktaki son karakter hemen ardından karakteri gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen maskeyle eşleşmiyor bir aralıktaki ilk karakteri bir işaretçi. Böyle bir değeri var olup olmadığını işlevi döndürür `last`.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [do_scan_not](#do_scan_not)( `maskVal`, `first`, `last`).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ctype_scan_not.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc1 ( "German_Germany" );  
  
   char *string = "Hello, my name is John!";  
  
   const char* i = use_facet<ctype<char> > ( loc1 ).scan_not  
      ( ctype_base::alpha, string, string + strlen(string) );  
   cout << "First nonalpha character is \"" << *i << "\" at position: "   
      << i - string << endl;  
}  
```  
  
```Output  
First nonalpha character is "," at position: 5  
```  
  
##  <a name="tolower"></a>CType::tolower  
 Bir karakteri ya da karakter aralığını küçük harflere dönüştürür.  
  
```  
CharType tolower(CharType ch) const;

 
const CharType *tolower(CharType* first, const CharType* last) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `ch`  
 Küçük harflere dönüştürülecek karakter.  
  
 `first`  
 Dönüştürülecek olan durumlarda karakterler aralığındaki ilk karakteri bir işaretçi.  
  
 `last`  
 Dönüştürülecek olan durumlarda karakterler aralığındaki son karakter hemen ardından karakteri gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işlevi parametresi küçük biçiminde döndürür `ch`. Küçük harf form var olup olmadığını döndürür `ch`.  
  
 İkinci üye işlevinin döndürdüğü `last`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevinin döndürdüğü [do_tolower](#do_tolower)( `ch`). İkinci üye işlevinin döndürdüğü [do_tolower](#do_tolower)( `first`, `last`).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ctype_tolower.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   locale loc1 ( "German_Germany" );  
  
   char string[] = "HELLO, MY NAME IS JOHN";  
  
   use_facet<ctype<char> > ( loc1 ).tolower  
      ( string, string + strlen(string) );  
   cout << "The lowercase string is: " << string << endl;  
}  
```  
  
```Output  
The lowercase string is: hello, my name is john  
```  
  
##  <a name="toupper"></a>CType::toupper  
 Bir karakteri ya da karakter aralığını büyük harflere dönüştürür.  
  
```  
CharType toupper(CharType ch) const; 
const CharType *toupper(CharType* first, const CharType* last) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `ch`  
 Büyük harfe dönüştürülecek karakter.  
  
 `first`  
 Dönüştürülecek olan durumlarda karakterler aralığındaki ilk karakteri bir işaretçi.  
  
 `last`  
 Dönüştürülecek olan durumlarda karakterler aralığındaki son karakter hemen ardından karakteri gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işlevi parametresi büyük biçiminde döndürür `ch`. Büyük harf form var olup olmadığını döndürür `ch`.  
  
 İkinci üye işlevinin döndürdüğü `last`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevinin döndürdüğü [do_toupper](#do_toupper)( `ch`). İkinci üye işlevinin döndürdüğü [do_toupper](#do_toupper)( `first`, `last`).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ctype_toupper.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc1 ( "German_Germany" );  
  
   char string[] = "Hello, my name is John";  
  
   use_facet<ctype<char> > ( loc1 ).toupper  
      ( string, string + strlen(string) );  
   cout << "The uppercase string is: " << string << endl;  
}  
```  
  
```Output  
The uppercase string is: HELLO, MY NAME IS JOHN  
```  
  
##  <a name="widen"></a>CType::widen  
 Bir karakter türü dönüştürür `char` yerel karakter türüne karşılık gelen karakter kümesinde `CharType` yerel ayarı tarafından kullanılır.  
  
```  
CharType widen(char byte) const; 
const char *widen(const char* first, const char* last, CharType* dest) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `byte`  
 Dönüştürülecek tür char yerel karakter, karakter kümesi.  
  
 `first`  
 Dönüştürülecek karakter aralığı ilk karakteri bir işaretçi.  
  
 `last`  
 Dönüştürülecek karakter aralığı son karakter hemen ardından karakteri gösteren bir işaretçi.  
  
 `dest`  
 İlk karakter türü için bir işaretçi `CharType` hedef aralığında Dönüştürülmüş aralıktaki karakterleri depolar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işlevi türü karakteri döndürür `CharType` yerel tür parametresi karakterine karşılık gelen `char`.  
  
 İkinci üye işlevi bir işaretçi türü karakter hedef aralığına döndürür `CharType` yerel türü karakterlerinden dönüştürülen bir yerel tarafından kullanılan `char`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevinin döndürdüğü [do_widen](#do_widen)( `byte`). İkinci üye işlevinin döndürdüğü [do_widen](#do_widen)( `first`, `last`, `dest`).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ctype_widen.cpp  
// compile with: /EHsc /W3  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   locale loc1 ( "English" );  
   char *str1 = "Hello everyone!";  
   wchar_t str2 [16];  
   bool result1 = (use_facet<ctype<wchar_t> > ( loc1 ).widen  
      ( str1, str1 + strlen(str1), &str2[0] ) != 0);  // C4996  
   str2[strlen(str1)] = '\0';  
   cout << str1 << endl;  
   wcout << &str2[0] << endl;  
  
   ctype<wchar_t>::char_type charT;  
   charT = use_facet<ctype<char> > ( loc1 ).widen( 'a' );  
}  
```  
  
```Output  
Hello everyone!  
Hello everyone!  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<yerel ayar >](../standard-library/locale.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

