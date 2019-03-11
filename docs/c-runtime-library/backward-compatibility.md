---
title: Geriye Dönük Uyumluluk
ms.date: 11/04/2016
f1_keywords:
- c.programs
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
ms.openlocfilehash: f672f0601a9d20a726f90963265d08ec212dedce
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744475"
---
# <a name="backward-compatibility"></a>Geriye Dönük Uyumluluk

Kitaplık OLDNAMES ürün sürümleri arasında uyumluluk için. LIB eski adları için yeni adlarını eşler. Örneğin, `open` eşlendiği `_open`. Açıkça OLDNAMES ile bağlanmanız gerekir. Yalnızca komut satırı seçenekleri aşağıdaki birleşimler ile derlerken LIB:

- `/Zl` (nesne dosya varsayılan kitaplık adını atla) ve `/Ze` (varsayılan: Microsoft uzantıları kullanın)

- `/link` (Bağlayıcı-denetimi) `/NOD` (varsayılan kitaplık arama), ve `/Ze`

Derleyici komut satırı seçenekleri hakkında daha fazla bilgi için bkz. [derleyici başvurusu](../build/reference/compiler-options.md).

## <a name="see-also"></a>Ayrıca bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)
