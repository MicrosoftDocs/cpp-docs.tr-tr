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
ms.openlocfilehash: 5b3b2c69e022de6420223786f0f3b3f266c4f816
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)
.NET Framework ile açık Platform Çağırma (veya PInvoke) özellikleri sağlar `Dllimport` DLL'leri içinde paketlenmiş yönetilmeyen işlevleri çağırmak yönetilen uygulamalara izin vermek üzere özniteliği. Açık PInvoke olduğu yönetilmeyen API'ler DLL'ler olarak paketlenir ve kaynak kodu kullanılabilir olmadığı durumlarda gereklidir. Win32 işlevleri çağırma, örneğin, PInvoke gerektirir. Örtük P kullanmayacak {Invoke; bkz: [C++ Çalışabilirliği kullanarak (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) daha fazla bilgi için.  
  
 PInvoke kullanarak çalışır <xref:System.Runtime.InteropServices.DllImportAttribute>. DLL ilk bağımsız değişken olarak adını alır, bu öznitelik, bir işlev bildirimi kullanılacak her bir DLL giriş noktası için önce yerleştirilir. İşlev imzası DLL tarafından dışarı aktarılan bir işlevin adını eşleşmesi gerekir (ancak bazı tür dönüşümleri örtük olarak tanımlayarak gerçekleştirilebilir `DllImport` bildirimleri yönetilen türler bakımından.)  
  
 Sonuç gerekli geçiş kodunu (veya dönüştürücü) içeren her yerel DLL işlevi için bir yönetilen giriş noktasıdır ve basit veri dönüşümleri. Yönetilen işlevler, ardından bu giriş noktaları üzerinden DLL içine çağırabilirsiniz. PInvoke sonucu tamamen yönetilen ve açık PInvoke için desteklenen bir modüle eklenen kod **/CLR**, **/CLR: pure**, ve **/CLR: safe** derlemeleri. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı. Daha fazla bilgi için bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
-   [Yönetilen koddan yerel işlevleri çağırma](../dotnet/calling-native-functions-from-managed-code.md)  
  
-   [Nasıl yapılır: Yönetilen Koddan PInvoke kullanarak yerel DLL'leri Çağırma](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)  
  
-   [Nasıl yapılır: PInvoke kullanarak dizeleri sıralama](../dotnet/how-to-marshal-strings-using-pinvoke.md)  
  
-   [Nasıl yapılır: PInvoke kullanarak yapıları sıralama](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
-   [Nasıl yapılır: PInvoke kullanarak dizileri sıralama](../dotnet/how-to-marshal-arrays-using-pinvoke.md)  
  
-   [Nasıl yapılır: PInvoke kullanarak işlev işaretçilerini sıralama](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)  
  
-   [Nasıl yapılır: PInvoke kullanarak katıştırılmış işaretçileri sıralama](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen koddan yerel işlevleri çağırma](../dotnet/calling-native-functions-from-managed-code.md)