---
description: 'Hakkında daha fazla bilgi edinin: proje derleme uyarısı PRJ0049'
title: Proje Derleme Uyarısı PRJ0049
ms.date: 11/04/2016
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
ms.openlocfilehash: 423b2220cdc80408c71f96c65eb078763291ec3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206363"
---
# <a name="project-build-warning-prj0049"></a>Proje Derleme Uyarısı PRJ0049

Başvurulan ' \<Reference> ' hedefi .NET Framework gerektiriyor \<MinFrameworkVersion> ve bu projenin hedef çerçevesinin üzerinde çalışması başarısız olacak

Visual Studio 2008 kullanılarak oluşturulan uygulamalar hedeflenecek .NET Framework sürümünü belirtebilir. Hedeflenen sürümden daha sonraki bir .NET Framework sürümüne bağlı bir derlemeye veya projeye başvuru eklerseniz, bu uyarıyı derleme zamanında alırsınız.

### <a name="to-correct-this-warning"></a>Bu uyarıyı düzeltmek için

1. Aşağıdakilerden birini seçin:

   - Projenin **Özellik sayfaları** iletişim kutusundaki hedeflenen Çerçeveyi, tüm başvurulan derlemelerin ve projelerin en düşük Framework sürümünden daha sonra veya ona eşit olacak şekilde değiştirin. Daha fazla bilgi için bkz. [başvuruları ekleme](../../build/adding-references-in-visual-cpp-projects.md).

   - Hedeflenen çerçeveden daha yeni olan en düşük çerçeve sürümüne sahip derleme veya projeye başvuruyu kaldırın. Bu öğeler, projenin **özellik sayfalarında** bir uyarı simgesiyle işaretlenir.

## <a name="see-also"></a>Ayrıca bkz.

[Proje derleme hataları ve uyarıları (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)
