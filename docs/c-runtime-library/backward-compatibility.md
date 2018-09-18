---
title: Geriye dönük uyumluluk | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3056b90f3c6f0f62158a9b6dcfe145cda9740c6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092199"
---
# <a name="backward-compatibility"></a>Geriye Dönük Uyumluluk

Kitaplık OLDNAMES ürün sürümleri arasında uyumluluk için. LIB eski adları için yeni adlarını eşler. Örneğin, `open` eşlendiği `_open`. Açıkça OLDNAMES ile bağlanmanız gerekir. Yalnızca komut satırı seçenekleri aşağıdaki birleşimler ile derlerken LIB:

- `/Zl` (nesne dosya varsayılan kitaplık adını atla) ve `/Ze` (varsayılan: Microsoft uzantıları kullanın)

- `/link` (Bağlayıcı-denetimi) `/NOD` (varsayılan kitaplık arama), ve `/Ze`

Derleyici komut satırı seçenekleri hakkında daha fazla bilgi için bkz. [derleyici başvurusu](../build/reference/compiler-options.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)