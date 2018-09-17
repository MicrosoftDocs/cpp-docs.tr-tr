---
title: -homeparams (kayıt parametrelerini yığına Kopyala) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /homeparams
dev_langs:
- C++
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6c51c5e6062f4d7b793e3adb6e9f22e03a65c11
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699848"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (Kayıt Parametrelerini Yığına Kopyala)

Yazmaçlarında işlev girişi ile birlikte kendi konumlarına yazılmasını zorlar parametreler geçildi.

## <a name="syntax"></a>Sözdizimi

```
/homeparams
```

## <a name="remarks"></a>Açıklamalar

Bu derleyici seçeneğini yalnızca x64 için olan derleyicileri (yerel ve çapraz derleme).

Parametreleri bir x64 içinde geçirilir, derleme, çağırma kuralları iste stackspace bile kayıtlara geçirilen parametreler için parametreleri. Daha fazla bilgi için [parametre geçirerek](../../build/parameter-passing.md). Ancak, derleme varsayılan olarak, kayıt parametrelerini yığına, parametreler için zaten sağlanan alana yazılmaz. Bu, bir en iyi duruma getirilmiş (sürüm) programınızın hata ayıklama derlemesine zorlaştırır.

Bir yayın yapısı için kullanmak **/homeparams** uygulamanızın hatalarını emin olmak için. **/ homeparams** kayıt parametrelerini yığına açın yüklemek için bir döngü gerektiğinden bir performans olumsuz anlamına gelmez.

Hata ayıklama yapısında, her zaman kayıtlara geçirilen parametreleri yığına doldurulur.

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