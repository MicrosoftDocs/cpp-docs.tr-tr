---
description: :/VMB,/VMG (temsil yöntemi) hakkında daha fazla bilgi
title: /vmb, /vmg (Temsil Yöntemi)
ms.date: 11/04/2016
f1_keywords:
- /vmb
- /vmg
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
ms.openlocfilehash: 19d183ef8d1dd152043d7249d907c9d5b48de230
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254292"
---
# <a name="vmb-vmg-representation-method"></a>/vmb, /vmg (Temsil Yöntemi)

Sınıf üyelerine yönelik işaretçileri temsil etmek için derleyicinin kullandığı yöntemi seçin.

Sınıfın bir üyesine yönelik bir işaretçi göndermeden önce her zaman bir sınıf tanımlarsanız, **/VMB** kullanın.

Sınıfı tanımlamadan önce bir sınıfın üyesine yönelik bir işaretçi bildirmek için **/VMG** kullanın. Bu gereksinim, birbirine başvuran iki farklı sınıfta üye tanımlarsanız ortaya çıkabilir. Bu tür karşılıklı başvurulan sınıflar için, tanımlanmadan önce bir sınıfa başvurulmalıdır.

## <a name="syntax"></a>Syntax

```
/vmb
/vmg
```

## <a name="remarks"></a>Açıklamalar

Bir işaretçi temsili belirtmek için kodunuzda [pointers_to_members](../../preprocessor/pointers-to-members.md) veya [Devralma anahtar sözcüklerini](../../cpp/inheritance-keywords.md) de kullanabilirsiniz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
