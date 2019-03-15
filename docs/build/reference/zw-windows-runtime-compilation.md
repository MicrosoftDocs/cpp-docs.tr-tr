---
title: /ZW (Windows Çalışma Zamanı Derlemesi)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
ms.openlocfilehash: a16482cf8d21651db9486ab19c347a4ccadf5279
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809437"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (Windows Çalışma Zamanı Derlemesi)

Derler kaynak kodu destekleyen Visual C++ bileşen uzantıları C + +/ CX için evrensel Windows Platformu (UWP) uygulamaları oluşturma.

Kullanırken **/ZW** derlemek için her zaman belirtin **/ehsc** de.

## <a name="syntax"></a>Sözdizimi

```cpp
/ZW /EHsc
/ZW:nostdlib /EHsc
```

## <a name="arguments"></a>Arguments

**nostdlib**<br/>
Bu Platform.winmd Windows.Foundation.winmd ve diğer varsayılan Windows meta veri (.winmd) dosyalarını otomatik olarak bir derlemede yer almaz gösterir. Bunun yerine, kullanmalısınız [/FU (zorlanan adı #using)](fu-name-forced-hash-using-file.md) Windows meta veri dosyaları açıkça belirtmek için derleyici seçeneği.

## <a name="remarks"></a>Açıklamalar

Belirttiğinizde **/ZW** derleyici seçeneği, bu özellikleri destekler:

- Gerekli meta veri dosyaları, ad alanları, veri türleri ve uygulamanız için Windows çalışma zamanı'nda yürütmek için gerekli işlevleri.

- Otomatik başvuru sayımı Windows çalışma zamanı nesneleri ve otomatik bir nesne, başvuru sayısı sıfıra gittiğinde atılıyor.

Artımlı bağlayıcı kullanılarak .obj dosyalarında dahil Windows meta verileri desteklemediğinden **/ZW** seçeneği [/GM derlemeyi (etkinleştirme en az yeniden derlemeyi)](gm-enable-minimal-rebuild.md) seçeneği ile uyumlu **/ZW** .

Daha fazla bilgi için [Visual C++ dil başvurusu](../../cppcx/visual-c-language-reference-c-cx.md).

## <a name="requirements"></a>Gereksinimler

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
