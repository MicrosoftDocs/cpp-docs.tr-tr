---
title: Derleyici Hatası C2143 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2143
dev_langs:
- C++
helpviewer_keywords:
- C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c729ecbdea13c36cf5df71efa16d12853fc4433
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890500"
---
# <a name="compiler-error-c2143"></a>Derleyici Hatası C2143

sözdizimi hatası: 'token2' önce ' token1' eksik

Derleyici, belirli bir belirteç (diğer bir deyişle, boşluk dışında dil öğesi) beklenen ve bunun yerine farklı bir belirteç bulundu.

Denetleme [C++ dil başvurusu](../../cpp/cpp-language-reference.md) kod sözdizimsel olarak yanlış olduğu belirlemek için. Soruna neden olan satır karşılaştıktan sonra derleyici bu hatayı rapor edebilir çünkü hata önünde birkaç kod satırlarını denetleyin.

C2143 farklı durumlarda ortaya çıkabilir.

Bir ad belirtebilme operatörün olduğunda oluşabilir (`::`, `->`, ve `.`) anahtar sözcüğüyle gelmelidir `template`, bu örnekte olduğu gibi:

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143
    {
    };
};

```

Varsayılan olarak, C++ olduğunu varsayar `Ty::PutFuncType` olmayan bir şablon; bu nedenle, aşağıdaki `<` daha az yorumlanır-işareti.  Derleyici açıkça, bildirmeniz gerekir `PutFuncType` böylece doğru açılı ayraç ayrıştırmak bir şablondur. Bu hatayı düzeltmek için `template` anahtar sözcüğü, burada gösterildiği gibi bağımlı tür adı:

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct
    {
    };
};

```

C2143 gerçekleşebilir, **/CLR** kullanılır ve `using` yönergesi sözdizimi hatası var:

```cpp
// C2143a.cpp
// compile with: /clr /c
using namespace System.Reflection;   // C2143
using namespace System::Reflection;
```

Ayrıca kullanmadan CLR söz dizimini kullanarak bir kaynak kodu dosyasını derlemek çalışırken de oluşabilir **/CLR**:

```cpp
// C2143b.cpp
ref struct A {   // C2143 error compile with /clr
   void Test() {}
};

int main() {
   A a;
   a.Test();
}
```

İzleyen ilk boşluk olmayan karakter bir `if` deyimi bir sol ayraç olması gerekir. Derleyici, başka bir şey çeviremez:

```cpp
// C2143c.cpp
int main() {
   int j = 0;

   // OK
   if (j < 25)
      ;

   if (j < 25)   // C2143
}
```

C2143, hatanın algılandığı yere satırında bir kapanış ayracı, parantez veya noktalı virgül eksik oluşur veya satırlardan birini yukarıda yalnızca:

```cpp
// C2143d.cpp
// compile with: /c
class X {
   int member1;
   int member2   // C2143
} x;
```

Veya bir sınıf bildiriminde geçersiz bir etiketi olduğunda:

```cpp
// C2143e.cpp
class X {
   int member;
} x;

class + {};   // C2143 + is an invalid tag name
class ValidName {};   // OK
```

Veya bir etiket ne zaman bir deyime bağlı değil. Örneğin, tek başına bir etiket yerleştirmeniz gerekir, bileşik bir deyimin sonunda, için boş bir deyimi ekleyin:

```cpp
// C2143f.cpp
// compile with: /c
void func1() {
   // OK
   end1:
      ;

   end2:   // C2143
}
```

C++ Standart Kitaplığı'nda bir tür nitelenmemiş bir çağrı yapıldığında hata oluşabilir:

```cpp
// C2143g.cpp
// compile with: /EHsc /c
#include <vector>
static vector<char> bad;   // C2143
static std::vector<char> good;   // OK
```

Veya eksik bir `typename` anahtar sözcüğü:

```cpp
// C2143h.cpp
template <typename T>
struct X {
   struct Y {
      int i;
   };
   Y memFunc();
};
template <typename T>
X<T>::Y X<T>::memFunc() {   // C2143
// try the following line instead
// typename X<T>::Y X<T>::memFunc() {
   return Y();
}
```

Veya bir açık örnek oluşturma tanımlamak çalışırsanız:

```cpp
// C2143i.cpp
// compile with: /EHsc /c
// template definition
template <class T>
void PrintType(T i, T j) {}

template void PrintType(float i, float j){}   // C2143
template void PrintType(float i, float j);   // OK
```

C programında, işlevin başında değişkenleri bildirilmelidir ve işlev bildirimi olmayan yönergeleri yürütüldükten sonra bunlar bildirilemez.

```C
// C2143j.c
int main()
{
    int i = 0;
    i++;
    int j = 0; // C2143
}
```
