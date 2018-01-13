---
title: "Kullanıcı tanımlı tür Dönüşümleri (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: explicit_cpp
dev_langs: C++
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
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 561730527a215d5314f7239affc764d9f5925f67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="user-defined-type-conversions-c"></a>Kullanıcı tanımlı tür Dönüşümleri (C++)
A *dönüştürme* farklı türde bir değerden bazı türünde yeni bir değer oluşturur. *Standart dönüşümler* yerleşik türlerinden ve oluşturabilirsiniz C++ dili ve Destek bölümüne yerleşik *kullanıcı tanımlı dönüşümler* için ya da kullanıcı tanımlı türler arasında dönüştürme gerçekleştirmek için.  
  
 Standart dönüşümler işaretçileri veya devralma, void işaretçileri, gelen ve giden yoluyla ilgili türler ve null işaretçi başvuruları arasında yerleşik türleri arasında dönüştürmeler gerçekleştirin. Daha fazla bilgi için bkz: [standart dönüşümler](../cpp/standard-conversions.md). Kullanıcı tanımlı dönüşümler kullanıcı tanımlı türler arasında veya kullanıcı tanımlı türler ve yerleşik türleri arasında dönüştürmeler gerçekleştirin. Bunları uygulayabilirsiniz [dönüştürme oluşturucuları](#ConvCTOR) veya as [dönüştürme işlevleri](#ConvFunc).  
  
 Dönüşümler ya da açık olabilir — Programcı çağırdığında bir şekilde atama veya doğrudan başlatma olduğu gibi dönüştürülecek bir türü için — ya da örtük — dil veya program çağırdığında Programcı tarafından verilen olandan farklı bir tür için.  
  
 Örtük dönüşümler çalıştı zaman:  
  
-   Bir işlev için sağlanan bağımsız değişken eşleştirme parametre ile aynı türü yok.  
  
-   İşlev dönüş türü aynı türde bir işlevinden döndürülen değer yok.  
  
-   Başlatıcı ifade başlatma nesne ile aynı türü yok.  
  
-   Bir koşul deyimi, döngü yapısı veya anahtar denetleyen bir ifade denetlemek için gerekli olan sonuç türü yok.  
  
-   Bir işleç için sağlanan işleneni eşleşen işleneni parametresi aynı türe sahip değil. Yerleşik işleçleri için her iki işlenen aynı türde olması gerekir ve her ikisi de gösterebilir ortak bir türü dönüştürülür. Daha fazla bilgi için bkz: [standart dönüşümler](standard-conversions.md). Kullanıcı tanımlı işleçler için her işlenen eşleşen işleneni parametre olarak aynı türe sahip olmalıdır.  
  
 Bir standart dönüştürme örtük bir dönüştürme tamamlayamıyor, derleyici tamamlamak için ek bir standart dönüştürme tarafından ardından isteğe bağlı kullanıcı tanımlı bir dönüştürme, kullanabilirsiniz.  
  
 Aynı dönüştürme gerçekleştiren iki veya daha fazla kullanıcı tanımlı dönüşümler bir dönüştürme sitede kullanılabilir olduğunda, dönüştürme belirsiz olarak kabul edilir. Bu tür belirsizlikleri hata olduklarından derleyici kullanılabilir dönüşümleri birini seçmeniz gerekir belirleyemiyor. Ancak, yalnızca kaynak kodundaki farklı konumlarda kullanılabilir dönüştürme kümesini farklı olabilir çünkü aynı dönüştürme gerçekleştirme birkaç yolu tanımlamak için bir hata değildir — Örneğin, bağlı olarak hangi üstbilgi dosyalarını bir kaynak dosyasına dahil edilir. Yalnızca bir dönüştürme dönüştürme sitede kullanılabilir olduğu sürece bu belirsizlik yoktur. Belirsiz dönüşümler oluşabilir, ancak en yaygın olanlardır birkaç yolu vardır:  
  
-   Birden çok devralma. Dönüştürme birden fazla temel sınıfında tanımlanır. 
  
-   Belirsiz işlevi çağrısı. Dönüştürme, hedef türü dönüştürme oluşturucusunun ve kaynak türündeki dönüştürme işlevi olarak tanımlanır. Daha fazla bilgi için bkz: [dönüştürme işlevleri](#ConvFunc).  
  
 Daha eksiksiz söz konusu türünün adı niteleme tarafından veya maksadınızı açıklamak için bir açık atama gerçekleştirerek genellikle bir belirsizlik çözebilirsiniz.  
  
 Dönüştürme oluşturucuları ve dönüştürme işlevleri üye erişim denetimi kuralları uyma ancak anlaşılır bir dönüştürme belirlenebilir açmadıklarını ve ne zaman dönüşümleri erişilebilirliğini yalnızca olarak kabul edilir. Bu erişim düzeyi rakip dönüştürme kullanılmasını görünür duruma önleyen olsa bile bir dönüştürme belirsiz olabileceği anlamına gelir. Üye erişilebilirlik hakkında daha fazla bilgi için bkz: [üye erişim denetimi](../cpp/member-access-control-cpp.md).  
  
## <a name="the-explicit-keyword-and-problems-with-implicit-conversion"></a>Explicit anahtar sözcüğü ve örtük dönüştürme sorunları  
 Kullanıcı tanımlı bir dönüştürme oluşturduğunuzda varsayılan olarak derleyici onu örtük dönüşümler gerçekleştirmek için kullanabilirsiniz. Bazen bu istediğiniz, ancak bunu istemiyorum kodu kabul etmek için örtük dönüşümler alımında derleyici Kılavuzu basit kural bazen yol açabilir.  
  
 İyi bilinen sorunlara neden olabilecek örtük bir dönüştürme örneğidir dönüştürme `bool`. Kullanılabilir bir sınıf türü bir Boolean bağlamında oluşturmak isteyebilirsiniz pek çok nedeni olabilir — örneğin, bu nedenle, BT'nin kullanılabilir denetlemek için bir `if` deyimi veya döngü — ancak yerleşik türü kullanıcı tanımlı bir dönüştürmeye gerçekleştirdiğinde derleyici , derleyici, daha sonra ek bir standart dönüştürme uygulamak için izin verilir. Bu ek standart dönüştürme amacı yükseltme gibi şeyler için izin vermektir `short` için `int`, ancak daha az belirgin dönüşümleri kapısının da açılır — Örneğin, `bool` için `int`, sınıfınız sağlar hiçbir zaman amaçlı tamsayı bağlamlarda kullanılacak yazın. Bu belirli sorun olarak bilinen *güvenli Bool sorun*. Bu tür sorunlar yerdir `explicit` anahtar sözcüğü yardımcı olabilir.  
  
 `explicit` Anahtar sözcüğü söyler derleyici belirtilen dönüşüm örtük dönüştürme gerçekleştirmek için kullanılamaz. Örtük dönüşümler önce söz dizimi kolaylık istediğinizi `explicit` anahtar sözcüğü sunulmuştur, istenmeyen sonuçları bazen oluşturulan bu örtük dönüştürme kabul etme veya daha az kullanışlı, adlandırılmış dönüştürme kullanın gerekiyordu geçici bir çözüm olarak işlev. Kullanarak şimdi `explicit` anahtar sözcüğü, yalnızca açık atamaları veya doğrudan başlatma gerçekleştirmek için kullanılabilir ve bu olmaz neden güvenli Bool sorundan örneği sorunları türü için uygun dönüşümleri oluşturabilirsiniz.  
  
 `explicit` Anahtar sözcüğü, C ++ 98 itibaren dönüştürme oluşturucuları ve C ++ 11 itibaren dönüştürme işlevleri için uygulanabilir. Aşağıdaki bölümlerde nasıl kullanılacağı hakkında daha fazla bilgi içeren `explicit` anahtar sözcüğü.  
  
##  <a name="ConvCTOR"></a>Dönüşüm oluşturucuları  
 Dönüştürme oluşturucuları kullanıcı tanımlı bir tür için kullanıcı tanımlı veya yerleşik türlerinden dönüştürmeler tanımlayın. Aşağıdaki örnek, yerleşik türünden dönüştüren bir dönüştürme Oluşturucu gösterir `double` kullanıcı tanımlı bir tür için `Money`.  
  
```  
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
  
 İlk işleve çağrı bildirimi `display_balance`, türünde bir bağımsız değişken aldığı `Money`, bağımsız değişkeni doğru türde olduğundan dönüştürme gerektirmez. İçin ancak, ikinci çağrıda `display_balance`, dönüştürme için gerekli bağımsız değişken türü bir `double` değerini `49.95`, değil ne işlev bekliyor değil. İşlevi bu değer, doğrudan kullanamaz, ancak bağımsız değişken türü dönüştürme olduğundan —`double`— eşleşen parametresinin türü için —`Money`— türünde geçici bir değer `Money` bağımsız değişkende oluşturulur ve kullanılacak işlev çağrısı tamamlayın. Üçüncü çağrısında `display_balance`, bağımsız değişken değil bildirimi bir `double`, ancak bunun yerine bir `float` değerini `9.99`— ve derleyici standart dönüştürme gerçekleştirebilirsiniz çünkü henüz işlev çağrısı hala tamamlanabilir — bu durumda , gelen `float` için `double`— ve kullanıcı tanımlı bir dönüştürme gerçekleştirmek `double` için `Money` gerekli dönüştürme işlemini tamamlamak için.  
  
### <a name="declaring-conversion-constructors"></a>Dönüştürme oluşturucuları bildirme  
 Bir dönüştürme Oluşturucu bildirmek için aşağıdaki kurallar geçerlidir:  
  
-   Yapılandırılan bir kullanıcı tanımlı tür dönüştürme işleminin hedef türüdür.  
  
-   Dönüştürme oluşturucuları genellikle kaynak türü tam olarak bir bağımsız değişken sürer. Bununla birlikte, her ek parametre varsayılan değere sahip olursa dönüştürme Oluşturucusu ek parametreler belirtebilirsiniz. Kaynak türü, ilk parametresinin türü kalır.  
  
-   Dönüştürme oluşturucuları tüm oluşturucular gibi bir dönüş türü belirtmeyin. Dönüş türü bildiriminde belirten bir hata var.  
  
-   Dönüştürme oluşturucuları açık olabilir.  
  
### <a name="explicit-conversion-constructors"></a>Açık dönüşüm oluşturucuları  
 Olması için bir dönüştürme oluşturucuya bildirme tarafından `explicit`, bunu yalnızca bir nesnenin doğrudan başlatma gerçekleştirmek veya belirtik işlemi gerçekleştirmek için kullanılabilir. Bu da örtük dönüştürme Oluşturucusu ait kaynak türü bağımsız değişkenleri kabul etmesini sınıfı türünde bir bağımsız değişken kabul edin ve sınıf türü kopyalama-başlatılan bir kaynak türü değerinden engeller işlevleri önler. Aşağıdaki örnek, bir açık dönüşüm Oluşturucusu tanımlamak gösterilmiştir ve hangi koduna sahip iyi biçimlendirilmiş bir etkisidir.  
  
```  
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
  
 Bu örnekte, hala açık dönüşüm Oluşturucusu doğrudan başlatma işlemi gerçekleştirmek için kullanabileceğiniz fark `payable`. Bunun yerine kopyalama başlatma için olsaydı `Money payable = 79.99;`, bir hata olabilir. İlk çağrıda `display_balance` bağımsız değişkeni doğru türde olduğundan etkilenmez. İkinci çağrı `display_balance` bir hata olduğundan dönüştürme Oluşturucusu örtük dönüşümler gerçekleştirmek için kullanılamaz. Üçüncü çağrısı `display_balance` açık atama nedeniyle uygundur `Money`, ancak derleyici hala Yardım duyuru örtük bir dönüştürme ekleyerek cast tamamlayın `float` için `double`.  
  
 Örtük dönüşümler vermeyle kolaylık tempting olabilse de, bunun nedenle Bul sabit hatalar ortaya çıkarabilir. Altın kural tüm dönüştürme oluşturucuları örtük olarak gerçekleşmesi için belirli bir dönüştürme istediğinizden emin olduğunuzda dışında açık olmasını sağlamaktır.  
  
##  <a name="ConvFunc"></a>Dönüşüm işlevleri  
 Dönüşüm işlevleri diğer türleri için kullanıcı tanımlı bir türden dönüşümleri tanımlayın. Bir değer farklı bir türe dönüştürüldüğüne olduğunda bunlar, dönüştürme oluşturucuları birlikte çağrılır çünkü bu işlevler "atama işleçleri" adlandırılır. Aşağıdaki örnekte kullanıcı tanımlı türünden dönüştüren bir dönüştürme işlevi gösteren `Money`, yerleşik bir türe `double`:  
  
```  
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
  
 Dikkat üye değişkeni `amount` özel ve ortak bir dönüştürme türü için işlev yapılan `double` yalnızca değerini döndürmek için sunulan `amount`. İşlevinde `display_balance`, örtük bir dönüştürme oluşur zaman değerini `balance` akış ekleme işlecini kullanarak standart çıktı akışı `<<`. Hiçbir akış ekleme işleci kullanıcı tanımlı tür için tanımlı olduğundan `Money`, ancak yerleşik türü için bir tane `double`, derleyici dönüştürme işlevini kullanabilirsiniz `Money` için `double` akış ekleme karşılamak için işleç.  
  
 Dönüşüm işlevleri türetilmiş sınıflar tarafından devralınır. Tam olarak aynı türde dönüştürürken bir türetilmiş sınıfta dönüştürme işlevleri yalnızca devralınan dönüştürme işlevi geçersiz kılar. Örneğin, kullanıcı tanımlı dönüştürme işlevinin türetilmiş sınıf `operator int` geçersiz — veya hatta etkisi — kullanıcı tanımlı dönüştürme işlevi temel sınıfın `operator short`rağmen standart dönüşümler dönüştürme tanımlayın arasındaki ilişki `int` ve `short`.  
  
### <a name="declaring-conversion-functions"></a>Dönüştürme işlevleri bildirme  
 Dönüştürme işlevi bildirmek için aşağıdaki kurallar geçerlidir:  
  
-   Dönüştürme işleminin hedef türü dönüştürme işlevi bildirimi önce bildirilmesi gerekir. Sınıflar, yapılar, numaralandırmalar ve tür tanımları dönüştürme işlevi bildirimi içinde bildirilemez.  
  
    ```  
    operator struct String { char string_storage; }() // illegal  
    ```  
  
-   Dönüştürme işlevleri bağımsız değişken almaz. Herhangi bir parametre bildirimine belirten bir hata var.  
  
-   Dönüşüm işlevleri de dönüştürme 's hedef türü adıdır dönüştürme işlevi adı tarafından belirtilen bir dönüş türüne sahip. Dönüş türü bildiriminde belirten bir hata var.  
  
-   Dönüşüm işlevleri sanal olabilir.  
  
-   Dönüşüm işlevleri açık olabilir.  
  
### <a name="explicit-conversion-functions"></a>Açık dönüşüm işlevleri  
 Dönüştürme işlevi açık olmasını bildirilmiş yalnızca, açık bir dönüştürme gerçekleştirmek için kullanılabilir. Bu da örtük olarak sınıf türü bağımsız değişkenleri kabul etmesini dönüştürme işlevin hedef türünde bir bağımsız değişken kabul edin ve hedef türü örnekleri kopyalama-başlatılan bir sınıf türü değerinden engeller işlevleri önler. Aşağıdaki örnekte bir açık dönüşüm işlevi ve hangi kodu doğru biçimlendirilmiş olan etkisini nasıl tanımlanacağı gösterilmektedir.  
  
```  
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
  
 Burada dönüştürme işlevi `operator double` açık, yapılan ve yazmak için bir açık atama `double` işlevinde sunulan `display_balance` dönüştürme gerçekleştirmek için. Bu atama atlanırsa derleyici uygun akış ekleme işleci bulamıyoruz olacaktır `<<` türü için `Money` ve bir hata ortaya çıkabilecek.  
  
