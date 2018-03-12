---
title: "/ FUNCTIONPADMIN (düzeltme eki eklenebilen görüntü oluşturma) | Microsoft Docs"
ms.custom: 
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /functionpadmin
dev_langs:
- C++
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c941ec7f0e94ba03979c914ddd26b8bd21237369
ms.sourcegitcommit: eb246547c7c9adc7d7ac4083ef09bf6e54dec914
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (Düzeltme Eki Eklenebilen Görüntü Oluşturma)

Görüntü için anında hazırlar.

## <a name="syntax"></a>Sözdizimi

> **/ FUNCTIONPADMIN**[**:**_alanı_]  

### <a name="arguments"></a>Arguments

*Alanı*<br/>
Her işlev bayt başlangıcını eklemek için doldurma miktarı. X86 üzerinde bu 5 baytını doldurma Varsayılanları ve x64 üzerinde bu 6 bayt varsayılan olarak. Diğer hedeflerde bir değer sağlanmalıdır.

## <a name="remarks"></a>Açıklamalar

Düzeltme eki eklenebilen görüntü üretmek bağlayıcı için sırayla .obj dosyaları ile derlenmiştir gerekir [/hotpatch (düzeltme eki eklenebilen görüntü oluşturma)](../../build/reference/hotpatch-create-hotpatchable-image.md).

Derleme ve cl.exe, tek bir çağrı görüntüyle bağlantı **/hotpatch** gelir **/functionpadmin**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Girin **/FUNCTIONPADMIN** seçeneğini **ek seçenekler**. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
