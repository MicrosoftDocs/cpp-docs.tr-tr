---
title: -Zp (yapı üyesi hizalama) | Microsoft Docs
ms.custom: ''
ms.date: 04/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs:
- C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1666da40f748d18c762eae19595692addcdbf78a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380868"
---
# <a name="zp-struct-member-alignment"></a>/Zp (Yapı Üyesi Hizalama)

Bir yapı üyeleri belleğe nasıl paketlenmiş denetler ve tüm yapılar aynı sevk modülde belirtir.

## <a name="syntax"></a>Sözdizimi

> **/ZP**[**1**|**2**|**4**|**8** | **16**]

## <a name="remarks"></a>Açıklamalar

Belirttiğinizde **/Zp**_n_ seçeneği, ilk iki üye türü boyutuna depolandıktan sonra her yapısı üye veya *n*-bayt sınırları (burada *n* 1, 2, 4, 8 ya da 16), hangisi daha küçüktür.

Kullanılabilir paket değerleri aşağıdaki tabloda açıklanmıştır:

|/ZP bağımsız değişken|Efekt|
|-|-|
|1.|1-bayt sınırları yapıları paketleri. Aynı **/Zp**.|
|2|2-bayt sınırları yapıları paketleri.|
|4|4-bayt sınırları yapıları paketleri.|
|8|Paketleri yapıları 8 baytlık sınırlarda (varsayılan).|
|16| Yapıları 16 bayt sınırları paketleri.|

Belirli bir uyum gereksinimlerin sürece bu seçeneği kullanmamanız gerekir.

> [!WARNING]  
> C++ üstbilgi Windows SDK'sındaki varsayın **/Zp8** paket. Bellek Bozulması oluşabilir **/Zp** Windows SDK üst bilgilerinin kullanırken ayarı değiştirildi.

Aynı zamanda [paketi](../../preprocessor/pack.md) denetim yapısı paket için. Hizalama hakkında daha fazla bilgi için bkz.

- [align](../../cpp/align-cpp.md)

- [__alignof İşleci](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [Yapı hizalama örnekleri](../../build/examples-of-structure-alignment.md) (x64 belirli)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **C/C++** > **kod oluşturma** özellik sayfası.

1. Değiştirme **yapı üyesi hizalama** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
- [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
