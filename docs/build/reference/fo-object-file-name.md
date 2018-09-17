---
title: -Fo (nesne dosya adı) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
dev_langs:
- C++
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9ab671cbae276796ce89ec12cecbc16334e234e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724273"
---
# <a name="fo-object-file-name"></a>/Fo (Nesne Dosya Adı)

Bir nesne (.obj) dosya adı veya varsayılan yerine kullanılacak dizini belirtir.

## <a name="syntax"></a>Sözdizimi

```
/Fopathname
```

## <a name="remarks"></a>Açıklamalar

Bu seçeneği kullanmazsanız, nesne dosyası taban adı kaynak dosyasını ve .obj uzantısı kullanır. Herhangi bir ad ve istediğiniz uzantı kullanabilirsiniz, ancak önerilen kuralı kullanmaktır. obj.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **Çıkış dosyalarını** özellik sayfası.

1. Değiştirme **nesne dosyası adını** özelliği.  Geliştirme ortamında, nesne dosyası uzantısına sahip olmalıdır. obj.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut satırını THIS.obj varolan bir dizin, \OBJECT, sürücüde b adlı bir nesne dosyası oluşturur

```
CL /FoB:\OBJECT\ THIS.C
```

## <a name="see-also"></a>Ayrıca Bkz.

[Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)
[derleyici seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)