---
title: Komut satırı hatası D8027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D8027
dev_langs:
- C++
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8234835d3bb0545c8a72bf35cfb55b2e18bc7da2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070385"
---
# <a name="command-line-error-d8027"></a>Komut Satırı Hatası D8027

'bileşen' yürütülemiyor

Derleyici, bağlayıcı ve belirtilen derleyici bileşeni çalıştırılamadı.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Bileşen yüklemek için yeterli bellek yok. NMAKE derleyici çağrılır, derleyici derleme görevleri dosyası dışında çalıştırın.

1. Geçerli işletim sistemi bileşeni çalıştırılamadı. Yol noktalarını yürütülebilir dosyalar için işletim sisteminize uygun sağlayın.

1. Bileşeni bozulmuş. Dağıtım disklerden Kurulum programını kullanarak bileşeni yeniden kopyalanması.

1. Bir seçenek yanlış belirtildi. Örneğin:

    ```
    cl /B1 file1.c
    ```