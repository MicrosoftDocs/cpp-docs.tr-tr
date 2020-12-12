---
description: 'Daha fazla bilgi edinin: Izlenecek yol: projeyi test etme (C++)'
title: 'İzlenecek Yol: Projeyi Test Etme (C++)'
ms.date: 04/25/2019
helpviewer_keywords:
- project testing [C++]
- testing projects
- projects [C++], testing
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
ms.openlocfilehash: 0469f6c161689d2638cfb206c91c2530b72cd00b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334775"
---
# <a name="walkthrough-testing-a-project-c"></a>İzlenecek Yol: Projeyi Test Etme (C++)

Bir programı hata ayıklama modunda çalıştırdığınızda, değişkenlerin ve nesnelerin durumunu incelemek üzere programı duraklatmak için kesme noktaları kullanabilirsiniz.

Bu kılavuzda, program çalıştığı için bir değişkenin değerini izleyebilir ve değerin neden beklediğiniz gibi olmadığını görürsünüz.

## <a name="prerequisites"></a>Önkoşullar

- Bu izlenecek yol, C++ dilinin temellerini anladığınızı varsayar.

- Ayrıca [, C++ masaüstü geliştirme Için Visual STUDIO IDE 'Yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)bölümünde listelenen daha önceki ilgili talimatları tamamlamış olduğunu varsaymaktadır.

### <a name="to-run-a-program-in-debug-mode"></a>Bir programı hata ayıklama modunda çalıştırmak için

1. Düzenlenmek üzere Games. cpp ' i açın.

1. Bu kod satırını seçin:

   `Cardgame solitaire(1);`

1. Bu satırda bir kesme noktası ayarlamak için, menü çubuğunda **Hata Ayıkla**  >  **geçiş noktası geçişi**' ni seçin veya **F9** tuşuna basın. Satırın solunda kırmızı bir daire görünür; bir kesme noktasının ayarlandığını gösterir. Kesme noktasını kaldırmak için menü komutunu veya **F9** tuşunu yeniden seçebilirsiniz.

   Bir fare kullanıyorsanız, sol kenar boşluğuna tıklayarak bir kesme noktası da ayarlayabilir veya kaldırabilirsiniz.

1. Menü çubuğunda **hata**  >  **ayıklamayı Başlat hata** Ayıkla ' yı seçin veya **F5** tuşunu seçin.

   Program kesme noktası olan satıra ulaştığında, programınız kesme modunda olduğundan, yürütme geçici olarak durmaktadır. Bir kod satırının solunda sarı bir ok, yürütülecek bir sonraki satır olduğunu gösterir.

1. Değişkenin değerini incelemek için `Cardgame::totalParticipants` işaretçiyi üzerine taşıyın `Cardgame` ve ardından araç ipucu penceresinin solundaki genişletme denetiminin üzerine taşıyın. Değişken adı `totalParticipants` ve **12** değeri görüntülenir.

   Değişken için kısayol menüsünü açın `Cardgame::totalParticipants` ve ardından **1. gözcü** penceresinde bu değişkeni göstermek için **Gözcü Ekle** ' yi seçin. Ayrıca bir değişkeni vurgulayabilir ve **1. gözcü** penceresine sürükleyebilirsiniz.

1. Bir sonraki kod satırına geçmek için, menü çubuğunda **Hata Ayıkla**  >  **adımı**' nı seçin veya **F10** tuşunu seçin.

   `Cardgame::totalParticipants` **1. gözcü** penceresindeki değeri artık **13** olarak gösteriliyor.

1. Deyimin kısayol menüsünü açın `return 0;` ve ardından **Imlece Çalıştır**' ı seçin. Kodun solundaki sarı ok, yürütülecek sonraki ifadeye işaret eder.

1. `Cardgame::totalParticipants`Bir `Cardgame` sona erdiğinde sayı azalır. Bu noktada, `Cardgame::totalParticipants` tüm örnekler silindiğinden 0 ' a eşit olması gerekir `Cardgame` , ancak 1. **Gözcü** penceresi 18 ' i `Cardgame::totalparticipants` gösterir . Fark, kodda bir hata olduğunu ve [izlenecek yol: bir proje hatalarını ayıklama (C++)](../ide/walkthrough-debugging-a-project-cpp.md)işlemini tamamlayarak tespit edebilir ve giderebileceğini gösterir.

1. Programı durdurmak için menü çubuğunda Hata   >  **ayıklamayı Durdur** Hata Ayıkla ' yı seçin veya **SHIFT** + **F5** klavye kısayolunu seçin.

## <a name="next-steps"></a>Sonraki Adımlar

**Previous:** [Izlenecek yol: proje derleme (C++)](../ide/walkthrough-building-a-project-cpp.md)<br/>
**Sonraki:** [izlenecek yol: bir projede hata ayıklama (C++)](../ide/walkthrough-debugging-a-project-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)<br/>
