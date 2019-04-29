---
title: / vmb, - vmg (temsil yöntemi)
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
ms.openlocfilehash: eac41de04ec883e7b5acf26596647f912b0b1d20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316749"
---
# <a name="vmb-vmg-representation-method"></a>/vmb, /vmg (Temsil Yöntemi)

Sınıf üyeleri için işaretçiler temsil etmek için derleyicinin kullandığı yöntemi seçin.

Kullanım **/vmb** sınıfının bir üyesine bir işaretçi bildirimini önce her zaman bir sınıfı tanımlamanız durumunda.

Kullanım **/vmg** sınıfı tanımlamadan önce bir sınıf üyesi için bir işaretçi bildirmek için. Birbirine başvuru iki farklı sınıflardaki üye tanımlarsanız, bu ihtiyacı ortaya çıkabilir. Tanımlanmadan karşılıklı olarak başvurulan tür sınıflar için bir sınıf başvurulmuş olması gerekir.

## <a name="syntax"></a>Sözdizimi

```
/vmb
/vmg
```

## <a name="remarks"></a>Açıklamalar

Ayrıca [pointers_to_members](../../preprocessor/pointers-to-members.md) veya [devralma anahtar sözcükleri](../../cpp/inheritance-keywords.md) kodunuzda bir işaretçi gösterimini belirtin.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
