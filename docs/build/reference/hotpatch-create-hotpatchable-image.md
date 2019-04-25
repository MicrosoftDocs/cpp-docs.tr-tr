---
title: /hotpatch (Düzeltme Eki Eklenebilen Görüntü Oluşturma)
ms.date: 11/12/2018
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
ms.openlocfilehash: 8830b26b8fdfc3db2aa5fe31a52e6226fd554946
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291658"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch (Düzeltme Eki Eklenebilen Görüntü Oluşturma)

Görüntüyü Yeniden başlatmasız düzeltme için hazırlar.

## <a name="syntax"></a>Sözdizimi

```
/hotpatch
```

## <a name="remarks"></a>Açıklamalar

Zaman **/hotpatch** kullanılan bir derleme içinde derleyici Yeniden başlatmasız düzeltme için gerekli olan her işlevin ilk yönergesinin en az iki bayt olmasını sağlar.

Kullandıktan sonra için bir resmi düzeltme eki eklenebilir hale getirme hazırlığını tamamlamak için **/hotpatch** derlemek için kullanmanız gerekir [/FUNCTIONPADMIN (düzeltme eki eklenebilen görüntü oluşturma)](functionpadmin-create-hotpatchable-image.md) bağlamak için. Derleme ve görüntü cl.exe, bir çağrı kullanılarak bağlantı **/hotpatch** gelir **/functionpadmin**.

Yönergeleri her zaman iki bayt olduğundan ARM mimarisi, daha büyük ve çünkü derleme her zaman kabul x64 gibi **/hotpatch** belirtilmiş belirtmek zorunda değilsiniz **/hotpatch** olduğunda Bu hedefler için derleme; Bununla birlikte, yine de kullanarak bağlamanız gerekir **/functionpadmin** kendileri için düzeltme eki eklenebilen görüntü oluşturma. **/Hotpatch** derleyici seçeneği yalnızca etkiler x86 derleme.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **C/C++** klasör.

1. Seçin **komut satırı** özellik sayfası.

1. Derleyici seçeneğini ekleyin **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
