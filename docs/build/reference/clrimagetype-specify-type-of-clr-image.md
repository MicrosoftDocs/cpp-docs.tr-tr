---
description: Daha fazla bilgi edinin:/CLRIMAGETYPE (CLR görüntü türünü belirt)
title: /CLRIMAGETYPE (CLR Görüntü Türünü Belirt)
ms.date: 05/16/2019
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
ms.openlocfilehash: 7c499eeddcacd674a9dfc2134e059fd8b3b9a6b6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179154"
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (CLR Görüntü Türünü Belirt)

Bağlantılı görüntüde CLR görüntü türünü ayarlayın.

## <a name="syntax"></a>Syntax

> **/Clrimagetype:**{**IJW** | **saf** | **güvenli** | **SAFE32BITPREFERRED**}

## <a name="remarks"></a>Açıklamalar

Bağlayıcı yerel nesneleri ve ayrıca [/clr](clr-common-language-runtime-compilation.md)KULLANıLARAK derlenen MSIL nesnelerini kabul eder. **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ve sonrasında desteklenmez. Aynı derlemede karma nesneler geçirildiğinde, sonuçta elde edilen çıkış dosyasının verifibilirliği, varsayılan olarak, giriş modüllerinin en düşük önem düzeyine eşittir. Örneğin, yerel bir görüntü ve bir karma mod görüntüsü geçirirseniz ( **/clr** kullanılarak derlenir), sonuçta elde edilen görüntü bir karma mod görüntüsü olur.

Gerekirse, daha düşük bir dosya düzeyi belirtmek için **/Clrimagetype** kullanabilirsiniz.

Bir dosyanın CLR görüntü türünü belirleme hakkında daha fazla bilgi için bkz. [/CLRHEADER](clrheader.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** düğümünü genişletin.

1. **Bağlayıcı** düğümünü genişletin.

1. **Gelişmiş** özellik sayfasını seçin.

1. **Clr görüntü türü** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC bağlayıcı seçenekleri](linker-options.md)
