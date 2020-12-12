---
description: Daha fazla bilgi edinin:/GF (Yinelenen dizeleri ortadan kaldırma)
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
ms.openlocfilehash: 65c8cca610b9e01cf49939c2074a698b00c6e338
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191946"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (Yinelenen Dizeleri Ele)

Derleyicinin, yürütme sırasında program görüntüsünde ve bellekte aynı dizelerin tek bir kopyasını oluşturmasını sağlar. Bu, daha küçük programlar oluşturabileceğiniz *dize havuzu* adlı bir iyileştirmedir.

## <a name="syntax"></a>Syntax

```
/GF
```

## <a name="remarks"></a>Açıklamalar

**/GF** kullanıyorsanız, işletim sistemi belleğin dize bölümünü değiştirmez ve dizeleri görüntü dosyasından geri okuyabilir.

**/GF** dizeleri salt okuma olarak havuzlar. **/GF** altındaki dizeleri değiştirmeye çalışırsanız bir uygulama hatası oluşur.

Dize havuzu oluşturma, birden çok arabelleğe birden çok işaretçi olarak tek bir arabelleğin birden çok işaretçisi olmasını sağlar. Aşağıdaki kodda, `s` ve `t` aynı dize ile başlatılır. Dize havuzu, aynı belleğe işaret etmesine neden olur:

```
char *s = "This is a character buffer";
char *t = "This is a character buffer";
```

> [!NOTE]
> Düzenle ve devam et için kullanılan [/Zi](z7-zi-zi-debug-information-format.md) seçeneği, **/GF** seçeneğini otomatik olarak ayarlar.

> [!NOTE]
> **/GF** derleyici seçeneği, her benzersiz dize için adreslenebilir bir bölüm oluşturur. Varsayılan olarak, bir nesne dosyası en fazla 65.536 adreslenebilir bölüm içerebilir. Programınız 65.536 'den fazla dize içeriyorsa, daha fazla bölüm oluşturmak için [/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md) derleyici seçeneğini kullanın.

[/O1](o1-o2-minimize-size-maximize-speed.md) veya [/O2](o1-o2-minimize-size-maximize-speed.md) kullanıldığında **/GF** geçerli olur.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Kod oluşturma** Özellik sayfasına tıklayın.

1. **Dize havuzunu etkinleştir** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
