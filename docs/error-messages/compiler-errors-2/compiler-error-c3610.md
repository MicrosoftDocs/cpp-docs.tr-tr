---
title: Derleyici Hatası C3610 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3610
dev_langs:
- C++
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b46b3669978ff3735d5a16015ca0a01e65f07ae9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037859"
---
# <a name="compiler-error-c3610"></a>Derleyici Hatası C3610

'valuetype': değer türü olmalıdır 'boxed' yapılmalıdır 'method' yönteminin çağrılabilmesi için önce

Varsayılan olarak, bir değer türü yönetilen yığında değil. .NET çalışma zamanı sınıflardan gibi yöntemleri aramadan önce `Object`, yönetilen yığınla değer türü geçmeniz.

C3610 eski derleyici seçeneği kullanılarak erişilebilir, yalnızca **/clr:oldSyntax**.
