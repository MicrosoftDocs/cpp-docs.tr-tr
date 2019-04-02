---
title: soyut (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- abstract
- abstract_cpp
helpviewer_keywords:
- abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
ms.openlocfilehash: 3f6196d50c2a0cca43ffd6f3b2becf3afc0649bd
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787735"
---
# <a name="abstract--ccli-and-ccx"></a>soyut (C + +/ CLI ve C + +/ CX)

**Soyut** anahtar sözcüğü ya da bildirir:

- Bir tür temel tür olarak kullanılabilir, ancak tür örneği oluşturulamıyor.

- Tür üye işlevi, yalnızca türetilmiş bir tür içinde tanımlanabilir.

## <a name="all-platforms"></a>Tüm Platformlar

### <a name="syntax"></a>Sözdizimi

*sınıf-bildirimi* *sınıf tanımlayıcısı* **soyut {}**

**Sanal** *dönüş türü* *üye işlev tanımlayıcı* **soyut ();**

### <a name="remarks"></a>Açıklamalar

İlk örnek söz dizimi bir sınıf, soyut olarak bildirir. *Sınıf-bildirimi* bileşeni, bir ya da bir yerel C++ bildirimi olabilir (**sınıfı** veya **yapı**), ya da bir C++ uzantı bildiriminde (**başvurusınıfı** veya **ref struct**) varsa `/ZW` veya `/clr` derleyici seçeneği belirtildi.

İkinci örnek söz dizimi, bir sanal üye işlevi soyut bildirir. Bir işlev soyut aynıdır saf sanal işlevi bildirmek bildirme. Bildirme bir üye işlev soyut da kapsayan sınıfa soyut bildirilmesine neden olur.

**Soyut** anahtar sözcüğü, yerel ve platforma özgü kodu desteklenir; diğer bir deyişle, onu içeren veya içermeyen derlenebilir `/ZW` veya `/clr` derleyici seçeneği.

Bir türü ile soyut ise derleme zamanında algılayabilir `__is_abstract(type)` türü niteliğine. Daha fazla bilgi için [tür özellikleri için derleyici desteği](compiler-support-for-type-traits-cpp-component-extensions.md).

**Soyut** anahtar sözcüğü, bir bağlama duyarlı geçersiz kılma tanımlayıcısı. Bağlama duyarlı anahtar sözcükler hakkında daha fazla bilgi için bkz. [Context-Sensitive Keywords](context-sensitive-keywords-cpp-component-extensions.md). Geçersiz kılma tanımlayıcıları hakkında daha fazla bilgi için bkz. [nasıl yapılır: Yerel derlemelerde geçersiz kılma tanımlayıcılarını bildirme](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Daha fazla bilgi için [başvuru sınıfları ve yapıları](../cppcx/ref-classes-and-structs-c-cx.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği bir hata oluşturur çünkü sınıfı `X` işaretlenmiş **soyut**.

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

Aşağıdaki kod örneği, bir hata oluşturur, çünkü işaretlenmiş bir yerel sınıf örneğini oluşturduğunda **soyut**. Bu hata ile veya olmadan oluşur `/clr` derleyici seçeneği.

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

Aşağıdaki kod örneği bir hata oluşturur çünkü işlevi `f` bir tanım içerir, ancak işaretlenen **soyut**. Örnekteki son deyim, soyut bir sanal işlev bildirme saf sanal işlevi bildirmek için eşdeğer olduğunu gösterir.

```cpp
// abstract_keyword_3.cpp
// compile with: /clr
ref class X {
public:
   virtual void f() abstract {}   // C3634
   virtual void g() = 0 {}   // C3634
};
```

## <a name="see-also"></a>Ayrıca Bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)
