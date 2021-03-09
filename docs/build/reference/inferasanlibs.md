---
description: /INFERASANLIBS (çıkartılan Temizleme libs kullanın) bağlayıcı seçeneğini hakkında daha fazla bilgi edinin
title: /INFERASANLIBS (çıkartılan Temizleme libs kullanın)
ms.date: 03/01/2021
f1_keywords:
- /INFERASANLIBS
- /INFERASANLIBS:NO
helpviewer_keywords:
- /INFERASANLIBS [C++]
- address sanitizer [C++] linker option
ms.openlocfilehash: 82337b5b77bab2a9066427662f3fd0956684c636
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470641"
---
# <a name="inferasanlibs-use-inferred-sanitizer-libs"></a>`/INFERASANLIBS` (Çıkartılan Temizleme libs kullanın)

**`/INFERASANLIBS`** Varsayılan Addresstemizleme kitaplıklarına bağlamayı etkinleştirmek veya devre dışı bırakmak için bağlayıcı seçeneğini kullanın. Visual Studio 2019 16,9 itibariyle desteklenen tek Temizleme, [addresstemizleme](../../sanitizers/asan.md)'dir.

## <a name="syntax"></a>Syntax

> **`/INFERASANLIBS`**\[**`:NO`**]

## <a name="remarks"></a>Açıklamalar

**`/INFERASANLIBS`** Bağlayıcı seçeneği, varsayılan [addresstemizleme](../../sanitizers/asan.md) kitaplıklarını mümkün hale getirmenizi sunar. Bu seçenek varsayılan olarak etkindir.

**`/INFERASANLIBS`** Ve **`/INFERASANLIBS:NO`** bağlayıcı seçenekleri, gelişmiş kullanıcılar için destek sunar. Daha fazla bilgi için bkz. [addresstemizleyebilir derleme ve dil başvurusu](../../sanitizers/asan-building.md).

Bu **`/INFERASANLIBS`** seçenek, Visual Studio 2019 sürüm 16,9 ' den başlayarak kullanılabilir.

### <a name="to-set-the-inferasanlibs-linker-option-in-the-visual-studio-development-environment"></a>**`/INFERASANLIBS`** Visual Studio geliştirme ortamındaki bağlayıcı seçeneğini ayarlamak için

1. Projenizin **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** özelliğini değiştirin. Varsayılan kitaplıkları etkinleştirmek için düzenleme kutusuna **/INFERASANLIBS** girin. Varsayılan kitaplıkları devre dışı bırakmak için, bunun yerine **/INFERASANLIBS: No** girin.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)\
[MSVC bağlayıcı seçenekleri](linker-options.md)\
[`/fsanitize` (Temizleyicilerin etkinleştir)](./fsanitize.md)\
[Addresstemizme genel bakış](../../sanitizers/asan.md)\
[Adrestemizleme bilinen sorunlar](../../sanitizers/asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](../../sanitizers/asan-building.md)
