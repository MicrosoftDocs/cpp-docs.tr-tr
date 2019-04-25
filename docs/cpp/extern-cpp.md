---
title: extern (C++)
ms.date: 04/12/2018
f1_keywords:
- extern
- extern_CPP
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
ms.openlocfilehash: 4a3a4e158794e06f28c638e87e014ddc3fb99837
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183745"
---
# <a name="extern-c"></a>extern (C++)

**Extern** anahtar sözcüğü, bir şey adı olduğunu belirtmek için bir genel değişken, işlev veya şablon bildirimine uygulanan *dış bağlantısı*. Bağlantı ve genel değişkenler kullanımına neden önerilmez arka plan bilgileri için bkz. [Program ve bağlantı](program-and-linkage-cpp.md).

**Extern** anahtar sözcüğü bağlama dört anlamları vardır:

1. const olmayan genel değişken bildiriminde, **extern** değişken veya işlev, başka bir çeviri biriminde tanımlanan belirtir. **Extern** değişkeni tanımlandığı tüm dosyalarda dışındaki uygulanmalıdır.
1. const Değişken bildiriminde değişkeni dış bağlantıya sahip olduğunu belirtir. **Extern** tüm dosyalardaki tüm bildirimleri için uygulanması gerekir. (Const genel değişkenler, varsayılan olarak iç bağlantısı vardır.)
1. **extern "C"** işlevi başka bir yerde tanımlandığını ve C dili çağırma kuralı gerektiğini belirtir. Extern "C" değiştiricisi, bir blok içinde birden çok işlev bildirimleri için de uygulanabilir.
1. bir şablon bildiriminde şablonu zaten başka bir yerde oluşturulmuş olduğunu belirtir. Geçerli konumda yeni bir tane oluşturmak yerine bir diğer oluşturma yeniden kullanmak, derleyiciye bir iyileştirme budur. Bu kullanımı hakkında daha fazla bilgi için **extern**, bkz: [şablonları](templates-cpp.md).

## <a name="extern-linkage-for-non-const-globals"></a>const olmayan globals için dış bağlantı

Bağlayıcı gördüğünde **extern** genel bir değişken bildirimi önce başka bir çeviri birimindeki tanımında arar. Genel kapsamda olmayana değişkenlerin bildirimleri varsayılan olarak dıştır; yalnızca geçerli **extern** tanımı sağlamayan bildirimlere.

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

## <a name="extern-linkage-for-const-globals"></a>const globals için dış bağlantı

A **const** genel değişkeni varsayılan olarak iç bağlantısı vardır. Değişkeninin dış bağlantıya sahip olmasını isterseniz, uygulama **extern** anahtar sözcüğü için tüm diğer dosyaları bildirimlerinde de tanımına:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>Extern constexpr bağlantı

Visual Studio 2017 sürüm 15.3 ve önceki sürümleri, değişkeni extern bile işaretlendi, derleyici her zaman bir constexpr değişken iç bağlantı getirdi. Visual Studio 2017 sürüm 15.5, yeni bir derleyici anahtarı ([/ZC: externconstexpr](../build/reference/zc-externconstexpr.md)) doğru standartlara uyan davranışını etkinleştirir. Sonuçta bu varsayılan olur.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Bir üstbilgi dosyası bir değişken bildirilen extern constexpr içeriyorsa, bu işaretlenmesi gerekir **__declspec(selectany)** doğru birleştirilmiş, yinelenen bildirimler sahip olmak için:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>extern "C" ve extern "C++" işlev bildirimleri

Bir dizeyle kullanıldığında C++ ' ta **extern** Bildirimciler için başka bir dilin bağlantı kurallarının kullanıldığını belirtir. C işlevlerine ve verilerine, yalnızca daha önce C bağlantısına sahip oldukları bildirilmişse erişilebilir. Ancak, ayrı olarak derlenmiş bir çeviri biriminde tanımlanmalıdır.

Microsoft C++ dizelerini destekler **"C"** ve **"C++"** içinde *dize sabit değeri* alan. Tüm standart içerme dosyaları **extern** "C" sözdizimini çalışma zamanı kitaplık işlevlerinin C++ programlarında kullanılacak.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C bağlantısına sahip adları bildirmek gösterilmektedir:

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

Kullanıcının kabul etmesi gereken birden fazla bağlama belirtimi, bir işleve sahiptir Bu işlevler, hem C hem de C++ bağlantısına sahip olarak bildirmek için bir hatadır. Ayrıca, bir işlev için iki bildirimi bir programda gerçekleşmesi durumunda — bir bağlama belirtimi ve görüntü olmadan — bildirimi bağlama belirtimi ile ilk olması gerekir. Bağlama belirtimi zaten işlevlerin yedekli tüm bildirimleri ilk belirtiminde belirtilen bağlantısı verilir. Örneğin:

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

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Program ve bağlantı](program-and-linkage-cpp.md)<br/>
[extern depolama sınıfı Belirleyicisi c](../c-language/extern-storage-class-specifier.md)<br/>
[C'de tanımlayıcıların davranışı](../c-language/behavior-of-identifiers.md)<br/>
[C adlarda bağlantı](../c-language/linkage.md)