---
title: Bağlayıcı Girişi olarak .netmodule Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
ms.openlocfilehash: fcba363cff567c69ac0fbd0a541953dfe2c8e910
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818108"
---
# <a name="netmodule-files-as-linker-input"></a>Bağlayıcı Girişi olarak .netmodule Dosyaları

Link.exe giriş olarak artık MSIL .obj ve netmodule'leri kabul eder. Bağlayıcı tarafından üretilen çıkış dosyası bir derleme veya hiçbir çalışma zamanı bağımlılık .obj veya bağlayıcıya giriş netmodule'leri herhangi biri ile bir .netmodule ' dir.

MSVC derleyicisi ile tarafından oluşturulmuş. netmodule'leri [/LN (MSIL modülü Oluştur)](ln-create-msil-module.md) veya bağlayıcı ile [noassembly (MSIL modülü Oluştur)](noassembly-create-a-msil-module.md). .objs her zaman bir Visual C++ derleme içinde oluşturulur. Diğer Visual Studio derleyicileri için kullanmak **/target: Module** derleyici seçeneği.

Visual C++ derlemeden .netmodule oluşturulan bağlayıcıya .obj dosyasına geçmesi gerekir. .Netmodule geçirmeye çünkü artık desteklenmiyor **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Bağlayıcı komut satırından çağırma hakkında daha fazla bilgi için bkz: [bağlayıcı komut satırı sözdizimi](linking.md), [komut satırından MSVC araç takımı kullanın](../building-on-the-command-line.md), ve [yolu ve ortam değişkenlerini ayarlama komut satırı derlemeleri için](../setting-the-path-and-environment-variables-for-command-line-builds.md).

Bağlayıcı için bir .netmodule veya .dll dosyası geçirme MSVC derleyicisi ile tarafından derlendiği **/CLR** bir bağlayıcı hatasına neden. Daha fazla bilgi için [.netmodule giriş dosyaları biçimini seçme](choosing-the-format-of-netmodule-input-files.md).

Bağlayıcı ile derlenmiş MSIL .obj dosyaları yanı sıra yerel .obj dosyaları kabul **/CLR**. Aynı yapı içinde karışık .objs geçirirken, sonuçta gelen çıktı dosyasının doğrulanabilirliği, varsayılan olarak giriş modülleri doğrulanabilirliğinin en düşük düzeyine eşit olacaktır.

Şu anda sahip olduğunuz uygulamanın iki veya daha fazla derleme oluşur ve uygulamanın bir derlemede yer istiyorsanız derlemeleri yeniden derleyin ve ardından .objs veya tek bir derleme oluşturmak için netmodule'leri bağlamanız gerekir.

Bir giriş noktasını kullanarak belirtmelisiniz [/Entry (giriş noktası simgesi)](entry-entry-point-symbol.md) yürütülebilir bir imaj oluştururken.

Bir MSIL .obj veya .netmodule dosyası ile bağlanırken kullanmak [/LTCG (bağlama zamanı kodu oluşturma)](ltcg-link-time-code-generation.md), bağlayıcı MSIL .obj veya .netmodule karşılaştığında, aksi takdirde, bağlantı/LTCG ile yeniden başlatılır.

MSIL .obj veya .netmodule dosyaları cl.exe dosyasına de geçirilebilir.

Giriş MSIL .obj veya .netmodule dosyaları kaynakları katıştırılmış olamaz. Bir kaynak bir çıktı dosyası (modül veya derleme) ile katıştırılmış [koduna konmaz (yönetilen kaynağı katıştır)](assemblyresource-embed-a-managed-resource.md) bağlayıcı seçeneği ile veya **/Resource** diğer Visual Studio derleyicilerinden derleyici seçeneği.

MSIL bağlantılandırma gerçekleştirirken ve ayrıca belirtmezseniz [/LTCG (bağlama zamanı kodu oluşturma)](ltcg-link-time-code-generation.md), bağlantıyı yeniden başlatılıyor raporlama bir bilgilendirme iletisi görürsünüz. Bu ileti, ancak ile MSIL bağlantılandırma bağlayıcı performansını artırmak üzere göz ardı edilebilir, açıkça belirtmediğiniz **/LTCG**.

## <a name="example"></a>Örnek

C++ kod **catch** karşılık gelen, blok **deneyin** bir sistem dışı özel durumu için çağrılır. Bununla birlikte, varsayılan olarak, sistem dışı istisnalar CLR sarmalar <xref:System.Runtime.CompilerServices.RuntimeWrappedException>. Ne zaman bir derleme Visual C++ ve Visual C++ olmayan modüllerden oluşturulur ve istediğiniz bir **catch** ilgili kendi çağrılmasına C++ kodunda block **deneyin** yan tümcesi olduğunda **deneyin**blok bir sistem dışı özel durumu oluşturur, eklemeniz gerekir `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` olmayan C++ modülleri için kaynak kodu özniteliği.

```cpp
// MSIL_linking.cpp
// compile with: /c /clr
value struct V {};

ref struct MCPP {
   static void Test() {
      try {
         throw (gcnew V);
      }
      catch (V ^) {
         System::Console::WriteLine("caught non System exception in C++ source code file");
      }
   }
};

/*
int main() {
   MCPP::Test();
}
*/
```

## <a name="example"></a>Örnek

Boolean değerini değiştirerek `WrapNonExceptionThrows` öznitelik, bir sistem dışı özel durumu yakalamak için Visual C++ kodu özelliği değiştirin.

```cpp
// MSIL_linking_2.cs
// compile with: /target:module /addmodule:MSIL_linking.obj
// post-build command: link /LTCG MSIL_linking.obj MSIL_linking_2.netmodule /entry:MLinkTest.Main /out:MSIL_linking_2.exe /subsystem:console
using System.Runtime.CompilerServices;

// enable non System exceptions
[assembly:RuntimeCompatibility(WrapNonExceptionThrows=false)]

class MLinkTest {
   public static void Main() {
      try {
         MCPP.Test();
      }
      catch (RuntimeWrappedException) {
         System.Console.WriteLine("caught a wrapped exception in C#");
      }
   }
}
```

```Output
caught non System exception in C++ source code file
```

## <a name="see-also"></a>Ayrıca bkz.

- [LINK Giriş Dosyaları](link-input-files.md)
- [MSVC bağlayıcı seçenekleri](linker-options.md)
