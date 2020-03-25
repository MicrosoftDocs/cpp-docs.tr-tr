---
title: Kullanıcı tanımlı tür dönüştürmeleri (C++)
ms.date: 11/04/2016
f1_keywords:
- explicit_cpp
helpviewer_keywords:
- constructors [C++], and constants
- conversion functions [C++]
- explicit keyword [C++]
- type conversion
- constructors [C++], drawbacks
- conversion constructors
- type conversion [C++], explicit conversion
- coercion [C++]
- conversions [C++], explicit
- objects [C++], converting
- conversion functions [C++], rules for declaring
- declaring functions [C++], conversion functions
- functions [C++], conversion
- converting objects
- constructors [C++], conversion
- conversions [C++], by constructors
- data type conversion [C++], explicit
ms.assetid: d40e4310-a190-4e95-a34c-22c5c20aa0b9
ms.openlocfilehash: 055b5bd5c82e4f0be449d548de25267eabef47bd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187940"
---
# <a name="user-defined-type-conversions-c"></a>Kullanıcı tanımlı tür dönüştürmeleri (C++)

*Dönüştürme* , farklı türde bir değerden bir türden yeni bir değer oluşturur. *Standart dönüştürmeler* C++ dilde yerleşiktir ve yerleşik türlerini destekler ve Kullanıcı tanımlı türler arasında, öğesinden veya arasında dönüştürme gerçekleştirmek için *Kullanıcı tanımlı dönüştürmeler* oluşturabilirsiniz.

Standart dönüştürmeler yerleşik türler arasında, devralma, void işaretçileri ve null işaretçilerle ilgili türlere işaretçiler veya başvurular arasında dönüştürme gerçekleştirir. Daha fazla bilgi için bkz. [Standart dönüştürmeler](../cpp/standard-conversions.md). Kullanıcı tanımlı dönüştürmeler, Kullanıcı tanımlı türler arasında veya Kullanıcı tanımlı türler ile yerleşik türler arasında dönüşümler gerçekleştirir. Bunları, [dönüştürme oluşturucuları](#ConvCTOR) veya [dönüştürme işlevleri](#ConvFunc)olarak uygulayabilirsiniz.

Programcılar, bir tür dönüştürme ya da doğrudan başlatma veya örtük olarak bir tür için çağrı yaptığı zaman, dil ya da program programcı tarafından verilenin dışında farklı bir tür aradığında, dönüştürme açık olabilir.

Örtük dönüştürmeler şu durumlarda denenir:

- Bir işleve sağlanan bağımsız değişken, eşleşen parametreyle aynı türde değil.

- Bir işlevden döndürülen değer, işlev dönüş türü ile aynı türde değil.

- Başlatıcı ifadesi, başlatmakta olduğu nesneyle aynı türde değil.

- Koşullu bir deyimi, döngü yapısını veya anahtarı denetleyen bir ifade onu denetlemek için gereken sonuç türüne sahip değil.

- Bir işlece sağlanan işlenen, eşleşen işlenen parametresi ile aynı türde değil. Yerleşik işleçler için her iki işlenen de aynı türde olmalıdır ve her ikisini temsil eden ortak bir türe dönüştürülür. Daha fazla bilgi için bkz. [Standart dönüştürmeler](standard-conversions.md). Kullanıcı tanımlı işleçler için, her işlenenin eşleşen işlenen parametresiyle aynı türde olması gerekir.

Bir standart dönüştürme örtük dönüştürmeyi tamamlayamadığında, derleyici Kullanıcı tanımlı bir dönüştürme kullanabilir ve isteğe bağlı olarak ek bir standart dönüştürme ile bunu tamamlar.

Aynı dönüştürmeyi gerçekleştiren iki veya daha fazla Kullanıcı tanımlı dönüştürme bir dönüştürme sitesinde kullanılabilir olduğunda, dönüştürme belirsiz olarak kabul edilir. Bu tür belirsizlikleri bir hatadır çünkü derleyici kullanılabilir dönüştürmelerin hangi birini seçmesi gerektiğini belirleyemez. Ancak, aynı dönüştürmeyi gerçekleştirmenin birden çok yolunu tanımlamak yalnızca bir hata değildir çünkü kullanılabilir dönüştürmeler kümesi kaynak koddaki farklı konumlarda farklı olabilir — Örneğin, bir kaynak dosyasına hangi başlık dosyalarının ekleneceğini bağlı olarak). Dönüştürme sitesinde yalnızca bir dönüştürme kullanılabilir olduğu sürece, belirsizlik yoktur. Belirsiz dönüştürmeler ortaya çıkabilecek birçok yol vardır, ancak en sık görülen değerler şunlardır:

- Birden çok devralma. Dönüştürme birden fazla temel sınıfta tanımlandı.

