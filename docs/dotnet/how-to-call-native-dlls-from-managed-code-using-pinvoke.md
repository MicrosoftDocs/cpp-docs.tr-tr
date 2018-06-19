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
ms.openlocfilehash: e82690e49daf324d0ff77f89710ecdd09b208c19
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129193"
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>Nasıl yapılır: Yönetilen Koddan PInvoke Kullanarak Yerel DLL'leri Çağırma
Platform Çağırma (P/Invoke) işlevselliği kullanılarak yönetilen koddan yönetilmeyen DLL'lere uygulanan işlevler çağrılabilir. DLL için kaynak kodunu kullanılabilir durumda değilse, P/Invoke birlikte için tek seçenektir. Ancak, diğer .NET dilleri, Visual C++ alternatif P/Invoke sağlar. Daha fazla bilgi için bkz: [C++ Çalışabilirliği kullanarak (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde Win32 kullanan [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) ekrandaki piksel cinsinden geçerli çözünürlüğü alınacak işlev.  
  
 Bağımsız değişken olarak yalnızca iç türlerini kullanan ve dönüş değerleri işlevleri için ek hiçbir iş gereklidir. İşlev işaretçileri, dizileri ve yapıları gibi diğer veri türlerine uygun verileri hazırlama sağlamak için ek öznitelikler gerektirir.  
  
 Gerekli olmamasına karşın, böylece genel ad alanında yok Bu örnekte gösterildiği gibi bir değer sınıfının P/Invoke bildirimleri statik üyeler olun iyi bir uygulamadır.  
  
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