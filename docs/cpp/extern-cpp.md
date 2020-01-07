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
ms.openlocfilehash: d42a32202f7fa67751ea36757c13b2c6af4953b2
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301541"
---
# <a name="extern-c"></a>extern (C++)

**Extern** anahtar sözcüğü, bir genel değişkene, işleve veya şablon bildirimine uygulanır, bu da adın *dış bağlantısına*sahip olduğunu belirtir. Bağlantı hakkında arka plan bilgileri ve genel değişkenlerin kullanılmasına neden önerilmez, bkz. [çeviri birimleri ve bağlantı](program-and-linkage-cpp.md).

**Extern** anahtar sözcüğünün, bağlama göre dört anlamı vardır:

1. const olmayan genel değişken bildiriminde **extern** , değişkenin veya işlevin başka bir çeviri biriminde tanımlandığını belirtir. **Extern** , değişkenin tanımlandığı yer hariç tüm dosyalara uygulanmalıdır.
1. bir const değişken bildiriminde, değişkenin dış bağlantı olduğunu belirtir. **Extern** , tüm dosyalardaki tüm bildirimlere uygulanmalıdır. (Global const değişkenlerinin varsayılan olarak iç bağlantısı vardır.)
1. **extern "c"** işlevin başka bir yerde tanımlandığını belirtir ve C dili çağırma kuralını kullanır. Extern "C" değiştiricisi, bir bloktaki birden çok işlev bildiriminde de uygulanabilir.
1. Şablon bildiriminde, şablonun zaten başka bir yerde örneği bulunduğunu belirtir. Bu, derleyiciye geçerli konumda yeni bir tane oluşturmak yerine diğer örnek oluşturmayı yeniden kullanacağınızı söyleyen bir iyileştirmedir. Bu **extern**kullanımı hakkında daha fazla bilgi için bkz. [Şablonlar](templates-cpp.md).

## <a name="extern-linkage-for-non-const-globals"></a>const olmayan genel öğeler için extern bağlantı

Bağlayıcı genel bir değişken bildiriminden önce **extern** olarak gördüğünde, tanımı başka bir çeviri biriminde arar. Genel kapsamdaki const olmayan değişkenlerin bildirimleri varsayılan olarak dış ' dir; yalnızca tanımı sağlamayan bildirimlere **extern** uygulayın.

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

## <a name="extern-linkage-for-const-globals"></a>const genel için extern bağlantı

Bir **const** genel değişkeninin varsayılan olarak iç bağlantısı vardır. Değişkenin dış bağlantıya sahip olmasını istiyorsanız, **extern** anahtar sözcüğünü diğer dosyalardaki diğer tüm bildirimlere ve tanımına uygulayın:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>extern constexpr bağlantısı

Visual Studio 2017 sürüm 15,3 ve önceki sürümlerde, derleyici her zaman, değişken extern olarak işaretlenmiş olsa bile bir constexpr değişkeni iç bağlantısı vermiştir. Visual Studio 2017 sürüm 15,5 ' de, yeni bir derleyici anahtarı ([/Zc: externConstexpr](../build/reference/zc-externconstexpr.md)) standartlara uygun doğru davranışı mümkün bir şekilde sunar. Sonuç olarak bu varsayılan değer olacaktır. /Permissive-seçeneği/Zc: externConstexpr 'yi etkinleştirmez.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Üst bilgi dosyası extern constexpr olarak tanımlanmış bir değişken içeriyorsa, yinelenen bildirimlerinin birleştirilmek için **__declspec (selectany)** olarak işaretlenmesi gerekir:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>extern "C" ve extern "C++" işlev bildirimleri

' C++De, bir dize ile kullanıldığında **extern** , başka bir dilin bağlantı kurallarının bildirimcler için kullanıldığını belirtir. C işlevlerine ve verilerine, yalnızca daha önce C bağlantısına sahip oldukları bildirilmişse erişilebilir. Ancak, ayrı olarak derlenmiş bir çeviri biriminde tanımlanmalıdır.

Microsoft C++ , *dize sabit değeri* alanında **"C"** ve **C++""** dizelerini destekler. Tüm standart içerme dosyaları, çalışma zamanı kitaplık işlevlerinin C++ programlarda kullanılmasına izin vermek için extern "C" sözdizimini kullanır.

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

Bir işlevde birden fazla bağlantı belirtimi varsa, bunu kabul etmelidir; işlevleri hem C hem C++ de bağlantısına sahip olarak bildirmek bir hatadır. Ayrıca, bir programda bir işlev için iki bildirim varsa — bir bağlantı belirtimi ve diğeri olmadan — bağlantı belirtimine sahip bildirim öncelikle olmalıdır. Zaten bağlantı belirtimine sahip olan işlevlerin tüm gereksiz bildirimlerine ilk bildirimde belirtilen bağlantı verilir. Örneğin:

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
[Çeviri birimleri ve bağlantı](program-and-linkage-cpp.md)<br/>
[C 'de extern depolama sınıfı tanımlayıcısı](../c-language/extern-storage-class-specifier.md)<br/>
[C 'deki tanımlayıcıların davranışı](../c-language/behavior-of-identifiers.md)<br/>
[C 'de bağlantı](../c-language/linkage.md)