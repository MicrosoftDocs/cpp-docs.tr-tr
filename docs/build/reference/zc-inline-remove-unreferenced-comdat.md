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
ms.openlocfilehash: 42791b2e337fb9a9724a165145e757152b8d679d
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518250"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (Başvurulmayan COMDAT'ı kaldırma)

Başvurulmayan verileri veya yalnızca iç bağlantısı olan işlevleri kaldırır. **/Zc: inline**altında, derleyici satır içi veriler veya işlevler içeren çeviri birimlerinin tanımlarını da içermesi gerektiğini belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Zc: satır içi**[ **-** ]

## <a name="remarks"></a>Açıklamalar

**/Zc: inline** belirtildiğinde, derleyici Başvurulmayan COMDAT işlevleri veya verileri için simge bilgilerini yaymaz. Ya da yalnızca iç bağlantısı olan veriler veya işlevler için. Bu iyileştirme, bağlayıcının yayın yapıları içinde veya [/OPT: ref](opt-optimizations.md) bağlayıcı seçeneğini belirttiğinizde bazı işleri basitleştirir. Bu derleyici iyileştirmesi,. obj dosya boyutunu önemli ölçüde azaltabilir ve bağlayıcı hızlarını geliştirir. İyileştirmeleri devre dışı bıraktığınızda derleyici seçeneği etkin değil ([/od](od-disable-debug.md)). Ya da [/GL belirttiğinizde (tüm program iyileştirmesi)](gl-whole-program-optimization.md).

Varsayılan olarak, bu seçenek komut satırı Derlemeleriyle kapalıdır ( **/Zc: inline-** ). [/Permissive-](permissive-standards-conformance.md) seçeneği **/Zc: inline**'ı etkinleştirmez. MSBuild projelerinde, bu seçenek, varsayılan olarak **Evet** olarak ayarlanan **başvurulmayan kodu ve veri özelliğini kaldırmak** >  > **C/C++**  > **Language** **yapılandırma özellikleri** tarafından ayarlanır.

**/Zc: inline** belirtilirse, derleyici, `inline` bildirildiği tüm işlevlerin aynı çeviri biriminde kullanılabilir bir tanımı olması gereken c++ 11 gereksinimini zorlar. Seçenek belirtilmediğinde, Microsoft derleyicisi hiçbir tanım görünmese de `inline` olarak belirtilen işlevleri çağıran uyumlu olmayan koda izin verir. Daha fazla bilgi için bkz. Bölüm 3,2 ve Bölüm 7.1.2 ' de C++ 11 standardı. Bu derleyici seçeneği Visual Studio 2013 güncelleştirme 2 ' de sunulmuştur.

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

int main() {
   Example example;
   example.inline_call(); // normal call when definition unavailable
}
```

**/Zc: inline** etkin olduğunda, derleyici örnek. obj `Example::inline_call` için satır içi olmayan bir kod gövdesi yaymadığı için aynı kod bir [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) hatasına neden olur. Bu, `main` satır içinde olmayan çağrının tanımsız bir dış sembole başvurmasına neden olur.

Bu hatayı çözmek için `Example::inline_call`bildiriminden `inline` anahtar sözcüğünü kaldırabilir, `Example::inline_call` tanımını üst bilgi dosyasına taşıyabilir veya `Example` uygulamasını Main. cpp öğesine taşıyabilirsiniz. Sonraki örnek, tanımı, üstbilgiyi içeren herhangi bir çağıranın görünür olduğu üstbilgi dosyasına taşıdır.

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

int main() {
   Example2 example2;
   example2.inline_call(); // normal call when definition unavailable
}
```

Visual C++'teki uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **C/C++**  > **dil** Özellik sayfası ' nı seçin.

1. **Başvurulmayan kodu ve verileri Kaldır** özelliğini değiştirin ve sonra **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)<br/>
