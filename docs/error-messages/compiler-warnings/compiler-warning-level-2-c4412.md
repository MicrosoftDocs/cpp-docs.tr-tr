---
title: Derleyici Uyarısı (düzey 2) C4412
ms.date: 11/04/2016
f1_keywords:
- C4412
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
ms.openlocfilehash: 79b4ac95fbac344ff86922b84870e01c6681ed69
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684999"
---
# <a name="compiler-warning-level-2-c4412"></a>Derleyici Uyarısı (düzey 2) C4412

> '*Function*': işlev imzası '*Type*' türünü içeriyor; C++ nesnelerinin saf kod ile karma veya yerel arasında geçmesi güvenli değildir.

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez. Saf olması gereken kodunuz varsa, bunu C# ' ye bağlantı noktası ile yapmanızı öneririz.

Derleyici, bir çalışma zamanı hatasına neden olabilecek güvensiz olabilecek bir durum algıladı: **/clr: Pure** compiland öğesinden dllimport ile içeri aktarılan bir işleve çağrı yapılıyor ve işlev imzası güvenli olmayan bir tür içeriyor. Bir üye işlevi içeriyorsa veya güvenli olmayan bir tür veya güvenli olmayan bir türe yöneltme olan bir veri üyesine sahipse tür güvenli değildir.

Bu, saf ve yerel kod (ya da karma yerel ve yönetilen) arasındaki varsayılan çağırma kuraldaki fark nedeniyle güvenli değildir. `dllimport` **/Clr: saf** compiland içine bir işlev aktarırken (aracılığıyla), İmzadaki her bir türdeki bildirimlerin, işlevi dışarı aktaran compiland 'dakilerle özdeş olduğundan emin olun (örtük çağırma kurallarıyla ilgili farklılıklar hakkında daha fazla dikkatli olun).

Bir sanal üye işlevi özellikle beklenmedik sonuçlara neden olacak şekilde açıktır.  Ancak, doğru sonuçları aldığınızdan emin olmak için sanal olmayan bir işlev de test edilmelidir. Doğru sonuçları aldığınızdan emin değilseniz, bu uyarıyı yoksayabilirsiniz.

C4412 varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. varsayılan ve [dllexport, dllimport](../../cpp/dllexport-dllimport.md) Için [kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Bu uyarıyı çözmek için, türden tüm işlevleri kaldırın.

## <a name="examples"></a>Örnekler

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

Aşağıdaki örnek, iki tür bildiren bir üst bilgi dosyasıdır. `Unsafe`Üye işlevi içerdiğinden tür güvenli değil.

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

**/Clr: Pure** derlemesinde varsayılan çağırma kuralı yerel bir derlemeden farklıdır.  C4412. h dahil edildiğinde `Test` Varsayılan olarak öğesine ayarlanır `__clrcall` . Bu programı derleyip çalıştırırsanız ( **/c**kullanmayın), program bir özel durum oluşturur.

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
