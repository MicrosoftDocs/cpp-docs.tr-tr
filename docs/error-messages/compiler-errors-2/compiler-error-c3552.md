---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3552'
title: Derleyici hatası C3552
ms.date: 11/04/2016
f1_keywords:
- C3552
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
ms.openlocfilehash: aca1474f53c8ac1a8257b23d0042550b76b3c0e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223262"
---
# <a name="compiler-error-c3552"></a>Derleyici hatası C3552

' TypeName ': bir geç belirtilen dönüş türü ' Auto ' içeremez

**`auto`** Anahtar sözcüğünü bir işlevin dönüş türü için bir yer tutucu olarak kullanırsanız, bir geç belirtilen dönüş türü belirtmeniz gerekir. Ancak, **`auto`** geç belirtilen dönüş türünü belirtmek için başka bir anahtar sözcük kullanamazsınız. Örneğin, aşağıdaki kod parçası hata C3552 verir.

`auto myFunction->auto; // C3552`
