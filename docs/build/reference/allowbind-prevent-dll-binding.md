---
title: /ALLOWBIND (DLL Bağlamayı Önle)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.PreventDLLBinding
- /allowbind
helpviewer_keywords:
- /ALLOWBIND linker option
- binding DLLs
- preventing DLL binding
- ALLOWBIND linker option
- -ALLOWBIND linker option
- DLLs [C++], preventing binding
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
ms.openlocfilehash: ffe32a1df1fb85c7ae47b07c1ada6c53b269f5f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667304"
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (DLL Bağlamayı Önle)

```
/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Açıklamalar

/ALLOWBIND:No görüntü bağlanması için izin verilmiyor Bind.exe'yi gösteren DLL üst bilgisinde bir bit ayarlar. Bir DLL dijital olarak imzalanmışsa bağlı olmasını istemeyebilirsiniz (bağlama imzayı).

Mevcut bir DLL ile /ALLOWBIND işlevselliği için düzenleyebilirsiniz [/ALLOWBIND](../../build/reference/allowbind.md) yardımcı programının EDITBIN seçeneği.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri**, **bağlayıcı**seçip **komut satırı**.

1. Girin `/ALLOWBIND:NO` içine **ek seçenekler**.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
[BindImage işlevi](/windows/desktop/api/imagehlp/nf-imagehlp-bindimage)<br/>
[BindImageEx işlevi](/windows/desktop/api/imagehlp/nf-imagehlp-bindimageex)