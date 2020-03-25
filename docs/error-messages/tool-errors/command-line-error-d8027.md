---
title: Komut Satırı Hatası D8027
ms.date: 11/04/2016
f1_keywords:
- D8027
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
ms.openlocfilehash: 42341507dfc2d3da02639dd28ab1265783452388
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196891"
---
# <a name="command-line-error-d8027"></a>Komut Satırı Hatası D8027

' Component ' yürütülemiyor

Derleyici verilen derleyici bileşenini veya bağlayıcıyı çalıştıramıyor.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Bileşeni yüklemek için yeterli bellek yok. Eğer NMAKE derleyicisini çağırırın, derleyicisini makefile dışında çalıştırın.

1. Geçerli işletim sistemi bileşeni çalıştıramıyor. Yolun işletim sisteminize uygun yürütülebilir dosyaları işaret ettiğini doğrulayın.

1. Bileşen bozuldu. Kurulum programını kullanarak bileşeni dağıtım disklerinden yeniden kopyalayın.

1. Bir seçenek yanlış belirtildi. Örneğin:

    ```
    cl /B1 file1.c
    ```
