---
title: Sonek İfadeleri
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], postfix
- postfix expressions
- expressions [C++], postfix
ms.assetid: 7ac62a57-06df-422f-b012-a75b37d7cb9b
ms.openlocfilehash: 9a5c99c78623f2192b59a73f270f3ad5d2a34516
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231175"
---
# <a name="postfix-expressions"></a>Sonek İfadeleri

Sonek ifadeleri, birincil ifadelerden veya içindeki son ek işleçlerinin bir birincil ifadeyi izlediği ifadelerden oluşur. Sonek işleçleri aşağıdaki tabloda listelenmiştir.

### <a name="postfix-operators"></a>Sonek İşleçleri

|İşleç Adı|İşleç Gösterimi|
|-------------------|-----------------------|
|[Alt simge işleci](../cpp/subscript-operator.md)|**[ ]**|
|[İşlev çağrısı işleci](../cpp/function-call-operator-parens.md)|**( )**|
|[Açık tür dönüştürme işleci](../cpp/explicit-type-conversion-operator-parens.md)|*tür adı* **()**|
|[Üye erişim işleci](../cpp/member-access-operators-dot-and.md)|**.** veya**->**|
|[Sonek artırma işleci](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**++**|
|[Sonek azaltma işleci](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**--**|

Aşağıdaki sözdizimi olası sonek ifadeleri açıklar:

```
primary-expression
postfix-expression[expression]postfix-expression(expression-list)simple-type-name(expression-list)postfix-expression.namepostfix-expression->namepostfix-expression++postfix-expression--cast-keyword < typename > (expression )typeid ( typename )
```

Yukarıdaki *sonek ifadesi* bir [birincil ifade](primary-expressions.md) veya başka bir sonek ifadesi olabilir. Soldan sağa sonek ifade grubu, bu şekilde ifadelerin aşağıdaki gibi zincirleme yapılmasına olanak verir:

```cpp
func(1)->GetValue()++
```

Yukarıdaki ifadede `func` bir birincil ifade, bir `func(1)` işlev sonek ifadesi, `func(1)->GetValue` sınıfın bir üyesini belirten bir sonek ifadesi, `func(1)->GetValue()` başka bir işlev sonek ifadesi ise ve tüm ifade, GetValue dönüş değerini arttırmadan bir sonek ifadedir.  İfadenin bir bütün olarak anlamı, "call" işlevinin bağımsız değişken olarak 1 geçirmesi ve dönüş değeri olarak sınıfa yönelik bir işaretçi almaktır.  Sonra `GetValue()` Bu sınıfa çağrı yapın ve ardından döndürülen değeri artırın.

Yukarıda listelenen ifadeler atama ifadeleridir, yani bu ifadelerin sonucu bir r-değeri olmalıdır.

Sonek ifade formu

```cpp
simple-type-name ( expression-list )
```

oluşturucunun çağrılacağını belirtir.  Basit tür adı bir temel tür ise, ifade listesi tek bir ifade olmalıdır ve bu ifade, ifadenin değerinin temel türe atanacağını belirtir.  Bu tür bir atama ifadesi bir oluşturucuyu taklit eder.  Bu form temel türlerin ve sınıfların aynı sözdizimini kullanılarak oluşturulmasına izin verdiğinden, bu form özellikle şablon sınıfları tanımlarken yararlıdır.

*Cast-anahtar sözcüğü* **`dynamic_cast`** , veya ' den **`static_cast`** biridir **`reinterpret_cast`** .  Ve ' de daha fazla bilgi [`dynamic_cast`](dynamic-cast-operator.md) bulunabilir [`static_cast`](static-cast-operator.md) [`reinterpet_cast`](reinterpret-cast-operator.md) .

**`typeid`** İşleci bir sonek ifadesi olarak kabul edilir.  Bkz. **TypeId işleci**.

## <a name="formal-and-actual-arguments"></a>Biçimsel ve gerçek bağımsız değişkenler

Çağıran programlar çağrılan işlevlere "gerçek bağımsız değişkenler" içinde bilgi aktarır. Çağrılan işlevler, karşılık gelen "biçimsel bağımsız değişkenleri" kullanarak bilgilere erişir.

Bir işlev çağrıldığında, aşağıdaki görevler yerine getirilir:

- Tüm gerçek bağımsız değişkenler (arayan tarafından sağlananlar) değerlendirilir. Bu bağımsız değişkenlerin değerlendirilmesine ilişkin herhangi bir sıralama yoktur, ancak işleve girmeden önce tüm bağımsız değişkenler değerlendirilir ve tüm yan etkiler tamamlanır.

- Her biçimsel bağımsız değişken, ifade listesi içinde karşılık gelen gerçek bağımsız değişkeniyle başlatılır. (Biçimsel bağımsız değişken, işlev üstbilgisinde belirtilen ve bir işlevin gövdesinde kullanılan bir bağımsız değişkendir.) Dönüştürmeler, başlatma işlemi tarafından yapılır — standart ve Kullanıcı tanımlı dönüştürmeler, gerçek bir bağımsız değişkeni doğru türe dönüştürerek gerçekleştirilir. Gerçekleştirilen başlatma aşağıdaki kodda kavramsal olarak gösterilmiştir:

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

   Başlatmanın, parantez sözdizimi yerine eşittir işareti sözdizimi kullanılıyormuş gibi yapıldığına dikkat edin. Değeri işleve geçirmeden önce `i` öğesinin bir kopyası oluşturulur. (Daha fazla bilgi için bkz. [başlatıcılar](../cpp/initializers.md) ve [dönüştürmeler](../cpp/user-defined-type-conversions-cpp.md)).

   Bu nedenle, işlev prototipi (bildirim) türünde bir bağımsız değişken çağırırsa **`long`** ve çağıran program türünde gerçek bir bağımsız değişken sağlarsa **`int`** , gerçek bağımsız değişken türüne standart bir tür dönüştürmesi kullanılarak yükseltilir **`long`** (bkz. [Standart dönüştürmeler](../cpp/standard-conversions.md)).

   Kendisi için biçimsel bağımsız değişkenin türüne yönelik standart veya kullanıcı tanımlı bir dönüştürme bulunmayan bir gerçek bağımsız değişken sağlamak hatadır.

   Sınıf türünde gerçek bağımsız değişkenler için, biçimsel bağımsız değişken, sınıfın oluşturucusu çağrılarak başlatılır. (Bu özel sınıf üye işlevleri hakkında daha fazla bilgi için bkz. [oluşturucular](../cpp/constructors-cpp.md) .)

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

`func`Main 'den çağrıldığında, biçimsel parametre `param1` değeri ile başlatılır `i` ( `i` **`long`** Standart bir dönüştürme kullanılarak doğru türe karşılık gelen türüne dönüştürülür) ve biçimsel parametre `param2` değeri ile başlatılır `j` ( `j` **`double`** Standart bir dönüştürme kullanılarak türe dönüştürülür).

## <a name="treatment-of-argument-types"></a>Bağımsız değişken türlerini işleme

Tür olarak belirtilen biçimsel bağımsız değişkenler **`const`** bir işlevin gövdesinde değiştirilemez. İşlevler, türünde olmayan herhangi bir bağımsız değişkeni değiştirebilir **`const`** . Ancak, değişiklik, işlev için yereldir ve gerçek bağımsız değişken türünde olmayan bir nesneye başvuru olmadığı müddetçe gerçek bağımsız değişkenin değerini etkilemez **`const`** .

Aşağıdaki işlevler bu kavramların bazılarını göstermektedir:

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

## <a name="ellipsis-and-default-arguments"></a>Üç nokta ve varsayılan bağımsız değişkenler

İşlevler, iki yöntemden birini kullanarak işlev tanımında belirtilenden daha az bağımsız değişken kabul edecek şekilde bildirilebilecek: üç nokta ( `...` ) veya varsayılan bağımsız değişkenler.

Üç nokta bağımsız değişkenlerin gerekli olabileceğini, ancak bildirimin ve türlerin bildirimde belirtilmiyor olduğunu gösterir. C++: tür güvenliği avantajlarından birini erteler olduğundan, bu normalde kötü C++ programlama uygulamasıdır. Farklı dönüştürmeler, biçimsel ve gerçek bağımsız değişken türlerinin bilinen işlevlerine kıyasla üç nokta ile belirtilen işlevlere uygulanır:

- Gerçek bağımsız değişken türü ise **`float`** , **`double`** işlev çağrısından önce türüne yükseltilir.

- Herhangi **`signed char`** **`unsigned char`** bir or, **`signed short`** veya **`unsigned short`** , numaralandırılmış tür veya bit alanı bir ya da bir **`signed int`** **`unsigned int`** integral promosyonu kullanılarak dönüştürülür.

- Sınıf türündeki herhangi bir bağımsız değişken değer tarafından veri yapısı olarak geçirilir; kopya, sınıfın kopya oluşturucusunu (varsa) çağırarak yerine ikili kopyalama tarafından oluşturulur.

Kullanılıyorsa üç nokta bağımsız değişken listesinde son olarak bildirilmelidir. Değişken sayıda bağımsız değişken geçirme hakkında daha fazla bilgi için, *çalışma zamanı kitaplığı başvurusunda* [va_arg, va_start ve va_list](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) tartışmalarına bakın.

CLR programlamada varsayılan bağımsız değişkenler hakkında bilgi için bkz. [değişken bağımsız değişken listeleri (...) (C++/CLI)](../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

Varsayılan bağımsız değişkenler, işlev çağrısında hiçbiri sağlanmadığında bir bağımsız değişken değeri belirtmenize olanak tanır. Aşağıdaki kod parçası, varsayılan bağımsız değişkenlerin nasıl çalıştığını gösterir. Varsayılan bağımsız değişkenleri belirtme kısıtlamaları hakkında daha fazla bilgi için bkz. [Varsayılan bağımsız değişkenler](../cpp/default-arguments.md).

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

Önceki program, `print` iki bağımsız değişken alan bir işlev bildirir. Ancak, ikinci bağımsız değişkeni *Sonlandırıcı*, varsayılan bir değere sahiptir `"\n"` . `main`' De, `print` varsayılan ikinci bağımsız değişkene, yazdırılmış dizeyi sonlandırmak için yeni bir satır sağlamak üzere ilk iki çağrı. Üçüncü çağrı ikinci bağımsız değişken için açık bir değer belirtir. Programın çıktısı

```Output
hello,
world!
good morning, sunshine.
```

## <a name="see-also"></a>Ayrıca bkz.

[Ifade türleri](../cpp/types-of-expressions.md)
