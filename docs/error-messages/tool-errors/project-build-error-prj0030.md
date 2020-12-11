---
description: 'Hakkında daha fazla bilgi edinin: proje derleme hatası PRJ0030'
title: Proje Derleme Hatası PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: a8fdb99e7444383f3634730b3053b00b81661aed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160291"
---
# <a name="project-build-error-prj0030"></a>Proje Derleme Hatası PRJ0030

Makro genişletme hatası. $ (Makro) için özyineleme sayısını değerlendir 32 düzey.

Bu hata, makrolarınızın özyineleme nedeniyle oluşur. Örneğin, **Ara dizin** özelliğini (bkz. [genel özellik sayfası (proje)](../../build/reference/general-property-page-project.md)) $ (intdir) olarak ayarlarsanız, özyineleme olur.

Bu hatayı çözmek için, makroları veya özellikleri tanımlamak için kullanıldıkları makrolar açısından tanımlamayın.
