---
title: "Numaralandırmalar (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- enum_cpp
dev_langs:
- C++
helpviewer_keywords:
- declarations, enumerations
- enumerators, declaring
- enum keyword [C++]
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: 081829db-5dca-411e-a53c-bffef315bcb3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96b1b29baaa779fda1e1f076daf3d8bd9335403b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="enumerations-c"></a>Numaralandırmalar [C++]
Numaralandırma numaralandırıcılar bilinen adlandırılmış tamsayı sabitleri kümesi içeren bir kullanıcı tanımlı bir türüdür.  
  
> [!NOTE]
>  Bu makalede ISO standart C++ dili kapsayan `enum` türü ve kapsamlı (veya kesin türü belirtilmiş) `enum class` C ++ 11'de sunulan türü. Hakkında bilgi için `public enum class` veya `private enum class` türleri C + +/ CLI ve C + +/ CX, bkz: [enum sınıfı](../windows/enum-class-cpp-component-extensions.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
// unscoped enum:  
enum [identifier] [: type]  
{enum-list};   
  
// scoped enum:  
enum [class|struct]   
[identifier] [: type]   
{enum-list};  
```  
  
```  
// Forward declaration of enumerations  (C++11):  
enum A : int; // non-scoped enum must have type specified
enum class B; // scoped enum defaults to int but ...
enum class C : short;  // ... may have any integral underlying type
```  
  
## <a name="parameters"></a>Parametreler  
 `identifier`  
 Numaralandırma verilen tür adı.  
  
 `type`  
 Numaralandırmalar temel alınan türü; Tüm numaralandırıcılar aynı temel türüne sahip. Herhangi bir tam sayı türü olabilir.  
  
 `enum-list`  
 Listedeki numaralandırıcılar virgülle ayrılmış listesi. Her bir numaralandırıcı veya kapsamdaki değişken adı benzersiz olmalıdır. Ancak, değerleri yinelenebilir. Dizininden kapsam dışı bir enum içindeki kapsamı çevresindeki kapsamıdır; kapsamlı bir enum içindeki kapsamıdır `enum-list` kendisi.  Kapsamlı bir enum içindeki listeden yeni bir tam sayı türü yürürlükte tanımlayan boş olabilir.
  
 `class`  
 Bu anahtar sözcük bildiriminde kullanarak enum kapsamlı, belirttiğiniz ve bir `identifier` sağlanmalıdır. Aynı zamanda `struct` anahtar sözcüğü yerine `class`, bu bağlamda anlam olarak eşdeğer olarak.  
  
## <a name="enumerator-scope"></a>Numaralandırıcı kapsamı  
 Numaralandırma adlandırılmış sabitler olarak temsil edilir ve numaralandırmalar olarak da adlandırılan değerleri aralığı tanımlamak için bir bağlam sağlar. Özgün C ve C++ enum türlerinde nitelenmemiş numaralandırmalar, içinde enum bildirildiği kapsam boyunca görülebilir. Kapsamlı numaralandırmaları Numaralandırıcı adı enum tür adıyla nitelendirilmelidir. Aşağıdaki örnek, bu numaralandırmaları iki tür arasındaki temel fark gösterir:  
  
```cpp  
namespace CardGame_Scoped  
{  
    enum class Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void PlayCard(Suit suit)  
    {  
        if (suit == Suit::Clubs) // Enumerator must be qualified by enum type  
        { /*...*/}  
    }  
}  
  
namespace CardGame_NonScoped  
{  
    enum Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void PlayCard(Suit suit)  
    {  
        if (suit == Clubs) // Enumerator is visible without qualification  
        { /*...*/  
        }  
    }  
}  
```  
  
 Bir numaralandırma içinde her ad numaralandırma değerleri sırasına göre onun yerine karşılık gelen bir tam sayı değeri atanır. Varsayılan olarak, ilk değer 0 atanır, 1 vb. bir sonraki atandı, ancak aşağıda gösterildiği gibi bir numaralandırıcı değerinin açıkça ayarlayabilirsiniz:  
  
```cpp  
enum Suit { Diamonds = 1, Hearts, Clubs, Spades };  
  
