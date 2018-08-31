---
title: 'Nasıl yapılır: PInvoke kullanarak yapıları sıralama | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data marshaling [C++], structures
- platform invoke [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a26394a906f40d6dc194118bb312cfe1a0ce834e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219890"
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>Nasıl yapılır: PInvoke Kullanarak Yapıları Sıralama
Bu belgede, C stili yapıları tarafından yönetilen işlevlerden P/Invoke kullanılarak çağrılabilir kabul nasıl yerel işlevleri açıklanmaktadır. C++ birlikte çalışabilirlik özellikleri yerine kullanmanızı öneririz ancak P/Invoke küçük derleme zamanı hata raporlama, P/Invoke sağladığı için tür açısından güvenli değildir ve yönetilmeyen API'ın bir DLL olarak paketlenmesi ve kaynak kodu değilse, uygulama can sıkıcı olabilir P/Invoke tek seçenek kullanılabilir. Aksi takdirde, aşağıdaki belgelere bakın:  
  
-   [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
  
-   [Nasıl yapılır: PInvoke Kullanarak Dizeleri Sıralama](../dotnet/how-to-marshal-strings-using-pinvoke.md)
  
 Varsayılan olarak, yerel ve yönetilen yapıları farklı bellekte, bu nedenle başarıyla veri bütünlüğünü korumak için ek adımlar gerektirir yönetilen veya yönetilmeyen sınırında yapıları geçirme düzenlenmiştir.  
  
 Bu belgede, yerel yapılar ve elde edilen yapıların yönetilmeyen işlevlerle nasıl geçirilebilir'sının yönetilen eşdeğerlerini tanımlamak için gereken adımlar açıklanmaktadır. Bu belge, basit varsayar yapıları — bu dizeler veya işaretçiler içermeyen — kullanılır. Blittable olmayan birlikte çalışabilirlik hakkında daha fazla bilgi için bkz. [C++ Çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md). P/Invoke dönüş değeri olarak kopyalanamaz türler sahip olamaz. Blok halinde kopyalanabilir türler, yönetilen ve yönetilmeyen kod içinde aynı gösterimi sahip. Daha fazla bilgi için [blok halinde kopyalanabilir ve örnekteki](https://msdn.microsoft.com/Library/d03b050e-2916-49a0-99ba-f19316e5c1b3).  
  
 Basit hazırlama, yönetilen veya yönetilmeyen sınırı arasında blittable yapıları ilk gerektirir neden yönetilen sürümleri her bir yerel yapısının tanımlanması. Bu yapılar, herhangi bir yasal adı olabilir; Yerel ve yönetilen sürümü kendi veri düzeni dışında iki yapı arasında bir ilişki yoktur. Bu nedenle, yönetilen sürümün alanları aynı boyut ve yerel sürümle aynı sırayla içermesi gereklidir. (Yönetilen ve yerel sürüm yapısı için uyumsuzluk çalışma zamanına kadar görünür olmaz eşdeğer emin olunması için bir mekanizma yoktur. Bu iki yapıları aynı veri yerleşimi olmasını sağlamak için programcının sorumluluğundadır.)  
  
 Yönetilen yapıları üyelerinin performans amacıyla bazen yeniden düzenlendiği kullanmak için gerekli <xref:System.Runtime.InteropServices.StructLayoutAttribute> yapısı düzenlenir, sıralı olarak belirtmek için özniteliği. Yerel yapı tarafından kullanılan ile aynı olması için ayarı paketleme yapısını açıkça ayarlamak için de iyi bir fikirdir. (Varsayılan olarak olsa da, Visual C++ hem yönetilen kod için bir 8 baytlık yapısı kullanır.)  
  
1.  Ardından, <xref:System.Runtime.InteropServices.DllImportAttribute> yapıyı kabul yönetilmeyen işlevlerle karşılık gelen bir giriş noktalarını bildirmek, ancak iki sürümü de aynı adı kullanırsanız, tartışmalı noktası olan işlev imzası yapısında yönetilen sürümünü kullanın yapısı.  
  
2.  Artık gerçekten yönetilen işlevleri olsa gibi yönetilen kod yönetilen sürüm yapısı yönetilmeyen bir işleve geçirebilirsiniz. Bu yapılar aşağıdaki örnekte gösterildiği gibi değere veya başvuruya göre geçirilebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, yönetilmeyen ve yönetilen bir modül oluşur. Yönetilmeyen, konum ve konum yapısını iki örneğini kabul eden GetDistance çağrılan bir işlev olarak adlandırılan bir yapıyı tanımlayan bir DLL modülüdür. İkinci modül GetDistance işlevi alır, ancak konum yapısının MLocation yönetilen eşdeğer açısından tanımlar yönetilen bir komut satırı uygulamasıdır. Uygulamada aynı adı büyük olasılıkla yapısı iki sürümü için kullanılacaktır; Ancak, farklı bir ad, burada DllImport prototip açısından yönetilen sürümün tanımlanır göstermek için kullanılır.  
  
 DLL hiçbir kısmı geleneksel kullanarak yönetilen kod için kullanıma sunulduğunu unutmayın #include yönergesi. Aslında, derleme zamanında algılanmaz DllImport ile içeri aktarılan işlevleri ile ilgili sorunlar için DLL yalnızca çalışma zamanında erişilir.  
  
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
