---
title: Proje Derleme Uyarısı PRJ0049
ms.date: 11/04/2016
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
ms.openlocfilehash: fba3de0be764aa56b56ed22c6a9fde9366295456
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816236"
---
# <a name="project-build-warning-prj0049"></a>Proje Derleme Uyarısı PRJ0049

Başvurulan hedefte '\<başvuru >'.NET Framework gerektirir \<MinFrameworkVersion > ve bu projenin hedef çatısının üzerinde çalıştırılması başarısız oluyor

Visual Studio 2008 kullanılarak oluşturulan uygulamalar, .NET Framework'ün hangi sürümünün hedefledikleri belirtebilirsiniz. Bir derleme veya hedeflenen sürümden daha sonraki .NET Framework sürümünü bağımlı proje başvuru eklerseniz, derleme zamanında bu uyarı alırsınız.

### <a name="to-correct-this-warning"></a>Bu uyarıyı düzeltmek için

1. Aşağıdakilerden birini seçin:

   - Projenin hedef Framework'ü değiştirmek **özellik sayfaları** iletişim kutusunu tüm başvurulan derlemeler ve projelerde en az bir framework sürümüne eşit veya değerinden sonra. Daha fazla bilgi için [başvurularının eklenmesi](../../build/adding-references-in-visual-cpp-projects.md).

   - Derleme veya hedef çatısından daha sonraki bir en az bir framework sürümüne sahip proje başvurusunu kaldırın. Bu öğeler, projenin bir uyarı simgesiyle işaretlenir **özellik sayfaları**.

## <a name="see-also"></a>Ayrıca Bkz.

[Proje Derleme Hataları ve Uyarıları (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)