---
title: Proje Derleme Hatası PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: aa1c8539247287f7644742857c3cb7de321a20a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385413"
---
# <a name="project-build-error-prj0030"></a>Proje Derleme Hatası PRJ0030

Makro genişletme hatası. Özyineleme aşıldı 32 düzeyleri (makro) $ için değerlendirin.

Özyineleme makroları tarafından bu hataya neden olur. Örneğin, ayarlarsanız **Ara dizin** özelliği (bkz [genel özellik sayfası (Proje)](../../build/reference/general-property-page-project.md)) $(IntDir) için özyineleme olacaktır.

Bu hatayı gidermek için makrolar veya özellikleri tanımlamak için kullanılan makrolar açısından tanımlamaz.