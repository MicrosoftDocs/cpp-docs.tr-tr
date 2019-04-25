---
title: /CLRIMAGETYPE (CLR Görüntü Türünü Belirt)
ms.date: 11/04/2016
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
ms.openlocfilehash: b2a6df0f778ba079bffefeeacdad22cb398a529a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272487"
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (CLR Görüntü Türünü Belirt)

CLR imaj türü bağlantılı resim ayarlayın.

## <a name="syntax"></a>Sözdizimi

> **/ CLRIMAGETYPE:**{**IJW**|**SAF**|**GÜVENLİ**|**SAFE32BITPREFERRED**}

## <a name="remarks"></a>Açıklamalar

Bağlayıcı yerel nesneleri kabul eder ve ayrıca kullanılarak derlenen MSIL nesnelerini [/CLR](clr-common-language-runtime-compilation.md). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri, Visual Studio 2015'te kullanım dışı bırakıldı ve Visual Studio 2017'de desteklenmez. Aynı yapı içinde karışık nesneler geçirildiğinde, sonuçta gelen çıktı dosyasının doğrulanabilirliği, varsayılan olarak, giriş modülleri doğrulanabilirliğinin en düşük düzeyine eşit olur. Örneğin, bir doğal görüntü ve karma mod bir görüntü geçirirseniz (kullanılarak derlenmiş **/CLR**), elde edilen görüntü karma modda görüntü olacaktır.

Kullanabileceğiniz **/CLRIMAGETYPE** doğrulanabilirliğini denetler, daha düşük bir düzeyde ihtiyacınız olup olmadığını belirtmek için.

Bir dosyanın CLR görüntü türünü belirleme hakkında daha fazla bilgi için bkz: [/CLRHEADER](clrheader.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **Gelişmiş** özellik sayfası.

1. Değiştirme **CLR imaj türü** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC Bağlayıcı Seçenekleri](linker-options.md)
