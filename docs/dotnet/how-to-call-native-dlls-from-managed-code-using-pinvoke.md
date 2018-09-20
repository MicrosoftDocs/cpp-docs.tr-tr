---
title: "Nasıl yapılır: Yönetilen Koddan PInvoke kullanarak yerel DLL'leri Çağırma | Microsoft Docs"
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- platform invoke [C++], calling native DLLs
- interop [C++], calling native DLLs
- marshaling [C++], calling native DLLs
- data marshaling [C++], calling native DLLs
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f849d2d9c3fd4a2d50d652ad159e93442b4c7ff3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404650"
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>Nasıl yapılır: Yönetilen Koddan PInvoke Kullanarak Yerel DLL'leri Çağırma

Platform Çağırma (P/Invoke) işlevini kullanarak yönetilen koddan yönetilmeyen DLL'ler uygulanan işlevler çağrılabilir. DLL kaynak kodunu kullanılabilir durumda değilse, P/Invoke birlikte çalışma için tek seçenektir. Ancak, diğer .NET dilleri farklı olarak, Visual C++ P/Invoke bir alternatif sunar. Daha fazla bilgi için [C++ Çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, Win32 kullanan [GetSystemMetrics](/windows/desktop/api/winuser/nf-winuser-getsystemmetrics) ekrandaki piksel cinsinden geçerli çözünürlüğünü almak için işlevi.

Bağımsız değişken olarak yalnızca iç türleri ve dönüş değerleri işlevler için hiçbir ek iş gereklidir. İşlev işaretçileri, diziler ve yapılar, gibi diğer veri türlerine uygun veri hazırlama sağlamak için ek öznitelikler gerektirir.

Gerekli olmamasına karşın, böylece genel ad alanında yok Bu örnekte gösterildiği gibi bir değer sınıfının P/Invoke bildirimleri statik üyeleri yapmak iyi bir uygulamadır.

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

## <a name="see-also"></a>Ayrıca Bkz.

[C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)