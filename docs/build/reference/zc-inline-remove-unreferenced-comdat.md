---
description: "Şu konuda daha fazla bilgi edinin:/Zc: inline (Başvurulmayan COMDAT 'ı Kaldır)"
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
ms.openlocfilehash: f9a3ac488057059d53925b8f505b9a3ad7f6674a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117555"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (Başvurulmayan COMDAT'ı kaldırma)

Başvurulmayan verileri veya yalnızca iç bağlantısı olan işlevleri kaldırır. **/Zc: inline** altında, derleyici satır içi veriler veya işlevler içeren çeviri birimlerinin tanımlarını da içermesi gerektiğini belirtir.

## <a name="syntax"></a>Syntax

> **/Zc: satır içi**[ **-** ]

## <a name="remarks"></a>Açıklamalar

**/Zc: inline** belirtildiğinde, derleyici Başvurulmayan COMDAT işlevleri veya verileri için simge bilgilerini yaymaz. Ya da yalnızca iç bağlantısı olan veriler veya işlevler için. Bu iyileştirme, bağlayıcının yayın yapıları içinde veya [/OPT: ref](opt-optimizations.md) bağlayıcı seçeneğini belirttiğinizde bazı işleri basitleştirir. Bu derleyici iyileştirmesi,. obj dosya boyutunu önemli ölçüde azaltabilir ve bağlayıcı hızlarını geliştirir. İyileştirmeleri devre dışı bıraktığınızda derleyici seçeneği etkin değil ([/od](od-disable-debug.md)). Ya da [/GL belirttiğinizde (tüm program iyileştirmesi)](gl-whole-program-optimization.md).

Varsayılan olarak, bu seçenek komut satırı Derlemeleriyle kapalıdır (**/Zc: inline-**). [/Permissive-](permissive-standards-conformance.md) seçeneği **/Zc: inline**'ı etkinleştirmez. MSBuild projelerinde seçeneği,   >  Varsayılan olarak  >    >  **Evet** olarak ayarlanan,**başvurulmayan kodu ve veri özelliğini kaldırmak** için yapılandırma özellikleri C/C++ dili tarafından ayarlanır.

**/Zc: inline** belirtilmişse, derleyici c++ 11 gereksinimini, belirtilen tüm işlevlerin **`inline`** , kullanıldıkları takdirde aynı çeviri biriminde kullanılabilir olması gerektiğini zorunlu kılar. Seçenek belirtilmediğinde, Microsoft derleyicisi **`inline`** hiçbir tanım görünür olmasa bile, belirtilen işlevleri çağıran uyumlu olmayan koda izin verir. Daha fazla bilgi için bkz. Bölüm 3,2 ve Bölüm 7.1.2 ' de C++ 11 standardı. Bu derleyici seçeneği Visual Studio 2013 güncelleştirme 2 ' de sunulmuştur.

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

**/Zc: inline** özelliği etkin olduğunda, derleyici örnek. obj için satır içi olmayan bir kod gövdesi yaymadığı için aynı kod bir [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) hatasına neden olur `Example::inline_call` . Bu, içinde satır içi olmayan çağrının `main` tanımsız bir dış sembole başvurmasına neden olur.

Bu hatayı çözmek için, ' **`inline`** ın bildiriminden anahtar sözcüğünü kaldırabilir `Example::inline_call` , tanımı `Example::inline_call` üstbilgi dosyasına taşıyabilir veya uygulamasını `Example` Main. cpp öğesine taşıyabilirsiniz. Sonraki örnek, tanımı, üstbilgiyi içeren herhangi bir çağıranın görünür olduğu üstbilgi dosyasına taşıdır.

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

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **dil** özellik sayfasını seçin.

1. **Başvurulmayan kodu ve verileri Kaldır** özelliğini değiştirin ve sonra **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)<br/>
