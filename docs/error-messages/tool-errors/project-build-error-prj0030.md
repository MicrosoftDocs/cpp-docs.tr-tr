---
title: Proje Derleme Hatası PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: 2a6cde4ca48acb9aadfe3109084483dbb554e1e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488081"
---
# <a name="project-build-error-prj0030"></a>Proje Derleme Hatası PRJ0030

Makro genişletme hatası. Özyineleme aşıldı 32 düzeyleri (makro) $ için değerlendirin.

Özyineleme makroları tarafından bu hataya neden olur. Örneğin, ayarlarsanız **Ara dizin** özelliği (bkz [genel özellik sayfası (Proje)](../../ide/general-property-page-project.md)) $(IntDir) için özyineleme olacaktır.

Bu hatayı gidermek için makrolar veya özellikleri tanımlamak için kullanılan makrolar açısından tanımlamaz.