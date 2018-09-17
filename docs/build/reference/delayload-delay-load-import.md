---
title: -DELAYLOAD (gecikme yükü içe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /delayload
- VC.Project.VCLinkerTool.DelayLoadDLLS
dev_langs:
- C++
helpviewer_keywords:
- DELAYLOAD linker option
- -DELAYLOAD linker option
- /DELAYLOAD linker option
- delayed loading of DLLs, /DELAYLOAD option
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 800b3d7d588d1038ac61cb7c9c4b9f1913bec9d4
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722377"
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (Yükü İçe Aktarmayı Geciktir)

> **/ DELAYLOAD:**_dll adı_

## <a name="parameters"></a>Parametreler

*dll adı*<br/>
Yüklenmesinin ertelenmesini istediğiniz bir DLL'nin adı.

## <a name="remarks"></a>Açıklamalar

/ Delayload seçeneği tarafından belirtilen DLL'yi `dllname` yalnızca ilk çağrıda bir işlev DLL içindeki program tarafından yüklenecek. Daha fazla bilgi için [Delay-Loaded DLL'ler için bağlayıcı desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md). İstediğiniz sayıda DLL'yi belirtmek için gerekli sayıda bu seçeneği kullanabilirsiniz. Programınızın ya da kendi gecikme yük yardımcı işlevinizi uygulayabilirsiniz, Delayimp.lib kullanmanız gerekir.

[/DELAY](../../build/reference/delay-delay-load-import-settings.md) seçeneği, bağlama ve yükleme seçenekleri Gecikmeli yüklenen her DLL için belirtir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

2. İçinde **bağlayıcı** klasörüne **giriş** özellik sayfası.

3. Değiştirme **yüklü DLL'leri Geciktir** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)