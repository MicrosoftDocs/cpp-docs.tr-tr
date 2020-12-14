---
description: Daha fazla bilgi edinin:/GY (Function-Level bağlamayı etkinleştir)
title: /Gy (İşlev Düzeyi Bağlamayı Etkinleştir)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
ms.openlocfilehash: 3c4136b25001f7f6d6729b9c6089995d1bcd71bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200136"
---
# <a name="gy-enable-function-level-linking"></a>/Gy (İşlev Düzeyi Bağlamayı Etkinleştir)

Derleyicinin paketlenmiş işlevler (Compts) biçiminde tek tek işlevleri paketetmesine olanak tanır.

## <a name="syntax"></a>Syntax

```
/Gy[-]
```

## <a name="remarks"></a>Açıklamalar

Bağlayıcı, bir DLL veya. exe dosyasında ayrı işlevleri dışlamak veya sıralamak için işlevlerin Compts olarak ayrı paketlenmesi gerekir.

Başvurulmayan paketlenmiş işlevleri. exe dosyasından dışlamak için [/opt (iyileştirmeler)](opt-optimizations.md) bağlayıcı seçeneğini kullanabilirsiniz.

Paketlenmiş işlevleri. exe dosyasında belirli bir sıraya dahil etmek için [/Order (Işlevleri sırayla koy)](order-put-functions-in-order.md) bağlayıcı seçeneğini kullanabilirsiniz.

Satır içi işlevler, çağrı olarak örneklendiğinde her zaman paketlenir (örneğin, ıntıl kapalıysa veya bir işlev adresi alırsanız). Ayrıca, sınıf bildiriminde tanımlanan C++ üye işlevleri otomatik olarak paketlenmiştir; diğer işlevler değildir ve bunları paketlenmiş işlevler olarak derlemek için bu seçeneğin seçilmesi gerekir.

> [!NOTE]
> Düzenle ve devam et için kullanılan [/Zi](z7-zi-zi-debug-information-format.md) seçeneği, **/GY** seçeneğini otomatik olarak ayarlar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Kod oluşturma** Özellik sayfasına tıklayın.

1. **Etkinleştirme Function-Level bağlama** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
