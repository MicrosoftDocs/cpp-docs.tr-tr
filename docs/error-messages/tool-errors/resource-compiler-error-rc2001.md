---
title: Kaynak Derleyicisi hatası RC2001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2001
dev_langs:
- C++
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ef1fd5d29fc5784ee418a8456cacec37e943b73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-error-rc2001"></a>Kaynak Derleyicisi Hatası RC2001
Yeni satır içinde sabiti  
  
 Bir dize sabiti ya da olmadan ikinci satırda bir ters eğik çizgi devam etti (**\\**) veya kapatmak ve çift tırnak işaretleri açmak (**"**).  
  
 Kaynak dosyanın iki satırda olan bir dize sabitine ayırmak için aşağıdakilerden birini yapın:  
  
-   İlk satır bir ters eğik çizgi satır devamlılığı karakteri ile bitmelidir.  
  
-   Çift tırnak işareti ile ilk satırdaki dize kapatın ve başka bir tırnak işaretiyle sonraki satıra dize açın.  
  
 \N, yeni satır karakteri bir dize sabitine katıştırmak için kaçış sırası içeren ilk satırı sona erdirmek yeterli değil.