---
description: Daha fazla bilgi edinin:/c (bağlama olmadan Derle)
title: /c (Bağlamadan Derle)
ms.date: 11/04/2016
f1_keywords:
- /c
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
ms.openlocfilehash: b9dd692dd99cddf63015fe26e37dc54841816f7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179375"
---
# <a name="c-compile-without-linking"></a>/c (Bağlamadan Derle)

Otomatik olarak BAĞLANTıYA izin vermez.

## <a name="syntax"></a>Syntax

```
/c
```

## <a name="remarks"></a>Açıklamalar

**/C** ile derleme yalnızca. obj dosyaları oluşturur. Yapılandırmanın bağlama aşamasını gerçekleştirmek için, uygun dosya ve seçeneklerle bağlantıyı açıkça çağırmanız gerekir.

Geliştirme ortamında oluşturulan herhangi bir iç proje varsayılan olarak **/c** seçeneğini kullanır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

- Bu seçenek geliştirme ortamının içinden kullanılamaz.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bu derleyici seçeneğini program aracılığıyla ayarlamak için, bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A> ..

## <a name="example"></a>Örnek

Aşağıdaki komut satırı Ilk. obj ve ıkıncı. obj nesne dosyalarını oluşturur. ÜÇÜNCÜ. obj yoksayıldı.

```
CL /c FIRST.C SECOND.C THIRD.OBJ
```

Yürütülebilir bir dosya oluşturmak için bağlantıyı çağırmanız gerekir:

```
LINK firsti.obj second.obj third.obj /OUT:filename.exe
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
