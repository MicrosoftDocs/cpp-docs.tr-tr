---
description: Daha fazla bilgi edinin:/DLL (DLL derleme)
title: /DLL (DLL Derleme)
ms.date: 11/04/2016
f1_keywords:
- /dll
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
ms.openlocfilehash: 42535fb15762e5c0f1691d5c28029c7368005f87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201410"
---
# <a name="dll-build-a-dll"></a>/DLL (DLL Derleme)

```
/DLL
```

## <a name="remarks"></a>Açıklamalar

/DLL seçeneği, ana çıkış dosyası olarak bir DLL oluşturur. DLL, genellikle başka bir program tarafından kullanılabilen dışarı aktarmaları içerir. ' Nin önerilen kullanım sırasıyla listelenen dışarı aktarmaları belirtmek için üç yöntem vardır:

1. kaynak kodunda [__declspec (dllexport)](../../cpp/dllexport-dllimport.md)

1. . Def dosyasındaki [dışarı aktarmalar](exports.md) deyimleri

1. BAĞLANTı komutunda bir [/Export](export-exports-a-function.md) belirtimi

Bir program birden fazla yöntem kullanabilir.

DLL oluşturmanın başka bir yolu da **kitaplık** Modülü tanım deyimidir. /BASE ve/DLL seçenekleri birlikte **LIBRARY** ifadesiyle eşdeğerdir.

Geliştirme ortamında bu seçeneği belirtmeyin; Bu seçenek yalnızca komut satırında kullanım içindir. Bu seçenek, bir uygulama sihirbazıyla bir DLL projesi oluşturduğunuzda ayarlanır.

İçeri aktarma kitaplığınızı bir ön adımda oluşturursanız,. dll 'nizi oluşturmadan önce, içeri aktarma kitaplığını oluştururken geçirdiğiniz gibi,. dll dosyasını oluştururken aynı nesne dosyaları kümesini geçirmeniz gerekir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** klasörünü tıklatın.

1. **Genel** Özellik sayfasına tıklayın.

1. **Yapılandırma türü** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
