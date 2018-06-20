---
title: Kapsam (C++) | Microsoft Docs
ms.custom: ''
ms.date: 04/08/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], scope
- scope [C++]
- function prototypes [C++], scope
- class scope
- prototype scope
- functions [C++], scope
- scope, C++ names
ms.assetid: 81fecbb0-338b-4325-8332-49f33e716352
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e79ae7f861553ce2bcd7bee6cbb14a3c2965d4ce
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238769"
---
# <a name="scope-c"></a>Kapsam (C++)

Sınıfı, işlev veya değişken gibi bir program öğesi bildirirken adını yalnızca "görülen" ve programınız belirli bölümlerinde kullanılır. Bir ad olduğu görünür bağlam adlı kendi *kapsam*. Örneğin, bir değişken bildirirseniz `x` bir işlevin içindeki `x` yalnızca o işlev gövdesi içinde görünür durumdadır. Bunun *yerel kapsam*. Programınızın diğer değişkenleri tarafından aynı ada sahip olamaz; farklı kapsamlarda oldukları sürece, bir tanım kuralını ihlal değil ve hiçbir hata oluşur.

Otomatik statik olmayan değişkenleri, kapsamı olduğunda bunlar oluşturulur ve program bellekte yok belirler. 

Kapsam altı tür vardır:

- **Genel kapsamlı** genel herhangi sınıfı, işlev veya ad alanı dışında bildirilmiş bir addır. Ancak, c++'ta bile bu adları örtük bir genel ad alanı mevcut. Global adlar kapsamını bildirimi noktasından bildirilen dosyanın sonuna genişletir. Global adlar için görünürlük ayrıca kurallarıyla yönetilir [bağlantı](program-and-linkage-cpp.md) adı diğer program dosyalarında görünür olup olmadığını belirleyin.

- **Namespace kapsam** içinde bildirilen bir adı bir [ad alanı](namespaces-cpp.md), herhangi bir sınıf ya da enum tanımının veya işlevi blok dışında kendi bildirimi noktasından ad alanı sonuna görülebilir. Bir ad alanı birden çok bloklarında farklı dosyalardaki tanımlanabilir.

- **Yerel kapsam** bir işlevi veya parametre adları dahil olmak üzere lambda içinde bildirilen bir ada sahip yerel kapsamı. Çoğunlukla "yerel" da adlandırılır. Bunlar yalnızca kendi bildirimi noktalarından işlevi veya lambda gövde sonuna görülebilir. Yerel kapsamı, bu makalenin sonraki bölümlerinde açıklanan blok kapsamı türüdür.

- **Sınıf kapsamı** sınıf üyeleri adlara sahip bildirim noktası bakılmaksızın sınıf tanımını boyunca genişletir sınıf kapsamı. Sınıf üyesi erişilebilirlik olan diğer denetlediği **ortak**, **özel**, ve **korumalı** anahtar sözcükler. Genel veya korumalı üyeleri yalnızca üye seçim işleçleri kullanarak erişilebilir (**.** veya **->**) veya işaretçi-üye işleçleri (**.\***  veya **-> \***).

- **Deyimi kapsam** adları içinde bildirilen bir **için**, **varsa**, **sırada**, veya **geçiş** deyimi görünür sonuna kadar bir ifade bloğu.

- **İşlev kapsamı** A [etiket](labeled-statements.md) işlev gövdesi bildirim kendi noktası önce bile boyunca görünür öyledir işlevi kapsama sahip. İşlev kapsamı deyimleri ister yazma olanaklı kılar `goto cleanup` önce `cleanup` etiket bildirildi.

## <a name="hiding-names"></a>Adları Gizleme

Kapalı bir bloğunda bildirerek, bir ad gizleyebilirsiniz. Aşağıdaki şekilde `i` böylece ilişkili değişkeni gizleme iç bloğu içinde yeniden bildirilen `i` dış blok kapsamında.

 ![Blok&#45;kapsam adı gizleme](../cpp/media/vc38sf1.png "vc38SF1") blok kapsamı ve ad gizleme

 Çizimde gösterilen program çıktısı şöyledir:

```cpp
i = 0
i = 7
j = 9
i = 0
```

> [!NOTE]
> Bağımsız değişken `szWhat` işlevi kapsamında olarak değerlendirilir. Bu nedenle, sanki işlevi en dıştaki bloğunda bildirilmiş değerlendirilir.

## <a name="hiding-class-names"></a>Sınıf adları gizleme

 Sınıf adları işlevi, nesne veya değişken veya aynı kapsamda Numaralandırıcı bildirerek gizleyebilirsiniz. Ancak, sınıf adı hala anahtar sözcüğüyle önekli olduğunda erişilip **sınıfı**.

```cpp
// hiding_class_names.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

// Declare class Account at global scope.
class Account
{
public:
    Account( double InitialBalance )
        { balance = InitialBalance; }
    double GetBalance()
        { return balance; }
private:
    double balance;
};

double Account = 15.37;            // Hides class name Account

int main()
{
    class Account Checking( Account ); // Qualifies Account as 
                                       //  class name

    cout << "Opening account with balance of: "
         << Checking.GetBalance() << "\n";
}
//Output: Opening account with balance of: 15.37
```

> [!NOTE]
> Herhangi bir sınıf adı yerleştirin (`Account`) anahtar sözcüğü sınıfı genel kapsamlı değişken hesabından ayırt etmek için kullanılması gereken için çağrılır. Kapsam çözümü işleci (:) sol tarafta sınıf adı ortaya çıktığında bu kuralın geçerli değildir. Kapsam çözümü işleci sol tarafındaki adları her zaman sınıf adları olarak kabul edilir.

 Aşağıdaki örnek, bir nesne türü için bir işaretçi bildirmek gösterilmiştir `Account` kullanarak **sınıfı** anahtar sözcüğü:

```cpp
class Account *Checking = new class Account( Account );
```

 `Account` Başlatıcı (parantez içinde) önceki deyiminde içinde genel kapsama sahip; türü **çift**.

> [!NOTE]
> Bu örnekte gösterildiği gibi tanımlayıcı adları kullanılmasını zayıf programlama stili olarak kabul edilir.

 İşaretçiler hakkında daha fazla bilgi için bkz: [türetilmiş türler](http://msdn.microsoft.com/en-us/aa14183c-02fe-4d81-95fe-beddb0c01c7c). Bildirim ve başlatma sınıfı nesneleri hakkında daha fazla bilgi için bkz: [sınıflar, yapılar ve birleşimleri](../cpp/classes-and-structs-cpp.md). Kullanma hakkında bilgi için **yeni** ve **silmek** serbest deposu işleçleri, bkz: [yeni ve delete işleçleri](new-and-delete-operators.md).

## <a name="hiding-names-with-global-scope"></a>Genel kapsamlı adları gizleme

 Blok kapsamında aynı adı açıkça bildirerek, genel kapsam adlarıyla gizleyebilirsiniz. Ancak, genel kapsam adları kapsam çözümü işleci kullanılarak erişilebilir (`::`).

```cpp
#include <iostream>

int i = 7;   // i has global scope, outside all blocks
using namespace std;

int main( int argc, char *argv[] ) {
   int i = 5;   // i has block scope, hides i at global scope
   cout << "Block-scoped i has the value: " << i << "\n";
   cout << "Global-scoped i has the value: " << ::i << "\n";
}
```

```Output
Block-scoped i has the value: 5
Global-scoped i has the value: 7
```

## <a name="see-also"></a>Ayrıca Bkz.

 [Temel Kavramlar](../cpp/basic-concepts-cpp.md)