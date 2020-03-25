---
title: Derleyici Uyarısı (düzey 2) C4412
ms.date: 11/04/2016
f1_keywords:
- C4412
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
ms.openlocfilehash: 601b99eec4625e9b598ece4cbb74d0039ad04bf0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161795"
---
# <a name="compiler-warning-level-2-c4412"></a>Derleyici Uyarısı (düzey 2) C4412

> '*Function*': işlev imzası '*Type*' türünü içeriyor; C++ nesneler saf kod ile karma veya yerel arasında geçiş için güvenli değildir.

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez. Saf olması gereken kodunuz varsa, bağlantı noktası oluşturmanız önerilir C#.

Derleyici, bir çalışma zamanı hatasına neden olabilecek güvensiz olabilecek bir durum algıladı: **/clr: Pure** compiland öğesinden dllimport ile içeri aktarılan bir işleve çağrı yapılıyor ve işlev imzası güvenli olmayan bir tür içeriyor. Bir üye işlevi içeriyorsa veya güvenli olmayan bir tür veya güvenli olmayan bir türe yöneltme olan bir veri üyesine sahipse tür güvenli değildir.

Bu, saf ve yerel kod (ya da karma yerel ve yönetilen) arasındaki varsayılan çağırma kuraldaki fark nedeniyle güvenli değildir. **/Clr: saf** compiland içine bir işlev (`dllimport`aracılığıyla) içeri aktarırken, İmzadaki her bir türdeki bildirimlerin, işlevi dışarı aktaran compiland 'dakilerle özdeş olduğundan emin olun (özellikle örtülü çağırma kuralları farklılıkları hakkında dikkatli olun).

Bir sanal üye işlevi özellikle beklenmedik sonuçlara neden olacak şekilde açıktır.  Ancak, doğru sonuçları aldığınızdan emin olmak için sanal olmayan bir işlev de test edilmelidir. Doğru sonuçları aldığınızdan emin değilseniz, bu uyarıyı yoksayabilirsiniz.

C4412 varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. varsayılan ve [dllexport, dllimport](../../cpp/dllexport-dllimport.md) Için [kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Bu uyarıyı çözmek için, türden tüm işlevleri kaldırın.

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

Aşağıdaki örnek, iki tür bildiren bir üst bilgi dosyasıdır. Üye işlevi olduğundan `Unsafe` türü güvenli değil.

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

Bu örnek, üst bilgi dosyasında tanımlanan türlerle işlevleri dışa aktarır.

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

**/Clr: Pure** derlemesinde varsayılan çağırma kuralı yerel bir derlemeden farklıdır.  C4412. h dahil edildiğinde `Test` varsayılan olarak `__clrcall`. Bu programı derleyip çalıştırırsanız ( **/c**kullanmayın), program bir özel durum oluşturur.

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
