---
title: /Fi (Çıktı Dosyası Adını Önişle)
ms.date: 08/12/2020
f1_keywords:
- /Fi
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
ms.openlocfilehash: 82bf09a8f01f656f90ad9971530b05f108fc95a4
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561095"
---
# <a name="fi-preprocess-output-file-name"></a>`/Fi` (Çıkış dosyası adını Önişle)

[ `/P` (Bir dosyaya ön işleme)](p-preprocess-to-a-file.md) derleyici seçeneğinin önceden işlenmiş çıktıyı yazdığı çıkış dosyasının adını belirtir.

## <a name="syntax"></a>Söz dizimi

> **`/Fi`**_`pathname`_

### <a name="parameters"></a>Parametreler

*`pathname`*\
Derleyici seçeneği tarafından üretilen çıkış dosyasının göreli veya mutlak yolu ve dosya adı **`/P`** . Veya birden *`.i`* fazla giriş dosyası belirtildiğinde çıkış dosyaları için dizin yolu. Seçeneği ile arasında boşluk koymayın **`/Fi`** *`pathname`* .

## <a name="remarks"></a>Açıklamalar

Derleyici seçeneğiyle **`/Fi`** birlikte derleyici seçeneğini kullanın **`/P`** . **`/P`** Belirtilmemişse, **`/Fi`** komut satırı uyarısı D9007 olur.

Parametresi için yalnızca bir dizin yolu (ters eğik çizgi ile biten bir yol **`\`** ) belirtirseniz *`pathname`* , kaynak dosyanın temel adı önceden işlenmiş çıkış dosyasının temel adı olarak kullanılır. *`pathname`* Parametresi belirli bir dosya adı uzantısı gerektirmez. Ancak, bir dosya adı uzantısı belirtmezseniz bir ". i" uzantısı kullanılır.

### <a name="example"></a>Örnek

Aşağıdaki komut satırı önceden işlenir *`PROGRAM.cpp`* , Yorumları korur, yönergeleri ekler [`#line`](../../preprocessor/hash-line-directive-c-cpp.md) ve sonucu *`MYPROCESS.i`* dosyaya yazar:

```cmd
CL /P /FiMYPROCESS.I PROGRAM.CPP
```

Bu komut satırı, *`main.cpp`* *`helper.cpp`* *`main.i`* *`helper.i`* adlı bir alt dizinde ve içinde önceden işlenir *`preprocessed`* :

```cmd
CL /P /Fi".\\preprocessed\\" main.cpp helper.cpp
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Kaynak dosyasını veya projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **Önişlemci** özellik sayfasını seçin.

1. **Ön işlemi bir dosya** özelliğine **Evet**olarak ayarlayın.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **`/Fi`** Derleyici seçeneğini ve *`pathname`* **ek seçenekler** kutusuna girin. Bir proje için bu özelliği ayarlarken yalnızca bir dosya adı değil, bir dizin yolu belirtin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[`/P` (Bir dosyaya ön işlem)](p-preprocess-to-a-file.md)<br/>
[Yol adını belirtme](specifying-the-pathname.md)
