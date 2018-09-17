---
title: -Include (simge başvurularını zorla) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
dev_langs:
- C++
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6528f6edc51a2dd01e8f91107827b570a44785de
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715787"
---
# <a name="include-force-symbol-references"></a>/INCLUDE (Simge Başvurularını Zorla)

```
/INCLUDE:symbol
```

## <a name="parameters"></a>Parametreler

*Sembol*<br/>
Sembol tablosuna eklenecek bir sembol belirtir.

## <a name="remarks"></a>Açıklamalar

/ INCLUDE seçeneği bağlayıcıya, belirtilen sembolü sembol tablosuna eklemek için söyler.

Birden çok sembolleri belirtmek için virgül (,), noktalı virgül (;) veya sembol adları arasında bir boşluk yazın. / INCLUDE komut satırında belirtin:`symbol` her simge için bir kez.

Bağlayıcı çözümler `symbol` programa sembol tanımını içeren nesneye ekleyerek. Bu özellik, aksi takdirde program bağlanmamış kitaplık nesnesini dahil etmek için kullanışlıdır.

Bu seçenekle bir simge belirtme tarafından sembolün kaldırılmasını geçersiz kılmalar [/OPT: ref](../../build/reference/opt-optimizations.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **giriş** özellik sayfası.

1. Değiştirme **sembol başvurularını zorla** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)