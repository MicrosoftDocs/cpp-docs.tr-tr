---
title: Matematik Hatası M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: d60e9b6284c79828fda1f7af542fcf197f189ad0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451018"
---
# <a name="math-error-m6108"></a>Matematik Hatası M6108

Karekök

Bir kare kökünü işlemi işlenen negatif.

Program çıkış kodu ile 136 sonlandırır.

> [!NOTE]
>  `sqrt` İşlevi C çalışma zamanı kitaplığı ve FORTRAN iç işlevi **SQRT** bu hata oluşturmaz. C `sqrt` işlevi bağımsız değişken işlemi gerçekleştirmeden önce denetler ve işlenen negatif ise, bir hata değeri döndürür. FORTRAN **SQRT** işlevi etki alanı hatasına [M6201](../../error-messages/tool-errors/math-error-m6201.md) yerine bu hata.