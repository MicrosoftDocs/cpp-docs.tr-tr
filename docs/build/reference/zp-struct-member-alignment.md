---
description: Daha fazla bilgi edinin:/Zp (yapı üyesi hizalama)
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
ms.openlocfilehash: b2029ebded53bcae1b44b5cd72bf59494e58ec4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224315"
---
# <a name="zp-struct-member-alignment"></a>/Zp (Yapı Üyesi Hizalama)

Bir yapının üyelerinin belleğe nasıl paketlendiğini denetler ve bir modüldeki tüm yapılar için aynı paketleme türünü belirtir.

## <a name="syntax"></a>Syntax

> **`/Zp`**[**`1`**|**`2`**|**`4`**|**`8`**|**`16`**]

## <a name="remarks"></a>Açıklamalar

**`/ZpN`** Seçeneği derleyiciye her bir yapı üyesini nerede depolayacağını söyler. Derleyici, üyeleri üye türünün boyutundan daha küçük olan veya *N* baytlık bir sınır olan bir sınırın üzerinde birinciden sonra depolar.

Kullanılabilir Paketleme değerleri aşağıdaki tabloda açıklanmıştır:

|/ZP bağımsız değişkeni|Etki|
|-|-|
|1|1 baytlık sınırlardaki yapıları paketler. Aynı **`/Zp`** .|
|2|2 baytlık sınırlardaki yapıları paketler.|
|4|4 baytlık sınırlardaki yapıları paketler.|
|8|8 baytlık sınırlardaki yapıları paketler (x86, ARM ve ARM64 için varsayılan).|
|16| 16 baytlık sınırlardaki yapıları paketler (x64 için varsayılan).|

Belirli hizalama gereksinimleriniz yoksa bu seçeneği kullanmayın.

> [!WARNING]
> Windows SDK ayarlanan C++ üst bilgileri ve **`/Zp8`** dahili olarak paketleme kabul eder. **`/Zp`** Ayar Windows SDK üst bilgileri içinde değiştirilirse bellek bozulması oluşabilir. Üst bilgiler, **`/Zp`** komut satırında ayarladığınız herhangi bir seçenekten etkilenmez.

[`pack`](../../preprocessor/pack.md)Yapı paketleme 'yi denetlemek için de kullanabilirsiniz. Hizalama hakkında daha fazla bilgi için bkz.

- [`align`](../../cpp/align-cpp.md)

- [`alignof` İşlecinde](../../cpp/alignof-operator.md)

- [`__unaligned`](../../cpp/unaligned.md)

- [`/ALIGN` (Bölüm hizalama)](align-section-alignment.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **kod oluşturma** özellik sayfasını seçin.

1. **Struct üye hizalaması** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md) \
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
