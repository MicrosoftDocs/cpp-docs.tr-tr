---
title: Kullanıcı tanımlı tür Dönüşümleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- explicit_cpp
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c0ad42083f6ee310295a401b722563579a6a78e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071178"
---
# <a name="user-defined-type-conversions-c"></a>Kullanıcı tanımlı tür Dönüşümleri (C++)

A *dönüştürme* farklı türde bir değer dosyasından bazı türünde yeni bir değer üretir. *Standart dönüştürmeler* C++ dili ve Destek, yerleşik türler ve siz oluşturabilirsiniz yerleşik *kullanıcı tanımlı dönüşümler* için ya da kullanıcı tanımlı türler arasında dönüştürmeler gerçekleştirmek için.

Standart dönüştürmeler işaretçileri veya başvuruları void işaretçileri, gelen ve devralma yoluyla ilgili türleri ve null işaretçi arasında yerleşik türler arasında dönüştürmeler gerçekleştirin. Daha fazla bilgi için [standart dönüştürmeler](../cpp/standard-conversions.md). Kullanıcı tanımlı dönüştürmeler veya kullanıcı tanımlı türler ve yerleşik türleri kullanıcı tanımlı türler arasında dönüştürmeler gerçekleştirin. Olarak uygulayabilirsiniz [dönüştürme oluşturucuları](#ConvCTOR) veya as [dönüştürme işlevleri](#ConvFunc).

Dönüştürme açık olabilir — Programcı çağırdığında bir türü için başka bir tür dönüştürme veya doğrudan başlatma olduğu gibi dönüştürülmesi için — ya da örtük — program ve dil çağırdığında Programcı tarafından verilen olandan farklı bir tür için.

Örtük dönüştürmeleri çalıştı olduğunda:

- Bir işlev için sağlanan bağımsız değişken parametresiyle eşleşen aynı türe sahip değil.

- Bir işlevden döndürülen değer işlev dönüş türünü aynı türe sahip değil.

- Bir başlatıcı ifadesinin, başlatma nesnesi aynı türe sahip değil.

- Bir koşul deyimi, uvozuje konstruktor veya anahtar denetleyen bir ifade denetlemek için gerekli olan sonuç türü yok.

- Operatörün sağladığı bir işlenen eşleşen işlenen parametresi aynı türe sahip değil. Yerleşik işleçler, her iki işlenen de aynı türde olmalıdır ve her ikisi de temsil edebilen ortak bir türe dönüştürülür. Daha fazla bilgi için [standart dönüştürmeler](standard-conversions.md). Kullanıcı tanımlı işleçler için her işlenen eşleşen işlenen parametresi aynı türde olmalıdır.

Standart bir dönüştürme örtük bir dönüştürme tamamlayamadığında, derleyici tamamlamak için isteğe bağlı olarak ek standart bir dönüştürme tarafından izlenen bir kullanıcı tanımlı dönüştürme kullanabilirsiniz.

Bir dönüştürme sitede aynı dönüştürme gerçekleştiren iki veya daha fazla kullanıcı tanımlı dönüştürme kullanılabilir olduğunda dönüştürme belirsiz olarak kabul edilir. Böyle belirsizlikleri bir hata olduğu kullanılabilir dönüştürmeler birini seçmeniz gerekir, derleyici belirlenemiyor. Ancak, yalnızca kaynak kodunda farklı konumlarda kullanılabilir dönüştürmeler kümesini farklı olabilir çünkü aynı dönüşüm gerçekleştirme birçok yolu tanımlamak için bir hata değildir — Örneğin, hangi üstbilginin bağlı olarak dosyaları bir kaynak dosyasına dahil edilir. Yalnızca bir dönüştürme dönüştürme sitede kullanılabilir olduğu sürece, belirsizlik olmaz yoktur. Belirsiz dönüşümler oluşabilir, ancak en yaygın olanlarından birkaç yolu vardır:

- Birden çok devralma. Dönüştürme birden fazla temel sınıfta tanımlı.

- Belirsiz işlev çağrısı. Dönüştürmenin bir dönüştürme işlevi kaynak türü ve hedef türünün bir dönüştürme Oluşturucu olarak tanımlanır. Daha fazla bilgi için [dönüştürme işlevleri](#ConvFunc).

Genellikle, tam olarak daha ilgili türün adını nitelendirme tarafından veya sizin amacı açıklamak için açık bir yayın gerçekleştirerek bir belirsizlik çözebilirsiniz.

Dönüştürme oluşturucuları hem dönüştürme işlevleri, üye erişim denetimi kurallara uyan ancak dönüştürmeler erişilebilirliğini, yalnızca bir dönüştürmesini belirlenebilir açmadıklarını ve ne zaman kabul edilir. Bu, rakip bir dönüştürmenin erişim düzeyi, kullanılmasını önleyen olsa bile bir dönüştürme belirsiz olabilir, anlamına gelir. Üye erişilebilirliği hakkında daha fazla bilgi için bkz: [üye erişim denetimi](../cpp/member-access-control-cpp.md).

## <a name="the-explicit-keyword-and-problems-with-implicit-conversion"></a>Explicit anahtar sözcüğü ve örtülü dönüştürme ile ilgili sorunlar

Bir kullanıcı tanımlı dönüştürme oluşturduğunuzda varsayılan olarak derleyici, örtülü dönüştürmeler gerçekleştirmek için kullanabilirsiniz. Bazen bu istediğiniz, ancak derleyici örtük dönüştürmeleri yapmak, yol basit kural bazen kendisine istemediğiniz kod kabul etmek için açabilir.

İyi bilinen sorunlara neden olabilecek bir örtük dönüştürme örneğidir dönüştürme **bool**. Kullanılabilir bir sınıf türü Boole bağlamında oluşturmak isteyebilirsiniz birçok neden vardır — örneğin, bu nedenle, BT kullanılabilir denetimine bir **varsa** deyim ya da döngü — ancak derleyici, kullanıcı tanımlı dönüştürme gerçekleştirdiğinde bir Yerleşik tür, derleyici, daha sonra ek bir standart dönüştürme uygulamak izin verilmez. Bu ek standart dönüştürme amacı yükseltme gibi şeyler için izin vermektir **kısa** için **int**, ancak ayrıca daha az belirgin dönüştürmeler için kapı açılır — Örneğin,  **bool** için **int**, hiçbir zaman amaçladığınız tamsayı bağlamlarda kullanılacak sınıf türüne izin verir. Bu belirli sorun olarak da bilinen *güvenli Bool sorun*. Bu tür sorunlar yerdir **açık** anahtar sözcüğü yardımcı olabilir.

**Açık** anahtar sözcüğü derleyiciye belirtilen dönüşüm örtük dönüştürmeler gerçekleştirmek için kullanılamaz. Örtük dönüştürmeleri önce söz dizimsel kolaylık istediğinizi **açık** anahtar sözcüğü tanıtılmıştır, istenmeyen sonuçları bazen oluşturulan bu örtülü dönüştürme kabul etme veya daha az uygun, kullanmanız gerekiyordu geçici çözüm olarak adlandırılmış dönüştürme işlevleri. Kullanarak artık **açık** anahtar sözcüğü, yalnızca açık atamaları veya doğrudan başlatma gerçekleştirmek için kullanılabilir ve, olmaz neden sorunları güvenli Bool sorundan örneği türünü kullanışlı dönüştürmeler oluşturabilirsiniz.

**Açık** anahtar sözcüğü, dönüştürme işlevleri beri C ++ 11 ve C ++ 98 bu yana dönüştürme oluşturucuları için uygulanabilir. Aşağıdaki bölümlerde nasıl kullanılacağı hakkında daha fazla bilgi içeren **açık** anahtar sözcüğü.

## <a name="ConvCTOR"></a> Dönüştürme oluşturucuları

Dönüştürme oluşturucuları, yerleşik veya kullanıcı tanımlı türlerden dönüştürmeler için kullanıcı tanımlı bir tür tanımlar. Aşağıdaki örnek, yerleşik türünden dönüştüren bir dönüştürme Oluşturucu gösterir **çift** kullanıcı tanımlı bir tür için `Money`.

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

İlk işleve çağrı bildirimi `display_balance`, türünde bir bağımsız değişken alan `Money`, kendi bağımsız değişkeni doğru türe olduğundan bir dönüştürme gerektirmez. Ancak, şirket için yapılan ikinci çağrı `display_balance`, dönüştürme için gerekli bağımsız değişken türünü bir **çift** değerini `49.95`, değil hangi işlevin beklediği. İşlevi bu değeri doğrudan kullanamazsınız, ancak bağımsız değişkenin türünden dönüştürme olmadığından —**çift**— eşleşen parametresinin türü için —`Money`— geçici bir değer türü `Money` nesnesinden oluşturulan bağımsız değişken ve işlev çağrısını tamamlamak için kullanılır. Üçüncü çağrısında `display_balance`, bağımsız değişken değil bildirimi bir **çift**, ancak bunun yerine bir **float** değerini `9.99`— ve henüz işlev çağrısı hala çünkü tamamlanabilir Derleyici, standart bir dönüşüm gerçekleştirebilir; bu durumda, gelen **float** için **çift**— ve ardından kullanıcı tanımlı dönüştürme işlemini gerçekleştirin **çift** için`Money` gerekli dönüştürme işlemini tamamlamak için.

### <a name="declaring-conversion-constructors"></a>Dönüştürme oluşturucuları bildirme

Bir dönüştürme Oluşturucu bildirmek için aşağıdaki kurallar geçerlidir:

- Hedef türü dönüştürme yapılandırılmakta olan kullanıcı tanımlı bir türdür.

- Dönüştürme oluşturucuları, genellikle kaynak türünde tam olarak bir bağımsız değişken alın. Ancak, her ek bir parametre bir varsayılan değere sahipse, bir dönüştürme Oluşturucu ek parametreler belirtebilirsiniz. Kaynak türü, ilk parametresinin türü kalır.

- Tüm oluşturucular gibi dönüştürme oluşturucuları bir dönüş türü belirtmeyin. Dönüş türü bildiriminde belirten bir hata var.

- Dönüştürme oluşturucuları açık olabilir.

### <a name="explicit-conversion-constructors"></a>Açık dönüştürme oluşturucuları

Olacak şekilde bir dönüştürme Oluşturucu bildirilerek tarafından **açık**, bir nesnenin doğrudan başlatma gerçekleştirmek için veya açık bir tür dönüştürme gerçekleştirmek için yalnızca kullanılabilir. Bu, aynı zamanda örtük dönüştürme oluşturucunun kaynak türü bağımsız değişkenleri kabul etmesini sınıf türünde bir bağımsız değişken kabul edin ve sınıf türü kopya başlatılan kaynak türü arasında bir değer olmasını önleyen işlevleri engeller. Aşağıdaki örnek, bir açık bir dönüştürme Oluşturucu tanımlamak gösterilmiştir ve hangi kod üzerinde sahip olduğu etkiyi iyi biçimlendirilmemiş.

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

Bu örnekte, hala açık bir dönüştürme Oluşturucu öğesinin doğrudan başlatılmasını gerçekleştirmek için kullanabileceğiniz fark `payable`. Bunun yerine kopya başlatma için olsaydı `Money payable = 79.99;`, bir hata olabilir. İlk çağrıda `display_balance` bağımsız değişkeni doğru türe olduğundan etkilenmez. İçin yapılan ikinci çağrı `display_balance` dönüştürme Oluşturucusu örtük dönüştürmeler gerçekleştirmek için kullanılamaz çünkü bir hata oluştu. Üçüncü çağrı `display_balance` açık tür dönüştürme için nedeniyle yasaldır `Money`, ancak derleyici hala Yardım dikkat edin, gelen örtük bir dönüştürme ekleyerek cast tamamlamak **float** için **çift**.

Örtük dönüştürmeleri zorlu kolaylık sağlamak cazip olabilir, ancak bunun yapılması bu nedenle bulunur zor hataları ortaya çıkarabilir. Tüm dönüştürme oluşturucuları açık, örtük olarak gerçekleşecek özel bir dönüştürmenin istediğiniz emin olduğunuzda hariç olmak üzere udur.

##  <a name="ConvFunc"></a> Dönüştürme işlevleri

Dönüştürme işlevleri, kullanıcı tanımlı bir tür dönüştürmelerinde diğer türlere tanımlayın. Farklı bir tür için bir değer atandığında, dönüştürme oluşturucuları birlikte çağrılır, çünkü bu işlevler için "atama işleçleri" adlandırılır. Aşağıdaki örnek, kullanıcı tanımlı tür, dönüştüren bir dönüştürme işlevi gösterir `Money`, yerleşik bir tür **çift**:

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

Dikkat üye değişkeni `amount` özel ve genel bir dönüştürme türü için işlev yapılan **çift** yalnızca değerini döndürmek için sunulan `amount`. İşlevde `display_balance`, örtük bir dönüştürme gerçekleşir, değerini `balance` standart çıktıya akış ekleme işlecini kullanarak akış `<<`. Kullanıcı tanımlı bir tür için hiçbir akış ekleme işleç tanımlandığından `Money`, yoktur ancak bir yerleşik türü için **çift**, derleyici, dönüştürme işlevinden kullanabilirsiniz `Money` için **çift** akış ekleme işleci karşılamak için.

Dönüştürme işlevleri, türetilmiş sınıflar tarafından devralınır. Bunlar tam olarak aynı türe dönüştürürken, türetilen bir sınıfta dönüştürme işlevleri yalnızca bir devralınan dönüştürme işlevi geçersiz kılar. Örneğin, bir kullanıcı tanımlı dönüştürme işlevi türetilmiş sınıfın **operator int** geçersiz — veya hatta etkisi — temel sınıfın bir kullanıcı tanımlı dönüştürme işlevi **işleci kısa**bile Standart dönüştürmeler arasındaki bir dönüştürme ilişkiyi tanımlayabilirsiniz ancak **int** ve **kısa**.

### <a name="declaring-conversion-functions"></a>Dönüşüm işlevlerini bildirme

Bir dönüştürme işlevi bildirmek için aşağıdaki kurallar geçerlidir:

- Dönüştürme hedef türüne dönüştürme işlevi bildirimi önce bildirilmelidir. Sınıflar, yapılar, numaralandırmalar ve tür tanımları dönüştürme işlevi bildirimi içinde bildirilemez.

    ```cpp
    operator struct String { char string_storage; }() // illegal
    ```

- Dönüştürme işlevleri bağımsız değişken almaz. Tüm parametreleri bildirimde belirten bir hata var.

- Dönüştürme işlevleri, aynı zamanda dönüştürme 's hedef türünün adı olan bir dönüştürme işlevi adı tarafından belirtilen bir dönüş türüne sahip. Dönüş türü bildiriminde belirten bir hata var.

- Dönüştürme işlevleri sanal olabilir.

- Dönüştürme işlevleri açık olabilir.

### <a name="explicit-conversion-functions"></a>Açık dönüştürme işlevleri

Bir dönüştürme işlevi açık olarak bildirilmiştir yalnızca, bir açık tür dönüştürme gerçekleştirmek için kullanılabilir. Bu sınıf türünün bağımsız değişkenler de örtülü olarak kabul etmesini dönüştürme işlevin hedef türünde bir bağımsız değişken kabul edin ve hedef türün örneklerinin kopyalama başlatılan sınıf türünde arasında bir değer olmasını önleyen işlevleri engeller. Aşağıdaki örnek, bir açık bir dönüştürme işlevi ve hangi kodun doğru biçimlendirilmiş sahip olduğu etkiyi nasıl tanımlanacağını gösterir.

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

Burada dönüştürme işlevi **double işleci** açık, yapılan ve yazmak için açık bir tür dönüştürme **çift** işlevi sunulan `display_balance` dönüştürme gerçekleştirmek için. Bu tür dönüştürme atlanırsa, derleyicinin uygun akış ekleme işleci bulamadı olacaktır `<<` türünün `Money` ve bir hata oluşacak.