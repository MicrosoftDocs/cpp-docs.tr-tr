---
title: Proje derleme uyarısı PRJ0049 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 169ba63318f630ac6a63b18d34fd6a7d829f4f90
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110893"
---
# <a name="project-build-warning-prj0049"></a>Proje Derleme Uyarısı PRJ0049

Başvurulan hedefte '\<başvuru >'.NET Framework gerektirir \<MinFrameworkVersion > ve bu projenin hedef çatısının üzerinde çalıştırılması başarısız oluyor

Visual Studio 2008 kullanılarak oluşturulan uygulamalar, .NET Framework'ün hangi sürümünün hedefledikleri belirtebilirsiniz. Bir derleme veya hedeflenen sürümden daha sonraki .NET Framework sürümünü bağımlı proje başvuru eklerseniz, derleme zamanında bu uyarı alırsınız.

### <a name="to-correct-this-warning"></a>Bu uyarıyı düzeltmek için

1. Aşağıdakilerden birini seçin:

   - Projenin hedef Framework'ü değiştirmek **özellik sayfaları** iletişim kutusunu tüm başvurulan derlemeler ve projelerde en az bir framework sürümüne eşit veya değerinden sonra. Daha fazla bilgi için [başvurularının eklenmesi](../../ide/adding-references-in-visual-cpp-projects.md).

   - Derleme veya hedef çatısından daha sonraki bir en az bir framework sürümüne sahip proje başvurusunu kaldırın. Bu öğeler, projenin bir uyarı simgesiyle işaretlenir **özellik sayfaları**.

## <a name="see-also"></a>Ayrıca Bkz.

[Proje Derleme Hataları ve Uyarıları (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)