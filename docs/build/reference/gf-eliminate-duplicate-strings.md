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
ms.openlocfilehash: 2f2bec446fcec522857b4c05a34311e6c26c9b75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270895"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (Yinelenen Dizeleri Ele)

Yürütme sırasında program görüntüsünde ve bellekte aynı dizelerin tek bir kopyasını oluşturmak derleyiciyi etkinleştirir. Bu adlı bir iyileştirme, *dize havuzu* daha küçük programlar oluşturabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
/GF
```

## <a name="remarks"></a>Açıklamalar

Kullanırsanız **/GF**, işletim sisteminin bellek dizesi kısmı kaydırmaz ve dizeleri geri resim dosyasını okuyabilir.

**/GF** havuzları dizeleri salt okunur. Altında dizelere değiştirmeye çalışırsanız **/GF**, bir uygulama hatası oluşur.

Dize havuzunu ne birden çok arabellekleri için birden çok işaretçi olarak tek bir arabellek için birden çok işaretçi olması düşünülmemiştir sağlar. Aşağıdaki kodda, `s` ve `t` aynı dizesi ile başlatılır. Dize havuzunu bunları aynı belleğe işaret edecek şekilde neden olur:

```
char *s = "This is a character buffer";
char *t = "This is a character buffer";
```

> [!NOTE]
>  [/Zi](z7-zi-zi-debug-information-format.md) seçeneği, Düzenle ve devam et için kullanılan otomatik olarak ayarlar **/GF** seçeneği.

> [!NOTE]
>  **/GF** derleyici seçeneği her benzersiz dize için adreslenebilir bir bölüm oluşturur. Ve varsayılan olarak, bir nesne dosyası en çok 65.536 adreslenebilir bölüm içerebilir. Programınızı birden fazla 65.536 dizelerini içeriyorsa, [/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md) derleyici seçeneği, daha fazla bölüm oluşturmak için.

**/GF** içinde etkisi yoktur olan [/O1](o1-o2-minimize-size-maximize-speed.md) veya **/O2** kullanılır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **kod oluşturma** özellik sayfası.

1. Değiştirme **dize havuzunu etkinleştir** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
