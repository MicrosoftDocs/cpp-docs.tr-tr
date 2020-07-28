---
title: Derleyici hatası C2143
ms.date: 11/04/2016
f1_keywords:
- C2143
helpviewer_keywords:
- C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
ms.openlocfilehash: 310083a650f842c6c0f0912efe1ceddb66c4fd6f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214756"
---
# <a name="compiler-error-c2143"></a>Derleyici hatası C2143

sözdizimi hatası: ' token1 ', ' token2 ' öncesinde yok

Derleyici belirli bir belirteci (diğer bir deyişle, beyaz boşluk dışında bir dil öğesi) bekliyordu ve bunun yerine başka bir belirteç buldu.

Kodun sözdizimsel olarak yanlış olduğunu öğrenmek için [C++ dil başvurusunu](../../cpp/cpp-language-reference.md) denetleyin. Derleyici soruna neden olan satırı bulduktan sonra bu hatayı rapor edebilir, hatanın önündeki birkaç kod satırını kontrol edin.

C2143, farklı durumlarda gerçekleşebilir.

Bir adı ( `::` ,, ve) uygun olmayan bir operatör `->` `.` anahtar sözcüğü gelmelidir **`template`** , bu örnekte olduğu gibi olabilir:

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143
    {
    };
};
```

Varsayılan olarak, C++ `Ty::PutFuncType` bir şablon olmadığını varsayar; bu nedenle, aşağıdakiler `<` küçüktür işareti olarak yorumlanır.  Derleyiciye, `PutFuncType` açılı ayracın doğru ayrıştırabilmesi için açıkça bir şablon olduğunu söylemelisiniz. Bu hatayı düzeltmek için, **`template`** aşağıda gösterildiği gibi bağımlı türün adında anahtar sözcüğünü kullanın:

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct
    {
    };
};
```

**/Clr** kullanıldığında ve bir yönergede sözdizimi hatası olduğunda, C2143 oluşabilir **`using`** :

```cpp
// C2143a.cpp
// compile with: /clr /c
using namespace System.Reflection;   // C2143
using namespace System::Reflection;
```

CLR sözdizimi kullanarak bir kaynak kodu dosyasını derlemeye çalıştığınızda da bu durum **/clr**:

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

Bir ifadeyi izleyen ilk boşluk olmayan karakter **`if`** bir sol parantez olmalıdır. Derleyici başka bir şey çeviremez:

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

Hatanın algılanmakta olduğu satırda veya yukarıdaki satırlardan birinde bir kapanış ayracı, parantez veya noktalı virgül eksik olduğunda C2143 oluşabilir:

```cpp
// C2143d.cpp
// compile with: /c
class X {
   int member1;
   int member2   // C2143
} x;
```

Ya da bir sınıf bildiriminde geçersiz bir etiket olduğunda:

```cpp
// C2143e.cpp
class X {
   int member;
} x;

class + {};   // C2143 + is an invalid tag name
class ValidName {};   // OK
```

Bir etiket bir ifadeye iliştirilmişse. Bir etiketi kendisine yerleştirmeniz gerekiyorsa (örneğin, bileşik bir deyimin sonunda), onu null ifadesine ekleyin:

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

C++ standart kitaplığındaki bir tür için nitelenmemiş bir çağrı yapıldığında hata ortaya çıkabilir:

```cpp
// C2143g.cpp
// compile with: /EHsc /c
#include <vector>
static vector<char> bad;   // C2143
static std::vector<char> good;   // OK
```

Ya da eksik bir **`typename`** anahtar sözcük var:

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

Açık bir örnek oluşturma da tanımlamaya çalışırsanız:

```cpp
// C2143i.cpp
// compile with: /EHsc /c
// template definition
template <class T>
void PrintType(T i, T j) {}

template void PrintType(float i, float j){}   // C2143
template void PrintType(float i, float j);   // OK
```

C programında değişkenlerin işlevin başlangıcında bildirilmesi gerekir ve işlevin bildirim dışı yönergeleri yürüttüğünde bu, bildirilemez.

```C
// C2143j.c
int main()
{
    int i = 0;
    i++;
    int j = 0; // C2143
}
```
