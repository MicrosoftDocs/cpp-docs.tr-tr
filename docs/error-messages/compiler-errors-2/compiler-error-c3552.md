---
title: Derleyici Hatası C3552
ms.date: 11/04/2016
f1_keywords:
- C3552
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
ms.openlocfilehash: 27c4707097f43266a3be57ad6dc9591ab6f34e97
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441814"
---
# <a name="compiler-error-c3552"></a>Derleyici Hatası C3552

'typename': bir sonradan belirtilen dönüş türü, 'auto' içeremez

Kullanırsanız `auto` anahtar sözcüğü bir işlevin dönüş türü için yer tutucu olarak sonradan belirtilmiş dönüş türü sağlamanız gerekir. Ancak, başka bir kullanamazsınız `auto` sonradan belirtilen dönüş türü belirtmek için anahtar sözcüğü. Örneğin, aşağıdaki kod parçası hatası C3552 verir.

`auto myFunction->auto; // C3552`