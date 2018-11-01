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
ms.openlocfilehash: 6be3b15efb56e97d658edb5890c3bdce4f64fbd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625166"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)