---
title: :::no-loc(extern):::C++
description: 'C++ dili :::no-loc(extern)::: anahtar sözcüğüne kılavuz.'
ms.date: 01/28/2020
f1_keywords:
- ':::no-loc(extern):::'
- :::no-loc(extern):::_CPP
helpviewer_keywords:
- ':::no-loc(extern)::: keyword [C++], linkage to non-C++ functions'
- declarations, :::no-loc(extern):::al
- ':::no-loc(extern):::al linkage, :::no-loc(extern)::: modifier'
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
no-loc:
- ':::no-loc(extern):::'
- ':::no-loc(const):::'
- ':::no-loc(constexpr):::'
- ':::no-loc(permissive):::'
ms.openlocfilehash: 510352f9e99e513f4a426f6ef89be4474085d97c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227510"
---
# <a name="no-locextern-c"></a>:::no-loc(extern):::C++

**`:::no-loc(extern):::`** Anahtar sözcüğü bir genel değişkene, işleve veya şablon bildirimine uygulanabilir. Simgenin * :::no-loc(extern)::: Al bağlantısına*sahip olduğunu belirtir. Bağlantı hakkında arka plan bilgileri ve genel değişkenlerin kullanılmasına neden önerilmez, bkz. [çeviri birimleri ve bağlantı](program-and-linkage-cpp.md).

**`:::no-loc(extern):::`** Anahtar sözcüğünün, bağlama göre dört anlamı vardır:

- Genel olmayan bir **`:::no-loc(const):::`** değişken bildiriminde, **`:::no-loc(extern):::`** değişkenin veya işlevin başka bir çeviri biriminde tanımlandığını belirtir. **`:::no-loc(extern):::`** Değişkenin tanımlandığı yer hariç tüm dosyalara uygulanması gerekir.

- **`:::no-loc(const):::`** Değişken bildiriminde, değişkenin al bağlantısına sahip olduğunu belirtir :::no-loc(extern)::: . **`:::no-loc(extern):::`** Tüm dosyalardaki tüm bildirimlere uygulanması gerekir. (Genel **`:::no-loc(const):::`** değişkenlerin varsayılan olarak iç bağlantısı vardır.)

- ** :::no-loc(extern)::: "C"** işlevin başka bir yerde tanımlandığını belirtir ve C dili çağırma kuralını kullanır. :::no-loc(extern):::"C" değiştiricisi, bir bloktaki birden çok işlev bildiriminde de uygulanabilir.

- Şablon bildiriminde, **`:::no-loc(extern):::`** şablonun zaten başka bir yerde örneği bulunduğunu belirtir. **`:::no-loc(extern):::`** derleyiciye, geçerli konumda yeni bir tane oluşturmak yerine, diğer örnek oluşturmayı yeniden kullanabilmeyeceğini söyler. Bu kullanımı hakkında daha fazla bilgi için **`:::no-loc(extern):::`** bkz. [açık örnek oluşturma](explicit-instantiation.md).

## <a name="no-locextern-linkage-for-non-no-locconst-globals"></a>:::no-loc(extern):::Genel olmayan için bağlantı :::no-loc(const):::

Bağlayıcı **`:::no-loc(extern):::`** genel bir değişken bildiriminden önce gördüğünde, tanımı başka bir çeviri biriminde arar. **`:::no-loc(const):::`** Genel kapsamdaki değişkenlerin bildirimleri :::no-loc(extern)::: Varsayılan olarak alınır. Yalnızca **`:::no-loc(extern):::`** tanımı sağlamayan bildirimlere uygulanır.

```cpp
//fileA.cpp
int i = 42; // declaration and definition

//fileB.cpp
:::no-loc(extern)::: int i;  // declaration only. same as i in FileA

//fileC.cpp
:::no-loc(extern)::: int i;  // declaration only. same as i in FileA

//fileD.cpp
int i = 43; // LNK2005! 'i' already has a definition.
:::no-loc(extern)::: int i = 43; // same error (:::no-loc(extern)::: is ignored on definitions)
```

## <a name="no-locextern-linkage-for-no-locconst-globals"></a>:::no-loc(extern):::Genel için bağlantı :::no-loc(const):::

**`:::no-loc(const):::`** Genel bir değişken varsayılan olarak iç bağlantıya sahiptir. Değişkenin al bağlantısına sahip olmasını istiyorsanız :::no-loc(extern)::: , **`:::no-loc(extern):::`** anahtar sözcüğünü tanımına ve diğer dosyalardaki diğer tüm bildirimlere uygulayın:

```cpp
//fileA.cpp
:::no-loc(extern)::: :::no-loc(const)::: int i = 42; // :::no-loc(extern)::: :::no-loc(const)::: definition

//fileB.cpp
:::no-loc(extern)::: :::no-loc(const)::: int i;  // declaration only. same as i in FileA
```

