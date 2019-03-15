---
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
ms.openlocfilehash: 5f7907d659ee3bedc590b88320df03edce005b06
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820513"
---
# <a name="dll-build-a-dll"></a>/DLL (DLL Derleme)

```
/DLL
```

## <a name="remarks"></a>Açıklamalar

/ DLL seçeneği bir DLL ana çıkış dosyası oluşturur. Bir DLL, genellikle başka bir program tarafından kullanılabilecek dışarı aktarmaları içerir. Önerilen Kullanım sırasına göre listelenmiş dışa belirtmek için üç yöntem vardır:

1. [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) kaynak kodunda

1. Bir [dışarı AKTARMALARI](exports.md) .def dosyası deyimi

1. Bir [/dışarı aktarma](export-exports-a-function.md) bağlantı komut belirtimi

Bir program, birden fazla yöntemi kullanabilirsiniz.

Bir DLL yapılandırmak için başka bir yöntem, **Kitaplığı** modül-tanımlama bildirimi. / Base ve/dll seçenekleri eşdeğer birbirine **Kitaplığı** deyimi.

Geliştirme ortamındaki bu seçeneği belirtmeyin; Bu seçenek, yalnızca komut satırı kullanımı için geçerlidir. Bir uygulama Sihirbazı ile bir DLL projesi oluşturduğunuzda, bu seçeneği ayarlanır.

Başlangıç bir adımda, .dll oluşturmadan önce içeri aktarma kitaplığını oluşturursanız, içeri aktarma kitaplığı derlerken geçti olarak, aynı nesne dosyaları kümesini .dll oluştururken geçmesi gerektiğini unutmayın.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **yapılandırma özellikleri** klasör.

1. Tıklayın **genel** özellik sayfası.

1. Değiştirme **yapılandırma türü** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
