---
title: Proje derleme hatası PRJ0030 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0030
dev_langs:
- C++
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 964fedd40f577a8b337c4ad0c20ba80d33ed2a23
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099928"
---
# <a name="project-build-error-prj0030"></a>Proje Derleme Hatası PRJ0030

Makro genişletme hatası. Özyineleme aşıldı 32 düzeyleri (makro) $ için değerlendirin.

Özyineleme makroları tarafından bu hataya neden olur. Örneğin, ayarlarsanız **Ara dizin** özelliği (bkz [genel özellik sayfası (Proje)](../../ide/general-property-page-project.md)) $(IntDir) için özyineleme olacaktır.

Bu hatayı gidermek için makrolar veya özellikleri tanımlamak için kullanılan makrolar açısından tanımlamaz.