## <a name="no-locextern-no-locconstexpr-linkage"></a>:::no-loc(extern)::::::no-loc(constexpr):::bağlantı

Visual Studio 2017 sürüm 15,3 ve önceki sürümlerde, derleyici, **`:::no-loc(constexpr):::`** değişken işaretlenmiş olsa bile her zaman bir iç bağlantı vermiştir **`:::no-loc(extern):::`** . Visual Studio 2017 sürüm 15,5 ve sonraki sürümlerde, [/Zc: :::no-loc(extern)::: constexpr](../build/reference/zc-:::no-loc(extern)::::::no-loc(constexpr):::.md) derleyici anahtarı, standartlara uygun doğru davranışa izin vermez. Sonuç olarak seçenek varsayılan olarak olur. [/:::no-loc(permissive):::-](../build/reference/:::no-loc(permissive):::-standards-conformance.md)Seçeneği **/Zc: :::no-loc(extern)::: constexpr**'yi etkinleştirmez.

```cpp
:::no-loc(extern)::: :::no-loc(constexpr)::: int x = 10; //error LNK2005: "int :::no-loc(const)::: x" already defined
```

Bir üst bilgi dosyası, tanımlanmış bir değişken içeriyorsa **`:::no-loc(extern):::`** **`:::no-loc(constexpr):::`** , `__declspec(selectany)` yinelenen bildirimlerinin birleştirilmek üzere işaretlenmesi gerekir:

```cpp
:::no-loc(extern)::: :::no-loc(constexpr)::: __declspec(selectany) int x = 10;
```

## <a name="no-locextern-c-and-no-locextern-c-function-declarations"></a>:::no-loc(extern):::"C" ve :::no-loc(extern)::: "C++" işlev bildirimleri

C++ ' da, bir dize ile kullanıldığında, **`:::no-loc(extern):::`** başka bir dilin bağlantı kurallarının, bildirimcler için kullanıldığını belirtir. C işlevlerine ve verilerine, yalnızca daha önce C bağlantısı varmış gibi bildirilirse erişilebilir. Ancak, ayrı olarak derlenmiş bir çeviri biriminde tanımlanmalıdır.

Microsoft C++, *dize sabit değeri* alanında **"C"** ve **"C++"** dizelerini destekler. Tüm standart içerme dosyaları, C++ programlarında çalışma zamanı kitaplık işlevlerinin kullanılmasına izin vermek için ** :::no-loc(extern)::: "C"** sözdizimini kullanır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C bağlantısı olan adların nasıl bildirilemeyeceğini göstermektedir:

```cpp
// Declare printf with C linkage.
:::no-loc(extern)::: "C" int printf(:::no-loc(const)::: char *fmt, ...);

//  Cause everything in the specified
//  header files to have C linkage.
:::no-loc(extern)::: "C" {
    // add your #include statements here
#include <stdio.h>
}

//  Declare the two functions ShowChar
//  and GetChar with C linkage.
:::no-loc(extern)::: "C" {
    char ShowChar(char ch);
    char GetChar(void);
}

//  Define the two functions
//  ShowChar and GetChar with C linkage.
:::no-loc(extern)::: "C" char ShowChar(char ch) {
    putchar(ch);
    return ch;
}

:::no-loc(extern)::: "C" char GetChar(void) {
    char ch;
    ch = getchar();
    return ch;
}

// Declare a global variable, errno, with C linkage.
:::no-loc(extern)::: "C" int errno;
```

Bir işlevde birden fazla bağlantı belirtimi varsa, bunları kabul etmelidir. İşlevleri hem C hem de C++ bağlantısına sahip olacak şekilde bildirmek bir hatadır. Ayrıca, bir programda bir işlev için iki bildirim varsa — bir bağlantı belirtimi ve diğeri olmadan — bağlantı belirtimine sahip bildirim öncelikle olmalıdır. Zaten bağlantı belirtimine sahip olan işlevlerin tüm gereksiz bildirimlerine ilk bildirimde belirtilen bağlantı verilir. Örnek:

```cpp
:::no-loc(extern)::: "C" int CFunc1();
...
int CFunc1();            // Redeclaration is benign; C linkage is
                         //  retained.

int CFunc2();
...
:::no-loc(extern)::: "C" int CFunc2(); // Error: not the first declaration of
                         //  CFunc2;  cannot contain linkage
                         //  specifier.
```

## <a name="see-also"></a>Ayrıca bkz.

[Lerimi](../cpp/keywords-cpp.md)\
[Çeviri birimleri ve bağlantı](program-and-linkage-cpp.md)\
[:::no-loc(extern):::C 'de depolama sınıfı Belirleyicisi](../c-language/:::no-loc(extern):::-storage-class-specifier.md)\
[C 'deki tanımlayıcıların davranışı](../c-language/behavior-of-identifiers.md)\
[C 'de bağlantı](../c-language/linkage.md)