```  
  
 Numaralandırıcı `Diamonds` değeri atanmış `1`. Açık bir değer verilmemişse sonraki numaralandırıcılar önceki Numaralandırıcı artı bir değer alır. Önceki örnekte, `Hearts` 2, değer olurdu `Clubs` 3 olması ve benzeri.  
  
 Her Numaralandırıcı bir sabit değer olarak kabul edilir ve benzersiz bir ad kapsamı içinde olmalıdır nerede `enum` (dizininden kapsam dışı numaralandırmalar için) tanımlanan veya enum kendisini (için kapsamlı numaralandırmaları) içinde. Adlar verilen değerlerin benzersiz olması gerekmez. Örneğin, varsa dizininden kapsam dışı enum bildirimi `Suit` bu:  
  
```cpp  
enum Suit { Diamonds = 5, Hearts, Clubs = 4, Spades };  
```  
  
 Ardından değerlerini `Diamonds`, `Hearts`, `Clubs`, ve `Spades` 5, 6, 4 ve 5, sırasıyla şunlardır. 5 birden çok kez kullanılır dikkat edin. Bu izin rağmen değil amaçlanmamış olabilir. Bu kurallar kapsamlı numaralandırmalar için aynıdır.  
  
 ## <a name="casting-rules"></a>Atama kuralları  
  
 Dizininden kapsam dışı liste sabitlerine örtük olarak dönüştürülebilir `int`, ancak bir `int` hiçbir zaman bir enum değeri örtük olarak dönüştürülebilir değildir. Ne olacağını atamak çalışırsanız aşağıdaki örnekte gösterildiği `hand` olmayan bir değer bir `Suit`:  
  
```cpp  
int account_num = 135692;  
Suit hand;  
hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'  
  
```  
  
 Bir cast dönüştürmek için gereken bir `int` için kapsamlı veya dizininden kapsam dışı bir numaralandırıcı. Ancak, bir cast olmadan bir tamsayı değerine dizininden kapsam dışı bir Numaralayıcı yükseltebilirsiniz.  
  
```cpp  
int account_num = Hearts; //OK if Hearts is in a unscoped enum  
```  
  
 Örtük dönüşümler bu şekilde kullanmak için istenmeyen yan etkileri yol açabilir. Dizininden kapsam dışı numaralandırmaları ile ilişkili programlama hataları ortadan kaldırmanıza yardımcı olmak için kapsamlı enum değerleri kesin türü belirtilmiş. Kapsamlı numaralandırmalar (tanımlayıcı) enum tür adıyla nitelenmelidir ve dolaylı olarak, aşağıdaki örnekte gösterildiği gibi dönüştürülemiyor:  
  
```cpp  
namespace ScopedEnumConversions  
{  
    enum class Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void AttemptConversions()  
    {  
        Suit hand;   
        hand = Clubs; // error C2065: 'Clubs' : undeclared identifier  
        hand = Suit::Clubs; //Correct.  
        int account_num = 135692;  
        hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'  
        hand = static_cast<Suit>(account_num); // OK, but probably a bug!!!  
  
        account_num = Suit::Hearts; // error C2440: '=' : cannot convert from 'Suit' to 'int'  
        account_num = static_cast<int>(Suit::Hearts); // OK  
}  
  
```  
  
 Dikkat satırı `hand = account_num;` dizininden kapsam dışı numaralandırmaları ile oluşan hatasından daha önce gösterildiği gibi hala neden olur. Bir açık atama ile izin verilir. Bununla birlikte, kapsamlı numaralandırmalar, denenen dönüştürme sonraki deyiminde `account_num = Suit::Hearts;`, artık bir açık atama izin verilir. 

## <a name="enums-with-no-enumerators"></a>Numaralandırmaları hiçbir numaralandırıcılar ile
**Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): bir numaralandırma (normal veya kapsamlı) açık bir temel alınan tür ve hiçbir numaralandırmalar tanımlayarak, etkin yeni bir getirebilir integral yazın başka bir türüne örtük dönüştürme vardır. Yerleşik temel alınan türü yerine bu türünü kullanarak tarafından yanlışlıkla örtük dönüşümler kaynaklanan Zarif hataları olasılığını ortadan kaldırabilirsiniz.  


```cpp
enum class byte : unsigned char { };
```

Yeni türü, temel alınan tür tam bir kopyasını ve bu nedenle performans cezaları ABIs arasında kullanılabileceği anlamına gelir aynı çağırma kuralı sahip. Tür atama yok türündeki değişkenler doğrudan listesi başlatma kullanarak başlatıldıklarında gereklidir. Aşağıdaki örnek, numaralandırmaları hiçbir numaralandırıcılar çeşitli bağlamlarda ile başlatmak gösterilmektedir:

```cpp
enum class byte : unsigned char { };

enum class E : int { };
E e1{ 0 };
E e2 = E{ 0 };

struct X 
{
    E e{ 0 };
    X() : e{ 0 } { }
};

E* p = new E{ 0 }; 

void f(E e) {};

int main()
{
    f(E{ 0 });
    byte i{ 42 };
    byte j = byte{ 42 };

    // unsigned char c = j; // C2440: 'initializing': cannot convert from 'byte' to 'unsigned char'
    return 0;
}
``` 
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)