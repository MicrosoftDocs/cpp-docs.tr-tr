---
title: "Kaynak Derleyicisi hatası RC2001 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC2001
dev_langs: C++
helpviewer_keywords: RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 23b853db3cbea89bf9cb1ba43607c312e5264394
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="resource-compiler-error-rc2001"></a>Kaynak Derleyicisi Hatası RC2001
Yeni satır içinde sabiti  
  
 Bir dize sabiti ya da olmadan ikinci satırda bir ters eğik çizgi devam etti (**\\**) veya kapatmak ve çift tırnak işaretleri açmak (**"**).  
  
 Kaynak dosyanın iki satırda olan bir dize sabitine ayırmak için aşağıdakilerden birini yapın:  
  
-   İlk satır bir ters eğik çizgi satır devamlılığı karakteri ile bitmelidir.  
  
-   Çift tırnak işareti ile ilk satırdaki dize kapatın ve başka bir tırnak işaretiyle sonraki satıra dize açın.  
  
 \N, yeni satır karakteri bir dize sabitine katıştırmak için kaçış sırası içeren ilk satırı sona erdirmek yeterli değil.