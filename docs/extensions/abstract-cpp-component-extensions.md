---
description: 'Daha fazla bilgi edinin: abstract (C++/CLı ve C++/CX)'
title: abstract (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- abstract
- abstract_cpp
helpviewer_keywords:
- abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
ms.openlocfilehash: e40d0d0c03bbf97b684d9e011f4bf614f6a44332
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177126"
---
# <a name="abstract--ccli-and-ccx"></a>abstract (C++/CLI ve C++/CX)

**Abstract** anahtar sözcüğü şu şekilde bildirir:

- Bir tür temel tür olarak kullanılabilir, ancak türün kendisi başlatılamaz.

- Bir tür üye işlevi yalnızca türetilmiş bir tür içinde tanımlanabilir.

## <a name="all-platforms"></a>Tüm Platformlar

### <a name="syntax"></a>Syntax

*sınıf bildirimi* *sınıfı tanımlayıcı* **Özet {}**

**`virtual`***Return-Type* *üye-Function-Identifier* **() abstract;**

### <a name="remarks"></a>Açıklamalar

İlk örnek sözdizimi Özet olacak bir sınıf bildirir. Or derleyici seçeneği belirtilmişse, *sınıf bildirimi* bileşeni yerel bir c++ bildirimi (**`class` * * * * veya **`struct`** ) ya da bir c++ uzantı bildirimi (** ref class * * veya **ref struct**) olabilir `/ZW` `/clr` .

İkinci örnek sözdizimi, bir sanal üye işlevini soyut olacak şekilde bildirir. Bir işlev soyut bildirmek, onu saf bir sanal işlevi bildirerek de aynıdır. Bir üye işlevi soyut olarak bildirmek kapsayan sınıfın soyut olarak bildirilmesine neden olur.

**Abstract** anahtar sözcüğü, yerel ve platforma özgü kodda desteklenir; diğer bir deyişle, `/ZW` veya derleyici seçeneği olmadan veya ile derlenebilir `/clr` .

Tür nitelik türünde soyut ise, derleme zamanında tespit edebilirsiniz `__is_abstract(type)` . Daha fazla bilgi için bkz. [tür nitelikleri Için derleyici desteği](compiler-support-for-type-traits-cpp-component-extensions.md).

**Abstract** anahtar sözcüğü, bağlama duyarlı bir geçersiz kılma belirticisidir. Bağlama duyarlı anahtar sözcükler hakkında daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](context-sensitive-keywords-cpp-component-extensions.md). Geçersiz kılma belirticileri hakkında daha fazla bilgi için bkz. [nasıl yapılır: yerel derlemelerde geçersiz kılma belirticileri bildirme](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Daha fazla bilgi için bkz. [başvuru sınıfları ve yapıları](../cppcx/ref-classes-and-structs-c-cx.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, sınıf `X` **soyut** olarak işaretlendiğinden bir hata oluşturur.

```cpp
// abstract_keyword.cpp
// compile with: /clr
ref class X abstract {
public:
   virtual void f() {}
};

int main() {
   X ^ MyX = gcnew X;   // C3622
}
```

Aşağıdaki kod örneği, **soyut** olarak işaretlenmiş bir yerel sınıf örneklediği için bir hata oluşturur. Derleyici seçeneği olmadan veya bu hata oluşur `/clr` .

```cpp
// abstract_keyword_2.cpp
class X abstract {
public:
   virtual void f() {}
};

int main() {
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'
                    // cannot be instantiated. See declaration of 'X'}
```

Aşağıdaki kod örneği bir hata oluşturur çünkü işlev `f` bir tanım içeriyor ancak **soyut** olarak işaretlenmiş. Örnekteki final ifadesinde, bir soyut sanal işlevi bildiren bir saf sanal işlevi bildirme ile eşdeğer olduğu gösterilmektedir.

```cpp
// abstract_keyword_3.cpp
// compile with: /clr
ref class X {
public:
   virtual void f() abstract {}   // C3634
   virtual void g() = 0 {}   // C3634
};
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
