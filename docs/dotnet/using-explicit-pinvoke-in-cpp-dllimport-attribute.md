---
description: "Daha fazla bilgi edinin: C++ ' ta açık PInvoke kullanma (DllImport özniteliği)"
title: C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
ms.openlocfilehash: 6c49195cdb677474809435a5bd826808260680e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305489"
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)

.NET Framework, `Dllimport` yönetilen uygulamaların DLL 'ler içinde paketlenmiş yönetilmeyen işlevleri çağırmasına izin veren özniteliğiyle birlikte açık platform çağırma (veya PInvoke) özellikleri sağlar. Yönetilmeyen API 'Lerin dll olarak paketlendiği ve kaynak kodunun kullanılamadığı durumlarda açık PInvoke gereklidir. Örneğin Win32 işlevlerini çağırmak için PInvoke gerekir. Aksi takdirde, daha fazla bilgi için örtük P {Invoke; bkz. [C++ birlikte çalışabilirliği (örtük PInvoke) kullanma](../dotnet/using-cpp-interop-implicit-pinvoke.md) .

PInvoke kullanılarak kullanılır <xref:System.Runtime.InteropServices.DllImportAttribute> . DLL adını ilk bağımsız değişkeni olarak alan bu öznitelik, kullanılacak her DLL giriş noktası için bir işlev bildiriminden önce yerleştirilir. İşlevin imzası, DLL tarafından dışarıya aktarılmış bir işlevin adıyla eşleşmelidir (ancak bazı tür dönüştürme `DllImport` bildirimleri yönetilen türler bakımından tanımlayarak örtük olarak gerçekleştirilebilir.)

Sonuç, gerekli geçiş kodunu (veya dönüştürücü) ve basit veri dönüşümlerini içeren her bir yerel DLL işlevi için yönetilen bir giriş noktasıdır. Yönetilen işlevler daha sonra bu giriş noktaları aracılığıyla DLL 'ye çağrı yapabilir. PInvoke 'un sonucu olarak bir modüle yerleştirilen kod tamamen yönetilir.

## <a name="in-this-section"></a>Bu Bölümde

- [Yönetilen koddan yerel Işlevleri çağırma](../dotnet/calling-native-functions-from-managed-code.md)

- [Nasıl yapılır: yönetilen koddan PInvoke kullanarak yerel dll 'Leri çağırma](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)

- [Nasıl yapılır: PInvoke kullanarak dizeleri sıralama](../dotnet/how-to-marshal-strings-using-pinvoke.md)

- [Nasıl yapılır: PInvoke kullanarak yapıları sıralama](../dotnet/how-to-marshal-structures-using-pinvoke.md)

- [Nasıl yapılır: PInvoke kullanarak dizileri sıralama](../dotnet/how-to-marshal-arrays-using-pinvoke.md)

- [Nasıl yapılır: PInvoke kullanarak Işlev Işaretçilerini sıralama](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)

- [Nasıl yapılır: PInvoke kullanarak katıştırılmış Işaretçileri sıralama](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yönetilen koddan yerel Işlevleri çağırma](../dotnet/calling-native-functions-from-managed-code.md)
