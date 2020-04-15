---
title: /GF (Yinelenen Dizeleri Ele)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
ms.openlocfilehash: e0d23004c7b710f51065db52410fbb15b7cca040
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320489"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (Yinelenen Dizeleri Ele)

Derleyicinin yürütme sırasında program görüntüsünde ve bellekte aynı dizeleri tek bir kopyasını oluşturmasını sağlar. Bu, daha küçük programlar oluşturabilen *dize birleştirme* adı verilen bir optimizasyondur.

## <a name="syntax"></a>Sözdizimi

```
/GF
```

## <a name="remarks"></a>Açıklamalar

**/GF**kullanıyorsanız, işletim sistemi belleğin dize kısmını değiştirmez ve dizeleri görüntü dosyasından geri okuyabilir.

**/GF** dizeleri salt okunur olarak biraraya getirin. **/GF**altında dizeleri değiştirmeye çalışırsanız, bir uygulama hatası oluşur.

Dize birleştirme, birden çok arabellek için birden çok işaretçi olarak tasarlanan şeyin tek bir arabelleğe birden çok işaretçi olmasını sağlar. Aşağıdaki kodda `s` ve `t` aynı dize ile başharf. Dize birleştirme, aynı belleğe işaret etmelerine neden olur:

```
char *s = "This is a character buffer";
char *t = "This is a character buffer";
```

> [!NOTE]
> Edit ve Continue için kullanılan [/ZI](z7-zi-zi-debug-information-format.md) seçeneği otomatik olarak **/GF** seçeneğini ayarlar.

> [!NOTE]
> **/GF** derleyicisi seçeneği, her benzersiz dize için adreslenebilir bir bölüm oluşturur. Ve varsayılan olarak, bir nesne dosyası en fazla 65.536 adreslenebilir bölüm içerebilir. Programınız 65.536'dan fazla dize içeriyorsa, daha fazla bölüm oluşturmak için [/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md) derleyici seçeneğini kullanın.

**/O1** veya [/O2](o1-o2-minimize-size-maximize-speed.md) kullanıldığında [/O2](o1-o2-minimize-size-maximize-speed.md) /GF geçerlidir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. **C/C++** klasörünü tıklatın.

1. Kod **Oluşturma** özelliği sayfasını tıklatın.

1. String **Pooling** özelliğini etkinleştir'i değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
