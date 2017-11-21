---
title: "Matematik hatası M6108 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: M6108
dev_langs: C++
helpviewer_keywords: M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6527a595673fddd9fe320097d093858d1c2c0ca1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="math-error-m6108"></a>Matematik Hatası M6108
kare kökünü  
  
 Kare kökünü işlemi işlenen negatif.  
  
 Program 136 çıkış koduyla sona erer.  
  
> [!NOTE]
>  `sqrt` C çalışma zamanı kitaplığı ve FORTRAN iç işlevi işlevi **SQRT** bu hatayı oluşturmaz. C `sqrt` işlevi bağımsız değişken işlemi gerçekleştirmeden önce denetler ve işlenen negatifse bir hata değeri döndürür. FORTRAN **SQRT** işlevi hatasına neden etki alanı [M6201](../../error-messages/tool-errors/math-error-m6201.md) yerine bu hata.