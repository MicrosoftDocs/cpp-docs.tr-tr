---
title: /showIncludes (Liste Dosyaları İçerir)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
ms.openlocfilehash: 7be3d93f91133ad1a29e6b4d6d2c50157a3376b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523051"
---
# <a name="showincludes-list-include-files"></a>/showIncludes (Liste Dosyaları İçerir)

Ekleme kodu dosyalarının bir listesini çıkarmak derleyicinin neden olur. İç içe geçmiş içeren dosyaları (dahil dosyalarından içerdiği görüntülenen dosyaları) de bulunur.

## <a name="syntax"></a>Sözdizimi

```
/showIncludes
```

## <a name="remarks"></a>Açıklamalar

İçerme dosyası derlenirken karşılaşıldığında, bir ileti çıktı, örneğin.

```
Note: including file: d:\MyDir\include\stdio.h
```

İç içe geçmiş içeren dosyaları gösterilen bir girinti, her iç içe geçme düzeyi için bir alanı örneğin:

```
Note: including file: d:\temp\1.h
Note: including file:  d:\temp\2.h
```

Bu durumda, `2.h` gelen içinde gelen `1.h`, bu nedenle girinti.

**/Showıncludes** seçeneği yayan için `stderr`değil `stdout`.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **Göster içerir** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)