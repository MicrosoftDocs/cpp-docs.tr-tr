---
title: C++ birlikte çalışması (örtük PInvoke) kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- blittable types [C++]
- platform invoke [C++], implicit
- interop [C++], features
- data marshaling [C++], C++ Interop features
- porting [C++], C++ native to .NET
- COM interfaces [C++]
- implicit platform invoke
- examples [C++], interoperability
- types [C++], blittable
- marshaling [C++], C++ Interop features
- platform invoke [C++], examples
- interoperability [C++]
- C++ Interop
- interoperability [C++], Implicit PInvoke
- C++, interop
- C++ COM Interop
- .NET [C++], porting C++ native to
ms.assetid: 5f710bf1-88ae-4c4e-8326-b3f0b7c4c68a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a095f252c4e46e212e42a7ab4cf3cb8d5ef6f53d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704300"
---
# <a name="using-c-interop-implicit-pinvoke"></a>C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)

Diğer .NET dilleri, Visual C++ yönetilen ve yönetilmeyen kodu aynı uygulama ve hatta aynı dosyada verir bir birlikte çalışabilirlik desteğe sahiptir (ile [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) pragmaları). Bu uygulamanın geri kalanına etkilemeden uygulamalarınız Visual C++ .NET işlevselliği tümleştirmek Visual C++ geliştiriciler sağlar.

Kullanarak yönetilen derlenecek dosyadan yönetilmeyen işlevleri çağırabilir [dllexport, dllimport](../cpp/dllexport-dllimport.md).

İşlev parametreleri nasıl sıralanacağını veya DllImportAttribute açıkça çağrıldığında belirtilen diğer ayrıntıları birini belirtmek gerekmediğinde örtük PInvoke kullanışlıdır.

Visual C++ yönetilen ve yönetilmeyen işlevleri birlikte çalışmak iki yol sunar:

- [C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

Açık PInvoke .NET Framework tarafından desteklenir ve çoğu .NET dillerinde kullanılabilir. Ancak adından da anlaşılacağı gibi C++ birlikte çalışabilirliği Visual C++'a özeldir.

## <a name="c-interop"></a>C++ Birlikte Çalışma

C++ birlikte çalışması üzerinde açık PInvoke önerilir, bu, daha iyi tür güvenliği sağlar, uygulama genellikle daha az sıkıcı, yönetilmeyen API değiştirilir ve ile mümkün olmayan performans geliştirmeleri olası açık hale getirir daha forgiving değil çünkü PInvoke. Ancak, C++ birlikte çalışabilirliği yönetilmeyen kaynak kod kullanılabilir değilse mümkün değildir.

## <a name="c-com-interop"></a>C++ COM Birlikte Çalışma

COM bileşenleriyle birlikte çalışmaya geldiğinde Visual C++'ın desteklediği birlikte çalışabilirlik özelliklerini diğer .NET dilleri göre belirgin bir avantaj sunar. .NET Framework'ün kısıtlamaları sınırlı olmak yerine [Tlbimp.exe (tür kitaplığı içeri Aktarıcı)](/dotnet/framework/tools/tlbimp-exe-type-library-importer), veri türleri ve her COM arabirimi her üyesinin zorunlu Etkilenme için sınırlı destek gibi C++ birlikte çalışabilirliği COM sağlar. konumundaki erişilecek bileşenleri olur ve ayrı birlikte çalışma derlemeleri gerektirmez. Visual Basic ve C#, Visual C++ COM nesneleri normal COM mekanizmalarını kullanarak doğrudan kullanabilirsiniz (gibi **CoCreateInstance** ve **QueryInterface**). Bu, otomatik olarak geçiş kodu yönetilmeyen yönetilen işlevlerden taşıyın ve yeniden eklemek derleyici neden C++ birlikte çalışabilirlik özellikleri nedeniyle mümkündür.

C++ birlikte çalışması kullanarak COM bileşenlerini normalde kullanılan ya da C++ sınıfları içinde kaydırılmış olarak kullanılabilir. Bu sarmalayıcı sınıflar özel çalışma zamanı aranabilir sarmalayıcıları denir veya CRCWs ve COM doğrudan uygulama kodu kullanarak iki avantajı vardır:

- Sonuçta elde edilen sınıf Visual C++ dışındaki dillerde kullanılabilir.

- COM arabirimi ayrıntılarını yönetilen istemci kodundan gizlenmiş olabilir. Verileri hazırlama ayrıntılarını içinde CRCW şeffaf bir şekilde gerçekleştirilebilir ve .NET veri türleri yerine yerel türleri kullanılabilir.

COM doğrudan veya bir CRCW aracılığıyla kullanılıp kullanılmamasına bakılmaksızın, basit, blittable türleri dışında bağımsız değişken türleri başvuruya gerekir.

## <a name="blittable-types"></a>Blok halinde kopyalanabilir türler

Basit, iç türleri kullanan yönetilmeyen API'ler için (bkz [blok halinde kopyalanabilir ve olmayan Blittable türleri](/dotnet/framework/interop/blittable-and-non-blittable-types)), hiçbir özel kodlama çünkü bu veri türleri aynı gösterimi belleğe sahip, ancak daha karmaşık veri türleri gerektiren gereklidir açık veri hazırlama. Bir örnek için bkz: [nasıl yapılır: yönetilen kod PInvoke kullanarak yerel DLL'lerden çağrı](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md).

