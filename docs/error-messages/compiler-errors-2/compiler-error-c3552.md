---
title: Derleyici hatası C3552
ms.date: 11/04/2016
f1_keywords:
- C3552
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
ms.openlocfilehash: 567c92ddabbe2517700e4c67ef2c1ba899baada8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200674"
---
# <a name="compiler-error-c3552"></a>Derleyici hatası C3552

' TypeName ': bir geç belirtilen dönüş türü ' Auto ' içeremez

`auto` anahtar sözcüğünü bir işlevin dönüş türü için yer tutucu olarak kullanırsanız, bir geç belirtilen dönüş türü belirtmeniz gerekir. Ancak, geç belirtilen dönüş türünü belirtmek için başka bir `auto` anahtar sözcük kullanamazsınız. Örneğin, aşağıdaki kod parçası hata C3552 verir.

`auto myFunction->auto; // C3552`
