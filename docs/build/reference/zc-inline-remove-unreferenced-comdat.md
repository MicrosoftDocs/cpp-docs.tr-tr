---
title: /Zc:inline (Başvurulmayan COMDAT'ı kaldırma)
ms.date: 03/01/2018
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
ms.openlocfilehash: 6855773c6ec807a7488fa5604ddee7fd43983135
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441242"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (Başvurulmayan COMDAT'ı kaldırma)

Başvurulmayan işlevleri kaldırır veya comdat'ları veya yalnızca iç bağlantıya sahip veri. Zaman **/ZC: inline** belirtilirse, derleyici gerektirir veya satır içi verileri satır içi işlevleri kullanmak çeviri birimleri veri veya işlevler için tanımları de içermelidir.

## <a name="syntax"></a>Sözdizimi

> **/ ZC: inline**[**-**]

## <a name="remarks"></a>Açıklamalar

Zaman **/ZC: inline** belirtilirse, derleyici sembol bilgilerini başvurulmayan COMDAT işlevleri veya veri veya işlevler veya yalnızca iç bağlantıya sahip veri ktıları. Bu iyileştirme, sürüm yapılarında bağlayıcı tarafından gerçekleştirilen işin bir kısmını basitleştirir veya bağlayıcı seçeneği [/OPT: ref](../../build/reference/opt-optimizations.md) belirtilir. Derleyici bu en iyi duruma getirme gerçekleştirdiğinde, önemli ölçüde .obj dosya boyutunu küçültmek ve bağlayıcı hızını artırın. İyileştirmeleri devre dışı bırakıldığında Bu derleyici seçeneğini etkin değil ([/Od](../../build/reference/od-disable-debug.md)) veya [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md) belirtilir.

Varsayılan olarak, bu seçenek kapalıdır (**/Zc:inline-**). [/ Permissive-](permissive-standards-conformance.md) seçeneği sağlamaz **/ZC: inline**.

Varsa **/ZC: inline** belirtilirse, derleyici zorlar bildirilen tüm işlevlerin C ++ 11 gereksinim `inline` kullanılıyorlarsa bir tanımı aynı çeviri biriminde kullanılabilir olması gerekir. Microsoft derleyici bildirilen işlevlerle çağıran uyumlu olmayan kod izin verir, bu seçenek belirtilmediğinde, `inline` bile tanım görülebilir. Daha fazla bilgi için C ++ 11 standardında, 3.2 ve bölümleri 7.1.2 bakın. Bu derleyici seçeneğini Visual Studio 2013 güncelleştirme 2'de kullanıma sunulmuştur.

Kullanılacak **/ZC: inline** seçeneğini güncelleştirme uyumlu olmayan kod.

Bu örnek nasıl uyumlu olmayan bir satır içi işlev bildirimi bir tanımı olmadan hala derler ve ne zaman bağlantıları gösterir. varsayılan **/Zc:inline-** seçeneği kullanıldığında:

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

Zaman **/ZC: inline** etkin, aynı kodu neden bir [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) hata, derleyici bir satır içi olmayan kod gövdesi vermez çünkü `Example::inline_call` example.obj içinde. Bu satır içi olmayan çağrısında neden `main` tanımlanmamış bir dış sembol başvurmak için.

Bu hatayı gidermek için kaldırabilirsiniz `inline` bildirimi from anahtar sözcüğü `Example::inline_call`, tanımını Taşı `Example::inline_call` üstbilgi içine dosya ya da uygulanması taşıma `Example` Main.cpp öğesi içinde. Sonraki örnek, başlık içeren tüm çağırana görünür olduğu üstbilgi dosyasına tanımı taşır.

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

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **dil** özellik sayfası.

1. Değiştirme **başvurulmayan kod ve verileri Kaldır** özelliği ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
