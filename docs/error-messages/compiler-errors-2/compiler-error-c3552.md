---
title: Derleyici Hatası C3552 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3552
dev_langs:
- C++
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd9f7ae37500e115fa33fa61298cab800c88f9c7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081266"
---
# <a name="compiler-error-c3552"></a>Derleyici Hatası C3552

'typename': bir sonradan belirtilen dönüş türü, 'auto' içeremez

Kullanırsanız `auto` anahtar sözcüğü bir işlevin dönüş türü için yer tutucu olarak sonradan belirtilmiş dönüş türü sağlamanız gerekir. Ancak, başka bir kullanamazsınız `auto` sonradan belirtilen dönüş türü belirtmek için anahtar sözcüğü. Örneğin, aşağıdaki kod parçası hatası C3552 verir.

`auto myFunction->auto; // C3552`