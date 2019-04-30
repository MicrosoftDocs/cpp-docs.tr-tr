---
title: C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)
ms.date: 11/04/2016
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
ms.openlocfilehash: aaa07373b7dd22807290ceefa9197b4013c61fe5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384523"
---
# <a name="using-c-interop-implicit-pinvoke"></a>C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)

Diğer .NET dilleri farklı olarak, Visual C++ yönetilen ve yönetilmeyen kod aynı uygulama ve hatta aynı dosyaya verir birlikte çalışabilirlik desteği vardır (ile [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) pragmalar). Bu uygulamanın kalan bozmadan uygulamalara Visual C++ .NET işlevselliğini tümleştirmek Visual C++ geliştiricileri sağlar.

Yönetilmeyen işlevleri kullanarak bir yönetilen derlenecek de çağırabilirsiniz [dllexport, dllimport](../cpp/dllexport-dllimport.md).

İşlev parametreleri nasıl sıralanacağını ve DllImportAttribute açıkça çağrıldığında belirtilen bir ayrıntıları hiçbirini belirtmek gerekmez, örtük PInvoke yararlı olur.

Visual C++ yönetilen ve yönetilmeyen işlevleri çalışmak iki yol sunar:

- [C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

Açık PInvoke, .NET Framework tarafından desteklenir ve çoğu .NET dillerinde kullanılabilir. Ancak adından da anlaşılacağı gibi C++ birlikte çalışması için Visual C++ özgüdür.

## <a name="c-interop"></a>C++ Birlikte Çalışma

C++ birlikte çalışması üzerinde açık PInvoke önerilir, bu, daha iyi tür güvenliği sağlar, uygulamak genellikle daha az sıkıcı, yönetilmeyen API değiştirilir ve ile mümkün olmayan performans geliştirmeleri olası açık hale getirir, daha forgiving olur çünkü PInvoke. Bununla birlikte, C++ birlikte çalışması yönetilmeyen kaynak kodu yoksa mümkün değildir.

## <a name="c-com-interop"></a>C++ COM Birlikte Çalışma

COM bileşenleri ile birlikte çalışma için söz konusu olduğunda, Visual C++ tarafından desteklenen birlikte çalışabilirlik özellikleri diğer .NET dilleri belirli bir avantajı sunar. .NET Framework'ün kısıtlamaları sınırlı kalmak yerine [Tlbimp.exe (tür kitaplığı içeri Aktarıcı)](/dotnet/framework/tools/tlbimp-exe-type-library-importer), veri türleri ve her COM arayüzünün her üyesine zorunlu açığa için sınırlı destek gibi C++ birlikte çalışması COM sağlar. adresindeki erişilecek bileşenleri olur ve ayrı birlikte çalışma derlemelerini gerektirmez. Visual Basic aksine ve C#, Visual C++, normal COM mekanizmalarını kullanarak doğrudan COM nesneleri kullanabilirsiniz (gibi **CoCreateInstance** ve **QueryInterface**). Bu, derleyicinin otomatik olarak yönetilen, yönetilmeyen işlevleri taşıma ve yeniden için geçiş kodu eklemek neden C++ birlikte çalışabilirlik özellikleri nedeniyle mümkündür.

C++ birlikte çalışması kullanarak COM bileşenlerini normalde kullanılan veya C++ sınıfları içinde sarmalanmış olarak kullanılabilir. Bu sarmalayıcı sınıflar olarak adlandırılan özel çalışma zamanı aranabilir sarmalayıcılarını veya CRCWs ve COM doğrudan uygulama kodu kullanarak iki avantajları vardır:

- Oluşturulan sınıf, Visual C++ dışındaki dillerde kullanılabilir.

- COM arabirimi ayrıntılarını yönetilen istemci kodundan gizlenebilir. Yerel türler yerine .NET veri türleri kullanılabilir ve verileri hazırlama ayrıntılarını içinde CRCW şeffaf bir şekilde gerçekleştirilebilir.

COM doğrudan veya bir CRCW aracılığıyla kullanılıp kullanılmamasına bakılmaksızın, basit bir blok halinde kopyalanabilir türler dışındaki bağımsız değişken türleri sıralanması gerekir.

## <a name="blittable-types"></a>Blok halinde kopyalanabilir türler

Basit, iç türleri kullanan yönetilmeyen API için (bkz [blok halinde kopyalanabilir ve örnekteki](/dotnet/framework/interop/blittable-and-non-blittable-types)), özel kodlama bu veri türlerini bellekte aynı gösterimi vardır, ancak daha karmaşık veri türleri gerektirir gereklidir. açık veri hazırlama. Bir örnek için bkz [nasıl yapılır: Yönetilen Koddan PInvoke kullanarak yerel DLL'leri Çağırma](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md).

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

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak ANSI Dizelerini Hazırlama](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Unicode Dizelerini Hazırlama](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak COM Dizelerini Hazırlama](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Yapıları Hazırlama](../dotnet/how-to-marshal-structures-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Dizileri Hazırlama](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışmayı Kullanarak Geri Çağrıları ve Temsilcileri Hazırlama](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Eklenmiş İşaretçileri Hazırlama](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)

- [Nasıl yapılır: Bir System::String'deki Karakterlere Erişme](../dotnet/how-to-access-characters-in-a-system-string.md)

- [Nasıl yapılır: char * Dizesini System::Byte Dizisine Dönüştürme](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)

- [Nasıl yapılır: System:: String'i wchar_t * veya char olarak dönüştürme\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)

- [Nasıl yapılır: System::String'i Standart Dizeye Dönüştürme](../dotnet/how-to-convert-system-string-to-standard-string.md)

- [Nasıl yapılır: Standart Dizeyi System::String Olarak Dönüştürme](../dotnet/how-to-convert-standard-string-to-system-string.md)

- [Nasıl yapılır: Bayt Dizisine Bir İşaretçi Alma](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)

- [Nasıl yapılır: Yönetilmeyen Kaynakları Bayt Dizisine Yükleme](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)

- [Nasıl yapılır: Yerel İşlevde Başvuru Sınıfını Değiştirme](../dotnet/how-to-modify-reference-class-in-a-native-function.md)

- [Nasıl yapılır: Resmin Yerel mi yoksa CLR mi Olduğunu Belirleme](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)

- [Nasıl yapılır: Yerel DLL'yi Genel Derleme Önbelleğine Ekleme](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)

- [Nasıl yapılır: Yerel Tür İçinde Değer Türüne Başvuruyu Tutma](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)

- [Nasıl yapılır: Yönetilmeyen Bellekte Nesne Başvurusunu Tutma](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)

- [Nasıl yapılır: / CLR derlemesini algılama](../dotnet/how-to-detect-clr-compilation.md)

- [Nasıl yapılır: System::Guid ve GUID Arasında Dönüştürme](../dotnet/how-to-convert-between-system-guid-and-guid.md)

- [Nasıl yapılır: Bir out Parametresi Belirtme](../dotnet/how-to-specify-an-out-parameter.md)

- [Nasıl yapılır: Bir/CLR derlemesinde yerel tür kullanma](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)

- [Nasıl yapılır: Yerel Türlerde İşleyicileri Bildirme](../dotnet/how-to-declare-handles-in-native-types.md)

- [Nasıl yapılır: C# Tarafından Kullanılması için Yerel Sınıfı Sarmalama](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

Birlikte çalışma bir senaryoda kullanma hakkında daha fazla bilgi için bkz: [temsilci (C++ bileşen uzantıları)](../extensions/delegate-cpp-component-extensions.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yönetilen Koddan Yerel İşlevleri Çağırma](../dotnet/calling-native-functions-from-managed-code.md)
