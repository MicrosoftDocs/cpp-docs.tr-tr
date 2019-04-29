---
title: /Zp (Yapı Üyesi Hizalama)
ms.date: 04/04/2019
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
ms.openlocfilehash: d76cd93c7af4228bff8f73fa3bcbf40fa149b0be
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315917"
---
# <a name="zp-struct-member-alignment"></a>/Zp (Yapı Üyesi Hizalama)

Bir yapının üyelerine belleğe nasıl paketlenir denetler ve tüm yapıları için aynı paket bir modülde belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Zp**[**1**|**2**|**4**|**8**|**16**]

## <a name="remarks"></a>Açıklamalar

**/ZP**_n_ seçeneği derleyici her yapı üyesi depolanacağı konumu söyler. Derleyici, birinci ya da üye türü boyutu daha küçük olan bir sınır üzerinde sonra üyeleri depolar veya *n*-bayt sınırını.

Kullanılabilir paketleme değerleri aşağıdaki tabloda açıklanmıştır:

|/ZP bağımsız değişken|Efekt|
|-|-|
|1.|1 baytlık sınırlardaki yapıları paketler. Aynı **/ZP**.|
|2|2 baytlık sınırlardaki yapıları paketler.|
|4|4 baytlık sınırlardaki yapıları paketler.|
|8|8 baytlık sınırlarda (ARM ve ARM64 x86 varsayılan değer) yapıları paketler.|
|16| 16-baytlık sınırlar (x64 varsayılan değer) üzerinde yapıları paketler.|

Hizalama belirli gereksinimleriniz yoksa bu seçeneği kullanmayın.

> [!WARNING]
> C++ üstbilgi Windows SDK'sındaki ayarlayın ve varsayar **/zp8** dahili olarak paketleme. Bellek Bozulması oluşabilir **/ZP** ayarı içinde Windows SDK'sı üst bilgileri değiştirildi. Üstbilgileri tarafından etkilenmez **/ZP** komut satırında ayarlanan seçeneği.

Ayrıca [paketi](../../preprocessor/pack.md) denetim yapısı paketleme için. Hizalama hakkında daha fazla bilgi için bkz.

- [align](../../cpp/align-cpp.md)

- [__alignof İşleci](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [/ALIGN (Bölüm Hizalama)](align-section-alignment.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **kod oluşturma** özellik sayfası.

1. Değiştirme **yapı üyesi hizalama** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md) \
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
