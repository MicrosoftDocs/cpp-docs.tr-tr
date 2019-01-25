---
title: struct (C++)
ms.date: 11/04/2016
f1_keywords:
- struct_cpp
helpviewer_keywords:
- struct constructors
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
ms.openlocfilehash: 78d3df4a96cb769cb31760c53c8486c86189e00c
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893346"
---
# <a name="struct-c"></a>struct (C++)

**Yapı** anahtar sözcüğü bir yapı türü ve/veya bir yapı türünün değişkenini tanımlar.

## <a name="syntax"></a>Sözdizimi

```
[template-spec] struct [ms-decl-spec] [tag [: base-list ]]
{
   member-list
} [declarators];
[struct] tag declarators;
```

#### <a name="parameters"></a>Parametreler

*Şablon belirtimi*<br/>
İsteğe bağlı şablon belirtimleri. Daha fazla bilgi için [şablon belirtimleri](templates-cpp.md).

*struct*<br/>
**Yapı** anahtar sözcüğü.

*MS-decl-spec*<br/>
İsteğe bağlı depolama sınıfı belirtimi. Daha fazla bilgi için [__declspec](../cpp/declspec.md) anahtar sözcüğü.

*Etiket*<br/>
Yapıya verilen tür adı. Etiket yapı kapsamında ayrılmış bir sözcük haline gelir. Etiket isteğe bağlıdır. Atlanırsa, anonim bir yapı tanımlanır. Daha fazla bilgi için [anonim sınıf türleri](../cpp/anonymous-class-types.md).

*temel-liste*<br/>
Bu yapının üyelerini derleyeceği isteğe bağlı sınıf veya yapı listesi. Bkz: [taban sınıfları](../cpp/base-classes.md) daha fazla bilgi için. Her temel sınıf veya yapı adı bir erişim belirticisi tarafından öncesinde ([genel](../cpp/public-cpp.md), [özel](../cpp/private-cpp.md), [korumalı](../cpp/protected-cpp.md)) ve [sanal](../cpp/virtual-cpp.md) anahtar sözcüğü. Üye erişimi tabloya bakın [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md) daha fazla bilgi için.

*üye listesi*<br/>
Yapı üyeleri listesi. Başvurmak [sınıf üyelerine genel bakış](../cpp/class-member-overview.md) daha fazla bilgi için. Burada tek fark **yapı** yerine kullanılan **sınıfı**.

*Bildirimciler*<br/>
Yapı adlarını belirten bildirimci listesi. Bildirimci listeleri yapı türünün bir veya daha fazla örneğini bildirir. Bildirimciler, yapının tüm veri üyeleri ise Başlatıcı Listeleri içerebilir **genel**. Veri üyeleri olduğundan Başlatıcı Listeleri yapılarda ortaktır **genel** varsayılan olarak.  Bkz: [genel bakış, Bildirimcileri](../cpp/overview-of-declarators.md) daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

Yapı türü, kullanıcı tanımlı bileşik bir türdür. Farklı türlere sahip olabilen alanlar veya üyelerden oluşur.

Üyeleri şeylerdir ancak C++'da, bir sınıf ile aynı yapısıdır **genel** varsayılan olarak.

Yönetilen sınıflar ve yapı birimleri hakkında daha fazla bilgi için bkz: [sınıfları ve yapıları](../windows/classes-and-structs-cpp-component-extensions.md).

## <a name="using-a-structure"></a>Bir Yapı Kullanma

C'de, açık olarak kullanmalısınız **yapı** bir yapıyı bildirmek için anahtar sözcüğü. C++'ta kullanmak gerekmez **yapı** tür tanımlandıktan sonra anahtar sözcüğü.

Yapı türü kapanış küme ayracı ile noktalı virgül arasına bir veya daha fazla virgülle ayrılmış değişken adı yerleştirilerek tanımlandığında değişkenleri bildirme seçeneğine sahip olursunuz.

Yapı değişkenleri başlatılabilir. Başlatma her değişken için ayraç içine alınmalıdır.

İlgili bilgiler için bkz. [sınıfı](../cpp/class-cpp.md), [birleşim](../cpp/unions.md), ve [enum](../cpp/enumerations-cpp.md).

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
