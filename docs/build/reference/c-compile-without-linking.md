---
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
ms.openlocfilehash: bfe351daf43b913f10df74b1059ba98f7d5d657b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294856"
---
# <a name="c-compile-without-linking"></a>/c (Bağlamadan Derle)

Otomatik bağlantı çağrısı engeller.

## <a name="syntax"></a>Sözdizimi

```
/c
```

## <a name="remarks"></a>Açıklamalar

İle derlerken **/c** yalnızca .obj dosyaları oluşturur. Derleme bağlama aşamasını gerçekleştirmek için seçenekleri ve uygun dosyaları ile bağlantı açıkça çağırmalıdır.

Geliştirme ortamında oluşturulmuş herhangi bir iç projesinin kullanan **/c** varsayılan seçeneği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

- Bu seçenek, geliştirme ortamında kullanılabilir değildir.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bu derleyici seçeneğini program üzerinden ayarlamak için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut satırını FIRST.obj ve SECOND.obj nesne dosyaları oluşturur. THIRD.obj göz ardı edilir.

```
CL /c FIRST.C SECOND.C THIRD.OBJ
```

Yürütülebilir bir dosya oluşturmak için bağlantı çağırmanız gerekir:

```
LINK firsti.obj second.obj third.obj /OUT:filename.exe
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
