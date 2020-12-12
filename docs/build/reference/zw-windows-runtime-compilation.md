---
description: Daha fazla bilgi edinin:/ZW (Windows Çalışma Zamanı Derlemesi)
title: /ZW (Windows Çalışma Zamanı Derlemesi)
ms.date: 04/08/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
ms.openlocfilehash: b2c39cdfb3f1d22d12c8d07b1e844c550a7a0e3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273923"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (Windows Çalışma Zamanı Derlemesi)

Evrensel Windows Platformu (UWP) uygulamaları oluşturmak için Microsoft C++ bileşen uzantıları C++/CX ' nı destekleyecek kaynak kodu derler.

Derlemek için **/ZW** kullandığınızda her zaman **/EHsc** ' i de belirtin.

## <a name="syntax"></a>Söz dizimi

```cpp
/ZW /EHsc
/ZW:nostdlib /EHsc
```

## <a name="arguments"></a>Bağımsız değişkenler

**nostdlib**<br/>
Platform. winmd, Windows. Foundation. winmd ve diğer varsayılan Windows meta veri (. winmd) dosyalarının derlemeye otomatik olarak dahil edilmediğini belirtir. Bunun yerine, Windows meta verileri dosyalarını açıkça belirtmek için [/Fu (zorlanan #using dosyası adı)](fu-name-forced-hash-using-file.md) derleyici seçeneğini kullanmanız gerekir.

## <a name="remarks"></a>Açıklamalar

**/ZW** seçeneğini belirttiğinizde, derleyici şu özellikleri destekler:

- Gerekli meta veri dosyaları, ad alanları, veri türleri ve uygulamanızın Windows Çalışma Zamanı yürütülmesi gereken işlevler.

- Otomatik başvuru-Windows Çalışma Zamanı nesnelerinin sayımı ve başvuru sayısı sıfıra gittiğinde otomatik olarak bir nesne atma.

Artımlı bağlayıcı, **/ZW** seçeneği kullanılarak. obj dosyalarında yer alan Windows meta verilerini desteklemediğinden, kullanım dışı olan [/GG (en az yeniden derlemeyi etkinleştir)](gm-enable-minimal-rebuild.md) seçeneği **/ZW** ile uyumsuzdur.

Daha fazla bilgi için [Visual C++ dil başvurusu](../../cppcx/visual-c-language-reference-c-cx.md)' na bakın.

## <a name="requirements"></a>Gereksinimler

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
