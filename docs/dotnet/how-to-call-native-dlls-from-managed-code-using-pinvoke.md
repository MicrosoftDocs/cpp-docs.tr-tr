---
title: "Nasıl yapılır: Yönetilen koddan PInvoke kullanarak yerel dll 'Leri çağırma"
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- platform invoke [C++], calling native DLLs
- interop [C++], calling native DLLs
- marshaling [C++], calling native DLLs
- data marshaling [C++], calling native DLLs
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
ms.openlocfilehash: b36496690c4d83837a6dff1752f3f0db514869eb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501235"
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>Nasıl yapılır: Yönetilen koddan PInvoke kullanarak yerel dll 'Leri çağırma

Yönetilmeyen DLL 'lerde uygulanan işlevler, platform Invoke (P/Invoke) işlevi kullanılarak yönetilen koddan çağrılabilir. DLL için kaynak kodu kullanılamıyorsa, her çalışma için P/Invoke tek seçenektir. Ancak, diğer .NET dillerinin aksine, Visual C++ P/Invoke için bir alternatif sağlar. Daha fazla bilgi için bkz [. C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, ekranın geçerli çözünürlüğünü piksel olarak almak için Win32 [Getsystemölçümlerini](/windows/win32/api/winuser/nf-winuser-getsystemmetrics) işlevini kullanır.

Bağımsız değişkenler ve dönüş değerleri olarak yalnızca iç türleri kullanan işlevler için ek çalışma gerekmez. İşlev işaretçileri, diziler ve yapılar gibi diğer veri türleri, doğru veri sıralamasını sağlamak için ek öznitelikler gerektirir.

Gerekli olmasa da, bu örnekte gösterildiği gibi, genel ad alanında yer almayan P/Invoke bildirimleri için bir değer sınıfının statik üyeleri yapmak iyi bir uygulamadır.

```
// pinvoke_basic.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value class Win32 {
public:
   [DllImport("User32.dll")]
   static int GetSystemMetrics(int);

   enum class SystemMetricIndex {
      // Same values as those defined in winuser.h.
      SM_CXSCREEN = 0,
      SM_CYSCREEN = 1
   };
};

int main() {
   int hRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CXSCREEN) );
   int vRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CYSCREEN) );
   Console::WriteLine("screen resolution: {0},{1}", hRes, vRes);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
