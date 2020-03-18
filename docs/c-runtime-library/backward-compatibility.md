---
title: Geriye Dönük Uyumluluk
ms.date: 11/04/2016
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
ms.openlocfilehash: 2c2b4570e5e3131911e7f424280f16e9977f047e
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438567"
---
# <a name="backward-compatibility"></a>Geriye Dönük Uyumluluk

Ürün sürümleri arasındaki uyumluluk için, kitaplık OLDNAMES. LıB eski adları yeni adlara eşler. Örneğin, `open` `_open`eşlenir. OLDNAMES ile açıkça bağlantı oluşturmanız gerekir. Yalnızca aşağıdaki komut satırı seçenekleri birleşimleriyle derleme yaptığınızda LIB:

- `/Zl` (varsayılan kitaplık adını nesne dosyasından atla) ve `/Ze` (varsayılan — Microsoft uzantıları kullanın)

- `/link` (bağlayıcı denetimi), `/NOD` (varsayılan kitaplık arama yok) ve `/Ze`

Derleyici komut satırı seçenekleri hakkında daha fazla bilgi için bkz. [derleyici başvurusu](../build/reference/compiler-options.md).

## <a name="see-also"></a>Ayrıca bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)
