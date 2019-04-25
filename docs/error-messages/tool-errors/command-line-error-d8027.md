---
title: Komut Satırı Hatası D8027
ms.date: 11/04/2016
f1_keywords:
- D8027
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
ms.openlocfilehash: d3a7908ec9e7e37d83fd7b928cad2ef256313c40
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62214187"
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