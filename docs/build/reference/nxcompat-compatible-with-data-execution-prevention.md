---
title: "/ NXCOMPAT (Veri Yürütme Engellemesi uyumlu) | Microsoft Docs"
ms.custom: 
ms.date: 12/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /NXCOMPAT
dev_langs:
- C++
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4669c24c3e15fc82f4ba81c83b8892ed18c24a5e
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (Veri Yürütme Önlemesi ile Uyumlu)

Bir yürütülebilir dosya Windows Veri Yürütme Engellemesi özelliği ile uyumlu olup olmadığını gösterir.

## <a name="syntax"></a>Sözdizimi

> **/ NXCOMPAT**[**: HAYIR**]

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **/NXCOMPAT** açıktır.

**/NXCOMPAT:No** açıkça Veri Yürütme Engellemesi uyumlu olarak yürütülebilir bir dosya belirtmek için kullanılır.

Veri Yürütme Engellemesi hakkında daha fazla bilgi için bu makalelere bakın:

- [Veri Yürütme Engellemesi (DEP) özelliğinin ayrıntılı bir açıklaması](http://go.microsoft.com/fwlink/p/?linkid=157771)

- [Veri Yürütme Engellemesi](http://go.microsoft.com/fwlink/p/?linkid=157770)

- [Veri Yürütme Engellemesi (Windows Embedded)](http://go.microsoft.com/fwlink/p/?linkid=157768)

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneği ayarlamak için

1. Projeyi açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Seçenek girin **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** değişikliği uygulamak için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)  
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)  
