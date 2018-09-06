---
title: -MIDL (MIDL komut satırı seçeneklerini belirt) | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
dev_langs:
- C++
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e513b0397a41a19c9a8088332eb3d1793b6b6647
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894596"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (MIDL Komut Satırı Seçeneklerini Belirt)

MIDL komut satırı seçenekleri için bir yanıt dosyası belirtir

## <a name="syntax"></a>Sözdizimi

> **/ MIDL:\@**<em>dosyası</em>

## <a name="arguments"></a>Arguments

*Dosya*  
İçeren dosyanın adını [MIDL komut satırı seçeneklerini](/windows/desktop/Midl/general-midl-command-line-syntax).

## <a name="remarks"></a>Açıklamalar

TLB dosya bir IDL dosyası dönüştürülmesi için tüm seçenekleri verilmelidir *dosya*; MIDL komut satırı seçenekleri, bağlayıcı'nın komut satırında belirtilemez. /MIDL belirtilmezse, MIDL Derleyici yalnızca IDL dosyası adı ve diğer bir seçenek ile çağrılır.

Bu dosya her satırda bir MIDL komut satırı seçeneği içermelidir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

2. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **katıştırılmış IDL** özellik sayfası.

3. Değiştirme **MIDL komutları** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
[Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
[/ IDLOUT (MIDL çıktı dosyalarının adı)](../../build/reference/idlout-name-midl-output-files.md)   
[/ IGNOREIDL (öznitelikleri Mıdl'ye işleme)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
[/ TLBOUT (adı. TLB dosyası)](../../build/reference/tlbout-name-dot-tlb-file.md)   
[Öznitelikli Program Derleme](../../windows/building-an-attributed-program.md)