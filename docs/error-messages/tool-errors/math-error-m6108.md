---
title: Matematik Hatası M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: 68e6ae823613d87eb01c443b564b46746259cd7b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173731"
---
# <a name="math-error-m6108"></a>Matematik Hatası M6108

kare kök

Kare kök işlemindeki işlenen negatif idi.

Program 136 çıkış koduyla sona eriyor.

> [!NOTE]
>  C çalışma zamanı kitaplığındaki `sqrt` işlevi ve FORTRAN Intrinsic işlevi **sqrt** bu hatayı oluşturmaz. C `sqrt` işlevi, işlemi gerçekleştirmeden önce bağımsız değişkeni denetler ve işlenen negatifse bir hata değeri döndürür. FORTRAN **sqrt** işlevi, bu hata yerıne [M6201](../../error-messages/tool-errors/math-error-m6201.md) etki alanı hatasını oluşturur.
