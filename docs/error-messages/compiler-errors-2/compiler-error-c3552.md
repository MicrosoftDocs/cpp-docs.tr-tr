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
ms.openlocfilehash: a5f1453a6175019ad7c90471330d11c77da26134
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3552"></a>Derleyici Hatası C3552
'typename': geç belirtilen dönüş türü, 'auto' içeremez  
  
 Kullanırsanız `auto` anahtar sözcüğü bir işlevin dönüş türü için bir yer tutucu olarak belirtilen geç dönüş türü sağlamanız gerekir. Ancak, başka bir kullanamazsınız `auto` geç belirtilen dönüş türü belirtmek için anahtar sözcüğü. Örneğin, aşağıdaki kod parçası C3552 hata verir.  
  
 `auto myFunction->auto; // C3552`