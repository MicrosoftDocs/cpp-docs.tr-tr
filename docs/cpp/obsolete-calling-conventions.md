---
description: 'Daha fazla bilgi: eski çağırma kuralları'
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
ms.openlocfilehash: 0dfbb34215ba79b54d01ce12fe4d543dbe1d6859
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146048"
---
# <a name="obsolete-calling-conventions"></a>Kullanılmayan Çağırma Kuralları

**Microsoft'a Özgü**

**__Pascal**, **__fortran** ve **__syscall** çağırma kuralları artık desteklenmiyor. Desteklenen çağrı kurallarından birini ve uygun bağlayıcı seçeneklerini kullanarak işlevlerini benzebilirsiniz.

\<windows.h> Artık, hedef için uygun çağırma kuralına çeviren WINAPı makrosunu destekler. Daha önce PASCAL veya **__far \_ _PASCAL** kullandığınız WinAPI 'yi kullanın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız değişken geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)
