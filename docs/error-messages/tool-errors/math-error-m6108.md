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
ms.openlocfilehash: e1624a89b472733b4adb5563c8ba52e0b03dcaa2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048623"
---
# <a name="math-error-m6108"></a>Matematik Hatası M6108

Karekök

Bir kare kökünü işlemi işlenen negatif.

Program çıkış kodu ile 136 sonlandırır.

> [!NOTE]
>  `sqrt` İşlevi C çalışma zamanı kitaplığı ve FORTRAN iç işlevi **SQRT** bu hata oluşturmaz. C `sqrt` işlevi bağımsız değişken işlemi gerçekleştirmeden önce denetler ve işlenen negatif ise, bir hata değeri döndürür. FORTRAN **SQRT** işlevi etki alanı hatasına [M6201](../../error-messages/tool-errors/math-error-m6201.md) yerine bu hata.