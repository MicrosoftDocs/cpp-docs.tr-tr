---
title: Proje Derleme Hatası PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: 3675c3796ae37df848e458aa2db665d8c4aa7766
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192516"
---
# <a name="project-build-error-prj0030"></a>Proje Derleme Hatası PRJ0030

Makro genişletme hatası. $ (Makro) için özyineleme sayısını değerlendir 32 düzey.

Bu hata, makrolarınızın özyineleme nedeniyle oluşur. Örneğin, **Ara dizin** özelliğini (bkz. [genel özellik sayfası (proje)](../../build/reference/general-property-page-project.md)) $ (intdir) olarak ayarlarsanız, özyineleme olur.

Bu hatayı çözmek için, makroları veya özellikleri tanımlamak için kullanıldıkları makrolar açısından tanımlamayın.
