---
title: Kullanılmayan Çağırma Kuralları
ms.date: 11/04/2016
f1_keywords:
- __fortran
- __pascal
- __syscall
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
ms.openlocfilehash: 156482a395c7dfc8711e273141a09a37ea3e135d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188564"
---
# <a name="obsolete-calling-conventions"></a>Kullanılmayan Çağırma Kuralları

**Microsoft 'a özgü**

**__Pascal**, **__fortran**ve **__syscall** çağırma kuralları artık desteklenmiyor. Desteklenen çağrı kurallarından birini ve uygun bağlayıcı seçeneklerini kullanarak işlevlerini benzebilirsiniz.

\<Windows. h > artık, hedef için uygun çağırma kuralına çeviren WINAPı makrosunu desteklemektedir. Daha önce PASCAL veya **__far \__pascal**kullandığınız WinAPI 'yi kullanın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)
