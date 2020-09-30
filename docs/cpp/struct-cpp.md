---
title: struct (C++)
ms.date: 11/04/2016
f1_keywords:
- struct_cpp
helpviewer_keywords:
- struct constructors
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
ms.openlocfilehash: d0092cf107159f4c84b431f5eeae130df64dc835
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507468"
---
# <a name="struct-c"></a>struct (C++)

**`struct`** Anahtar sözcüğü bir yapı türü ve/veya bir yapı türünün değişkenini tanımlar.

## <a name="syntax"></a>Sözdizimi

```
[template-spec] struct [ms-decl-spec] [tag [: base-list ]]
{
   member-list
} [declarators];
[struct] tag declarators;
```

#### <a name="parameters"></a>Parametreler

*Şablon-spec*<br/>
İsteğe bağlı şablon belirtimleri. Daha fazla bilgi için [Şablon belirtimleri](templates-cpp.md)' ne bakın.

*sýný*<br/>
**`struct`** Anahtar sözcüğü.

*MS-decl-spec*<br/>
İsteğe bağlı depolama sınıfı belirtimi. Daha fazla bilgi için [__declspec](../cpp/declspec.md) anahtar sözcüğüne bakın.

*etiket*<br/>
Yapıya verilen tür adı. Etiket yapı kapsamında ayrılmış bir sözcük haline gelir. Etiket isteğe bağlıdır. Atlanırsa, anonim bir yapı tanımlanır. Daha fazla bilgi için bkz. [anonim sınıf türleri](../cpp/anonymous-class-types.md).

*temel liste*<br/>
Bu yapının üyelerini derleyeceği isteğe bağlı sınıf veya yapı listesi. Daha fazla bilgi için bkz. [temel sınıflar](../cpp/base-classes.md) . Her temel sınıf veya yapı adı öncesinde bir erişim belirticisi ([genel](../cpp/public-cpp.md), [özel](../cpp/private-cpp.md), [korumalı](../cpp/protected-cpp.md)) ve [sanal](../cpp/virtual-cpp.md) anahtar sözcük olabilir. Daha fazla bilgi için [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md) içindeki üye erişimi tablosuna bakın.

*üye listesi*<br/>
Yapı üyeleri listesi. Daha fazla bilgi için [sınıf üyesine genel bakış](../cpp/class-member-overview.md) bölümüne bakın. Burada tek fark, **`struct`** yerinde kullanılır **`class`** .

*Bildirimciler*<br/>
Yapının adlarını belirten bildirimci listesi. Bildirimci listeleri yapı türünün bir veya daha fazla örneğini bildirir. Bildiriciler, yapının tüm veri üyeleri ise başlatıcı listeleri içerebilir **`public`** . Veri üyeleri varsayılan olarak olduğundan, başlatıcı listeleri yapılarda ortaktır **`public`** .  Daha fazla bilgi için bkz. [Bildirimcilerin genel bakış](./declarations-and-definitions-cpp.md) .

## <a name="remarks"></a>Açıklamalar

Yapı türü, kullanıcı tanımlı bileşik bir türdür. Farklı türlere sahip olabilen alanlar veya üyelerden oluşur.

C++ ' da, bir yapı, üyelerinin varsayılan olarak olması dışında bir sınıf ile aynıdır **`public`** .

C++/CLı ' daki yönetilen sınıflar ve yapılar hakkında daha fazla bilgi için bkz. [sınıflar ve yapılar](../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="using-a-structure"></a>Bir Yapı Kullanma

C 'de, **`struct`** bir yapıyı bildirmek için anahtar sözcüğünü açık olarak kullanmalısınız. C++ ' da, **`struct`** tür tanımlandıktan sonra anahtar sözcüğünü kullanmanız gerekmez.

Yapı türü kapanış küme ayracı ile noktalı virgül arasına bir veya daha fazla virgülle ayrılmış değişken adı yerleştirilerek tanımlandığında değişkenleri bildirme seçeneğine sahip olursunuz.

Yapı değişkenleri başlatılabilir. Başlatma her değişken için ayraç içine alınmalıdır.

İlgili bilgiler için bkz. [Class](../cpp/class-cpp.md), [Union](../cpp/unions.md)ve [enum](../cpp/enumerations-cpp.md).

## <a name="example"></a>Örnek

```cpp
#include <iostream>
using namespace std;

struct PERSON {   // Declare PERSON struct type
    int age;   // Declare member types
    long ss;
    float weight;
    char name[25];
} family_member;   // Define object of type PERSON

struct CELL {   // Declare CELL bit field
    unsigned short character  : 8;  // 00000000 ????????
    unsigned short foreground : 3;  // 00000??? 00000000
    unsigned short intensity  : 1;  // 0000?000 00000000
    unsigned short background : 3;  // 0???0000 00000000
    unsigned short blink      : 1;  // ?0000000 00000000
} screen[25][80];       // Array of bit fields

int main() {
    struct PERSON sister;   // C style structure declaration
    PERSON brother;   // C++ style structure declaration
    sister.age = 13;   // assign values to members
    brother.age = 7;
    cout << "sister.age = " << sister.age << '\n';
    cout << "brother.age = " << brother.age << '\n';

    CELL my_cell;
    my_cell.character = 1;
    cout << "my_cell.character = " << my_cell.character;
}
// Output:
// sister.age = 13
// brother.age = 7
// my_cell.character = 1
```
