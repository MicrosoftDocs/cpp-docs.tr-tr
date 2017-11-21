---
title: "C++ birlikte çalışması (örtük PInvoke) kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1f400ed3e93af8f7e0727d3fe378d0ac471bd18f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-c-interop-implicit-pinvoke"></a>C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)
Diğer .NET dilleri, Visual C++ yönetilen ve yönetilmeyen kodu aynı uygulama ve hatta aynı dosyada verir bir birlikte çalışabilirlik desteğe sahiptir (ile [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) pragmaları). Bu uygulamanın geri kalanına etkilemeden uygulamalarınız Visual C++ .NET işlevselliği tümleştirmek Visual C++ geliştiriciler sağlar.  
  
 Kullanarak yönetilen derlenecek dosyadan yönetilmeyen işlevleri çağırabilir [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
 İşlev parametreleri nasıl sıralanacağını veya DllImportAttribute açıkça çağrıldığında belirtilen diğer ayrıntıları birini belirtmek gerekmediğinde örtük PInvoke kullanışlıdır.  
  
 Visual C++ yönetilen ve yönetilmeyen işlevleri birlikte çalışmak iki yol sunar:  
  
-   [C++ (DllImport özniteliği) açık PInvoke kullanma](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
 Açık PInvoke .NET Framework tarafından desteklenir ve çoğu .NET dillerinde kullanılabilir. Ancak adından da anlaşılacağı gibi C++ birlikte çalışabilirliği Visual C++'a özeldir.  
  
## <a name="c-interop"></a>C++ Birlikte Çalışma  
 C++ birlikte çalışması üzerinde açık PInvoke önerilir, bu, daha iyi tür güvenliği sağlar, uygulama genellikle daha az sıkıcı, yönetilmeyen API değiştirilir ve ile mümkün olmayan performans geliştirmeleri olası açık hale getirir daha forgiving değil çünkü PInvoke. Ancak, C++ birlikte çalışabilirliği yönetilmeyen kaynak kod kullanılabilir değilse veya ile derleme yapılırken mümkün değildir **/CLR: safe**. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı. Bilgi için bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## <a name="c-com-interop"></a>C++ COM Birlikte Çalışma  
 COM bileşenleriyle birlikte çalışmaya geldiğinde Visual C++'ın desteklediği birlikte çalışabilirlik özelliklerini diğer .NET dilleri göre belirgin bir avantaj sunar. .NET Framework'ün kısıtlamaları sınırlı olmak yerine [Tlbimp.exe (tür kitaplığı içeri Aktarıcı)](/dotnet/framework/tools/tlbimp-exe-type-library-importer), veri türleri ve her COM arabirimi her üyesinin zorunlu Etkilenme için sınırlı destek gibi C++ birlikte çalışabilirliği COM sağlar. konumundaki erişilecek bileşenleri olur ve ayrı birlikte çalışma derlemeleri gerektirmez. Daha fazla bilgi için bkz: [kullanarak COM .NET gelen](http://msdn.microsoft.com/en-us/03976661-6278-4227-a6c1-3b3315502c15).  
  
## <a name="blittable-types"></a>Blok halinde kopyalanabilir türler  
 Basit, iç türleri kullanan yönetilmeyen API'ler için (bkz [blok halinde kopyalanabilir ve olmayan Blittable türleri](http://msdn.microsoft.com/Library/d03b050e-2916-49a0-99ba-f19316e5c1b3)), hiçbir özel kodlama çünkü bu veri türleri aynı gösterimi belleğe sahip, ancak daha karmaşık veri türleri gerektiren gereklidir açık veri hazırlama. Bir örnek için bkz: [nasıl yapılır: yönetilen kod PInvoke kullanarak yerel DLL'lerden çağrı](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md).  
  
## <a name="example"></a>Örnek  
  
```  
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
  
-   [Nasıl yapılır: C++ birlikte çalışması kullanarak ANSI dizelerini sıralama](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
-   [Nasıl yapılır: C++ Çalışabilirliği kullanarak Unicode dizelerini sıralama](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Nasıl yapılır: C++ birlikte çalışması kullanarak COM dizelerini sıralama](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
-   [Nasıl yapılır: C++ birlikte çalışması kullanarak yapıları sıralama](../dotnet/how-to-marshal-structures-using-cpp-interop.md)  
  
-   [Nasıl yapılır: C++ birlikte çalışması kullanarak dizileri sıralama](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)  
  
-   [Nasıl yapılır: sıralama geri aramalar ve temsilciler C++ birlikte çalışması kullanarak](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
-   [Nasıl yapılır: C++ birlikte çalışması kullanarak katıştırılmış işaretçileri sıralama](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)  
  
-   [Nasıl yapılır: String'deki karakterlere erişme](../dotnet/how-to-access-characters-in-a-system-string.md)  
  
-   [Nasıl yapılır: Dönüştür char * dizesini System::Byte dizisine](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)  
  
-   [Nasıl yapılır: System:: String'i wchar_t * veya char dönüştürme\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)  
  
-   [Nasıl yapılır: System:: String'i standart dizeye dönüştürme](../dotnet/how-to-convert-system-string-to-standard-string.md)  
  
-   [Nasıl yapılır: standart dizeyi System::String olarak dönüştürme](../dotnet/how-to-convert-standard-string-to-system-string.md)  
  
-   [Nasıl yapılır: Bayt dizisine bir işaretçi edinin](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)  
  
-   [Nasıl yapılır: yönetilmeyen kaynakları Bayt dizisine yükleme](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)  
  
-   [Nasıl yapılır: Yerel İşlevde Başvuru sınıfını değiştirme](../dotnet/how-to-modify-reference-class-in-a-native-function.md)  
  
-   [Nasıl yapılır: bir resmin yerel mi yoksa CLR mi olduğunu belirleme](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)  
  
-   [Nasıl yapılır: yerel DLL'i genel derleme önbelleğine ekleme](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)  
  
-   [Nasıl yapılır: yerel tür içinde değer türüne başvuruyu tutma](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)  
  
-   [Nasıl yapılır: yönetilmeyen bellekte nesne başvurusunu tutma](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)  
  
-   [Nasıl yapılır: / CLR derlemesini algılama](../dotnet/how-to-detect-clr-compilation.md)  
  
-   [Nasıl yapılır: System::Guid ve GUID arasında dönüştürme](../dotnet/how-to-convert-between-system-guid-and-guid.md)  
  
-   [Nasıl yapılır: bir çıkış belirtin parametresi](../dotnet/how-to-specify-an-out-parameter.md)  
  
-   [Nasıl yapılır: / CLR derlemesinde yerel tür kullanma](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)  
  
-   [Nasıl yapılır: yerel türlerde işleyicileri bildirme](../dotnet/how-to-declare-handles-in-native-types.md)  
  
-   [Nasıl yapılır: C# tarafından kullanılması için yerel sınıfı sarmalama](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
 Birlikte çalışabilirlik senaryosunda temsilcileri kullanma hakkında daha fazla bilgi için bkz: [temsilci (C++ bileşen uzantıları)](../windows/delegate-cpp-component-extensions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen koddan yerel işlevleri çağırma](../dotnet/calling-native-functions-from-managed-code.md)