---
title: -WX (Bağlayıcı uyarılarını hata olarak) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /WX
dev_langs:
- C++
helpviewer_keywords:
- /WX linker option
- -WX linker option
- WX linker option
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91f73af0c270be4452a4b556d2cb77c0d55bed33
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722598"
---
# <a name="wx-treat-linker-warnings-as-errors"></a>/WX (Bağlayıcı Uyarılarını Hata Olarak İşle)

```
/WX[:NO]
```

## <a name="remarks"></a>Açıklamalar

Wx bağlayıcı bir uyarı oluşturduğunda çıkış dosyası oluşturulmamasını sağlar.

Bu benzer **wx** derleyici için (bkz [/w, /W0, / W1, / w2, / W3, / W4, / W1, / w2, / W3, / W4, /Wall, WD, / we Wo, wv, /WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md) daha fazla bilgi için). Ancak, belirtme **wx** derleme, gelmez için **wx** bağlantı aşaması için de geçerli olur; açıkça belirtmeniz gerekir **wx** her aracı için.

Varsayılan olarak, **wx** etkili değildir. Bağlayıcı uyarılarını hata olarak değerlendirilecek belirtin **wx**. **/WX:No** değil belirtmekle aynı **wx**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)