---
title: -vmb, - vmg (temsil yöntemi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /vmb
- /vmg
dev_langs:
- C++
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a95081dfb417711002039727b04d1916c5fe0a14
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720583"
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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)