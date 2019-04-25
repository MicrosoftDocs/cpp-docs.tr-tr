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
ms.openlocfilehash: bd9976e434441d2480386ee6fa3d0315fd8d2ef5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295157"
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (DLL Bağlamayı Önle)

```
/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Açıklamalar

/ALLOWBIND:No görüntü bağlanması için izin verilmiyor Bind.exe'yi gösteren DLL üst bilgisinde bir bit ayarlar. Bir DLL dijital olarak imzalanmışsa bağlı olmasını istemeyebilirsiniz (bağlama imzayı).

Mevcut bir DLL ile /ALLOWBIND işlevselliği için düzenleyebilirsiniz [/ALLOWBIND](allowbind.md) yardımcı programının EDITBIN seçeneği.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri**, **bağlayıcı**seçip **komut satırı**.

1. Girin `/ALLOWBIND:NO` içine **ek seçenekler**.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)<br/>
[BindImage işlevi](/windows/desktop/api/imagehlp/nf-imagehlp-bindimage)<br/>
[BindImageEx işlevi](/windows/desktop/api/imagehlp/nf-imagehlp-bindimageex)
