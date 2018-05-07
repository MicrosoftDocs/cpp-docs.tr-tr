---
title: Platform::String sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::String::String
- VCCORLIB/Platform::String::Begin
- VCCORLIB/Platform::String::CompareOrdinal
- VCCORLIB/Platform::String::Concat
- VCCORLIB/Platform::String::Data
- VCCORLIB/Platform::String::Dispose
- VCCORLIB/Platform::String::End
- VCCORLIB/Platform::String::Equals
- VCCORLIB/Platform::String::GetHashCode
- VCCORLIB/Platform::String::IsEmpty
- VCCORLIB/Platform::String::IsFastPass
- VCCORLIB/Platform::String::Length
- VCCORLIB/Platform::String::ToString
dev_langs:
- C++
helpviewer_keywords:
- Platform::String
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7a18b1a8ced533389b5938d44a73589336f717f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="platformstring-class"></a>Platform::String sınıfı
Metin göstermek için kullanılan sıralı Unicode karakterler koleksiyonunu temsil eder. Daha fazla bilgi ve örnekler için bkz: [dizeleri](../cppcx/strings-c-cx.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
public ref class String sealed : Object,  
    IDisposable,  
    IEquatable,  
    IPrintable  
```  
  
## <a name="iterators"></a>Yineleyiciler  
 String sınıfı üyesi olmayan iki yineleyici işlevleri ile kullanılabilir `std::for_each` bir dize nesnesi karakterleri numaralandırmak için şablon işlevi.  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`const char16* begin(String^ s)`|Bir işaretçi belirtilen dize nesnesi başlangıcını döndürür.|  
|`const char16* end(String^ s)`|Belirtilen dize nesnesi sonunu aşan bir işaretçi döndürür.|  
  
### <a name="members"></a>Üyeler  
 String sınıfı nesne ve IDisposable, IEquatable ve IPrintable arabirimlerinden devralır.  
  
 String sınıfı aşağıdaki türden üyeleri de vardır.  
  
 **Oluşturucular**  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[String::String](#ctor)|Dize sınıfının yeni bir örneğini başlatır.|  
  
 **Yöntemler**  
  
 String sınıfı Equals(), Finalize(), GetHashCode(), GetType(), MemberwiseClose() ve ToString() yöntemleri devralır [Platform::Object sınıfı](../cppcx/platform-object-class.md). Dize ayrıca aşağıdaki yöntemleri içerir.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[String::Begin](#begin)|Bir işaretçi geçerli dize başlangıcını döndürür.|  
|[String::CompareOrdinal](#compareordinal)|İki karşılaştırır `String` nesneleri tarafından temsil edilen iki dize değerlerini karşılık gelen karakterleri sayısal değerleri değerlendirme nesneleri.|  
|[String::concat](#concat)|İki dize nesnelerini değerlerini art arda ekler.|  
|[String::Data](#data)|Bir işaretçi geçerli dize başlangıcını döndürür.|  
|[String::Dispose](#dispose)|Serbest bırakma veya kaynakları serbest bırakır.|  
|[String::End](#end)|Geçerli dize sonu geçmiş bir işaretçi döndürür.|  
|[String::Equals](#equals)|Belirtilen nesne geçerli nesneye eşit olup olmadığını gösterir.|  
|[String::GetHashCode](#gethashcode)|Bu örneğin karma kodunu döndürür.|  
|[String::IsEmpty](#isempty)|Geçerli dize nesnesi boş olup olmadığını gösterir.|  
|[String::IsFastPass](#isfastpass)|Nesne geçerli dize katılıyor olup olmadığını belirten bir *hızlı geçişi* işlemi. İşlemi hızlı geçişi, başvuru sayımı askıya alınır.|  
|[String::length](#length)|Geçerli dize nesnesi uzunluğunu alır.|  
|[String::toString](#tostring)|Değeri geçerli dizesi ile aynı olan bir dize nesnesi döndürür.|  
  
 **İşleçler**  
  
 Dize sınıfı aşağıdaki işleçleri sahiptir.  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[String::operator == işleci](#operator-equality)|İki belirtilen dize nesnesi aynı değere sahip olup olmadığını gösterir.|  
|[operator + işleci](#operator-plus)|İki dize nesnelerini yeni bir dize nesnesi art arda ekler.|  
|[String::operator > işleci](#operator-greater-than)|Bir dize nesnesi değerini ikinci bir değerden daha büyük olup olmadığını belirten dize nesnesi.|  
|[String::operator > = işleci](#operator-greater-than-or-equals)|Bir dize nesnesi değerini saniyenin değerine eşit veya daha büyük olup olmadığını belirten dize nesnesi.|  
|[String::operator! = işleci](#operator-inequality)|İki belirtilen dize nesnesi farklı değerlere sahip olup olmadığını gösterir.|  
|[String::operator < işleci](#operator-less-than)|Bir dize nesnesi değerini ikinci bir değerden daha küçük olup olmadığını belirten dize nesnesi.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Üstbilgi** vccorlib.h (varsayılan olarak dahil)  

 
## <a name="begin"></a>  String::Begin yöntemi
Bir işaretçi geçerli dize başlangıcını döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
char16* Begin()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli dize başlangıcını gösteren bir işaretçi.  
  
## <a name="compareordinal"></a>  String::CompareOrdinal yöntemi
İki karşılaştırır `String` nesneleri tarafından temsil edilen iki dize değerlerini karşılık gelen karakterleri sayısal değerleri değerlendirme nesneleri.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
int CompareOrdinal(  
           String^ str1,   
           String^ str2)  
  
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 İlk dize nesnesi.  
  
 `str2`  
 İkinci dize nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İki comparands sözcük ilişkisi belirten tamsayı. Aşağıdaki tabloda olası dönüş değerleri listelenmektedir.  
  
|Değer|Koşul|  
|-----------|---------------|  
|-1|`str1` olan değerinden `str2`.|  
|0|`str1` eşittir `str2`.|  
|1.|`str1` Daha fazla `str2`.|  
  


## <a name="concat"></a>  String::concat yöntemi
İki dize nesnelerini değerlerini art arda ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp    
String^ Concat( String^ str1, String^ str2)  
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 İlk dize nesnesi veya `null`.  
  
 `str2`  
 İkinci dize nesnesi veya `null`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni bir dize ^ nesne değeri olan değerlerin birleşimini, `str1` ve `str2`.  
  
 Varsa `str1` olan `null` ve `str2` değil, `str1` döndürülür. Varsa `str2` olan `null` ve `str1` değil, `str2` döndürülür. Varsa `str1` ve `str2` her ikisi de `null`, boş dize ("M") döndürülür.  
  


## <a name="data"></a>  String::Data yöntemi
Nesnenin veri arabelleği başına C tarzı dizisi olarak işaretçi döndüren `char16` (`wchar_t`) öğeleri.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
const char16* Data()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi başına bir `const char16` Unicode karakter dizisi (`char16` typedef için olan `wchar_t`).  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüştürmek için bu yöntemi kullanın `Platform::String^` için `wchar_t*`. Zaman `String` nesne kapsam dışında gider, veri işaretçi artık geçerli olması sağlanır. Özgün ömrü aşan veri depolamak için `String` nesne, kullanın [wcscpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) dizi kendiniz ayırmış olmanız belleğe kopyalamak için.  
  


## <a name="dispose"></a>  String::Dispose yöntemi
Serbest bırakma veya kaynakları serbest bırakır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
virtual override void Dispose()  
```  

## <a name="end"></a>  String::End yöntemi
Geçerli dize sonu geçmiş bir işaretçi döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
char16* End()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli dize sonu geçmiş bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 End() Begin() + uzunluk döndürür.  
  


## <a name="equals"></a>  String::Equals yöntemi
Belirtilen dize geçerli nesne ile aynı değere sahip olup olmadığını belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
bool String::Equals(Object^ str);  
  
bool String::Equals(String^ str);  
  
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 Karşılaştırma yapılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` varsa `str` geçerli nesneye eşit; Aksi takdirde, `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem eşdeğerdir [String::CompareOrdinal](#compareordinal). İlk aşırı içinde beklenen `str` parametresi bir dizeye dönüştürülür ^ nesnesi.  
  


## <a name="gethashcode"></a>  String::GetHashCode Yöntemi
Bu örneğin karma kodunu döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
virtual override int GetHashCode()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu örneğin karma kodu.  
  


## <a name="isempty"></a>  String::IsEmpty yöntemi
Geçerli dize nesnesi boş olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp    
bool IsEmpty()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Geçerli dize nesnesi ise `null` veya boş dize (L""); Aksi halde, `false`.  
  


## <a name="isfastpass"></a>  String::IsFastPass yöntemi
Nesne geçerli dize katılıyor olup olmadığını belirten bir *hızlı geçişi* işlemi. İşlemi hızlı geçişi, başvuru sayımı askıya alınır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp    
bool IsFastPass();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Geçerli dize nesnesi hızlı geçmiş Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Burada başvuruları sayılan bir nesne bir parametre ve çağrılan işlev yalnızca söz konusu nesne okuyan bir işlev çağrısında derleyici Güvenli başvuru sayımı askıya alıp arama performansı. Kodunuzu bu özellik ile yapmak için kullanışlı bir şey yoktur. Sistem tüm ayrıntılarını işler.  
  


## <a name="length"></a>  String::length yöntemi
Geçerli dize nesnesi karakter sayısını alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp    
unsigned int Length()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli dize nesnesi karakter sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir karakter içeren bir dize uzunluğu sıfır olur. Aşağıdaki dize uzunluğu 5.:  
  
```    
String^ str = "Hello";  
int len = str->Length(); //len = 5  
```  
  
 Tarafından döndürülen karakter dizisi [String::Data](#data) sonlandırma NULL ya da '\0' bir ek karakter içeriyor. Bu da iki bayt uzunluğundadır karakterdir.  
  


## <a name="operator-plus"></a>  String::operator + işleci
İki art arda ekler [dize](../cppcx/platform-string-class.md) yeni nesnelerine [dize](../cppcx/platform-string-class.md) nesnesi.
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
bool String::operator+( String^ str1, String^ str2)  
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 İlk `String` nesnesi.  
  
 `str2`  
 İkinci `String` içeriği için eklenecek nesne `str1`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` varsa `str1` eşittir `str2`; Aksi halde, `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç oluşturur bir `String^` iki işlenen veriler içeren nesne. Aşırı performans kritik olmadığında kolaylık sağlamak için kullanın. Birkaç çağrıları "`+`" bir işlevdeki fark edilmez büyük olasılıkla, ancak büyük nesneler veya metin veri sıkı döngü düzenleme, standart C++ mekanizmaları ve türlerini kullanın.  
  
##  <a name="operator-equality"></a> String::operator == işleci
Belirtilen iki dize nesnelerini aynı metin değeri içerip içermediğini belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp    
bool String::operator==( String^ str1, String^ str2)  
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 İlk dizesi Karşılaştırılacak nesne.  
  
 `str2`  
 İkinci dize Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` varsa içeriğini `str1` eşit olan `str2`; Aksi halde, `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç eşdeğerdir [String::CompareOrdinal](#compareordinal).  
  


##  <a name="operator-greater-than"></a>  String::operator&gt; 
Bir dize nesnesi değerini ikinci bir değerden daha büyük olup olmadığını belirten dize nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp    
bool String::operator>( String^ str1, String^ str2)  
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 İlk dize nesnesi.  
  
 `str2`  
 İkinci dize nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` varsa değerini `str1` değerinden daha büyük `str2`; Aksi halde, `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç açıkça çağrısına eşdeğerdir [String::CompareOrdinal](#compareordinal) ve bir sonuç sıfırdan büyük alma.  
  


## <a name="operator-greater-than-or-equals"></a> String::operator&gt;= 
Bir dize nesnesi değerini saniyenin değerine eşit veya daha büyük olup olmadığını belirten dize nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp    
bool String::operator>=( String^ str1, String^ str2) 
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 İlk dize nesnesi.  
  
 `str2`  
 İkinci dize nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` varsa değerini `str1` değerine eşit veya daha büyük olan `str2`; Aksi halde, `false`.  
  


## <a name="operator-inequality"></a> String::operator! = 
İki belirtilen dize nesnesi farklı değerlere sahip olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
bool String::operator!=( String^ str1, String^ str2)  
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 İlk dizesi Karşılaştırılacak nesne.  
  
 `str2`  
 İkinci dize Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` varsa `str1` eşit değil `str2`; Aksi halde, `false`.   


## <a name="operator-less-than"></a> String::operator&lt; 
Bir dize nesnesi değerini ikinci bir değerden daha küçük olup olmadığını belirten dize nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
bool String::operator<( String^ str1, String^ str2)  
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 İlk dize nesnesi.  
  
 `str2`  
 İkinci dize nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` varsa değerini `str1` değeri'dan küçük `str2`; Aksi halde, `false`.  
  
## <a name="ctor"></a> String::String Oluşturucusu
Giriş dizesi verilerin bir kopyasını, yeni bir String sınıfı örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp    
String();    
String(char16* s)  
String(char16* s, unsigned int n)  
```  
  
### <a name="parameters"></a>Parametreler  
 `s`  
 Bir dizesini başlatır geniş karakter dizisi. char16  
  
 `n`  
 Dize uzunluğu belirten bir sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Performans kritik ise ve kaynak dizesi ömrü denetlemek, kullanabileceğiniz [Platform::StringReference](../cppcx/platform-stringreference-class.md) dize yerine.  
### <a name="example"></a>Örnek  
  
```cpp  
String^ s = L"Hello!";  
```  
  
## <a name="tostring"></a> String::toString
Değeri geçerli dizesi ile aynı olan bir dize nesnesi döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
String^ String::ToString()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir dize nesnesi değeri geçerli dizesi ile aynıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)