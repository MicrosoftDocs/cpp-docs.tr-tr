---
title: .netmodule bağlayıcı girişi olarak dosyalar
description: Karma 'in nasıl kullanılacağını açıklar.obj '.netmodule .NET derlemeleri oluştururken bağlayıcı girişi olarak dosyalar.
ms.date: 01/30/2020
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodule files
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
no-loc:
- obj
- netmodule
- clr
- pure
- safe
ms.openlocfilehash: 83eab25624bdb81ba9191e4efe6a774551502ee0
ms.sourcegitcommit: c4528a7424d35039454f17778baf1b5f98fbbee7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912821"
---
# <a name="opno-locnetmodule-files-as-linker-input"></a>.netmodule bağlayıcı girişi olarak dosyalar

LINK. exe, MSIL *`.obj`* ve *`.netmodule`* dosyalarını girdi olarak kabul eder. Bağlayıcı tarafından üretilen çıkış dosyası, bağlayıcıya giriş yapan *`.obj`* veya *`.netmodule`* dosya üzerinde çalışma zamanı bağımlılığı olmayan bir derleme veya *`.netmodule`* dosyasıdır.

## <a name="remarks"></a>Açıklamalar

*`.netmodule`* dosyaları [/ln (MSIL Modülü Oluştur)](ln-create-msil-module.md) ile MSVC derleyicisi tarafından ya da [/NOASSEMBLY (MSIL Modülü Oluştur)](noassembly-create-a-msil-module.md)ile bağlayıcı tarafından oluşturulur. *`.obj`* dosyalar her zaman bir C++ derlemede oluşturulur. Diğer Visual Studio derleyicileri için **/target: Module** derleyici seçeneğini kullanın.

Bağlayıcı, *`.netmodule`* oluşturan C++ derlemeden *`.obj`* dosyasını geçirmelidir. *`.netmodule`* **/clr:pure** ve **/clr:safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ve sonrasında desteklenmez.

Bağlayıcıyı komut satırından çağırma hakkında daha fazla bilgi için bkz. [bağlayıcı komut satırı sözdizimi](linking.md), [komut satırından MSVC araç takımını kullanma](../building-on-the-command-line.md)ve [komut satırı derlemeleri Için yolu ve ortam değişkenlerini ayarlama](../setting-the-path-and-environment-variables-for-command-line-builds.md).

**/clr** ile MSVC derleyicisi tarafından derlenen bağlayıcıya bir *`.netmodule`* veya *`.dll`* dosyası geçirme bağlayıcı hatasına neden olabilir. Daha fazla bilgi için bkz [..netmodule giriş dosyalarının biçimini seçme](choosing-the-format-of-netmodule-input-files.md).

Bağlayıcı hem yerel *`.obj`* dosyalarını hem de **/clr** derlenmiş MSIL *`.obj`* dosyalarını kabul eder. Karma *`.obj`* dosyalarını aynı derlemede geçirebilirsiniz. Elde edilen çıkış dosyasının varsayılan doğruıı özelliği, en düşük giriş modülünün verifime özelliğiyle aynıdır.

İki veya daha fazla derlemeden oluşan bir uygulamayı tek bir derlemede bulundurmak üzere değiştirebilirsiniz. Derlemelerin kaynaklarını yeniden derleyin ve sonra tek bir derleme oluşturmak için *`.obj`* dosyalarını veya *`.netmodule`* dosyalarını bağlayın.

Yürütülebilir bir görüntü oluştururken [/Entry (giriş noktası simgesi)](entry-entry-point-symbol.md) kullanarak bir giriş noktası belirtin.

Bir MSIL *`.obj`* veya *`.netmodule`* dosyası ile bağlantı sırasında, [/LTCG (bağlantı zamanı kodu oluşturma)](ltcg-link-time-code-generation.md)kullanın, aksi takdirde bağlayıcı MSIL *`.obj`* veya *`.netmodule`* ile karşılaştığında, bağlantı **/LTCG**ile yeniden başlatılır. Bağlantının yeniden başlatıldığı bilgilendirici bir ileti görürsünüz. Bu iletiyi yoksayabilirsiniz, ancak bağlayıcı performansını artırmak için **/LTCG**'yi açıkça belirtin.

MSIL *`.obj`* veya *`.netmodule`* dosyaları CL. exe ' ye de geçirilebilir.

Giriş MSIL *`.obj`* veya *`.netmodule`* dosyalarının katıştırılmış kaynakları olamaz. [/ASSEMBLYRESOURCE (yönetilen kaynağı katıştır)](assemblyresource-embed-a-managed-resource.md) bağlayıcı seçeneğini kullanarak, kaynakları bir çıkış modülüne veya derleme dosyasına ekleyin. Ya da diğer Visual Studio derleyicileri içindeki **/Resource** derleyici seçeneğini kullanın.

## <a name="examples"></a>Örnekler

C++ Kodda, karşılık gelen bir **`try`** **`catch`** bloğu`System` olmayan bir özel durum için çağrılacaktır. Ancak varsayılan olarak, CLR`System` olmayan özel durumları <xref:System.Runtime.CompilerServices.RuntimeWrappedException>ile sarmalanmış. Bir bütünleştirilmiş C++ kod veC++ modüllerden bir derleme oluşturulduğunda ve **`try`** bloğu`System` olmayan bir özel durum oluşturduğunda,C++ C++ koddaki **`catch`** bloğunun karşılık gelen **`try`** yan tümcesinden çağrılması istediğinizde, modüller dışındaki `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` özniteliğini kaynak koda eklemeniz gerekir.

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

`WrapNonExceptionThrows` özniteliğinin `Boolean` değerini değiştirerek, C++ kodun`System` olmayan bir özel durumu yakalayabilme özelliğini değiştirirsiniz.

```csharp
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
- [MSVC Bağlayıcı Seçenekleri](linker-options.md)
