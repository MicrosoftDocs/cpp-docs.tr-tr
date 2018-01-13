---
title: "İşlev aşırı yüklemesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- function overloading [C++], about function overloading
- function overloading
- declaring functions [C++], overloading
ms.assetid: 3c9884cb-1d5e-42e8-9a49-6f46141f929e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 785692992863e5a1cf3800f536d3f8fe3790b4a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="function-overloading"></a>İşlev Aşırı Yüklemesi
C++, aynı kapsamda aynı ada sahip birden fazla işlevin belirtilmesini sağlar. Bunlar, aşırı yüklenmiş işlevler olarak bilinir ve Aşırı Yükleme bölümünde ayrıntılı olarak açıklanmaktadır. Aşırı yüklenmiş işlevler, programcıların bir işlev için bağımsız değişkenlerin türlerine ve sayısına göre farklı semantikler sağlamasına imkan tanır.  
  
 Örneğin, bir **yazdırma** bir dize alır işlevi (veya **char \*** ) bağımsız değişkeni bir bağımsız değişken türü birden çok farklı görevleri gerçekleştirir **çift** . Aşırı yükleme, tekdüzen adlandırmaya imkan tanır ve programcıların `print_sz` veya `print_d` gibi adlar oluşturma zorunluluğunu ortadan kaldırır. Aşağıdaki tabloda, C++'nın aynı kapsamda aynı ana sahip işlev gruplarını birbirinden ayırmak için işlev bildiriminin hangi bölümlerini kullandığını gösterir.  
  
### <a name="overloading-considerations"></a>Aşırı Yükleme Hakkında Önemli Noktalar  
  
|İşlev Bildirimi Öğesi|Aşırı yükleme için kullanılır mı?|  
|----------------------------------|---------------------------|  
|İşlevin dönüş türü|Hayır|  
|Bağımsız değişkenlerin sayısı|Evet|  
|Bağımsız değişkenlerin türü|Evet|  
|Üç noktanın olması veya olmaması|Evet|  
|`typedef` adlarının kullanımı|Hayır|  
|Belirtilmemiş dizi sınırları|Hayır|  
|**const** veya `volatile` (aşağıya bakın)|Evet|  
  
 İşlev dönüş türü temel alınarak ayırt edilebilir rağmen bunlar bu temelinde aşırı yüklenemez.  `Const`veya `volatile` yalnızca temel olarak uygulamak için bir sınıfta kullanılabilir aşırı yüklemesi için kullanılan **bu** sınıfı, işlevin dönüş türü için bir işaretçi.  Diğer bir deyişle, aşırı yüklemesi yalnızca geçerlidir **const** veya `volatile` anahtar sözcüğünü izleyen bildiriminde işlevin bağımsız değişken listesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, aşırı yüklemenin nasıl kullanılabileceği gösterilmektedir.  
  
```  
// function_overloading.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <math.h>  
  
// Prototype three print functions.  
int print( char *s );                  // Print a string.  
int print( double dvalue );            // Print a double.  
int print( double dvalue, int prec );  // Print a double with a  
//  given precision.  
using namespace std;  
int main( int argc, char *argv[] )  
{  
const double d = 893094.2987;  
if( argc < 2 )  
    {  
// These calls to print invoke print( char *s ).  
print( "This program requires one argument." );  
print( "The argument specifies the number of" );  
print( "digits precision for the second number" );  
print( "printed." );  
exit(0);  
    }  
  
// Invoke print( double dvalue ).  
print( d );  
  
// Invoke print( double dvalue, int prec ).  
print( d, atoi( argv[1] ) );  
}  
  
// Print a string.  
int print( char *s )  
{  
cout << s << endl;  
return cout.good();  
}  
  
// Print a double in default precision.  
int print( double dvalue )  
{  
cout << dvalue << endl;  
return cout.good();  
}  
  
// Print a double in specified precision.  
//  Positive numbers for precision indicate how many digits  
//  precision after the decimal point to show. Negative  
//  numbers for precision indicate where to round the number  
//  to the left of the decimal point.  
int print( double dvalue, int prec )  
{  
// Use table-lookup for rounding/truncation.  
static const double rgPow10[] = {   
10E-7, 10E-6, 10E-5, 10E-4, 10E-3, 10E-2, 10E-1, 10E0,  
10E1,  10E2,  10E3,  10E4, 10E5,  10E6  
    };  
const int iPowZero = 6;  
// If precision out of range, just print the number.  
if( prec < -6 || prec > 7 )  
return print( dvalue );  
// Scale, truncate, then rescale.  
dvalue = floor( dvalue / rgPow10[iPowZero - prec] ) *  
rgPow10[iPowZero - prec];  
cout << dvalue << endl;  
return cout.good();  
}  
```  
  
 Yukarıdaki kod dosya kapsamındaki `print` işlevinin aşırı yüklenmesini gösterir.  
  
 Varsayılan bağımsız değişken işlev türünün bir parçası olarak kabul edilmez. Bu nedenle, aşırı yüklenmiş işlev seçmede kullanılmaz. Yalnızca kendi varsayılan bağımsız değişkenlerinde farklı olan iki işlevde, aşırı yüklenmiş işlevler yerine birden çok tanım dikkate alınır.  
  
 Varsayılan bağımsız değişkenleri, aşırı yükleme işleçleri için verilemez.  
  
  
