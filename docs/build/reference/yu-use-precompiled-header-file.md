---
title: /Yu (Önceden derlenmiş başlık dosyasını kullanma)
ms.date: 07/31/2020
f1_keywords:
- /Yu
helpviewer_keywords:
- Yu compiler option [C++]
- /Yu compiler option [C++]
- -Yu compiler option [C++]
- PCH files, use existing
- .pch files, use existing
- precompiled header files, use existing
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
ms.openlocfilehash: 8cccce39949f23e4ceb72807ecaef3597ab733c4
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520475"
---
# <a name="yu-use-precompiled-header-file"></a>`/Yu`(Önceden derlenmiş üst bilgi dosyası kullan)

Derleyiciye geçerli derlemede varolan önceden derlenmiş üst bilgi ( *`.pch`* ) dosyasını kullanmasını söyler.

## <a name="syntax"></a>Syntax

> **`/Yu`**\[*dosya adı*]

## <a name="arguments"></a>Arguments

*filename*<br/>
Bir Önişlemci yönergesi kullanılarak kaynak dosyada bulunan bir üst bilgi dosyasının adı `#include` .

## <a name="remarks"></a>Açıklamalar

Ekleme dosyasının adı, **`/Yc`** ön derlenmiş üstbilgiyi oluşturan ve **`/Yu`** önceden derlenmiş üstbilginin kullanımını belirten sonraki bir seçenek için aynı olmalıdır.

İçin **`/Yc`** *dosya adı* , ön derlemenin durdurduğu noktayı belirtir; derleyici *dosya adında* tüm kodu önceden derler ve ekleme dosyasının temel adını ve bir uzantısını kullanarak elde edilen ön derlenmiş üst bilgiyi adlandırır *`.pch`* .

*`.pch`* Dosyanın kullanılarak oluşturulmuş olması gerekir **`/Yc`** .

Derleyici. h dosyasından önce oluşan tüm kodu önceden derlenmiş olarak değerlendirir. Yalnızca `#include` dosyayla ilişkili yönergenin ötesine atlar *`.h`* , dosyasında bulunan kodu kullanır *`.pch`* ve sonra tüm kodu dosya *adı*sonra derler.

Komut satırında, **`/Yu`** ve *dosya adı*arasında boşluk yapılmasına izin verilmez.

**`/Yu`** Bir dosya adı olmadan seçeneği belirttiğinizde, kaynak programınızın [`#pragma hdrstop`](../../preprocessor/hdrstop.md) ön derlenmiş üstbilginin dosya adını belirten bir pragma içermesi gerekir *`.pch`* . Bu durumda, derleyici tarafından adlandırılan önceden derlenmiş üstbilgiyi ( *`.pch`* dosya) kullanır [`/Fp (Name .pch file)`](fp-name-dot-pch-file.md) . Derleyici, bu pragma 'un konumunu atlar ve derlenen durumu belirtilen ön derlenmiş üstbilgi dosyasından geri yükler. Sonra yalnızca pragma 'u izleyen kodu derler. `#pragma hdrstop`Bir dosya adı belirtmezse, derleyici kaynak dosyanın temel adından türetilmiş bir ada sahip bir dosya arar *`.pch`* . Ayrıca, **`/Fp`** seçeneğini farklı bir dosya belirtmek için de kullanabilirsiniz *`.pch`* .

**`/Yu`** Bir dosya adı olmadan seçeneğini belirtirseniz ve bir pragma belirtmeksizin `hdrstop` , bir hata iletisi oluşturulur ve derleme başarısız olur.

Dosya adı **`/Yc`** _filename_ ve **`/Yu`** _Dosya_ adı seçenekleri aynı komut satırında gerçekleşse ve her ikisi de aynı dosya adına başvuru yaptıysanız, **`/Yc`** _dosya adı_ öncelik kazanır, adlandırılmış dosya dahil olmak üzere tüm kodun ön derlemesini önder. Bu özellik, makefiles 'ın yazılmasını basitleştirir.

*`.pch`* Dosyalar makine ortamı ve programla ilgili bellek adres bilgileri hakkında bilgi içerdiğinden, yalnızca *`.pch`* oluşturulduğu makinede bir dosya kullanmanız gerekir.

Önceden derlenmiş üstbilgiler hakkında daha fazla bilgi için bkz.

- [`/Y`(Önceden derlenmiş üst bilgiler)](y-precompiled-headers.md)

- [Önceden derlenmiş üst bilgi dosyaları](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenizdeki bir. cpp dosyasında [ `/Yc` (önceden derlenmiş üst bilgi dosyası oluştur)](yc-create-precompiled-header-file.md) öğesini belirtin.

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **ön derlenmiş üstbilgileri** özellik sayfasını seçin.

1. **Ön derlenmiş üstbilgi** özelliğini, **Dosya aracılığıyla PCH oluştur/kullan** özelliğini veya **önceden derlenmiş üst bilgi oluştur/kullan** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A> . ve.

## <a name="example"></a>Örnek

Aşağıdaki kod varsa:

```cpp
#include <afxwin.h>   // Include header for class library
#include "resource.h" // Include resource definitions
#include "myapp.h"    // Include information specific to this app
...
```

komut satırı kullanılarak derlenirse `CL /YuMYAPP.H PROG.CPP` , derleyici üç içerme deyimini işlemez. Bunun yerine, ' den önceden derlenmiş kod kullanır ve bu, her *`MYAPP.pch`* üç dosyanın (ve içerdikleri tüm dosyaların) ön işleme dahil olduğu süreyi kaydeder.

[`/Fp (Name .pch file)`](fp-name-dot-pch-file.md) **`/Yu`** *`.pch`* Aşağıdaki örnekte olduğu gibi, ad *dosya adı* bağımsız değişkeninden **`/Yc`** veya kaynak dosyanın temel adına farklıysa, dosyanın adını belirtmek için seçeneğini kullanabilirsiniz:

```cmd
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP
```

Bu komut, adlı önceden derlenmiş bir üst bilgi dosyasını belirtir *`MYPCH.pch`* . Derleyici, tüm üstbilgi dosyalarının önceden derlenmiş durumunu ve dahil olmak üzere geri yüklemek için içeriğini kullanır *`MYAPP.h`* . Daha sonra derleyici, * yönergeden sonra oluşan kodu derler `#include "MYAPP.h"` .

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)
