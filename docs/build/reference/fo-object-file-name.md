---
title: /Fo (Nesne dosyası adı)
description: Visual Studio'da Microsoft C++ /Fo (Nesne dosya adı) derleyicisi seçeneğine başvuru kılavuzu.
ms.date: 04/20/2020
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
ms.openlocfilehash: cd22ba745128fe1df67853d98c1495491b9ca840
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748966"
---
# <a name="fo-object-file-name"></a>/Fo (Nesne Dosya Adı)

Varsayılan yerine kullanılacak*`.obj`* bir nesne ( ) dosya adı veya dizin belirtir.

## <a name="syntax"></a>Sözdizimi

> **`/Fo`**_Yoladı_

## <a name="remarks"></a>Açıklamalar

CL **`/Fo`** derleyici komutu tarafından oluşturulan tüm nesne dosyaları için bir çıktı dizini ayarlamak için derleyici seçeneğini kullanabilirsiniz. Veya, tek bir nesne dosyasını yeniden adlandırmak için kullanabilirsiniz.

Varsayılan olarak, derleyici tarafından oluşturulan nesne dosyaları geçerli dizine yerleştirilir. Onlara kaynak dosyanın temel adı ve *`.obj`* uzantısı verilir.

Nesne dosyasını **`/Fo`** yeniden adlandırma seçeneğini kullanmak için çıktı dosya adını *yol adı* bağımsız değişkeni olarak belirtin. Bir nesne dosyasını yeniden adlandırdığınızda, istediğiniz adı ve uzantıyı kullanabilirsiniz, ancak önerilen kural kuralı . *`.obj`* Derleyici, derlenecek birden fazla kaynak dosya belirttiğiniz **`/Fo`** zaman bir dosya adı belirtirseniz D8036 komut satırı hatası oluşturur.

CL komutu tarafından oluşturulan tüm nesne dosyaları için bir çıktı dizini ayarlamak için **`/Fo`** seçeneği kullanmak için, *dizin yol adı* bağımsız değişkeni olarak belirtin. Dizin, *yol adı* bağımsız değişkeninde bir çizgi ile gösterilir. Belirtilen dizin mevcut olmalıdır; otomatik olarak oluşturulmaz.

## <a name="example"></a>Örnek

Aşağıdaki komut satırı, d sürücüsünde varolan bir dizinde * \\* *sample.obj* adlı bir nesne dosyası oluşturur.

```cmd
CL /Fo"D:\intermediate\" /EHsc /c sample.cpp
```

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>Seçeneği Visual Studio'da veya programlı olarak ayarlama

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. Yapılandırma **Özellikleri** > **C/C++** > **Çıktı Dosyaları** özelliği sayfasını seçin.

1. Çıktı dizini ayarlamak için **Nesne Dosya Adı** özelliğini değiştirin. IDE'de, nesne dosyasının bir *`.obj`* uzantısı olmalıdır.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[Yol Adını Belirtme](specifying-the-pathname.md)
