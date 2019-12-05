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
ms.openlocfilehash: 7f059afe02cbbad77920fd8c4a0e6cb7c958e992
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857365"
---
# <a name="obsolete-calling-conventions"></a>Kullanılmayan Çağırma Kuralları

**Microsoft 'a özgü**

**__Pascal**, **__fortran**ve **__syscall** çağırma kuralları artık desteklenmiyor. Desteklenen çağrı kurallarından birini ve uygun bağlayıcı seçeneklerini kullanarak işlevlerini benzebilirsiniz.

\<Windows. h > artık, hedef için uygun çağırma kuralına çeviren WINAPı makrosunu desteklemektedir. Daha önce PASCAL veya **__far \__pascal**kullandığınız WinAPI 'yi kullanın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)