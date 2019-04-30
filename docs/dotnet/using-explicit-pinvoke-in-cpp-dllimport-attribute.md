---
title: C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
ms.openlocfilehash: ee9d77920f04f7eba5112c66a906b02b7fc4a658
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384432"
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)

.NET Framework ile açık Platform Çağırma (veya PInvoke) özellikleri sağlar `Dllimport` DLL'leri içinde paketlenmiş yönetilmeyen işlevleri çağırmak yönetilen uygulamalar izin vermek için özniteliği. Açık PInvoke burada yönetilmeyen API DLL'ler olarak paketlenir ve kaynak kodu kullanılabilir olmayan durumlar için gereklidir. Win32 işlevlerini çağırma, örneğin, PInvoke gerektirir. Aksi takdirde, örtük kullan {Invoke; bkz: [C++ Çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) daha fazla bilgi için.

PInvoke kullanarak çalışır <xref:System.Runtime.InteropServices.DllImportAttribute>. İlk bağımsız değişken olarak DLL adını alır, bu öznitelik, bir işlev bildirimi kullanılacak her bir DLL giriş noktası için önce yerleştirilir. İşlev imzası DLL tarafından dışarı aktarılan bir işlevin adı eşleşmelidir (ancak bazı tür dönüştürme örtük olarak tanımlayarak gerçekleştirilebilir `DllImport` bildirimleri yönetilen türleri açısından.)

Gerekli geçiş kodunu (veya dönüştürücü) içeren her bir yerel DLL işlevi için bir yönetilen giriş noktası sonucudur ve basit veri dönüştürme. Yönetilen işlevleri aracılığıyla bu giriş noktaları DLL içine çağrı yapabilir. Bir modüle PInvoke sonucu olarak eklenen kod tamamen yönetilir.

## <a name="in-this-section"></a>Bu Bölümde

- [Yönetilen Koddan Yerel İşlevleri Çağırma](../dotnet/calling-native-functions-from-managed-code.md)

- [Nasıl yapılır: PInvoke Kullanarak Yönetilen Koddan Yerel DLL'leri Çağırma](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)

- [Nasıl yapılır: PInvoke Kullanarak Dizeleri Hazırlama](../dotnet/how-to-marshal-strings-using-pinvoke.md)

- [Nasıl yapılır: PInvoke Kullanarak Yapıları Hazırlama](../dotnet/how-to-marshal-structures-using-pinvoke.md)

- [Nasıl yapılır: PInvoke Kullanarak Dizileri Hazırlama](../dotnet/how-to-marshal-arrays-using-pinvoke.md)

- [Nasıl yapılır: PInvoke Kullanarak İşlev İşaretçilerini Hazırlama](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)

- [Nasıl yapılır: PInvoke Kullanarak Eklenmiş İşaretçileri Hazırlama](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yönetilen Koddan Yerel İşlevleri Çağırma](../dotnet/calling-native-functions-from-managed-code.md)