## <a name="argument-matching"></a>Bağımsız Değişken Eşleştirme  
 Aşırı yüklenen işlevler için işlev çağrısında sağlanan bağımsız değişkenler geçerli kapsamdaki işlev bildirimleri en iyi eşleşmeyi için seçilir. Uygun bir işlev bulunursa, o işlev çağrılır. Bu bağlamda "uygun" aşağıdakilerden biri anlamına gelir:  
  
-   Tam bir eşleşme bulunamadı.  
  
-   Önemsiz dönüştürme gerçekleştirildi.  
  
-   Bir tam sayı yükseltme gerçekleştirildi.  
  
-   İstenen bağımsız değişken türü için standart bir dönüştürme yok.  
  
-   Bir kullanıcı tarafından tanımlanan dönüştürme (dönüşüm işleci veya oluşturucusu) istenen bağımsız değişken türü var.  
  
-   Elips tarafından temsil edilen bağımsız değişken bulunamadı.  
  
 Derleyici işlevleri her bağımsız değişkeni için aday kümesi oluşturur. Aday işlevler konumda gerçek bağımsız değişkeni biçimsel bağımsız değişken türüne dönüştürülebilir işlevlerdir.  
  
 Her bağımsız değişkeni için "en iyi eşleşen işlevleri" kümesi oluşturulur ve tüm ayarlar kesişimi seçili işlevdir. Kesişimi birden fazla işlev içeriyorsa, aşırı yüklemesi belirsiz ve bir hata oluşturur. Sonunda seçilen her zaman en az bir değişken için her bir grup işlevinde'den daha iyi bir eşleşme işlevdir. (Hiçbir Temizle kazanan varsa) durum bu değilse, işlev çağrısı bir hata oluşturur.  
  
 Aşağıdaki bildirimler göz önünde bulundurun (işlevleri işaretlenmiş `Variant 1`, `Variant 2`, ve `Variant 3`, kimliği'nde aşağıdaki tartışma için):  
  
```  
Fraction &Add( Fraction &f, long l );       // Variant 1  
Fraction &Add( long l, Fraction &f );       // Variant 2  
Fraction &Add( Fraction &f, Fraction &f );  // Variant 3  
  
Fraction F1, F2;  
```  
  
 Aşağıdaki deyim göz önünde bulundurun:  
  
```  
F1 = Add( F2, 23 );  
```  
  
 Önceki deyimi iki kümesi oluşturur:  
  
|Kümesi 1: Türü kesir işlevinin ilk bağımsız değişkeni olan aday İşlevler|Kümesi 2: Adayı işlevleri Whose ikinci bağımsız değişkeni dönüştürülebilir tür int|  
|--------------------------------------------------------------------------|-----------------------------------------------------------------------------------|  
|Değişken 1|Değişken 1 (`int` dönüştürülebilir `long` standart dönüştürme kullanılarak)|  
|Değişken 3||  
  
 2. ayarlamak işlevlerdir karşılığında var. işlevlerdir biçimsel parametresi türü için fiili parametre türünden örtük dönüşümler ve bu tür işlevler arasında "biçimsel parametresi türü için fiili parametre türü dönüştürme Maliyet" olduğu bir işlevi yoktur en küçük.  
  
 Bu iki kümenin kesişimini değişken 1'dir. Belirsiz işlev çağrısı örneğidir:  
  
```  
F1 = Add( 3, 6 );  
```  
  
 Önceki işlev çağrısı şu kümeler oluşturur:  
  
|Kümesi 1: Adayı işlevleri emin olan ilk bağımsız değişken türü int|Kümesi 2: Adayı işlevleri olduğunu sahip ikinci bağımsız değişkeni tür int|  
|---------------------------------------------------------------------|----------------------------------------------------------------------|  
|Değişken 2 (`int` dönüştürülebilir `long` standart dönüştürme kullanılarak)|Değişken 1 (`int` dönüştürülebilir `long` standart dönüştürme kullanılarak)|  
  
 Bu iki kesişimi boş olduğunu unutmayın. Bu nedenle, derleyici bir hata iletisi oluşturur.  
  
 Bağımsız değişken eşleştirme, bir işlev için  *n*  varsayılan bağımsız değişkenler olarak değerlendirilir  *n* + 1 ayrı işlevleri, her biri farklı sayıda bağımsız değişken.  
  
 Joker karakter üç nokta (...) görür; herhangi bir gerçek bağımsız değişken eşleşir. Aşırı yüklenmiş işlevi kümelerinizi onaylamadığından çok dikkatli tasarım değil, bu çok sayıda belirsiz kümelerine neden olabilir.  
  
> [!NOTE]
>  Bir işlev çağrısı karşılaşılanaa kadar aşırı yüklenmiş işlevlerin belirsizlik belirlenemiyor. Bu noktada, ayarlar her işlev çağrısı bağımsız değişkeni için oluşturulmuştur ve anlaşılır bir aşırı bulunup bulunmadığını belirleyebilirsiniz. Bu, bunlar belirli işlev çağrısı tarafından evoked kadar belirsizlikleri kodunuzda kalabileceği anlamına gelir.  
  
## <a name="argument-type-differences"></a>Bağımsız Değişken Türü Farkları  
 Aşırı yüklenmiş işlevler, farklı başlatıcıları olan bağımsız değişken türlerini ayırt eder. Bu nedenle, belirli türden bir bağımsız değişken ve bu türe yapılan bir başvuru, aşırı yükleme amaçları için aynı olarak kabul edilir. Aynı başlatıcıları aldıkları için aynı olarak kabul edilirler. Örneğin `max( double, double )`, `max( double &, double & )` ile aynı olarak kabul edilir. Böyle iki işlevin bildirilmesi bir hataya neden olur.  
  
 Değiştiren bir tür bağımsız değişkenleri aynı nedenden dolayı işlev **const** veya `volatile` aşırı yükleme amacıyla temel türü'den farklı kabul edilmediği.  
  
 Ancak, mekanizması aşırı yükleme işlevi tarafından tam başvuruları ayırt edebilirsiniz **const** ve `volatile` ve temel tür referansı. Bu, aşağıdaki gibi kodlara imkan tanır:  
  
```  
// argument_type_differences.cpp  
// compile with: /EHsc /W3  
// C4521 expected  
#include <iostream>  
  
using namespace std;  
class Over {  
public:  
   Over() { cout << "Over default constructor\n"; }  
   Over( Over &o ) { cout << "Over&\n"; }  
   Over( const Over &co ) { cout << "const Over&\n"; }  
   Over( volatile Over &vo ) { cout << "volatile Over&\n"; }  
};  
  
int main() {  
   Over o1;            // Calls default constructor.  
   Over o2( o1 );      // Calls Over( Over& ).  
   const Over o3;      // Calls default constructor.  
   Over o4( o3 );      // Calls Over( const Over& ).  
   volatile Over o5;   // Calls default constructor.  
   Over o6( o5 );      // Calls Over( volatile Over& ).  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```  
Over default constructor  
Over&  
Over default constructor  
const Over&  
Over default constructor  
volatile Over&  
```  
  
 İşaretçiler **const** ve `volatile` nesneler de değerlendirilir temel türü işaretçilerini farklı aşırı yükleme amacıyla.  
  
## <a name="argument-matching-and-conversions"></a>Bağımsız değişken eşleme ve dönüşümleri  
 İşlev bildirimleri değişkenlerinde karşı gerçek bağımsız değişkenler eşleşecek şekilde derleyici çalıştığında, tam eşleşme bulunamazsa, doğru türde elde etmek için standart veya kullanıcı tanımlı dönüşümler sağlayabilir. Bu kurallar tabi dönüşümleri uygulamadır:  
  
-   Birden fazla kullanıcı tanımlı dönüştürme içeren dönüşümleri dizilerini kabul edilmez.  
  
-   Ara dönüşümleri kaldırarak kısaltılmış dönüşümleri dizilerini kabul edilmez.  
  
 Dönüştürme, sonuç dizisi varsa, en iyi sıra eşleşen adı verilir. Nesne türüne dönüştürmek için çeşitli yolları vardır `int` yazmak için `unsigned long` standart dönüşümler kullanma (açıklanan [standart dönüşümler](../cpp/standard-conversions.md)):  
  
-   Dönüştür `int` için `long` ve sonra `long` için `unsigned long`.  
  
-   Dönüştür `int` için `unsigned long`.  
  
 İstenen hedef, ulaşır ilk sırası en iyi sıra eşleşen değildir — daha kısa bir dizi bulunmaktadır.  
  
 Aşağıdaki tabloda dönüşümleri, en iyi eşleşen hangi sırasıdır belirleme sınırlı etkisi Önemsiz dönüşümleri, adlı bir grup gösterir. Önemsiz dönüşümleri dizisi seçimine etkileyen örnekleri aşağıdaki tablonun listesinde ele alınmıştır.  
  
### <a name="trivial-conversions"></a>Önemsiz dönüşümleri  
  
|Türünden Dönüştür|Türüne dönüştürün|  
|-----------------------|---------------------|  
|*tür adı*|*tür adı***&**|  
|*tür adı***&**|*tür adı*|  
|*tür adı* **]**|*tür adı\**|  
|*tür adı* **(** *bağımsız değişken listesi* **)**|**(**  *\*türü adı* **) (** *bağımsız değişken listesi* **)**|  
|*tür adı*|**const** *türü adı*|  
|*tür adı*|`volatile`*türü adı*|  
|*tür adı\**|**const** *türü adı\**|  
|*tür adı\**|`volatile`*türü adı\**|  
  
 Dönüşümler girişimine dizisi aşağıdaki gibidir:  
  
1.  Tam eşleşme. Hangi işlev çağrılır ve işlev prototipi türleri bildirilen türler arasında tam bir eşleşme her zaman en iyi eşleşme olan. Önemsiz dönüşümleri dizilerini tam eşleşme sınıflandırılır. Ancak, bu dönüşümleri yapmayın sıraları Dönüştür sıraları iyi değerlendirilir:  
  
    -   İşaretçi işaretçisine gelen **const** (`type`  **\***  için **const** `type`  **\***  ).  
  
    -   İşaretçi işaretçisine gelen `volatile` (`type`  **\***  için `volatile` `type`  **\*** ).  
  
    -   Başvuru için başvurusundan **const** (`type`  **&**  için **const** `type`  **&** ).  
  
    -   Başvuru için başvurusundan `volatile` (`type`  **&**  için `volatile` `type`  **&** ).  
  
2.  Promosyon kullanarak eşleşir. Yalnızca tamsayı yükseltmeleri, gelen dönüşümleri içeren tam bir eşleşme olarak sınıflandırılan değil dizisi **float** için **çift**, ve önemsiz dönüşümleri promosyonlar kullanarak bir eşleşme olarak sınıflandırılmış. Eşleşen ne kadar iyi bir tam bir eşleşme olarak promosyonlar kullanarak bir eşleşme standart dönüşümler kullanarak eşleşmeden daha iyi olsa da.  
  
3.  Standart dönüşümler kullanarak eşleşir. Tam bir eşleşme veya yalnızca standart dönüşümler ve önemsiz dönüşümleri içeren promosyonlar kullanarak bir eşleşme olarak sınıflandırılan değil dizisi standart dönüşümler kullanarak bir eşleşme olarak sınıflandırılır. Bu kategoride aşağıdaki kurallar uygulanır:  
  
    -   Bir işaretçi dönüştürmeye türetilmiş bir sınıf, doğrudan veya dolaylı bir taban sınıfı için bir işaretçi dönüştürme için tercih **void \***  veya **const void \*** .  
  
    -   Bir işaretçi bir dönüştürme için bir taban sınıfı için bir işaretçi türetilmiş bir sınıf için temel sınıfı için doğrudan bir temel sınıf daha yakındır daha iyi bir eşleşme üretir. Aşağıdaki çizimde gösterildiği gibi sınıf hiyerarşisi olduğunu varsayın.  
  
 ![Tercih edilen dönüşümleri](../cpp/media/vc391t1.gif "vc391T1")  
Tercih edilen dönüşümleri gösteren grafik  
  
 Türüne dönüştürme `D*` yazmak için `C*` türüne dönüştürme için tercih edilir `D*` yazmak için `B*`. Benzer şekilde, türüne dönüştürme `D*` yazmak için `B*` türüne dönüştürme için tercih edilir `D*` yazmak için `A*`.  
  
 Bu aynı kural başvuru dönüşümleri uygular. Türüne dönüştürme `D&` yazmak için `C&` türüne dönüştürme için tercih edilir `D&` yazmak için `B&`ve benzeri.  
  
 Bu aynı kural işaretçi-üye dönüşümleri uygular. Türüne dönüştürme `T D::*` yazmak için `T C::*` türüne dönüştürme için tercih edilir `T D::*` yazmak için `T B::*`ve benzeri (burada `T` üye türü).  
  
 Önceki kural türetme yalnızca belirli bir yol geçerlidir. Aşağıdaki çizimde gösterilen grafik göz önünde bulundurun.  
  
 ![Çoklu &#45; tercih edilen dönüşümleri gösterir devralma](../cpp/media/vc391t2.gif "vc391T2")  
Tercih edilen dönüşümleri gösteren birden çok devralma grafiği  
  
 Türüne dönüştürme `C*` yazmak için `B*` türüne dönüştürme için tercih edilir `C*` yazmak için `A*`. Aynı yolda oldukları nedeni ve `B*` daha yakındır. Ancak, türüne dönüştürme `C*` yazmak için `D*` türüne dönüştürme için tercih değil `A*`; tercih yoktur dönüşümleri farklı yollar izledikleri için.  
  
1.  Kullanıcı tanımlı dönüşümler ile eşleşir. Bu sıra tam bir eşleşme, promosyonlar kullanarak bir eşleşme veya standart dönüşümler kullanarak bir eşleşme olarak sınıflandırılan olamaz. Sıra, yalnızca kullanıcı tanımlı dönüşümler, standart dönüşümler veya kullanıcı tanımlı dönüşümler ile bir eşleşme olarak sınıflandırılan Önemsiz dönüşümleri içermelidir. Kullanıcı tanımlı dönüşümler ile eşleşmeyi üç nokta ile bir eşleşme ancak standart dönüşümler ile bir eşleşme olarak kadar iyi bir eşleşme değerinden daha iyi bir eşleşme olarak kabul edilir.  
  
2.  Üç nokta ile eşleşir. Üç nokta bildiriminde eşleşen dizisi üç nokta ile bir eşleşme olarak sınıflandırılır. Bu zayıf eşleşme olarak kabul edilir.  
  
 Yerleşik yükseltme veya dönüştürme yok, kullanıcı tanımlı dönüşümler uygulanır. Bu dönüşümleri eşleşen bağımsız değişken türü temel alınarak seçilir. Aşağıdaki kod göz önünde bulundurun:  
  
```  
// argument_matching1.cpp  
class UDC  
{  
public:  
   operator int()  
   {  
      return 0;  
   }  
   operator long();  
};  
  
void Print( int i )  
{  
};  
  
UDC udc;  
  
int main()  
{  
   Print( udc );  
}  
```  
  
 Sınıfı için kullanılabilen kullanıcı tanımlı dönüşümler `UDC` türünden olan `int` ve türü **uzun**. Bu nedenle, eşleşen nesne türünü dönüştürmelerde derleyici göz önünde bulundurur: `UDC`. Bir dönüştürme `int` var olduğundan ve onu seçilir.  
  
 Bağımsız değişken eşleştirme işlemi sırasında standart dönüşümler bağımsız değişkeni ve kullanıcı tanımlı bir dönüştürme sonucu için uygulanabilir. Bu nedenle, aşağıdaki kod çalışır:  
  
```  
void LogToFile( long l );  
...  
UDC udc;  
LogToFile( udc );  
```  
  
 Önceki örnekte, kullanıcı tanımlı dönüştürme **long işleci**, dönüştürmek için çağrılan `udc` yazmak için **uzun**. Türü için kullanıcı tanımlı dönüştürme, **uzun** olsaydı tanımlanan dönüştürme gibi proceeded: türü `UDC` türü dönüştürülmüş `int` kullanıcı tanımlı dönüştürme kullanarak. Ardından standart dönüştürme türünden `int` yazmak için **uzun** bildirimi değişkeninde eşleşecek şekilde uygulanmış.  
  
 Bağımsız değişken eşleşmesi için tüm kullanıcı tanımlı dönüşümler gerekirse standart dönüşümler en iyi eşleşmeyi hesaplanırken kullanılmaz. Kullanıcı tanımlı bir dönüştürme birden fazla aday işlevi gerektirir olsa bile bu geçerlidir; Böyle bir durumda işlevleri eşit olarak kabul edilir. Örneğin:  
  
```  
// argument_matching2.cpp  
// C2668 expected  
class UDC1  
{  
public:  
   UDC1( int );  // User-defined conversion from int.  
};  
  
class UDC2  
{  
public:  
   UDC2( long ); // User-defined conversion from long.  
};  
  
void Func( UDC1 );  
void Func( UDC2 );  
  
int main()  
{  
   Func( 1 );  
}  
```  
  
 Her iki sürümü `Func` türüne dönüştürmek için kullanıcı tanımlı bir dönüştürme gerektiren `int` sınıfı tür bağımsız değişkeni için. Olası dönüşümleri şunlardır:  
  
-   Türünden dönüştürmek `int` yazmak için `UDC1` (kullanıcı tanımlı dönüştürme).  
  
-   Türünden dönüştürmek `int` yazmak için **uzun**; ardından türüne dönüştürme `UDC2` (iki aşamalı dönüştürme).  
  
 Standart dönüştürme gibi kullanıcı tanımlı dönüştürme bu ikinci gerektirir olsa bile, iki dönüşümleri hala eşit olarak kabul edilir.  
  
> [!NOTE]
>  Kullanıcı tanımlı dönüşümler dönüştürme yapım veya dönüştürme (dönüştürme işlevi) başlatma tarafından kabul edilir. Her iki yöntem en iyi eşleşmeyi değerlendirirken eşit olarak kabul edilir.  
  
## <a name="argument-matching-and-the-this-pointer"></a>Bağımsız değişken eşleştirme ve this işaretçisi  
 Sınıf üyesi işlevleri, `static` olarak bildirilip bildirilmediklerine bağlı olarak farklı bir şekilde değerlendirilir. Statik olmayan işlevlerde `this` işaretçisini sağlayan örtük bağımsız değişken olduğu için statik olmayan işlevlerin statik işlevlere göre bir bağımsız değişkeni daha olduğu kabul edilir; aksi takdirde, benzer olarak bildirilirler.  
  
 Bu statik olmayan üye işlevleri, örtük `this` işaretçisinin işlevi çağırmak için kullanılan nesne türüyle eşleşmesini veya aşırı yüklenmiş işleçler için ilk bağımsız değişkenin işlecin uygulandığı nesneyle eşleşmesini gerektirir. (Aşırı yüklenmiş işleçler hakkında daha fazla bilgi için bkz: [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md).)  
  
 Aşırı yüklenmiş işlevlerdeki diğer bağımsız değişkenlerin aksine, `this` işaretçi bağımsız değişkeni eşleştirilmeye çalışılırken hiçbir geçici nesne kullanıma sunulmaz ve hiçbir dönüşüm işlemi denenmez.  
  
 Zaman `->` üye seçimi işleci sınıfının üye işlevini erişmek için kullanılan `class_name`, `this` işaretçi değişkeni olan bir tür `class_name * const`. Üyeleri olarak bildirilen varsa `const` veya `volatile`, türleri `const class_name * const` ve `volatile class_name * const`sırasıyla.  
  
 `.` üye seçme işleci, örtük `&` (adres) işlecinin nesne adının önüne eklenmesi dışında tamamen aynı şekilde çalışır. Aşağıdaki örnekte, bunun nasıl çalıştığı gösterilmektedir:  
  
```  
// Expression encountered in code  
obj.name  
  
// How the compiler treats it  
(&obj)->name  
```  
  
 Sol işleneni `->*` ve `.*` (işaretçiden üyeye) işleçleri aynı şekilde ele `.` ve `->` bağımsız değişken eşleştirme göre (üye seçim) işleçleri.  
  
## <a name="restrictions"></a>Kısıtlamalar  
 Birkaç kısıtlamaları aşırı yüklenmiş işlevlerin kabul edilebilir bir kümesini yöneten:  
  
-   Aşırı yüklenmiş işlevlerin kümesinde iki tüm işlevler farklı bağımsız değişken listeleri olması gerekir.  
  
-   Tek başına, dönüş türüne göre aynı türdeki bağımsız değişken listeleriyle işlevler aşırı yüklemesi bir hatadır.  
  
     **Microsoft özel**  
  
 Aşırı yüklenebilir **new işleci** yalnızca temeline göre dönüş türü — özellikle, belirtilen bellek modeli değiştiricisi temel alınarak.  
  
**SON Microsoft özel**  
  
-   Üye işlevleri yalnızca tek bir statik olmanın ve diğer statik olmayan temel alarak aşırı yüklenemez.  
  
-   `typedef`bildirimleri yeni türleri tanımlamaz; Bunlar, mevcut türleri için eş anlamlı sözcükleri tanıtır. Tekrar yüklemesi mekanizması etkilemez. Aşağıdaki kod göz önünde bulundurun:  
  
    ```  
    typedef char * PSTR;  
  
    void Print( char *szToPrint );  
    void Print( PSTR szToPrint );  
    ```  
  
     Önceki iki işlevleri aynı bağımsız değişken listeleri vardır. `PSTR`türü için eş anlamlı olduğundan **char \*** . Üye kapsamda bu kodu bir hata oluşturur.  
  
-   Numaralandırılmış türler farklı türler ve Aşırı yüklenen işlevler arasında ayrım yapmak için kullanılır.  
  
-   Türleri "dizisi" ve "işaretçi" Aşırı yüklenen işlevler arasında ayrım amacıyla aynı olarak kabul edilir. Bu, yalnızca ayrı olarak dimensioned diziler için geçerlidir. Bu nedenle, aşağıdaki işlevleri çakışma aşırı yüklenmiş ve bir hata iletisi oluşturur:  
  
    ```  
    void Print( char *szToPrint );  
    void Print( char szToPrint[] );  
    ```  
  
     Çarp dimensioned diziler için ikinci ve tüm izleyen boyutları türünün bir parçası olarak kabul edilir. Bu nedenle, bunlar Aşırı yüklenen işlevler arasında ayrım kullanılır:  
  
    ```  
    void Print( char szToPrint[] );  
    void Print( char szToPrint[][7] );  
    void Print( char szToPrint[][9][42] );  
    ```  
  
## <a name="declaration-matching"></a>Bildirim eşleştirme  
 Her iki işlev bildirimleri aynı kapsamda aynı ada sahip aynı işlevi veya aşırı yüklenmiş iki ayrı işlev başvurabilir. Bağımsız değişken olarak listeleniyorsa (önceki bölümde açıklandığı gibi) eşdeğer türlerle bağımsız bildirimleri içeren, aynı işleve işlev bildirimleri bakın. Aksi takdirde, aşırı yüklemesi kullanılarak seçilen iki farklı işlevler başvurun.  
  
 Sınıf kapsamı kesinlikle gözlenir; Bu nedenle, bir taban sınıf içinde bildirilen bir işlev işlevi olarak aynı kapsamda türetilen bir sınıfta bildirilmedi. Temel sınıfı işlevinde aynı ada sahip bir türetilmiş sınıfta bir işlev bildirilirse, türetilmiş sınıf işlev aşırı yüklemesi neden yerine temel sınıf işlevi gizler.  
  
 Blok kapsamı kesinlikle gözlenir; Bu nedenle, dosya kapsamda bildirilen işlevi bir işlevi olarak aynı kapsamda yerel olarak bildirilmedi. Yerel olarak bildirilen bir işlev dosya kapsamda bildirilen bir işlevi olarak aynı ada sahipse, yerel olarak bildirilen işlev aşırı yüklemesi neden yerine dosya kapsamlı işlevi gizler. Örneğin:  
  
```  
// declaration_matching1.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
void func( int i )  
{  
    cout << "Called file-scoped func : " << i << endl;  
}  
  
void func( char *sz )  
{  
   cout << "Called locally declared func : " << sz << endl;  
}  
  
int main()  
{  
   // Declare func local to main.  
   extern void func( char *sz );  
  
   func( 3 );   // C2664 Error. func( int ) is hidden.  
   func( "s" );  
}  
```  
  
 Önceki kod iki işlev tanımları gösterir `func`. Türünde bir bağımsız değişken tanımı `char *` için yerel olan `main` nedeniyle `extern` deyimi. Bu nedenle, bir bağımsız değişken türü tanımı `int` gizlenir ve ilk çağrıda `func` hatalı.  
  
 Aşırı yüklenmiş üye işlevleri için işlev'in farklı sürümlerini farklı erişim ayrıcalıkları verilebilir. Bunlar hala kapsayan sınıfı kapsamında olduğu kabul edilir ve böylece aşırı yüklenmiş işlevlerdir. Aşağıdaki kodda göz önünde bulundurun üye fonksiyonu `Deposit` aşırı yüklendi; bir sürümüdür ortak, diğer özel.  
  
 Bu örnek amacı sağlamaktır bir `Account` içinde doğru parolayı mevduatları gerçekleştirmek için gereken sınıfı. Bu, aşırı yüklemesi kullanılarak gerçekleştirilir.  
  
 Unutmayın çağrısı `Deposit` içinde `Account::Deposit` özel üye işlevi çağırır. Bu çağrı doğru olduğundan `Account::Deposit` bir üye işlevidir ve bu nedenle özel üyeleri sınıfın erişimi.  
  
```  
// declaration_matching2.cpp  
class Account  
{  
public:  
   Account()  
   {  
   }  
   double Deposit( double dAmount, char *szPassword );  
  
private:  
   double Deposit( double dAmount )  
   {  
      return 0.0;  
   }  
   int Validate( char *szPassword )  
   {  
      return 0;  
   }  
  
};  
  
int main()  
{  
    // Allocate a new object of type Account.  
    Account *pAcct = new Account;  
  
    // Deposit $57.22. Error: calls a private function.  
    // pAcct->Deposit( 57.22 );  
  
    // Deposit $57.22 and supply a password. OK: calls a  
    //  public function.  
    pAcct->Deposit( 52.77, "pswd" );  
}  
  
double Account::Deposit( double dAmount, char *szPassword )  
{  
   if ( Validate( szPassword ) )  
      return Deposit( dAmount );  
   else  
      return 0.0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [işlevler [C++]](../cpp/functions-cpp.md)