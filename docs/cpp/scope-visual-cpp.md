---
title: Kapsam (C++)
ms.date: 11/19/2018
helpviewer_keywords:
- classes [C++], scope
- scope [C++]
- function prototypes [C++], scope
- class scope
- prototype scope
- functions [C++], scope
- scope, C++ names
ms.assetid: 81fecbb0-338b-4325-8332-49f33e716352
ms.openlocfilehash: 5cff7a4607201175c7095a87134850583b76d636
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227094"
---
# <a name="scope-c"></a>Kapsam (C++)

Sınıf, işlev veya değişken gibi bir program öğesi bildirdiğinizde, adı yalnızca "görünebilir" olabilir ve programınızın belirli bölümlerinde kullanılabilir. Bir adın görünür olduğu bağlam *kapsamı*olarak adlandırılır. Örneğin, bir işlev içinde bir değişken bildirirseniz `x` , `x` Bu işlev gövdesinde yalnızca görünür. *Yerel kapsama*sahiptir. Programınızda aynı ada sahip başka değişkenlere sahip olabilirsiniz; Farklı kapsamlarda oldukları sürece, tek bir tanım kuralını ihlal etmez ve hata oluşmaz.

Otomatik statik olmayan değişkenler için, kapsam Program belleğinde ne zaman oluşturulup yok edildiğini de belirler.

Altı tür kapsam vardır:

- **Genel kapsam** Genel ad, herhangi bir sınıf, işlev veya ad alanı dışında bildirildiği bir addır. Ancak, C++ ' da bu adlar dolaylı bir genel ad alanıyla birlikte bulunur. Genel adların kapsamı, bildirim noktasından, bildirildiği dosyanın sonuna kadar uzanır. Genel adlar için görünürlük Ayrıca, adın programdaki diğer dosyalarda görünür olup olmadığını belirleyen [bağlantı](program-and-linkage-cpp.md) kurallarına tabidir.

- **Ad alanı kapsamı** Herhangi bir sınıf veya sabit listesi tanımı ya da işlev bloğunun dışında bir [ad alanı](namespaces-cpp.md)içinde belirtilen bir ad, bildirim noktasından ad alanının sonuna kadar görünür olur. Bir ad alanı, farklı dosyalar genelinde birden çok blok içinde tanımlanabilir.

- **Yerel kapsam** Parametre adları da dahil olmak üzere bir işlev veya lambda içinde belirtilen bir ad, yerel kapsama sahiptir. Bunlar genellikle "Yereller" olarak anırlar. Bunlar yalnızca kendi bildirim noktasından işlevin veya lambda gövdesinin sonuna kadar görünür. Yerel kapsam, bu makalenin ilerleyen kısımlarında ele alınan bir blok kapsamı türüdür.

- **Sınıf kapsamı** Sınıf üyelerinin adları, bildirim noktasına bakılmaksızın sınıf tanımının tamamında genişleyen sınıf kapsamına sahiptir. Sınıf üyesi erişilebilirliği **`public`** ,, **`private`** ve anahtar kelimeleri tarafından daha fazla denetlenir **`protected`** . Ortak veya korumalı üyelere yalnızca üye seçim işleçleri (**.** ya da **->** ) ya da üye işaretçisi işleçleri (**.** <strong>\*</strong> veya **->** <strong>\*</strong> ).

- **Ekstre kapsamı** ,, Veya ifadesinde belirtilen adlar, **`for`** **`if`** **`while`** **`switch`** ifade bloğunun sonuna kadar görünür.

- **İşlev kapsamı** Bir [etikette](labeled-statements.md) işlev kapsamı vardır. Bu, bir işlev gövdesi boyunca, bildirim noktası önünde bile görünür olduğu anlamına gelir. İşlev kapsamı `goto cleanup` , etiket bildirilmeden önce gibi deyimler yazmanızı mümkün kılar `cleanup` .

## <a name="hiding-names"></a>Adları Gizleme

Bir adı, bir kapalı blokta bildirerek gizleyebilirsiniz. Aşağıdaki şekilde, `i` iç blok içinde yeniden bildirilmiştir ve böylece `i` dış blok kapsamında ilişkili değişkeni gizler.

![&#45;kapsam adı gizlemeyi engelle](../cpp/media/vc38sf1.png "&#45;kapsam adı gizlemeyi engelle") <br/>
Kapsam ve ad gizlemeyi engelle

Şekilde gösterilen programın çıktısı:

```cpp
i = 0
i = 7
j = 9
i = 0
```

> [!NOTE]
> Bağımsız değişken `szWhat` işlevin kapsamında olduğu kabul edilir. Bu nedenle, işlevin en dıştaki bloğunda bildirildiği gibi davranır.

## <a name="hiding-class-names"></a>Sınıf adlarını gizleme

Aynı kapsamda bir işlev, nesne veya değişken ya da Numaralandırıcı bildirerek sınıf adlarını gizleyebilirsiniz. Ancak, anahtar sözcüğünün önekli sınıf adına yine de erişilebilir **`class`** .

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

    cout << "Opening account with a balance of: "
         << Checking.GetBalance() << "\n";
}
//Output: Opening account with a balance of: 15.37
```

> [!NOTE]
> Herhangi bir yerde sınıf adı ( `Account` ) çağrılır, anahtar sözcük sınıfı, bunu küresel kapsamlı değişken hesabından ayırt etmek için kullanılmalıdır. Bu kural, sınıf adı kapsam çözümleme işlecinin (::) ' nin sol tarafında gerçekleştiğinde uygulanmaz. Kapsam çözümleme işlecinin sol tarafındaki adlar her zaman sınıf adları olarak kabul edilir.

Aşağıdaki örnek, `Account` anahtar sözcüğünü kullanarak türünde bir nesne için bir işaretçinin nasıl bildirileceğini gösterir **`class`** :

```cpp
class Account *Checking = new class Account( Account );
```

`Account`Yukarıdaki deyimindeki başlatıcıdaki (parantez içinde) genel kapsama sahiptir; bu tür **`double`** .

> [!NOTE]
> Bu örnekte gösterildiği gibi tanımlayıcı adlarının yeniden kullanılması kötü programlama stili olarak kabul edilir.

Sınıf nesnelerinin bildirimi ve başlatılması hakkında daha fazla bilgi için bkz. [sınıflar, yapılar ve birleşimler](../cpp/classes-and-structs-cpp.md). Ve serbest mağaza işleçlerini kullanma hakkında daha fazla bilgi için **`new`** **`delete`** bkz. [New ve delete işleçleri](new-and-delete-operators.md).

## <a name="hiding-names-with-global-scope"></a>Genel kapsamlı adları gizleme

Blok kapsamında aynı adı açıkça bildirerek genel kapsamlı adları gizleyebilirsiniz. Ancak, genel kapsam adlarına kapsam çözümleme işleci () kullanılarak erişilebilir `::` .

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

## <a name="see-also"></a>Ayrıca bkz.

[Temel kavramlar](../cpp/basic-concepts-cpp.md)
