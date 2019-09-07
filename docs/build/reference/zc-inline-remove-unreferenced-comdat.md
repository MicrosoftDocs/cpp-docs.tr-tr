---
title: /Zc:inline (Başvurulmayan COMDAT'ı kaldırma)
ms.date: 09/05/2019
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
ms.openlocfilehash: f0c0d9a4e5e5f52d239f1a8591006b3d9e369778
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740108"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (Başvurulmayan COMDAT'ı kaldırma)

Başvurulmayan işlevleri veya yalnızca iç bağlantısı olan verileri kaldırır. **/Zc: inline** belirtildiğinde, derleyici, satır içi verileri veya satır içi işlevleri kullanan çeviri birimlerinin Ayrıca veri veya işlevler için tanımları içermesi gerekir.

## <a name="syntax"></a>Sözdizimi

> **/Zc: satır içi** [ **-** ]

## <a name="remarks"></a>Açıklamalar

**/Zc: inline** belirtildiğinde, derleyici Başvurulmayan COMDAT işlevleri veya verileri için veya yalnızca iç bağlantıya sahip işlevler veya veriler için simge bilgilerini göstermez. Bu iyileştirme, yayın yapılarında bağlayıcı tarafından gerçekleştirilen çalışmanın bazılarını basitleştirir veya [/OPT: ref](opt-optimizations.md) ' bağlayıcı seçeneği belirtildiğinde. Derleyici bu iyileştirme gerçekleştirdiğinde,. obj dosya boyutunu önemli ölçüde azaltabilir ve bağlayıcı hızlarını geliştirebilirsiniz. İyileştirmeler devre dışı bırakıldığında ([/od](od-disable-debug.md)) veya [/GL (tüm program iyileştirmesi)](gl-whole-program-optimization.md) belirtildiğinde bu derleyici seçeneği etkin değildir.

Varsayılan olarak, bu seçenek komut satırı Derlemeleriyle kapalıdır ( **/Zc: inline-** ). [/Permissive-](permissive-standards-conformance.md) seçeneği **/Zc: inline**'ı etkinleştirmez. MSBuild projelerinde seçeneği, > tarafından **Evet** olarak ayarlanan,**başvurulmayan kodu ve veri özelliğini kaldır** **yapılandırma özellikleri** >  > **C++** tarafından ayarlanır. varsayılanını.

**/Zc: inline** belirtilmişse, derleyici c++ 11 gereksinimini, belirtilen tüm işlevlerin `inline` , kullanıldıkları takdirde aynı çeviri biriminde kullanılabilir olması gerektiğini zorunlu kılar. Seçenek belirtilmediğinde, Microsoft derleyicisi hiçbir tanım görünür `inline` olmasa bile, belirtilen işlevleri çağıran uyumlu olmayan koda izin verir. Daha fazla bilgi için bkz. Bölüm 3,2 ve Bölüm 7.1.2 ' de C++ 11 standardı. Bu derleyici seçeneği Visual Studio 2013 güncelleştirme 2 ' de sunulmuştur.

**/Zc: inline** seçeneğini kullanmak için uyumlu olmayan kodu güncelleştirin.

Bu örnek, varsayılan **/Zc: inline-** seçeneği kullanıldığında bir tanım olmadan bir satır içi işlev bildiriminin uyumlu olmayan bir şekilde nasıl derlendiğini ve bağlantılarını gösterir:

```cpp
// example.h
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#pragma once

class Example {
public:
   inline void inline_call(); // declared but not defined inline
   void normal_call();
   Example() {};
};
```

```cpp
// example.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include <stdio.h>
#include "example.h"

void Example::inline_call() {
   printf("inline_call was called.\n");
}

void Example::normal_call() {
   printf("normal_call was called.\n");
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file
}
```

```cpp
// zcinline.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include "example.h"

void main() {
   Example example;
   example.inline_call(); // normal call when definition unavailable
}
```

**/Zc: inline** özelliği etkin olduğunda, derleyici örnek. obj için [](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) satır içi olmayan bir kod gövdesi yaymadığı için `Example::inline_call` aynı kod bir LNK2019 hatasına neden olur. Bu, içinde `main` satır içi olmayan çağrının tanımsız bir dış sembole başvurmasına neden olur.

Bu hatayı çözmek `inline` için, ' ın `Example::inline_call`bildiriminden anahtar sözcüğünü kaldırabilir `Example::inline_call` , tanımı `Example` üstbilgi dosyasına taşıyabilir veya uygulamasını Main. cpp öğesine taşıyabilirsiniz. Sonraki örnek, tanımı, üstbilgiyi içeren herhangi bir çağıranın görünür olduğu üstbilgi dosyasına taşıdır.

```cpp
// example2.h
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#pragma once
#include <stdio.h>

class Example2 {
public:
   inline void inline_call() {
      printf("inline_call was called.\n");
   }
   void normal_call();
   Example2() {};
};
```

```cpp
// example2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void Example2::normal_call() {
   printf("normal_call was called.\n");
   inline_call();
}
```

```cpp
// zcinline2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void main() {
   Example2 example2;
   example2.inline_call(); // normal call when definition unavailable
}
```

Visual C++'teki uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **C/C++** dil > Özellik sayfası ' nı seçin.

1. **Başvurulmayan kodu ve verileri Kaldır** özelliğini değiştirin ve sonra **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)<br/>
