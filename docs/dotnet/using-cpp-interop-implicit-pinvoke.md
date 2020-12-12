---
description: 'Hakkında daha fazla bilgi edinin: C++ birlikte çalışabilirliği kullanma (örtük PInvoke)'
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
ms.openlocfilehash: e2b1f1aeef68fd6329ef04a53249d7dce627f2c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255559"
---
# <a name="using-c-interop-implicit-pinvoke"></a>C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)

Diğer .NET dillerinin aksine, Visual C++ yönetilen ve yönetilmeyen kodun aynı uygulamada ve hatta aynı dosyada ( [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) pragmalar ile) var olmasına olanak tanıyan birlikte çalışabilirlik desteğine sahiptir. Bu, Visual C++ geliştiricilerin, uygulamanın geri kalanını etkilemeden .NET işlevselliğini mevcut Visual C++ uygulamalarıyla tümleştirmesine olanak tanır.

Ayrıca [, dllexport, dllimport](../cpp/dllexport-dllimport.md)kullanarak yönetilen bir compiland öğesinden yönetilmeyen işlevleri çağırabilirsiniz.

Örtük PInvoke, işlev parametrelerinin nasıl sıralanacaktır veya DllImportAttribute açıkça çağrılırken belirtime diğer ayrıntıların herhangi birini belirtmeniz gerekmiyorsa yararlıdır.

Visual C++ yönetilen ve yönetilmeyen işlevlerin birlikte çalışabilme için iki yol sunar:

- [C++ ' ta açık PInvoke kullanma (DllImport özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

Açık PInvoke .NET Framework tarafından desteklenir ve çoğu .NET dilinde kullanılabilir. Ancak, adından da anlaşılacağı gibi, C++ birlikte çalışması Visual C++ özgüdür.

## <a name="c-interop"></a>C++ Birlikte Çalışma

C++ birlikte çalışması daha iyi tür güvenliği sağlar ve genellikle uygulamak daha az sıkıcı olur. Ancak, yönetilmeyen kaynak kodu yoksa ve platformlar arası projeler için C++ birlikte çalışması bir seçenek değildir.

## <a name="c-com-interop"></a>C++ COM Birlikte Çalışma

Visual C++ tarafından desteklenen birlikte çalışabilirlik özellikleri, COM bileşenleriyle birlikte çalışmaya yönelik olarak daha fazla .NET dili üzerinden belirli bir avantaj sunar. Veri türleri için sınırlı destek ve her COM arabiriminin her üyesinin zorunlu pozlaması gibi .NET Framework [Tlbimp.exe (tür kitaplığı alma)](/dotnet/framework/tools/tlbimp-exe-type-library-importer)kısıtlamalarına sınırlı olmak yerine, C++ bırlıkte çalışması com bileşenlerine ' de erişilmesine izin verir ve ayrı birlikte çalışma derlemeleri gerektirmez. Visual Basic ve C# ' den farklı olarak, Visual C++ normal COM mekanizmalarını ( **Cocreateınstance** ve **QueryInterface** gıbı) kullanarak doğrudan com nesneleri kullanabilir. Bu, derleyicinin yönetilen ve yönetilmeyen işlevlere geçiş kodunu otomatik olarak eklemesini ve yeniden geri taşımasını sağlayan C++ birlikte çalışma özellikleri nedeniyle mümkündür.

C++ birlikte çalışabilirliğine göre COM bileşenleri, normalde kullanıldığı veya C++ sınıflarının içine sarmalanabileceği için kullanılabilir. Bu sarmalayıcı sınıflar, özel çalışma zamanı çağrılabilir sarmalayıcılar veya CRCWs olarak adlandırılır ve COM 'u doğrudan uygulama kodunda kullanmanın iki avantajı vardır:

- Elde edilen sınıf, Visual C++ dışındaki dillerden kullanılabilir.

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

- [Nasıl yapılır: C++ birlikte çalışması kullanarak ANSI Dizelerini Sıralama](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ birlikte çalışabilirliği kullanarak Unicode dizelerini sıralama](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ birlikte çalışması kullanarak COM dizelerini sıralama](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ birlikte çalışması kullanarak yapıları sıralama](../dotnet/how-to-marshal-structures-using-cpp-interop.md)

- [Nasıl yapılır: C++ birlikte çalışması kullanarak dizileri sıralama](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)

- [Nasıl yapılır: C++ birlikte çalışabilirliği kullanarak geri çağırmaları ve temsilcileri sıralama](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

- [Nasıl yapılır: C++ birlikte çalışması kullanarak katıştırılmış Işaretçileri sıralama](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)

- [Nasıl yapılır: bir System:: String içindeki karakterlere erişme](../dotnet/how-to-access-characters-in-a-system-string.md)

- [Nasıl yapılır: char * dizesini System:: Byte dizisine dönüştürme](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)

- [Nasıl yapılır: System:: String 'i wchar_t * veya char olarak dönüştürme\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)

- [Nasıl yapılır: System:: String 'i standart dizeye dönüştürme](../dotnet/how-to-convert-system-string-to-standard-string.md)

- [Nasıl yapılır: Standart Dizeyi System:: String olarak dönüştürme](../dotnet/how-to-convert-standard-string-to-system-string.md)

- [Nasıl yapılır: bayt dizisine bir Işaretçi alma](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)

- [Nasıl yapılır: yönetilmeyen kaynakları bayt dizisine yükleme](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)

- [Nasıl yapılır: yerel Işlevde başvuru sınıfını değiştirme](../dotnet/how-to-modify-reference-class-in-a-native-function.md)

- [Nasıl yapılır: bir resmin yerel mi yoksa CLR mi olduğunu belirleme](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)

- [Nasıl yapılır: yerel DLL 'i genel derleme önbelleğine ekleme](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)

- [Nasıl yapılır: Yerel tür içinde değer türüne başvuruyu tutma](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)

- [Nasıl yapılır: yönetilmeyen bellekte nesne başvurusunu tutma](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)

- [Nasıl yapılır:/clr derlemesini algılama](../dotnet/how-to-detect-clr-compilation.md)

- [Nasıl yapılır: System:: Guid ve _GUID arasında dönüştürme](../dotnet/how-to-convert-between-system-guid-and-guid.md)

- [Nasıl yapılır: bir out parametresi belirtme](../dotnet/how-to-specify-an-out-parameter.md)

- [Nasıl yapılır:/clr derlemesinde yerel tür kullanma](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)

- [Nasıl yapılır: yerel türlerde tutamaçları bildirme](../dotnet/how-to-declare-handles-in-native-types.md)

- [Nasıl yapılır: yerel sınıfı C tarafından kullanılmak üzere sarın #](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

Birlikte çalışabilirlik senaryosunda temsilciler kullanma hakkında daha fazla bilgi için bkz. [Temsilci (C++ Bileşen Uzantıları)](../extensions/delegate-cpp-component-extensions.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yönetilen koddan yerel Işlevleri çağırma](../dotnet/calling-native-functions-from-managed-code.md)
