---
title: -hotpatch (düzeltme eki eklenebilen görüntü oluşturma) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
dev_langs:
- C++
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97e1b6197ea60099457db7788ad7e24b96c9fcb8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716982"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch (Düzeltme Eki Eklenebilen Görüntü Oluşturma)

Görüntüyü Yeniden başlatmasız düzeltme için hazırlar.

## <a name="syntax"></a>Sözdizimi

```
/hotpatch
```

## <a name="remarks"></a>Açıklamalar

Zaman **/hotpatch** kullanılan bir derleme içinde derleyici Yeniden başlatmasız düzeltme için gerekli olan her işlevin ilk yönergesinin en az iki bayt olmasını sağlar.

Kullandıktan sonra için bir resmi düzeltme eki eklenebilir hale getirme hazırlığını tamamlamak için **/hotpatch** derlemek için kullanmanız gerekir [/FUNCTIONPADMIN (düzeltme eki eklenebilen görüntü oluşturma)](../../build/reference/functionpadmin-create-hotpatchable-image.md) bağlamak için. Derleme ve görüntü cl.exe, bir çağrı kullanılarak bağlantı **/hotpatch** gelir **/functionpadmin**.

Yönergeleri her zaman iki bayt olduğundan ARM mimarisi, daha büyük ve çünkü derleme her zaman kabul x64 gibi **/hotpatch** belirtilmiş belirtmek zorunda değilsiniz **/hotpatch** olduğunda Bu hedefler için derleme; Bununla birlikte, yine de kullanarak bağlamanız gerekir **/functionpadmin** kendileri için düzeltme eki eklenebilen görüntü oluşturma. **/Hotpatch** derleyici seçeneği yalnızca etkiler x86 derleme.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **C/C++** klasör.

1. Seçin **komut satırı** özellik sayfası.

1. Derleyici seçeneğini ekleyin **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="guidance"></a>Kılavuz

Güncelleştirme yönetimi hakkında daha fazla bilgi için bkz: "Güncelleme yönetimi için Güvenlik Kılavuzu" [ http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx ](http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx).

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)