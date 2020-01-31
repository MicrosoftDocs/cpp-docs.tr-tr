---
title: extern (C++)
description: C++ Language extern anahtar sözcüğüne kılavuzluk edin.
ms.date: 01/28/2020
f1_keywords:
- extern
- extern_CPP
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
no-loc:
- extern
- const
- constexpr
- permissive
ms.openlocfilehash: 422b6960802c59f1c45e0c22a4a85988c808a5b3
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821772"
---
# <a name="opno-locextern-c"></a>extern (C++)

**extern** anahtar sözcüğü, genel bir değişkene, işleve veya şablon bildirimine uygulanabilir. Simgenin *dış bağlantıya*sahip olduğunu belirtir. Bağlantı hakkında arka plan bilgileri ve genel değişkenlerin kullanılmasına neden önerilmez, bkz. [çeviri birimleri ve bağlantı](program-and-linkage-cpp.md).

**extern** anahtar sözcüğünün, içeriğe bağlı olarak dört anlamı vardır:

- **const** genel olmayan bir değişken bildiriminde, **extern** değişkenin veya işlevin başka bir çeviri biriminde tanımlandığını belirtir. **extern** , değişkenin tanımlandığı yer hariç tüm dosyalarda uygulanmalıdır.

- **const** değişken bildiriminde, değişkenin dış bağlantı olduğunu belirtir. **extern** tüm dosyalardaki tüm bildirimlere uygulanmalıdır. (Genel **const** değişkenlerinin varsayılan olarak iç bağlantısı vardır.)

- **"c"extern** , işlevin başka bir yerde tanımlandığını belirtir ve C dili çağırma kuralını kullanır. extern "C" değiştiricisi, bir bloktaki birden çok işlev bildiriminde de uygulanabilir.

- Şablon bildiriminde, **extern** şablonun başka bir yerde zaten başlatılmış olduğunu belirtir. **extern** , derleyicisine, geçerli konumda yeni bir tane oluşturmak yerine, diğer örnek oluşturmayı yeniden kullanabilmeyeceğini söyler. Bu **extern** kullanımı hakkında daha fazla bilgi için bkz. [açık örnek oluşturma](explicit-instantiation.md).

## <a name="opno-locextern-linkage-for-non-opno-locconst-globals"></a>const olmayan genel öğeler için extern bağlantısı

Bağlayıcı genel bir değişken bildiriminden önce **extern** gördüğünde, tanımı başka bir çeviri biriminde arar. Genel kapsamda **const** olmayan değişkenlerin bildirimleri varsayılan olarak dış ' dır. Yalnızca tanımı sağlamayan bildirimlere **extern** uygulayın.

```cpp
//fileA.cpp
int i = 42; // declaration and definition

//fileB.cpp
extern int i;  // declaration only. same as i in FileA

//fileC.cpp
extern int i;  // declaration only. same as i in FileA

//fileD.cpp
int i = 43; // LNK2005! 'i' already has a definition.
extern int i = 43; // same error (extern is ignored on definitions)
```

## <a name="opno-locextern-linkage-for-opno-locconst-globals"></a>const genel için extern bağlantısı

**const** genel değişkeninin varsayılan olarak iç bağlantısı vardır. Değişkenin dış bağlantıya sahip olmasını istiyorsanız, **extern** anahtar sözcüğünü tanımına ve diğer dosyalardaki diğer tüm bildirimlere uygulayın:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="opno-locextern-opno-locconstexpr-linkage"></a>extern constexpr bağlantısı

Visual Studio 2017 sürüm 15,3 ve önceki sürümlerde, derleyici her zaman bir **constexpr** değişken iç bağlantı vermiştir ve değişken **extern** olarak işaretlenmiş olsa bile. Visual Studio 2017 sürüm 15,5 ve sonraki sürümlerde, [/Zc: externConstexpr](../build/reference/zc-externconstexpr.md) derleyici anahtarı doğru standartlara uygun davranışı sunar. Sonuç olarak seçenek varsayılan olarak olur. [/permissive-](../build/reference/permissive-standards-conformance.md) seçeneği **/Zc: externConstexpr**'ı etkinleştirmez.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Bir üst bilgi dosyası **extern** **constexpr** olarak belirtilen bir değişken içeriyorsa, yinelenen bildirimlerinin birleştirilmek için `__declspec(selectany)` olarak işaretlenmelidir:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="opno-locextern-c-and-opno-locextern-c-function-declarations"></a>extern "C" ve extern "C++" işlev bildirimleri

' C++De, bir dize ile birlikte kullanıldığında **extern** , başka bir dilin bağlantı kurallarının, bildirimcler için kullanıldığını belirtir. C işlevlerine ve verilerine, yalnızca daha önce C bağlantısı varmış gibi bildirilirse erişilebilir. Ancak, ayrı olarak derlenmiş bir çeviri biriminde tanımlanmalıdır.

Microsoft C++ , *dize sabit değeri* alanında **"C"** ve **C++""** dizelerini destekler. Tüm standart içerme dosyaları, C++ programlarda çalışma zamanı kitaplık işlevlerinin kullanılmasına izin vermek için **extern "C"** sözdizimini kullanır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C bağlantısı olan adların nasıl bildirilemeyeceğini göstermektedir:

```cpp
// Declare printf with C linkage.
extern "C" int printf(const char *fmt, ...);

//  Cause everything in the specified
//  header files to have C linkage.
extern "C" {
    // add your #include statements here
#include <stdio.h>
}

//  Declare the two functions ShowChar
//  and GetChar with C linkage.
extern "C" {
    char ShowChar(char ch);
    char GetChar(void);
}

//  Define the two functions
//  ShowChar and GetChar with C linkage.
extern "C" char ShowChar(char ch) {
    putchar(ch);
    return ch;
}

extern "C" char GetChar(void) {
    char ch;
    ch = getchar();
    return ch;
}

// Declare a global variable, errno, with C linkage.
extern "C" int errno;
```

Bir işlevde birden fazla bağlantı belirtimi varsa, bunları kabul etmelidir. İşlevleri hem C hem C++ de bağlantısına sahip olarak bildirmek bir hatadır. Ayrıca, bir programda bir işlev için iki bildirim varsa — bir bağlantı belirtimi ve diğeri olmadan — bağlantı belirtimine sahip bildirim öncelikle olmalıdır. Zaten bağlantı belirtimine sahip olan işlevlerin tüm gereksiz bildirimlerine ilk bildirimde belirtilen bağlantı verilir. Örneğin:

```cpp
extern "C" int CFunc1();
...
int CFunc1();            // Redeclaration is benign; C linkage is
                         //  retained.

int CFunc2();
...
extern "C" int CFunc2(); // Error: not the first declaration of
                         //  CFunc2;  cannot contain linkage
                         //  specifier.
```

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)\
[Çeviri birimleri ve bağlantı](program-and-linkage-cpp.md)\
[C\extern depolama sınıfı Belirleyicisi](../c-language/extern-storage-class-specifier.md)
[C\ tanımlayıcıları davranışı](../c-language/behavior-of-identifiers.md)
[C 'de bağlantı](../c-language/linkage.md)
