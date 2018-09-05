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
ms.openlocfilehash: 733d090073fe2ed08a0499ea205c2377b4bdb289
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679703"
---
# <a name="scope-c"></a>Kapsam (C++)

Bir program öğesi gibi bir sınıf, işlev veya değişkeni bildirdiğinizde, onun adı yalnızca "görülen" ve programınızın belirli bölümlerinde kullanılan. Bir ad olduğu görünür bağlam adı verilen kendi *kapsam*. Örneğin, bir değişken bildirirseniz `x` bir işlev içinde `x` yalnızca bu işlev gövdesi içinde görünür olur. Sahip *yerel kapsama*. Programınızda başka değişkenler tarafından aynı ada sahip olabilir; farklı kapsamlarda oldukları sürece tek tanım kuralı ihlal değildir ve herhangi bir hata ortaya çıkar.

Otomatik statik olmayan değişkenler, kapsam, bunlar oluşturulur ve programı belleğe yok belirler. 

Kapsam altı tür vardır:

- **Genel kapsam** genel bir sınıf, işlev veya ad alanı dışında bildirilen bir addır. Ancak c++'ta bile bu adlar örtük genel ad alanı ile mevcut. Global adlar kapsamını bildirim noktasından bildirilmiş olan dosyanın sonuna kadar genişletir. Genel adlar için görünürlük kuralları tarafından da yönetilen [bağlantı](program-and-linkage-cpp.md) adı programdaki diğer dosyalardaki görünür olup olmadığını belirler.

- **Namespace kapsam** içinde bildirilen bir adı bir [ad alanı](namespaces-cpp.md), herhangi bir sınıf veya numaralandırma tanımı veya işlev bloğu dışında bildirim noktasında ad alanı sonuna görülebilir. Bir ad alanı birden çok bloklarında farklı dosyalardaki tanımlanabilir.

- **Yerel kapsama** bir işlev veya parametre adları da dahil olmak üzere, lambda içinde bildirilen bir ada sahip yerel kapsamı. Genellikle "yerel" da adlandırılır. Bunlar yalnızca bildirimin kendi noktalarından işlevi veya lambda gövdesi sonuna görülebilir. Yerel kapsama bir blok kapsamı, bu makalenin sonraki bölümlerinde ele alınan türüdür.

- **Sınıf kapsamında** adlarında sınıfı üyeleri sınıf tanımının bildirim noktasından bakılmaksızın boyunca genişleten sınıf kapsamı. Sınıf üyesi erişilebilirliği olan tarafından denetlenen yapılacaktır **genel**, **özel**, ve **korumalı** anahtar sözcükleri. Ortak veya korumalı üyeler, yalnızca üye seçim işleçleri kullanarak erişilebilir (**.** veya **->**) veya işaretçi-üye işleçleri (**.** <strong>\*</strong> veya **->** <strong>\*</strong>).

- **Deyimi kapsamı** bildirilen adlar bir **için**, **varsa**, **sırada**, veya **geçiş** deyimi görünür sonuna kadar deyim bloğu.

- **İşlev kapsamı** A [etiket](labeled-statements.md) genelinde bir işlev gövdesinin önce bildirim noktasında görülebilir olduğu anlamına gelir, işlev kapsamına sahiptir. İşlev kapsamında ister ifadeleri yazmak mümkün kılar `goto cleanup` önce `cleanup` etiket bildirilir.

## <a name="hiding-names"></a>Adları Gizleme

Kapalı bir bloğunda bildirerek adları gizleyebilirsiniz. Aşağıdaki şekilde, `i` böylece ile ilişkili bir değişkeni gizleme iç bloğu içinde yeniden tanımlanıyor `i` Dıştaki bloğun kapsamında.

 ![Blok&#45;kapsam ad gizleme](../cpp/media/vc38sf1.png "vc38SF1") blok kapsamı ve ad gizleme

 Şekilde gösterildiği programının çıktısı şöyledir:

```cpp
i = 0
i = 7
j = 9
i = 0
```

> [!NOTE]
> Bağımsız değişken `szWhat` işlev kapsamında olduğu kabul edilir. Bu nedenle, işlevin en dıştaki bloğunun içinde bildirilmiş yokmuş gibi değerlendirilir.

## <a name="hiding-class-names"></a>Sınıf adlarını gizleme

 İşlev, nesne veya değişken veya aynı kapsamda Numaralandırıcı bildirerek sınıf adları gizleyebilirsiniz. Ancak, sınıf adı hala anahtar sözcüğü öneki erişilebilir **sınıfı**.

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
> Herhangi bir sınıf adı yerleştirin (`Account`) anahtar sözcüğü sınıfı kapsamlı genel değişken hesaptan ayırmak için kullanılması gereken için çağrılır. Sınıf adı kapsam çözümleme işleci (:) sol tarafında oluştuğunda, bu kuralı uygulanmaz. Kapsam çözümleme işlecinin sol tarafındaki adlar her zaman sınıf adları olarak kabul edilir.

 Aşağıdaki örnek, bir işaretçi bir nesne türü bildirmek gösterilmiştir `Account` kullanarak **sınıfı** anahtar sözcüğü:

```cpp
class Account *Checking = new class Account( Account );
```

 `Account` Önceki deyim (parantez) başlatıcısında genel kapsam vardır; türünde, **çift**.

> [!NOTE]
> Bu örnekte gösterildiği gibi tanımlayıcı adları yeniden kötü programlama stil olarak kabul edilir.

Bildirim ve sınıf nesnelerin başlatılması hakkında daha fazla bilgi için bkz. [sınıflar, yapılar ve birleşimler](../cpp/classes-and-structs-cpp.md). Kullanma hakkında bilgi için **yeni** ve **Sil** ücretsiz depolama işleçleri, bkz: [yeni ve delete işleçleri](new-and-delete-operators.md).

## <a name="hiding-names-with-global-scope"></a>Genel kapsamlı adları gizleme

 Blok kapsamında aynı adı açıkça bildirerek genel kapsamı ile adları gizleyebilirsiniz. Ancak, genel kapsam adlarına kapsam çözümleme işleci kullanılarak erişilebilir (`::`).

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
 [Temel Kavramlar](../cpp/basic-concepts-cpp.md)