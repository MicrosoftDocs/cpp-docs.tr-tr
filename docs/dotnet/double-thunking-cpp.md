---
title: Çift Dönüştürme (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- double thunks
- interop [C++], double thunking
- mixed assemblies [C++], double thunking
- /clr compiler option [C++], double thunking
- interoperability [C++], double thunking
ms.assetid: a85090b2-dc3c-498a-b40c-340db229dd6f
ms.openlocfilehash: 6b2d3b4415b81dc5a9b7d0e36c154d9ee74b98ee
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221490"
---
# <a name="double-thunking-c"></a>Çift Dönüştürme (C++)

Çift thunking, yönetilen bir bağlamda bir işlev çağrısı Visual C++ yönetilen bir işlevi çağırdığında ve program yürütmenin yönetilen işlevi çağırmak için işlevin yerel giriş noktasını çağırdığı durumlarda karşılaşabileceğiniz performans kaybını ifade eder. Bu konu, Çift dönüştürmenin nerede oluştuğunu ve performansı artırmak için bunu nasıl önleyebileceğiniz anlatılmaktadır.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **/clr**ile derlerken, yönetilen bir işlevin tanımı derleyicinin yönetilen bir giriş noktası ve yerel giriş noktası oluşturmasına neden olur. Bu, yönetilen işlevin yerel ve yönetilen çağrı sitelerinden çağrılmasına izin verir. Ancak, yerel bir giriş noktası varsa, işleve yapılan tüm çağrılar için giriş noktası olabilir. Çağıran bir işlev yönetiliyorsa, yerel giriş noktası daha sonra yönetilen giriş noktasını çağırır. Aslında, işlevi çağırmak için iki çağrı gerekir (Bu nedenle, Çift thunking). Örneğin, sanal işlevler her zaman bir yerel giriş noktası aracılığıyla çağırılır.

Tek bir çözüm, derleyicinin yönetilen bir işlev için yerel bir giriş noktası üretmediğini söylemek, işlevin yalnızca yönetilen bağlamdan [__clrcall](../cpp/clrcall.md) çağırma kuralı kullanılarak çağrılacaktır.

Benzer şekilde, yönetilen bir işlevi ([dllexport, dllimport](../cpp/dllexport-dllimport.md)) dışa aktardığınızda, yerel bir giriş noktası oluşturulur ve bu işlevi çağıran ve çağıran tüm işlevleri yerel giriş noktası aracılığıyla çağırır. Bu durumda çift dönüştürmeyi önlemek için, yerel dışarı aktarma/içe aktarma semantiğini kullanmayın; meta verilere `#using` (bkz. [#using yönergesine](../preprocessor/hash-using-directive-cpp.md)) başvurun.

Derleyici, gereksiz çift dönüştürmeyi azaltmak için güncelleştirilmiştir. Örneğin, İmzada yönetilen bir tür (dönüş türü dahil) olan herhangi bir işlev, örtük olarak olarak işaretlenir `__clrcall` .

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek çift thunking gösterir. Yerel olarak derlendiğinde ( **/clr**olmadan), içindeki sanal işlevine yapılan çağrı, `main` `T` kopya oluşturucusuna bir çağrı ve yıkıcıya bir çağrı oluşturur. Sanal işlev **/clr** ve ile bildirildiğinde benzer davranış elde edilir `__clrcall` . Bununla birlikte, yalnızca **/clr**ile derlendiğinde, işlev çağrısı kopya oluşturucusuna bir çağrı oluşturur, ancak yerel-yönetilen dönüştürücü nedeniyle kopya oluşturucusuna başka bir çağrı yapılır.

### <a name="code"></a>Kod

```cpp
// double_thunking.cpp
// compile with: /clr
#include <stdio.h>
struct T {
   T() {
      puts(__FUNCSIG__);
   }

   T(const T&) {
      puts(__FUNCSIG__);
   }

   ~T() {
      puts(__FUNCSIG__);
   }

   T& operator=(const T&) {
      puts(__FUNCSIG__);
      return *this;
   }
};

struct S {
   virtual void /* __clrcall */ f(T t) {};
} s;

int main() {
   S* pS = &s;
   T t;

   printf("calling struct S\n");
   pS->f(t);
   printf("after calling struct S\n");
}
```

### <a name="sample-output"></a>Örnek Çıktı

```
__thiscall T::T(void)
calling struct S
__thiscall T::T(const struct T &)
__thiscall T::T(const struct T &)
__thiscall T::~T(void)
__thiscall T::~T(void)
after calling struct S
__thiscall T::~T(void)
```

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Önceki örnek, Çift dönüştürmenin varlığını göstermiştir. Bu örnek, etkisini gösterir. **`for`** Döngü sanal işlevi çağırır ve program, yürütme süresini bildirir. Program **/clr**ile derlendiğinde en yavaş zaman raporlanır. En hızlı zaman, **/clr** olmadan derlerken veya sanal işlev ile bildirilmişse raporlanır `__clrcall` .

### <a name="code"></a>Kod

```cpp
// double_thunking_2.cpp
// compile with: /clr
#include <time.h>
#include <stdio.h>

#pragma unmanaged
struct T {
   T() {}
   T(const T&) {}
   ~T() {}
   T& operator=(const T&) { return *this; }
};

struct S {
   virtual void /* __clrcall */ f(T t) {};
} s;

int main() {
   S* pS = &s;
   T t;
   clock_t start, finish;
   double  duration;
   start = clock();

   for ( int i = 0 ; i < 1000000 ; i++ )
      pS->f(t);

   finish = clock();
   duration = (double)(finish - start) / (CLOCKS_PER_SEC);
   printf( "%2.1f seconds\n", duration );
   printf("after calling struct S\n");
}
```

### <a name="sample-output"></a>Örnek Çıktı

```
4.2 seconds
after calling struct S
```

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
