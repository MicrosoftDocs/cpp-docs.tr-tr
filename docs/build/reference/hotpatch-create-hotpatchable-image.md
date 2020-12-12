---
description: Şu konuda daha fazla bilgi edinin:/hotpatch (düzeltme eki eklenebilir görüntü oluşturma)
title: /hotpatch (Düzeltme Eki Eklenebilen Görüntü Oluşturma)
ms.date: 11/12/2018
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
ms.openlocfilehash: 2fc5fe629afcb1e721943b852c6f92351900ab7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199876"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch (Düzeltme Eki Eklenebilen Görüntü Oluşturma)

Sık yama için bir görüntü hazırlar.

## <a name="syntax"></a>Syntax

```
/hotpatch
```

## <a name="remarks"></a>Açıklamalar

Bir derlemede **/hotpatch** kullanıldığında, derleyici, her işlevin ilk yönergesinin en az iki bayt olmasını sağlar ve bu, sık düzeltme eki uygulama için gereklidir.

Bir görüntünün hotpatch hale getirme hazırlığını tamamlamaya yönelik olarak derlemek için **/hotpatch** kullandıktan sonra, bağlantı için [/functionpadmin (düzeltme eki uygulama oluştur)](functionpadmin-create-hotpatchable-image.md) kullanmanız gerekir. Bir cl.exe çağrısı kullanarak bir görüntüyü derleyip bağladığınızda **/hotpatch** **/FUNCTIONPADMIN**' i belirtir.

Yönergeler ARM mimarisinde her zaman iki bayt veya daha büyük olduğundan ve x64 derlemesi **/hotpatch** belirtildiğinde her zaman kabul edildiğinden, bu hedeflere yönelik derleme yaparken **/hotpatch** belirtmeniz gerekmez; Ancak, bunlar için düzeltme eki uygulanmış görüntüler oluşturmak üzere **/FUNCTIONPADMIN** kullanarak yine de bağlantı oluşturmanız gerekir. **/Hotpatch** derleyici seçeneği yalnızca x86 derlemesini etkiler.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü seçin.

1. **Komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna derleyici seçeneğini ekleyin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
