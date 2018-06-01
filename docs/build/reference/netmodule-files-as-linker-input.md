---
title: Bağlayıcı girişi olarak .netmodule dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbb2ab74e8c9d0285b9bec2f9979257d89797022
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704571"
---
# <a name="netmodule-files-as-linker-input"></a>Bağlayıcı Girişi olarak .netmodule Dosyaları

Link.exe giriş olarak şimdi MSIL .obj ve .netmodules kabul eder. Bağlayıcı tarafından üretilen çıkış bir derlemeyi ya da hiç çalışma zamanı bağımlılık herhangi bir bağlayıcıya giriş .netmodules ve .obj ile .netmodule dosyasıdır.

Visual C++ derleyicisi ile tarafından oluşturulan .netmodules [/LN (MSIL modülü Oluştur)](../../build/reference/ln-create-msil-module.md) veya bağlayıcı ile [/NOASSEMBLY (MSIL modülü Oluştur)](../../build/reference/noassembly-create-a-msil-module.md). .objs her zaman bir Visual C++ derleme içinde oluşturulur. Diğer Visual Studio derleyiciler için kullanmak **/target: Module** derleyici seçeneği.

.Obj dosya bağlayıcıya .netmodule oluşturulan Visual C++ derlemeden geçmesi gerekir. Bir .netmodule bilgilerinde çünkü artık desteklenmeyen **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Bağlayıcı komut satırından çağırma hakkında daha fazla bilgi için bkz: [bağlayıcı komut satırı sözdizimi](../../build/reference/linker-command-line-syntax.md), [komut satırında C/C++ derleme kodu](../../build/building-on-the-command-line.md), ve [yolu ve ortam değişkenlerini ayarlama Komut satırı derlemeleri](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).

Bağlayıcı için bir .netmodule veya .dll dosyası geçirme derlenmiş ile Visual C++ derleyicisi tarafından **/CLR** bir bağlayıcı hatasına neden. Daha fazla bilgi için bkz: [.netmodule girdi dosyalarını biçimi seçme](../../build/reference/choosing-the-format-of-netmodule-input-files.md).

MSIL .obj dosyaları ile derlenmiş yanı sıra yerel .obj dosyaları bağlayıcı kabul **/CLR**. Karma .objs aynı derlemede geçirirken, sonuçta elde edilen çıktı dosyası verifiability varsayılan olarak, en düşük düzeyde verifiability giriş modüllerin eşit olacaktır.

Şu anda oluşan bir uygulama iki veya daha fazla derlemelerin varsa ve derlemede dahil edilmek üzere uygulama istediğiniz derlemeleri yeniden derleyin ve .objs veya tek bir derleme üretmek için .netmodules bağlayın.

Bir giriş noktasını kullanarak belirtmelisiniz [/Entry (giriş noktası simgesi)](../../build/reference/entry-entry-point-symbol.md) yürütülebilir görüntü oluşturulurken.

Bir MSIL .obj ya da .netmodule dosyasıyla bağlanırken kullanmak [/LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md), aksi takdirde bağlayıcı MSIL .obj veya .netmodule karşılaştığında, onu /LTCG bağlantısıyla başlayacaktır.

MSIL .obj veya .netmodule dosyaları cl.exe için de geçirilebilir.

Giriş MSIL .obj veya .netmodule dosyaları kaynakları katıştırılmış olamaz. Bir kaynak ile bir çıktı dosyasına (modülü veya derleme) katıştırılır [/ASSEMBLYRESOURCE (yönetilen kaynağı katıştır)](../../build/reference/assemblyresource-embed-a-managed-resource.md) bağlayıcı seçeneği veya ile **/Resource** diğer Visual Studio derleyicileri derleyici seçeneği.

MSIL bağlantılandırma gerçekleştirirken ve ayrıca belirtmezseniz [/LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md), bağlantı yeniden başlatılıyor raporlama bir bilgilendirme iletisi görürsünüz. Bu ileti, MSIL bağlantılandırma bağlayıcı performansı artırmak üzere ancak göz ardı edilebilir, açıkça belirtmek **/LTCG**.

## <a name="example"></a>Örnek

C++ kodu **catch** karşılık gelen, blok **deneyin** için sistemi olmayan özel çağrılır. Ancak, varsayılan olarak, sistem dışı istisnalar CLR sarmalar <xref:System.Runtime.CompilerServices.RuntimeWrappedException>. Ne zaman bir derlemeyi Visual C++ ve Visual C++ dışı modüllerden oluşturulur ve istediğiniz bir **catch** kendi ilgili çağrılacak C++ kodu engelleme **deneyin** yan tümcesi olduğunda **deneyin**blok sistem dışı özel durum oluşturur, eklemelisiniz `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` özniteliği olmayan C++ modülleri için kaynak koduna.

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

Boolean değerini değiştirerek `WrapNonExceptionThrows` özniteliği, Visual C++ kodu bir sistem dışı özel durumu yakalayın yeteneğini değiştirin.

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

- [LINK Giriş Dosyaları](../../build/reference/link-input-files.md)
- [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
