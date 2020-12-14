---
description: Daha fazla bilgi edinin:/LN (MSIL Modülü Oluştur)
title: /LN (MSIL Modülü Oluştur)
ms.date: 11/04/2016
f1_keywords:
- /LN
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
ms.openlocfilehash: 63b6f47fe6bef24341d3c19a6ad96ac3808e486e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190931"
---
# <a name="ln-create-msil-module"></a>/LN (MSIL Modülü Oluştur)

Bir derleme bildiriminin çıkış dosyasına eklenmemelidir.

## <a name="syntax"></a>Syntax

```
/LN
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **/ln** etkin değildir (çıkış dosyasına bir derleme bildirimi eklenir).

**/Ln** kullanıldığında, [/clr (ortak dil çalışma zamanı derleme)](clr-common-language-runtime-compilation.md) seçeneklerinden biri de kullanılmalıdır.

Bildirimde derleme meta verilerine sahip olmayan yönetilen bir programa modül denir. [/C (bağlama olmadan Derle)](c-compile-without-linking.md) ve **/ln** ile derlerseniz, çıkış dosyasını oluşturmak için bağlayıcı AŞAMASıNDA [/NOASSEMBLY (MSIL Modülü Oluştur)](noassembly-create-a-msil-module.md) seçeneğini belirtin.

Derlemeler oluşturmaya yönelik bileşen tabanlı bir yaklaşım almak istiyorsanız modüller oluşturmak isteyebilirsiniz.  Diğer bir deyişle, türleri yazabilir ve bunları modüller halinde derleyebilirsiniz.  Daha sonra, bir veya daha fazla modülden derleme oluşturabilirsiniz.  Modüllerden derlemeler oluşturma hakkında daha fazla bilgi için, bkz [.. netmodule dosyaları bağlayıcı girişi](netmodule-files-as-linker-input.md) veya [Al.exe (derleme Bağlayıcısı)](/dotnet/framework/tools/al-exe-assembly-linker)olarak.

Modül için varsayılan dosya uzantısı. netmodule 'dir.

Visual Studio 2005 ' den önceki sürümlerde, **/clr: noAssembly** ile bir modül oluşturulmuştur.

MSVC Bağlayıcısı. netmodule dosyalarını girdi olarak kabul eder ve bağlayıcı tarafından üretilen çıkış dosyası, bağlayıcıya giriş yapan. netmodules üzerinde çalışma zamanı bağımlılığı olmayan bir derleme veya. netmodule olur.  Daha fazla bilgi için, bkz [.. netmodule dosyaları bağlayıcı girişi olarak](netmodule-files-as-linker-input.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

- Çıkış dosyasını oluşturmak için bağlayıcı aşamasında [/NOASSEMBLY (MSIL Modülü Oluştur)](noassembly-create-a-msil-module.md) belirtin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bu derleyici seçeneği program aracılığıyla değiştirilemez.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
