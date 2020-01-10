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
ms.openlocfilehash: d26fbefd87b3ba6d6ca7e183be78608777f383b5
ms.sourcegitcommit: 27d9db019f6d84c94de9e6aff0170d918cee6738
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2020
ms.locfileid: "75676931"
---
# <a name="using-c-interop-implicit-pinvoke"></a>C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)

Diğer .NET dillerinin aksine, Visual C++ , yönetilen ve yönetilmeyen kodun aynı uygulamada ve hatta aynı dosyada ( [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) pragmalar ile) var olmasına olanak tanıyan birlikte çalışabilirlik desteğine sahiptir. Bu, Visual C++ geliştiricilerin, uygulamanın geri kalanını etkilemeden mevcut görsel C++ uygulamalarla .net işlevselliğini tümleştirmelerine olanak sağlar.

Ayrıca [, dllexport, dllimport](../cpp/dllexport-dllimport.md)kullanarak yönetilen bir compiland öğesinden yönetilmeyen işlevleri çağırabilirsiniz.

Örtük PInvoke, işlev parametrelerinin nasıl sıralanacaktır veya DllImportAttribute açıkça çağrılırken belirtime diğer ayrıntıların herhangi birini belirtmeniz gerekmiyorsa yararlıdır.

Visual C++ , yönetilen ve yönetilmeyen işlevlerin birlikte çalışabilme için iki yol sunar:

- [C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

Açık PInvoke .NET Framework tarafından desteklenir ve çoğu .NET dilinde kullanılabilir. Ancak, adından da anlaşılacağı gibi C++ , birlikte çalışma, görsele C++özgüdür.

## <a name="c-interop"></a>C++ Birlikte Çalışma

C++Birlikte çalışma daha iyi tür güvenliği sağlar ve genellikle uygulamak daha az sıkıcı olur. Ancak, C++ yönetilmeyen kaynak kodu yoksa ve platformlar arası projeler için birlikte çalışabilirlik bir seçenek değildir.

## <a name="c-com-interop"></a>C++ COM Birlikte Çalışma

Visual C++ tarafından desteklenen birlikte çalışabilirlik ÖZELLIKLERI, com bileşenleriyle birlikte çalışmaya yönelik olarak daha fazla .net dili üzerinden özel bir avantaj sunar. Veri türleri için sınırlı destek ve her COM arabiriminin her üyesinin zorunlu pozlaması gibi .NET Framework [Tlbimp. exe (tür kitaplığı alma)](/dotnet/framework/tools/tlbimp-exe-type-library-importer)kısıtlamalarına sınırlı olmak yerine, C++ birlikte çalışabilirlik com bileşenlerine çalışır ve ayrı birlikte çalışma derlemeleri gerektirmez. Visual Basic ve C#farklı olarak, C++ VISUAL com nesnelerini normal com mekanizmalarını (örneğin, **Cocreateınstance** ve **QueryInterface**) kullanarak doğrudan kullanabilir. Bu, derleyicinin yönetilen ve C++ yönetilmeyen işlevlere geçiş kodunu otomatik olarak eklemesini ve yeniden geri dönmesi için geçiş kodunu otomatik olarak eklemesine neden olan birlikte çalışma özellikleri nedeniyle mümkündür.

Birlikte C++ çalışma kullanarak com bileşenleri, normalde kullanıldığı veya sınıfların içine C++ sarmalanabileceği için kullanılabilir. Bu sarmalayıcı sınıflar, özel çalışma zamanı çağrılabilir sarmalayıcılar veya CRCWs olarak adlandırılır ve COM 'u doğrudan uygulama kodunda kullanmanın iki avantajı vardır:

- Elde edilen sınıf, görsel C++dışındaki dillerden kullanılabilir.

- COM arabiriminin ayrıntıları yönetilen istemci kodundan gizlenebilir. .NET veri türleri yerel türlerin yerine kullanılabilir ve veri hazırlama ayrıntıları CRCW içinde saydam bir şekilde gerçekleştirilebilir.

COM 'un doğrudan mi yoksa bir CRCW aracılığıyla mı kullanıldığı bağımsız değişken türleri, blittable türlerin sıralanması gerekir.

## <a name="blittable-types"></a>Blittable türleri

Basit, iç türler (bkz. [blittable ve blittable olmayan türler](/dotnet/framework/interop/blittable-and-non-blittable-types)) kullanan yönetilmeyen API 'ler için, bu veri türleri bellekte aynı gösterimine sahip olduğu halde daha karmaşık veri türleri açık veri hazırlama gerektirdiğinden özel bir kodlama gerekmez. Bir örnek için bkz. [nasıl yapılır: yönetilen koddan PInvoke kullanarak yerel dll 'Leri çağırma](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md).

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

- [Nasıl yapılır: System:: String 'i wchar_t * veya char\* dönüştürme](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)

- [Nasıl yapılır: System::String'i Standart Dizeye Dönüştürme](../dotnet/how-to-convert-system-string-to-standard-string.md)

- [Nasıl yapılır: Standart Dizeyi System::String Olarak Dönüştürme](../dotnet/how-to-convert-standard-string-to-system-string.md)

- [Nasıl yapılır: Bayt Dizisine Bir İşaretçi Alma](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)

- [Nasıl yapılır: Yönetilmeyen Kaynakları Bayt Dizisine Yükleme](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)

- [Nasıl yapılır: Yerel İşlevde Başvuru Sınıfını Değiştirme](../dotnet/how-to-modify-reference-class-in-a-native-function.md)

- [Nasıl yapılır: Bir Resmin Yerel mi yoksa CLR mi olduğunu belirleme](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)

- [Nasıl yapılır: Yerel DLL'i Genel Derleme Önbelleğine Ekleme](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)

- [Nasıl yapılır: Yerel Tür İçinde Değer Türüne Başvuruyu Tutma](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)

- [Nasıl yapılır: Yönetilmeyen Bellekte Nesne Başvurusunu Tutma](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)

- [Nasıl yapılır:/clr derlemesini algılama](../dotnet/how-to-detect-clr-compilation.md)

- [Nasıl yapılır: System::Guid ve GUID Arasında Dönüştürme](../dotnet/how-to-convert-between-system-guid-and-guid.md)

- [Nasıl yapılır: Bir out Parametresini Belirleme](../dotnet/how-to-specify-an-out-parameter.md)

- [Nasıl yapılır:/clr derlemesinde yerel tür kullanma](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)

- [Nasıl yapılır: Yerel Türlerde İşleyicileri Bildirme](../dotnet/how-to-declare-handles-in-native-types.md)

- [Nasıl yapılır: C# Tarafından Kullanılması için Yerel Sınıfı Sarmalama](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

Birlikte çalışabilirlik senaryosunda temsilciler kullanma hakkında bilgi için bkz. [Temsilci (C++ bileşen uzantıları)](../extensions/delegate-cpp-component-extensions.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yönetilen Koddan Yerel İşlevleri Çağırma](../dotnet/calling-native-functions-from-managed-code.md)
