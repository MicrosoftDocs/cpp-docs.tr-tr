---
description: 'Daha fazla bilgi edinin: kaynak derleyicisi uyarısı RC4005'
title: Kaynak Derleyicisi Uyarısı RC4005
ms.date: 11/04/2016
f1_keywords:
- RC4005
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
ms.openlocfilehash: 138037e48356448550308abee8dc43cd06b9ac06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237133"
---
# <a name="resource-compiler-warning-rc4005"></a>Kaynak Derleyicisi Uyarısı RC4005

' tanımlayıcı ': makro yeniden tanımı

Tanımlayıcı iki kez tanımlanır. Derleyici ikinci makro tanımını kullandı.

Bu uyarı, komut satırında ve bir yönergeyle kodda bir makro tanımlayarak oluşabilir `#define` . Ayrıca, içerme dosyalarından içeri aktarılan makrolardan kaynaklanabilir.

Uyarıyı ortadan kaldırmak için tanımlardan birini kaldırın veya `#undef` ikinci tanımdan önce bir yönerge kullanın.
