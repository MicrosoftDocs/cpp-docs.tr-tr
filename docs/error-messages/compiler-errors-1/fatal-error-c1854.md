---
title: Önemli hata C1854 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: error-reference
f1_keywords:
- C1854
dev_langs:
- C++
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83450169ec928bb77e46916619c84b3b9a3443a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029396"
---
# <a name="fatal-error-c1854"></a>Önemli hata C1854

> Nesne dosyasındaki Ön derlenmiş üstbilginin oluşturulması sırasında bilgilerin üzerine yazılamaz: '*filename*'

Belirttiğiniz [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](../../build/reference/yu-use-precompiled-header-file.md) seçeneği belirttikten sonra [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) seçeneği aynı dosya için.

Bu sorunu gidermek için genel olarak, yalnızca bir dosya kullanarak derlenmesi için projenizi kümesindeki **/Yc** seçenek ve diğer tüm dosyaları kullanarak derleme **/Yu** seçeneği. Kullanımı hakkında ayrıntılar için **/Yc** seçeneği ve Visual Studio IDE içinde ayarlamak için bkz [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md). Önceden derlenmiş üst bilgileri kullanma hakkında daha fazla bilgi için bkz. [önceden derlenmiş üst bilgi dosyaları oluşturma](../../build/reference/creating-precompiled-header-files.md).