## <a name="example"></a>Örnek

```cpp
// vcmcppv2_impl_dllimp.cpp
// compile with: /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

// Implicit DLLImport specifying calling convention
extern "C" int __stdcall MessageBeep(int);

// explicit DLLImport needed here to use P/Invoke marshalling because
// System::String ^ is not the type of the first parameter to printf
[DllImport("msvcrt.dll", EntryPoint = "printf", CallingConvention = CallingConvention::Cdecl,  CharSet = CharSet::Ansi)]
// or just
// [DllImport("msvcrt.dll")]
int printf(System::String ^, ...);

int main() {
   // (string literals are System::String by default)
   printf("Begin beep\n");
   MessageBeep(100000);
   printf("Done\n");
}
```

```Output
Begin beep
Done
```

## <a name="in-this-section"></a>Bu Bölümde

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak ANSI Dizelerini Sıralama](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ Çalışabilirliği Kullanarak Unicode Dizelerini Sıralama](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak COM Dizelerini Sıralama](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Yapıları Sıralama](../dotnet/how-to-marshal-structures-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Dizileri Sıralama](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışmayı Kullanarak Geri Çağrıları ve Temsilcileri Sıralama](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Katıştırılmış İşaretçileri Sıralama](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)

- [Nasıl yapılır: Bir System::String'deki Karakterlere Erişme](../dotnet/how-to-access-characters-in-a-system-string.md)

- [Nasıl yapılır: char * Dizesini System::Byte Dizisine Dönüştürme](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)

- [Nasıl yapılır: System:: String'i wchar_t * veya char dönüştürme\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)

- [Nasıl yapılır: System::String'i Standart Dizeye Dönüştürme](../dotnet/how-to-convert-system-string-to-standard-string.md)

- [Nasıl yapılır: Standart Dizeyi System::String Olarak Dönüştürme](../dotnet/how-to-convert-standard-string-to-system-string.md)

- [Nasıl yapılır: Bayt Dizisine Bir İşaretçi Alma](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)

- [Nasıl yapılır: Yönetilmeyen Kaynakları Bayt Dizisine Yükleme](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)

- [Nasıl yapılır: Yerel İşlevde Başvuru Sınıfını Değiştirme](../dotnet/how-to-modify-reference-class-in-a-native-function.md)

- [Nasıl yapılır: Bir Resmin Yerel mi yoksa CLR mi olduğunu belirleme](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)

- [Nasıl yapılır: Yerel DLL'i Genel Derleme Önbelleğine Ekleme](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)

- [Nasıl yapılır: Yerel Tür İçinde Değer Türüne Başvuruyu Tutma](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)

- [Nasıl yapılır: Yönetilmeyen Bellekte Nesne Başvurusunu Tutma](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)

- [Nasıl yapılır: / CLR derlemesini algılama](../dotnet/how-to-detect-clr-compilation.md)

- [Nasıl yapılır: System::Guid ve GUID Arasında Dönüştürme](../dotnet/how-to-convert-between-system-guid-and-guid.md)

- [Nasıl yapılır: Bir out Parametresini Belirleme](../dotnet/how-to-specify-an-out-parameter.md)

- [Nasıl yapılır: / CLR derlemesinde yerel tür kullanma](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)

- [Nasıl yapılır: Yerel Türlerde İşleyicileri Bildirme](../dotnet/how-to-declare-handles-in-native-types.md)

- [Nasıl yapılır: C# Tarafından Kullanılması için Yerel Sınıfı Sarmalama](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

Birlikte çalışabilirlik senaryosunda temsilcileri kullanma hakkında daha fazla bilgi için bkz: [temsilci (C++ bileşen uzantıları)](../windows/delegate-cpp-component-extensions.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yönetilen Koddan Yerel İşlevleri Çağırma](../dotnet/calling-native-functions-from-managed-code.md)
