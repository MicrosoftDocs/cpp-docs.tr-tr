---
title: Matematik hatası M6108 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6108
dev_langs:
- C++
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4dfeca48aa04ebfbc097649e5c25253166c50dad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33325857"
---
# <a name="math-error-m6108"></a>Matematik Hatası M6108
kare kökünü  
  
 Kare kökünü işlemi işlenen negatif.  
  
 Program 136 çıkış koduyla sona erer.  
  
> [!NOTE]
>  `sqrt` C çalışma zamanı kitaplığı ve FORTRAN iç işlevi işlevi **SQRT** bu hatayı oluşturmaz. C `sqrt` işlevi bağımsız değişken işlemi gerçekleştirmeden önce denetler ve işlenen negatifse bir hata değeri döndürür. FORTRAN **SQRT** işlevi hatasına neden etki alanı [M6201](../../error-messages/tool-errors/math-error-m6201.md) yerine bu hata.