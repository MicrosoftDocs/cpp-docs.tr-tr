---
title: /Zp (Yapı Üyesi Hizalama)
ms.date: 12/17/2018
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
ms.openlocfilehash: d1821d8dc5eab202a918893a1e7895151629b551
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627533"
---
# <a name="zp-struct-member-alignment"></a>/Zp (Yapı Üyesi Hizalama)

Bir yapının üyelerine belleğe nasıl paketlenir denetler ve tüm yapıları için aynı paket bir modülde belirtir.

## <a name="syntax"></a>Sözdizimi

> **/ZP**[**1**|**2**|**4**|**8** | **16**]

## <a name="remarks"></a>Açıklamalar

Belirttiğinizde **/ZP**_n_ seçeneği, ilk iki üye türü boyutuna depolandıktan sonra her yapı üyesi veya *n*-baytlık sınırlar (burada *n* 1, 2, 4, 8 veya 16 olan), hangisi daha küçükse.

Kullanılabilir paketleme değerleri aşağıdaki tabloda açıklanmıştır:

|/ZP bağımsız değişken|Efekt|
|-|-|
|1.|1 baytlık sınırlardaki yapıları paketler. Aynı **/ZP**.|
|2|2 baytlık sınırlardaki yapıları paketler.|
|4|4 baytlık sınırlardaki yapıları paketler.|
|8|(Varsayılan) 8 baytlık sınırlardaki yapıları paketler.|
|16| 16 baytlık sınırlardaki yapıları paketler.|

Hizalama belirli gereksinimleriniz yoksa bu seçeneği kullanmamanız gerekir.

> [!WARNING]
> Windows SDK'sındaki C++ üstbilgi varsayar **/zp8** paketleme. Bellek Bozulması oluşabilir **/ZP** Windows SDK'sı üst bilgileri kullanırken ayarı değiştirildi.

Ayrıca [paketi](../../preprocessor/pack.md) denetim yapısı paketleme için. Hizalama hakkında daha fazla bilgi için bkz.

- [align](../../cpp/align-cpp.md)

- [__alignof İşleci](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [Yapı hizalama örnekleri](../../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 belirli)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **C/C++** > **kod oluşturma** özellik sayfası.

1. Değiştirme **yapı üyesi hizalama** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleyici Seçenekleri](../../build/reference/compiler-options.md)
- [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
