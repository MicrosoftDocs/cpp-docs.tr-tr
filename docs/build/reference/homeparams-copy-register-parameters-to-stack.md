---
description: Şu konuda daha fazla bilgi edinin:/homeparams (kayıt parametrelerini yığına Kopyala)
title: /homeparams (Kayıt Parametrelerini Yığına Kopyala)
ms.date: 12/17/2018
f1_keywords:
- /homeparams
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
ms.openlocfilehash: 52145534121831be256c3db2a6ccacdffb30b2c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191478"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (Kayıt Parametrelerini Yığına Kopyala)

Kayıtlarda geçirilen parametreleri, işlev girişi üzerine yığındaki konumlarına de yazılmasına zorlar.

## <a name="syntax"></a>Syntax

> **/homeparams**

## <a name="remarks"></a>Açıklamalar

Bu derleyici seçeneği yalnızca x64 hedef olan yerel ve çapraz derleyiciler içinde kullanılabilir.

X64 çağırma kuralı, Yazmaçlarda geçirilen parametreler için bile tüm parametreler için yığın alanının ayrılmasını gerektirir. Daha fazla bilgi için bkz. [parametre geçirme](../../build/x64-calling-convention.md#parameter-passing). Varsayılan olarak, kayıt parametreleri, sürüm yapılarında bunlar için ayrılan yığın alanına kopyalanmaz. Bu, programınızın en iyi duruma getirilmiş bir yayın derlemesinde hata ayıklamayı zorlaştırır.

Yayın yapıları için, uygulamanızın hatalarını ayıklayabilmeniz için derleyicinin kayıt parametrelerini yığına kopyalamasını zorlamak için **/homeparams** seçeneğini kullanabilirsiniz. **/homeparams** bir performans dezavantajına sahiptir, çünkü Register parametrelerini yığına yüklemek için ek bir bisiklet gerektirir.

Hata ayıklama yapılarında, yığın her zaman Yazmaçlarda geçirilen parametrelerle doldurulur.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** özellik sayfasını açın.

1. **Ek seçenekler** kutusunda derleyici seçeneğini girin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
