---
title: 'Nasıl yapılır: PInvoke Kullanarak Yapıları Sıralama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], structures
- platform invoke [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
ms.openlocfilehash: e132505ef536a79c67afdd76443c2637c08f923b
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008746"
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>Nasıl yapılır: PInvoke Kullanarak Yapıları Sıralama

Bu belge, C stili yapıları kabul eden yerel işlevlerin P/Invoke kullanılarak yönetilen işlevlerden nasıl çağrılacağını açıklar. P/Invoke çok az derleme zamanı hata raporlama sağladığından, tür kullanımı güvenli olmadığından ve bu yönetilmeyen API bir DLL olarak paketleniyorsa ve kaynak kodu kullanılabilir değilse, P/Invoke tek seçenek olduğundan p/Invoke yerine C++ birlikte çalışma özelliklerini kullanmanızı öneririz. Aksi takdirde, aşağıdaki belgelere bakın:

- [C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [Nasıl yapılır: PInvoke kullanarak dizeleri sıralama](../dotnet/how-to-marshal-strings-using-pinvoke.md)

Varsayılan olarak, yerel ve yönetilen yapılar bellekte farklı şekilde düzenlenir, bu nedenle yapıları yönetilen/yönetilmeyen sınır genelinde başarıyla geçirmek, veri bütünlüğünü korumak için ek adımlar gerektirir.

Bu belgede yerel yapıların yönetilen eşdeğerlerini tanımlamak için gereken adımlar ve elde edilen yapıların yönetilmeyen işlevlere nasıl geçirilebileceği açıklanmaktadır. Bu belgede basit yapıların (dizeler veya işaretçiler içermeyen) kullanıldığı varsayılır. Blittable olmayan birlikte çalışabilirlik hakkında daha fazla bilgi için bkz. [C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md). P/Invoke, dönüş değeri olarak blittable olmayan türlere sahip olamaz. Blittable türleri, yönetilen ve yönetilmeyen koddaki aynı temsilde sahiptir. Daha fazla bilgi için bkz. [blittable ve blittable olmayan türler](/dotnet/framework/interop/blittable-and-non-blittable-types).

Yönetilen/yönetilmeyen sınır genelinde Simple, blittable yapılarını sıralama, her yerel yapının yönetilen sürümlerinin tanımlanmasını gerektirir. Bu yapılar geçerli bir ada sahip olabilir; veri mizanpajlarından farklı olan iki yapının yerel ve yönetilen sürümü arasında hiçbir ilişki yoktur. Bu nedenle, yönetilen sürümün aynı boyut ve yerel sürümle aynı sırada olan alanları içermesi çok önemlidir. (Yapının yönetilen ve yerel sürümlerinin aynı olduğundan emin olmanın bir mekanizması yoktur, bu nedenle uyumsuzluklar çalışma zamanına kadar görünür olmayacaktır. Bu, iki yapının aynı veri düzenine sahip olduğundan emin olmak için programcı sorumluluğundadır.)

Yönetilen yapıların üyeleri bazen performans amaçlarıyla yeniden düzenlendiğinden, <xref:System.Runtime.InteropServices.StructLayoutAttribute> yapının sırayla düzenlendiğini göstermek için özniteliğini kullanmak gereklidir. Yapı paketleme ayarını açıkça yerel yapı tarafından kullanılan ile aynı olacak şekilde ayarlamak da iyi bir fikirdir. (Varsayılan olarak, Visual C++ her iki yönetilen kod için 8 baytlık bir yapı paketleme kullanır.)

1. Daha sonra, <xref:System.Runtime.InteropServices.DllImportAttribute> yapıyı kabul eden yönetilmeyen işlevlere karşılık gelen giriş noktalarını bildirmek için kullanın, ancak yapının her iki sürümü için aynı adı kullandığınızda bir moot noktası olan işlev imzalarında yapının yönetilen sürümünü kullanın.

1. Artık yönetilen kod, yapının yönetilen sürümünü, gerçekten yönetilen işlevler gibi yönetilmeyen işlevlere geçirebilir. Bu yapılar, aşağıdaki örnekte gösterildiği gibi değere veya başvuruya göre geçirilebilir.

## <a name="unmanaged-and-a-managed-modules"></a>Yönetilmeyen ve yönetilen modüller

Aşağıdaki kod, yönetilmeyen ve yönetilen bir modülden oluşur. Yönetilmeyen modül, konum yapısının iki örneğini kabul eden GetDistance adlı bir yapıyı ve Location adlı bir işlevi tanımlayan bir DLL 'dir. İkinci modül, GetDistance işlevini içeri aktaran bir yönetilen komut satırı uygulamasıdır, ancak bunu konum yapısının, MLocation 'ın yönetilen eşdeğeri açısından tanımlar. Uygulamada aynı ad büyük olasılıkla yapının her iki sürümü için de kullanılır; Ancak, DllImport prototipinin yönetilen sürüm açısından tanımlandığını göstermek için burada farklı bir ad kullanılır.

Geleneksel #include yönergesini kullanarak, DLL 'nin hiçbir kısmının yönetilen koda sunulmadığını unutmayın. Aslında, DLL 'ye yalnızca çalışma zamanında erişilir, bu nedenle DllImport ile içeri aktarılan işlevlerle ilgili sorunlar derleme zamanında algılanmaz.

### <a name="example-unmanaged-dll-module"></a>Örnek: yönetilmeyen DLL modülü

```cpp
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

### <a name="example-managed-command-line-application-module"></a>Örnek: yönetilen komut satırı uygulama modülü

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[C++ ' ta açık PInvoke kullanma (DllImport özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
