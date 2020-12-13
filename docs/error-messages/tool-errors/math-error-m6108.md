---
description: 'Daha fazla bilgi edinin: matematik hatası M6108'
title: Matematik Hatası M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: 1a0acf13bd166e499334cb13de33093c2c804f5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143890"
---
# <a name="math-error-m6108"></a>Matematik Hatası M6108

kare kök

Kare kök işlemindeki işlenen negatif idi.

Program 136 çıkış koduyla sona eriyor.

> [!NOTE]
> `sqrt`C çalışma zamanı kitaplığı ve FORTRAN iç Işlev **sqrt** içindeki işlev bu hatayı oluşturmaz. C `sqrt` işlevi, işlemi gerçekleştirmeden önce bağımsız değişkeni denetler ve işlenen negatifse bir hata değeri döndürür. FORTRAN **sqrt** işlevi, bu hata yerıne [M6201](../../error-messages/tool-errors/math-error-m6201.md) etki alanı hatasını oluşturur.
