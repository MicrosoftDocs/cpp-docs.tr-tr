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
ms.openlocfilehash: 984a20d701b159820a94483fe9d3743f015b71f6
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741966"
---
# <a name="double-thunking-c"></a>Çift Dönüştürme (C++)

Çift dönüştürme için Visual C++ yönetilen işlevi ve program yürütmenin bir yönetilen bağlam çağrıları işlev çağrısında yönetilen işlevi çağırmak için işlev yerel giriş noktası çağırdığında karşılaşabileceğiniz performans kaybı ifade eder. Bu konu, çift dönüştürme nerede oluştuğunu ve performansı geliştirmek için önlemek nasıl açıklar.

## <a name="remarks"></a>Açıklamalar

İle derlerken varsayılan olarak **/CLR**, yönetilen bir işlev tanımı bir yönetilen giriş noktasını ve yerel giriş noktası oluşturmak derleyicinin neden olur. Bu, yerel ve yönetilen çağrı sitelerinden çağrılacak yönetilen işlevi sağlar. Ancak, yerel giriş noktası mevcut olduğunda, bu işleve yapılan tüm çağrılar için giriş noktası olabilir. Bir arama işlevi yönetiliyorsa, yerel giriş noktası sonra yönetilen giriş noktasını çağırır. Aslında, işlevin çalıştırılabilmesi için iki çağrıları gereklidir (Bu nedenle, dönüştürme çift). Örneğin, sanal işlevleri her zaman yerel giriş noktası aracılığıyla çağrılır.

Bir çözüm olan işlevi yalnızca bir yönetilen bağlamında kullanarak çağrılır, yönetilen bir işlev için bir yerel giriş noktası değil derleyici bildirmek için [__clrcall](../cpp/clrcall.md) çağırma kuralı.

Benzer şekilde, dışarı aktarırsanız ([dllexport, dllimport](../cpp/dllexport-dllimport.md)) yönetilen bir işlev bir yerel giriş noktasını oluşturulur ve içeri aktarır ve bu işlevi çağıran bir işlev yerel giriş noktası çağırır. Bu durumda çift dönüştürme önlemek için yerel dışarı/içeri aktarma semantiği kullanmayın; yalnızca meta veriler aracılığıyla başvuru `#using` (bkz [#using yönergesi](../preprocessor/hash-using-directive-cpp.md)).

Derleyici, gereksiz çift dönüştürme azaltmak için güncelleştirildi. Örneğin, (dönüş türü dahil) imzasında yönetilen bir tür olan herhangi bir işlev örtük olarak işaretlenecek `__clrcall`. Çift Thunk hakkında daha fazla bilgi için bkz. [ https://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx ](https://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx).

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, çift dönüştürme gösterir. Yerel olarak derlendiğinde (olmadan **/CLR**), sanal işlev çağrısı `main` bir çağrı oluşturur `T`'s oluşturucuyu ve yok edici bir çağrı kopyalayın. Sanal işlev ile bildirildiğinde benzer bir davranış elde **/CLR** ve `__clrcall`. Ancak, yalnızca ile derlendiğinde **/CLR**kopya oluşturucusunun yönetilen yerel dönüştürücü nedeniyle başka bir çağrı yoktur ancak işlev çağrısı kopya oluşturucusuna bir çağrı oluşturur.

### <a name="code"></a>Kod

```
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

Çift dönüştürme varlığını önceki örnek gösterilmektedir. Bu örnek etkisini gösterir. `for` Döngü sanal işlevi ve program raporları yürütme süresi çağırır. En yavaş zaman program ile derlendiğinde bildirilir **/CLR**. Hızlı süreler olmadan derleme yaparken raporlanır **/CLR** veya sanal işlev ile bildirilirse `__clrcall`.

### <a name="code"></a>Kod

```
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

[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
