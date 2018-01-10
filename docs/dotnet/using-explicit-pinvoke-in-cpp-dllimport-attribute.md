---
title: "C++ (DllImport özniteliği) açık PInvoke kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d05c88167629bcb6bf86dc600afde0ea3162064f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)
.NET Framework ile açık Platform Çağırma (veya PInvoke) özellikleri sağlar `Dllimport` DLL'leri içinde paketlenmiş yönetilmeyen işlevleri çağırmak yönetilen uygulamalara izin vermek üzere özniteliği. Açık PInvoke olduğu yönetilmeyen API'ler DLL'ler olarak paketlenir ve kaynak kodu kullanılabilir olmadığı durumlarda gereklidir. Win32 işlevleri çağırma, örneğin, PInvoke gerektirir. Örtük P kullanmayacak {Invoke; bkz: [C++ Çalışabilirliği kullanarak (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) daha fazla bilgi için.  
  
 PInvoke kullanarak çalışır <xref:System.Runtime.InteropServices.DllImportAttribute>. DLL ilk bağımsız değişken olarak adını alır, bu öznitelik, bir işlev bildirimi kullanılacak her bir DLL giriş noktası için önce yerleştirilir. İşlev imzası DLL tarafından dışarı aktarılan bir işlevin adını eşleşmesi gerekir (ancak bazı tür dönüşümleri örtük olarak tanımlayarak gerçekleştirilebilir `DllImport` bildirimleri yönetilen türler bakımından.)  
  
 Sonuç gerekli geçiş kodunu (veya dönüştürücü) içeren her yerel DLL işlevi için bir yönetilen giriş noktasıdır ve basit veri dönüşümleri. Yönetilen işlevler, ardından bu giriş noktaları üzerinden DLL içine çağırabilirsiniz. PInvoke sonucu tamamen yönetilen ve açık PInvoke için desteklenen bir modüle eklenen kod **/CLR**, **/CLR: pure**, ve **/CLR: safe** derlemeleri. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı. Daha fazla bilgi için bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
-   [Yönetilen Koddan Yerel İşlevleri Çağırma](../dotnet/calling-native-functions-from-managed-code.md)  
  
-   [Nasıl yapılır: Yönetilen Koddan PInvoke Kullanarak Yerel DLL'leri Çağırma](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)  
  
-   [Nasıl yapılır: PInvoke Kullanarak Dizeleri Sıralama](../dotnet/how-to-marshal-strings-using-pinvoke.md)  
  
-   [Nasıl yapılır: PInvoke Kullanarak Yapıları Sıralama](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
-   [Nasıl yapılır: PInvoke Kullanarak Dizileri Sıralama](../dotnet/how-to-marshal-arrays-using-pinvoke.md)  
  
-   [Nasıl yapılır: PInvoke Kullanarak İşlev İşaretçilerini Sıralama](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)  
  
-   [Nasıl yapılır: PInvoke Kullanarak Katıştırılmış İşaretçileri Sıralama](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen Koddan Yerel İşlevleri Çağırma](../dotnet/calling-native-functions-from-managed-code.md)