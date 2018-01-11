---
title: Sonek ifadeleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- operators [C++], postfix
- postfix expressions
- expressions [C++], postfix
ms.assetid: 7ac62a57-06df-422f-b012-a75b37d7cb9b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8b965027e67cc2b2581c2ab00e51d2be7a899302
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="postfix-expressions"></a>Sonek İfadeleri
Sonek ifadeleri, birincil ifadelerden veya içindeki son ek işleçlerinin bir birincil ifadeyi izlediği ifadelerden oluşur. Sonek işleçleri aşağıdaki tabloda listelenmiştir.  
  
### <a name="postfix-operators"></a>Sonek İşleçleri  
  
|İşleç Adı|İşleç Gösterimi|  
|-------------------|-----------------------|  
|[Alt simge işleci](../cpp/subscript-operator.md)|**[ ]**|  
|[İşlev çağırma işleci](../cpp/function-call-operator-parens.md)|**( )**|  
|[Açık tür dönüştürme işleci](../cpp/explicit-type-conversion-operator-parens.md)|*tür adı* **)**|  
|[Üye erişimi işleci](../cpp/member-access-operators-dot-and.md)|**.** veya**->**|  
|[Sonek artırma işleci](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[Sonek azaltma işleci](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**--**|  
  
 Aşağıdaki sözdizimi olası sonek ifadeleri açıklar:  
  
```  
  
      primary-expression   
postfix-expression[expression]postfix-expression(expression-list)simple-type-name(expression-list)postfix-expression.namepostfix-expression->namepostfix-expression++postfix-expression--cast-keyword < typename > (expression )typeid ( typename )  
```  
  
 *Sonek ifade* birincil ifadesi veya başka bir sonek ifadesi yukarıdaki olabilir.  Bkz: **birincil ifadeler**.  Soldan sağa sonek ifade grubu, bu şekilde ifadelerin aşağıdaki gibi zincirleme yapılmasına olanak verir:  
  
```  
func(1)->GetValue()++  
```  
  
 Yukarıdaki ifadede, func birincil ifade, func(1) bir işlev sonek ifadesi, func(1)->GetData sınıfın bir üyesini belirten sonek ifadesi, func(1)->GetData() başka bir işlev sonek ifadesi, tüm ifade ise GetData'nın dönüş değerini arttıran bir sonek ifadesidir.  İfadenin bir bütün olarak anlamı, "call" işlevinin bağımsız değişken olarak 1 geçirmesi ve dönüş değeri olarak sınıfa yönelik bir işaretçi almaktır.  Ardından o sınıfta GetValue() çağrılır ve döndürülen değer arttırılır.  
  
 Yukarıda listelenen ifadeler atama ifadeleridir, yani bu ifadelerin sonucu bir r-değeri olmalıdır.  
  
 Sonek ifade formu  
  
```  
simple-type-name ( expression-list )  
```  
  
 oluşturucunun çağrılacağını belirtir.  Basit tür adı bir temel tür ise, ifade listesi tek bir ifade olmalıdır ve bu ifade, ifadenin değerinin temel türe atanacağını belirtir.  Bu tür bir atama ifadesi bir oluşturucuyu taklit eder.  Bu form temel türlerin ve sınıfların aynı sözdizimini kullanılarak oluşturulmasına izin verdiğinden, bu form özellikle şablon sınıfları tanımlarken yararlıdır.  
  
 *Cast anahtar sözcüğü* biri `dynamic_cast`, `static_cast` veya `reinterpret_cast`.  Daha fazla bilgi bulunabilir **dynamic_cast**, **static_cast** ve **reinterpet_cast**.  
  
 `typeid` işleci bir sonek ifade olarak kabul edilir.  Bkz: **typeid işleci**.  
  
## <a name="formal-and-actual-arguments"></a>Resmi ve gerçek bağımsız değişkenler  
 Çağıran programlar çağrılan işlevlere "gerçek bağımsız değişkenler" içinde bilgi aktarır. Çağrılan işlevler, karşılık gelen "biçimsel bağımsız değişkenleri" kullanarak bilgilere erişir.  
  
 Bir işlev çağrıldığında, aşağıdaki görevler yerine getirilir:  
  
-   Tüm gerçek bağımsız değişkenler (arayan tarafından sağlananlar) değerlendirilir. Bu bağımsız değişkenlerin değerlendirilmesine ilişkin herhangi bir sıralama yoktur, ancak işleve girmeden önce tüm bağımsız değişkenler değerlendirilir ve tüm yan etkiler tamamlanır.  
  
-   Her biçimsel bağımsız değişken, ifade listesi içinde karşılık gelen gerçek bağımsız değişkeniyle başlatılır. (Biçimsel bağımsız değişken, işlev üstbilgisinde bildirilen ve bir işlevin gövdesinde kullanılan bir bağımsız değişkendir.) Dönüştürme işlemleri neredeyse başlatma ile gerçekleştirilir; hem standart hem de kullanıcı tanımlı dönüştürmeler, gerçek bir bağımsız değişkeni doğru türe dönüştürürken gerçekleştirilir. Gerçekleştirilen başlatma aşağıdaki kodda kavramsal olarak gösterilmiştir:  
  
    ```  
    void Func( int i ); // Function prototype  
    ...  
    Func( 7 );          // Execute function call  
    ```  
  
     Çağrıdan önceki kavramsal başlatmalar şunlardır:  
  
    ```  
    int Temp_i = 7;  
    Func( Temp_i );  
    ```  
  
     Başlatmanın, parantez sözdizimi yerine eşittir işareti sözdizimi kullanılıyormuş gibi yapıldığına dikkat edin. Değeri işleve geçirmeden önce `i` öğesinin bir kopyası oluşturulur. (Daha fazla bilgi için bkz: [başlatıcıları](../cpp/initializers.md) ve [dönüşümleri](../cpp/user-defined-type-conversions-cpp.md)).  
  
     Bu nedenle, işlev prototipi (bildirim) türünde bir bağımsız değişken için çağırırsa **uzun**, ve gerçek bağımsız değişken türü çağıran program sağlarsa `int`, gerçek bağımsız değişkeni bir standart tür dönüştürme kullanılarak yükseltilir türü için **uzun** (bkz [standart dönüşümler](../cpp/standard-conversions.md)).  
  
     Kendisi için biçimsel bağımsız değişkenin türüne yönelik standart veya kullanıcı tanımlı bir dönüştürme bulunmayan bir gerçek bağımsız değişken sağlamak hatadır.  
  
     Sınıf türünde gerçek bağımsız değişkenler için, biçimsel bağımsız değişken, sınıfın oluşturucusu çağrılarak başlatılır. (Bkz [oluşturucular](../cpp/constructors-cpp.md) bu özel sınıf üyesi işlevleri hakkında daha fazla bilgi için.)  
  
-   İşlev çağrısı yürütülür.  
  
 Aşağıdaki program parçası, bir işlev çağrısı göstermektedir:  
  
```  
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
  
 Zaman `func` biçimsel parametresi main adlı `param1` değeri ile başlatılmış `i` (`i` türüne dönüştürülüp **uzun** standart kullanarak doğru türde karşılık gelecek şekilde dönüştürme işlemi) ve biçimsel parametresi `param2` değeri ile başlatılmış `j` (`j` türüne dönüştürülüp **çift** standart dönüştürme kullanarak).  
  
## <a name="treatment-of-argument-types"></a>Bağımsız değişken türlerinin işlenmesi  
 Biçimsel bağımsız değişkenler, bir işlev gövdesi içinde const türleri değiştirilemez olarak bildirildi. İşlevler türünde değil herhangi bir bağımsız değişken değiştirebilirsiniz **const**. Ancak, değişikliği işlev için yerel olan ve gerçek bağımsız değişkeni bir nesne türü için bir başvuru olduğundan sürece gerçek bağımsız değişkeninin değeri etkilemez **const**.  
  
 Aşağıdaki işlevleri bu kavramların bazıları gösterilmektedir:  
  
```  
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
 İşlevler, iki yöntemden birini kullanarak işlevi tanımında belirtilenden daha az sayıda bağımsız değişken kabul etmek için bildirilebilir: üç nokta (`...`) veya varsayılan bağımsız değişkenler.  
  
 Üç nokta bağımsız değişken gerekli olabilir ancak sayısını ve türlerini bildiriminde belirtilmeyen gösterir. Bu C++ avantajlarından biri hedefini uğratır çünkü bu normalde zayıf C++ programlama uygulamadır: tür güvenliği. Farklı dönüşümleri resmi ve gerçek bağımsız değişken türleri bilinen bu işlevlere üç nokta ile bildirilen işlevler uygulanır:  
  
-   Gerçek bağımsız değişken türü ise **float**, yazmak için yükseltilen **çift** işlev çağrısı önce.  
  
-   Tüm imzalı veya imzasız `char`, **kısa**, numaralandırılmış türü veya bit alan işaretli veya işaretsiz bir için dönüştürülür `int` tam sayı yükseltme kullanma.  
  
-   Sınıf türü herhangi bir bağımsız değişken bir veri yapısı geçirilen değer tarafından; ikili yerine (varsa) sınıfının kopya Oluşturucu çağırarak kopyalayarak kopyası oluşturulur.  
  
 Üç nokta, kullandıysanız, son bağımsız değişken listesinde bildirilmesi gerekir. Açıklamalara değişken sayıda bağımsız değişken geçirme hakkında daha fazla bilgi için bkz: [va_arg, va_start ve va_list](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
 CLR programlama varsayılan bağımsız değişkenleri hakkında daha fazla bilgi için bkz: [değişken bağımsız değişken listeleri (...) (C + +/ CLI) ](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).  
  
 Varsayılan bağımsız değişkenler, bağımsız değişken yok işlev çağrısında sağlanırsa varsayın değer belirtmenize olanak verir. Aşağıdaki kod parçası varsayılan bağımsız değişkenler nasıl çalıştığı gösterilmektedir. Varsayılan bağımsız değişkenleri belirtme kısıtlamaları hakkında daha fazla bilgi için bkz: [varsayılan bağımsız değişkenler](../cpp/default-arguments.md).  
  
```  
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
  
 Bir işlev önceki program bildirir `print`, iki bağımsız değişkeni alır. Ancak, ikinci bağımsız değişkeni `terminator`, varsayılan bir değeri yok `"\n"`. İçinde **ana**, ilk iki çağrıları `print` yazdırılan dizeyi sonlandırmak için yeni bir satır sağlamak varsayılan ikinci bağımsız değişkeni izin verin. Üçüncü çağrısı ikinci bağımsız değişkeni için açık bir değer belirtir. Programdan alınan çıkış  
  
```  
hello,  
world!  
good morning, sunshine.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade Türleri](../cpp/types-of-expressions.md)