---
title: "Derleyici Hatası C3552 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3552
dev_langs: C++
helpviewer_keywords: C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 54526c39a928cc534ba815ef8fda802db85f4020
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3552"></a>Derleyici Hatası C3552
'typename': geç belirtilen dönüş türü, 'auto' içeremez  
  
 Kullanırsanız `auto` anahtar sözcüğü bir işlevin dönüş türü için bir yer tutucu olarak belirtilen geç dönüş türü sağlamanız gerekir. Ancak, başka bir kullanamazsınız `auto` geç belirtilen dönüş türü belirtmek için anahtar sözcüğü. Örneğin, aşağıdaki kod parçası C3552 hata verir.  
  
 `auto myFunction->auto; // C3552`