---
title: Derleyici Uyarısı (Düzey 2) C4412
ms.date: 11/04/2016
f1_keywords:
- C4412
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
ms.openlocfilehash: 2c9d50fc3433321c0ca92366a512892212545754
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665523"
---
# <a name="compiler-warning-level-2-c4412"></a>Derleyici Uyarısı (Düzey 2) C4412

> '*işlevi*': işlev imzası içeren tür '*türü*'; C++ nesnelerinin saf kod arasında geçirilmesi güvenli değildir ve karma veya yerel.

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor. Saf olması gereken bir kodunuz varsa, kendisine bağlantı öneririz C#.

Derleyici bir çalışma zamanı hatasına neden, güvensiz olabilecek bir durum algılandı: gelen bir arama yapılıyor bir **/CLR: pure** dllimport ve işlev imzası içeri aktarılan işleve derlenecek güvenli olmayan bir tür içeriyor . Üye işlevi içeriyor ya da güvenli olmayan bir türü veya bir yöneltme güvenli olmayan bir tür için bir veri üyesine sahip bir tür güvenli değildir.

Bu fark için varsayılan çağırma kuralları saf ve yerel kod arasında nedeniyle güvenli değildir (veya yerel ve yönetilen karışık). İçeri aktarılırken (aracılığıyla `dllimport`) bir işleve bir **/CLR: pure** derlenecek, her tür imzası bildirimleri (özellikle hakkında dikkatli işlevi dışarı aktarır derlenecek ortamınızdakilerle olduğundan emin olun farkları örtük çağırma kuralları).

Bir sanal üye işlevi, beklenmedik sonuçlar özellikle yatkındır.  Ancak, sanal olmayan bir işlev doğru sonuçları aldığınızdan emin olmak için test edilmelidir. Doğru sonuçları elde edeceğinizi eminseniz bu uyarıyı yoksayabilirsiniz.

Varsayılan olarak C4412 kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) ve [dllexport, dllimport](../../cpp/dllexport-dllimport.md) daha fazla bilgi için.

Bu uyarıyı çözmek için tüm işlevleri türünden kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4412 oluşturur.

```cpp
// C4412.cpp
// compile with: /c /W2 /clr:pure
#pragma warning (default : 4412)

struct Unsafe {
   virtual void __cdecl Test();
};

struct Safe {
   int i;
};

__declspec(dllimport) Unsafe * __cdecl func();
__declspec(dllimport) Safe * __cdecl func2();

int main() {
   Unsafe *pUnsafe = func();   // C4412
   // pUnsafe->Test();

   Safe *pSafe = func2();   // OK
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, iki tür bildiren bir üstbilgi dosyasıdır. `Unsafe` Türüdür güvenli olmayan bir üye işlev olduğundan.

```cpp
// C4412.h
struct Unsafe {
   // will be __clrcall if #included in pure compilation
   // defaults to __cdecl in native or mixed mode compilation
   virtual void Test(int * pi);

   // try the following line instead
   // virtual void __cdecl Test(int * pi);
};

struct Safe {
   int i;
};
```

## <a name="example"></a>Örnek

Bu örnek üstbilgi dosyasında tanımlanan türleri ile işlevleri dışa aktarır.

```cpp
// C4412_2.cpp
// compile with: /LD
#include "C4412.h"

void Unsafe::Test(int * pi) {
   *pi++;
}

__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }
```

## <a name="example"></a>Örnek

İçin varsayılan çağırma kuralını bir **/CLR: pure** derleme, yerel bir derlemeden farklıdır.  C4412.h eklendiğinde `Test` varsayılan olarak `__clrcall`. Derleme ve bu programı çalıştır (kullanmayın **/c**), programın bir özel durum oluşturur.

Aşağıdaki örnek C4412 oluşturur.

```cpp
// C4412_3.cpp
// compile with: /W2 /clr:pure /c /link C4412_2.lib
#pragma warning (default : 4412)
#include "C4412.h"

__declspec(dllimport) Unsafe * __cdecl func();
__declspec(dllimport) Safe * __cdecl func2();

int main() {
   int n = 7;
   Unsafe *pUnsafe = func();   // C4412
   pUnsafe->Test(&n);

   Safe *pSafe = func2();   // OK
}
```