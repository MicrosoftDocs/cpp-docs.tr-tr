---
title: Derleyici hatası C3552
ms.date: 11/04/2016
f1_keywords:
- C3552
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
ms.openlocfilehash: d2d3a60fcd4a26238cd6cf330f47b48c5b3198ad
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230837"
---
# <a name="compiler-error-c3552"></a>Derleyici hatası C3552

' TypeName ': bir geç belirtilen dönüş türü ' Auto ' içeremez

**`auto`** Anahtar sözcüğünü bir işlevin dönüş türü için bir yer tutucu olarak kullanırsanız, bir geç belirtilen dönüş türü belirtmeniz gerekir. Ancak, **`auto`** geç belirtilen dönüş türünü belirtmek için başka bir anahtar sözcük kullanamazsınız. Örneğin, aşağıdaki kod parçası hata C3552 verir.

`auto myFunction->auto; // C3552`
