---
title: "Nasıl yapılır: PInvoke kullanarak yapıları sıralama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- data marshaling [C++], structures
- platform invoke [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2ebda5f17b94fa28a5eb5222ccc991119ec4f81a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>Nasıl yapılır: PInvoke Kullanarak Yapıları Sıralama
Bu belgede C stilinde dizeleri örneği sağlayan yönetilen işlevler çağrılabilir kabul nasıl yerel işlevler açıklanmaktadır <xref:System.String> P/Invoke kullanarak. C++ birlikte çalışabilirlik özellikleri yerine kullanmanızı öneririz rağmen P/Invoke P/Invoke çok az derleme zamanı hata raporlama, sağladığından tür kullanımı uyumlu değil ve yönetilmeyen API DLL olarak paketlenir ve kaynak kodu değilse uygulaması can sıkıcı olabilir P/Invoke tek seçenek kullanılabilir. Aksi takdirde, aşağıdaki belgelere bakın:  
  
-   [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [Nasıl yapılır: PInvoke Kullanarak Yapıları Sıralama](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
 Varsayılan olarak, yerel ve yönetilen yapılar farklı bellekte, bunu başarıyla yönetilen ve yönetilmeyen sınırından yapıları geçirme veri tutarlılığını korumak için ek adımlar gerektirir düzenlenmiştir.  
  
 Bu belge yerel yapılar ve elde edilen yapıların yönetilmeyen işlevlerle nasıl geçirilebilir yönetilen eşdeğerlerini tanımlamak için gereken adımları açıklar. Bu belge, basit varsayar yapıları — dizeler veya işaretçiler içermeyen olanlar — kullanılır. Blittable olmayan birlikte çalışabilirlik hakkında daha fazla bilgi için bkz: [C++ Çalışabilirliği kullanarak (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md). P/Invoke kopyalanamaz türler dönüş değeri olarak sahip olamaz. Blittable türleri aynı gösterimi yönetilen ve yönetilmeyen kodunda vardır. Daha fazla bilgi için bkz: [blok halinde kopyalanabilir ve olmayan Blittable türleri](http://msdn.microsoft.com/Library/d03b050e-2916-49a0-99ba-f19316e5c1b3).  
  
 Basit hazırlama, yönetilen ve yönetilmeyen sınır arasında blittable yapıları ilk gerektirir neden yönetilen sürümlerinin her yerel yapısının tanımlanması. Bu yapıları herhangi bir yasal ad olabilir; Veri düzenleri dışında iki yapıları yerel ve yönetilen sürümü arasında ilişkisi yoktur. Bu nedenle, yönetilen sürümün aynı boyut ve yerel sürümü aynı sırada olan alanları içeren önemlidir. (Uyumsuzlukları çalışma zamanına kadar görünür olmaz şekilde yapısı yönetilen ve yerel sürümlerini eşdeğer sağlamaya yönelik bir mekanizma yoktur. Bu iki yapıları aynı veri düzeni olmasını sağlamak için programcı sorumluluğundadır.)  
  
 Yönetilen yapıların üyeleri bazen performans amacıyla yeniden düzenlendiği kullanmak gerekli olan <xref:System.Runtime.InteropServices.StructLayoutAttribute> yapısı düzenlenir, sıralı olarak belirtmek için öznitelik. Yerel yapısı tarafından kullanılan aynı olacak şekilde ayarı paket yapısı açıkça ayarlamak için de iyi bir fikirdir. (Varsayılan olarak olsa da, hem yönetilen kod için 8-bayt yapısının bir Visual C++ kullanır.)  
  
1.  Ardından, kullanın <xref:System.Runtime.InteropServices.DllImportAttribute> yapısı kabul yönetilmeyen işlevlerle karşılık gelen giriş noktalarını bildirmek, ancak her iki sürümü için aynı adı kullanırsanız tartışmalı noktası olan yapısının olan işlev imzalarında yönetilen bir sürümünü kullanmak için yapısı.  
  
2.  Şimdi gerçekten yönetilen işlevler olsa gibi yönetilen kod için yönetilmeyen işlevler yapısı yönetilen bir sürümünü geçirebilirsiniz. Bu yapıları değere veya başvuruya göre aşağıdaki örnekte gösterildiği gibi geçirilebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, bir yönetilmeyen ve yönetilen bir modül oluşur. Yönetilmeyen modül konumu ve konum yapısını iki örneğini kabul GetDistance adında bir işlevi olarak adlandırılan bir yapıyı tanımlayan bir DLL'dir. İkinci modül GetDistance işlevi alır, ancak konum yapısının MLocation yönetilen eşdeğer açısından tanımlayan bir yönetilen komut satırı uygulamasıdır. Uygulamada aynı adı her iki sürümünün de yapısı için büyük olasılıkla kullanılacak; Ancak, farklı bir ad, burada DllImport prototip bakımından yönetilen sürümün tanımlanır göstermek için kullanılır.  
  
 DLL hiçbir bölümünün geleneksel kullanarak yönetilen kod açıktır Not #include yönergesi. Aslında, DLL işlevleri DllImport ile alınan sorun derleme zamanında algılanmaz şekilde yalnızca çalışma zamanında erişilir.  
  
```  
// TraditionalDll3.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
#include <stdio.h>  
#include <math.h>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
   #define TRADITIONALDLL_API __declspec(dllexport)  
#else  
   #define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
#pragma pack(push, 8)  
struct Location {  
   int x;  
   int y;  
};  
#pragma pack(pop)  
  
extern "C" {  
   TRADITIONALDLL_API double GetDistance(Location, Location);  
   TRADITIONALDLL_API void InitLocation(Location*);  
}  
  
double GetDistance(Location loc1, Location loc2) {  
   printf_s("[unmanaged] loc1(%d,%d)", loc1.x, loc1.y);  
   printf_s(" loc2(%d,%d)\n", loc2.x, loc2.y);  
  
   double h = loc1.x - loc2.x;  
   double v = loc1.y = loc2.y;  
   double dist = sqrt( pow(h,2) + pow(v,2) );  
  
   return dist;  
}  
  
void InitLocation(Location* lp) {  
   printf_s("[unmanaged] Initializing location...\n");  
   lp->x = 50;  
   lp->y = 50;  
}  
```  
  
## <a name="example"></a>Örnek  
  
```  
// MarshalStruct_pi.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Sequential, Pack=8)]  
value struct MLocation {  
   int x;  
   int y;  
};  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL3.dll")]  
   static public double GetDistance(MLocation, MLocation);  
   [DllImport("TraditionalDLL3.dll")]  
   static public double InitLocation(MLocation*);  
};  
  
int main() {  
   MLocation loc1;  
   loc1.x = 0;  
   loc1.y = 0;  
  
   MLocation loc2;  
   loc2.x = 100;  
   loc2.y = 100;  
  
   double dist = TraditionalDLL::GetDistance(loc1, loc2);  
   Console::WriteLine("[managed] distance = {0}", dist);  
  
   MLocation loc3;  
   TraditionalDLL::InitLocation(&loc3);  
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);  
}  
```  
  
```Output  
[unmanaged] loc1(0,0) loc2(100,100)  
[managed] distance = 141.42135623731  
[unmanaged] Initializing location...  
[managed] x=50 y=50  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)