---
title: Matematik Hatası M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: c6bd403437ee5e55eaf4add288995d0e4aa76c3b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361968"
---
# <a name="math-error-m6108"></a>Matematik Hatası M6108

Karekök

Kare kök işlemindeki operand negatifti.

Program çıkış kodu 136 ile sona erer.

> [!NOTE]
> C `sqrt` çalışma zamanı kitaplığındaki işlev ve FORTRAN içsel işlevi **SQRT** bu hatayı oluşturmaz. C `sqrt` işlevi işlemi gerçekleştirmeden önce bağımsız değişkeni denetler ve operand negatifse bir hata değeri döndürür. FORTRAN **SQRT** işlevi, bu hata yerine [M6201](../../error-messages/tool-errors/math-error-m6201.md) etki alanı hatası oluşturur.