- Belirsiz işlev çağrısı. Dönüştürme, hedef türün bir dönüştürme Oluşturucusu ve kaynak türünün bir dönüştürme işlevi olarak tanımlanır. Daha fazla bilgi için bkz. [dönüştürme işlevleri](#ConvFunc).

Yalnızca ilgili türün adını daha fazla niteleyerek veya amacınızı açıklığa kavuşturmak için açık bir atama gerçekleştirerek, bir belirsizliğe genellikle çözüm yapabilirsiniz.

Hem dönüştürme oluşturucuları hem de dönüştürme işlevleri üye erişim denetimi kurallarına uyar, ancak dönüştürmenin erişilebilirliği yalnızca ve belirsiz bir dönüştürme belirlenebileceği zaman kabul edilir. Bu, rekabet dönüştürmesinin erişim düzeyi kullanılmasını engelleyebilse bile dönüştürmenin belirsiz olabileceği anlamına gelir. Üye erişilebilirliği hakkında daha fazla bilgi için bkz. [üye Access Control](../cpp/member-access-control-cpp.md).

## <a name="the-explicit-keyword-and-problems-with-implicit-conversion"></a>Örtük dönüştürme ile açık anahtar sözcük ve sorunlar

Varsayılan olarak, Kullanıcı tanımlı bir dönüştürme oluşturduğunuzda Derleyici bunu örtük dönüştürmeler gerçekleştirmek için kullanabilir. Bazen bu, istediğiniz şeydir, ancak örtük dönüştürmeler yaparken derleyiciye kılavuzluk eden basit kuralların, kendisine istemediğiniz kodu kabul etmesine yol açabilir.

Örtük dönüştürmeye sorun oluşmasına neden olabilecek bir iyi bilinen örnek, **bool**değerine dönüştürülür. Bir Boolean bağlamında kullanılabilecek bir sınıf türü oluşturmak isteyebileceğiniz pek çok neden vardır — örneğin, bir **IF** ifadesini veya döngüsünü denetlemek için kullanılabilmesi, ancak derleyici yerleşik bir türe Kullanıcı tanımlı bir dönüştürme gerçekleştirdiğinde, derleyicinin daha sonra ek bir standart dönüştürme uygulamasına izin verilir. Bu ek standart dönüştürmenin amacı, **Short** 'dan **int**'e yükseltme gibi şeyler için izin vermek, ancak örneğin **bool** 'dan **int**'e kadar, sınıf türünün hiçbir şekilde amaçlanmayan tamsayı bağlamlarda kullanılmasını sağlar. Bu sorun, *güvenli bool sorunu*olarak bilinir. Bu tür bir sorun, **Açık** anahtar sözcüğünün yardım edebilir.

**Explicit** anahtar sözcüğü derleyiciye belirtilen dönüştürmenin örtük dönüştürmeler gerçekleştirmek için kullanılamayacağını söyler. **Açık** anahtar sözcüğünün tanıtılmasından önce örtük dönüştürmelerin sözdizimsel kolaylığını istediyseniz, örtük dönüştürmenin bazen oluşturduğu veya daha az kullanışlı, adlandırılmış dönüştürme işlevlerini geçici bir çözüm olarak kullandığı istenmeyen sonuçları kabul etmeniz gerekiyordu. Artık **explicit** anahtar sözcüğünü kullanarak yalnızca açık yayınlar veya doğrudan başlatma gerçekleştirmek için kullanılabilecek ve güvenli bool sorunu tarafından muaf olan sorunların türüne yol açabilecek uygun dönüştürmeler oluşturabilirsiniz.

**Explicit** anahtar sözcüğü, c++ 98 ' den bu yana dönüştürme oluşturuculara ve c++ 11 ' den beri işlevleri dönüştürmek için uygulanabilir. Aşağıdaki bölümler, **explicit** anahtar sözcüğünün nasıl kullanılacağına ilişkin daha fazla bilgi içerir.

## <a name="conversion-constructors"></a><a name="ConvCTOR"></a>Dönüştürme oluşturucuları

Dönüştürme oluşturucuları Kullanıcı tanımlı veya yerleşik türlerden Kullanıcı tanımlı bir türe dönüşümler tanımlar. Aşağıdaki örnek, yerleşik türden **Double** 'tan kullanıcı tanımlı `Money`dönüştüren bir dönüştürme oluşturucusunu gösterir.

```cpp
#include <iostream>

class Money
{
public:
    Money() : amount{ 0.0 } {};
    Money(double _amount) : amount{ _amount } {};

    double amount;
};

void display_balance(const Money balance)
{
    std::cout << "The balance is: " << balance.amount << std::endl;
}

int main(int argc, char* argv[])
{
    Money payable{ 79.99 };

    display_balance(payable);
    display_balance(49.95);
    display_balance(9.99f);

    return 0;
}
```

`display_balance`, `Money`türünde bir bağımsız değişken alan ve bağımsız değişkeni doğru türde olduğundan, işleve yapılan ilk çağrının bir dönüştürme gerektirdiğine dikkat edin. Ancak, `display_balance`ikinci çağrıda, bağımsız değişkenin türü olan bir **Double** değeri, işlevin beklediği bir `49.95`değer olmadığından, bir dönüştürme gerekir. İşlev bu değeri doğrudan kullanamaz, ancak bağımsız değişken türünden (**çift**) eşleşen parametrenin türüne bir dönüştürme olduğundan,`Money`— `Money` türünde geçici bir değer, bağımsız değişkenden oluşturulur ve işlev çağrısını tamamlamaya yönelik kullanılır. `display_balance`üçüncü çağrısında, bağımsız değişkenin bir **Double**olmadığına, ancak `9.99`bir değere sahip bir **float** olduğuna dikkat edin; ancak derleyici, bu durumda bir standart dönüştürme gerçekleştirebildiğinden (Bu örnekte, **float** 'ten **Double**'a) ve ardından gerekli dönüştürmeyi tamamlamak için bir `Money` **Double** ' a kadar, Kullanıcı tanımlı dönüştürmeyi gerçekleştirmeye devam edebilir.

### <a name="declaring-conversion-constructors"></a>Dönüştürme oluşturucuları bildirme

Aşağıdaki kurallar bir dönüştürme Oluşturucusu bildirmek için geçerlidir:

- Dönüştürmenin hedef türü, oluşturulan kullanıcı tanımlı türdür.

- Dönüştürme oluşturucuları genellikle kaynak türünde olan tam olarak bir bağımsız değişken alır. Ancak, her ek parametrenin varsayılan bir değeri varsa, bir dönüştürme Oluşturucusu ek parametreler belirtebilir. Kaynak türü ilk parametrenin türü olarak kalır.

- Tüm oluşturucular gibi dönüştürme oluşturucuları, dönüş türü belirtmez. Bildirimde bir dönüş türü belirtmek bir hatadır.

- Dönüştürme oluşturucuları açık olabilir.

### <a name="explicit-conversion-constructors"></a>Açık dönüştürme oluşturucuları

Bir dönüştürme oluşturucusunu **Açık**olacak şekilde bildirerek, yalnızca bir nesnenin doğrudan başlatılmasını veya açık bir tür dönüştürmeyi gerçekleştirmek için kullanılabilir. Bu, sınıf türünün bir bağımsız değişkenini kabul eden işlevlerin aynı zamanda dönüştürme oluşturucusunun kaynak türünün bağımsız değişkenlerini kabul etmesine engel olur ve sınıf türünün, kaynak türündeki bir değerden kopyalanmasını engeller. Aşağıdaki örnek, bir açık dönüştürme oluşturucusunun nasıl tanımlanacağını ve hangi kodun doğru biçimlendirildiğini gösteren etkisini gösterir.

```cpp
#include <iostream>

class Money
{
public:
    Money() : amount{ 0.0 } {};
    explicit Money(double _amount) : amount{ _amount } {};

    double amount;
};

void display_balance(const Money balance)
{
    std::cout << "The balance is: " << balance.amount << std::endl;
}

int main(int argc, char* argv[])
{
    Money payable{ 79.99 };        // Legal: direct initialization is explicit.

    display_balance(payable);      // Legal: no conversion required
    display_balance(49.95);        // Error: no suitable conversion exists to convert from double to Money.
    display_balance((Money)9.99f); // Legal: explicit cast to Money

    return 0;
}
```

Bu örnekte, `payable`doğrudan başlatılmasını gerçekleştirmek için açık dönüştürme oluşturucusunu kullanmaya devam edebilirsiniz. Bunun yerine `Money payable = 79.99;`kopyalamak için bir hata olabilir. Bağımsız değişken doğru türde olduğu için `display_balance` ilk çağrısı etkilenmez. `display_balance` ikinci çağrısı bir hatadır, çünkü dönüştürme Oluşturucusu örtük dönüştürmeler gerçekleştirmek için kullanılamaz. `display_balance` yapılan üçüncü çağrı, `Money`açıkça dönüştürmenin geçerli olduğu, ancak derleyicinin, **float** 'ten **Double**'a örtük bir tür ekleyerek, dönüştürmeyi tamamlamaya yardımcı olduğuna dikkat edin.

Örtük Dönüştürmelere izin vermek mümkün olmakla birlikte, bunu yapmak, zor bulma hataları ortaya çıkarabilir. Kaydırma kuralı, belirli bir dönüştürmenin örtük olarak gerçekleşmesini istediğinizden emin olmadığınız sürece tüm dönüştürme oluşturucularını açık hale getirme kuralıdır.

##  <a name="conversion-functions"></a><a name="ConvFunc"></a>Dönüştürme işlevleri

Dönüştürme işlevleri Kullanıcı tanımlı bir türden diğer türlere dönüşümler tanımlar. Bu işlevler bazen "atama işleçleri" olarak adlandırılır çünkü bir değer farklı bir türe yayınlandığı zaman, dönüştürme oluşturucularıyla birlikte çağrılır. Aşağıdaki örnek, Kullanıcı tanımlı tür, `Money`, yerleşik türe ( **Double**) dönüştüren bir dönüştürme işlevi gösterir.

```cpp
#include <iostream>

class Money
{
public:
    Money() : amount{ 0.0 } {};
    Money(double _amount) : amount{ _amount } {};

    operator double() const { return amount; }
private:
    double amount;
};

void display_balance(const Money balance)
{
    std::cout << "The balance is: " << balance << std::endl;
}
```

Üye değişkeninin `amount` özel hale getirildiğine ve **Double** türüne sahip bir genel dönüştürme işlevinin, `amount`değerini döndürecek şekilde tanıtıldığına dikkat edin. İşlev `display_balance`, `balance` değeri, akış ekleme işleci `<<`kullanılarak standart çıktıya akışa eklendiğinde örtük bir dönüştürme gerçekleşir. Kullanıcı tanımlı tür `Money`için herhangi bir akış ekleme işleci tanımlanmadığı için, ancak yerleşik tür **Double**için bir tane varsa, derleyici, akış ekleme işlecini karşılamak için `Money` dönüştürme işlevini **çift** olarak kullanabilir.

Dönüştürme işlevleri türetilmiş sınıflar tarafından devralınır. Türetilmiş bir sınıftaki dönüştürme işlevleri yalnızca tam olarak aynı türe dönüştürülerse devralınan bir dönüştürme işlevini geçersiz kılar. Örneğin, türetilmiş sınıf **işlecinin** bir Kullanıcı tanımlı dönüştürme işlevi, standart dönüşümler **int** ve **Short**arasında bir dönüştürme ilişkisi tanımlasa da, temel sınıf **işlecinin Short**bir Kullanıcı tanımlı dönüştürme işlevi olarak geçersiz kılınmaz — veya bile etkilemez.

### <a name="declaring-conversion-functions"></a>Dönüştürme işlevleri bildirme

Aşağıdaki kurallar bir dönüştürme işlevi bildirmek için geçerlidir:

- Dönüştürmenin hedef türü, dönüştürme işlevinin bildiriminden önce bildirilmelidir. Sınıflar, yapılar, numaralandırmalar ve tür tanımları dönüştürme işlevinin bildirimi içinde bildirilemez.

    ```cpp
    operator struct String { char string_storage; }() // illegal
    ```

- Dönüştürme işlevleri bağımsız değişken almaz. Bildirimde herhangi bir parametre belirtilmesi bir hatadır.

- Dönüştürme işlevleri, dönüştürme işlevinin adı ile belirtilen bir dönüş türüne sahiptir, bu da dönüştürmenin hedef türünün adıdır. Bildirimde bir dönüş türü belirtmek bir hatadır.

- Dönüştürme işlevleri sanal olabilir.

- Dönüştürme işlevleri açık olabilir.

### <a name="explicit-conversion-functions"></a>Açık dönüştürme işlevleri

Bir dönüştürme işlevi açık olarak bildirildiğinde, yalnızca açık bir dönüştürme gerçekleştirmek için kullanılabilir. Bu, dönüştürme işlevinin hedef türünün bir bağımsız değişkenini kabul eden işlevlerin, sınıf türünün bağımsız değişkenlerini de dolaylı olarak kabul etmesini engeller ve hedef türün örneklerinin, sınıf türündeki bir değerden kopyalanmasını engeller. Aşağıdaki örnek, bir açık dönüştürme işlevinin nasıl tanımlanacağını ve hangi kodun doğru biçimlendirildiğini gösteren etkisini gösterir.

```cpp
#include <iostream>

class Money
{
public:
    Money() : amount{ 0.0 } {};
    Money(double _amount) : amount{ _amount } {};

    explicit operator double() const { return amount; }
private:
    double amount;
};

void display_balance(const Money balance)
{
    std::cout << "The balance is: " << (double)balance << std::endl;
}
```

Burada, dönüştürme işlevi **işleci Double** açık yapıldı ve **çift** türüne açık bir dönüştürme işlemi, dönüştürme işlemini gerçekleştirmek için `display_balance` işlevde ortaya çıkarılmıştır. Bu atama atlandığında, derleyici tür `Money` için uygun bir akış ekleme operatörü `<<` bulamaz ve bir hata oluşur.
