---
title: Önemli hata C1854
ms.date: 11/04/2016
f1_keywords:
- C1854
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
ms.openlocfilehash: feb385161c9bc13d89052b4947174fbdce7a0d00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457388"
---
# <a name="fatal-error-c1854"></a>Önemli hata C1854

> Nesne dosyasındaki Ön derlenmiş üstbilginin oluşturulması sırasında bilgilerin üzerine yazılamaz: '*filename*'

Belirttiğiniz [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](../../build/reference/yu-use-precompiled-header-file.md) seçeneği belirttikten sonra [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) seçeneği aynı dosya için.

Bu sorunu gidermek için genel olarak, yalnızca bir dosya kullanarak derlenmesi için projenizi kümesindeki **/Yc** seçenek ve diğer tüm dosyaları kullanarak derleme **/Yu** seçeneği. Kullanımı hakkında ayrıntılar için **/Yc** seçeneği ve Visual Studio IDE içinde ayarlamak için bkz [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md). Önceden derlenmiş üst bilgileri kullanma hakkında daha fazla bilgi için bkz. [önceden derlenmiş üst bilgi dosyaları oluşturma](../../build/reference/creating-precompiled-header-files.md).
