---
description: Daha fazla bilgi edinin:/ıNCLUDE (simge başvurularını zorla)
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
ms.openlocfilehash: 4938f5e92f91718f522df103303e6382005d463c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191309"
---
# <a name="include-force-symbol-references"></a>/INCLUDE (Simge Başvurularını Zorla)

```
/INCLUDE:symbol
```

## <a name="parameters"></a>Parametreler

*sembol*<br/>
Sembol tablosuna eklenecek bir simge belirtir.

## <a name="remarks"></a>Açıklamalar

/INCLUDE seçeneği bağlayıcıya sembol tablosuna belirtilen bir sembol eklemesini söyler.

Birden çok sembol belirtmek için, virgül (,), noktalı virgül (;) veya sembol adları arasına boşluk yazın. Komut satırında, her simge için/INCLUDE: `symbol` bir kez belirtin.

Bağlayıcı, `symbol` sembol tanımını içeren nesneyi programa ekleyerek çözümlenir. Bu özellik, başka türlü programa bağlanmayacak bir kitaplık nesnesi eklemek için yararlıdır.

Bu seçenekle bir sembol belirtilmesi, bu sembolün kaldırma işlemini [/OPT: ref](opt-optimizations.md)ile geçersiz kılar.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Giriş** Özellik sayfasına tıklayın.

1. **Zorla sembol başvuruları** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
