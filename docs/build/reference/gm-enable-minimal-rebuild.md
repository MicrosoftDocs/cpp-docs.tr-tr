---
title: -Gm (en az yeniden etkinleştirme) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.MinimalRebuild
- /Gm
- /FD
- VC.Project.VCCLWCECompilerTool.MinimalRebuild
dev_langs:
- C++
helpviewer_keywords:
- /Gm compiler option [C++]
- minimal rebuild
- enable minimal rebuild compiler option [C++]
- Gm compiler option [C++]
- -Gm compiler option [C++]
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f18881e79a3f82941f04dccbde210b2c62dcbca
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725770"
---
# <a name="gm-enable-minimal-rebuild"></a>/Gm (En Az Yeniden Derlemeyi Etkinleştir)

Değiştirilmiş C++ sınıf tanımlarını (Üstbilgi (.h) dosyalarında depolanan) içeren C++ kaynak dosyalarının derlenmesi gerekip gerekmediğini belirler. en az yeniden derlemeyi etkinleştirir.

## <a name="syntax"></a>Sözdizimi

```
/Gm
```

## <a name="remarks"></a>Açıklamalar

Derleyici, sınıf tanımları ve kaynak dosyaları arasındaki bağımlılık bilgileri ilk derleme sırasında projenin .idb dosyasında depolar. (Bağımlılık bilgileri hangi kaynak dosyası hangi sınıf tanımını temel bağımlı olduğunu bildirir ve hangi .h dosya tanımı içinde yer alır.) Sonraki derler .idb dosyasında depolanan bilgileri değiştirilmiş .h dosyası içerse bile bir kaynak dosyası derlenecek gerekip gerekmediğini belirlemek için kullanın.

> [!NOTE]
>  En az yeniden derleme sınıfı kullanır tanımları arasında değiştirme olmayan dosyaları içerir. Sınıf tanımları (bulunmamalıdır belirli bir sınıfın sadece bir tanım) bir proje için genel olmalıdır .idb dosyasındaki bağımlılık bilgileri için tüm proje oluşturulduğundan. Projenizdeki bir sınıf için birden fazla tanıma sahip en az yeniden derlemeyi devre dışı bırakın.

Artımlı bağlayıcı kullanılarak .obj dosyalarında dahil Windows meta verileri desteklemediğinden [/ZW (Windows çalışma zamanı derlemesi)](../../build/reference/zw-windows-runtime-compilation.md) seçeneği **/GM derlemeyi** seçeneği ile uyumlu  **/ZW**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **kod oluşturma** özellik sayfası.

1. Değiştirme **en az yeniden derlemeyi etkinleştir** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)