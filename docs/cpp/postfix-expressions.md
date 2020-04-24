---
title: Sonek İfadeleri
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], postfix
- postfix expressions
- expressions [C++], postfix
ms.assetid: 7ac62a57-06df-422f-b012-a75b37d7cb9b
ms.openlocfilehash: 897eb80c713f786ecf0f7e6c9cf24cd8bdfc0aa8
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032284"
---
# <a name="postfix-expressions"></a>Sonek İfadeleri

Sonek ifadeleri, birincil ifadelerden veya içindeki son ek işleçlerinin bir birincil ifadeyi izlediği ifadelerden oluşur. Sonek işleçleri aşağıdaki tabloda listelenmiştir.

### <a name="postfix-operators"></a>Sonek İşleçleri

|İşleç Adı|İşleç Gösterimi|
|-------------------|-----------------------|
|[Alt yazı işleci](../cpp/subscript-operator.md)|**[ ]**|
|[Fonksiyon çağrı operatörü](../cpp/function-call-operator-parens.md)|**( )**|
|[Açık tür dönüştürme işleci](../cpp/explicit-type-conversion-operator-parens.md)|*tür adı* **( )**|
|[Üye erişim operatörü](../cpp/member-access-operators-dot-and.md)|**.** Veya**->**|
|[Sonek artırma işleci](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**++**|
|[Sonek azaltma işleci](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**--**|

Aşağıdaki sözdizimi olası sonek ifadeleri açıklar:

```
primary-expression
postfix-expression[expression]postfix-expression(expression-list)simple-type-name(expression-list)postfix-expression.namepostfix-expression->namepostfix-expression++postfix-expression--cast-keyword < typename > (expression )typeid ( typename )
```

Yukarıdaki *postfix-ifadesi* birincil bir ifade veya başka bir postfix ifadesi olabilir.  **Birincil ifadelere**bakın.  Soldan sağa sonek ifade grubu, bu şekilde ifadelerin aşağıdaki gibi zincirleme yapılmasına olanak verir:

```cpp
func(1)->GetValue()++
```

Yukarıdaki ifadede, `func` birincil ifadedir, `func(1)` işlev postfix `func(1)->GetValue` ifadesidir, sınıfın bir üyesini belirten `func(1)->GetValue()` bir postfix ifadesidir, başka bir işlev postfix ifadesidir ve tüm ifade GetValue'In dönüş değerini artan bir postfix ifadesidir.  İfadenin bir bütün olarak anlamı, "call" işlevinin bağımsız değişken olarak 1 geçirmesi ve dönüş değeri olarak sınıfa yönelik bir işaretçi almaktır.  Sonra `GetValue()` o sınıfı arayın, sonra döndürülen değeri artım.

Yukarıda listelenen ifadeler atama ifadeleridir, yani bu ifadelerin sonucu bir r-değeri olmalıdır.

Sonek ifade formu

```cpp
simple-type-name ( expression-list )
```

oluşturucunun çağrılacağını belirtir.  Basit tür adı bir temel tür ise, ifade listesi tek bir ifade olmalıdır ve bu ifade, ifadenin değerinin temel türe atanacağını belirtir.  Bu tür bir atama ifadesi bir oluşturucuyu taklit eder.  Bu form temel türlerin ve sınıfların aynı sözdizimini kullanılarak oluşturulmasına izin verdiğinden, bu form özellikle şablon sınıfları tanımlarken yararlıdır.

*Döküm anahtar kelime* **dynamic_cast**biridir , **static_cast** veya **reinterpret_cast**.  Daha fazla bilgi **dynamic_cast**bulunabilir , **static_cast** ve **reinterpet_cast**.

**Typeid** işleci bir postfix ifadesi olarak kabul edilir.  **Bkz. typeid işleci.**

## <a name="formal-and-actual-arguments"></a>Biçimsel ve gerçek bağımsız değişkenler

Çağıran programlar çağrılan işlevlere "gerçek bağımsız değişkenler" içinde bilgi aktarır. Çağrılan işlevler, karşılık gelen "biçimsel bağımsız değişkenleri" kullanarak bilgilere erişir.

Bir işlev çağrıldığında, aşağıdaki görevler yerine getirilir:

- Tüm gerçek bağımsız değişkenler (arayan tarafından sağlananlar) değerlendirilir. Bu bağımsız değişkenlerin değerlendirilmesine ilişkin herhangi bir sıralama yoktur, ancak işleve girmeden önce tüm bağımsız değişkenler değerlendirilir ve tüm yan etkiler tamamlanır.

- Her biçimsel bağımsız değişken, ifade listesi içinde karşılık gelen gerçek bağımsız değişkeniyle başlatılır. (Biçimsel bir bağımsız değişken, işlev üstbilgisinde bildirilen ve bir işlevin gövdesinde kullanılan bir bağımsız değişkendir.) Dönüşümler, başlangıç olarak yapılır — gerçek bir bağımsız değişkeni doğru türe dönüştürmede hem standart hem de kullanıcı tarafından tanımlanan dönüşümler gerçekleştirilir. Gerçekleştirilen başlatma aşağıdaki kodda kavramsal olarak gösterilmiştir:

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

   Başlatmanın, parantez sözdizimi yerine eşittir işareti sözdizimi kullanılıyormuş gibi yapıldığına dikkat edin. Değeri işleve geçirmeden önce `i` öğesinin bir kopyası oluşturulur. (Daha fazla bilgi [için, Bkz. Başlangıç Layıcılar](../cpp/initializers.md) ve [Dönüşümler).](../cpp/user-defined-type-conversions-cpp.md)

   Bu nedenle, işlev prototipi (bildirimi) **uzun**tür bir argüman gerektiriyorsa ve arama programı tür **int**gerçek bir argüman sağlarsa, gerçek bağımsız değişken **uzun** yazmak için standart bir tür dönüştürme kullanılarak teşvik edilir (Bkz. [Standart Dönüşümler).](../cpp/standard-conversions.md)

   Kendisi için biçimsel bağımsız değişkenin türüne yönelik standart veya kullanıcı tanımlı bir dönüştürme bulunmayan bir gerçek bağımsız değişken sağlamak hatadır.

   Sınıf türünde gerçek bağımsız değişkenler için, biçimsel bağımsız değişken, sınıfın oluşturucusu çağrılarak başlatılır. (Bu özel sınıf üye işlevler hakkında daha fazla şey için [Yapıcılar'a](../cpp/constructors-cpp.md) bakın.)

- İşlev çağrısı yürütülür.

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

Ana `func` dan çağrıldığında, resmi `param1` parametre değeri ile `i` `i` başharfe dönüştürülür (standart bir dönüştürme kullanarak doğru türe karşılık `param2` gelecek şekilde **uzun** yazıya dönüştürülür) ve resmi parametre değeri ile başharfe dönüştürülür `j` (`j` standart dönüştürme kullanılarak **çift** tipe dönüştürülür).

## <a name="treatment-of-argument-types"></a>Argüman türlerinin tedavisi

Const türleri olarak bildirilen biçimsel bağımsız değişkenler bir işlevin gövdesi içinde değiştirilemez. İşlevler **tür const**olmayan herhangi bir bağımsız değişkeni değiştirebilirsiniz. Ancak, değişiklik işlev için yerel dir ve gerçek bağımsız değişken tür **const**olmayan bir nesneye bir başvuru olmadığı sürece gerçek bağımsız değişkenin değerini etkilemez.

Aşağıdaki işlevler bu kavramlardan bazılarını göstermektedir:

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

## <a name="ellipsis-and-default-arguments"></a>Elips ve varsayılan bağımsız değişkenler

İşlevler, iki yöntemden birini kullanarak işlev tanımında belirtilenden daha az`...`bağımsız değişken kabul eder: elipsis ( ) veya varsayılan bağımsız değişkenler.

Elips, bağımsız değişkenlerin gerekli olabileceğini, ancak sayı ve türlerin bildirimde belirtilmediğini belirtir. Bu normalde kötü C++ programlama uygulamasıdır çünkü C++'ın avantajlarından birini yener: tür güvenliği. Resmi ve fiili bağımsız değişken türlerinin bilindiği işlevlerden farklı dönüşümler elipsile bildirilen işlevlere uygulanır:

- Gerçek bağımsız değişken tür **float**ise, işlev çağrısından önce **çift** tür etmek için teşvik edilir.

- İmzalanmış veya imzalanmamış **char,** **kısa,** numaralandırılmış tür veya bit alanı, integral promosyonu kullanılarak imzalı veya imzasız bir **int'e** dönüştürülür.

- Sınıf türünden herhangi bir bağımsız değişken, veri yapısı olarak değere göre geçirilir; kopya, sınıfın kopya oluşturucusu (varsa) çağırmak yerine ikili kopyalama ile oluşturulur.

Elipsler, kullanılırsa, bağımsız değişken listesinde son olarak bildirilmelidir. Değişken sayıda bağımsız değişken geçirme hakkında daha fazla bilgi *için, Çalışma Zamanı Kitaplığı Başvurusu'nda* [va_arg, va_start ve va_list](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) tartışmasına bakın.

CLR programlamada varsayılan bağımsız değişkenler hakkında bilgi için değişken [bağımsız değişken listeleri (...) (C++/CLI)](../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md)bakın.

Varsayılan bağımsız değişkenler, işlev çağrısında hiçbiri sağlanmışsa bağımsız değişkenin varsayması gereken değeri belirtmenizi sağlar. Aşağıdaki kod parçası varsayılan bağımsız değişkenlerin nasıl çalıştığını gösterir. Varsayılan bağımsız değişkenler belirtme kısıtlamaları hakkında daha fazla bilgi için varsayılan [bağımsız değişkenler'e](../cpp/default-arguments.md)bakın.

```cpp
// expre_Ellipsis_and_Default_Arguments.cpp
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

Önceki program, iki bağımsız `print`değişken gerektiren bir işlev bildirir. Ancak, ikinci bağımsız değişken, *sonlandırıcı,* varsayılan `"\n"`bir değere sahiptir. In, `main`ilk iki `print` çağrı, yazdırılan dize sonlandırmak için yeni bir satır sağlamak için varsayılan ikinci bağımsız değişken izin verir. Üçüncü çağrı, ikinci bağımsız değişken için açık bir değer belirtir. Programdan çıktı

```Output
hello,
world!
good morning, sunshine.
```

## <a name="see-also"></a>Ayrıca bkz.

[İfade Türleri](../cpp/types-of-expressions.md)
