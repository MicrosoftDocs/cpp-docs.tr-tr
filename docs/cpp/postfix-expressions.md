---
title: Sonek ifadeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], postfix
- postfix expressions
- expressions [C++], postfix
ms.assetid: 7ac62a57-06df-422f-b012-a75b37d7cb9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6299249b477b568579063f7ee61060514c3028bd
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948237"
---
# <a name="postfix-expressions"></a>Sonek İfadeleri
Sonek ifadeleri, birincil ifadelerden veya içindeki son ek işleçlerinin bir birincil ifadeyi izlediği ifadelerden oluşur. Sonek işleçleri aşağıdaki tabloda listelenmiştir.  
  
### <a name="postfix-operators"></a>Sonek İşleçleri  
  
|İşleç Adı|İşleç Gösterimi|  
|-------------------|-----------------------|  
|[Alt simge işleci](../cpp/subscript-operator.md)|**[ ]**|  
|[İşlev çağırma işleci](../cpp/function-call-operator-parens.md)|**( )**|  
|[Açık tür dönüştürme işleci](../cpp/explicit-type-conversion-operator-parens.md)|*tür adı* **)**|  
|[Üye erişimi işleci](../cpp/member-access-operators-dot-and.md)|**.** veya **->**|  
|[Sonek artırma işleci](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[Sonek azaltma işleci](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**--**|  
  
 Aşağıdaki sözdizimi olası sonek ifadeleri açıklar:  
  
```  
  
primary-expression   
postfix-expression[expression]postfix-expression(expression-list)simple-type-name(expression-list)postfix-expression.namepostfix-expression->namepostfix-expression++postfix-expression--cast-keyword < typename > (expression )typeid ( typename )  
```  
  
 *Sonek ifadesi* yukarıdaki birincil ifade veya başka bir sonek ifadesi olabilir.  Bkz: **birincil ifadeler**.  Soldan sağa sonek ifade grubu, bu şekilde ifadelerin aşağıdaki gibi zincirleme yapılmasına olanak verir:  
  
```cpp 
func(1)->GetValue()++  
```  
  
 Yukarıdaki ifadede, func birincil ifade, func(1) bir işlev sonek ifadesi, func(1)->GetData sınıfın bir üyesini belirten sonek ifadesi, func(1)->GetData() başka bir işlev sonek ifadesi, tüm ifade ise GetData'nın dönüş değerini arttıran bir sonek ifadesidir.  İfadenin bir bütün olarak anlamı, "call" işlevinin bağımsız değişken olarak 1 geçirmesi ve dönüş değeri olarak sınıfa yönelik bir işaretçi almaktır.  Ardından o sınıfta GetValue() çağrılır ve döndürülen değer arttırılır.  
  
 Yukarıda listelenen ifadeler atama ifadeleridir, yani bu ifadelerin sonucu bir r-değeri olmalıdır.  
  
 Sonek ifade formu  
  
```cpp 
simple-type-name ( expression-list )  
```  
  
 oluşturucunun çağrılacağını belirtir.  Basit tür adı bir temel tür ise, ifade listesi tek bir ifade olmalıdır ve bu ifade, ifadenin değerinin temel türe atanacağını belirtir.  Bu tür bir atama ifadesi bir oluşturucuyu taklit eder.  Bu form temel türlerin ve sınıfların aynı sözdizimini kullanılarak oluşturulmasına izin verdiğinden, bu form özellikle şablon sınıfları tanımlarken yararlıdır.  
  
 *Cast-keyword* biri **dynamic_cast**, **static_cast** veya **reinterpret_cast**.  Daha fazla bilgi bulunabilir **dynamic_cast**, **static_cast** ve **reinterpet_cast**.  
  
 **TypeID** işleci bir sonek ifade olarak kabul edilir.  Bkz: **typeid işleci**.  
  
## <a name="formal-and-actual-arguments"></a>Resmi ve gerçek bağımsız değişkenler  
 Çağıran programlar çağrılan işlevlere "gerçek bağımsız değişkenler" içinde bilgi aktarır. Çağrılan işlevler, karşılık gelen "biçimsel bağımsız değişkenleri" kullanarak bilgilere erişir.  
  
 Bir işlev çağrıldığında, aşağıdaki görevler yerine getirilir:  
  
-   Tüm gerçek bağımsız değişkenler (arayan tarafından sağlananlar) değerlendirilir. Bu bağımsız değişkenlerin değerlendirilmesine ilişkin herhangi bir sıralama yoktur, ancak işleve girmeden önce tüm bağımsız değişkenler değerlendirilir ve tüm yan etkiler tamamlanır.  
  
-   Her biçimsel bağımsız değişken, ifade listesi içinde karşılık gelen gerçek bağımsız değişkeniyle başlatılır. (Biçimsel bağımsız değişken, işlev üstbilgisinde bildirilen ve bir işlevin gövdesinde kullanılan bir bağımsız değişkendir.) Dönüştürme işlemleri neredeyse başlatma ile gerçekleştirilir; hem standart hem de kullanıcı tanımlı dönüştürmeler, gerçek bir bağımsız değişkeni doğru türe dönüştürürken gerçekleştirilir. Gerçekleştirilen başlatma aşağıdaki kodda kavramsal olarak gösterilmiştir:  
  
    ```cpp 
    void Func( int i ); // Function prototype  
    ...  
    Func( 7 );          // Execute function call  
    ```  
  
     Çağrıdan önceki kavramsal başlatmalar şunlardır:  
  
    ```cpp 
    int Temp_i = 7;  
    Func( Temp_i );  
    ```  
  
     Başlatmanın, parantez sözdizimi yerine eşittir işareti sözdizimi kullanılıyormuş gibi yapıldığına dikkat edin. Değeri işleve geçirmeden önce `i` öğesinin bir kopyası oluşturulur. (Daha fazla bilgi için [başlatıcılar](../cpp/initializers.md) ve [dönüştürmeler](../cpp/user-defined-type-conversions-cpp.md)).  
  
     Bu nedenle, işlev prototipi (bildirim) türünde bir bağımsız değişken için çağırırsa **uzun**, ve çağıran program gerçek bağımsız değişken türü sağlarsa **int**, gerçek bağımsız değişken kullanarak yükseltilmiş bir yazmak için standart bir tür dönüştürme **uzun** (bkz [standart dönüştürmeler](../cpp/standard-conversions.md)).  
  
     Kendisi için biçimsel bağımsız değişkenin türüne yönelik standart veya kullanıcı tanımlı bir dönüştürme bulunmayan bir gerçek bağımsız değişken sağlamak hatadır.  
  
     Sınıf türünde gerçek bağımsız değişkenler için, biçimsel bağımsız değişken, sınıfın oluşturucusu çağrılarak başlatılır. (Bkz [oluşturucular](../cpp/constructors-cpp.md) bu özel sınıf üye işlevleri hakkında daha fazla bilgi için.)  
  
-   İşlev çağrısı yürütülür.  
  
 Aşağıdaki program parçası, bir işlev çağrısı göstermektedir:  
  
```cpp 
// expre_Formal_and_Actual_Arguments.cpp  
void func( long param1, double param2 );  
  
int main()  
{  
    long i = 1;  
    double j = 2;  
  
    // Call func with actual arguments i and j.  
    func( i, j );  
}  
  
// Define func with formal parameters param1 and param2.  
void func( long param1, double param2 )  
{  
}  
```  
  
 Zaman `func` ana biçimsel parametre olarak adlandırılan `param1` değeriyle başlatılır `i` (`i` türüne dönüştürülür **uzun** standart kullanarak doğru türe karşılık olarak dönüştürme) ve biçimsel parametre `param2` değeriyle başlatılır `j` (`j` türüne dönüştürülür **çift** standart bir dönüştürme kullanılarak).  
  
## <a name="treatment-of-argument-types"></a>Bağımsız değişken türlerinin işlenmesi  
 Biçimsel bağımsız değişkenler, const türleri işlevinin gövdesi içinde değiştirilemez olarak bildirilmiş. İşlevler, türde değil herhangi bir bağımsız değişken değiştirebilirsiniz **const**. Ancak, değişiklik işlevi için yereldir ve gerçek bağımsız değişken türü bir nesneye bir başvuru değilse gerçek bağımsız değişkenin değerini etkilemez **const**.  
  
 Aşağıdaki işlevleri bazı bu kavramları göstermektedir:  
  
```cpp 
// expre_Treatment_of_Argument_Types.cpp  
int func1( const int i, int j, char *c ) {  
   i = 7;   // C3892 i is const.  
   j = i;   // value of j is lost at return  
   *c = 'a' + j;   // changes value of c in calling function  
   return i;  
}  
  
double& func2( double& d, const char *c ) {  
   d = 14.387;   // changes value of d in calling function.  
   *c = 'a';   // C3892 c is a pointer to a const object.  
    return d;  
}  
```  
  
## <a name="ellipses-and-default-arguments"></a>Üç noktalar ve varsayılan bağımsız değişkenler  
 İşlevleri, iki yöntemden birini kullanarak işlev tanımında belirtilenden daha az sayıda bağımsız değişken kabul etmeleri bildirilebilir: üç nokta (`...`) ya da varsayılan bağımsız değişkenler.  
  
 Elipsler bağımsız değişkenlerin gerekli olabileceğini, ancak sayı ve türlerinin bildirimde belirtilmeyen gösterir. Avantajlarından biri C++ programlamasıdır normalde kötü olmasıdır: tür güvenliği. Farklı dönüştürmeler, kendisi için biçimsel ve fiili bağımsız değişken türleri bilinen işlevlerden üç noktayla belirtilen işlevlere uygulanır:  
  
-   Gerçek bağımsız değişken türü ise **float**, türüne yükseltilir **çift** işlev çağrısından önce.  
  
-   Tüm işaretli veya işaretlenmemiş **char**, **kısa**, numaralandırılan tür veya bit alanı, bir işaretli veya işaretsiz bir için dönüştürülür **int** integral yükseltme kullanılarak.  
  
-   Sınıf türünün herhangi bir bağımsız değişken bir veri yapısı olarak değere göre geçirilir; ikili yerine sınıfın kopya oluşturucusunu (varsa) çağırarak kopyalayarak kopya oluşturulur.  
  
 Elipsler kullandıysanız, son bağımsız değişken listesinde bildirilmesi gerekir. Değişken sayıda bağımsız değişken geçirme hakkında daha fazla bilgi için, bkz [va_arg, va_start ve va_list](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
 CLR programlamada varsayılan bağımsız değişkenler hakkında daha fazla bilgi için bkz: [değişken bağımsız değişken listeleri (...) (C + +/ CLI) ](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).  
  
 Varsayılan bağımsız değişken bağımsız değişken yok işlev çağrısında sağlanırsa değer belirtmenize olanak verir. Aşağıdaki kod parçası, varsayılan bağımsız değişkenler nasıl çalıştığını gösterir. Varsayılan bağımsız değişkenleri belirtme sınırlamaları hakkında daha fazla bilgi için bkz: [varsayılan bağımsız değişkenler](../cpp/default-arguments.md).  
  
```cpp 
// expre_Ellipses_and_Default_Arguments.cpp  
// compile with: /EHsc  
#include <iostream>  
  
// Declare the function print that prints a string,  
// then a terminator.  
void print( const char *string,  
            const char *terminator = "\n" );  
  
int main()  
{  
    print( "hello," );  
    print( "world!" );  
  
    print( "good morning", ", " );  
    print( "sunshine." );  
}  
  
using namespace std;  
// Define print.  
void print( const char *string, const char *terminator )  
{  
    if( string != NULL )  
        cout << string;  
  
    if( terminator != NULL )  
        cout << terminator;  
}  
```  
  
 Önceki program bir işlev bildirir `print`, bu iki bağımsız değişkeni alır. Ancak, ikinci bağımsız değişkeni `terminator`, varsayılan bir değeri yok `"\n"`. İçinde `main`, ilk iki çağrıları `print` varsayılan ikinci bağımsız yazdırılan dizeyi sonlandırmak için yeni bir satır sağlamasına izin verin. Üçüncü çağrı, ikinci bağımsız değişkeni için açık bir değer belirtir. Programdan alınan çıkış  
  
```Output 
hello,  
world!  
good morning, sunshine.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade Türleri](../cpp/types-of-expressions.md)