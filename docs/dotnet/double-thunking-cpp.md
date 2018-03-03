---
title: "Çift Thunking (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- double thunks
- interop [C++], double thunking
- mixed assemblies [C++], double thunking
- /clr compiler option [C++], double thunking
- interoperability [C++], double thunking
ms.assetid: a85090b2-dc3c-498a-b40c-340db229dd6f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1d905f962af6a9cf07ecb0926503fc24e21c0136
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="double-thunking-c"></a>Çift Dönüştürme (C++)
Çift dönüştürme, bir Visual C++ yönetilen işlevi ve program yürütmenin yönetilen bağlam çağrıları işlev çağrısında yönetilen işlevi çağırmak için işlevin yerel giriş noktası çağırdığında karşılaşabileceğiniz performans kaybı anlamına gelir. Bu konuda, çift dönüştürme nerede oluştuğunu ve performansı artırmak için kaçının nasıl anlatılmaktadır.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak ile derleme yapılırken, **/CLR**, yönetilen bir işlev tanımı yönetilen bir giriş noktası ve bir yerel giriş noktası oluşturmak derleyicinin neden olur. Bu, yerel ve yönetilen çağrı sitelerinden çağrılacak Yönetilen işlev sağlar. Ancak, yerel giriş noktası varsa, işlev tüm çağrıları için giriş noktası olabilir. Bir arama işlevi yönetiliyorsa, yerel giriş noktası sonra yönetilen giriş noktası çağırır. İki çağrıları işlevi çağırmak için uygulamada gereklidir (Bu nedenle, dönüştürme çift). Örneğin, sanal işlevler her zaman yerel giriş noktası aracılığıyla çağrılır.  
  
 Bir çözüm olan yönetilen bir işlev için yerel giriş noktası değil oluşturulacak derleyici işlevi yalnızca bir yönetilen bağlamdan kullanarak çağrılacağı bildirmek için [__clrcall](../cpp/clrcall.md) çağırma.  
  
 Benzer şekilde, dışarı aktarırsanız ([dllexport, dllimport](../cpp/dllexport-dllimport.md)) yönetilen bir işlev yerel giriş noktası oluşturulur ve içe aktarır ve bu işlev çağrıları herhangi bir işlev yerel giriş noktası aracılığıyla çağırır. Bu durumda çift dönüştürme önlemek için yerel dışa aktarma/içe aktarma semantiği kullanmayın; yalnızca meta verileri yoluyla başvuru `#using` (bkz [#using yönergesi](../preprocessor/hash-using-directive-cpp.md)).  
  
 Derleyici, gereksiz çift dönüştürme azaltmak için güncelleştirilmiştir. Örneğin, herhangi bir yönetilen türü (dönüş türü dahil) imzada işleviyle örtük olarak işaretlenir `__clrcall`. Çift dönüştürücü eleme hakkında daha fazla bilgi için bkz: [http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx](http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx).  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, çift dönüştürme gösterir. Yerel olarak derlendiğinde (olmadan **/CLR**), sanal işlev çağrısı `main` yapılan bir çağrı oluşturur `T`'s oluşturucu ve yıkıcı yapılan bir çağrı kopyalayın. Benzer davranış sanal işlev ile bildirildiğinde elde **/CLR** ve `__clrcall`. Ancak, yalnızca ile derlendiğinde **/CLR**, işlev çağrısının bir çağrı kopya Oluşturucu oluşturur ancak başka bir çağrıyı yönetilen yerel dönüştürücü nedeniyle kopya oluşturucu yok.  
  
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
 Çift dönüştürme varlığı önceki örnek gösterilmektedir. Bu örnek etkisini gösterir. `for` Döngü çağırır sanal işlevi ve program raporları yürütme süresi. Program ile derlendiğinde yavaş zaman bildirilir **/CLR**. Hızlı zamanlar olmadan derlerken bildirilen **/CLR** veya sanal işlev ile bildirilirse `__clrcall`.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)