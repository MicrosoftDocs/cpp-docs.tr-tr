---
title: Kullanıcı Tanımlı Tür Dönüşümleri (C++)
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
ms.openlocfilehash: e74d5b3a748a9aab22a6a9d83c4d6c4bd3379df4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374689"
---
# <a name="user-defined-type-conversions-c"></a>Kullanıcı Tanımlı Tür Dönüşümleri (C++)

*Dönüştürme,* farklı bir türdeki bir değerden bazı türde yeni bir değer üretir. *Standart dönüşümler* C++ dilinde yerleşiktir ve yerleşik türlerini destekler ve kullanıcı tarafından tanımlanan türlere, buradan veya bunlar arasında dönüşümler gerçekleştirmek için *kullanıcı tanımlı dönüşümler* oluşturabilirsiniz.

Standart dönüşümler yerleşik türler arasında, işaretçiler veya devralmayla ilişkili türlere başvurular arasında, geçersiz işaretçilere ve null işaretçisine dönüşümler gerçekleştirir. Daha fazla bilgi için [Standart Dönüşümler'e](../cpp/standard-conversions.md)bakın. Kullanıcı tanımlı dönüşümler, kullanıcı tarafından tanımlanan türler arasında veya kullanıcı tarafından tanımlanan türler ve yerleşik türler arasında dönüşümler gerçekleştirir. Bunları [Dönüşüm oluşturucuları](#ConvCTOR) veya [Dönüşüm işlevleri](#ConvFunc)olarak uygulayabilirsiniz.

Dönüşümler açık olabilir —programcı bir türün diğerine dönüştürülmesini istediğinde, örneğin bir döküm veya doğrudan başlatma da olduğu gibi-veya örtülü olarak- dil veya programcı tarafından verilenden farklı bir tür için çağrıda bulunursa.

Örtük dönüşümler şu anda denenir:

- Bir işleve verilen bağımsız değişken, eşleşen parametreyle aynı türe sahip değildir.

- Bir işlevden döndürülen değer, işlev dönüş türüyle aynı türe sahip değildir.

- Baş harfi ifade, başharfe büründürüncürün nesnesi ile aynı türde değildir.

- Koşullu bir deyimi, döngü yapısını veya anahtarı denetleyen bir ifade, onu denetlemek için gereken sonuç türüne sahip değildir.

- Bir işleç için verilen bir operand eşleşen operand-parametre ile aynı türde değildir. Yerleşik işleçler için, her iki operands aynı türe sahip olmalı ve her ikisini de temsil edebilir ortak bir türe dönüştürülür. Daha fazla bilgi için [Standart Dönüşümler'e](standard-conversions.md)bakın. Kullanıcı tanımlı işleçler için, her operand eşleşen operand-parametre ile aynı türe sahip olmalıdır.

Bir standart dönüştürme örtülü bir dönüştürmeyi tamamlayamadığınızda, derleyici bunu tamamlamak için isteğe bağlı olarak ek bir standart dönüştürme tarafından izlenen kullanıcı tanımlı bir dönüştürme kullanabilir.

Aynı dönüşümü gerçekleştiren iki veya daha fazla kullanıcı tanımlı dönüşüm bir dönüşüm sitesinde kullanılabilirolduğunda, dönüştürmenin belirsiz olduğu söylenir. Derleyici, kullanılabilir dönüşümlerden hangisini seçmesi gerektiğini belirleyemediğinden, bu tür belirsizlikler bir hatadır. Ancak, kullanılabilir dönüşümkümesi kaynak kodundaki farklı konumlarda farklı olabileceğinden(örneğin, kaynak dosyaya hangi üstbilgi dosyalarının dahil edildiğine bağlı olarak) aynı dönüşümü gerçekleştirmenin birden çok yolunu tanımlamak hata değildir. Dönüşüm sitesinde yalnızca bir dönüşüm mevcut olduğu sürece belirsizlik yoktur. Belirsiz dönüşümlerin ortaya çıkabileceği birkaç yol vardır, ancak en yaygın olanlar şunlardır:

- Birden fazla miras. Dönüştürme birden fazla taban sınıfta tanımlanır.

- Belirsiz işlev çağrısı. Dönüştürme, hedef türün dönüşüm oluşturucusu ve kaynak türünün dönüşüm işlevi olarak tanımlanır. Daha fazla bilgi için [Dönüşüm işlevlerine](#ConvFunc)bakın.

Genellikle bir belirsizliği, ilgili türün adını daha tam olarak nitelendirerek veya niyetinizi açıklığa kavuşturmak için açık bir döküm gerçekleştirerek çözebilirsiniz.

Hem dönüşüm oluşturucuları hem de dönüşüm işlevleri üye erişim denetim kurallarına uyar, ancak dönüşümlerin erişilebilirliği yalnızca kesin bir dönüştürme belirlenebilirse ve belirlendiğinde dikkate alınabilir. Bu, rakip bir dönüştürmenin erişim düzeyi dönüştürülmesini engellese bile dönüştürmenin belirsiz olabileceği anlamına gelir. Üye erişilebilirliği hakkında daha fazla bilgi için [Üye Erişim Denetimi'ne](../cpp/member-access-control-cpp.md)bakın.

## <a name="the-explicit-keyword-and-problems-with-implicit-conversion"></a>Açık anahtar kelime ve örtülü dönüştürme ile ilgili sorunlar

Varsayılan olarak, kullanıcı tarafından tanımlanan bir dönüşüm oluşturduğunuzda, derleyici bunu örtülü dönüşümler gerçekleştirmek için kullanabilir. Bazen istediğiniz budur, ancak bazen derleyiciyi örtülü dönüşümler yaparken yönlendiren basit kurallar, derleyicinin istemediğiniz kodu kabul etmesini sağlayabilir.

Sorunlara neden olabilecek örtük bir dönüştürmenin iyi bilinen bir örneği **bool'a**dönüştürülmesidir. Örneğin, **if** deyimini veya döngüyü denetlemek için kullanılabilmek için Boolean bağlamında kullanılabilecek bir sınıf türü oluşturmak istemenizin birçok nedeni vardır, ancak derleyici kullanıcı tarafından tanımlanan bir dönüştürmeyi yerleşik bir türe gerçekleştirdiğinde, derleyicinin daha sonra ek bir standart dönüşüm uygulamasına izin verilir. Bu ek standart dönüştürmenin amacı, **kısadan** **int'e**promosyon gibi şeylere izin vermektir, ancak aynı zamanda daha az belirgin dönüşümler için de kapı açar-örneğin, **bool'dan** **int'e**, sınıf türünizin hiç amaçlanamayacağınız tamsayı bağlamlarında kullanılmasına izin verir. Bu özel sorun *Güvenli Bool Sorunu*olarak bilinir. Bu tür bir sorun, **açık** anahtar kelimenin yardımcı olabileceği yerdir.

**Açık** anahtar kelime derleyiciye, belirtilen dönüştürmenin örtülü dönüşümler gerçekleştirmek için kullanılamayacağı nı söyler. **Açık** anahtar kelime kullanılmadan önce örtük dönüşümlerin sözdizimi kolaylığını istiyorsanız, örtük dönüştürmenin bazen oluşturduğu istenmeyen sonuçları kabul etmek veya daha az kullanışlı, adlandırılmış dönüşüm işlevlerini geçici çözüm olarak kullanmanız gerekir. Şimdi, **açık** anahtar kelimeyi kullanarak, yalnızca açık dökümleri veya doğrudan başlatmayı gerçekleştirmek için kullanılabilecek ve Güvenli Bool Sorunu tarafından örneklenen sorunlara yol açmaz uygun dönüşümler oluşturabilirsiniz.

**Açık** anahtar kelime C++98'den beri dönüşüm oluşturuculara ve C++11'den dönüştürme işlevlerine uygulanabilir. Aşağıdaki **bölümlerde açık** anahtar kelimenin nasıl kullanılacağı hakkında daha fazla bilgi bulunur.

## <a name="conversion-constructors"></a><a name="ConvCTOR"></a>Dönüşüm yapıcılar

Dönüşüm oluşturucular, dönüşümleri kullanıcı tanımlı veya yerleşik türlerden kullanıcı tanımlı türe tanımlar. Aşağıdaki örnekte, yerleşik tür **çiftten** kullanıcı tanımlı bir türe `Money`dönüştüren bir dönüşüm oluşturucusu gösterilmiştir.

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

Tür `Money`bir bağımsız değişken `display_balance`alan işlevin ilk çağrısının, bağımsız değişkeni doğru tür olduğu için dönüştürme gerektirmediğini unutmayın. Ancak, ikinci çağrıda `display_balance`, bir dönüştürme gerekir, çünkü bağımsız değişkentürü, bir `49.95`değeri olan bir **çift** , işlevin beklediği gibi değildir. İşlev bu değeri doğrudan kullanamaz, ancak bağımsız değişken türünden çift **-eşleşen**parametretürüne kadar- bir`Money`dönüşüm olduğundan, `Money` bağımsız değişkenden geçici bir tür değeri oluşturulur ve işlev çağrısını tamamlamak için kullanılır. Üçüncü `display_balance`çağrıda, bağımsız değişkenin **çift**değil, bunun yerine bir değeri `9.99`olan bir **float** olduğunu ve derleyici bu durumda **float'tan** **çifte**standart bir dönüştürme gerçekleştirebildiği ve ardından kullanıcı tarafından `Money` tanımlanan dönüşümü gerekli dönüşümü tamamlamak için **çifte** gerçekleştirebileceğinden yine de işlev çağrısı tamamlanabilir.

### <a name="declaring-conversion-constructors"></a>Dönüşüm oluşturucuları bildirme

Aşağıdaki kurallar bir dönüşüm oluşturucu bildirmek için geçerlidir:

- Dönüştürmenin hedef türü, oluşturulmakta olan kullanıcı tanımlı türüdür.

- Dönüştürme oluşturucular genellikle kaynak türünden tam olarak bir bağımsız değişken alır. Ancak, her ek parametrenin varsayılan değeri varsa, dönüşüm oluşturucu ek parametreler belirtebilir. Kaynak türü ilk parametre türü kalır.

- Dönüşüm oluşturucuları, tüm oluşturucular gibi, bir dönüş türü belirtmez. Bildirimde bir iade türü belirtmek bir hatadır.

- Dönüştürme oluşturucuları açık olabilir.

### <a name="explicit-conversion-constructors"></a>Açık dönüştürme oluşturucuları

Bir dönüştürme oluşturucusu **açık**olarak beyan ederek, yalnızca bir nesnenin doğrudan başlatılmasını gerçekleştirmek veya açık bir döküm gerçekleştirmek için kullanılabilir. Bu, sınıf türünden bir bağımsız değişkeni kabul eden işlevlerin dönüşüm oluşturucukaynak türünün bağımsız değişkenlerini de dolaylı olarak kabul etmesini önler ve sınıf türünün kaynak türünün bir değerinden kopya-başharfe çevrilmesini önler. Aşağıdaki örnek, açık bir dönüştürme oluşturucusu nasıl tanımlanabildiğini ve hangi kodun iyi biçimlendirilmiş olduğu üzerindeki etkisini gösterir.

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

Bu örnekte, ''nin doğrudan başlatılmasını gerçekleştirmek için açık `payable`dönüştürme oluşturucuyu kullanmaya devam edebilirsiniz. Bunun yerine kopya-başharf `Money payable = 79.99;`eki olsaydı, bu bir hata olur. Bağımsız değişken `display_balance` doğru tür olduğundan ilk çağrı etkilenmez. Dönüşüm oluşturucu `display_balance` örtülü dönüşümler gerçekleştirmek için kullanılamadığından, ikinci çağrı bir hatadır. Üçüncü çağrı `display_balance` için açık döküm nedeniyle `Money`yasal , ama derleyici hala **float çift**örtülü bir döküm **float** ekleyerek döküm tamamlamak yardımcı olduğunu fark .

Örtük dönüşümlere izin vermenin kolaylığı cazip olsa da, bunu yapmak bulunması zor hataları ortaya çıkabilir. Başparmak kuralı, belirli bir dönüşümün örtülü olarak gerçekleşmesini istediğinizden emin olmak dışında tüm dönüşüm oluşturucuları açık hale getirmektir.

## <a name="conversion-functions"></a><a name="ConvFunc"></a>Dönüştürme işlevleri

Dönüştürme işlevleri, kullanıcı tanımlı bir türden diğer türlere dönüşümleri tanımlar. Bu işlevler bazen "döküm işleçleri" olarak adlandırılır, çünkü dönüşüm oluşturucuları ile birlikte, bir değer farklı bir türe atıldığında çağrılır. Aşağıdaki örnek, kullanıcı tanımlı türden, `Money`yerleşik bir türe, **çift**e dönüşen bir dönüştürme işlevini gösterir:

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

Üye değişkenin `amount` özel hale getirildiğine ve yalnızca değerini döndürmek için **çift** türetmek `amount`için genel dönüşüm işlevinin sunulduğuna dikkat edin. İşlevde, `display_balance`akış ekleme işleci `balance` `<<`kullanılarak değeri standart çıktıya aktarıldığında örtülü bir dönüştürme oluşur. Kullanıcı tanımlı `Money`türü için akış ekleme işleci tanımlanmadığından, ancak yerleşik tip **çift**için bir tane olduğundan, `Money` derleyici akış ekleme işlecini karşılamak için dönüştürme işlevini **çifte** kadar kullanabilir.

Dönüştürme işlevleri türetilmiş sınıflar tarafından devralınır. Türetilmiş bir sınıftaki dönüşüm işlevleri yalnızca aynı türe dönüştürdüklerinde devralınan bir dönüştürme işlevini geçersiz kılar. Örneğin, türemiş sınıf **işleci int** kullanıcı tanımlı dönüştürme işlevi geçersiz kılmaz-hatta etkisi-temel sınıf **işleci kısa**bir kullanıcı tanımlı dönüşüm işlevi, standart dönüşümler **int** ve **kısa**arasında bir dönüşüm ilişkisi tanımlasa bile .

### <a name="declaring-conversion-functions"></a>Dönüşüm işlevlerini bildirme

Dönüşüm işlevini bildirmek için aşağıdaki kurallar geçerlidir:

- Dönüştürmenin hedef türü, dönüştürme işlevinin beyanı nın bildirilmesinden önce bildirilmelidir. Sınıflar, yapılar, sayısallaştırmalar ve daktinolar dönüştürme işlevinin bildirimi içinde bildirilemez.

    ```cpp
    operator struct String { char string_storage; }() // illegal
    ```

- Dönüştürme işlevleri bağımsız değişken almaz. Bildirimde herhangi bir parametre belirtilmesi bir hatadır.

- Dönüştürme işlevleri, dönüşüm işlevinin adıyla belirtilen ve aynı zamanda dönüşümün hedef türünün adı olan bir iade türüne sahiptir. Bildirimde bir iade türü belirtmek bir hatadır.

- Dönüştürme işlevleri sanal olabilir.

- Dönüştürme işlevleri açık olabilir.

### <a name="explicit-conversion-functions"></a>Açık dönüştürme işlevleri

Dönüştürme işlevinin açık olduğu belirtildiğinde, yalnızca açık bir döküm gerçekleştirmek için kullanılabilir. Bu, dönüştürme işlevinin hedef türünün bağımsız değişkenini kabul eden işlevlerin sınıf türünün bağımsız değişkenlerini de dolaylı olarak kabul etmesini önler ve hedef türün örneklerinin sınıf türündeki bir değerden kopyala başlatılmasını önler. Aşağıdaki örnek, açık bir dönüştürme işlevinin nasıl tanımlandığını ve hangi kodun iyi biçimlendirilmiş olduğu üzerindeki etkisini gösterir.

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

Burada dönüştürme işlevi **işleci çift** açık hale getirilmiş ve dönüştürme gerçekleştirmek için `display_balance` işlevde **çift** yazmak için açık bir döküm getirilmiştir. Bu döküm atlanırsa, derleyici tür `<<` `Money` için uygun bir akış ekleme işleci bulamıyor ve bir hata oluşacak.
