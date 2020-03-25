---
title: Proje Derleme Uyarısı PRJ0049
ms.date: 11/04/2016
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
ms.openlocfilehash: e857a50215dc7516c0e2ec45a97638c76f40f43b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191762"
---
# <a name="project-build-warning-prj0049"></a>Proje Derleme Uyarısı PRJ0049

Başvurulan '\<Reference > ' hedefi .NET Framework \<MinFrameworkVersion > gerektirir ve bu projenin hedef çerçevesinde çalıştırılamaz

Visual Studio 2008 kullanılarak oluşturulan uygulamalar hedeflenecek .NET Framework sürümünü belirtebilir. Hedeflenen sürümden daha sonraki bir .NET Framework sürümüne bağlı bir derlemeye veya projeye başvuru eklerseniz, bu uyarıyı derleme zamanında alırsınız.

### <a name="to-correct-this-warning"></a>Bu uyarıyı düzeltmek için

1. Aşağıdakilerden birini seçin:

   - Projenin **Özellik sayfaları** iletişim kutusundaki hedeflenen Çerçeveyi, tüm başvurulan derlemelerin ve projelerin en düşük Framework sürümünden daha sonra veya ona eşit olacak şekilde değiştirin. Daha fazla bilgi için bkz. [başvuruları ekleme](../../build/adding-references-in-visual-cpp-projects.md).

   - Hedeflenen çerçeveden daha yeni olan en düşük çerçeve sürümüne sahip derleme veya projeye başvuruyu kaldırın. Bu öğeler, projenin **özellik sayfalarında**bir uyarı simgesiyle işaretlenir.

## <a name="see-also"></a>Ayrıca bkz.

[Proje Derleme Hataları ve Uyarıları (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)
