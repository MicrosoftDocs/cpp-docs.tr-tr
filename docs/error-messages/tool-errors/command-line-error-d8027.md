---
description: 'Hakkında daha fazla bilgi edinin: Command-Line Error D8027'
title: Komut Satırı Hatası D8027
ms.date: 11/04/2016
f1_keywords:
- D8027
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
ms.openlocfilehash: 80d0812571043249616108e99e763b105b527475
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115657"
---
# <a name="command-line-error-d8027"></a>Komut Satırı Hatası D8027

' Component ' yürütülemiyor

Derleyici verilen derleyici bileşenini veya bağlayıcıyı çalıştıramıyor.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Bileşeni yüklemek için yeterli bellek yok. Eğer NMAKE derleyicisini çağırırın, derleyicisini makefile dışında çalıştırın.

1. Geçerli işletim sistemi bileşeni çalıştıramıyor. Yolun işletim sisteminize uygun yürütülebilir dosyaları işaret ettiğini doğrulayın.

1. Bileşen bozuldu. Kurulum programını kullanarak bileşeni dağıtım disklerinden yeniden kopyalayın.

1. Bir seçenek yanlış belirtildi. Örnek:

    ```
    cl /B1 file1.c
    ```
