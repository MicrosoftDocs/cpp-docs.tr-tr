---
title: "Matematik hatası M6108 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- M6108
dev_langs:
- C++
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6db123d9cb96274848a3edd9f845f86f413d8e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6108"></a>Matematik Hatası M6108
kare kökünü  
  
 Kare kökünü işlemi işlenen negatif.  
  
 Program 136 çıkış koduyla sona erer.  
  
> [!NOTE]
>  `sqrt` C çalışma zamanı kitaplığı ve FORTRAN iç işlevi işlevi **SQRT** bu hatayı oluşturmaz. C `sqrt` işlevi bağımsız değişken işlemi gerçekleştirmeden önce denetler ve işlenen negatifse bir hata değeri döndürür. FORTRAN **SQRT** işlevi hatasına neden etki alanı [M6201](../../error-messages/tool-errors/math-error-m6201.md) yerine bu hata.