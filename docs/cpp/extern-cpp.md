---
title: extern (C++) | Microsoft Docs
ms.custom: ''
ms.date: 04/12/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- extern
- extern_CPP
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00b9f94d02443163f45b83d64702fe49622597cd
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238768"
---
# <a name="extern-c"></a>extern (C++)

**Extern** anahtar sözcüğü o şey adı olduğunu belirtmek için bir genel değişkeni, işlev veya şablon bildirimine uygulanan *dış bağlantı*. Bağlantı ve genel değişkenler kullanılmasına neden önerilmez hakkında bilgi için bkz: [Program ve bağlantı](program-and-linkage-cpp.md).

**Extern** anahtar sözcüğü bağlam bağlı olarak dört anlamları vardır:

1. const olmayan genel değişken bildiriminde, **extern** değişken veya işlev, başka bir çeviri biriminde tanımlanan belirtir. **Extern** değişkeni tanımlandığı tüm dosyaları dışındaki uygulanmış olması gerekir.
1. const Değişken bildiriminde değişkeni dış bağlantı olduğunu belirtir. **Extern** tüm dosyalarda tüm bildirimler için uygulanması gerekir. (Genel const değişkenler, iç bağlantı varsayılan olarak vardır.)
1. **extern "C"** işlevi başka bir yerde tanımlanır ve C dili çağırma kullanır belirtir. Extern "C" değiştiricisi ayrıca bir blok içinde birden çok işlev bildirimleri için uygulanabilir.
1. bir şablon bildirimindeki şablon zaten başka bir yerde örneği oluşturulmuş olduğunu belirtir. Derleyici, geçerli konumundaki yeni bir tane oluşturmak yerine diğer oluşturmada yeniden kullanabileceğiniz bildiren bir en iyi duruma getirme budur. Bu kullanımı hakkında daha fazla bilgi için **extern**, bkz: [şablonları](templates-cpp.md).

## <a name="extern-linkage-for-non-const-globals"></a>const olmayan globals dış bağlantı

Bağlayıcı gördüğünde **extern** genel bir değişken bildirimi önce başka bir çeviri birim tanımında arar. Genel kapsamlı const olmayan değişkenlerin bildirimleri varsayılan olarak dış; yalnızca geçerli **extern** tanımı sağlamıyorsa bildirimleri için.

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

## <a name="extern-linkage-for-const-globals"></a>const globals dış bağlantı

A **const** genel değişkeni varsayılan olarak iç bağlantı vardır. Dış bağlantı sağlamak için değişkenin istiyorsanız, uygulama **extern** anahtar sözcüğü tüm diğer dosyaların bildirimlerinde konusunda da tanımı:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>Extern constexpr bağlantı

Değişkeni extern bile işaretlendi, Visual Studio 2017 içinde sürüm 15.3 ve önceki sürümlerde, derleyici constexpr değişken iç bağlantı her zaman verdi. Visual Studio 2017 sürüm 15,5, yeni derleyici anahtar içinde ([/Zc:externConstexpr](../build/reference/zc-externconstexpr.md)) doğru standartları uyumsuz davranışı etkinleştirir. Sonuç olarak bu varsayılan olur.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Üstbilgi dosyası değişken bildirilen extern constexpr içeriyorsa, işaretlenmesi gerekiyor **__declspec(selectany)** birlikte, yinelenen bildirimler doğru olması için:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>extern "C" ve extern "C++" işlev bildirimleri

 Bir dizeyle kullanıldığında C++ ' ta **extern** başka bir dilde bağlantı kuralları declarator(s) için kullanıldığını belirtir. C işlevlerine ve verilerine, yalnızca daha önce C bağlantısına sahip oldukları bildirilmişse erişilebilir. Ancak, ayrı olarak derlenmiş bir çeviri biriminde tanımlanmalıdır.

 Microsoft C++ dizeleri destekler **"C"** ve **"C++"** içinde *değişmez dize değeri* alan. Tüm standart eklenmesi dosyaları kullan **extern** C++ programlarında kullanılacak çalışma zamanı kitaplığı işlevleri izin vermek için "C" sözdizimi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C bağlantı adlarında bildirme gösterilmektedir:

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

 Kullanıcının kabul etmesi gerekir birden fazla bağlantı belirtimi, bir işlev varsa, C ve C++ bağlantı sahip olarak işlevleri bildirmek için bir hata var. Ayrıca, bir işlev için iki bildirimleri bir programda gerçekleşmesi durumunda — bir bağlantı belirtimi ve biri olmadan biriyle — bağlantı belirtimi bildirimiyle ilk olması gerekir. Tüm gereksiz bildirimleri bağlantı belirtimi zaten işlevlerin ilk bildiriminde belirtilen bağlantı verilir. Örneğin:

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

## <a name="see-also"></a>Ayrıca Bkz.

- [Anahtar Sözcükler](../cpp/keywords-cpp.md)
- [Program ve bağlantı](program-and-linkage-cpp.md)
- [extern depolama sınıfı tanımlayıcısı c](../c-language/extern-storage-class-specifier.md) 
- [Tanımlayıcıları C'de davranışı](../c-language/behavior-of-identifiers.md) 
- [C'de bağlantı](../c-language/linkage.md)