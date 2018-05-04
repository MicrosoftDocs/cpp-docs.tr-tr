---
title: struct (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- struct_cpp
dev_langs:
- C++
helpviewer_keywords:
- struct constructors
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a9ea6bea20ad1591db9b07507b4db959d10a318
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="struct-c"></a>struct (C++)
`struct` Anahtar sözcüğü bir yapı türüne ve/veya bir yapı türünde bir değişken tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[template-spec] struct[ms-decl-spec] [tag [: base-list ]]  
{   
   member-list   
} [declarators];  
[struct] tag declarators;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `template-spec`  
 İsteğe bağlı şablon belirtimleri. Daha fazla bilgi için bkz [şablon belirtimleri](templates-cpp.md).  
  
 `struct`  
 `struct` Anahtar sözcüğü.  
  
 `ms-decl-spec`  
 İsteğe bağlı depolama sınıfı belirtimi. Daha fazla bilgi için bkz [__declspec](../cpp/declspec.md) anahtar sözcüğü.  
  
 `tag`  
 Yapıya verilen tür adı. Etiket yapı kapsamında ayrılmış bir sözcük haline gelir. Etiket isteğe bağlıdır. Atlanırsa, anonim bir yapı tanımlanır. Daha fazla bilgi için bkz: [anonim sınıf türleri](../cpp/anonymous-class-types.md).  
  
 `base-list`  
 Bu yapının üyelerini derleyeceği isteğe bağlı sınıf veya yapı listesi. Bkz: [taban sınıfları](../cpp/base-classes.md) daha fazla bilgi için. Her temel sınıf veya yapı adı bir erişim belirteci tarafından gelmesi ([ortak](../cpp/public-cpp.md), [özel](../cpp/private-cpp.md), [korumalı](../cpp/protected-cpp.md)) ve [sanal](../cpp/virtual-cpp.md) anahtar sözcük. Üye erişimi tablosunda görmek [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md) daha fazla bilgi için.  
  
 `member-list`  
 Yapı üyeleri listesi. Başvurmak [sınıf üyelerine genel bakış](../cpp/class-member-overview.md) daha fazla bilgi için. Burada yalnızca fark `struct` yerine kullanılan `class`.  
  
 `declarators`  
 Sınıfın adlarını belirten bildirimci listesi. Bildirimci listeleri yapı türünün bir veya daha fazla örneğini bildirir. Bildirimler, başlatıcı listeleri içerebilir, sınıfın tüm veri üyesi `public`. Veri üyeleri olduğundan Başlatıcı Listeleri yapılarda ortak `public` varsayılan olarak.  Bkz: [genel bakış, Bildirimciler](../cpp/overview-of-declarators.md) daha fazla bilgi için.  
  
## <a name="remarks"></a>Açıklamalar  
 Yapı türü, kullanıcı tanımlı bileşik bir türdür. Farklı türlere sahip olabilen alanlar veya üyelerden oluşur.  
  
 Üyeleri ancak bu C++'da bir sınıf ile aynı yapısıdır `public` varsayılan olarak.  
  
 Yönetilen sınıflar ve yapılar hakkında daha fazla bilgi için bkz: [sınıflar ve yapılar](../windows/classes-and-structs-cpp-component-extensions.md).  
  
## <a name="using-a-structure"></a>Bir Yapı Kullanma  
 C, açıkça kullanmalısınız `struct` bir yapıyı bildirme anahtar. C++'da kullanmak gerekmez `struct` türü tanımlandıktan sonra anahtar sözcük.  
  
 Yapı türü kapanış küme ayracı ile noktalı virgül arasına bir veya daha fazla virgülle ayrılmış değişken adı yerleştirilerek tanımlandığında değişkenleri bildirme seçeneğine sahip olursunuz.  
  
 Yapı değişkenleri başlatılabilir. Başlatma her değişken için ayraç içine alınmalıdır.  
  
 İlgili bilgi için bkz: [sınıfı](../cpp/class-cpp.md), [UNION](../cpp/unions.md), ve [enum](../cpp/enumerations-cpp.md).  
  
## <a name="example"></a>Örnek  
  
```  
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
  
