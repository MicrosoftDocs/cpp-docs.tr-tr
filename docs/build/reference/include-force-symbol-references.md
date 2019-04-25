---
title: /INCLUDE (Simge Başvurularını Zorla)
ms.date: 11/04/2016
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
ms.openlocfilehash: 1f7a443e32ed20550e3017c7e6ce70f4adf5137d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269876"
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

Bu seçenekle bir simge belirtme tarafından sembolün kaldırılmasını geçersiz kılmalar [/OPT: ref](opt-optimizations.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **giriş** özellik sayfası.

1. Değiştirme **sembol başvurularını zorla** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
