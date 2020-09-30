---
title: Geriye Dönük Uyumluluk
description: Microsoft OLDNAMES ' i kullanma. Geri uyumluluk için işlev adlarını eşlemek üzere LIB kitaplığı.
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
ms.openlocfilehash: b09104a5cff4d8e4cc31f9cc4707e808988401d6
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590296"
---
# <a name="backward-compatibility"></a>Geriye Dönük Uyumluluk

Ürün sürümleri arasındaki uyumluluk için, kitaplık OLDNAMES. LıB eski adları yeni adlara eşler. Örneğin, `open` ile eşlenir `_open` . OLDNAMES ile açıkça bağlantı oluşturmanız gerekir. Yalnızca aşağıdaki komut satırı seçenekleri birleşimleriyle derleme yaptığınızda LIB:

- `/Zl` (varsayılan kitaplık adını nesne dosyasından atla) ve `/Ze` (varsayılan değer: Microsoft uzantıları kullanın)

- `/link` (bağlayıcı-denetim), `/NOD` (varsayılan kitaplık arama yok) ve `/Ze`

Derleyici komut satırı seçenekleri hakkında daha fazla bilgi için bkz. [derleyici başvurusu](../build/reference/compiler-options.md).

## <a name="see-also"></a>Ayrıca bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)
