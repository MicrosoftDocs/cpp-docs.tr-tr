---
title: Kullanılmayan çağırma kuralları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __fortran
- __pascal
- __syscall
dev_langs:
- C++
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eec6f8370103ed0256471c009d6e97cc693a1cd7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071347"
---
# <a name="obsolete-calling-conventions"></a>Kullanılmayan Çağırma Kuralları

## <a name="microsoft-specific"></a>Microsoft'a Özgü

**__Pascal**, **__fortran**, ve **__syscall** çağırma kuralları artık desteklenmiyor. Uygun bağlayıcı seçenekleri ve desteklenen çağırma kuralları birini kullanarak işlevlerini taklit edebilir.

\<Windows.h > artık hedef uygun çağırma kuralının izlendiği WINAPI makrosu destekler. Burada daha önce kullandığınız PASCAL WINAPI kullanın veya **__far \__pascal**.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)