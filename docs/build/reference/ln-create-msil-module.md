---
title: /LN (MSIL Modülü Oluştur)
ms.date: 11/04/2016
f1_keywords:
- /LN
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
ms.openlocfilehash: 18b0e72d50f328afc1f2856f833cec1aa7d46f30
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57813142"
---
# <a name="ln-create-msil-module"></a>/LN (MSIL Modülü Oluştur)

Bir derleme bildirimi çıkış dosyası içine eklenmesi gerektiğini değil belirtir.

## <a name="syntax"></a>Sözdizimi

```
/LN
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **/LN** (bir derleme bildirimi, çıktı dosyasına eklenir) etkin değil.

Zaman **/LN** kullanılan birini [/CLR (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md) seçenekleri de kullanılmalıdır.

Derleme meta verileri bildiriminde yok. yönetilen bir program, bir modül adı verilir. Derleme yaparsanız [/c (derleme olmadan bağlamayı)](c-compile-without-linking.md) ve **/LN**, belirtin [noassembly (MSIL modülü Oluştur)](noassembly-create-a-msil-module.md) çıkış dosyası oluşturmak için bağlayıcı aşamasındadır.

Derlemeleri oluşturmak için bileşen tabanlı bir yaklaşımda göz atmak istiyorsanız modüller oluşturmak isteyebilirsiniz.  Diğer bir deyişle, türleri yazabilir ve bunları modülleri derleyin.  Ardından, bir derleme bir veya daha fazla modüllerden oluşturabilirsiniz.  Derlemeleri modülleri oluşturma hakkında daha fazla bilgi için bkz. [bağlayıcı girişi olarak .netmodule dosyaları](netmodule-files-as-linker-input.md) veya [Al.exe (Assembly Linker)](/dotnet/framework/tools/al-exe-assembly-linker).

Bir modül için varsayılan dosya uzantısı .netmodule'dür.

Visual C++ 2005 önce Visual C++ sürümlerde bir modül oluşturulurken **/clr:noAssembly**.

MSVC bağlayıcı girişi .netmodule dosyaları kabul eder ve bağlayıcı tarafından üretilen çıkış dosyası bir derleme veya .netmodule herhangi bir bağlayıcıya giriş netmodule'leri hiçbir çalışma zamanı bağımlılığa sahip olacaktır.  Daha fazla bilgi için [bağlayıcı girişi olarak .netmodule dosyaları](netmodule-files-as-linker-input.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

- Belirtin [noassembly (MSIL modülü Oluştur)](noassembly-create-a-msil-module.md) çıkış dosyası oluşturmak için bağlayıcı aşamasındadır.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bu derleyici seçeneğini program aracılığıyla değiştirilemez.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
