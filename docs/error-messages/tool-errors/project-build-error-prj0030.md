---
title: Proje Derleme Hatası PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: aa1c8539247287f7644742857c3cb7de321a20a2
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811482"
---
# <a name="project-build-error-prj0030"></a>Proje Derleme Hatası PRJ0030

Makro genişletme hatası. Özyineleme aşıldı 32 düzeyleri (makro) $ için değerlendirin.

Özyineleme makroları tarafından bu hataya neden olur. Örneğin, ayarlarsanız **Ara dizin** özelliği (bkz [genel özellik sayfası (Proje)](../../build/reference/general-property-page-project.md)) $(IntDir) için özyineleme olacaktır.

Bu hatayı gidermek için makrolar veya özellikleri tanımlamak için kullanılan makrolar açısından tanımlamaz.